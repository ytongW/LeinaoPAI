
FROM nvidia/cuda:10.0-cudnn7-devel-ubuntu16.04

MAINTAINER marearth@mail.ustc.edu.cn

RUN apt-get clean    && \
    cd /var/lib/apt   &&   mkdir -p lists/partial      &&\
    apt-get clean   && \   
    apt-get update   &&\     
    apt-get install -y --no-install-recommends \
    build-essential cmake  git  curl vim  wget  tree  \
    python-dev python-pip python-tk\
    python3-dev  python3-pip python3-tk  \
    libopenblas-dev liblapack-dev   \
    mlocate htop tar zip openssh-server  \
    screen  unzip  graphviz   ca-certificates  python-setuptools   swig \
    libjpeg-dev libpng-dev libopencv-dev   &&\
    rm -rf /var/lib/apt/lists/*   

RUN curl -o ~/conda.sh -O  https://repo.continuum.io/archive/Anaconda3-5.1.0-Linux-x86_64.sh  && \
    chmod +x ~/conda.sh && \
    ~/conda.sh -b -p /opt/conda3 && \
    rm ~/conda.sh && \
    /opt/conda3/bin/conda clean -ya 
    

ENV PATH /opt/conda3/bin:$PATH
ENV LD_LIBRARY_PATH /usr/lib/x86_64-linux-gnu:/usr/local/cuda-10.0/lib64:$LD_LIBRARY_PATH

RUN pip install --no-cache-dir wheel  setuptools
RUN pip install --no-cache-dir pillow  scikit-learn  Cython    easydict   hickle  pyyaml matplotlib   scikit-image    \
	lxml  tensorflow_gpu==1.13.1   h5py   pydot_ng   keras==2.2.4  opencv-python    tqdm  threadpool  torch==1.1.0  torchvision tensorboardX


EXPOSE 6006
EXPOSE 22






	
