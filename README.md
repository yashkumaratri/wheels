# TensorFlow Optimized Wheels

TF wheels to run on new CUDA 9/10 with older TF's : Tested 1.2.1

pip install --ignore-installed --upgrade https://github.com/mind/wheels/releases/download/tf1.2.1-gpu/tensorflow-1.2.1-cp36-cp36m-linux_x86_64.whl


Custom builds for TensorFlow with platform optimizations, including SSE, AVX and FMA. If you are seeing messages like the following with the stock `pip install tensorflow`, you've come to the right place.

```
The TensorFlow library wasn't compiled to use AVX instructions, but these are available on your machine and could speed up CPU computations.
The TensorFlow library wasn't compiled to use AVX2 instructions, but these are available on your machine and could speed up CPU computations.
The TensorFlow library wasn't compiled to use SSE4.1 instructions, but these are available on your machine and could speed up CPU computations.
The TensorFlow library wasn't compiled to use SSE4.2 instructions, but these are available on your machine and could speed up CPU computations.

or:
Your CPU supports instructions that this TensorFlow binary was not compiled to use: SSE4.1 SSE4.2 AVX AVX2 FMA
```

These wheels are built for use on [TinyMind](https://www.tinymind.com), the cloud machine learning platform. If you want to install them on your own Linux box (Ubuntu 16.04 LTS), you can do so with:

```sh
# RELEASE is the git tag like tf1.1-cpu. WHEEL is the full wheel name.
pip --no-cache-dir install https://github.com/mind/wheels/releases/download/{RELEASE}/{WHEEL}
```

The list of all wheels can be found in the [releases page](https://github.com/mind/wheels/releases).

## Versions

Click on the links below to jump to specific release versions. Again, they are built for Ubuntu 16.04 LTS unless otherwise noted.

TF | Builds
-----------|-------
1.1 | [CPU](https://github.com/mind/wheels/releases/tag/tf1.1-cpu), [GPU](https://github.com/mind/wheels/releases/tag/tf1.1-gpu)
1.2 | [CPU](https://github.com/mind/wheels/releases/tag/tf1.2-cpu), [GPU (Python 3.6 only)](https://github.com/mind/wheels/releases/tag/tf1.2-gpu)
1.2.1 | [CPU](https://github.com/mind/wheels/releases/tag/tf1.2.1-cpu), [GPU](https://github.com/mind/wheels/releases/tag/tf1.2.1-gpu)
1.3 | [CPU](https://github.com/mind/wheels/releases/tag/tf1.3-cpu), [GPU with MPI](https://github.com/mind/wheels/releases/tag/tf1.3-gpu)
1.3.1 | [CPU](https://github.com/mind/wheels/releases/tag/tf1.3.1-cpu), [CPU Debug](https://github.com/mind/wheels/releases/tag/tf1.3-cpu-debug), [GPU](https://github.com/mind/wheels/releases/tag/tf1.3.1-gpu), [GPU with MPI](https://github.com/mind/wheels/releases/tag/tf1.3-gpu-mpi)
1.4 | [CPU](https://github.com/mind/wheels/releases/tag/tf1.4-cpu), [CPU Debug](https://github.com/mind/wheels/releases/tag/tf1.4-cpu-debug), [CPU macOS](https://github.com/mind/wheels/releases/tag/tf1.4-cpu-mac), GPU ([CUDA 8](https://github.com/mind/wheels/releases/tag/tf1.4-gpu), [CUDA 9 for Compute 3.7](https://github.com/mind/wheels/releases/tag/tf1.4-gpu-cuda9-37), [CUDA 9 for Compute 3.7/6.0/7.0](https://github.com/mind/wheels/releases/tag/tf1.4-gpu-cuda9), [CUDA 9 generic](https://github.com/mind/wheels/releases/tag/tf1.4-gpu-cuda9-generic), [CUDA 9 without MKL](https://github.com/mind/wheels/releases/tag/tf1.4-gpu-cuda9-nomkl))
1.4.1 | [CPU](https://github.com/mind/wheels/releases/tag/tf1.4.1-cpu), GPU ([CUDA 8](https://github.com/mind/wheels/releases/tag/tf1.4.1-gpu), [CUDA 9](https://github.com/mind/wheels/releases/tag/tf1.4.1-gpu-cuda9), [CUDA 9.1](https://github.com/mind/wheels/releases/tag/tf1.4.1-gpu-cuda91))
1.5 | [CPU](https://github.com/mind/wheels/releases/tag/tf1.5-cpu), GPU ([CUDA 9](https://github.com/mind/wheels/releases/tag/tf1.5-gpu), [CUDA 9 without MKL](https://github.com/mind/wheels/releases/tag/tf1.5-gpu-nomkl), [CUDA 9.1](https://github.com/mind/wheels/releases/tag/tf1.5-gpu-cuda91), [CUDA 9.1 without MKL](https://github.com/mind/wheels/releases/tag/tf1.5-gpu-cuda91-nomkl))
1.6 | [CPU](https://github.com/mind/wheels/releases/tag/tf1.6-cpu), GPU ([CUDA 9.1](https://github.com/mind/wheels/releases/tag/tf1.6-gpu-cuda91), [CUDA 9.1 without MKL](https://github.com/mind/wheels/releases/tag/tf1.6-gpu-cuda91-nomkl))
1.7 | [CPU](https://github.com/mind/wheels/releases/tag/tf1.7-cpu), GPU ([CUDA 9](https://github.com/mind/wheels/releases/tag/tf1.7-gpu-nomkl), [CUDA 9.1, cuDNN 7.1](https://github.com/mind/wheels/releases/tag/tf1.7-gpu-cuda91-nomkl))

Please note that your machine needs to have a relatively new Intel CPU (and Nvidia GPU if you use the GPU version) to be compatible with the wheels below. If the hardware is not up-to-date, the wheels will not work.

Wheels for TensorFlow 1.4.1 and above contain support for GCP, S3 and Hadoop. Compilation flags include:

```
--config=opt --config=cuda --cxxopt=-D_GLIBCXX_USE_CXX11_ABI=0 --copt=-mavx --copt=-msse4.1 --copt=-msse4.2 --copt=-mavx2 --copt=-mfma --copt=-mfpmath=both
```

Wheels you will most likely need are listed below. Need something or a wheel doesn't work for you? File an issue. (Unfortunately, we won't be able to accommodate for requests for Windows wheels, as we don't have Windows machines ourselves.)

Version | Python | Arch | Link
--------|--------|------|-----
1.1 | 2.7 | CPU | https://github.com/mind/wheels/releases/download/tf1.1-cpu/tensorflow-1.1.0-cp27-cp27mu-linux_x86_64.whl
1.1 | 3.5 | CPU | https://github.com/mind/wheels/releases/download/tf1.1-cpu/tensorflow-1.1.0-cp35-cp35m-linux_x86_64.whl
1.1 | 3.6 | CPU | https://github.com/mind/wheels/releases/download/tf1.1-cpu/tensorflow-1.1.0-cp36-cp36m-linux_x86_64.whl
1.1 | 2.7 | GPU | https://github.com/mind/wheels/releases/download/tf1.1-gpu/tensorflow-1.1.0-cp27-cp27mu-linux_x86_64.whl
1.1 | 3.5 | GPU | https://github.com/mind/wheels/releases/download/tf1.1-gpu/tensorflow-1.1.0-cp35-cp35m-linux_x86_64.whl
1.1 | 3.6 | GPU | https://github.com/mind/wheels/releases/download/tf1.1-gpu/tensorflow-1.1.0-cp36-cp36m-linux_x86_64.whl
1.2 | 2.7 | CPU | https://github.com/mind/wheels/releases/download/tf1.2-cpu/tensorflow-1.2.0-cp27-cp27mu-linux_x86_64.whl
1.2 | 3.5 | CPU | https://github.com/mind/wheels/releases/download/tf1.2-cpu/tensorflow-1.2.0-cp35-cp35m-linux_x86_64.whl
1.2 | 3.6 | CPU | https://github.com/mind/wheels/releases/download/tf1.2-cpu/tensorflow-1.2.0-cp36-cp36m-linux_x86_64.whl
1.2 | 3.6 | GPU | https://github.com/mind/wheels/releases/download/tf1.2-gpu/tensorflow-1.2.0-cp36-cp36m-linux_x86_64.whl
1.2.1 | 2.7 | CPU | https://github.com/mind/wheels/releases/download/tf1.2.1-cpu/tensorflow-1.2.1-cp27-cp27mu-linux_x86_64.whl
1.2.1 | 3.5 | CPU | https://github.com/mind/wheels/releases/download/tf1.2.1-cpu/tensorflow-1.2.1-cp35-cp35m-linux_x86_64.whl
1.2.1 | 3.6 | CPU | https://github.com/mind/wheels/releases/download/tf1.2.1-cpu/tensorflow-1.2.1-cp36-cp36m-linux_x86_64.whl
1.2.1 | 2.7 | GPU | https://github.com/mind/wheels/releases/download/tf1.2.1-gpu/tensorflow-1.2.1-cp27-cp27mu-linux_x86_64.whl
1.2.1 | 3.5 | GPU | https://github.com/mind/wheels/releases/download/tf1.2.1-gpu/tensorflow-1.2.1-cp35-cp35m-linux_x86_64.whl
1.2.1 | 3.6 | GPU | https://github.com/mind/wheels/releases/download/tf1.2.1-gpu/tensorflow-1.2.1-cp36-cp36m-linux_x86_64.whl
1.3 | 2.7 | CPU | https://github.com/mind/wheels/releases/download/tf1.3-cpu/tensorflow-1.3.0-cp27-cp27mu-linux_x86_64.whl
1.3 | 3.5 | CPU | https://github.com/mind/wheels/releases/download/tf1.3-cpu/tensorflow-1.3.0-cp35-cp35m-linux_x86_64.whl
1.3 | 3.6 | CPU | https://github.com/mind/wheels/releases/download/tf1.3-cpu/tensorflow-1.3.0-cp36-cp36m-linux_x86_64.whl
1.3 | 2.7 | GPU | https://github.com/mind/wheels/releases/download/tf1.3-gpu/tensorflow-1.3.0-cp27-cp27mu-linux_x86_64.whl
1.3 | 3.5 | GPU | https://github.com/mind/wheels/releases/download/tf1.3-gpu/tensorflow-1.3.0-cp35-cp35m-linux_x86_64.whl
1.3 | 3.6 | GPU | https://github.com/mind/wheels/releases/download/tf1.3-gpu/tensorflow-1.3.0-cp36-cp36m-linux_x86_64.whl
1.3.1 | 2.7 | CPU | https://github.com/mind/wheels/releases/download/tf1.3.1-cpu/tensorflow-1.3.1-cp27-cp27mu-linux_x86_64.whl
1.3.1 | 3.5 | CPU | https://github.com/mind/wheels/releases/download/tf1.3.1-cpu/tensorflow-1.3.1-cp35-cp35m-linux_x86_64.whl
1.3.1 | 3.6 | CPU | https://github.com/mind/wheels/releases/download/tf1.3.1-cpu/tensorflow-1.3.1-cp36-cp36m-linux_x86_64.whl
1.3.1 | 2.7 | GPU | https://github.com/mind/wheels/releases/download/tf1.3.1-gpu/tensorflow-1.3.1-cp27-cp27mu-linux_x86_64.whl
1.3.1 | 3.5 | GPU | https://github.com/mind/wheels/releases/download/tf1.3.1-gpu/tensorflow-1.3.1-cp35-cp35m-linux_x86_64.whl
1.3.1 | 3.6 | GPU | https://github.com/mind/wheels/releases/download/tf1.3.1-gpu/tensorflow-1.3.1-cp36-cp36m-linux_x86_64.whl
1.4 | 2.7 | CPU | https://github.com/mind/wheels/releases/download/tf1.4-cpu/tensorflow-1.4.0-cp27-cp27mu-linux_x86_64.whl
1.4 | 3.5 | CPU | https://github.com/mind/wheels/releases/download/tf1.4-cpu/tensorflow-1.4.0-cp35-cp35m-linux_x86_64.whl
1.4 | 3.6 | CPU | https://github.com/mind/wheels/releases/download/tf1.4-cpu/tensorflow-1.4.0-cp36-cp36m-linux_x86_64.whl
1.4 | 2.7 | GPU | https://github.com/mind/wheels/releases/download/tf1.4-gpu/tensorflow-1.4.0-cp27-cp27mu-linux_x86_64.whl
1.4 | 3.5 | GPU | https://github.com/mind/wheels/releases/download/tf1.4-gpu/tensorflow-1.4.0-cp35-cp35m-linux_x86_64.whl
1.4 | 3.6 | GPU | https://github.com/mind/wheels/releases/download/tf1.4-gpu/tensorflow-1.4.0-cp36-cp36m-linux_x86_64.whl
1.4.1 | 2.7 | CPU | https://github.com/mind/wheels/releases/download/tf1.4.1-cpu/tensorflow-1.4.1-cp27-cp27mu-linux_x86_64.whl
1.4.1 | 3.5 | CPU | https://github.com/mind/wheels/releases/download/tf1.4.1-cpu/tensorflow-1.4.1-cp35-cp35m-linux_x86_64.whl
1.4.1 | 3.6 | CPU | https://github.com/mind/wheels/releases/download/tf1.4.1-cpu/tensorflow-1.4.1-cp36-cp36m-linux_x86_64.whl
1.4.1 | 2.7 | GPU | https://github.com/mind/wheels/releases/download/tf1.4.1-gpu/tensorflow-1.4.1-cp27-cp27mu-linux_x86_64.whl
1.4.1 | 3.5 | GPU | https://github.com/mind/wheels/releases/download/tf1.4.1-gpu/tensorflow-1.4.1-cp35-cp35m-linux_x86_64.whl
1.4.1 | 3.6 | GPU | https://github.com/mind/wheels/releases/download/tf1.4.1-gpu/tensorflow-1.4.1-cp36-cp36m-linux_x86_64.whl
1.5 | 2.7 | CPU | https://github.com/mind/wheels/releases/download/tf1.5-cpu/tensorflow-1.5.0-cp27-cp27mu-linux_x86_64.whl
1.5 | 3.5 | CPU | https://github.com/mind/wheels/releases/download/tf1.5-cpu/tensorflow-1.5.0-cp35-cp35m-linux_x86_64.whl
1.5 | 3.6 | CPU | https://github.com/mind/wheels/releases/download/tf1.5-cpu/tensorflow-1.5.0-cp36-cp36m-linux_x86_64.whl
1.5 | 2.7 | GPU | https://github.com/mind/wheels/releases/download/tf1.5-gpu/tensorflow-1.5.0-cp27-cp27mu-linux_x86_64.whl
1.5 | 3.5 | GPU | https://github.com/mind/wheels/releases/download/tf1.5-gpu/tensorflow-1.5.0-cp35-cp35m-linux_x86_64.whl
1.5 | 3.6 | GPU | https://github.com/mind/wheels/releases/download/tf1.5-gpu/tensorflow-1.5.0-cp36-cp36m-linux_x86_64.whl
1.6 | 2.7 | CPU | https://github.com/mind/wheels/releases/download/tf1.6-cpu/tensorflow-1.6.0-cp27-cp27mu-linux_x86_64.whl
1.6 | 3.5 | CPU | https://github.com/mind/wheels/releases/download/tf1.6-cpu/tensorflow-1.6.0-cp35-cp35m-linux_x86_64.whl
1.6 | 3.6 | CPU | https://github.com/mind/wheels/releases/download/tf1.6-cpu/tensorflow-1.6.0-cp36-cp36m-linux_x86_64.whl
1.6 | 2.7 | GPU | https://github.com/mind/wheels/releases/download/tf1.6-gpu-cuda91/tensorflow-1.6.0-cp27-cp27mu-linux_x86_64.whl
1.6 | 3.5 | GPU | https://github.com/mind/wheels/releases/download/tf1.6-gpu-cuda91/tensorflow-1.6.0-cp35-cp35m-linux_x86_64.whl
1.6 | 3.6 | GPU | https://github.com/mind/wheels/releases/download/tf1.6-gpu-cuda91/tensorflow-1.6.0-cp36-cp36m-linux_x86_64.whl

## Help!

This section contains tips for debugging your setup. Seriously though, try [TinyMind](https://www.tinymind.com) out and you will never need to waste time debugging again. We also have [Docker images](https://hub.docker.com/r/tinymind/tensorflow/) that you can use on your own machines. If this section doesn't solve your problem, be sure to file an issue.

### CUDA

Different TensorFlow versions support/require different CUDA versions:

TF | CUDA | cuDNN | Compute Capability
-----------|------|-------|-------------------
1.1, 1.2 | 8.0 | 5.1 | 3.7 (K80)
1.2.1-1.3.1 | 8.0 | 6.0 | 3.7
1.4 | 8.0/9.0 | 6.0/7.0 | 3.7, 6.0 (P100), 7.0 (V100)
1.4.1 | 8.0/9.0/9.1 | 6.0/7.0 | 3.7, 6.0, 7.0
1.5 | 9.0/9.1 | 7.0 | 3.7, 6.0, 7.0
1.6 | 9.1 | 7.0 | 3.7, 6.0, 7.0
1.7 | 9.0/9.1 | 7.0/7.1 | 3.7, 6.0, 7.0

TensorFlow < 1.4 doesn't work with CUDA 9, the current version. Instead of `sudo apt-get install cuda`, you need to do `sudo apt-get install cuda-8-0`. CUDA 8 variants of TensorFlow 1.4 go with cuDNN 6.0, and CUDA 9.x variants go with cuDNN 7.x.

```sh
# Install CUDA 8
curl -O http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_8.0.61-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu1604_8.0.61-1_amd64.deb
sudo apt-get update
sudo apt-get install cuda-8-0

# Install CUDA 9
curl -O http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_9.0.176-1_amd64.deb
sudo dpkg -i cuda-repo-ubuntu1604_9.0.176-1_amd64.deb
sudo apt-key adv --fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/7fa2af80.pub
sudo apt-get update
sudo apt-get install cuda
```

Make sure that CUDA-related environment variables are set properly:

```sh
echo 'export CUDA_HOME=/usr/local/cuda' >> ~/.bashrc
echo 'export PATH=$PATH:$CUDA_HOME/bin' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CUDA_HOME/lib64' >> ~/.bashrc
. ~/.bashrc
```

[Download the correct cuDNN](https://developer.nvidia.com/cudnn) and install it as follows:

```sh
# The cuDNN tar file.
tar xzvf cudnn-9.0-linux-x64-v7.0.tgz
sudo cp cuda/lib64/* /usr/local/cuda/lib64/
sudo cp cuda/include/cudnn.h /usr/local/cuda/include/
```

Missing `libcupti` library? Install it and add it to your `PATH`.

```sh
sudo apt-get install libcupti-dev
echo 'export LD_LIBRARY_PATH=/usr/local/cuda/extras/CUPTI/lib64:$LD_LIBRARY_PATH' >> ~/.bashrc
```

### TensorRT

Certain wheels support TensorRT. To install TensorRT, first download it from [Nvidia's website](https://developer.nvidia.com/tensorrt), and then run:

```sh
sudo dpkg -i nv-tensorrt-repo-ubuntu1604-ga-cuda9.0-trt3.0.4-20180208_1-1_amd64.deb
sudo apt-get update
sudo apt-get install tensorrt
```

### MKL

MKL is [Intel's deep learning kernel library](https://github.com/01org/mkl-dnn), which makes training neural nets on CPU much faster. If you don't have it, install it like the following:

```sh
# If you don't have cmake
sudo apt install cmake

git clone https://github.com/01org/mkl-dnn.git
cd mkl-dnn/scripts && ./prepare_mkl.sh && cd ..
mkdir -p build && cd build && cmake .. && make
sudo make install

echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib' >> ~/.bashrc
```

### Glibc 2.23

Please note that Ubuntu 16.04 LTS is the intended environment. If you have an old OS, you may run into issues with old glibc versions. You may want to check out [discussions here](https://github.com/mind/wheels/issues/7) to see if they would help.

### MPI

Using a wheel with MPI support? Be sure to run `sudo apt-get install mpich`.
