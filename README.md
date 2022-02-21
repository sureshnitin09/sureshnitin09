1 - while loop
2 - odd or even
3 - prime or not
4 - factors of x
5 - multiplication table
6 - pattern 1
7 pattern -2
8 pattern -3
9 print natural numbers
10 factorial of given number
11 fibonacci
12 Max-Min of an array
13 Matrix Addition
14 Lower Triangle of Matrix
15 Form a Sentence
16 Pattern Matching
17 sll - insert at begin
18 sll - insert at end
19 sll - insert at pos
20 sll - delete at begin
21 sll - delete at end
22 dll - insert at end
23 dll operations
24 dll - delete at pos
25 cll operations









































1 - while loop
#include <stdio.h>

int main(){
	int var, sum = 0, input_count = 0;
	while (input_count!=5)
	{
		scanf("%d", &var);
		sum += var;
		input_count ++;
	}
	printf("%d", sum);
	return 0;
}

//2 - odd or even
#include <stdio.h>

int main(){
	int var, i= 0;
    while(i!=5){
        scanf("%d",&var);
        if(var%2==0)
            printf("even\n");
        else
            printf("odd\n");
        i++;
    }
	return 0;
}

//3 - prime or not
#include <stdio.h>

int main(){
    int number, is_prime=1;
    scanf("%d", &number);
    for(int i=2;i*i<number;i++)
        if(number%i==0){
            is_prime=0;
            break;
        }
    if (is_prime == 1 && number>1) 
        printf("yes");
    else
        printf("no");
    return 0;
}

//4 - factors of x
#include <stdio.h>

int main() {   
    int i,n,t;
    scanf("%d",&t);
    for(i=0;i<t;i++){
        scanf("%d",&n);
        for(int j=1;j<=n;j++)
            if(n%j==0)
                printf("%d ",j);
        printf("\n");
    }
    return 0;
}

//5 - multiplication table
#include <stdio.h>

int main(){
	int i, N;
	scanf("%d", &N);
	for(i=1;i<=10;i++)
        printf("%d ",i*N);
	return 0;
}

//6 - pattern 1
#include <stdio.h>

int main(){
    int n,i,j;
    scanf("%d",&n);
    for(i=1;i<=n;i++){
        for(j=1;j<=i;j++)
            printf("%d",j);
        printf("\n");
    }
    return 0;
}

//7 pattern -2
#include <stdio.h>

int main(){
    int x,i,j,n;
    scanf("%d",&n);
    for(i=1;i<=n;i++){
        if(i%2!=0)
            x=1;
        else
            x=0;
        for(j=1;j<=i;j++){
            printf("%d",x);
            if(x==1)
                x=0;
            else
                x=1;
        }
        printf("\n");
    }
    return 0;
}

//8 pattern -3
#include <stdio.h>

int main(){   
    int i,j,n;
    scanf("%d",&n);
    for(i=1;i<=n;i++){
        for(j=1;j<=n-i;j++)
            printf(" ");
        for(j=1;j<=i;j++)
            printf("%d",j);
        printf("\n");
    }
    return 0;
}

//9 print natural numbers
#include <stdio.h>

int main(){  
    int n;
    scanf("%d",&n);
    for(int i=1;i<=n;i++)
        printf("%d ",i);
    return 0;
}

//10 factorial of given number
#include <stdio.h>

int main(){
    int n,p=1;
    scanf("%d",&n);
    for(int i=1;i<=n;i++)
        p*=i;
    printf("%d",p);
    return 0;
}
//11 fibonacci
#include <stdio.h>

int fib(int n){
    if(n<=1)
        return n;
    return fib(n-1)+fib(n-2);
}

int main(){
    int n;
    scanf("%d",&n);
    printf("%d",fib(n));
    return 0;
}

//12 Max-Min of an array
#include <stdio.h>

int main(){
    int n;
    scanf("%d",&n);
    int a[n],max=-101,min=101;
    for(int i=0;i<n;i++){
        scanf("%d",&a[i]);
        if(a[i]>max)
            max=a[i];
        if(a[i]<min)
            min=a[i];
    }
    printf("%d\n%d",max,min);
    return 0;
}

//13 Matrix Addition
#include <stdio.h>

int main(){
    int r1,c1;
    scanf("%d%d",&r1,&c1);
    int a[r1+c1];
    for(int i=0;i<r1+c1;i++)
        scanf("%d",&a[i]);
    int r2,c2;
    scanf("%d%d",&r2,&c2);
    int b[r2+c2];
    for(int i=0;i<r2+c2;i++)
        scanf("%d",&b[i]);
    if(r1==r2&&c1==c2){
        int s[r1+c1];
        for(int i=0;i<r1+c1;i++)
            s[i]=a[i]+b[i];
        for(int i=0;i<r1+c1;i++){
            printf("%d ",s[i]);
            if((i+1)%r1==0)
                printf("\n");
        }
    }
    else
        printf("%d",-1);
    return 0;
}

//14 Lower Triangle of Matrix
#include <stdio.h>

int main(){
    int n;
    scanf("%d",&n);
    int m[n][n];
    for(int i=0;i<n;i++)
        for(int j=0;j<n;j++)
            scanf("%d",&m[i][j]);
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
            if(i>=j)
                printf("%d ",m[i][j]);
            else
                printf("%d ",0);
        }
        printf("\n");
    }
    return 0;
}

//15 Form a Sentence
#include <stdio.h>

int main(){
    int n;
    scanf("%d",&n);
    char s[n][100000];
    for(int i=0;i<n;i++)
        scanf(" %[^\n]%*c",s[i]);
    for(int i=0;i<n;i++){
        if(i!=n-1)
            printf("%s ",s[i]);
        else
            printf("%s.",s[i]);
    }
    return 0;
}

//16 Pattern Matching
#include <stdio.h>

