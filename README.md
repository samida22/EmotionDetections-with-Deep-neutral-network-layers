# EmotionDetections-with-Deep-neutral-network-layers
Ongoing, Tuning and maintaining model hyperparameters.
# Model for predicting the emotions 
  ## 1.  data pre-processing:
    -The dataset consisted of 7 classes in train and test files with 7 types of expressions.
     The data set can be found in kaggle.
    -import all the necessary packages.
    -Prepare data with the help of image data generator from keras.
    -we will be giving images in the batch of 128
 ## 2. now its time for training the datas, I am building every thing from scratch.I will try it later with resnet and vgg19 soon
      from keras.models import Sequential
      from keras.layers import Dense,Activation,Flatten,Dropout
      from keras.layers import Conv2D,MaxPooling2D
      from keras.callbacks import ModelCheckpoint
      -now create sequential model and add layers respectively 
I will do following things for model it can be changed during tuning process some of hyperparameters , will update soon.
      # Conv2D--MaxPool Conv2D-MaxPool Flatten-Dropout--Dense--Dense

      #1st CNN layer	
        convolution layer with 128 filters of 3 by 3
        Batch normalization
        Relu activation
        maxpool layer of 2 by 2 size
        dropout layers

      #2nd CNN layer
         convolution layer with 128 filters of 5 by 5
        Batch normalization
        Relu activation
        maxpool layer of 2 by 2 size
        dropout layers

      #3rd CNN layer

        convolution layer with 512 filters of 3 by 3
        Batch normalization
        Relu activation
        maxpool layer of 2 by 2 size
        dropout layers

      #4th CNN layer
        convolution layer with 512 filters of 3 by 3
        Batch normalization
        Relu activation
        maxpool layer of 2 by 2 size
        dropout layers


       #Flattening the layers
          faltten layer


      #Fully connected 1st layer

        Dense Layer of 256
        Batch normalization
        Relu activation
        Dropout layer

      #Fully connected 2nd layer

        Dense Layer of 512
        Batch normalization
        Relu activation
        Dropout layer
      #Last layer with no_Of_Classes with softmax activation    
      
      -we are going to keep check points
      - we are doing early stopping in case for worse case. we will be monitoring val_loss as tracking metrics
      -we are going to keep best weights
      -callback_list will be maintained for tracking checkpoints, early stopping points, reduce_learning_rates for better peformance
      -now we are going to compile our model with adam optimizer and metric as accuracy
      -we are going to train for 40 epochs
      -plot of loss vs epochs for training loss and validation loss is shown below
      -next plot of loss vs epochs for training accuracy and validation accuracy
      
 
  # 3. Final steps is to detect emotion in for this we are going to load our model and apply harrcascade classifier to detect faces and draw bounding boxes around and predict emotions
     for this we are going to convert the frame img into gray normalize and resize it to 224 by 224. we are going to find the region of interest and detect the emotions in the faces.
    pass the frame to model for predictions util ret returns false or some key is pressed.
    
    
    ## not good result enough but will update soon
    


      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
      
