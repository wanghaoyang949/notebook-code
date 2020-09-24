# leetcode-notebook刷题笔记



## 注意点

数组：

```
1.以下tmp赋值方法完全不同：
  ① 直接赋值，赋值完毕与nums无关：
    int[] tmp=new int[nums.length];
    for(int i=0;i<nums.length;i++){
        tmp[i]=nums[i];
    } 
  ② 引用，类似指针，tmp会随着nums变化而实时变化：
    int[] tmp=nums;
2.利用HashSet的元素不重复性，涉及到:set.contains(nums[i])、set.add(nums[i])方法。同时HashSet和HashMap相比Set是一维，Map是二维。
3.利用Arrays.sort(nums)排序方法，先排序，再判断相邻是否相等。
```

字符串：
```
1.long而非Long;
2.s.charAt(i)而非s.charAt[i];
3.s.indexOf('')可以找到字符在字符串的索引;
4.字符的大写字母比小写字母ASCII码小 32;
5.操作可变字符串使用StringBuilder或StringBuffer，在这些字符串尾部追加字符时用append;
6.equals可用于字符串的比较，不变字符串一般放到前面;
7.substring判断相等一般可以改写为循环每一位判断;
8.append时最好不要多个变量放到一起，可能会造成相加的现象;
               sb.append(String.valueOf(cur) + (sequence.charAt(sequence.length()-1)));
    最好写成：    sb.append(String.valueOf(cur));
                 sb.append((sequence.charAt(sequence.length()-1)));
9.String.valueOf(cur)将int型转为String型。
10.for循环内少一些判断可以优化时间复杂度；
11.判断当前字符串是否超过32位整数，可用 Long.parseLong(sb.toString()) >= Integer.MAX_VALUE；
12.Java封装类和基本数据类型,Long和long的区别：
   · Java的数据类型分为两种：
        ① 基本类型：byte(8),short(16),int(32),long(64),float(32),double(64),char(16), boolean(1)
        ② 对象类型：Byte,Short,Integer,Long,Float,Double,Character,Boolean
   · 上面的对象类型分别是基本类型和包装类型，例如Byte是byte的包装类。
   · Java语言是一个面向对象的语言，但是Java中的基本数据类型却是不面向对象的，这在实际使用时存在很多的不便，为了解决这个不足，在设计类时为每个基本数据类型设计了一个对应的类进行代表，这样8个基本数据类型对应的类统称为包装类（Wrapper Class）
   · 对于包装类说，这些类的用途主要包含两种：
        a、作为和基本数据类型对应的类类型存在，方便涉及到对象的操作。
        b、包含每种基本数据类型的相关属性如最大值、最小值等，以及相关的操作方法。
     Long数据的大小的比较
   · 对于Long类型的数据，这个数据是一个对象，所以对象不可以直接通过“>”,“==”，“<”的比较，如果要比较两个对象的是否相等的话，我们可以用Long对象的.equals（）方法：
            Long l1 = new Long(100);  
            Long l2 = new Long(200);  
            System.out.println(l1.equals(l2));  
   · 如果要进行“>”,“<”的比较的话，可以通过Long对象的.longValue()方法：
            Long l1 = new Long(100);  
            Long l2 = new Long(200);  
            System.out.println(l1.longValue()<l2.longValue());  
   · long数据的大小的比较
      对于long类型的数据，这个数据是一个基本数据类型，不属于对象，所以可以直接通过“>”,“==”，“<”作比较
            long l3 = 300;  
            long l4 = 400;  
            System.out.println(l3>l4);  
            System.out.println(l3<l4);  
            System.out.println(l3==l4);
                    
   · Long.ValueOf("String")返回Long包装类型
   · Long.parseLong("String")返回long基本数据类型
```

链表：
```
1.链表删除节点方法：
 ① 输出删除节点的上个节点node，将node.next赋值为node.next.next；
 ② 输出删除节点node，将node.val赋值为node.next.val，next赋值为node.next.next。
2.引入： ListNode dummy=new ListNode(0);
         dummy.next=head;
  可以处理length为1，n为1的情况。
  即没有进入for循环，可直接利用dummy.next=dummy.next。next;将头结点赋为空。
```

