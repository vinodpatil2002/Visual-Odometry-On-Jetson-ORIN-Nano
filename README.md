# Visual-Odometry-On-Jetson-ORIN-Nano
Visual Odometry using ORB SLAM on NVIDIA's Jetson ORIN Nano with Stereo Camera input.

## Dependencies 
- OpenCV  (Required 4.8.0)
- Eigen (Required 3.2)
- Pangolin (Required 0.6)
- DepthAI 

All the commands required are mentioned below 



## Installing Dependencies 

### Other : 
  ```
$ sudo apt update && sudo apt upgrade
$ sudo apt-get install cmake
$ sudo apt-get install libopenblas-dev
```

### OpenCV :
  - Install OpenCV from [this link](http://techawarey.com/programming/install-opencv-c-c-in-ubuntu-18-04-lts-step-by-step-guide/) .
  
### Eigen 3.2 :
```
$ wget https://gitlab.com/libeigen/eigen/-/archive/3.2.10/eigen-3.2.10.tar.gz
$ tar xzf eigen-3.2.10.tar.gz
$ cd eigen-3.2.10
$ mkdir build && cd build 
$ cmake ..
$ sudo make install
```

### Pangolin v0.6 :

```
$ sudo apt-get install libglew-dev cmake libpython2.7-dev
$ wget https://github.com/stevenlovegrove/Pangolin/archive/v0.6.tar.gz
$ tar -xzvf v0.6.tar.gz
$ cd Pangolin-0.6
$ mkdir build && cd build 
$ cmake ..
$ make -j4
```
### Depth AI :
```
$ git clone https://github.com/luxonis/depthai-core.git
$ cd depthai-core
$ git submodule update --init --recursive
$ cmake -S. -Bbuild -D'BUILD_SHARED_LIBS=ON'
$ cmake --build build
```
Usually if you install DepthAI in the current folder there is a chance you will get "No such file or directory error".
So it would be wise to copy all the header and the required files in `usr/local/include/` directory.
You will get to know once you get the above error so just copy those files in the location mentioned.





## Installing ORB SLAM :
 - The present repo doesn't run on higher versions of OpenCV.
 - Clone this [Repository](https://github.com/IHKYoung/ORB_SLAM2.git) instead.
 
### Commands for installing :

```
$ git clone https://github.com/vinodpatil2002/Visual-Odometry-On-Jetson-ORIN-Nano.git
$ cd Visual-Odometry-On-Jetson-ORIN-Nano/ORB_SLAM2
$ ./build.sh
```



Note : Remember to remove the build files from the directory where it's built.

```
$ rm -rf build
```

### Examples :
```
./Examples/Monocular/mono_tum Vocabulary/ORBvoc.txt Examples/Monocular/TUMX.yaml PATH_TO_SEQUENCE_FOLDER
```

### Live Input:
Connect stereo camera to your Jetson Nano board and make sure it's connected properly.
```
./Examples/Monocular/test
```

If any minor errors while installing, refer to the issues mentioned in the original repository or any other online sites or AI.



## Authors

- [@vinodpatil2002](https://github.com/vinodpatil2002)
- [@ankitraichur](https://github.com/ankitraichur/)

