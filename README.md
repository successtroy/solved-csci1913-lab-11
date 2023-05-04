Download Link: https://assignmentchef.com/product/solved-csci1913-lab-11
<br>
A deque (pronounced like deck) is a double-ended queue. Deques are like ordinary queues, except that objects can be inserted and deleted at both the front and the rear. Unlike the linked queues described in the lectures, they work without special cases. In this laboratory assignment, you will write a Java class called Deque that implements a linked deque.

<ol>

 <li><strong> Theory.</strong></li>

</ol>

A deque can be implemented easily using a circular, doubly-linked list with a head node. For example, a deque containing the objects <em>A</em>, <em>B</em>, <em>C</em>, <em>D</em>, and <em>E </em>might use a list that looks like the following diagram. (To save space, the diagram does not show arrows pointing to those objects.)

head

The variable head points to the head node. The expression head.right points to the node at the front of the deque, which in turn points to the object <em>A</em>. The expression head.left points to the node at the rear of the deque, which in turn points to the object <em>E</em>.

<ol start="2">

 <li><strong> Implementation.</strong></li>

</ol>

You must write a class called Deque that implements a deque, using a doubly-linked circular list with a head node. Instances of Deque must be able to hold objects whose type is given by a class parameter Base. As a result, your class Deque must look like this, with your code in place of the three dots.

<h1>class Deque&lt;Base&gt;</h1>

{

…

}

To simplify grading, your code must use the same names for things that are used here. Your class Deque must have a private nested class called Node. The class Node implements the nodes of the doubly-linked list. It must have a private pointer slot called object that points to the object at the Node. It must have private pointer slots called left and right that point to the Node’s at the left and right of the Node, respectively. It must have a constructor that initializes the object, left, and right slots of the Node.

Your class Deque must also have a private variable head that points to the head node of the circular doubly-linked list. Also, your class must have the following methods.

<h1>• public Deque()</h1>

Constructor. Make a new, empty Deque. The variable head must be set so it points to a new head Node here.

<h1>• public void enqueueFront(Base object)</h1>

Add a new Node at the front of the Deque. The object slot of the new Node must point to the parameter object.

<h1>• public void enqueueRear(Base object)</h1>

Add a new Node at the rear of the Deque. The object slot of the new Node must point to the parameter object.

<h1>• public Base dequeueFront()</h1>

If the Deque is empty, then throw an IllegalStateException. Otherwise, get the Base object from the Node at the front of the Deque. Delete the Node at the front of the Deque, and return the Base object.

<h1>• public Base dequeueRear()</h1>

If the Deque is empty, then throw an IllegalStateException. Otherwise, get the Base object from the the Node at the rear of the Deque. Delete the Node at the rear of the Deque, and return the Base object.

<h1>• public boolean isEmpty()</h1>

Return true if the Deque is empty. Return false otherwise.

Important! Your enqueueFront and enqueueRear methods must work without special cases. That is, they must do the same thing when adding a Node to an empty Deque and to a non-empty Deque. You will receive no points for this lab if enqueueFront and enqueueRear use special cases.

The file tests11.java on Canvas contains Java code that performs a series of tests. The tests call methods from the Deque class; some of them print what those methods return. Each test is also followed by a comment that tells how many points it is worth, and optionally what must be printed if it works correctly.