int main(){
    char s[101],c[101];
    scanf(" %[^\n]%*c",s);
    scanf(" %[^\n]%*c",c);
    int idx=-1,i,j;
    for(i=0;s[i]!='\0';i++){
        if(s[i]==c[0]){
            for(j=i;c[j]!='\0';j++)
                if(s[j]!=c[j])
                    break;
            if(c[j]=='\0'){
                idx=i;
                break;
            }
        }
    }
    printf("%d",idx);
    return 0;
}

//17 sll - insert at begin
#include <stdio.h>
#include <stdlib.h>

struct Node{
    int data;
    struct Node* next;
}*head=NULL;
void insertBegin(int n){
    struct Node *newNode=(struct Node*)malloc(sizeof(struct Node));
    newNode->data=n;
    newNode->next=head;
    head=newNode;
}
void display(void){
    while(head){
        printf("%d ",head->data);
        head=head->next;
    }
}
int main(){
    int n;
    scanf("%d",&n);
    for(int i=0;i<n;i++){
        int t;
        scanf("%d",&t);
        insertBegin(t);
    }
    display();
    return 0;
}

//18 sll - insert at end

#include <stdio.h>
#include <stdlib.h>

struct Node{
    int data;
    struct Node* next;
}*head=NULL;
void insertEnd(int n){
    struct Node *newNode=(struct Node*)malloc(sizeof(struct Node));
    newNode->data=n;
    if(!head){
        head=newNode;
        return;
    }
    struct Node *temp=head;
    while(temp->next)
        temp=temp->next;
    temp->next=newNode;
}
void display(void){
    if(!head) return;
    while(head->next){
        printf("%d->",head->data);
        head=head->next;
    }
    printf("%d",head->data);
}
int main(){
    int n;
    scanf("%d",&n);
    for(int i=0;i<n;i++){
        int t;
        scanf("%d",&t);
        insertEnd(t);
    }
    display();
    return 0;
}

//19 sll - insert at pos
#include <stdio.h>
#include <stdlib.h>

struct Node{
    int data;
    struct Node* next;
}*head=NULL;

void insertPos(int pos,int n){
    struct Node *newNode=(struct Node*)malloc(sizeof(struct Node));
    newNode->data=n;
    if(pos==1){
        newNode->next=head;
        head=newNode;
        return;
    }
    struct Node *curr=head,*prev=NULL;
    for(int i=0;i<pos-1;i++){
        prev=curr;
        curr=curr->next;
    }
    newNode->next=prev->next;
    prev->next=newNode;
    return;
}
void display(void){
    if(!head) return;
    while(head->next){
        printf("%d->",head->data);
        head=head->next;
    }
    printf("%d",head->data);
}

int main(){
    int n;
    scanf("%d",&n);
    for(int i=0;i<n;i++){
        int k,num;
        scanf("%d%d",&k,&num);
        insertPos(k,num);
    }
    display();
    return 0;
}

//20 sll - delete at begin
#include <stdio.h>
#include <stdlib.h>

struct Node{
    int data;
    struct Node* next;
}*head=NULL;
void insertBegin(int n){
    struct Node *newNode=(struct Node*)malloc(sizeof(struct Node));
    newNode->data=n;
    newNode->next=head;
    head=newNode;
}
void delete(void){
    if(head==NULL)
        return;
    head=head->next;
    return;
}
void display(void){
    if(!head) return;
    while(head->next){
        printf("%d->",head->data);
        head=head->next;
    }
    printf("%d",head->data);
}
int main(){
    int n;
    scanf("%d",&n);
    for(int i=0;i<n;i++){
        int t;
        scanf("%d",&t);
        insertBegin(t);
    }
    int x;
    scanf("%d",&x);
    while(x--) delete();
    display();
    return 0;
}

//21 sll - delete at end
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

struct Node{
    int data;
    struct Node* next;
}*head=NULL;
void insertEnd(int n){
    struct Node *newNode=(struct Node*)malloc(sizeof(struct Node));
    newNode->data=n;
    if(!head){
        head=newNode;
        return;
    }
    struct Node *temp=head;
    while(temp->next)
        temp=temp->next;
    temp->next=newNode;
}
void delete(){
    if(!head || !head->next){
        head=NULL;
        return;
    }
    struct Node *temp=head;
    while(temp->next->next)
        temp=temp->next;
    temp->next=NULL;
}
void display(void){
    if(!head) return;
    while(head->next){
        printf("%d->",head->data);
        head=head->next;
    }
    printf("%d",head->data);
}
int main(){
    int n;
    scanf("%d",&n);
    for(int i=0;i<n;i++){
        int t;
        scanf("%d",&t);
        insertEnd(t);
    }
    int x;
    scanf("%d",&x);
    while(x--) delete();
    display();
    return 0;
}

//22 dll - insert at end
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

struct node{
    struct node *prev;
    int data;
    struct node *next;
}*head=NULL;

void insertAtEnd(int n){
    struct node *temp=(struct node*)malloc(sizeof(struct node));
    temp->data=n;
    if(head==NULL){
        head=temp;
        return;
    }
    struct node *p=head;
    while(p->next)
        p=p->next;
    p->next=temp;
    temp->prev=p;
}

void display(void){
    if(head==NULL)
        return;
    struct node *p=head;
    while(p->next){
        printf("%d<==>",p->data);
        p=p->next;
    }
    printf("%d",p->data);
}

int main() {
    int n,t;
    scanf("%d",&n);
    for(int i=0;i<n;i++){
        scanf("%d",&t);
        insertAtEnd(t);
    }
    display();
    return 0;
}


//23 dll operations
#include <stdio.h>
#include <stdlib.h>

struct node{
    struct node *prev;
    int data;
    struct node *next;
}*head=NULL,*tail=NULL;

