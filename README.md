# AddBinaryNumbers

#include <iostream>
#include<cmath>
using namespace std;
int reverse(int n){
    int ans =0;
    while(n>0){
        int lasdigit = n%10;
        ans = ans*10 + lasdigit;
        n/= 10;
    }
    return ans;
}
int addbinary(int a, int b){
    int ans =0;
    int prevCarry =0;
    while( a>0 && b>0){
        if(a%2 ==0 && b% 2 ==0)
        {
            ans = ans *10 + prevCarry;
            prevCarry = 0;
        }
        else if(a%2 ==0 && b%2 ==1){
            if(prevCarry == 1){
                ans = ans*10 +0;
                prevCarry =1;
            }
            else{
                ans  = ans *10 +1;
                prevCarry = 0;
            }
        }
        else{
            ans  = ans *10 + prevCarry;
            prevCarry = 1;
        }
        a /= 10;
        b  /= 10;
    }
    while(a>0){
        if(prevCarry == 1){
            ans =  ans*10 +0;
            prevCarry =1;
        }
        else{
            ans = ans*10+1;
            prevCarry = 0;
        }
    }
    while(a>0){
        if(prevCarry == 1){
            if(a%2 == 1){
                ans =  ans*10+0;
                prevCarry =1;
            }
            else{
                ans = ans*10+1;
                prevCarry =0;
            }
        }
        else{
            ans = ans * 10 + (a%2);
        }
        a/=10;
    }
       while(b>0){
        if(prevCarry == 1){
            ans =  ans*10 +0;
            prevCarry =1;
        }
        else{
            ans = ans*10+1;
            prevCarry = 0;
        }
    }
    while(b>0){
        if(prevCarry == 1){
            if(b%2 == 1){
                ans =  ans*10+0;
                prevCarry =1;
            }
            else{
                ans = ans*10+1;
                prevCarry =0;
            }
        }
        else{
            ans = ans * 10 + (b%2);
        }
        b/=10;
    }
    if(prevCarry == 1){
        ans =  ans*10 + 1;
    }
    ans = reverse(ans);
    return ans;
}
int main() {
    int a, b;
    std::cin >> a>> b;
    std::cout <<addbinary(a,b);
}

	
		Bit Manipulation
    
    Funcions::
    
    #include <iostream>
using namespace std;

int getBit(int n, int pos){
    return(n && (1<<pos) !=0);
}

int setBit(int n, int pos){
    return(n |1<<pos);
}

int clearBit(int n, int pos){
    int mask =~(1<<pos);
    return (n & mask);
}

int updateBit(int n, int pos, int value){
    int mask =~(1<<pos);
    n = (n & mask);
    return(n | value);
}
int main() {
    //std::cout << getBit(5,1) << std::endl;       
    // cout<<setBit(6,0);
    //cout<<clearBit(6,1);
    
    cout<<updateBit(10,0,1);
	// your code goes here
	return 0;
}

    
   
