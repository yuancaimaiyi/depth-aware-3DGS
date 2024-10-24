# depth-aware-3DGS
Code for "Few-shot Novel View Synthesis using Depth Aware 3D Gaussian Splatting" (ECCV 24 workshops)

[Paper Link](https://arxiv.org/pdf/2410.11080)

## Installations

```
git clone https://github.com/raja-kumar/depth-aware-3DGS --recursive
conda create -n depth_aware_3dgs python=3.10
conda activate depth_aware_3dgs
conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia
pip install -r requirements.txt
pip install submodules/diff-gaussian-rasterization
pip install submodules/simple-knn
```

## Dataset

### Colmap
Follow the instruction in the [original 3DGS](https://github.com/graphdeco-inria/gaussian-splatting) repo.

### depth data
we use [GLPN](https://huggingface.co/vinvino02/glpn-nyu) for depth estimation. Use below script to generate depth data. (change the path variables)

```
python estimate_depth.py
```

### Sample data

Preprocessed data can be accessed [here](https://drive.google.com/drive/folders/1CAtlega8ZTndsgCzvqVmFtoi5gFEK3iW?usp=sharing). This can be used directly for training.

## Training

```
python train.py -s ./data/fern --scene fern
```

## Citation

If you found our work useful for your research, Please cite our paper
```
@article{kumar2024few,
  title={Few-shot Novel View Synthesis using Depth Aware 3D Gaussian Splatting},
  author={Kumar, Raja and Vats, Vanshika},
  journal={arXiv preprint arXiv:2410.11080},
  year={2024}
}
```

## Attributions
The repo uses the code from [gaussian-splatting](https://github.com/graphdeco-inria/gaussian-splatting) and [diff-gaussian-rasterization](https://github.com/ashawkey/diff-gaussian-rasterization). We would like to thank the authors for their amazing work.