void insertAtBegin(int n){
    struct node *temp=(struct node*)malloc(sizeof(struct node));
    temp->data=n;
    if(!head){
        head=tail=temp;
        return;
    }
    temp->next=head;
    head->prev=temp;
    head=temp;
}
void insertAtEnd(int n){
    struct node *temp=(struct node*)malloc(sizeof(struct node));
    temp->data=n;
    if(!head){
        head=tail=temp;
        return;
    }
    tail->next=temp;
    temp->prev=tail;
    tail=temp;
}
void deleteAtBegin(void){
    if(!head){
        printf("Invalid\n");
        return;
    }
    else if(head==tail){
        head=tail=NULL;
        return;
    }
    head=head->next;
    if(head)
        head->prev=NULL;
}
void deleteAtEnd(void){
    if(!head){
        printf("Invalid\n");
        return;
    }
    else if(head==tail){
        head=tail=NULL;
        return;
    }
    tail=tail->prev;
    if(tail)
        tail->next=NULL;
}
int len(void){
    struct node *temp=head;
    int l=0;
    while(temp){
        temp=temp->next;
        l++;
    }
    return l;
}
void insertAtPos(int pos,int n){
    struct node *temp=(struct node*)malloc(sizeof(struct node));
    temp->data=n;
    int l=len();
    if(pos<1 || pos>l+1){
        printf("Invalid\n");
        return;
    }
    else if(pos==1){
        temp->next=head;
        if(head) head->prev=temp;
        head=temp;
        return;
    }
    struct node *p=head;
    for(int i=1;i<pos-1;i++)
        p=p->next;
    temp->next=p->next;
    temp->prev=p;
    if(p->next) p->next->prev=temp;
    p->next=temp;
}

void display(void){
    if(!head){
        printf("Empty\n");
        return;
    }
    struct node *p=head;
    while(p->next){
        printf("%d<==>",p->data);
        p=p->next;
    }
    printf("%d\n",p->data);
}

int main() {
    int n;
    scanf("%d",&n);
    while(n--){
        int a,b,c;
        scanf("%d",&a);
        if(a==1){
            scanf("%d",&b);
            insertAtBegin(b);
        }
        else if(a==2){
            scanf("%d",&b);
            insertAtEnd(b);
        }
        else if(a==3)
            deleteAtBegin();
        else if(a==4)
            deleteAtEnd();
        else if(a==5){
            scanf("%d",&b);
            scanf("%d",&c);
            insertAtPos(b,c);
        }
        else
            display();
    }
    return 0;
}


//24 dll - delete at pos
#include <stdio.h>
#include <stdlib.h>

struct node{
    struct node *prev;
    int data;
    struct node *next;
}*head=NULL,*tail=NULL;

void insertAtEnd(int n){
    struct node *temp=(struct node*)malloc(sizeof(struct node));
    temp->data=n;
    if(!head){
        head=tail=temp;
        return;
    }
    tail->next=temp;
    temp->prev=tail;
    tail=temp;
}

int len(void){
    int l=0;
    struct node *temp=head;
    while(temp){
        temp=temp->next;
        l++;
    }
    return l;
}

void deleteAtPos(int pos){
    int l=len();
    if(pos<1 || pos>l){
        printf("Invalid\n");
        return;
    }
    else if(head==tail){
        head=tail=NULL;
        return;
    }
    else if(pos==1){
        head=head->next;
        head->prev=NULL;
        return;
    }
    else if(pos==l){
        tail=tail->prev;
        tail->next=NULL;
        return;
    }
    struct node *p=head;
    for(int i=1;i<pos-1;i++)
        p=p->next;
    p->next=p->next->next;
    p->next->prev=p;
}

void display(void){
    if(head==NULL){
        printf("Empty\n");
        return;
    }
    struct node *p=head;
    while(p->next){
        printf("%d<=>",p->data);
        p=p->next;
    }
    printf("%d\n",p->data);
}

int main() {
    int n;
    scanf("%d",&n);
    while(n--){
        int a;
        scanf("%d",&a);
        insertAtEnd(a);
    }
    int d;
    scanf("%d",&d);
    while(d--){
        int b;
        scanf("%d",&b);
        deleteAtPos(b);
    }
    display();
    return 0;
}


//25 cll operations
#include <stdio.h>
#include <stdlib.h>

struct node{
    int data;
    struct node *next;
}*tail=NULL;

void insertAtBegin(int n){
    struct node *temp=(struct node*)malloc(sizeof(struct node));
    temp->data=n;
    if(!tail){
        tail=temp;
        tail->next=tail;
    }
    else{
        temp->next=tail->next;
        tail->next=temp;
    }
}

void insertAtEnd(int n){
    struct node *temp=(struct node*)malloc(sizeof(struct node));
    temp->data=n;
    temp->next=NULL;
    if(tail==NULL){
        tail=temp;
        tail->next=tail;
    }
    else{
        temp->next=tail->next;
        tail->next=temp;
        tail=temp;
    }
}

void deleteAtBegin(){
    if(!tail)
        printf("Invalid\n");
    else{
        struct node *temp=tail->next;
        if(tail==tail->next)
            tail=NULL;
        else
            tail->next=temp->next;
    }
}

void deleteAtEnd(){
    if(!tail)
        printf("Invalid\n");
    else{
        struct node *cur,*prev=NULL;
        cur=tail->next;
        if(tail->next==tail)
            tail=NULL;
        else{
            while(cur->next!=tail->next){
                prev=cur;
                cur=cur->next;
            }
            prev->next=tail->next;
            tail=prev;
        }
    }
}

void display(void){
    if(tail==NULL)
        printf("Empty\n");
    else{
        struct node *temp=tail->next;
        printf("->");
        while(tail!=temp){
            printf("%d->",temp->data);
            temp=temp->next;
        }
        printf("%d->\n",temp->data);
    }
}

int main() {
    int n;
    scanf("%d",&n);
    while(n--){
        int a,b;
        scanf("%d",&a);
        if(a==1){
            scanf("%d",&b);
            insertAtBegin(b);
        }
        else if(a==2){
            scanf("%d",&b);
            insertAtEnd(b);
        }
        else if(a==3)
            deleteAtBegin();
        else if(a==4)
            deleteAtEnd();
        else
            display();
    }
    
    return 0;
}


