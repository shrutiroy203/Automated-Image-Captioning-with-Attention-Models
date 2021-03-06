## Table of contents
* [Problem Statement](#problem-statement)
* [Technologies](#technologies)
* [Encoder-Decoder with Attention Architecture](#encoder-decoder-with-attention-architecture)
* [Resources](#resources)

## Problem Statement
The goal of the project is to generate a caption automatically given an image. The model uses [Flickr8k dataset](https://www.kaggle.com/aladdinpersson/flickr8kimagescaptions) with captions which includes ~8000 images with their captions
	
## Technologies
Project is created with:
* Pytorch v1.7
* Python v3.8

## Encoder-Decoder with Attention Architecture
The project uses an Encoder-Decoder framework with Bahdanau attention Layer. 

### Encoder Layer
We used GoogleNet Pretrained layers to encode and represent the images. 

### Decoder Layer
We used Long-Short-Term Memory layer to learn the captions after using Image embedding from encoder layer as the initial hidden state. Each sentence ends with a special <EOS> token indicating the end of sequence for the decoder layer 

### Bahdanau Attention Layer
Instead of using the full image sequence we use Bahdanau Attention layer to focus on specific part of the image vectors while learning the words. The encoder and decoder are used to generate the context vectors. After aligning the two inputs, the attention scores are passed through a softmax layer which helps generate attention weights. These attention weights are then used to emphasize the most important word while learning the captions. 

This concept can be expressed by the image below generated with our trained model:

  
![Screen Shot 2021-08-11 at 11 29 42 AM](https://user-images.githubusercontent.com/69861343/129103734-2323e6a1-be33-4b20-a31b-d40e763b71bd.png)

### Loss function 
  We used Cross Entropy loss while training the model to identify the word in Vocab dictionary 

## Use Cases of Automated Image Captioning
The ability for a computer to be able to "see" and "interpret" an image is both helpful and profitable. From search engines retrieving relevant articles to annotating keywords to automatically tagging products in online catalogs, the use cases are endless. If we were to continue refining this project, we would like to apply it to:
1. Analyzing product images and automatically suggest relevant attributes and categories in ecommerce catalogs
2. Assigning relevant keywords to images that reflect their visual content for search engines
3. Creating a product for the blind and visually impaired  that will help them navigate through everyday situations
4. Security and fraud detection

## Resources
- [Article on Bahadanu Attention Layer](https://towardsdatascience.com/sequence-2-sequence-model-with-attention-mechanism-9e9ca2a613a)
- [Flickr8 dataset](https://www.kaggle.com/aladdinpersson/flickr8kimagescaptions)
- [Image captioning tutorial](https://www.youtube.com/watch?v=y2BaTt1fxJU&list=PLhhyoLH6IjfxeoooqP9rhU3HJIAVAJ3Vz&index=21)
- [Use Cases](https://evergreen.team/articles/automatic-image-captioning.html)




