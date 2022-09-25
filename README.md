# Neural_Network_Charity_Analysis

### Neural Networks and Deep Learning

### Overview

In this analysis, machine learning and neural network are used to analyse a dataset of over 34,000 ogranizations that have received funding in the past. The features in the dataset are used to create a binary classifier that is capable of predicting whether applicants will be successful if they recieve funding. The data set contains a number of columns that capture metadata about each organization, such as:

  - EIN and NAME—Identification columns
  - APPLICATION_TYPE—Alphabet Soup application type
  - AFFILIATION—Affiliated sector of industry
  - CLASSIFICATION—Government organization classification
  - USE_CASE—Use case for funding
  - ORGANIZATION—Organization type
  - STATUS—Active status
  - INCOME_AMT—Income classification
  - SPECIAL_CONSIDERATIONS—Special consideration for application
  - ASK_AMT—Funding amount requested
  - IS_SUCCESSFUL—Was the money used effectively

### Tools Used

  - Python 3.7 & Pandas Library
  - TensorFlow 2.10.0
  - Scikit-learn 1.0
  - Jupyter Notebook
  

### Results

#### Data Preprocessing for neural network model

  - Target Variables: "IS_SUCCESSFUL"
  - Features: "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "STATUS-ACTIVE", "INCOME_AMT", "SPECIAL_CONSIDERATIONS", ASK_AMT"
  - Variables to be removed: "EIN" and "NAME"

  - 'EIN' and 'NAME' columns are dropped
  
  <img width="487" alt="D1_1" src="https://user-images.githubusercontent.com/104603128/192154841-f369a17d-9cde-46f9-8759-e1614f6976bb.png">

  - Binning values
  
  <img width="240" alt="D1_2" src="https://user-images.githubusercontent.com/104603128/192154900-2dcbbdc9-333e-4be0-b3b8-9e16df18b470.png">
  
  
  <img width="164" alt="D1_2_2" src="https://user-images.githubusercontent.com/104603128/192154904-477229f9-0b4c-4ff0-894f-03a01a0aa993.png">

  - Categorical variables encoded using one-hot encoding

  <img width="487" alt="D1_3" src="https://user-images.githubusercontent.com/104603128/192154925-78b00c61-7df3-4506-b392-d171d3f0b15e.png">

  - Preprocessed data is split into features and target arrays and then into training and testing datasets.
  
  - Numerical values are standardized using the StandardScaler() module.
  
#### Compiling, training and evaluating the model

  - Neural network model created using Tensorflow Keras and number of input features and nodes for each layer assigned.
  - Activation functions are specified for the two hidden layers and output layer.
  - Number of layers used - hidden layers x 2 & output layer
  - Number of neurons and activation function:
    - Hidden Layer-1: number of neurons-80 & activation function-"relu"
    - Hidden Layer-2: number of neurons-30 & activation function-"relu"
    - Output Layer: activation function-"sigmoid"
  
   <img width="310" alt="D2_1" src="https://user-images.githubusercontent.com/104603128/192155270-28321816-6bd1-427d-81bd-1c8f2f859271.png">
  
  - Callback is created for saving the model's weights every 5 epochs.
  
  - Model is compiled and trained

  <img width="488" alt="D2_2" src="https://user-images.githubusercontent.com/104603128/192155316-804ee3f7-eb31-446a-94d7-82fa8d513439.png">
  
  - Loss and accuracy are determined
  
  <img width="331" alt="D2_3" src="https://user-images.githubusercontent.com/104603128/192155332-48abbef9-7087-47de-9605-efba0dfdca73.png">
  
  Achieved model accuracy: 69%. Target model performance of 75% not achieved. 
  
  - Results are saved and exported to HDF5 file - AlphabetSoupCharity.h5
  
#### Optimizing the model

 ##### Attempt-1: "SPECIAL_CONSIDERATIONS" column is dropped 
 
 <img width="308" alt="Attempt1" src="https://user-images.githubusercontent.com/104603128/192161132-c1b7d3fe-12fc-4957-947a-765773054392.png">

 Result: Accuracy dropped to 68.8%
 
 
 #### Attempt-2: Bin values are optimizied & more hidden layers are added to the model and number of neurons in each layer are optimized.
  
    <img width="269" alt="Attempt2_1" src="https://user-images.githubusercontent.com/104603128/192161371-eb6faded-87f4-4f7d-a73e-f0ea84f35534.png">

  - Result: Accuracy dropped to 53.3%

  <img width="307" alt="Attempt2" src="https://user-images.githubusercontent.com/104603128/192161398-7e720023-6531-415b-b899-e9b1df9c0395.png">

#### Attempt-3: Activation functions are changed for each layer. Number of epochs for the training regimen are reduced.  

  <img width="420" alt="Attempt3_1" src="https://user-images.githubusercontent.com/104603128/192161562-1f73f223-90ee-46d1-a661-26f17b71ba71.png">

  - Result: Accuracy dropped to 49.7%
  
  <img width="300" alt="Attempt3_2" src="https://user-images.githubusercontent.com/104603128/192161588-f2b32ba5-6b2f-46fc-b9a4-2ed8e7c6de9a.png">


### Summary

  - The model accuracy was not improved despite 3 different attempts.
  - Further analysis can be done using Random Forest Classifiers. This method combines multiple smaller models into a more robust and accurate model by combining the outputs from a number of weak learner algorithms to make a final classification decision. This model is suitable for our tabular data. 

  

  
