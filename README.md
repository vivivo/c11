#include<iostream>
#include<string>
#include<sstream>
using namespace std;
long long fibo(int n);
string output(long long num);
int main(){
    int n=0;
    cout<<"enter a number: ";
    cin>>n;
    string s=output(fibo(n));
    cout<<"fibo("<<n<<")="<<s<<endl;
    system("PAUSE");
    return 0;
    }
long long fibo(int n){
     while(n<2)
     return 1;
     long long temp1=1;
     long long temp2=1;
     long long total=2;
     while(n-->2){
                  total=temp1+temp2;
                  temp1=temp2;
                  temp2=total;
                  }
     return total;
     }
#define sep ','
#define size 3         
string output(long long num){
       stringstream temp,out;
       temp<<num;
       string s=temp.str();
       int n =s.size()%size;
       int i=0;
       if(n>0&&s.size()>size){
                              out<<s.substr(i,n)<<sep;
                              i+=n;
                              }
                              n=s.size()/size-1;
                              while(n-->0){
                                           out<<s.substr(i,size)<<sep;
                                           i+=size;
                                           }
                                           out<<s.substr(i);
                                           return out.str();
       }     
