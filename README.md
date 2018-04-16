# YOLO_v1

This implementation of [YOLO](https://arxiv.org/pdf/1506.02640.pdf).

## Installation
1. Clone YOLO_v1 repository
	```Shell
	$ git clone https://github.com/hizhangp/yolo_tensorflow.git
    $ cd YOLO_v1
	```

2. Download Pascal VOC2007 dataset, and put the dataset into `data/Pascal_voc`

3. Download [YOLO_small](https://drive.google.com/file/d/0B5aC8pI-akZUNVFZMmhmcVRpbTA/view?usp=sharing)
<br>
Put weight file into `data/output`

4. Modify configuration into `yolo/config.py`

5. Training
	```Shell
	$ python train.py
	```

6. Test
	```Shell
	$ python test.py
	```

## Training on Your Own Dataset
To train the model on your own dataset, you should need to modefy:
<br>
1. Put all the images into the `Images` folder, put all the labels into the `Labels` folder.Select a part of the image for training, write this part of the image filename into `train.txt`, the remaining part of the image filename written in `test.txt`.Then put the `Images`, `Labels`, `train.txt` and `test.txt` into `data/data_set`.Put weight file in `data/output`
<br>
2. `config.py` modify the CLASSES
<br>
3. `train.py` replace`from utils.pascal_voc import pascal_voc` with `from utils.preprocess import preprocess`, and replace `pascal = pascal_voc()` with `pascal = preprocess()`.

## Requirements
1. Tensorflow
2. OpenCV
