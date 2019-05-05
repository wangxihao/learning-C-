## 比较实用的函数
#include <iostream>
#"其他文件夹"
using namespace std;

int main(){
	int n;
	vector<int> v;
	while (cin >> n)
	{
		for (int j = 0; j < n; ++j)
		{
			int x; cin >> x;
			v.push_back(x);
		}


		sort(v.begin(), v.end());

		int step;
		cin >> step;
		int big = v[n - 1];
		int smaller = big - 7 * step;
		vector<int> res;
		for (int i = smaller; i <= big; i += step)
		{
			if (find(v.begin(), v.end(), i) != v.end())  //反回的迭代器不等于v.end()，v.end()并不是vector中的最后一个元素，而是下一个
				res.push_back(1);                        //find范围[begin,last)

			else
				res.push_back(0);

		}

		unsigned int result = 0;
		for (int i = 0; i < res.size(); i++)
		{
			result += res[i] << (7 - i);
		}

		cout << result;

	}
	return 0;
}


