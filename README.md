//# hi
//for Babeltime
//这个是一个简单的加减乘除的java小程序，数学世界有这些简单的运算逐渐构成，游戏世界也是由简单的一行行代码构成，大道相同
import java.util.Stack;


public class BasicCalculatorII {

    public int calculate(String s) {
     int res=0,d=0;
     char sign='+';
     Stack<Integer> nums=new Stack<Integer>();
     for(int i=0;i<s.length();i++){
    	 if(s.charAt(i)>='0'){
    		 d=d*10+s.charAt(i)-'0';
    	 }
    	 if(s.charAt(i)<'0'&&s.charAt(i)!=' '||i==s.length()-1){
    		 if(sign=='+') nums.push(d);
    		 if(sign=='-') nums.push(-d);
    		 if(sign=='*'||sign=='/'){
    			 int tmp=sign=='*'?nums.peek()*d:nums.peek()/d;
    			 nums.pop();
    			 nums.push(tmp);
    		 }
    	  sign=s.charAt(i);
    	  d=0;
    		 
    	 }
    	 

     }
    	
    	while(!nums.isEmpty()){
    		 res+=nums.pop();
    	 }
    	 return res;
    	
    }
	
}
