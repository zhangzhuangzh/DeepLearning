# Hello_git

#include <iostream>
#include <algorithm>

using namespace std;
int x[100], y[100], n;
int team, max_s = 0;
int max(int a, int b, int c)
{
	if (a < c)
		a = c;
	if (a < b)
		a = b;
	return a;
}
void fun(int num_a, int num_b, int i, int team)
{
	int a, b, c, tmp;
	if (i == n)
	{
		if (max_s < team  && num_a == num_b)
		{
			max_s = team;
		}
		return;
	}
	
	fun(num_a + x[i], num_b, i + 1, team + y[i] );
		
	fun(num_a, num_b + x[i], i + 1, team + y[i] );
	
	fun(num_a, num_b, i + 1, team);

}

int main()
{
	int num_a = 0, num_b = 0;
	cin >> n;
	int i;
	for (i = 0; i < n; i++)
	{
		cin >> x[i] >> y[i];
	}
	fun(0, 0, 0, 0);
	cout <<max_s<< endl;
}
end
