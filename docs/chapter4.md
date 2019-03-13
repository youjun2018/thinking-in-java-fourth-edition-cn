
# 第4章 控制执行流程

在 Java 中，涉及的关键字包括 **if-else、while、do-while、for、return、break** 以及选择语句 **switch**。然而，Java并不支持 **goto** 语句（该语句引起许多反对意见，但它仍是解决某些特殊问题的最便利的方法）。在 Java 中，仍然可以进行类似 **goto** 那样的跳转，但比起典型的 **goto**，有了很多限制。

## 4.1 true和false

注意，Java 不允许我们将一个数字作为布尔值使用，虽然这在C和C++里是允许的（在这些语言里，“真”是非零，而“假”是零）。如果想在布尔测试中使用一个非布尔值，比如在 **if(a)** 中，那么首先必须用一个条件表达式将其转换成布尔值，例如 **if(a!=0)**。

## 4.2 if-else

其中 **else** 是可选的，两种形式，如下：



```
if(Boolean-expression)
  statement
```



或



```
if(Boolean-expression)
  statement
else
  statement
```



## 4.3 迭代

**while、do-while** 和 **for** 用来控制循环，有时将它们划分为<font face="">迭代语句</font>(iteration statement)。语句会重复执行，直到起控制作用的<font face="">布尔表达式</font>(Booleanexpression)得到“假”的结果为止。**while** 循环的格式如下：



```
while(Boolean-expression)
  statement
```



### 4.3.1 do-while

格式如下：



```
do
  statement
while(Boolean-expression);
```



### 4.3.2 for



```
for(initialization; Boolean-expression; step)
  statement
```



<font face="楷体">初始化</font>(initialization)表达式、<font face="楷体">布尔表达式</font>(Bolean-expression)，或者<font face="楷体"></font>(step)运算，都可以为空。

### 4.3.3 逗号操作符

本章前面已经提到了逗号操作符（注意不是逗号分隔符，逗号用作分隔符时用来分隔函数的不同参数），Java 里唯一用到逗号操作符的地方就是 **for** 循环的控制表达式。在控制表达式的初始化和步进控制部分，可以使用一系列由逗号分隔的语句；而且那些语句均会独立执行。

在一个控制表达式中，定义多个变量的这种能力只限于 **for** 循环适用，在其他任何选择或迭代语句中都不能使用这种方式。

## 4.4 Foreach语法

Java SE5 引入了一种新的更加简洁的 **for** 语法用于数组和容器，即foreach语法，表示不必创建 **int** 变量去对由访问项构成的序列进行计数，foreach将自动产生每一项。



```
for（float x : f)  // float f = new float[10];
  System.out.println(x);
```



任何返回一个数组的方法都可以使用 foreach。例如，**String** 类有一个方法 **toCharArray()**，它返回一个 **char** 数组，因此可以很容易地像下面这样迭代在字符串里面的所有字符：



```
for(char c: "An African Swallow".toCharArray())
  System.out.print(c + " ");
```



foreach 还可以用于任何 **Iterable** 对象。

## 4.5 return

在 Java 中有很多个关键词表示无条件分支，它们只是表示这个分支无需任何测试即可发生。这些关键词包括 **return、break、continue** 和一种与其他语言中的 goto 类似的跳转到标号语句的方式。

**return** 关键词有两方面的用途：一方面指定一个方法返回什么值（假设它没有 **void** 返回值），另一方面它会导致当前的方法退出，并返回那个值。

如果在返回 **void** 的方法中没有 **return** 语句，那么在该方法的结尾处会有一个隐式的 **return**，因此在方法中并非总是必须要有一个 **return** 语句。

## 4.6 break和continue

在任何迭代语句的主题部分，都可用 **break** 和 **continue** 控制循环的流程。其中，**break** 用于强行退出循环，不执行循环中剩余的语句。而 **continue** 则停止执行当前的迭代，然后退出循环起始处，开始下一次迭代。

无穷循环的第二种形式是 **for(;;)**。编译器将 **while(true)** 与 **for(;;)** 看作是同一回事。所以具体选用哪个取决于自己的编程习惯。

## 4.7 臭名昭著的goto









































end of chapter 4
