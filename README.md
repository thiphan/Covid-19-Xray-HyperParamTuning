# Covid-19-Xray-HyperParamTuning
## Introduction
This project proposed VGG16 model using transfer learning, fine-tuning techniques and hyperparameter tuning process to identify covid-19 affected lung using X-ray images.The model showed 97% of accuracy and 98% of recall. 

## Datasets 
Dataset contains 3 folders, namely:
Covid: contains lung x-ray images with covid-19 disease
Pneumonia:contains lung x-ray images with pneumonia disease
Normal: contains healthy lung x-ray images

## Transfer learning and fine tuning
![image](https://user-images.githubusercontent.com/36075177/161779271-d7caf194-a366-479b-b77a-e9bd81eb282b.png) <br/>
<br/>
The fine tuning has implemented by removing the final pooling and fully connected layer in the original model. All layers of the under-investigation models were fixed except a certain number of the last layers which were retrained during the training process. The classification block of the pretrained models was replace by a new classification block containing a fully connected layer and a classification layer of 3 classes. Since ReLU is the most common activation function used in CNN and Softmax is the most common activation function used for multiclass classification, this project keeps those functions for new added fully connected layer and classification layer. 

## Hyperparameter tuning
The hyperparameters boundaries in this experiment were set as below: 
- Number of trainable layers was set from 0 to the index of the last 10 convolutional layers.
- Learning rate was chosen in {1e-2, 1e-3, 1e-4, 1e-5}
- Gradient descent optimizer was chosen among SGD, RMSprop, Adam
- Number of neurons in fully connected layer was chosen in range of [32, 1024] with step of 32. 
- Batch size was chosen in {32, 64, 128}

Optimization algorithm: Hyberband<br/>
Number of trial: 30 <br/>
Max epochs: 10