//26 add 2 polynomials
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

struct node{
    int c;
    int e;
    struct node *next;
}*h1=NULL,*t1=NULL,*h2=NULL,*t2=NULL;

void insertAtEnd1(int a,int b){
    struct node *temp=(struct node*)malloc(sizeof(struct node));
    temp->c=a;
    temp->e=b;
    temp->next=NULL;
    if(h1==NULL)
        h1=t1=temp;
    else{
        t1->next=temp;
        t1=temp;
    }
}

void insertAtEnd2(int a,int b){
    struct node *temp=(struct node*)malloc(sizeof(struct node));
    temp->c=a;
    temp->e=b;
    temp->next=NULL;
    if(h2==NULL)
        h2=t2=temp;
    else{
        t2->next=temp;
        t2=temp;
    }
}

void poly1(void){
    if(h1==NULL)
        return;
    struct node *temp=h1;
    while(temp->next){
        printf("%dx^%d+",temp->c,temp->e);
        temp=temp->next;
    }
    if(temp->e)
        printf("%dx^%d",temp->c,temp->e);
    else
        printf("%d",temp->c);
}

void poly2(void){
    if(h2==NULL)
        return;
    struct node *temp=h2;
    while(temp->next){
        printf("%dx^%d+",temp->c,temp->e);
        temp=temp->next;
    }
    if(temp->e)
        printf("%dx^%d",temp->c,temp->e);
    else
        printf("%d",temp->c);
}

void sumPoly(void){
    if(h1==NULL && h2==NULL)
        return;
    else if(h1==NULL)
        poly2();
    else if(h2==NULL)
        poly1();
    else{
        struct node *p1=h1,*p2=h2;
        while(p1&&p2){
            int c1,c2,e1,e2;
            c1=p1->c;
            c2=p2->c;
            e1=p1->e;
            e2=p2->e;
            if(p1->next==NULL && p2->next==NULL){
                if(e1==e2){
                    if(e1)
                        printf("%dx^%d",c1+c2,p1->e);
                    else
                        printf("%d",c1+c2);
                }
                else if(e1>e2){
                    printf("%dx^%d+",c1,e1);
                    if(e2)
                        printf("%dx^%d",c2,e2);
                    else
                        printf("%d",c2);
                }
                else{
                    printf("%dx^%d+",c2,e2);
                    if(e1)
                        printf("%dx^%d",c1,e1);
                    else
                        printf("%d",c1);
                }
                return;
            }
            if(e1==e2){
                printf("%dx^%d+",c1+c2,e1);
                p1=p1->next;
                p2=p2->next;
            }
            else if(e1>e2){
                printf("%dx^%d+",c1,e1);
                p1=p1->next;
            }
            else{
                printf("%dx^%d+",c2,e2);
                p2=p2->next;
            }
        }
        if(p1){
            while(p1->next){
                printf("%dx^%d+",p1->c,p1->e);
                p1=p1->next;
            }
            if(p1->e)
                printf("%dx^%d",p1->c,p1->e);
            else
                printf("%d",p1->c);
        }
        else if(p2){
            while(p2->next){
                printf("%dx^%d+",p2->c,p2->e);
                p2=p2->next;
            }
            if(p2->e)
                printf("%dx^%d",p2->c,p2->e);
            else
                printf("%d",p2->c);
        }
    }
    /*
    else{
        struct node *p1=h1,*p2=h2;
        while(p1||p2){
            int c1,c2,e1,e2;
            c1=(p1==NULL)?0:p1->c;
            c2=(p2==NULL)?0:p2->c;
            e1=(p1==NULL)?0:p1->e;
            e2=(p2==NULL)?0:p2->e;
            if(p1->next==NULL && p2->next==NULL){
                if(e1==e2){
                    if(e1)
                        printf("%dx^%d",c1+c2,p1->e);
                    else
                        printf("%d",c1+c2);
                }
                else if(e1>e2){
                    printf("%dx^%d+",c1,e1);
                    if(e2)
                        printf("%dx^%d",c2,e2);
                    else
                        printf("%d",c2);
                }
                else{
                    printf("%dx^%d+",c2,e2);
                    if(e1)
                        printf("%dx^%d",c1,e1);
                    else
                        printf("%d",c1);
                }
                break;
            }
            if(e1==e2){
                printf("%dx^%d+",c1+c2,e1);
                p1=p1->next;
                p2=p2->next;
            }
            else if(e1>e2){
                printf("%dx^%d+",c1,e1);
                p1=p1->next;
            }
            else{
                printf("%dx^%d+",c2,e2);
                p2=p2->next;
            }
        }
    }*/
}

int main() {
    int n;
    scanf("%d",&n);
    while(n--){
        int a,b;
        scanf("%d%d",&a,&b);
        insertAtEnd1(a,b);
    }
    int m;
    scanf("%d",&m);
    while(m--){
        int a,b;
        scanf("%d%d",&a,&b);
        insertAtEnd2(a,b);
    }
    printf("\nFirst polynomial is:");
    poly1();
    printf("\n\nSecond polynomial is:");
    poly2();
    printf("\n\nThe sum Polynomial is:");
    sumPoly();
    return 0;
}


//27 stacks using arrays
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int stk[25];
int top=-1;

void push(void){
    int x;
    scanf("%d",&x);
    top++;
    stk[top]=x;
}

void pop(void){
    if(top==-1)
        printf("Invalid\n");
    else
        top--;
}

void peek(void){
    if(top==-1)
        printf("Invalid\n");
    else
        printf("%d\n",stk[top]);
}

void empty(void){
    if(top==-1)
        printf("1\n");
    else
        printf("0\n");
}

