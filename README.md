# Neural Network Implementation for Project Sentinel

## Overview

The architecture of the neural network leverages a teacher-student approach for pose estimation, where the teacher model serves as
a "ground truth" for our student model.

### 1. Teacher Network (MMPose)

The teacher network is implemented using MMPose, an open-source toolbox for pose estimation tasks. MMPose provides state-of-the-art models with high accuracy but may require more computational resources.

### 2. Student Network

TBD

## Installation Guide

### Setting up MMPose

1. Follow the installation guide on the [official MMPose documentation website](https://mmpose.readthedocs.io/en/latest/installation.html).

### Annotate datasets with MMPose

1. Activate your conda environment with `conda activate openmmlab`
2. Run the following in your terminal to annotate your file:

   ```bash
   python demo/inferencer_demo.py path/to/video.mp4 --pose2d human --vis-out-dir results_folder --show-progress
   ```

#### Important Notes for MMPose Installation

- **Mac Users**: Always specify `--device cpu` in command line calls or `device='cpu'` in Python code, as CUDA is not available on macOS

- **Common Issues**:
  - If encountering incompatible mmcv versions, try `pip uninstall mmcv` followed by `mim install "mmcv>=2.0.0,<2.2.0"`
  - If encountering incompatible mmdet versions, try `pip uninstall mmdet` followed by `mim install "mmdet>=3.0.0,<3.3.0"`
  - Option A takes up more disk space, but tends to be more reliable. If you find yourself struggling to run Option B, try Option A.
