**To set up the GUI on a Windows Machine :**

1. Run this in the terminal on Clion (Powershell):

git clone https://github.com/glfw/glfw extern/glfw

2. In CMakeLists.txt Replace the line find_package(glfw3 3.3 REQUIRED) with

set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
add_subdirectory(extern/glfw)

3. Re-Build the Project

Menu -> Build -> Build Project

**To Set up the GUI on a MAC**
Use Homebrew (Makesure homebrew is installed)
1. Run this in the terminal on Clion

brew install glfw

2. Depending of if you have Apple Silicon or Intel chip (M series are Apple Silicon, others are Intel), run the following command

Apple Silicon :
cmake -S . -B build -DCMAKE_PREFIX_PATH=/opt/homebrew
cmake --build build

Intel:
cmake -S . -B build -DCMAKE_PREFIX_PATH=/usr/local
cmake --build build

3.In CMakeLists.txt:

find_package(glfw3 3.3 REQUIRED)
target_link_libraries(app PRIVATE glfw)
