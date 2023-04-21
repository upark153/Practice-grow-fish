# Practice-grow-fish
This is a programming exercise for raising fish in c language.
![image](https://user-images.githubusercontent.com/115389450/233516037-def44633-62e8-4723-9c3a-93f8aaefa086.png)
- - -
문제 1
- - -
```
// 세개의 정수를 인자로 전달받아서
// 가장 큰 수를 반환하는 함수
// 가장 작은 수를 반환하는 함수 
// 그리고 이 함수들을 호출하는 적절한 main 함수
#include <stdio.h>

int max(int a, int b, int c)
{
    int result;
    result = ((a>b)&&(a>c))?a:((b>a)&&(b>c))?b:c;
    return result;
}
int mini(int a, int b, int c)
{
    int result;
    result= ((a>b)&&(b>c))?c:((c>a)&&(a>b))?b:a;
    return result;
}

int main(void)
{
    int a,b,c;
    printf("세 개의 정수 입력: ");
    scanf("%d %d %d", &a, &b, &c);
    printf("가장 큰 수:%d, 가장 작은 수:%d\n", max(a,b,c), mini(a,b,c));
    return 0;
}
```
- - -
문제 2
- - -
```
// 인자로 전달된 수만큼의 피보나치 수열을 출력하는 함수 정의
// 예를 들어서
// 프로그램 사용자가 5를 입력하면
// 0에서 시작해서 5개의 피보나치 수열 출력
// 참고로 피보나치 수열은 다음과 같다
// 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...
// 피보나치 수열은 0과 1에서 시작한다.
// 그리고 세 번째 이후의 수열부터는
// 이전의 두 값의 합으로 구성된다.
// 즉 세 번째 수는 0과 1의 합으로 이뤄져서 1이 되고,
// 네 번 째 수는 1과 1의 합으로 이뤄져서 2가  된다.

#include <stdio.h>
int fibonacci(int x) // 재귀 함수 사용 ?
{
    if(x==0) // x가 0일 때 0 값 반환
        return 0;
    else if(x==1) // x가 1일 때 1값 반환
        return 1;
    return fibonacci(x - 2) + fibonacci(x - 1);  // ex: x가 5이면 fibonacci(3) + fibonacci(4)의 값을 반환한다.    
}

int main(void)
{
    int a = 0; // 몇 번 수열까지 표시하시겠습니까?
    int i = 0; // 반복. 몇번째자리까지 표시하는지. 그리고 반복문 탈출.

    printf("피보나치 수열을 출력합니다\n");
    printf("몇번수열까지 표시하시겠습니까? 입력: ");
    scanf("%d", &a);

    for(i=0; i<a; i++)
    {
        printf("%d\n", fibonacci(i)); // i가 5이면 위에 전역함수에 x=i, 즉 5를 대입한다.
    }
    return 0;
}
```
- - -
문제 3
- - -
```
// 인자로 전달된 수만큼의 피보나치 수열을 출력하는 함수 정의
// 예를 들어서
// 프로그램 사용자가 5를 입력하면
// 0에서 시작해서 5개의 피보나치 수열 출력
// 참고로 피보나치 수열은 다음과 같다
// 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...
// 피보나치 수열은 0과 1에서 시작한다.
// 그리고 세 번째 이후의 수열부터는
// 이전의 두 값의 합으로 구성된다.
// 즉 세 번째 수는 0과 1의 합으로 이뤄져서 1이 되고,
// 네 번 째 수는 1과 1의 합으로 이뤄져서 2가  된다.

#include <stdio.h>
int fibonacci(int x) // 재귀 함수 사용 ?
{
    if(x==0) // x가 0일 때 0 값 반환
        return 0;
    else if(x==1) // x가 1일 때 1값 반환
        return 1;
    return fibonacci(x - 2) + fibonacci(x - 1);  // ex: x가 5이면 fibonacci(3) + fibonacci(4)의 값을 반환한다.    
}

int main(void)
{
    int a = 0; // 몇 번 수열까지 표시하시겠습니까?
    int i = 0; // 반복. 몇번째자리까지 표시하는지. 그리고 반복문 탈출.

    printf("피보나치 수열을 출력합니다\n");
    printf("몇번수열까지 표시하시겠습니까? 입력: ");
    scanf("%d", &a);

    for(i=0; i<a; i++)
    {
        printf("%d\n", fibonacci(i)); // i가 5이면 위에 전역함수에 x=i, 즉 5를 대입한다.
    }
    return 0;
}
```
![image](https://user-images.githubusercontent.com/115389450/233516195-f2791ea5-8233-4a4c-90f0-33fa1bf23e77.png)
```
// 다음은 프로그램 사용자가
// 입력하는 값을 누적하여 
// 그 합계를 출력하는 예제이다.

#include <stdio.h>

static int total=0; // int total=0에 static 함수를 앞에 붙여주었다.
                      // 전역변수 total을 static변수로 대체? static은 다른 함수에서 호출하지 못하는 정적함수?
int AddToTotal(int num) // addtotal 은 입력 값 누적하여 더하는 함수
{
    total+=num; // total 값은 total+num
    return total; 
}

int main(void)
{
    int num;
    int i;
    for(i=0; i<3; i++)
    {
        printf("입력%d: ", i+1);
        scanf("%d", &num);
        printf("누적:%d \n", AddToTotal(num));
    }
    return 0;
}
```
- - -
물고기 키우기 
- - -
```
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main()
{ 
    
    int Ryu=1; // 류 금붕어
    int Ryu_partner=1; // 류 금붕어 아내
    int Ryu_partner_child=0; // 류 파트너 금붕어
    int child=0; // 류파트너 금붕어가 낳은 새끼들이 낳은 새끼들
    int Ryu_die_child=0; // 금붕어가 죽는 수
    int finaltotal; // 최종 수
    int num=0; // 몇번째 1000마리가 되는지

    printf("류 금붕어의 애칭:최강\n");
    printf("류 짝꿍 애칭:최강파트너\n");

    srand(time(0));


    for(finaltotal=2;  finaltotal-num<=1000; finaltotal++)
    {
        num+=1;
        printf("금붕어가 %d번째자식을 낳기 시작합니다\n", num);

        Ryu_partner_child=rand()%10+1; // 1~10마리 랜덤으로 낳는다

        printf("금붕어가 태어난 숫자 : %d 마리\n", Ryu_partner_child);
        if(Ryu_partner_child%2==0) // 짝수일 경우 새끼를 낳는다.
        {
            printf("태어난 금붕어가 새끼를 낳기 시작합니다\n");
            child=rand()%5+1; // 2마리=1마리, 4마리=2마리, 6마리=3마리, 8마리=4마리, 10마리=5마리
            printf("태어난 금붕어가 낳은 자식 숫자 : %d 마리\n", child);
        }
        while(num>1) // 2번째 판부터 죽는다.
        {
            Ryu_die_child=rand()%10+1;  // 1~10마리 랜덤으로 죽는다
            printf("금붕어 죽은 숫자 : %d 마리\n", Ryu_die_child);
            break;
        }

        finaltotal += Ryu_partner_child+child-Ryu_die_child; // 최종 금붕어 수= 최종수+류아내자식들+자식들의자식들-죽은금붕어
        printf("금붕어의 현재 숫자 : %d 마리\n", finaltotal-num); // num을 빼준이유는 ++로 1씩 계속 증가하기 때문에
    }
    if(finaltotal-num>1000) // 만약 1000마리 넘으면
    {
        printf("어항에 존재할 수 있는 금붕어는 1000마리입니다.\n");
        printf("어항을 벗어난 금붕어는 죽습니다 ㅜㅜ\n");
        int last;
        int fishbowl=1000; 
        last=finaltotal-num; 
        last=last-(last-fishbowl); // 1000마리 넘은 수에서 어항수 1000을 뺀 수를 최종수에서 빼줬습니다.
        printf("어항에 살아있는 금붕어 개수: %d\n", last);         // 마지막 1000마리
    }
    return 0;
}
```
- - -
물고기 키우기 복습
- - -
```
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main(void)
{
  int num=1; // 몇 번째 1000마리가 되는지
  int total_fish=2; // 류와 류아내분
  int fish_child; // 물고기 자식들 탄생
  int fish_die; // 죽은 물고기들..
  char ryu[50], ryu_wife[50]; // 문자열을 받기 위한 char함수 선언 
                                    // 한글은 3바이트라서, 숫자 50을 입력했을 때 150바이트까지 들어간다고 한다

  printf("류 애칭 : \n"); 
  scanf("%s", ryu);
  printf("류 아내 애칭 : \n");
  scanf("%s", ryu_wife);
  printf("류 키우기 시작!\n");
  
  srand(time(0));
  fish_child=rand()%10 +1; // 처음 시작할 때는 반복문을 사용하지 않고 했다. 
  total_fish+=fish_child; // 전체 물고기 + 물고기 자식들
  printf(" %d번째 \n %d쌍이 짝짓기 \n %d마리가 탄생 \n 총 %d 마리", 
              num, total_fish/2, fish_child, total_fish);
  /* 사실 띄어쓰기나 줄을 바꾸는 것에 대해서 고민을 안 했었다.
     하지만 이번 과제를 통해서 띄어쓰기 및 줄 바꿈으로 터미널에 표시되는 값의 가독성이 좋아짐을 느꼈다.
     여기서 total_fish 값을 2로 나눠준 이유는 결국 1쌍은 2마리의 물고기이므로 몇쌍이 짝짓기를 했는가?
     의 물음에 대한 답이 된다. 하나의 값에 중요한 값을 나타낼 수 있다는 사실은 공부를 할수록 대단한 것 같다. */
  
   while(total_fish<1000) // 전체 물고기가 1000마리가 되기 전까지 반복한다.
   {
         num++; // 몇번째 판에 물고기가 1000마리가 되는가를 알기 위해서
         int total = total_fish; // while문 안에 for문이 시작하기 전에 total이라는 새로운 변수를 지정 한 이유는?
                                    //  새로운 변수를 지정해줌으로써 전체 물고기 값의 메모리 재할당?
            for(int i=0; i<total/2; i++) // i는 반복문을 위한 변수, total/2를 한 이유는? 
            {
              fish_child = (rand()%5+1) * 2 // 물고기 자식들은 1,2,3,4,5마리의 자식을 낳고 거기에 2를 곱해 준 이유는?
                                                    // 2, 4, 6, 8, 10이 되는데 1이라는 숫자가 나오면 짝짓기를 하지 못하므로
                                                    // 2를 곱해주었다고 한다(맞나?) 우선 이렇게 이해는 했다.
              total_fish += fish_child; // 다시 반복문안에 전체 물고기 = 전체물고기 +물고기 자식들
            }
          die_fish = (rand()%5+1) *2 // 죽는 물고기 수에도 2를 곱해주었다.
          total_fish -= die_fush; // 전체 물고기 = 전체물고기 - 죽은 물고기 수
          printf("\n%d번째 \n%d쌍이 짝짓기 \n%d마리가 탄생 \n%d마리가 사망 \n 총 %d마리",
                     num, total/2, total_fish-total, die_fish, total_fish);
                    /* 몇번째? , 
                       몇쌍이 짝짓기하는가? - total(전체 수)/2, 
                       몇마리가 탄생하는가? - for문안에 total/2가 i값보다 작을 때 계속 반복하고 있다.
                       따라서 total_fish 에서 total을 빼주었다?
                       몇마리가 사망하였는가? - die_fish
                       총 몇마리인가? - total_fish */
    }
    printf("\n 1000마리가 되기까지 걸린 횟수 : %d\n", num);
   
 return 0;
}
```
