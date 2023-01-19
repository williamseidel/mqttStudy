set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE AUTOUIC ON)

include_directories(${CMAKE_CURRENT_SOURCE_DIR})

include_directories($ENV{PAHO_MQTT_C_ROOT}/include)
include_directories($ENV{PAHO_MQTT_CPP_ROOT}/include)

link_directories($ENV{PAHO_MQTT_C_ROOT}/lib)
link_directories($ENV{PAHO_MQTT_C_ROOT}/lib64)
link_directories($ENV{PAHO_MQTT_CPP_ROOT}/lib)
link_directories($ENV{PAHO_MQTT_CPP_ROOT}/lib64)

file(GLOB srcs
	"src/*.h"
	"*src/*.cpp")

add_executable(pub
	${srcs})

target_link_libraries(pub
	paho-mqttpp3
	paho-mqtt3a)


