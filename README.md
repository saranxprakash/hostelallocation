#include <iostream>
#include<stdlib.h>
using namespace std;

class admin{
    int userid;
    char pass[15];
    public:
    void registration();
    void login();
    void display1(){
        cout<<"user id:"<<userid;
    }
};
void admin::registration(){
    cout<<"user id: ";
    cin>>userid;
    cout<<endl<<"password: ";
    cin>>pass;

}

class student:public admin{
    char stud_name[50];
    public:
    char gender,hometown;
    void getstudata();
    void display2(){cout<<endl<<" name:"<<stud_name;
    cout<<endl<<"gender : "<<gender;

    }
};
void student::getstudata(){
    cout<<endl<<"your name:";
    cin>>stud_name;
    cout<<endl<<"enter your gender(M/F)";
    cin>>gender;
    cout<<endl<<"hometown at pondicherry or not(y/n)";
    cin>>hometown;

};
/*class hostel:public student{
    public:
    
    char checkhometown(char s){
        
    }
    char checkgender(char g);{
        if(g=='M' || g=='y')
    }
};*/

class boys_hostel:public student {
        char boys_hostel_name[15]="boyshostel1";
        int room_no;
        public:
        void allocation1(){
    
            room_no=101;
        }
        void display3(){
            display1();
            display2();
            cout<<endl<<"hostal name : boyshostel1";
            cout<<endl<<"hostel room number:"<<room_no;

        }
};

class girls_hostel: public student{
        char girls_hostel_name[15]="girlshostel1";
        int room_no;
        public:
        void allocation2(){
       
            room_no=101;
        }
        void display4(){
            display1();
            display2();
            cout<<endl<<"hostal name : girlshostel1";
            cout<<endl<<"hostel room number:"<<room_no;

        }
};
int main(){
    int choice;
    cout<<"1.registeration"<<endl
        <<"2.login"<<endl;
    
    admin adm;
    student stu;
    boys_hostel bh;
    girls_hostel gh;
        adm.registration();
        stu.getstudata();
        if(stu.hometown=='Y' ||stu.hometown =='y'){
            cout<<"you are not eligible for hostel ";
            exit (0);
        }
        if(stu.gender=='M' ||stu.gender =='m'){
            bh.allocation1();
            bh.display3();
        }
        else{
            gh.allocation2();
            gh.display4();
        }


    return 0;
}
