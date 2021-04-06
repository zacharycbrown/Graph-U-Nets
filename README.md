PyTorch Implementation of Graph U-Nets
======================================

The original version of this repository can be found at https://github.com/HongyangGao/Graph-U-Nets.git and was created by [Hongyang Gao](https://faculty.sites.iastate.edu/hygao/) @ Iowa State University, and
[Shuiwang Ji](http://people.tamu.edu/~sji/) @ Texas A&M University.

The current version of this repository was adapted from the original for use in the ECE 590 Deep Learning course at Duke University, by Zachary Brown on April 6th, 2021.
Modifications include:

 a) The inclusion of a jupyter notebook file (ece590_gnn2_graph_unet_notebook_v04062021.ipynb) so that users can run the code in google colab rather than needing a local machine.
 
 b) Changes to the directories used in the run_GNN.sh and data_loader.py files to enable the implementation of a).

About
-----

PyTorch implementation of Graph U-Nets. Check http://proceedings.mlr.press/v97/gao19a/gao19a.pdf for more information.

Methods
-------

### Graph Pooling Layer

![gPool](./doc/GPool.png)

### Graph Unpooling Layer

![gPool](./doc/GUnpool.png)

### Graph U-Net

![gPool](./doc/GUnet.png)

Installation
------------


Type

    ./run_GNN.sh DATA FOLD GPU
to run on dataset using fold number (1-10).

You can run

    ./run_GNN.sh DD 0 0
to run on DD dataset with 10-fold cross
validation on GPU #0.


Code
----

The detail implementation of Graph U-Net is in src/utils/ops.py.


Datasets
--------

Check the "data/README.md" for the format. 


Results
-------


| Models   | DD              | IMDBMULTI       | PROTEINS        |
| -------- | --------------- | --------------- | --------------- |
| PSCN     | 76.3 ± 2.6%     | 45.2 ± 2.8%     | 75.9 ± 2.8%     |
| DIFFPOOL | 80.6%           | -               | 76.3%           |
| SAGPool  | 76.5%           | -               | 71.9%           |
| GIN      | 82.0 ± 2.7%     | 52.3 ± 2.8%     | 76.2 ± 2.8%     |
| g-U-Net  | **83.0 ± 2.2%** | **56.7 ± 2.9%** | **78.7 ± 4.2%** |

Reference
---------

The citation for the original Graph U-Net original paper:

    @inproceedings{gao2019graph,
        title={Graph U-Nets},
        author={Gao, Hongyang and Ji, Shuiwang},
        booktitle={International Conference on Machine Learning},
        pages={2083--2092},
        year={2019}
    }
