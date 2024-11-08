# CNNs_vs._Transformer
Contrasting CNN and Transformer Architectures in Brain-like Visual Encoding
Comparing CNN architectures such as ResNet-18 and EfficientNet with the transformer model ViT-B/16
fMRI data from the 2023 Algonauts challenge subset of the Natural Scenes Dataset (NSD) was used which involves a dataset of fMRI responses to natural scene images.
Three pretrained models were entered 
ResNet18: A model with 18 layers. Has been successfully used in Alzheimer detection (Odusami et al., 2022)
EfficientNet: An attempt to make Convolutional Neural Networks perform better and faster by effectively summarizing key aspects (Tan & Le., 2019)
ViT-B/16 is a vision transformer model which has been shown to be effective at image analysis but does likely not do this in a similar way to humans (Qin et al., 2022)
Evaluate convolutional architectures alongside transformer architectures and compare them to identify which models perform better for analyzing brain data of viewing natural images.
Models used are ResNet18, EfficientNet and Vit_b_16 
Hypothesis: The convolutional architecture exhibits a closer resemblance to the activity of brain data when in a simple scene viewing task when compared to transformer models
Subject: Using fMRI data from Subject 1.
Total Images: 872 (NSD Image Dataset).
Training Stimulus Images: 785
Test Stimulus Images: 87
Pre-Trained DNNs Used: 
EfficientNet and ResNet-18:
Used avgpool layer, summarizing global features.
Brain-like Representation: Aligned with higher-order brain areas that focus on abstract, global representations rather than fine spatial details.
Vision Transformer (ViT-B/16):
Used encoder.layers.encoder_layer_11.
Self-attention mechanism captures more contextual, patch-based relationships, potentially less brain-like for certain visual areas where hierarchical abstraction is key.
Dimensionality Reduction:
Challenge: With 785 training images and a high-dimensional feature space, there’s a risk of overfitting.
Solution: Apply Principal Component Analysis (PCA) to reduce dimensions to 50 components, balancing the model's complexity and available data.
Discussion
When considering the correlations for the models alone it seems that ViT is feasible for both Early and Ventral streams, whereas the ResNet and EfficientNet models seemed more feasible for the Ventral stream 
Results may imply that ResNet and EfficientNet are stronger at modelling brain activity during the ventral stream, whereas Transformer models are stronger at modelling brain activity in early visual areas which is indirectly backed up by prior literature (Quinn et al., 2022)
The general tendency for CNNs to outperform the Transformer model in the ventral stream is likely because ViTs tend to not very accurately rely on the semantic categorization of images that humans use, although it might still be strong in discriminating basic image features (Qin et al., 2022). 
However it is worth noting that many Transformer models have a shape bias, like human vision does and make errors more akin to those a human would make when compared to a CNN (Tuli et al., 2021) which may explain the superior performance in Early ROIs
Summary
ViT superior performance in early visual areas in simple scene viewing tasks
ResNet and EffNet superior performance in the ventral stream in simple scene viewing tasks
References 
Odusami, M., Maskeliūnas, R., Damaševičius, R., & Krilavičius, T. (2021). Analysis of features of Alzheimer’s disease: Detection of early stage from functional brain changes in magnetic resonance images using a finetuned ResNet18 network. Diagnostics, 11(6), 1071.
Qin, Y., Zhang, C., Chen, T., Lakshminarayanan, B., Beutel, A., & Wang, X. (2022). Understanding and improving robustness of vision transformers through patch-based negative augmentation. Advances in Neural Information Processing Systems, 35, 16276-16289.
Tan, M., & Le, Q. (2019, May). Efficientnet: Rethinking model scaling for convolutional neural networks. In International conference on machine learning (pp. 6105-6114). PMLR.
Tuli, S., Dasgupta, I., Grant, E., & Griffiths, T. L. (2021). Are convolutional neural networks or transformers more like human vision?. arXiv preprint arXiv:2105.07197.

