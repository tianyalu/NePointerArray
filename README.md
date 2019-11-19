## NePointerArray 指针数组，数组指针
**注意：**  
优先级：() > [] > *
### 1. 指针
```c
//指针
void pointer() {
    int arr[] = {100, 200, 300};
    for (int i = 0; i < 3; i++) {
        printf("数组 %d\n", arr[i]);
    }
//    int* p = arr;
    int* p = &arr[0];
    *(p + 1) = 400;
    for (int i = 0; i < 3; i++) {
        printf("数组： %d\n", arr[i]);
    }
}
```

### 2. 指针数组
是一个数组，里面存放多个指针  
```c 
//int* p[n]
void pointerArray() {
    int arr[] = {100, 200, 300};
    int* p[3]; //指针数组
    printf("-------操作后-------\n");
    for (int i = 0; i < 3; i++) {
        p[i] = &arr[i];
    }
    
    for (int i = 0; i < 3; i++) {
        printf("数组： %d\n", *p[i]);
    }
}
```

### 3. 数组指针
指向一个一维数组的指针，若该一维数组长度为n,则指针+1时会跨越n个数据长度  
```c
//int (*p)[n]
void arrayPointer() {
    int arr[3][4] = {
        {100, 200, 300, 400},
        {500, 600, 700, 800},
        {900, 1000, 1100, 1200}
    };
    int (*p)[4];
    p = arr;
    p++;
    for (int i = 0; i < 3; i++) {
        printf("数组： %d\n", (*p)[i]);
    }
}
```
![image](https://github.com/tianyalu/NePointerArray/blob/master/show/array_pointer.png)