int main() {
    int n;
    scanf("%d",&n);
    while(n--){
        int ch;
        scanf("%d",&ch);
        switch(ch){
            case 1: push();
                    break;
            case 2: pop();
                    break;
            case 3: peek();
                    break;
            case 4: empty();
                    break;
            default:
                    printf("Invalid\n");
        }
    }
    
    return 0;
}


//28 stacks using linked list
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

struct node{
    int data;
    struct node *next;
}*head=NULL;

void push(void){
    int n;
    scanf("%d",&n);
    struct node *temp=(struct node*)malloc(sizeof(struct node));
    temp->data=n;
    temp->next=NULL;
    if(head==NULL)
        head=temp;
    else{
        temp->next=head;
        head=temp;
    }
}

void pop(void){
    if(head==NULL)
        printf("Invalid\n");
    else if(head->next==NULL)
        head=NULL;
    else{
        struct node *temp=head;
        head=head->next;
        free(temp);
    }
}

void peek(void){
    if(head==NULL)
        printf("Invalid\n");
    else
        printf("%d\n",head->data);
}

void empty(void){
    if(head==NULL)
        printf("1\n");
    else
        printf("0\n");
}

int main() {
    int n;
    scanf("%d",&n);
    while(n--){
        int ch;
        scanf("%d",&ch);
        switch(ch){
            case 1: push();
                    break;
            case 2: pop();
                    break;
            case 3: peek();
                    break;
            case 4: empty();
                    break;
        }
    }
       
    return 0;
}


//29 infix to postfix
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

char opr[20]; //operator stk
int top=-1;

int pre(char c){
    if(c=='(')
        return 0;
    else if(c=='+' || c=='-')
        return 1;
    else if(c=='^')
        return 3;
    else
        return 2;
}

void push(char c){
    top++;
    opr[top]=c;
}

char pop(void){
    top--;
    return opr[top+1];
}

int main() {
    char s[20];
    scanf(" %[^\n]*c",s);
    int l=strlen(s),k=0;
    char res[l+1];//add null char
    for(int i=0;i<l;i++){
        if(s[i]>='a' && s[i]<='z'){
            res[k]=s[i];
            k++;
        }
        else{
            if(top==-1)
                push(s[i]);
            else if(s[i]=='(')
                push(s[i]);
            else if(s[i]==')'){
                while(top!=-1 && opr[top]!='('){
                    res[k]=pop();
                    k++;
                }
                pop();
            }
            else{
                while(top!=-1 && pre(s[i])<=pre(opr[top])){
                    res[k]=pop();
                    k++;
                }
                push(s[i]);
            }
        }
    }
    while(top!=-1){
        res[k]=pop();
        k++;
    }
    res[k]='\0';
    printf("%s",res);
    return 0;
}


//30 stack operations
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int stk[25];
int top=-1;

void push(void){
    int x;
    scanf("%d",&x);
    top++;
    stk[top]=x;
}

void pop(void){
    if(top==-1)
        printf("Invalid\n");
    else
        top--;
}

void peek(void){
    if(top==-1)
        printf("Invalid\n");
    else
        printf("%d\n",stk[top]);
}

void empty(void){
    if(top==-1)
        printf("1\n");
    else
        printf("0\n");
}

void min(void){
    if(top==-1)
        printf("Invalid\n");
    else{
        int m=stk[0];
        for(int i=0;i<top;i++){
            if(stk[top]<m)
                m=stk[top];
        }
        printf("%d\n",m);
    }
}

void max(void){
    if(top==-1)
        printf("Invalid\n");
    else{
        int m=stk[0];
        for(int i=0;i<top;i++){
            if(stk[top]>m)
                m=stk[top];
        }
        printf("%d\n",m);
    }
}

int main() {
    int n;
    scanf("%d",&n);
    while(n--){
        int ch;
        scanf("%d",&ch);
        switch(ch){
            case 1: push();
                    break;
            case 2: pop();
                    break;
            case 3: peek();
                    break;
            case 4: empty();
                    break;
            case 5: min();
                    break;
            case 6: max();
                    break;
            default:
                    printf("Invalid\n");
        }
    }
    
    return 0;
}
//31 queues using arrays
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int queue[25];
int f=-1,r=-1;

void enqueue(void){
    int n;
    scanf("%d",&n);
    if(f==-1 && r==-1){
        f++;
        r++;
    }
    else
        r++;
    queue[r]=n;
}

void dequeue(void){
    if(f==-1 && r==-1)
        printf("invalid\n");
    else{
        f++;
        if(f>r)
            f=r=-1;
    }
}

void front(void){
    if(f==-1 && r==-1)
        printf("invalid\n");
    else
        printf("%d\n",queue[f]);
}

void rear(void){
    if(f==-1 && r==-1)
        printf("invalid\n");
    else
        printf("%d\n",queue[r]);
}

void isEmpty(void){
    if(f==-1 && r==-1)
        printf("1\n");
    else
        printf("0\n");
}

int main() {
    int t=0;
    scanf("%d",&t);
    while(t--){
        int ch;
        scanf("%d",&ch);
        switch(ch){
            case 1: enqueue();
                    break;
            case 2: dequeue();
                    break;
            case 3: front();
                    break;
            case 4: rear();
                    break;
            case 5: isEmpty();
                    break;
            default:
                    printf("invalid\n");
                    break;
        }
    }
    return 0;
}


//32 queues using linked list
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

struct node{
    int data;
    struct node *next;
}*head=NULL,*tail=NULL;

void enqueue(void){
    int n;
    scanf("%d",&n);
    struct node *temp=(struct node*)malloc(sizeof(struct node));
    temp->data=n;
    temp->next=NULL;
    if(head==NULL)
        head=tail=temp;
    else{
        tail->next=temp;
        tail=temp;
    }
}

void dequeue(void){
    if(head==NULL)
        printf("invalid\n");
    else if(head==tail)
        head=tail=NULL;
    else{
        struct node *temp=head;
        head=head->next;
        free(temp);
    }
}

