static:在类初次被加载时就被初始化了,所有对象共享,只有一个副本.没有的在对象被创建时初始化,每一个对象都有一个副本
sql:列别名不能用在where中,但是可以用在order by 中	
	Select -1>选择列,-2>distinct,-3>top
	  1>…From 表
	  2>…Where 条件
	  3>…Group by 列
	  4>…Having 筛选条件
	  6>…Order by 列
	  top仅在个别数据库能够使用,MySQL使用limit
	  布尔逻辑:and,or,not,between,in,is,null
		SELECT DISTINCE name,age
		FROM users  
		如果name相同,age不同,不会被删除
	  聚合函数:sum(),count(),min(),max(),avg();操作一列
	  count(*),count(列名):
	  count(*)查询所有,只要这条记录有值就会被统计,当字段数量多时,建议用count(*),它与偏移量无关;当建立索引的字段有不为空设置时,count(*)可以用到索引,此时两者一样快
	  count(列名)只统计此列存在的,如果使用索引的话快速.但是当字段数量过多,偏移量太大的话速度变慢,此时建议使用count(*)
	"SELECT
	GradeType AS 'Grade Type',
	AVG(Grade)AS 'Average Grade'
	FROM Grades
	GROUP BY GradeType
	ORDER BY GradeType"------计算出每个级别类型的平均值并且按照级别类型升序排序
	基于聚合查询条件-HAVING
	WHERE子句是单独的执行查询条件.HAVING关键字允许对于组级别使用查询条件-----搜索选修课类型为A并且所有课程平均成绩大于70的成绩
	
	注意：如果想要在结果中添加GradeType的值，如果直接在SELECT后边添加这个列，将会出错。这是因为，所有列都必须要么出现在GROUP BY中，要么包含在一个聚合函数中。
	SELECT 
	Name,
	GradeType,
	AVG(ISNULL(Grades,0)) AS 'Average Grades'
	FROM Grades
	WHERE GradeType='A'
	GROUP BY Name,GradeType
	HAVING AVG(ISNULL(Grades,0))>70
	ORDER BY Name
 
JVM:Java经过编译后产生.class文件,JVM来解释运行它.针对每个操作系统有它自己对应的版本
每当运行一个程序时,Java程序会开启一个进程.
static不能使用this,super关键字,因为this代表对象,类被初始化时对象可能不存在
方法什么时候被定义成静态:此方法如果没有引用此类中非静态属性和方法时就可以被定义为静态
静态代码块只在类加载时被执行一次(new 多个对象只执行一次).如果和主方法在一个类中则优先于主方法执行
主函数的解释:保证所在类的独立运行.是程序的入口,被JVM调用
继承:当new子类对象时,会先new父类对象.当重写父类run方法时,不需要将super.run()方法放在第一位,因为此时父类对象已经加载完毕
非静态方法:编译看左边,运行看右边
静态方法:编译看左边,运行看左边
JS:
添加/删除一个元素都需要获得这个元素的父元素
如果能够在不引用父元素的情况下删除某个元素，就太好了。
不过很遗憾。DOM 需要清楚您需要删除的元素，以及它的父元素。
这是常用的解决方案：找到您希望删除的子元素，然后使用其 parentNode 属性来找到父元素：
var child=document.getElementById("p1");
child.parentNode.removeChild(child);

JavaScript中的所有事物都是对象：字符串、数值、数组、函数...
此外，JavaScript 允许自定义对象。
JavaScript 对象
JavaScript 提供多个内建对象，比如 String、Date、Array 等等。
对象只是带有属性和方法的特殊数据类型
JS对象与json的区别:JS对象的key不加引号
提示：绝不要在数字前面写零，除非您需要进行八进制转换.
属性：
    MAX VALUE
    MIN VALUE
    NEGATIVE INFINITIVE
    POSITIVE INFINITIVE
    NaN
    prototype
    constructor

方法：
    toExponential()
    toFixed()
    toPrecision()
    toString()
    valueOf()

JavaScript String（字符串）对象 实例:
计算字符串的长度
    如何使用长度属性来计算字符串的长度。
为字符串添加样式
    如何为字符串添加样式。
indexOf() 方法
    如何使用 indexOf() 来定位字符串中某一个指定的字符首次出现的位置。
