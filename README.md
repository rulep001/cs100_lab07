# CS 100 - Lab 7: Iterator Pattern

## Guidelines
The iterator pattern allows for traversal of various types of containers without the client knowing the underlying
structure of the container. Therefore, the iterator’s job is to simplify traversal and to remove the technical
nuances of accessing a container allowing the developer to code at a higher level of abstraction. To make our
iterator as reusable as possible we have to implement a core interface that all of our iterators will inherit.    
In this lab, we will create a pre-order traversal iterator as well as the different collection iterators necessary
to fully iterate our composite system. Our Iterator class will be used for both collection iterators and traversal
iterators, so we want to keep it fairly basic.

## Base
```
class Iterator {
    protected:
        Base* self_ptr;
        Base* current_ptr;
    public :
        Iterator (Base* ptr) { this->self_ptr = ptr };
        /*Sets up the iterator to start at the beginning of traversal*/ 
        virtual void first() = 0;
        /*Move onto the next element*/ 
        virtual void next() = 0;
        /*Returns if you have finished iterating through all elements*/
        virtual bool is_done() = 0;
        /*Return the element the iterator is currently at*/
        virtual Base* current() = 0;
```