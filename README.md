READ ME
Ball handling robot

Assignment 2 Mobile Robotics PDE4430
Ball Handling Robot - A ROS-based robot simulation capable of manipulating balls using a gripper and a depth camera.

Motivation
The motivation behind this project is to develop a robot simulation that will demonstrate the capabilities of a ball-handling robot. The project aims to show the integration of a gripper and a depth camera in a ROS environment, allowing the robot to grasp and manipulate balls with precision.

Build status
The current construction of the project is stable and working as expected. There are no known errors or bugs that require your immediate attention.

Code style
The code for this project follows the ROS coding style guidelines for consistency and readability.

Screenshots

![image](https://github.com/robofan45/ass2VRDF/assets/115145225/70ddfb19-43a4-4bae-a9b5-cedfb0fbd367)

Technology/framework used
ROS (Robot Operating System)
Gazebo and Rviz Simulator.
URDF (Unified Robot Description Format)
Xacro (XML Macros)

Characteristics of Robot
Four-wheeled robot base for stable mobility
Vertically oriented wheels for smooth movement
Two-finger gripper to grab balls.
Depth camera to see the environment and detect balls.
ROS-based architecture for easy integration and control

Code examples
The main code of the ball manipulation robot is written in URDF format. Here is a short overview of the code structure:

- The `base_link` represents the main body of the robot.
- The four-wheel links (`front_left_wheel`, `front_right_wheel`, `rear_left_wheel`, `rear_right_wheel`) are connected to the base link by continuous joints.
- The `gripper_base` link is fixed to the base link using a fixed joint.
- The "clamp" link represents the main body of the calliper and is connected to the calliper base by a prismatic joint.
- Prismatic joints join two gripper finger links (`gripper_finger_left`, `gripper_finger_right`) to the gripper link.
- The `camera_link` represents the depth camera and is connected to the base link via a fixed joint.

##Clamp functionality
The gripper of this robot consists of one "gripper" link and two "gripper_finger" links. The gripper is connected to the `gripper_base` link, which in turn is connected to the `base_link` of the robot.

The gripper fingers are controlled by prismatic joints called `gripper_finger_left_joint` and `gripper_finger_right_joint`. These joints allow the fingers to move along the Y axis, allowing the gripper to open and close.

The `gripper_finger_right_joint` is set to mimic the `gripper_finger_left_joint` with a multiplier of -1. This means that when the left finger moves, the right finger moves in the opposite direction, allowing the gripper to grip objects symmetrically.

## Facility
1. Install ROS following the official ROS installation guide for your OS.
2. Clone this repo to your ROS workspace:
             ```
             CD ~/catkin_ws/src
             git clone https://github.com/your-username/ball-handling-robot.git
             ```
3. Build the package using catkin:
             ```
             CD ~/catkin_ws
             catkin_make
             ```
4. Get the ROS configuration file:
             ```
             source ~/catkin_ws/devel/setup.bash
             ```

How to use?
1. Start the Gazebo simulation:
             ```
             roslaunch ball_handling_robot mirador.launch
             ```
2. Start RViz visualization:
             ```
             roslaunch ball_handling_robot rviz.launch
             ```
3. Control the robot using the provided ROS themes and services.

Credits
The ROS tutorials, classes and documentation were a valuable resource in the development of this project. The Gazebo simulator and its plugins were used to create the simulation environment.
and thanks to Dr Sameer Kishore for supervision and guardians. 