void front(void){
    if(head==NULL)
        printf("invalid\n");
    else
        printf("%d\n",head->data);
}

void rear(void){
    if(head==NULL)
        printf("invalid\n");
    else
        printf("%d\n",tail->data);
}

void isEmpty(void){
    if(head==NULL)
        printf("1\n");
    else
        printf("0\n");
}

int main() {
    int t=0;
    scanf("%d",&t);
    while(t--){
        int ch;
        scanf("%d",&ch);
        switch(ch){
            case 1: enqueue();
                    break;
            case 2: dequeue();
                    break;
            case 3: front();
                    break;
            case 4: rear();
                    break;
            case 5: isEmpty();
                    break;
            default:
                    printf("invalid\n");
                    break;
        }
    }
    return 0;
}


//33 postfix evaluation
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int stk[10005];
int top=-1;

void push(int n){
    top++;
    stk[top]=n;
}

int pop(void){
    top--;
    return stk[top+1];
}

int main() {
    char s[1000];
    scanf(" %[^\n]*c",s);
    int l=strlen(s);
    for(int i=0;i<l;i++){
        if(s[i]>='0' && s[i]<='9')
            push(s[i]-'0');
        else if(s[i]=='(' || s[i]==')'){
            //do nothing
        }
        else{
            int a=pop(),b=pop();
            if(s[i]=='+')
                push(a+b);
            else if(s[i]=='-')
                push(a-b);
            else if(s[i]=='*')
                push(a*b);
            else
                push(a/b);
        }
    }
    printf("%d",pop());
    return 0;
}


//34 bracket sequence
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

char stk[1000];
int top=-1;

void push(char c){
    top++;
    stk[top]=c;
}

char pop(void){
    if(top==-1)
        return '!';
    top--;
    return stk[top+1];
}

int isValid(char c,char s){
    if(c=='(' && s==')')
        return 1;
    else if(c=='[' && s==']')
        return 1;
    else if(c=='{' && s=='}')
        return 1;
    else
        return 0;
}

int main() {
    int t;
    scanf("%d",&t);
    while(t--){
        char s[1000];
        scanf("%s",s);
        int l=strlen(s);
        int flag=1;
        if(l%2!=0||s[0]==')'||s[0]==']'||s[0]=='}'||s[l-1]=='{'||s[l-1]=='['||s[l-1]=='(')
            flag=0;
        else{
            for(int i=0;i<l;i++){
                if(s[i]=='['||s[i]=='('||s[i]=='{')
                    push(s[i]);
                else{
                    char c=pop();
                    if(c=='!'){
                        flag=0;
                        break;
                    }
                    else{
                        if(isValid(c,s[i])==0){
                            flag=0;
                            break;
                        }
                    }
                }
            }
            if(flag==1 && top!=-1)
                flag=0;
        }
        if(flag==1)
            printf("Valid\n");
        else
            printf("Invalid\n");
        top=-1;
    }
    return 0;
}


//35 circular queue using arrays
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int main() {
    int n;
    scanf("%d",&n);
    int q;
    scanf("%d",&q);
    int queue[n];
    int f=-1,r=-1;
    while(q--){
        int ch,d;
        scanf("%d",&ch);
        switch(ch){
            case 1:
                scanf("%d",&d);
                if(f==-1 && r==-1){
                    f=r=0;
                    queue[f]=d;
                    //printf("%d %d\n",queue[r],queue[r]);
                }
                else if(f+r==n-1 || r+1==f)
                    printf("Queue is Full\n");
                else if(r==n-1){
                    r=0;
                    queue[r]=d;
                }
                else{
                    r++;
                    queue[r]=d;
                    //printf("%d\n",queue[r]);
                }
                break;
            case 2:
                if(f==-1 && r==-1)
                    printf("Queue is Empty\n");
                else if(f==0 && r==0)
                    f=r=-1;
                else if(f==n-1)
                    f=0;
                else
                    f++;
                break;
            case 3:
                if(f==-1 && r==-1)
                    printf("Queue is Empty\n");
                else
                    printf("%d\n",queue[f]);
                break;
            case 4:
                if(f==-1 && r==-1)
                    printf("Queue is Empty\n");
                else
                    printf("%d\n",queue[r]);
                break;
            case 5:
                if(f==-1 && r==-1)
                    printf("1\n");
                else
                    printf("0\n");
                break;
            default:
                printf("Invalid\n");
                break;
        }
    }
    return 0;
}


//36 palindrome
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

char stk[50];
int top=-1;

void push(char c){
    top++;
    stk[top]=c;
}

char pop(void){
    if(top==-1)
        return '!';
    top--;
    return stk[top+1];
}

int main() {
    int t;
    scanf("%d",&t);
    while(t--){
        char s[100];
        scanf("%s",s);
        int l=strlen(s),flag=1,i;
        for(i=0;i<l/2;i++)
            push(s[i]);
        if(l%2==0)
            i=l/2;
        else
            i=l/2+1;
        for(;i<l;i++){
            char c=pop();
            if(c=='!' || c!=s[i]){
                flag=0;
                break;
            }
        }
        if(flag)
            printf("YES\n");
        else
            printf("NO\n");
    }
    return 0;
}


//37 arrange array-1
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int main() {
    int n;
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++)
        scanf("%d",&arr[i]);
    int k;
    scanf("%d",&k);
    for(int i=0,t=0;i<n && t<k;i++,t++){
        int min=i;
        for(int j=i+1;j<n;j++){
            if(arr[min]>arr[j])
                min=j;
        }
        int temp=arr[i];
        arr[i]=arr[min];
        arr[min]=temp;
    }
    for(int i=0;i<n;i++)
        printf("%d ",arr[i]);
    return 0;
}


//38 selection sort
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int main() {
    int n;
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++)
        scanf("%d",&arr[i]);
    for(int i=0;i<n;i++){
        for(int j=i+1;j<n;j++)
            if(arr[i]>arr[j]){
                int temp=arr[i];
                arr[i]=arr[j];
                arr[j]=temp;
            }
    }
    for(int i=0;i<n;i++)
        printf("%d ",arr[i]);
    return 0;
}


