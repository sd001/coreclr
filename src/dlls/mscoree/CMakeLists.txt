include_directories("../../inc")

set(CLR_SOURCES
    mscoree.cpp
)

if(WIN32)
set(CLR_SOURCES ${CLR_SOURCES}
    comcallunmarshal.cpp
    delayload.cpp
    Native.rc
)

set (DEF_SOURCES
  mscorwks_ntdef.src
)
convert_to_absolute_path(DEF_SOURCES ${DEF_SOURCES})
else(WIN32)
set(CLR_SOURCES ${CLR_SOURCES}
    unixinterface.cpp
)
endif(WIN32)

convert_to_absolute_path(CLR_SOURCES ${CLR_SOURCES})
add_subdirectory(coreclr)
