# CarND-Path-Planning-Project
Self-Driving Car Engineer Nanodegree Program
---



---
## Introduction

In this project an algorithm for path planning will be implemented for an ego car in simulation environment to drive itself though a test track around 7 Km. Every 0.02 second the simulator provides car information and fusion information of other cars in the highway and take the generated trajactory to control the ego car.

## Code model

The path planning algorithm is implemented in three steps: vehicle prediction, behavior generation and trajectory generation

![Screenshot](https://github.com/truongconghiep/CarND-Path-Planning-Project/blob/master/diagram/PathPlanning.jpg)

### Prediction

In this step sensor fusion data is provided by the simulator and used as input for prediction of vehicles on the road. The sensor fusion data is including Frenet coordination d and s and component velocity vx and vy in cartestian system. From this information position of other cars on the road will be predicted, such as next d and s coordination of the other cars.

If another car is driving on the same line of the ego car and the distance between them is smaller than 30 meters, it will be recognized by the ego car.
If another car is driving on the right or left lane to the ego car and the car is in 30 meters in front of the ego car or 10 meters behind the ego car, it will be recognize by the ego car.

### Behavior generation

In this step the reaction of the car on situations on the road will be generated. If another car is detected ahead, the ego car will change to the left or right lane if no car is detected on these lanes. Otherwise it will slow down and follows the car ahead and waits until other lanes are free. If no car is detected ahead the ego car, it will keep driving on the same lane if the current lane is in the middle of the road. Otherwise it will try to move to the middle lane if the lane is not occupied by other vehicles. If the middle lane is not free the ego car will keep driving ahead in the same lane until the middle lane free.

### Trajectory generation













