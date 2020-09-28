Synchronized reading of multiple webcams using v4l2
----------------------------------------

Installation
------------
`sudo apt install libjpeg-turbo8-dev libjpeg-dev cmake`
`python setup.py install` for system-wide installation
`python setup.py install --user` for user-specific installation


Use
---
```
import numpy as np
import multicam as mc
with mc.Camsys(['/dev/video0','/dev/video2'], (640,480), 'YUYV', fps=30) as cs:
    try:
        while True: 
            res = cs.read() #RGB images
            print(res.shape)
    except KeyboardInterrupt:
        pass
``` 
