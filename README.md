# DeepDreamVideo (w/ multithreading) - In development
Implementing **#deepdream** on video

**Creative Request**

It would be very helpful for other deepdream researchers, if you could **include the used parameters in the description of your youtube videos**. You can find the parameters in the image filenames.

Included experiment: Deep Dreaming Fear & Loathing in Las Vegas: the Great Fan Francisco Acid Wave

The results can be seen on youtube: https://www.youtube.com/watch?v=oyxSerkkP4o

Mp4 not yet destroyed by youtube compression also at [mega.nz](https://mega.nz/#!KldUTKKD!38qj6WtEOE4pno90dAW98gkNK2O3tvz6ZwKTxpHJWFc) together with [original video file](https://mega.nz/#!X9MWWDTQ!lbC7C5B4incMkLGVM00qwI4NP-ifi2KcqsmfsdIm_E0).

All single processed + unprocessed frames are also at [github](https://github.com/graphific/Fear-and-Loathing-experiment)

![deepdreamanim1](http://media.giphy.com/media/l41lRx92QqsIXy5MI/giphy.gif "deep dream animation 1")
![deepdreamanim2](http://media.giphy.com/media/l41lSzjTsGJcIzpKg/giphy.gif "deep dream animation 2")

##INSTALL Dependencies

A good overview (constantly being updated) on which software libraries to install & list of web resources/howto is at reddit: https://www.reddit.com/r/deepdream/comments/3cawxb/what_are_deepdream_images_how_do_i_make_my_own/


##Usage:

Extract 25 frames a second from the source movie

`./1_movie2frames.sh ffmpeg [movie.mp4] [directory]`

Let a pretrained deep neural network dream on it frames, one by one, taking each new frame and adding 0-50% of the old frame into it for continuity of the hallucinated artifacts, and go drink your caffe

`python 2_dreaming_time.py -i [regular frames directory] -o [deepdream frames directory]`

Once enough frames are processed (the script will cut the audio to the needed length automatically) or once all frames are done, put the frames + audio back together:

`./3_frames2movie.sh [deepdream frames directory] [original_video_with_sound]`




## An investigation of using the MIT Places trained CNN (mainly landscapes):

https://www.youtube.com/watch?v=6IgbMiEaFRY


## Installing DeepDream:

- original Google code is relatively straightforward to use: https://github.com/google/deepdream/blob/master/dream.ipynb

- gist for osx: https://gist.github.com/robertsdionne/f58a5fc6e5d1d5d2f798

- docker image: https://registry.hub.docker.com/u/mjibson/deepdream/

- booting preinstalled ami + installing caffe at amazon: https://github.com/graphific/dl-machine

- general overview of convolutinal nets using Caffe: https://github.com/graphific/DL-Meetup-intro/blob/master/PyConSe15-cat-vs-dog.ipynb

- or using lasagne: http://www.slideshare.net/roelofp/python-for-image-understanding-deep-learning-with-convolutional-neural-nets


## Credits

Roelof | [KTH](www.csc.kth.se/~roelof/) & [Graph Technologies](http://www.graph-technologies.com/) | [@graphific](https://twitter.com/graphific)

Multithreading by WaffleHacker (still in development)