match() 方法
    如何使用 match() 来查找字符串中特定的字符，并且如果找到的话，则返回这个字符。
如何替换字符串中的字符 - replace()
    如何使用 replace() 方法在字符串中用某些字符替换另一些字符。

日期对象用于处理日期和时间。
JavaScript Date（日期）对象 实例
返回当日的日期和时间
    如何使用 Date() 方法获得当日的日期。
getTime()
    getTime() 返回从 1970 年 1 月 1 日至今的毫秒数。
setFullYear()
    如何使用 setFullYear() 设置具体的日期。
toUTCString()
    如何使用 toUTCString() 将当日的日期（根据 UTC）转换为字符串。
getDay()
    如何使用 getDay() 和数组来显示星期，而不仅仅是数字。
显示一个钟表
    如何在网页上显示一个钟表。
创建数组
    创建数组，为其赋值，然后输出这些值。
For...In 声明
    使用 for...in 声明来循环输出数组中的元素。
合并两个数组 - concat()
    如何使用 concat() 方法来合并两个数组。
用数组的元素组成字符串 - join()
    如何使用 join() 方法将数组的所有元素组成一个字符串。
文字数组 - sort()
    如何使用 sort() 方法从字面上对数组进行排序。
数字数组 - sort()
    如何使用 sort() 方法从数值上对数组进行排序。
Window 对象
所有浏览器都支持 window 对象。它表示浏览器窗口。
所有 JavaScript 全局对象、函数以及变量均自动成为 window 对象的成员。
全局变量是 window 对象的属性。
全局函数是 window 对象的方法。
甚至 HTML DOM 的 document 也是 window 对象的属性之一：
ArrayList:
是List接口的可变数组的实现。实现了所有可选列表操作，并允许包括 null 在内的所有元素。除了实现 List 接口外，此类还提供一些方法来操作内部用来存储列表的数组的大小。
每个ArrayList实例都有一个容量，该容量是指用来存储列表元素的数组的大小。它总是至少等于列表的大小。随着向ArrayList中不断添加元素，其容量也自动增长。
自动增长会带来数据向新数组的重新拷贝，因此，如果可预知数据量的多少，可在构造ArrayList时指定其容量。在添加大量元素前，应用程序也可以使用ensureCapacity操作来增加
ArrayList实例的容量，这可以减少递增式再分配的数量。注意，此实现不是同步的。如果多个线程同时访问一个ArrayList实例，而其中至少一个线程从结构上修改了列表，那么它必须保持外部同步。	

