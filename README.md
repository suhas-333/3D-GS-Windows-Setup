
# Prerequisites

- __Git__ - [here ](https://git-scm.com/downloads). Follow default installation instructions. You can test to see if you have it already installed by typing ```git --version``` into command prompt
- __Conda__ - [Anaconda](https://www.anaconda.com/download) 
- __CUDA Toolkit__ -  11.8 [here](https://developer.nvidia.com/cuda-toolkit-archive). You can check which version of CUDA Toolkit you have installed by typing ```nvcc --version``` into command prompt.
- __Visual Studio__ 2019 [here](https://www.techspot.com/downloads/downloadnow/7241/?evp=70f51271955e6392571f575e301cd9a3&file=9642). Make sure you add __Desktop Development with C++__ when installing
- __COLMAP__ - [here](https://github.com/colmap/colmap/releases)
- __ImageMagik__ - [here](https://imagemagick.org/script/download.php)
- __FFMPEG__ - [here](https://ffmpeg.org/download.html)

# Clone the Repository

Run Powershell as administrator

```git clone https://github.com/graphdeco-inria/gaussian-splatting --recursive``` 

# Set up the conda environment 

cd into the repo folder where environment.yml is present 

```shell
SET DISTUTILS_USE_SDK=1                         #On windows 
conda env create --file environment.yml
conda activate gaussian_splatting
```

In case there are dependency errors and the env creation stops in the middle, delete the environment, fix dependencies and re-run. 

```shell 
conda env remove -n gaussian_splatting
```
[Try pip install ninja]

# Train a model 

Download the T&T+DB COLMAP (650MB) [here](https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/datasets/input/tandt_db.zip).
Download this tandt_db.zip file.

put it in a data folder.

```shell
python train.py -s data/tandt/truck --iterations 7000    #default is 30000
```

At the end of training it puts all files in a new output folder. 


# Run the model

Set up viewers and run using [link](https://github.com/suhas-333/3D-GS-Viewer)

```shell
cd "C:\Path\To\Where\You\Extracted\viewers\bin" 

.\SIBR_gaussianViewer_app.exe -m "C:\Path\To\Your\ae542f1e-6 or folder name"
```
