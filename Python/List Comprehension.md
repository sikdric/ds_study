- 가장 기본적인 List Comprehension


```python
list1 = [1,2,3,4,5,6,7,8,9,10]
print([x for x in list1])
```

    [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    

- 함수 또는 연산을 추가한 List Comprehension


```python
def ftn(x):
    return x*2

[ftn(x) for x in list1]
```




    [2, 4, 6, 8, 10, 12, 14, 16, 18, 20]



- 조건문을 추가한 List Comprehension
    - 조건이 True인 요소들만 리스트에 추가한다
    - 조건이 False인 친구들은 Drop된다.


```python
[x for x in list1 if x%2==0]
```




    [2, 4, 6, 8, 10]



- 조건에서 False인 친구들도 다른 방식으로 리스트에 추가하고 싶다면?
    - 조건문(if else)을 먼저 넣어준 후에 List Comprehension 실시


```python
[x if x%2==0 else 'False' for x in list1]
```




    ['False', 2, 'False', 4, 'False', 6, 'False', 8, 'False', 10]




```python
['True' if x%2==0 else 'False' for x in list1]
```




    ['False',
     'True',
     'False',
     'True',
     'False',
     'True',
     'False',
     'True',
     'False',
     'True']



- 충첩 for문 List Comprehension
    - list = 大
    - [小 for 中 in 大 for 小 in 中]


```python
list2 = [[1,2,3,4],[6,7,8,9]]
[x for y in list2 for x in y]
```




    [1, 2, 3, 4, 6, 7, 8, 9]



- 응용 


```python
trash = [10,20,30]
list = range(31)

[x for x in list if x not in trash and x>=9]
```




    [9, 11, 12, 13, 14, 15, 16, 17, 18, 19, 21, 22, 23, 24, 25, 26, 27, 28, 29]



- 다음 문장에서 "토"가 몇번 나왔을까?


```python
corpus = "산토끼 토끼야. 어디를 가느냐. 깡충깡충 뛰면서. 어디를 가느냐. 산 고개 고개를. 나 혼자 넘어서. 토실토실 알밤을. 주워 올 테야."
```


```python
len([x for x in list(corpus) if x == '토'])
```




    4


