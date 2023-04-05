# JS Function

## Function 本质是 object
- let f = function(){};
- array.push(function(){});
- function call(func){func();}
- return function(){}
- f.myName = "power"; 可以拥有property

## rest参数——接受不定长参数
- 声明时rest参数只能为最后一个
- 参数名称前加...
- 在函数内，rest是一个数组
```JS
    let max = function(first, ...rest) {
        let res = first;
        rest.foreach(x => res = max(res, x));
        return res
    }
```

## arguments 隐式保存参数（引用）
```JS
    let f = function(a) {
        assert(a == arguments[0])
        a = 1
        assert(a == arguments[0])
    }
```
- arrow function 没有自己的arguments
- arguments 总是忠实的记录着函数调用时实际传入的参数

## spread 操作符...array 相当于python中的*list
```JS
    let values = [1,2,3,4];
    Math.max(...values)
```