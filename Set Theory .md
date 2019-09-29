
# Defining a set
define a set $S = \{1,2,3,4\}$


```python
S = {1,2,3,4}
```


```python
S
```




    {1, 2, 3, 4}



Verigy type of a variable


```python
type(S)
```




    set



# Basic Operations

## Union
define two sets  $A=\{a,b,c,d\}$ and $B = \{b,c,x,y\}$ and finf their union $C = A \cup B$


```python
A = {'a','b','c','d'}
B = {'b','c','x','y'}
```


```python
C = A.union(B)
```


```python
C
```




    {'a', 'b', 'c', 'd', 'x', 'y'}



## Intersection 
find the intersection of $A$ and $B$ , $D=A\cap B$


```python
D = A.intersection(B)
```


```python
D
```




    {'b', 'c'}



## Difference 
find difference of A and B. The result $(A-B) \ne (B-A)$ shows that, the subjected operation is __not commutative__


```python
A.difference(B)
```




    {'a', 'd'}




```python
B.difference(A)
```




    {'x', 'y'}



Another way to computer Difference is using the $'-'$ operator 


```python
A - B
```




    {'a', 'd'}



## Compliment
the complement operation is not implicitly defined as it's computed with respect to the Universal set($U$). thus to find complement <br>
* Step 1 : Define Universal set $U$
* Step 2 : Calculate Complement $X^c = U - X$


```python
U = {1,2,3,4,5,6,7,8,9,10}
```


```python
U
```




    {1, 2, 3, 4, 5, 6, 7, 8, 9, 10}



Sometimes the set is too large to fill manually, in such cases we take help of a library called __Numpy__. 


```python
import numpy as np  # call it once and rename as np
```


```python
set(np.arange(0,10))
```




    {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}



We've previously defined the set $S={1,2,3,4}$ now to find the complement of $S$ w.r.t $U$, we'll compute $U-S$


```python
S
```




    {1, 2, 3, 4}




```python
U-S
```




    {5, 6, 7, 8, 9, 10}



## Subset 
check if $A=\{1,2,3\}$ is a subset of $B=\{0,1,2,3,4,5\}$ ? 


```python
A = {1,2,3}
B = {0,1,2,3,4,5}
```


```python
A.issubset(B)
```




    True




```python
B.issuperset(A)
```




    True



## Disjoint set
Check if $A=\{1,3,5\}$ and $B=\{2,4,6\}$ are disjoint sets?


```python
A={1,3,5}
B={2,4,6}
```


```python
A.isdisjoint(B)
```




    True



# Advanced Operations 
the following operations are bit advanced in nature, there are no inbuild functions in python to compute them, However
implementation in python are given below.

## Power set 


```python
def powerset(s):
    x = len(s)
    masks = [1 << i for i in range(x)]
    for i in range(1 << x):
        yield [ss for mask, ss in zip(masks, s) if i & mask]
x=list(powerset([1,2,3]))
p={None}
for i in x:
    print(set(i))
```

    set()
    {1}
    {2}
    {1, 2}
    {3}
    {1, 3}
    {2, 3}
    {1, 2, 3}
    

## Catesian Product 


```python
import itertools as it

X = {1,2,3}
Y = {2,3,4}
set(it.product(X,Y))
```




    {(1, 2), (1, 3), (1, 4), (2, 2), (2, 3), (2, 4), (3, 2), (3, 3), (3, 4)}




```python
A={None}
```


```python
A.union({1})
```




    {1, None}




```python

```
