# Simulations for the UNICORN project
Code for double beta decay in QD simulation. **This framework is derived from code originally developed for the LHCb Electromagnetic Calorimeter Upgrade II. The principal contributors to the original code are Marco Pizzichemi, Loris Martinazzoli, and Matteo Salomoni. For further information, please write to marco.pizzichemi@cern.ch.**

Requires version 11.1.2 of GEANT4 with C++ standard 17
Recommended version of ROOT 6.28/06, which comes with C++ standard 17 as well.


For MacOS:
- check the prerequisities for both ROOT and GEANT4 software
- the recommended way to install root is via homebrew: brew install root
- to install GEANT4: download GEANT4 v11.1.2 source code, create install_11_1_2 and build_11_1_2 directory, cd to the build directory and use the following commands

```
cmake -DCMAKE_INSTALL_PREFIX=../install_11_1_2  -DGEANT4_BUILD_MULTITHREADED=ON -DGEANT4_INSTALL_DATA=ON -DGEANT4_USE_GDML=ON -DGEANT4_USE_QT=ON -DGEANT4_INSTALL_PACKAGE_CACHE=OFF -DCMAKE_CXX_STANDARD=17 -DGEANT4_BUILD_CXXSTD=17 ../geant4-v11.1.2
make -jX, where X is the # of CPU cores you want to use
make install -jX
```

To run the GEANT4 code: first remove the build directory! It still contains cmake references which will be in conflict with your local directories.
After that, compile with

```
./deploy.sh
```

In general, the main sim executable `build/dbd` can be run as

```
 General usage:
 dbd <config_file> [-m macro ] [-r seed] [-o output]
 note: -m -r -o options are optional

 To run cd to the build directory and run:
 ./dbd ../example/config_bc422.cfg
```

One example of a config file is in the `example` folder.




 Be careful to change the absolute path of the `dbd` to reflect your PC configuration.

Remember: **this framework is derived from code originally developed for the LHCb Electromagnetic Calorimeter Upgrade II. The principal contributors to the original code are Marco Pizzichemi, Loris Martinazzoli, and Matteo Salomoni. For further information, please write to marco.pizzichemi@cern.ch.**
