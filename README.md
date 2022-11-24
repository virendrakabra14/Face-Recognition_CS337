# Face Recognition
## CS337 (AI/ML) Project
### Pranjal Kushwaha, Shashwat Garg, Vedang Asgaonkar, Virendra Kabra

All the code is in a jupyter notebook and is divided into 5 main sections. We fix a random seed to maintain reproducibility in the results.

Put the data in the directory ./Face-Recognition_CS337/input/lfw-dataset/ for running the demo

The first section is the basic model training.
This includes formatting and selecting the useful data, creating the model, loading the data, defining the model parameters, loss functions & optimizers and finally training the model.

Here, alongwith the classic CrossEntropyLoss, we also use a triplet loss, as inspired from the FaceNet paper. This loss promotes clustering of similar images in the latent space representation, thereby improving robustness and accuracy of the model. For more details, kindly refer to the report

The second section deals with the case of modifying the dataset. This is mostly similar to the first section, and just has some extra lines of code to freeze the parameters in the encoder layer. This leads to faster training as a result of largely reusing an older model.

This is followed by an instance of the VGG model, which we trained for 500 epochs. We trained this model as a benchmark check against our much smaller model. We found that for the smaller dataset that we were using alongwith the limited resources, our model inspired from FaceNet performed better than VGG16.

Next, we have the adversarial attacks on our model. Here, a generator adds noise to the images and the noisy images are fed into our model. We test for both l1 and l2 noises, the results of which can be found in the report.

Finally we have a Demo section where we display some images from our test set for the original trained model. You can run with this section after importing all the packages and loading the model.

Trained models:
* [CNN on 10 faces](https://drive.google.com/file/d/1lYIf0Zt6V2ejj5jRbfDqk6jrnmmgCCoJ/view?usp=sharing)
* [Transfer learning to 15 faces](https://drive.google.com/file/d/1DsZZwrCDvaXleEMmCQ9Sj5UJB4iWlUdR/view?usp=share_link)
* [VGG16](https://drive.google.com/file/d/1hY2y229YCSMc9cBoybW2vyLvrxD47frL/view?usp=sharing)
