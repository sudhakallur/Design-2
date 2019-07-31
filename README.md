# Design-2

## Problem 1: (https://leetcode.com/problems/implement-queue-using-stacks/)
Implement the following operations of a queue using stacks.

push(x) -- Push element x to the back of queue.

pop() -- Removes the element from in front of queue.

peek() -- Get the front element.

empty() -- Return whether the queue is empty. 


class MyQueue {

    /** Initialize your data structure here. */
    Stack<Integer> st = new Stack<Integer>();
    Stack<Integer> st1 = new Stack<Integer>();
    public MyQueue() {
        
    }
    
    /** Push element x to the back of queue. */
    public void push(int x) {
        if(!st1.empty())
        {
            while(!st1.empty())
            {
                st.push(st1.pop());
            }
            st.push(x);
        }
        else
        {
            st.push(x);
        }
    }
    
    /** Removes the element from in front of queue and returns that element. */
    public int pop() {
        if(!st1.empty())
        {
           return st1.pop();
        }
        else
        {
            while(!st.empty())
            {
                st1.push(st.pop());
            }
            return st1.pop();
        }
    }
    
    /** Get the front element. */
    public int peek() {
        if(!st.empty())
        {
            while(!st.empty()){
                st1.push(st.pop());
            }
            return st1.peek();
        }
    return 0;
    
    }
    
    /** Returns whether the queue is empty. */
    public boolean empty() {
        if(!st1.empty() || !st.empty())
        {
           return false; 
        }
        else
        {
            return true;
        }
    }
}

/**
 * Your MyQueue object will be instantiated and called as such:
 * MyQueue obj = new MyQueue();
 * obj.push(x);
 * int param_2 = obj.pop();
 * int param_3 = obj.peek();
 * boolean param_4 = obj.empty();
 */
 
 
 

## Problem 2:(https://leetcode.com/problems/design-hashset/)
Design a HashSet without using any built-in hash table libraries.
To be specific, your design should include these functions:

add(value): Insert a value into the HashSet. 

contains(value) : Return whether the value exists in the HashSet or not.

remove(value): Remove a value in the HashSet. If the value does not exist in the HashSet, do nothing.



