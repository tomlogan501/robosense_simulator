cmake_minimum_required(VERSION 3.8)
project(robosense_description)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(urdf REQUIRED)

#this must be added so launch files can be used from CLI
install(DIRECTORY
  urdf
  meshes
  launch
  rviz
  world
  DESTINATION share/${PROJECT_NAME}
)

ament_package()