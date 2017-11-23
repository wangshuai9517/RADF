# Recurrently Aggregating Deep Features for Salient Object Detection

by Xiaowei Hu, Lei Zhu, Jing Qin, Chi-Wing Fu, and Pheng-Ann Heng

This implementation is written by Xiaowei Hu at the Chinese University of Hong Kong.

***

## Citation
@inproceedings{hu18recurrently,   
&nbsp;&nbsp;&nbsp;&nbsp;  author = {Xiaowei Hu and Lei Zhu and Jing Qin and Chi-Wing Fu and Pheng-Ann Heng},    
&nbsp;&nbsp;&nbsp;&nbsp;  title = {Recurrently Aggregating Deep Features for Salient Object Detection},    
&nbsp;&nbsp;&nbsp;&nbsp;  booktitle = {AAAI},    
&nbsp;&nbsp;&nbsp;&nbsp;  year  = {2018}    
}

## Saliency Maps   

The results of salienct object detection on five datasets (ECSSD, HKU-IS, PASCAL-S, SOD, DUT-OMRON) can be found on [Google Drive](https://drive.google.com/drive/folders/0B8VpfLBo2BeyNWxnMURWNlU0YVE?usp=sharing).


## Installation
1. Clone the RADF repository, and we'll call the directory that you cloned RADF into `RADF`.

    ```shell
    git clone https://github.com/xw-hu/RADF.git
    ```

2. Build RADF (based on Caffe)

   *This model is tested on Ubuntu 16.04, CUDA 8.0, cuDNN 5.0

   ```shell
   # Follow the Caffe installation instructions here:   
   # [http://caffe.berkeleyvision.org/installation.html](http://caffe.berkeleyvision.org/installation.html)   
   ```
   In Makefile.config:  uncomment WITH_PYTHON_LAYER := 1 
   
   ```shell
   make all -j XX
   make pycaffe
   ```

## Test
1. Please download our pretrained model on [Google Drive](https://drive.google.com/open?id=0B8VpfLBo2BeybkpYenNMbXNwR1U).

   Put this model in `RADF/examples/snapshot/`.

2. Export PYTHONPATH in the command window such as:

   ```shell
   export PYTHONPATH='/home/xwhu/RADF/python'
   ```
 
3. Run the test model (please modify the path for reading images):
   
   ```shell
   ipython notebook RADF_test.ipynb
   ``` 

4. Apply CRF to do the post-processing for each image.   
   The code for CRF can be found in [https://github.com/Andrew-Qibin/dss_crf](https://github.com/Andrew-Qibin/dss_crf)   
   *Note that please provide a link to the original code as a footnote or a citation if you plan to use it.
  
## Train

