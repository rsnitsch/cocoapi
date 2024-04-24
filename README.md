# Fork of [gautamchitnis / cocoapi](https://github.com/gautamchitnis/cocoapi)

## This fork's README:

This fork is based on `gautamchitnis/cocoapi` which is already a fork of the original repo `philferriere/cocoapi`.

I created this fork to fix some outdated code in order to be able to run the code from the torchvision
tutorial (https://pytorch.org/tutorials/intermediate/torchvision_tutorial.html) successfully on Windows.

### Changes compared to `gautamchitnis/cocoapi`

#### Replaced np.float with np.float64

Fixes AttributeError: module 'numpy' has no attribute 'float':

    in File "...\pycocotools\cocoeval.py", line 378, in accumulate
        tp_sum = np.cumsum(tps, axis=1).astype(dtype=np.float)
                                                     ^^^^^^^^

Background: np.float has been marked deprecated in numpy 1.20 and has been finally removed 
in numpy 1.24. See: https://stackoverflow.com/a/74861894/623685
