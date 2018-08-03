---
layout: post
comments: true
title:  "Heaps & Heapsort!"
subtitle: "Implementation of Priority Queue"
date:   2018-8-3 06:10:00 -0400
background: '/img/posts/02.jpg'
---

html header: <script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>



## Heaps & Heapsort

#### Priority Queue:

##### Definition: Implement a set S of elements, each elements associated with a key.

> `insert(S,x)` : Insert element x into set S.
>
> `max(S)` : Return element of S with the largest key.
>
> `extract_max(S)` : Return element of S with the largest key, and remove it from set S.
>
> `increse_key(S,x,k)` :  Increse the val of x's  key to new value k.



#### Heap 

##### Definition: Implementation of a Priority Queue. An array visualized as a nearly complete binary tree. 

> ##### Heap as a Tree.
>
> root of  tree : first element (i = 1)
>
> ​	(it is much easier to implement with the initial index 1) 
>
> `parent(i) = i/2;`
>
> `left(i) = 2*i`
>
> `right(i) = 2*i +1`



> Max-Heap property : The key of a node is greater than or equal to (>=) the keys of its children 
>
> Min-Heap property : The key of a node is smaller than or equal to (<=) the keys of its children

An example of a max-heap (binary tree)

<<<<<<< HEAD
![](C:\Users\super\Documents\GitHub\withjack.github.io\_posts\algorithms\heap.jpg)
=======
![img](https://github.com/withJack/withjack.github.io/blob/master/_posts/algorithms/heap.jpg) 
>>>>>>> 7421ab1ca0d3d395936f3bb56d08c78b88b19785



#### Heapsort

##### Definition: Transforming an array into new array which satisfies either the max-heap property or the min-heap property.

> ##### Heap operations
>
> `build_max_heap()` : Produces a max-heap from an unordered array.
>
> `max_heapify(A, i)` : Correct a single violation of the heap property in a subtree's root. 
>
> ​	Assumption : Trees rooted at `left(i)` and `right(i)` are max heaps.
>
> ​	Complexity : $ theta $( lg(n) ). Hight of the tree is lg(n), 
>
> `heap_size(A)` : Number of nodes (or indices).
>
> ##### converting A[1...n] into a max-heap (pseudo-code)
>
> ```pseudocode
> Build-max-heap(A):
> 
> 	for i = n/2 down to 1
> 
> 		do max_heapify(A, i)
> ```
>
> * Why n/2 down to 1: Elements A[n/2+1 ... n] is always leaves. Leaves always satisfies the assumption!
> * Complexity for Build-max-heap(A) : O(nlg(n))
>
> ##### Observation 
>
> 1. `max_heapify` taken O(1) for nodes that are one level above the leaves and in general O(L) time for nodes that are L level above the leaves.
>
> 2. n/4 nodes with level 1, n/8 with level 2, ... ,1 node with lg(n) level.
>
> 3. Total amount of work in the for loop (pseudo-code): 
>
>    $$ n/4(1c) + n/8(2c) + ... 1(lg(n)c) = c2^k (1/2^0 + 2/2^1 + ... + (k+1)/2^k) $$ when $$ n/4 = 2^k $$
>
>    $$ c(1/2^0 + 2/2^1 + ... + (k+1)/2^k) $$ is bounded by constant and $$ 2^k $$ is O(n). 
>
> -> Complexity : O(n) 
>
> ##### Heapsort (pseudo-code)
>
> ```
> Build-max-heap from unordered array                                 - O(n)
> recursive (n times)
>     find max element A[1]                                           - O(1)
>     swap elements A[n] with A[1].                                   - O(1)
>         (now max element is at the end of array)
>     discend node n from heap. decrementing heap-size.
>     new root may violate max heap, but children are max-heap.       - O(lg(n))
> ```
>
> Complexity : O(nlg(n))



### Implementation

I have a sample implementation for Heapsort in my [github](https://github.com/withJack/Algorithm-Implementations/blob/master/Heapsort.cpp).

It has some difference between Explanation above and the code.

Please look at the comments in the code for better understanding.      
  
  
  
  
  
Thanks, with Jack.  
  
  
  
  
  
{% include disqus.html %}
