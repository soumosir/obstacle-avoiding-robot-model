# obstacle-avoiding-robot-model
using nueral network

 Overview
Training a Robot to navigate moving obstacles Command directions are angular and linear velocity A neural network is divised to solve this.
 
    
  
  Data Analysis
Based on the fields and feature set
1080 sensor data normalized to 6 directional sensor viewing 270 degree angel
The positional coordinated are kept as is x,y,qr,qk for final goal, local goal and position of the robot
Output is considered to be [v,w] the linear and angular velocity
 
  Model selection and comparison of the errors
mse in training data -LR: 0.08469151131341271
mse in testing date -LR : 0.08275897426599729
mse in training data -Ridge: 0.08469151131345751
mse in testing date -Ridge : 0.08275897544343264
mse in training data -SDGRegressor: 0.08484172256219111 mse in testing date -SDGRegressor : 0.08305160480836499 mse in training data -model_lasso: 0.08971326567345395 mse in testing date -model_lasso : 0.08305160480836499 Training data with neural networks mse: 0.0394
Test Data with neural networks : mse: 0.0397
           
  Lowest error
We see the neural network provided with the lowest Ein of 0.0394
Eout of 0.0397
Now let is decipher how we optimized our model based on
     - hyper parameter tuning
 - regularization

  Hyperparameter tuning
1. Number of layers varied
2. Weight in each layes(desnsity of layer)
3. Learning Rate [0.1,0.01,0.001]
4. Regularization
a. L1 regularizaers
b. L2 regulariers
c. Dropout
 
  Final Model and performance
mse: 0.0394 - accuracy: 0.7967 val_mse: 0.0389 - val_accuracy: 0.9234 Layers with units - [12,8,32,16,32,2]
   
 Generalization Error bound
  In the present case,
 Number of samples in test dataset =389817
  And for 𝛿 = 0.05, the confidence level of 95% is given by :
 And substituting the vaues
 0.0397 <=0.0394 + 0.00217521263
 The statement hold true.
 Hence, if sample outside the current dataset is given for model prediction, the error in that
 prediction will be within E of predicted value with 95% confidence
