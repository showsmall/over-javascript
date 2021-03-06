## 一 引用类型

先看一道面试题：
```js
var a = 10;
var b = a;
a = 11;
console.log(b);         // 10

var arr = [1,2,3];
var arr2 = arr;
arr[0] = 9;
console.log(arr2);      // [ 9, 2, 3 ]
```

在上述示例中：
- 数据类型a是基础数据类型，在赋值给b时，是重新申请的内存，并将值拷贝过来进行存储。
- 数据类型arr是引用类型，在复制给arr2时，也重新申请内存，但是拷贝过来的是arr的内存地址，而不是地址指向的值

引用类型存储的数据其实是真实数据在内存中的地址。  

在JS数据类型中，Object类型即是引用类型，基于Object类型还有一些衍生的引用类型，如：Array、Function、Date、Math等。   

## 二 Object数据类型

object数据类型可以通过 Object对象来创建，Object对象可以视为所有对象的祖先对象（基本类），创建方式：
```js
var obj1 = new Object();
var obj2 = new Object;          // 有效，但是不推荐该方式

console.log(typeof obj1);       // object
```

## 三 Object对象实例

由于Object对象是所有对象的祖先对象（基类），所以其属性和方法，其他对象都会拥有：
- `constructor`属性：保存当前对象的构造函数
- `hasOwnProperty(propStr)方法`：检测实例对象是否包含该属性用于检查给定的属性（不会检测原型中的属性）
- `isPrototypeOf(protoObj)方法`：检测当前对象是否是传入的原型对象
- `propertyIsEnumerable(propStr)`：检测传入的参数属性是否能够被for-in枚举到。
- `toString()`：返回对象的字符串表示。
- `valueOf()`：返回对象的字符串、数值或布尔值表示
- `getPrototypeOf(obj)`：返回obj实例对应构造函数的原型

从上看出，Object主要用来处理对象相关的操作。  

