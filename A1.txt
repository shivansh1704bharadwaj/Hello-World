#include <iostream>
using namespace std;


int main() {
    int t,j=1;
    cin>>t;
    while(t--)
    {
        int n;
        cin>>n;
        int min=n+10,counter=0,count=0;
        char a[n][n];
        for(int i=0;i<n;i++)
        {
            for(int j=0;j<n;j++)
            {
                cin>>a[i][j];
            }
        }
        
        
        for(int i=0;i<n;i++)
        {
            for(int j=0;j<n;j++)
            {
                if(a[i][j]=='O')
                {
                    count=n+11;
                continue;
                }
                else
                {
                    if(a[i][j]=='.')
                    {
                    
                    count++;
                    }
                }
                if(j==n-1)
                {
                    for(int k=0;k<n;k++)
                    a[i][k]=='X';
                }
            }
            if(count<min)
            {
                min=count;
                counter=0;
            }
            if(count==min)
                counter++;
                count=0;
        }
        
        
        for(int i=0;i<n;i++)
        {
            for(int j=0;j<n;j++)
            {
                if(a[j][i]=='O')
                {
                    count=n+1;
                continue;
                }
                else
                {
                    if(a[j][i]=='.')
                    {
                    
                    count++;
                    }
                }
                if(j==n-1)
                {
                    for(int k=0;k<n;k++)
                    a[k][i]=='X';
                }
            }
            if(count<min)
            {
                min=count;
                counter=0;
            }
            if(count==min)
                counter++;
                count=0;
        }
        if(min>n)
        cout<<"Case #"<<j<<": Impossible"<<"\n";
        else
        cout<<"Case #"<<j<<": "<<min<<" "<<counter<<"\n";
        j++;
        
    }
	// your code goes here
	return 0;
}