cpu个数、核数、线程数、Java多线程关系的理解:
tomcat是由Java写的一个软件(也就是一套程序),所以当启动tomcat时需要告知JDK(内有JVM)的安装位置.tomcat是由JVM运行的,每启动一个tomcat就会在内存中存在一个JVM实例;
软件是一个物理上存在的一个可运行的文件,进程是逻辑上的软件在内存中的实例.
一 cpu个数、核数、线程数的关系
cpu个数：是指物理上，也及硬件上的核心数；
核数：是逻辑上的，简单理解为逻辑上模拟出的核心数；
线程数：是同一时刻设备能并行执行的程序个数，线程数=cpu个数 * 核数
二 cpu线程数和Java多线程
首先明白几个概念：
(1) 单个cpu线程在同一时刻只能执行单一Java程序，也就是一个线程
(2) 单个线程同时只能在单个cpu线程中执行
(3) 线程是操作系统最小的调度单位，进程是资源（比如：内存）分配的最小单位
(4) Java中的所有线程在JVM进程中,CPU调度的是进程中的线程
(5) Java多线程并不是由于cpu线程数为多个才称为多线程，当Java线程数大于cpu线程数，操作系统使用时间片机制，采用线程调度算法，频繁的进行线程切换。
a 那么java多进程，每个进程又多线程，cpu是如何调度的呢？
个人理解：操作系统并不是单纯均匀的分配cpu执行不同的进程，因为线程是调度的最小单位，所以会根据不同进程中的线程个数进行时间分片，均匀的执行每个线程，也就是说A进程中有10个线程，而B进程中有2个进程，那么cpu分给进程的执行时间理论上应该是5:1才合理。
b cpu线程数和java线程数有直接关系吗？
个人理解：没有直接关系，正如上面所说，cpu采用分片机制执行线程，给每个线程划分很小的时间颗粒去执行，但是真正的项目中，线程要做很多的的操作，读写磁盘、数据逻辑处理、出于业务需求必要的休眠等等操作。
c 如何确定程序线程数？
个人理解：一般情况程序线程数等于cpu线程数的两到三倍就能很好的利用cpu了，过多的程序线程数不但不会提高性能，反而还会因为线程间的频繁切换而受影响，具体需要根据线程处理的业务考略，不断调整线程数个数，确定当前系统最优的线程数。
 JVM是一份本地化的程序，本质上是可执行的文件，是静态的概念。程序运行起来成为进程，是动态的概念。
 java程序是跑在JVM上的，严格来讲，是跑在JVM实例上的，一个JVM实例其实就是JVM跑起来的进程，二者合起来称之为一个JAVA进程.各个JVM实例之间是相互隔离的。

 HashMap:
 它根据键的HashCode存储值,键只能一条为null,值可以有多条为null.
 LinkedHashMap也是HashMap,内部维持了一个双向链表,可以保持顺序
 TreeMap可以用于排序
 
 区别class类的实例和类的实例: 
 java每个类都对应一个class类的实例，class类的实例在jvm加载类时创建。synchronized (someclass.class) or public synchronized static void 
 somestaticmethod()会使用someclass.class监视器。
 
 关于使用@Autowired注解为空:只有添加spring注解例如(@Controller,@Component)交给spring管理,spring才会将bean注入

 总之，创建字符串有两种方式：两种内存区域(pool,heap)
      1.""创建的字符串在字符串池中。
      2.new 创建字符串时，首先查看池中是否有相同的字符串，如果有则拷贝一份放到堆中，然后返回堆中的地址；如果池中没有则在堆中创建一分，然后返回堆中的地址，
      3.在对字符串赋值时，如果右操作数含有一个或一个以上的字符串引用时，则在堆中再建立一个字符串对象，返回引用如：String s= str1+"blog";

关于虚拟机内存分布:https://www.cnblogs.com/dreamroute/p/5946272.html
Java中的常量池，实际上分为两种形态：静态常量池和运行时常量池。
所谓静态常量池，即*.class文件中的常量池，class文件中的常量池不仅仅包含字符串(数字)字面量，还包含类、方法的信息，占用class文件绝大部分空间。
而运行时常量池，则是jvm虚拟机在完成类装载操作后，将class文件中的常量池载入到内存中，并保存在方法区中，我们常说的常量池，就是指方法区中的运行时常量池

精度损失:https://www.cnblogs.com/kniught-ice/p/4755122.html
首先需要注意的是，直接使用字符串来构造BigDecimal是绝对没有精度损失的，如果用double或者把double转化成string来构造BigDecimal依然会有精度损失，
所以我觉得这种解决方法就是在数据库中就把浮点数用string来表示存放，涉及到运算直接用string构造double，否则肯定会有精度损失。

new comparator<T>返回值:
分析：返回值分为负数正数和0
负数代表左值小于右值，排在上面
正数代表左值大于右值，排在下面
0代表左值等于右值，排在上面
可以这样理解：排序就是比较谁大谁小，将小的放在前面，大的放在后面。例如当返回负数的时候，表明第一个数应该排在第二个数的上面。
可以按照你想要的规则进行排序，不论是按照集合中的正序（返回值1），还是集合中的倒序（返回值-1）还是按照字典排序（如上），都是可以的。


package com.xhengxuyuanzhi;

/**
 * 饿汉式单例模式
 * 特点：可以通过反射机制攻击；线程安全[多个类加载器除外]。
 */
public class HungryType {
    public static final HungryType instance = new HungryType();   
    private HungryType(){
        //初始化HungryType要做的事
    }   
    public void splitAlipay() {
        System.out.println("饿汉式单利模式");
    }   
    public static void main(String[] args) {
        HungryType ht = HungryType.instance;
        ht.splitAlipay();       
    }
}


package com.xhengxuyuanzhi;

/**
 * 懒汉模式单例
 * 特点：延时加载；线程不安全，多线程下不能正常工作；
 */
public class SluggardType {
    private static SluggardType instance = null;
    
    private SluggardType() {
    
    }
    
