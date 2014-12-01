cmake_minimum_required(VERSION 2.8.3)
project(robot_msgs)

## Find catkin macros and libraries

find_package(catkin REQUIRED COMPONENTS
    sensor_msgs
    roscpp
    std_msgs
    geometry_msgs
    message_generation
)

add_message_files(
	FILES
	imagePosition.msg
	detectedObject.msg
	IrTransformMsg.msg
)

add_service_files(
	FILES
	MakeTurn.srv
        FollowWall.srv
	ResetPWM.srv
)

generate_messages(
	DEPENDENCIES
	std_msgs
	geometry_msgs
	sensor_msgs
)
catkin_package(
	
#  INCLUDE_DIRS include
#  LIBRARIES Object_Recognition
  CATKIN_DEPENDS message_runtime
#  DEPENDS system_lib
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

