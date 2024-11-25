# Improved-YOLOv8
ABSTRACT

In response to the problems of missed detection, false detection, and slow detection speed in surface defect detection of strip alloy material, this paper proposes an improved YOLOv8 based algorithm for surface defect detection of strip alloy material. Firstly, a Multiscale Feature Encoder (MFE) module is proposed, and a Feature Aggregation Diffusion (MFAD) structure is constructed in the neck to fully integrate the multiscale features extracted by the model backbone network, and the diffusion mechanism is used to spread features with rich contextual information to various scales. A Task Dynamic Alignment Detection Head (TDADH) with shared parameters is proposed, which reduces the number of parameters through shared parameters and works in conjunction with task alignment function to strengthen the association between classification and localization branches, thereby improving the detection accuracy of the model. Perceptual Attention Spatial Pyramid Pooling (PASPP) module is proposed, which models the spatial pyramid pooling by dynamically allocating high-dimensional features from both the channel and spatial dimensions, to prevent the loss of feature details caused by convolutional iteration and enhance the model's representation ability. Experimental results have shown that a 90.1\% mAP50 has been achieved on the surface defect dataset of our collected strip alloy materials, which is 6.3\% higher than the yolov8 network, with a 16.4\% reduction in parameter count and a detection speed of 232fps. Compared with current classic deep detection models, it has the highest detection accuracy and balances detection accuracy and speed well. At the same time, our algorithm also performs better on the surface defect dataset GC10-DET of strip steel and the general dataset PASCAL VOC2012.

DATASET

The defect image dataset used in this article is gathered from an industrial processing workshop. An image acquisition device is installed at the rear winding section of the workshop to capture double surfaces images of metal materials using two single-scanline cameras. A dataset comprising 2942 defect images is collected, including eight types: dent, peeling, swelling, weld, stratch, gap, curved scar and perforation, as illustrated in Fig. 6. Each image has a resolution of 4096 × 2048 pixels. The collected image data is randomly divided into training, validation, and test sets in a ratio of 6:2:2. Data augmentation techniques, such as flipping, symmetry and mosaic augmentation, are applied to the divided datasets to increase the number of defect images. The resulting strip alloy material surface defect dataset contains 5723 images. The distribution of defect labels before and after data augmentation is presented in Table I. Notably, peeling and scratch defects are more prevalent in actual production. Consequently, there is a larger number of labels for these two categories compared to others, which helps enhance the detection accuracy for these defects.
![image](https://github.com/user-attachments/assets/74aa3415-031b-469b-9cd8-ebc8dcdd2f7d)

Experiments are conducted using YOLOv8n and our method on the dataset before and after data augmentation, and the AP values for each defect category are shown in Fig. 7. YOLOv8n achieved a mAP50 of 74.8% before data augmentation and 83.7% after augmentation, reflecting an improvement of 8.9%. Our method achieved a mAP50 of 76.7% before data augmentation and 90.1% after augmentation, demonstrating a significant improvement of 13.4%. In comparison, our method exhibited a greater performance increase after data augmentation, demonstrating superior effectiveness.
![image](https://github.com/user-attachments/assets/43477d63-1acf-41b6-9363-737a544159f7)
![image](https://github.com/user-attachments/assets/8758ce1a-2e21-43d2-9793-ee5dbd85a32b)
