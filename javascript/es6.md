# es6

**es6，也称es2015**
> 
js的规范从提案到成为标准一般经历5个阶段：statge0-4，展示阶段、征求意见阶段、草案阶段、候选人阶段、定案阶段

**新增的能力**
* let、const：块级作用域，不会变量提升（申明后才能使用）、不允许重复声明，es6一共有6种声明变量的方式：var、function、let、const、import、class。let声明的全局变量将不再是全局对象(window)的属性了
* 解构赋值：
    1. 从数组和对象中取值，为变量进行赋值，称为解构。
    2. 如果右边是不可遍历的结构将会报错(iterator)。
    3. 解构可以指定默认值。
    4. 字符串也可以解构。var [a, b, c] = ‘abc’。
    5. 解构的处理逻辑是右边不是对象，就先封装成对象，然后在这个对象里面找相应属性进行解构，包括原型链上的属性。因此不能转化为对象undefined、null的就会报错。
    6. 函数参数解构，也可以使用默认值
    7. 解构的变量声明语句(前面有var等的，没有的话不会报错)中不能带有()括号，包括函数参数解构
    8. 常用途：[x, y] = [y, x]、返回多个值使用、提取json、函数参数默认值、加载模块时获取模块内对象
* 字符串扩展：``符号
* 正则表达式扩展：new RegExp(/^a$/ig, ‘g’)第二个参数不会报错了
* 数值扩展、Math扩展
* 数组扩展：为Array增加了一些静态方法，from、of，数组实例也增加了一些方法
* 函数扩展
    1. 函数参数默认值
    2. 支持参数结构形式，并可同时使用默认值
    3. 函数的length有变化，会减去默认参数，同理...rest参数也会减去，另外如果默认参数不是尾参数，也会导致之后的参数不算进去
    4. 增加...rest参数，只能是最后一个参数
* 扩展运算符：
    1. …，好例子[…'abcde’]。
    2. 任何实现了iterator接口的对象都可以用扩展运算符...转换成数组[...xxx]，当然没有实现的可以直接用Array.from转换成数组
    3. Map、Set、generator（返回的是遍历器对象）都可以用扩展运算符
* 箭头函数
    1. 函数中的this，是定义时所在的对象，不是使用时所在的对象
    2. 不可以使用new，会报错
    3. 不可以使用arguments，不存在了，可以使用rest参数代替
    4. 不可以使用yield，因此箭头函数不能作为generator函数
    5. 因为箭头函数本身就没有this，所以会沿着作用域链向上找this，也就是说绑定定义时的那个作用域，另外因为没有this，所以箭头函数也不能使用call、apply、bind
* 对象的扩展
    1. 直接写入变量和函数，作为对象的属性和方法
    2. 把表达式放进[]里来作为属性名