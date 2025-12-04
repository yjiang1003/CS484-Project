# COVID-19 AND VIRAL PNEUMONIA DETECTION TOOL
By: Thailer Simmons, Juan Zanguitu, Yingqi Jiang, Hrideta Rimu​
## PROJECT OBJECTIVE​
This project uses machine learning to classify chest X-ray images into three categories:

- **COVID-19**
- **Normal**
- **Viral Pneumonia**

We build and compare three different models:

1. **Baseline CNN**
2. **Improved CNN** (with data augmentation + deeper layers)
3. **Transfer Learning + Fine-Tuning** using MobileNetV2

The goal is to understand how model design affects performance on a small medical dataset.

## BACKGROUND ​
COVID-19 diagnosis is often based on RT-PCR tests, which can be slow and requires intensive resources. Chest X-rays provide a faster, more accessible screening method. ​

### Dataset is collected from Kaggle:​
Total images: 1,823.​
Classes: COVID-19 (536), Viral Pneumonia (619), Normal (668).​ Image types: JPEG, PNG, JFIF, Other.​
https://www.kaggle.com/datasets/sid321axn/covid-cxr-image-dataset-research/data.​

## Models

### Baseline CNN
A simple convolutional neural network with:
- 3 Conv2D + MaxPool blocks  
- Dense(128)  
- Softmax output  
- Trained for 15 epochs  

### Improved CNN
Adds:
- Data augmentation  
- More convolution filters  
- Dropout for regularization  
- Larger dense layer (256 units)  

### Transfer Learning + Fine-Tuning
Uses **MobileNetV2** pretrained on ImageNet:
- Phase 1: freeze base layers, train classifier  
- Phase 2: unfreeze top layers and fine-tune  
- More stable but limited by dataset size


### Getting started 
Clone the repository

```git clone https://github.com/yjiang1003/CS484-Project.git```

create a virtual environment

Windows:

```python -m venv venv ```

```.\venv\Scripts\Activate.ps1```

Mac/Linux:

```python3 -m venv venv```

```source venv/bin/activate```

ensure the correct packages are installed by running this command 

```pip install -r requirements.txt```

Download the dataset from Kaggle and change the path within the .ipynb file
https://www.kaggle.com/datasets/sid321axn/covid-cxr-image-dataset-research/data.​

```data_path = pathlib.Path("YOUR PATH TO DATASET")```
