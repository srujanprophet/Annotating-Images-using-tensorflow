# Annotating-Images-using-tensorflow
This project can detect objects in images , videos and webcam using pre-trained models.

## Setting up the environment
1. Conda is recommended. You can use an existing environment or create a new one as follows.
``` 
conda create -n TensorFlow_api python=3.5 numpy pillow
activate TensorFlow_api
```
2. Then, install dependencies
```
pip install TensorFlow-gpu
conda install -c menpo opencv
conda install -c conda-forge imageio
pip install tqdm, moviepy
```
3. Next, you need to get the tensorflow object detection API project. Can be done by 
```
mkdir api_project . # creating local directory
cd api_project 
git init
git remote add -f origin https://github.com/tensorflow/models.git # Fetching the files
git config core.sparseCheckout true
echo "research/object_detection/*" >> .git/info/sparse-checkout
git pull origin master # Checking out to make available locally
```
4. The TensorFlow object detection API uses protobufs, protocol buffers -- Google's data interchange format.
Instruction for compiling are :
  #### Windows
  First, unpack the protoc-3.2.0-win32.zip that can be found at https://github.com/google/protobuf/releases into the project folder. Now you should have a new protoc-3.4.0-win32 directory, containing a readme.txt and two directories, bin, and include. The folders contain a precompiled binary version of the protocol buffer compiler (protoc). All you have to do is add the protoc-3.4.0-win32 directory to the system path.

After adding it to the system path, you can execute the following command:
```
protoc-3.4.0-win32/bin/protoc.exe object_detection/protos/*.proto --python_out=.
```

5. For <em>Unix</em> environments, the installation procedure for protobuf can be done using shell commands, just follow the instructions available at https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/installation.md.

