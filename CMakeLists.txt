cmake_minimum_required(VERSION 2.8)
project(ferns)

find_package(OpenCV REQUIRED)
find_package(ZLIB REQUIRED)

include_directories(include)
include_directories(SYSTEM ${OpenCV_INCLUDE_DIRS})

add_executable(ferns_demo
  src/affine_image_generator06.cc
  src/affine_transformation_range.cc
  src/buffer_management.cc
  src/cmphomo.cc
  src/fern_based_point_classifier.cc
  src/ferns.cc
  src/fine_gaussian_pyramid.cc
  src/homography_estimator.cc
  src/homography06.cc
  src/main.cc
  src/mcv.cc
  src/mcvGaussianSmoothing.cc
  src/planar_pattern_detector.cc
  src/planar_pattern_detector_builder.cc  
  src/pyr_yape06.cc
  src/template_matching_based_tracker.cc
)

target_link_libraries(ferns_demo ${OpenCV_LIBRARIES} ${ZLIB_LIBRARIES})
