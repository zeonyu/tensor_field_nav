# tensor_field_nav (Tensor Field Based Navigation)

## Introduction

Tensor_field_nav package is used for autonomous mapping of unkonown indoor scenes guided by time-varing tensor field. It leverages rgbd sensor like kinect to scan environment, and receives scene geometry information from octomap. Based on the partially mapping scene, a 2D tensor field is computed on the floor plane, under the constraints of 2d grid map. The robot is guided by the field with smooth paths, which are locally formed with advection and globally planned with help of the field topology.

During online scanning, the tensor field is updated in real-time, conforming to the incrementally reconstructed scene. To ensure a smooth robot path when advecting over the time-varying field, we propose a space-time optimization of tensor fields via imposing both spatial smoothness and temporal coherence. There are several important advantages of tensor field guided navigation. First, tensor fields are orientation-free and thus contain much less singularities (degenerate points), as compared to vector fields which are predominantly used in the literature. Fewer singularities lead not only to smoother path advection, which is critical for quality reconstruction, but also to more efficient navigation due to less ambiguity. In addition, tensor fields are sink-free, avoiding the issue of local trapping. Most importantly, the topological skeleton of a tensor field, comprised of all degenerate points and the separatrices connecting them, can be viewed as a routing graph. With this global structure, one can achieve global path planning for efficient scene scanning.

## Requirements

This package relies on some third dependencies, it requires installation of CUDA, Opencv.


## Download and Installation

Dowload tensor_field_nav package with the following command to your catkin workspace.
```
catkin_ws/src$ git clone 
catkin_ws/src$ cd ..
catkin_ws$ catkin_make
```
## Run
roslaunch tensor_field_nav_core complete_run.launch

roslaunch octomap_tensor_field octomap_mapping.launch




