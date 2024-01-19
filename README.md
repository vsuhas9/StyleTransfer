# Style Transfer for Game Asset Images

## Definition:  
- This technique takes two images as input and produces a third.
- The first image is the base image that we wish to transform.
- The second image represents the style we want to apply to the source image.
- Finally, the algorithm renders a third image that emulates the style characterized by the style image.


![style_trans](https://github.com/vsuhas9/StyleTransfer/assets/34618423/78aaecd2-bd76-491c-81fc-7447d8a328b8)

## Current Output using Monet Styling

![Masterlayer_Event221_SetA png_8f02369f42 jpg_generated_at_iteration_3000](https://github.com/vsuhas9/StyleTransfer/assets/34618423/f17057c7-6d89-4588-9200-56b1ab64d9c3)

## Current Output using Anime Styling

![Masterlayer_Event221_SetA png_anime jpg_generated_at_iteration_2000](https://github.com/vsuhas9/StyleTransfer/assets/34618423/f5f556cd-2945-49b7-95e8-216274702bad)

## Current Research and Approaches:
- There have been several recent advancements in GANs and style transfer.
- One such advancement is the Gated-GAN method, which allows training multi-style GANs for style transfer.
- Another recent study has explored the capabilities, limitations, and challenges of style transfer with CycleGANs
- The state of art approach uses VGG19 as a baseline reference

## Literature Survey
- The Current literature survey has revealed that Inverse Diffusion Algorithm as mentioned in https://github.com/zyxElsa/InST yields promising results.


## Loss Function and Analysis

- To calculate two parts of the loss function, we will take the Gram matrix of the outputs from several convolution layers in the VGG network.
- To determine both style and similarity to the original image, we will compare the convolution layer output of VGG rather than directly compare the image pixels.
- Then, we will directly compare pixels near each other at the last.
- We can calculate the Gram matrix by multiplying a matrix by its transpose.
- Because we are taking convolution output from several different levels of the VGG network
- the Gram matrix provides a means of combining these layers. The Gram matrix of the VGG convolution layers represents the style of the image.
- We will calculate this style for the original image, the style-reference image, and the final output image as the algorithm generates it. 

## Observations
- The current VGG Model takes one input style Image and one input target image, and thereby the computation times to do this increases
- The model consumes around 7.2 GPU RAM.
- Cyclic GAN Model was untrainable at 14 GB RAM for low-resolution Images.

## The problem of Low resolution
- The problem of low resolution can be solved by using ESR GAN, as mentioned in https://github.com/xinntao/ESRGAN

![teaser](https://github.com/vsuhas9/StyleTransfer/assets/34618423/f8fad33e-f972-43e6-8822-ec9866e15574)


## Links and URLs




## References:
1. https://www.researchgate.net/figure/llustration-of-the-network-architecture-of-VGG-19-model-conv-means-convolution-FC-means_fig2_325137356
2. https://abdulkaderhelwan.medium.com/recent-advancements-in-gans-and-style-transfer-b7ba2b54cc68
3. https://www.youtube.com/watch?v=pLWIaQwkJwU&list=PLjy4p-07OYzulelvJ5KVaT2pDlxivl_BN
4. https://arxiv.org/pdf/1508.06576.pdf
5. https://www.kaggle.com/models/google/arbitrary-image-stylization-v1
6. https://www.youtube.com/watch?v=W3urLYx9JZY


