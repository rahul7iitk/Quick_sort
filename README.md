# Quick_sort
#include<stdio.h>

void sort(int[],int,int);
int partition(int[],int,int);

int main()
{
    int n;
    scanf("%d",&n);
    
    int m[n];
    
    for(int i=0;i<n;i++)
    scanf("%d",&m[i]);
    
    
    sort(m,0,n-1);
    
    
    for(int i=0;i<n;i++)
    printf("%d ",m[i]);
    
    return 0;
    
}

void sort(int m[],int start,int end)
{
    if(start>end)
    return;
    
    int p=partition(m,start,end);
    
    sort(m,start,p-1);
    sort(m,p+1,end);
    
}

int partition(int m[],int start,int end)
{
    int pivot=m[start];
    
    int fp=start,lp=end;
    
    while(fp<=end&&lp>=start)
    {
        while(m[fp]<=pivot)
       { fp++;
       if(fp>end)
       break;
       }
        
        while(m[lp]>=pivot)
       { lp--;
       if(lp<start)
       break;
       }
        if(fp<lp)
        {
            int t=m[fp];
            m[fp]=m[lp];
            m[lp]=t;
            fp++;
            lp--;
        }
        else
        {
          int t=m[fp-1];
          m[fp-1]=m[start];
          m[start]=t;
          return fp-1;
            
        }
        
    }
    return -1;
    
}
        
    
