//39 arrange array-2
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int main() {
    int n;
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++)
        scanf("%d",&arr[i]);
    int temp=arr[n-1],idx=0;
    for(int i=0;i<n-1;i++)
        if(arr[i]>temp){
            idx=i;
            break;
        }
    for(int i=n-1;i>idx;i--){
        arr[i]=arr[i-1];
    }
    arr[idx]=temp;
    for(int i=0;i<n;i++)
        printf("%d ",arr[i]);
    return 0;
}

//40 insertion sort
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int main() {
    int n;
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++)
        scanf("%d",&arr[i]);
    for(int i=1;i<n;i++){
        int k=arr[i],j=i-1;
        while(j>=0 && arr[j]>k){
            arr[j+1]=arr[j];
            j--;
        }
        arr[j+1]=k;
    }
    for(int i=0;i<n;i++)
        printf("%d ",arr[i]);
    return 0;
}
//41 merge arrays
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int main() {
    int n;
    scanf("%d",&n);
    int a1[n];
    for(int i=0;i<n;i++)
        scanf("%d",&a1[i]);
    int m;
    scanf("%d",&m);
    int a2[m];
    for(int i=0;i<m;i++)
        scanf("%d",&a2[i]);
    int arr[m+n];
    int i,j,k;
    for(i=0,j=0,k=0;i<n&&j<m;){
        if(a1[i]<a2[j]){
            arr[k]=a1[i];
            k++;
            i++;
        }
        else{
            arr[k]=a2[j];
            k++;
            j++;
        }
    }
    if(i==n)
        while(j!=m){
            arr[k]=a2[j];
            k++;
            j++;
        }
    else
        while(i!=n){
            arr[k]=a1[i];
            k++;
            i++;
        }
    for(i=0;i<m+n;i++)
        printf("%d ",arr[i]);
    return 0;
}


//42 merge sort
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

void merge(int arr[],int l,int m,int r){
    int n1=m-l+1,n2=r-m;
    int a1[n1],a2[n2];
    for(int i=0;i<n1;i++)
        a1[i]=arr[l+i];
    for(int i=0;i<n2;i++)
        a2[i]=arr[m+i+1];
    int i=0,j=0,k=l;
    while(i<n1 && j<n2){
        if(a1[i]<=a2[j]){
            arr[k]=a1[i];
            k++;
            i++;
        }
        else{
            arr[k]=a2[j];
            k++;
            j++;
        }
    }
    while(i<n1){
        arr[k]=a1[i];
        k++;
        i++;
    }
    while(j<n2){
        arr[k]=a2[j];
        k++;
        j++;
    }
}

void mergeSort(int arr[],int l,int r){
    if(r>l){
        int m=(l+r)/2;
        mergeSort(arr,l,m);
        mergeSort(arr,m+1,r);
        merge(arr,l,m,r);
    }
}

int main() {
    int n;
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++)
        scanf("%d",&arr[i]);
    mergeSort(arr,0,n-1);
    for(int i=0;i<n;i++)
        printf("%d ",arr[i]);
    return 0;
}


//43 quick sort
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int partition(int arr[],int l,int h){
    int p=arr[h];
    int i=l-1;
    for(int j=l;j<h;j++){
        if(arr[j]<p){
            i++;
            int temp=arr[i];
            arr[i]=arr[j];
            arr[j]=temp;
        }
    }
    int temp=arr[i+1];
    arr[i+1]=arr[h];
    arr[h]=temp;
    return i+1;
}

void quickSort(int arr[],int l,int h){
    if(l<h){
        int p=partition(arr,l,h);
        quickSort(arr,l,p-1);
        quickSort(arr,p+1,h);
    }
}

int main() {
    int t;
    scanf("%d",&t);
    while(t--){
        int n;
        scanf("%d",&n);
        int arr[n];
        for(int i=0;i<n;i++)
            scanf("%d",&arr[i]);
        quickSort(arr,0,n-1);
        for(int i=0;i<n;i++)
            printf("%d ",arr[i]);
        printf("\n");
    }
    return 0;
}


//44 heap sort
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

void heapify(int arr[],int n,int i){
    int b=i;
    int l=2*i+1;
    int r=2*i+2;
    if(l<n && arr[l]>arr[b])
        b=l;
    if(r<n && arr[r]>arr[b])
        b=r;
    if(b!=i){
        int temp=arr[i];
        arr[i]=arr[b];
        arr[b]=temp;
        heapify(arr,n,b);
    }
}

void heapSort(int arr[],int n){
    for(int i=n/2-1;i>=0;i--)
        heapify(arr,n,i);
    for(int i=n-1;i>0;i--){
        int temp=arr[0];
        arr[0]=arr[i];
        arr[i]=temp;
        heapify(arr,i,0);
    }
}

int main() {
    int n;
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++)
        scanf("%d",&arr[i]);
    heapSort(arr,n);
    for(int i=0;i<n;i++)
        printf("%d ",arr[i]);
    return 0;
}


//45 binary tree traversal using arrays
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int arr[10005]={0};

void preorder(int n,int i){
    if(arr[i]){
        printf("%d ",arr[i]);
        preorder(n,2*i+1);
        preorder(n,2*i+2);
    }
    return;
}

void inorder(int n,int i){
    if(i>=n)
        return;
    if(arr[i]){
        inorder(n,2*i+1);
        printf("%d ",arr[i]);
        inorder(n,2*i+2);
    }
}

void postorder(int n,int i){
    if(i>=n)
        return;
    if(arr[i]){
        postorder(n,2*i+1);
        postorder(n,2*i+2);
        printf("%d ",arr[i]);
    }
}

