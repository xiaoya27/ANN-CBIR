## the structure/content of the python notebook are listed as follows:

[part1](part1_feature_extraction.ipynb):

* Features from pretrained models like VGG-16, VGG-19, ResNet-50, InceptionV3 and MobileNet

* Benchmark feature extraction speed with different model 

* finetuned MobileNet with caltech101 labeled data


[part2](part2_similarity_search.ipynb): 

* Index feature list with Nearest Neighbor Brute Force Algorithm and visualize with PCA and t-SNE



[part3](part3_similarity_search.ipynb): 

* benchmark the algorithms based on the time it takes to index images and locate the most similar image based on its features using the Caltech-101 dataset.



TODO:

* Reduce feature dimension 

* Query accuracy with Euclidean L2  vs  cosine vs regular Euclidean distance

### Some benchmarks on different algorithms to see relative speeds

These results lead to the benchmarking of time for indexing and searching on Caltech101. Repeating Level 2 on the Caltech256 features we can benchmark that as well. 

Benchmarking the different models on Caltech101. (Rounded to nearest integer)

| Algorithm | Number of features indexed | Time to search 1 image (ms) | Time to search 100 images (ms)  | Time to search 1000 images (ms)  | Time to index (ms)    |
|-------------|----------------------------|------------------------|---------------------------|---|---|
| Brute force | 2048 | 14 | 38 | 240 | 22 | 
| k-d tree | 2048 | 16 | 2270 | 24100 | 1020    |
| Ball tree | 2048 | 15 | 1690 | 17000 | 1090   |
| PCA + brute force | 100 | 1 | 13 | 135 | 0.334   |
| PCA + k-d tree | 100 | 1 | 77 | 801 | 20   |
| PCA + ball tree | 100 | 1 | 80 | 761 |  23   |
| Annoy | 2048 | 0.16 | 40    | 146 | 1420 |
| PCA + Annoy | 100 | **.008** | **2.3**   | **20.3** | 109 | 



