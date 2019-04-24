#include<stdio.h>
int main()
{
	char str[50];
	char *p = str;
	char(*b)[11] ;
	char str2[11][11];
	b = str2;
	printf("------------------------------------\n");
	printf("please input string:\n");
	gets_s(str);
	int i = 0, j = 0, count = 0;
	for (i = 0; i <= 100; i++)
	{
		if (*p == '\0')
			break;
		for (;*p>'9'||*p<'0'; p++);
		if (*p <= '9' && *p >= '0')
		{
			for (j = 0; j <= 100; j++)
			{
				if (*p <= '9' && *p >= '0')
				{
					*(*(b + i) + j) = *p;
				}
				p++;
				if (*p < '0' || *p > '9')
					break;
			}
			
		}
		*(*(b + i) + j + 1) = '\0';
	}
	count = i ;
	printf("------------------------------------\n");
	printf("There are %d numbers",count);
	printf("------------------------------------\n");
	printf("they are :\n");
	for (int k = 0; k < i; k++)
		printf("%s\n", *(b + k));
	return 0;
}