int main() {
    int n;
    scanf("%d",&n);
    scanf("%d",&arr[0]);
    for(int i=1;i<n;i++){
        char ch; int p,c,j=0;
        scanf("%d %c %d",&p,&ch,&c);
        for(j=0;j<pow(2,n);j++){
            if(arr[j]==p)
                break;
        }
        if(ch=='L')
            arr[2*j+1]=c;
        else
            arr[2*j+2]=c;
    }
    int x=2*n;
    printf("Preorder:");
    preorder(x,0);
    printf("\nInorder:");
    inorder(x,0);
    printf("\nPostorder:");
    postorder(x,0);
    return 0;
}


//46 binary tree traversal using linked list
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

struct node{
    struct node *left;
    int data;
    struct node* right;
};

struct node* create(void){
    int n;
    scanf("%d",&n);
    struct node* temp=(struct node*)malloc(sizeof(struct node));
    temp->data=n;
    temp->left=NULL;
    temp->right=NULL;
    return temp;
}

struct node* find(struct node* root,int p){
    if(!root)
        return NULL;
    if(root->data==p)
        return root;
    struct node* temp=find(root->left, p);
    if(temp)
        return temp;
    temp=find(root->right,p);
    return temp;
}

void insert(struct node* root){
    char ch;
    int p;
    scanf("%d %c",&p,&ch);
    struct node *temp=create();
    struct node *t=find(root,p);
    
    if(ch=='L')
        t->left=temp;
    else
        t->right=temp;
}

void preorder(struct node* root){
    if(!root)
        return;
    printf("%d ",root->data);
    preorder(root->left);
    preorder(root->right);
}

void inorder(struct node* root){
    if(!root)
        return;
    inorder(root->left);
    printf("%d ",root->data);
    inorder(root->right);
}

void postorder(struct node* root){
    if(!root)
        return;
    postorder(root->left);
    postorder(root->right);
    printf("%d ",root->data);
}

int main() {
    int n;
    scanf("%d",&n);
    struct node* root=create();
    for(int i=1;i<n;i++){
        insert(root);
    }
    printf("Preorder:");
    preorder(root);
    printf("\nInorder:");
    inorder(root);
    printf("\nPostorder:");
    postorder(root);
    return 0;
}


//47 level order traversal
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

struct node{
    struct node *left;
    int data;
    struct node* right;
};

struct node* create(void){
    int n;
    scanf("%d",&n);
    struct node* temp=(struct node*)malloc(sizeof(struct node));
    temp->data=n;
    temp->left=NULL;
    temp->right=NULL;
    return temp;
}

struct node* find(struct node* root,int p){
    if(!root)
        return NULL;
    if(root->data==p)
        return root;
    struct node* temp=find(root->left, p);
    if(temp)
        return temp;
    temp=find(root->right,p);
    return temp;
}

void insert(struct node* root){
    char ch;
    int p;
    scanf("%d %c",&p,&ch);
    struct node *temp=create();
    struct node *t=find(root,p);
    if(ch=='L')
        t->left=temp;
    else
        t->right=temp;
}

int height(struct node* root){
    if(!root)
        return 0;
    int l=height(root->left)+1;
    int r=height(root->right)+1;
    return l>r?l+1:r+1;
}

void curLevel(struct node* root,int h){
    if(!root)
        return;
    if(h==1){
        printf("%d ",root->data);
        return;
    }
    if(h>1){
        curLevel(root->left,h-1);
        curLevel(root->right,h-1);
    }
}

void levelOrder(struct node* root){
    int h=height(root);
    for(int i=1;i<=h;i++)
        curLevel(root,i);
}

int main() {
    int n;
    scanf("%d",&n);
    struct node* root=create();
    for(int i=1;i<n;i++){
        insert(root);
    }
    printf("Level Order Traversal:");
    levelOrder(root);
    return 0;
}


//48 binary search tree
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

struct node{
    struct node *left;
    int data;
    struct node* right;
};

struct node* create(int n){
    struct node* temp=(struct node*)malloc(sizeof(struct node));
    temp->data=n;
    temp->left=NULL;
    temp->right=NULL;
    return temp;
}

struct node* insert(struct node* root,int k){
    if(!root){
        root=create(k);
        return root;
    }
    if(k<=root->data)
        root->left=insert(root->left,k);
    else
        root->right=insert(root->right,k);
    return root;
}

void preorder(struct node* root){
    if(!root)
        return;
    printf("%d ",root->data);
    preorder(root->left);
    preorder(root->right);
}

void inorder(struct node* root){
    if(!root)
        return;
    inorder(root->left);
    printf("%d ",root->data);
    inorder(root->right);
}

void postorder(struct node* root){
    if(!root)
        return;
    postorder(root->left);
    postorder(root->right);
    printf("%d ",root->data);
}

int main() {
    int n;
    scanf("%d",&n);
    struct node* root=NULL;
    for(int i=0;i<n;i++){
        int k;
        scanf("%d",&k);
        root=insert(root,k);
    }
    printf("Preorder:");
    preorder(root);
    printf("\nInorder:");
    inorder(root);
    printf("\nPostorder:");
    postorder(root);
    return 0;
}

//49 binary search
#include <stdio.h>

int bs(int arr[],int n,int k){
    int l=0,h=n-1;
    while(l<=h){
        int m=(l+h)/2;
        if(arr[m]==k) return 1;
        else if(arr[m]>k) h=m-1;
        else l=m+1;
    }
    return 0;
}

int main(){
    int n;
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++)
        scanf("%d",&arr[i]);
    int v;
    scanf("%d",&v);
    if(bs(arr,n,v))
        printf("Yes");
    else
        printf("No");
    return 0;
}


//50 hashing
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int arr[100000]={0};

int main() {
    int n,d,v;
    scanf("%d",&n);
    for(int i=0;i<n;i++){
        scanf("%d",&d);
        arr[d]++;
    }
    scanf("%d",&v);
    if(arr[v])
        printf("Yes\n");
    else
        printf("No\n");
    return 0;
}
