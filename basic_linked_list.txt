#include <iostream>

using namespace std;

struct node {int x; node *nextptr;};

int main()
{
    node *root;
    node *tail;
    node *pointer;
    node *traverseptr;
    node *currentptr;
    int temp;
    int a,y;
    int listcount;
    char store;

    temp = -1;

    while(temp!=0)
    {

        cout<<"Enter 1 to add value to the list"<<endl;
        cout<<"Enter 2 to traverse the full list"<<endl;
        cout<<"Enter 3 to Traverse one element at a time"<<endl;
        cout<<"Enter 0 to exit"<<endl;
        cin>>temp;

        switch(temp)
        {
            case 1:


                cout<<"Enter the value to be added to the list or enter -1 to stop adding values to the list"<<endl;
                cin>>a;

                pointer = new node;
                pointer->nextptr = 0;
                pointer->x = a;

                if(listcount==0)
                {
                    root = pointer;
                    tail = pointer;
                    pointer->nextptr = root;
                }
                else
                {
                    tail->nextptr = pointer;
                    tail = pointer;
                    pointer->nextptr = root;
                }

                listcount++;

            break;

            case 2:

            traverseptr = root;
            for(y=1;y<=listcount;y++)
            {
                cout<<traverseptr->x;
                traverseptr = traverseptr->nextptr;
            }

            break;
            case 3:

            currentptr = root;
            store = 'n';

            while(store =='n')
            {
                cout<<currentptr->x;
                currentptr = currentptr->nextptr;
                cout<<"Enter n to display the next element or e to go back to the main window"<<endl;
                cin>>store;
            }
            break;
        }
    }


return 0;
}

