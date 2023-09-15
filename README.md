# CIFAR-100 Object Recognition

## Project Description

This project aims to evaluate and compare the accuracy of two supervised learning image classification methods when applied to the CIFAR-100 data-set. 
The goal of each classification algorithm is to categorise images according to their correct label, from the 100 fine granularity or 20 coarse granularity classes presented in the CIFAR-100 data-set. 
To do this, both models will be trained using 50,000 images from the CIFAR-100 data-set, with testing carried out on the remaining 10,000 images.

## Methods

### 1. Convolutional Neural Network (CNN)

This method involved creating a neural network consisting of a series of convolutional layers, max pooling layers and dense layers in order to classify a 32x32x3 RGB image. 
To do this, the Keras sequential model was used. This approach is commonly used for image classification, as it requires little pre-processing of the image, whilst providing down-sampling and feature extraction during the process.

### 2. HOG, PCA & SVM

This method involved a multi-step process of feature extraction using a Histogram of Oriented Features (HOG) algorithm,
followed by dimensionality reduction using Principal Component Analysis (PCA), 
before classification is carried out using a Support Vector Machine (SVM) algorithm.

#### Feature Extraction using HOG

Before being passed to the SVM classifier, prominent features of each image in the data-set were extracted using the Sk-learn HOG function, creating a vector representation of the image which will be used in the following steps.

#### Dimensionality Reduction using PCA

PCA was be used to reduce the dimensionality of the data before being passed to the SVM classifier.
Using a value of 300 PCA components, feature data was be reduced from over 5,000 to 300 features, whilst retaining 90% of the explained data variance.

#### Classification using SVM

A Keras SVC model was created and fit to the reduced PCA training split data using both the fine and coarse label data. Predictions for both coarse and fine labels were be made using the SVC.predict() function.


## Results


The CNN classifier resulted in a test set accuracy of 47.78% for the coarse labels and 37.83% for the fine data labels. 
The SVM classifier resulted in a lower test accuracy of 30% for the coarse data labels, and 21% for the fine data labels.
