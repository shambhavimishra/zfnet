# zfnet
ZFNet or deconvnet built by Matthew Zeiler and Rob Fergus and trained on a GTX 580 GPU for twelve days
Developed a visualization technique named Deconvolutional Network “deconvnet” because it maps features to pixels.
It was an improvement on AlexNet by tweaking the architecture hyperparameters, in particular by expanding the size of the middle convolutional layers and making the stride and filter size on the first layer smaller
It project the feature activations back to the input pixel space and perform the sensitivity analysis of the classifier output by occluding/obstruct portions of the input image, revealing which parts of the scene are important for classification
operation of a convnet requires interpreting the feature activity in intermediate layers
A way to map these activities back to the input pixel space, showing what input pattern originally caused a given activation in the feature maps
A deconvnet can be thought of as a convnet model that uses the same components (filtering, pooling) but in reverse, so instead of mapping pixels to features does the opposite.
Then we successively 
Unpool
Rectify
Filter 
To reconstruct the activity in the layer beneath that gave rise to the chosen activation. This is then repeated until input pixel space is reached.
ZFNet used filters of size 7x7 and a decreased stride value, instead of using 11x11 sized filters in the first layer 
AlexNet to improved ZFNET 
CONV1: change from (11x11 stride 4) to (7x7 stride 2) 
CONV3,4,5: instead of 384, 384, 256 filters use 512, 1024, 512
ImageNet top 5 error: 16.4% -> 11.7%
