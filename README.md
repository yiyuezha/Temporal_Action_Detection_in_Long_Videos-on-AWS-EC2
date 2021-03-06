# Temporal_Action_Detection_in_Long_Videos-on-AWS-EC2
Yiyue Zhang (Team Lead), Weijing Wang, Jiyang Gao

The amount of videos is increasing very rapidly, as capturing videos has become much easier than before with the
wide use of iPhone, GoPro and other portable devices. The need for temporal analysis of the large amount user generated videos is also increasing rapidly. For example, users may want to collect highlight moments out of the long boring videos, e.g. a fancy surfing motion, an incredible skydiving. To achieve this goal, we need a computer vision system that is able to process large scale of video data rapidly and precisely generate temporal annotations. This problem is called temporal action detection in the field of computer vision. Temporal action detection is an important problem, as fast and accurate extraction of semantically important (e.g. human actions) segments from untrimmed videos is an important step for large-scale video analysis.

In this project paper, we compare implement and train the state-of-the-art action proposal generation and action detection method, TURN [5], on AWS EC2. Based on TURN, we originally propose to use max-pooling for clip- feature modeling to capture the signature information inside the clip. Besides TURN, other state-of-the-art methods address this problem by applying action classifiers on sliding windows. Although sliding windows may contain an identifiable portion of the actions, they may not necessarily cover the entire action instance, which would lead to inferior performance.

We train different system variants in TURN to compare the C3D/Flow feature performance. We test our proposed max-pooling method in TURN and shows a performance boost. The generated proposals are applied in action detection task with SVM classifiers and SCNN detectors, and achieve state-of-the-art performance.

For computing platform and implementation, we use the codes provided by TURN [5], and train the model on AWS EC2 platform. We use a p2.xlarge instance which includes a single Nvidia K80 GPU, 4 vCPU and 61GB memory. We use the “Deep Learning Base AMI” to initialize the instance.

In the following, we first demonstrate the problem statement and methods, and then introduce the experiment settings on AWS EC2, including the environment configuration, model parameters and training details. In section 4, we will discuss the evaluation results and comparing with other methods.
