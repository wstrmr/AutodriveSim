# AutoDriveSim
AutoDrive simulation using opendavinci

![Alt text](Diagram.png?raw=true)

###Instructions
This guide assumes you are using the [pre-built virtual machine image](http://www.cse.chalmers.se/%7Ebergerc/msv4/2015-01-22_MiniSmartVehicles4.ova) (user:msv)(pass:msv).
####Download the Repository
```
cd ~
git clone git@github.com:davidkron/AutodriveSim.git
```
####Install OpenCV
Follow [this installation guide](http://docs.opencv.org/3.0-last-rst/doc/tutorials/introduction/linux_install/linux_install.html).
#####Register OpenCV Libraries
```
sudo echo "/usr/local/lib" >> /etc/ld.so.conf.d/opencv.conf
sudo ldconfig
sudo echo "PKG_CONFIG_PATH=$PKG_CONFIG_PATH:/usr/local/lib/pkgconfig" >> /etc/bash.bashrc
sudo echo "export PKG_CONFIG_PATH" >> /etc/bash.bashrc
```
**\*IMPORTANT:\*** Restart computer or logout&login for OpenCV to work properly.
####Compile and Install OpenDaVINCI
Create installation directory for the OpenDaVINCI code (this repository's code).
```
sudo mkdir /opt/odv
sudo chown msv:msv /opt/odv
```
Finally, compile and install.
```
cd ~/AutodriveSim
./build.sh
```
####Run OpenDaVINCI
```
cd ~/AutodriveSim
./autodrive.sh
```

###Buildscripts
* **build.sh** - Generates and compiles makefiles (run this the first time and whenever you make cmake modifications)
* **compile.sh** - Only compiles from makefiles
* **autodrive.sh** - Runs the necessary components for simulation
