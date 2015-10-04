# 简单计算器
  支持加、减、乘、除、括号的整数运算
  错误处理相关的代码省略了

##原理: 
###第1步: 
将表达式中的每个元素保存到链表中存储, 并且简单的处理负数
如: -4+(-12+25)*(-30) 到list中之后: 

    node1:  (
    node2:  0
    node3:  -
    node4:  4
    node5:  )
    node6:  +
    node7:  (
    node8:  0
    node9:  -
    node10: 12
    node11: +
    node12: 25
    node13: )
    node14: *
    node15: (
    node16: 0
    node17: -
    node18: 30
    node19: )
    
###第2步: 利用递归下降的方法把表达式转换为具有优先级的表达式树. 
上面的式子转换之后的数据结构为:

              +
          /      \
         -        *
        / \     /   \
       0   4    +    -
               / \  / \
              -  25 0 30
             / \
            0  12
            
###第3步: 后序遍历这个表达式树, 遇到数字就压栈, 遇到操作符就出栈计算, 再把结果压栈

最后栈顶元素就是运算结果






