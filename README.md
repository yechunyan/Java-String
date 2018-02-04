# Java-String
对常用的String方法做个简单的归纳

    //例如：
    pulbic class Demo{
    public static void main(String args[]){
    String stra = "helloworld" ; //直接赋值的方式
    String strb = new String("helloworld") ; //实例化方式，用new在堆内存中开辟新空间“helloworld”。
    String strc = "HelloWorld" ;
    String strd = " how are you " ;
    
    //第一个：equals方法，stra的值与strb的值比较，内容相同，即为true,否则为false
    System.out.println(stra.equals(strb)); 
    
    //第二个：等号==与equals方法的比较
    System.out.println(stra.equals(strb)) ; //这里返回true,因为equals()方法是对内容的比较，即相同值一样就可以。
    System.out.println(stra == strb) ; //这里返回false，因为==是对内存的值比较，虽然他们的内容都是helloworld,
    但是stra是直接赋值，没有开辟新的空间，所以他们在内存的值是不一样的。
    
    //第三个：intern()方法，手动入池。
    System.out.println(stra == strb) ; //返回false，上面说了是因为==是对内存的值比较,且stra是直接赋值的方法，
    所以值会自动入池。
    System.out.println(stra == strb.intern()) ;//返回true,这是因为intern()方法把在堆内存开辟的“helloworld”
    手动入池，new后的不会自动入池。
    System.out.println(strb == stra.intern()) ; //返回false,这是因为stra本身是直接赋值的方式实例化，
    系统会自动入池，而strb是new开辟了新空间，系统不会自动入池，所以注意这里不要写反了。
    
    //第四个：equlasIgnoreCase()方法，不区分大小写。
    System.out.println(stra.equalsIgnoreCase(strc)) ; //返回true,虽然strc的值中有大写，
    但是equlasIgnoreCase()方法是不区分大小写。
    
    //第五个：contains()方法，包含的意思。
    System.out.println(stra.contains("he")) ; //返回true
    System.out.println(stra.contains("ho")) ; //返回false,虽然"h"和"o"都在里面，
    但是不是靠在一起，中间有别的字母。所以要注意。
    
    //第六个：compareTo()方法，字符串的比较。
    System.out.println(stra.compareTo(strb)) ; //返回0,因为这两个字符串比较的大小一样。
    System.out.println(stra.compareTo(strc)); //返回32，因为stra的值比strc的值大于32，
    如：h=H+32,同理：a=97,A=65,a=A+32
    
    //第七个：trim()方法，去掉左右空格，但中间的空间不会去掉。
    System.out.println(strd.trim());
    
    //第八个：length()方法,字符串长度
    Syste.out.println(stra.length()) ;//返回长度值，如helloworld长度为10，注意，字符串的length()后面是带括号的，
    与数组不同，数组length是不带括号的。
    
    //第九个：isEmpty()方法,判断是否为空。
    System.out.println(stra.isEmpty()) ; //返回false,因为stra的值不是为空。
    
    //第十个：substring()方法，截取字符串
    System.out.println(stra.substring(5)) ; //返回world，因为“helloworld”被截取从第5位开始，注意，位数是从0开始，
    即：“helloworld”表示“0~9”，所以从第五位开始是"w"。
    
    //第十一个：concat(),这是与“+”连接符一样
    System.out.println(stra.concat(strb)) ;//返回“helloworldhelloworld”,两个连续拼接在一起的字符串。
    
    //第十二个：toLowerCase()方法,小写转换
    System.out.println(strc.toLowerCase()) //strc值中有大写字母的全部转换成小写字母。
    
    //第十三个：toUpperCas()方法，大写转换
    System.out.println(stra.toLowerCase()) //stra值中所有小写字母的全部转换成大写字母。
    
    //第十四个：indexOf,表示返回从左到右（或从前到后）所指定的第一个位置。
    System.out.println(stra.indexOf("o")) ;//返回4，所以从左边的0位开始算起，“helloworld”第四位是“o”。
    
    //第十五个：lastIndexOf，表示返回从右到左（或从后到前）所指定的第一个位置。
    System.out.println(stra.lastIndexOf("o")) ;//返回6,从右向左算“o”的位置在第6位。
    
    //第十六个方法：replaceAll(),表示替位所有指定的目标
    System.out.println(stra.replaceAll("l","_")) ; //返回he__owor_d,把所有的"l"都被替换成“_”下划线。
    
    //第十七个方法：replaceFirst(),表示替位从左到右指定的第一位置的目标，其它位置不替换
    System.out.println(stra.replaceFirst("l","_")) ; //返回he_loworld。
    
    //第十八个方法：startsWith(),判断从左到右开始位置与指定的目标是否相同
    System.out.println(stra.startsWith("he")) ; //返回true,因为stra的值helloworld，是从he开头。
    System.out.println(stra.startsWith("el")) ; //返回false，因为指定的“el”与开始的值不符。
    System.out.println(stra.startsWith("el",1)) ; //返回true,因为从第一位开始算起，"el"与helloworld的值相同，
    注意，“helloworld”是从0开始算起，所以“e”是排在第二位其实就是1。
    
    //第十九个方法：endsWith()，判断从右到左开始位置与指定的目标是否相同
    System.out.println(stra.startsWith("ld")) ; //返回true,同理，与上面的startsWith()方法逻辑一样。
    
    //第二十个方法：split()方法，拆分字符串
    String stra ="hello.world";
    String result [ ] =stra.split("\\."); //因为把字符串拆分后，就变成一个个字符，所以split()方法，需要定义数组，
    这里split()方法是按“.”来拆分的，但是因为点“.”是特殊字符，所以需要转义，即正则
		  
      for(int x=0;x<result.length;x++){ //遍历
      
		System.out.println(result[x]); //按点拆分，输出。
        }
    }
}
