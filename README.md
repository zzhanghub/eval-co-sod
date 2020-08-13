<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="http://zhaozhang.net/coca.html">
    <img src="img/eval_co-sod.png" alt="Logo" width="210" height="100">
  </a>

  <h3 align="center">PyTorch-Based Evaluation Tool for Co-Saliency Detection</h3>

  <p align="center">
    Automatically evaluate 8 metrics and draw 4 types of curves
    <br />
    <a href="http://zhaozhang.net/coca.html"><strong>⭐ Project Home »</strong></a>
    <br />
  </p>
</p>


***
**Eval Co-SOD** is an extended version of [Evaluate-SOD](https://github.com/Hanqer/Evaluate-SOD) for **co-saliency detection task**.
It provides eight metrics and four curves:
* Metrics:
    * Mean Absolute Error (MAE)
	* Maximum F-measure (max-Fm)
	* Mean F-measure (mean-Fm)
	* Maximum E-measure (max-Em)
	* Mean E-measure (mean-Em)
	* S-measure (Sm)
	* Average Precision (AP)
	* Area Under Curve (AUC)
* Curves:
	* Precision-Recall (PR) curve
	* Receiver Operating Characteristic (ROC) curve
	* F-measure curve
	* E-measure curve


## Prerequisites
* PyTorch >= 1.0


## Usage

### 1. Prepare your data
The structure of `root_dir` should be organized as follows:
```
.
├── gt
│   ├── dataset1
│   │   ├── accordion
│   │   │   ├── 51499.png
│   │   │   └── 186605.png
│   │   └── alarm clock
│   │       ├── 51499.png
│   │       └── 186605.png
│   ├── dataset2 ...
│   └── dataset3 ...
│ 
└── pred
    └── method1
    │   ├── dataset1
    │   │   ├── accordion
    │   │   │   ├── 51499.png
    │   │   │   └── 186605.png
    │   │   └── alarm clock
    │   │       ├── 51499.png
    │   │       └── 186605.png
    │   ├── dataset2 ..
    │   └── dataset3 ...
    └──method2 ...
```

### 2. Evaluate on the 8 metrices
1. Configure `eval.sh`
```shell
--methods method1+method2+method3 (Multiple items are connected with '+')
--datasets dataset1+dataset2+dataset3
--save_dir ./Result (Path to save results)
--root_dir ../SalMaps
```

2. Run by
```
sh eval.sh
```

### 3. Draw the 4 types of curves
1. Configure `plot_curve.sh`
```shell
--methods method1+method2+method3 (Multiple items are connected with '+')
--datasets dataset1+dataset2+dataset3
--out_dir ./Result/Curves (Path to save results)
--res_dir ./Result/Detail
```

2. Run by
```
sh plot_curve.sh
```

## Citation
If you find this tool is useful for your research, please cite the following papers.
```
@inproceedings{zhang2020gicd,
 title={Gradient-Induced Co-Saliency Detection},
 author={Zhang, Zhao and Jin, Wenda and Xu, Jun and Cheng, Ming-Ming},
 booktitle={European Conference on Computer Vision (ECCV)},
 year={2020}
}

@inproceedings{fan2020taking,
  title={Taking a Deeper Look at the Co-salient Object Detection}, 
  author={Fan, Deng-Ping and Lin, Zheng and Ji, Ge-Peng and Zhang, Dingwen and Fu, Huazhu and Cheng, Ming-Ming},   
  booktitle={IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
  year={2020} 
} 
```

## Contact
If you have any questions, feel free to contact me via `zzhang🥳mail😲nankai😲edu😲cn`
