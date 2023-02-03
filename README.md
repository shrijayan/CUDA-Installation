# CUDA Installation Guide for Jetson Nano
This repository contains the necessary steps to install CUDA on a Jetson Nano device. CUDA is a parallel computing platform and API that makes use of the GPU to perform complex computations faster than on a CPU alone.

## Prerequisites
Before starting the CUDA installation, you should have a Jetson Nano with at least the following specs:

* A Jetson Nano Developer Kit with at least 4 GB of memory
* A microSD card with at least 16 GB of storage
* A USB keyboard and mouse
* A monitor with an HDMI input
* An HDMI cable
* A 5V power supply with at least 4A of current

## Step 1: Update the System
Start by updating the system to ensure that all packages are up-to-date. Open a terminal and enter the following commands:



```sudo apt-get update
sudo apt-get upgrade```

## Step 2: Install CUDA
Next, download the CUDA Toolkit for Jetson Nano from the NVIDIA website. The version you download should match the version of the Jetson Nano you are using.

After downloading the toolkit, open a terminal and navigate to the directory where the file is stored. Run the following command to install CUDA:

Copy code
```sudo sh cuda_filename.run
Where cuda_filename.run is the name of the file you downloaded.```

Follow the instructions in the installer to complete the installation process.

## Step 3: Update Paths
After installing CUDA, you need to update your system's PATH and LD_LIBRARY_PATH environment variables to include CUDA. Open your .bashrc file with a text editor and add the following lines at the end of the file:


Copy code
export PATH=$PATH:/usr/local/cuda/bin
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/cuda/lib64
Save the changes to the file and then run the following command in the terminal to apply the changes:


Copy code
source ~/.bashrc

## Step 4: Verify the Installation
To verify that the installation was successful, run the following command in the terminal:

Copy code
nvidia-smi

You should see output similar to the following, which indicates that CUDA is installed and functioning correctly on your Jetson Nano:


Copy code
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 450.51.05    Driver Version: 450.51.05    CUDA Version: 11.0     |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  NVIDIA Tegra X1    Off  | 00000000:00:00.0 Off |                  N/A |
| N/A   43C    P0    N/A /  N/A |    813MiB /  4051MiB |      0%      Default |
+-------------------------------+----------------------+----------------------+

+-----------------------------------------------------------------------------+
| Processes:                                                       GPU Memory |
|  GPU       PID   Type   Process name                             Usage      |
|=============================================================================|
