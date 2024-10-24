# ROS 4-Wheeled Robot with Lidar and Camera (robot_description)

## Description

This project implements a 4-wheeled robot model in ROS Noetic using URDF (Unified Robot Description Format). The robot is equipped with simulated lidar and camera sensors for obstacle detection and avoidance (planned functionality). It can be controlled using Teleop Twist Keyboard and visualized with RVIZ.

## Hardware (Simulated)

* 4 Wheels
* Lidar Sensor
* Camera Sensor

## Gazebo Plugins
* Skid Steer Plugin: `gazebo_ros_skid_steer_controller`
* Lidar Plugin: `gazebo_ros_lidar`
* Camera Plugin: `gazebo_ros_camera`

## Software

* ROS Noetic
* `robot_description` (ROS package containing the URDF model)
* `gazebo_ros` (Gazebo ROS simulation tools)
* `teleop_twist_keyboard` (ROS package for keyboard control)
* `rviz` (ROS visualization tool)

## Dependencies

* ROS Noetic installation completed

## Package structure:
Inside the `robot_description` package directory, there are three folders: 
* `urdf` that have the urdf code to create the 4-wheeled robot and the plugins
* `launch` that have the launch file code to open the robot in rivz and gazebo
* `world` that have a file of gazebo world to open while running the code

**note:** to open an empty world file of gazebo comment this line in the launch file code:
```bash
<arg name="world_name" value="$(arg default)"/>
```
into this: 
```bash
<!--arg name="world_name" value="$(arg default)"/-->
```
to change the world file, go to the launch file to this line change `myworld` into your file name:

```bash
<arg name="default" default="$(find robot_description)/world/myworld.world" />
```

## Installation

**1. Create a ROS Workspace:**

```bash
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/src
```

**2. Create a ROS Package:**

```bash
catkin_create_pkg robot_description 
```
* you can change the package name: `robot_description` into any name but you should change this name on these files into the same name you choose

**3. Clone the Repository:**

```bash
git clone https://github.com/starAwesome123/robot_description
```
**4. Build the project:**

```bash
cd ~/catkin_ws
catkin_make
```

## To run the Package

**1. Launch `roscore`:**

```bash
roscore
```
**2. Launch the launch file:**
```Bash
roslaunch robot_description robo.launch
```
**3. Control the Robot:**
```bash
rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```

## Future Plans

* Implement obstacle avoidance algorithms using lidar and camera data.
* Develop path planning and navigation capabilities.
* Explore object recognition and interaction using computer vision.
* Consider task automation for specific routines.
* Implement remote control for operation from a distance.
* Investigate integration with other systems.
