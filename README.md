# deep-learning-challenge
Module 21 Challenge

## Overview
We attempted to create neural network that could predict if applicants applying for funding from the Alphabet Soup nonprofit would be successful. We attempted to create a model that was 75% accurate. We tried 3 different models to predict if they would be successuful.

* The modeling code for Model 1 can all be found in the `AlphabetSoupCharity_Optimization1.ipynb` file in the main repo.
* The modeling code for Model 2 can all be found in the `AlphabetSoupCharity_Optimization2.ipynb` file in the main repo.
* The modeling code for Model 3 can all be found in the `AlphabetSoupCharity_Optimization3.ipynb` file in the main repo.

Model summary files can be found in the `Models` directory.
* The `Models/model_1` directory has summary files for the first attempt.
* The `Models/model_2` directory has summary files for the second attempt.
* The `Models/model_3` directory has summary files for the third attempt.

## Results

### Data Preprocessing

#### Target Variable
* `IS_SUCCESSFUL`

#### Feature Variables
* `APPLICATION_TYPE`
* `AFFILIATION`
* `CLASSIFICATION`
* `USE_CASE`
* `ORGANIZATION`
* `STATUS`
* `INCOME_AMT`
* `SPECIAL_CONSIDERATIONS`
* `ASK_AMT`
* `IS_SUCCESSFUL`

#### Variables to be removed
* `EIN`
* `NAME`

### Compiling, Training, and Evaluating the Model
Since this is a binary classification problem (the venture is either successful or unsuccessful) a Sigmoid Acitvation is used for all of our output layers.

#### Model 1

| Variable | Value |
| --- | --- |
| Number of Hidden Layers | 2 |
| Hidden Layer 1 Neurons | 80 |
| Hidden Layer 1 Activation Function | ReLU |
| Hidden Layer 2 Neurons | 30 |
| Hidden Layer 2 Activation Function | ReLU |
| Output Layer Activation Function | Sigmoid |
| Number of Epochs | 100 |
| Model Accuracy | 0.7301457524299622 |

This was a baseline test using the most common activation function for hidden layers (ReLU) and 2 layers. This was very close in getting us our 75% accurate number. So we attempted a few tweaks of the model to get closer.

#### Model 2
*This model was created using Keras Tuner* 

| Variable | Value |
| --- | --- |
| Number of Layers | 5 |
| Hidden Layer 1 Neurons | 46 |
| Hidden Layer 1 Activation Function | TanH |
| Hidden Layer 2 Neurons | 21 |
| Hidden Layer 2 Activation Function | TanH |
| Hidden Layer 3 Neurons | 11 |
| Hidden Layer 3 Activation Function | TanH |
| Hidden Layer 4 Neurons | 11 |
| Hidden Layer 4 Activation Function | TanH |
| Hidden Layer 4 Neurons | 16 |
| Hidden Layer 4 Activation Function | TanH |
| Output Layer Activation Function | Sigmoid |
| Number of Epochs | 12 |
| Model Accuracy | 0.7343440055847168 |

We ran Keras Tuner, allowing it to choose between TanH and ReLU for hidden layer functions. Here it chose TanH which makes a lot of sense again for a binary classification problem.

We also allowed it to have 2-6 hidden layers, and here it found 4 was the best.

We did not achieve the 75% accuracy mark here, so I attempted to add Epochs to try and hit the mark.

#### Model 3

| Variable | Value |
| --- | --- |
| Number of Layers | 5 |
| Hidden Layer 1 Neurons | 46 |
| Hidden Layer 1 Activation Function | TanH |
| Hidden Layer 2 Neurons | 21 |
| Hidden Layer 2 Activation Function | TanH |
| Hidden Layer 3 Neurons | 11 |
| Hidden Layer 3 Activation Function | TanH |
| Hidden Layer 4 Neurons | 11 |
| Hidden Layer 4 Activation Function | TanH |
| Hidden Layer 4 Neurons | 16 |
| Hidden Layer 4 Activation Function | TanH |
| Output Layer Activation Function | Sigmoid |
| Number of Epochs | 50 |
| Model Accuracy | 0.7322449088096619 |

Here we ran the exact same model with more Epochs. It appears that the model accuarcy went down when we added more Epochs, which may be an indication of overfitting.

## Summary
While we did not achieve the 75% mark, we got very close and with more rounds, I believe could achieve success. I would recommend creating a model that has the right amount of Epochs to achieve the desired result. I also would recommend finding the most important feature variables for this problem, and then removing those that do not contribute as much so you can save processing time and get a more accurate result.

