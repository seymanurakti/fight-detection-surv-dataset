## Vision-based Fight Detection From Surveillance Cameras

A new fight dataset is shared through this repository. This dataset is benefited for developing a fight detection system which is aimed to use in surveillance cameras in public areas such as streets, underground stations and more. The details of the implementation and experiments are included in our paper "Vision-based Fight Detection From Surveillance Cameras" which will be presented at IPTA 2019 conference. The project is developed based on the CNN + LSTM action recognition systems and is improved using a re-trained Xception CNN, Bi-LSTM and self-attention layer.

## System Design

![system design](https://i.ibb.co/zbVMpBp/Fig2.jpg)

The system works in two parts as feature extraction and classification. The dataset contains video samples in 2 seconds long. Since the CNN is 2D the data requires some modification. So, 5-10 frames are obtained from each video sequence by considering the total frame number in the sample in a uniform manner. The frames are resized according to the input size of CNN architecture. Then, each frame is sent to CNN for feature extraction. At the end of the process we had a feature vector for each frame. After, all of the features are sent into Bi-LSTM for sequence learning. LSTM systems can learn the relationship between the current element and the previous elements. Bi-LSTM systems also can find relations between current element and the future elements so it observes the sequence in both forward and backward way. In our case, the elements were frames and the system has learnt how the frames change according to the time. So that, it can recognize the action that is occuring in the sequence. The self-attention layer improves the given input by calculating the effects of each element on the current element. Thus, it learns for each element in the sequence, which elements must be given attention the most. 

## Surveillance Camera Fight Dataset

The dataset is collected from the Youtube videos that contains fight instances in it. Also, some non-fight sequences from regular surveillance camera videos are included.

- There are 300 videos in total as 150 fight + 150 non-fight
- Videos are 2-second long
- Only the fight related parts are included in the samples

![sample-frames](https://i.ibb.co/BjMPGCS/Fig3.png)

Besides, since the task is detecting fights through surveillance cameras, the videos that have no background motion are preferred as samples. Also, various fight scenarios such as hitting with an object, kicking, fisting, wrestling are included. The environment in the samples are also varies such as cafe, street, bus, and more. 

## Citation

The reference information will be shared after the paper is published in conference proceedings.