    public static SluggardType getInstance(){
        if(instance == null){
            instance = new SluggardType();
        }
        return instance;
    }
    
    public void say(){
        System.out.println("懒汉模式单例");
    }
    
    public static void main(String[] args) {
        SluggardType.getInstance().say();
    }
}


package com.xhengxuyuanzhi;

/**
 * 懒汉模式(双重校验锁[不推荐])单例
 */
public class SluggardType2 {  
    //volatile 关键字可以禁止指令重排 ：可以确保instance = new SluggardType2()对应的指令不会重排序
    //但是因为对volatile的操作都在Main Memory中，而Main Memory是被所有线程所共享的，这里的代价就是牺牲了性能，无法利用寄存器或Cache
    private volatile static SluggardType2 instance = null;  
    private SluggardType2(){}    
    public static SluggardType2 getInstance(){
        if(instance == null){
            synchronized (SluggardType2.class) {
                if(instance == null){
                    instance = new SluggardType2();
                }
            }
        }    
        return instance;
    }    
    public void say(){
        System.out.println(" 懒汉模式(双重校验锁[不推荐])单例");
    }   
    public static void main(String[] args) {
        SluggardType2.getInstance().say();
    }        
}


package com.xhengxuyuanzhi;

/**
 * @author 微信公众号：程序员之路 
 *         博客：http://www.cnblogs.com/chengxuyuanzhilu/
 * 
 * 借助内部类实现单利模式：
 * 特点：既能实现延迟加载，又能实现线程安全
 */
public class InnerClassSingleton {
    /**
     * 类级的内部类，也就是静态的成员式内部类，该内部类的实例与外部类的实例没有绑定关系，而且只有被调用到时才会装载(装在过程是由jvm保证线程安全)
     * ，从而实现了延迟加载
     */
    private static class SingletonHolder {
        /**
         * 静态初始化器，由JVM来保证线程安全
         */
        private static InnerClassSingleton instance = new InnerClassSingleton();
    }

    /**
     * 私有化构造方法
     */
    private InnerClassSingleton() {
    }

    /**
     * 这个模式的优势在于：getInstance方法并没有被同步，并且只是执行一个域的访问，因此延迟初始化并没有增加任何访问成本
     */
    public static InnerClassSingleton getInstance() {
        return SingletonHolder.instance;
    }

}


package com.xhengxuyuanzhi;
/*
 * 枚举实现线程安全的单例模式:
 * 特点：JVM会保证enum不能被反射并且构造器方法只执行一次
 */
public class EnumSingleton {
    private EnumSingleton() {}
    public static EnumSingleton getInstance() {
        return Singleton.INSTANCE.getInstance();
    }
    private static enum Singleton {
        INSTANCE;
        private EnumSingleton singleton;
        // JVM会保证此方法绝对只调用一次
        private Singleton() {
            singleton = new EnumSingleton();
        }
        public EnumSingleton getInstance() {
            return singleton;
        }
    }
}

获取class类的三种方式:
对象.getClass();
Class.forName("");
类.class;

sleep()方法和wait()方法简单对比
两者最主要的区别在于：sleep方法没有释放锁，而wait方法释放了锁 。
两者都可以暂停线程的执行。
Wait通常被用于线程间交互/通信，sleep通常被用于暂停执行。
wait()方法被调用后，线程不会自动苏醒，需要别的线程调用同一个对象上的notify()或者nofifyAl()方法。sleep()方法执行完成后，线程会自动苏醒。

为什么我们调用start()方法时会执行run()方法，为什么我们不能直接调用run()方法？
这是另一个非常经典的java多线程面试问题，而且在面试中会经常被问到。很简单，但是很多人都会答不上来！
new一个Thread，线程进入了新建状态;调用start()方法，会启动一个线程并使线程进入了就绪状态，当分配到时间片后就可以开始运行了。 
start()会执行线程的相应准备工作，然后自动执行run()方法的内容，这是真正的多线程工作。 
而直接执行run()方法，会把run方法当成一个mian线程下的普通方法去执行，并不会在某个线程中执行它，所以这并不是多线程工作。
总结： 调用start方法方可启动线程并使线程进入就绪状态，而run方法只是thread的一个普通方法调用，还是在主线程里执行。

















 


