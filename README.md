# HITDAY28

package hit.day28;
public class GenericsRevision {
	public static void main(String[] args) {
		Child3<Ball> child3=new Child3<>();
		child3.setObj(new Ball());
		child3.getObj().play();
		
		Child3<Sweet> child33=new Child3<>();
		child33.setObj(new Sweet());
		child33.getObj().eat();
	}
}
class Ball{
	public void play() {
		System.out.println("playing with the ball...");
	}
}
class Sweet{
	public void eat() {
		System.out.println("eating the sweet....");
	}
}
//1. Approach 1
//one way of creating association between child and the items is
class Child{
	Ball ball;
	public void action() {
		ball.play();
	}
}
//the problem with the above association is, the child is tightly coupled with ball
//2. Approach 2
class Child2{
	Object obj;
	public void action() {
		if(obj instanceof Ball) {
			Ball ball=(Ball)obj;
			ball.play();
		}
		else if(obj instanceof Sweet) {
			Sweet sweet=(Sweet)obj;
			sweet.eat();
		}
	}
}
//the problem with the above approach is, though this accept object which looks like loosely coupled
//but the if-else-if ladder makes it tightly coupled...
//the code is open for modification - which is a bad code...
//3. Approach 3  - Generics Approach
class Child3<T>{
	T obj;
	public void setObj(T obj) {
		this.obj=obj;
	}
	public T getObj() {
		return this.obj;
	}
}
  
  package hit.day28;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Iterator;
import java.util.List;
import java.util.ListIterator;
public class ColDemo1 {
	public static void main(String[] args) {
		List<String> list=new ArrayList<>(10);
		list.add("hello");
		list.add("world");
		list.add("hai");
		
		System.out.println(list.get(0));
		System.out.println(list.size());
		System.out.println(list.contains("haiii"));
		System.out.println(list);
		Collections.sort(list);
		System.out.println(list);
		System.out.println(list.isEmpty());
		list.remove(0);
		System.out.println(list);
		list.set(1, "newvalue");//it will replace the existing one at that place
		System.out.println(list);
		Object s[]=list.toArray();
		
		for(int i=0;i<list.size();i++) {
			System.out.println(list.get(i));
		}
		
		for(String ss:list) {
			System.out.println(ss);
		}
		Iterator<String> iter=list.iterator();
		while(iter.hasNext()) {
			System.out.println(iter.next());
		}
		System.out.println(iter.hasNext());
		
		ListIterator<String> listiter=list.listIterator();
		while(listiter.hasNext()) {
			System.out.println(listiter.next());
		}
		while(listiter.hasPrevious()) {
			System.out.println(listiter.previous());
		}
	}
}
  
  package hit.day28;
import java.util.Collections;
import java.util.Iterator;
import java.util.LinkedList;
import java.util.List;
import java.util.ListIterator;
public class ColDemo2 {
	public static void main(String[] args) {
		List<String> list=new LinkedList<String>();
		//hang him, not leave him
		//hang him not leave him
		
		list.add("hello");
		list.add("hai");
		list.add("world");
		
		System.out.println(list);
		
		System.out.println(list.get(0));
		System.out.println(list.size());
		System.out.println(list.contains("haiii"));
		System.out.println(list);
		Collections.sort(list);
		System.out.println(list);
		System.out.println(list.isEmpty());
		list.remove(0);
		System.out.println(list);
		list.set(1, "newvalue");//it will replace the existing one at that place
		System.out.println(list);
		Object s[]=list.toArray();
		
		for(int i=0;i<list.size();i++) {
			System.out.println(list.get(i));
		}
		
		for(String ss:list) {
			System.out.println(ss);
		}
		Iterator<String> iter=list.iterator();
		while(iter.hasNext()) {
			System.out.println(iter.next());
		}
		System.out.println(iter.hasNext());
		
		ListIterator<String> listiter=list.listIterator();
		while(listiter.hasNext()) {
			System.out.println(listiter.next());
		}
		while(listiter.hasPrevious()) {
			System.out.println(listiter.previous());
		}
		
	}
}
  
  package hit.day28;
import java.util.Collections;
import java.util.Enumeration;
import java.util.Iterator;
import java.util.List;
import java.util.ListIterator;
import java.util.Vector;
public class ColDemo3 {
	public static void main(String[] args) {
		Vector<String> list=new Vector<>(10,5);
		
		list.add("hello");
		list.add("hai");
		list.add("world");
		
		System.out.println(list);
		//list.ensureCapacity();
		System.out.println(list.get(0));
		System.out.println(list.size());
		System.out.println(list.contains("haiii"));
		System.out.println(list);
		Collections.sort(list);
		System.out.println(list);
		System.out.println(list.isEmpty());
		list.remove(0);
		System.out.println(list);
		list.set(1, "newvalue");//it will replace the existing one at that place
		System.out.println(list);
		Object s[]=list.toArray();
		
		for(int i=0;i<list.size();i++) {
			System.out.println(list.get(i));
		}
		
		for(String ss:list) {
			System.out.println(ss);
		}
		Iterator<String> iter=list.iterator();
		while(iter.hasNext()) {
			System.out.println(iter.next());
		}
		System.out.println(iter.hasNext());
		
		ListIterator<String> listiter=list.listIterator();
		//list.add("new value....");
		while(listiter.hasNext()) {
			System.out.println(listiter.next());
		}
		while(listiter.hasPrevious()) {
			System.out.println(listiter.previous());
		}
	
		Enumeration<String> en=list.elements();
		list.add("new value.....2222..................");
		while(en.hasMoreElements()) {
			System.out.println(en.nextElement());
		}
		
	}
}
  
  package hit.day28;
import java.util.HashSet;
import java.util.Iterator;
import java.util.Set;
import java.util.TreeSet;
//homework - stack and queue
public class ColDemo4 {
	public static void main(String[] args) {
		//Set<String> set=new HashSet<String>();
		Set<String> set=new TreeSet<String>();
		set.add("hello");
		set.add("hai");
		set.add("hello");
		set.add("world");
		set.add("earth");
		
		System.out.println(set);
		set.add("zebra");
		set.add("almighty");
		
		System.out.println(set);
		
		Iterator iter=set.iterator();
		while(iter.hasNext()) {
			System.out.println(iter.next());
		}
		
		for(String s:set) {
			System.out.println(s);
		}
		
	
		
	}
}
