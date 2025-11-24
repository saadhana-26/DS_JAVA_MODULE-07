# Ex6 Right Rotation LinkedList
## DATE:23-11-2025
## AIM:
To write a Java  program to:  
* Create a singly linked list.  
* Rotate the linked list to the right by k positions.  
* Display the rotated linked list.  
## Algorithm
1.Start the program.  
2.Create a linked list node class containing data and next.  
3.Insert elements into the linked list.  
4.Count the number of nodes and make the list circular by connecting the last node to the head.  
5.Find the new head by moving length - k steps forward and set the new tail's next to null.  
6.Display the rotated linked list.  
7.Stop the program.    

## Program:
java
/*
Program to  Right Rotation LinkedList
Developed by: SAADHANA L
RegisterNumber: 212224060224  
*/
~~~
import java.util.Scanner;
public class RotateLinkedList {
    public static Node rotate(Node head, int k) {
        if (head == null || head.next == null || k == 0) {
            return head;
        }
        Node current = head;
        int length = 1;
        while (current.next != null) {
            current = current.next;
            length++;
        }
        current.next = head;
        k = k % length;
        int stepsToNewHead = length - k;
        Node newTail = current;
        while (stepsToNewHead-- > 0) {
            newTail = newTail.next;
        }
        Node newHead = newTail.next;
        newTail.next = null;
        return newHead;
    }
    public static void display(Node head) {
        Node current = head;
        System.out.print("LinkedList: ");
        while (current != null) {
            System.out.print(current.data + " ");
            current = current.next;
        }
        System.out.println();
    }
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Node head = null, tail = null;
        int n = scanner.nextInt();
        for (int i = 0; i < n; i++) {
            Node newNode = new Node(scanner.nextInt());
            if (head == null) {
                head = tail = newNode;
            } else {
                tail.next = newNode;
                tail = newNode;
            }
        }
        int k = scanner.nextInt();
        head = rotate(head, k);
        display(head);
        scanner.close();
    }
}
class Node {
    int data;
    Node next;
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

~~~
## Output:
<img width="892" height="163" alt="image" src="https://github.com/user-attachments/assets/80640050-b78c-4777-bc1d-1a1638cc3d22" />


## Result:
Thus, the java program to perfom right rotation on linked list is implemented successfully.
