# Occlusion-Avoidance-and-DL-for-Tracking
Math Model for Occlusion Avoidance and Tracking by Deep Learning

**Contents**

* [Introduction](#Introduction)
* [Abstract](#Abstract)
* [Highlights of this work](#Highlights)
* [Prerequisites](#prerequisites)
* [Working](#working)
* [Results](#Results)

### Introduction
This repository contain the internship work on "Multi-robot Tracking of Target with Aerial and Ground Robots". This work is carried at LAAS-CNRS, Toulouse, France as a part of my Master thesis internship  2020 under the supervision of Prof. Antonio Franchi in coordination with Mr.Martin Jacquet(PhD) within ANR Project MuroPhen. This project is licensed under the terms of the BSD 3-Clause.

### Abstract
Recent research in Aerial Robotics defines Visual Tracking Methods deployed on Quadrotors. The idea is to study the existing state-of-the-art real time track-
ing algorithms and free to adopt the existing ones considering the problem of occlusion avoidance. Occlusions are mostly unpredictable and still ongoing re-
search in tracking scenarios. The inability to track the object’s features when some obstacle is encountered in between the camera field of view and moving
target are usually termed as ’Phenomenon of Occlusion’. The physical world obstacles causing these phenomenon are called ‘Occlusions’. Basically, occlusions
are two types. One is Spatio-temporal: No occlusion, partial occlusion & full occlusion. Other one is Time sequences based: Regular time occlusions and Irregular time occlusions.

Deploying a tracking algorithm considering the Occlusion Avoidance is a challenging task. This will include exploitation of the following parameters: geometric, photo-metric, motion, time, camera, feedbacks, control loops, real time stability, sensors, UAV dynamics etc. One has to build his own environment and
the required dataset in indoor or outdoor arena allotted to him. This work states the novel & spanking new solution for Occlusion Aviodance through the Time of
Occlusion concept to drive or navigate or control the UAV in the 3D environment. Then after deploy the tracking algorithm for tracking the moving target. Deep
Learning Tools are observed as profound methods and provide effective results (enabling optimization efficiently).

After a rigorous study of 10 Standard Robotic papers and over 20 papers on state-of-the-art Deep Neural Networks, the latest evolutions like YOLO, RetinaNet and Joint Monocular 3D Tracking surely believed to be future milestones upon using these tracking networks on Aerial Vehicles. Each one of them is expected to do potentially well & therefore these algorithms are tested and reported with qualitative results.

### Highlights:
1. A Novel Math Model development: Refer chapter-3 in this thesis document or slide no.8 & 9 from the thesis ppt
2. Tracking by Deep Learning Models: YOLOv3, YOLOv4 and Detectron2
3. Use of GPU with CUDA, CuDNN
4. Tuning YOLO and Detectron2 to Depth based Tracking system

### Prerequisites
#### YOLOv3:
* Transfer Learning – pre-trained net, pretrained weights, predef-annotations
* TensorFlow 1.15, Keras 2.2.4, Numpy 1.16, Opencv 3.6.9,python 3.2.4.17
* batch size: 8 (can be 8 or 32). Batch Norm Epsilon= 1e-5, leaky ReLU=0.1, anchor boxes - 9 no.s, epoches: CPU
* Backbone: Darknet-53 residual connections, 72 Conv. Layers, Upsample layer, Non-max suppression
* COCO Dataset: 80 classes
#### YOLOv4:
* Opencv>=2.4, intel i7, cmake>=3.8, openmp, git, g++,
* darknet backbone, for GPU usage: CUDA 10.0, CuDNN >=7.0
#### Detectron2:
* RetinaNet includes mask RCNN
* Written in Python - powered by Pytorch
* Uses COCO Dataset
* Multiple Networks grouped
* python>=3.6, Pytorch>=1.4, torchvision, pycocotools,
* opencv-python, opencv>=4, gcc>=5, CUDA 10.1, CuDNN >=7.0

### Working
#### a. Run YOLOv3 webcam based tracking (image_detect.py  is the main file)
1. Clone this repo. Download YOLOv3 weights from YOLO website, 
   or use: wget https://pjreddie.com/media/files/yolov3.weights
2. Copy downloaded weights file to model_data folder.
3. Convert Darknet YOLO to Keras:
   python convert.py model_data/yolov3.cfg model_data/yolov3.weights model_data/yolo_weights.h5
4. Test YOLO v3 with image_detect.py or realtime_detect.py (modify used model and classes according to your needs)
   1. output of YOLOv3 CPU my PC found here: https://youtu.be/J-xz2tQTK1c
   2. output of YOLOv3 CPU LAAS PC found here: https://youtu.be/ytDOpJ9F0mc

#### b. Run YOLOv4 and Detectron2 webcam based tracking (all tested on LAAS PC)
1. for YOLOv4 webcam object tracking - follow the commands instructed in 'history linux20' file
2. output of YOLOv4 CPU found here: https://youtu.be/RpzwnDiODpA
3. output of YOLOv4 GPU found here: https://youtu.be/06AHNylwcoo
4. for Detectron2 webcam object tracking - follow the commands instructed in 'history linux20' file
5. output of Detectron2 CPU found here: https://youtu.be/rZjaWulg4lQ
6. output of Detectron2 GPU found here: https://youtu.be/LFksvpn_jSs

Thanks to YOLOv4 and Detectron2 software, they are cloned as it is.

Their installations are adopted to our PC configurations in proper way and then it was magic. 

### Results
The YOLOv3, YOLOv4 and Detectron2 are tested on various PC configurations using webcam
![traj](others/performance.png)

### Future Work
1. Tuning YOLO and Detectron2 to Depth based Tracking using "Triangle similarity technique"
2. Implementing the software on Robotic platforms
(Under construction)
