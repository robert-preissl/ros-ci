
cmake_minimum_required(VERSION 3.0.2)
project(ci_test)

find_package(catkin REQUIRED COMPONENTS
  rospy
  std_msgs
)

catkin_package(CATKIN_DEPENDS rospy std_msgs)

catkin_install_python(PROGRAMS move.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

#if(CATKIN_ENABLE_TESTING)
  find_package(rostest REQUIRED)
  add_rostest(sim.test)
  #endif()
