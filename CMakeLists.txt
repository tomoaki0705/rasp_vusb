cmake_minimum_required(VERSION 3.1)

set(SOURCE 
        rasp_vusb_server/IPResolver.cpp
        rasp_vusb_server/KeyboardDevice.cpp
        rasp_vusb_server/main.cpp
        rasp_vusb_server/MouseDevice.cpp
        rasp_vusb_server/NoResetEvent.cpp
        rasp_vusb_server/UsbEmulator.cpp
        rasp_vusb_server/VUsbServer.cpp
    )

add_executable(raspKM ${SOURCE})
find_package(Threads REQUIRED)
find_package(OpenSSL REQUIRED)
target_link_libraries(raspKM Threads::Threads)
target_link_libraries(raspKM OpenSSL::SSL)
