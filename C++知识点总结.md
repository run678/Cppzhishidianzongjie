# 数据结构：图

## 图的邻接表：

![image-20210917112141686](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210917112141686.png)

![image-20210917111624826](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210917111624826.png)

![image-20210917111700947](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210917111700947.png

![image-20210917145558582](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210917145558582.png)

```c++
#include <iostream>
#include <vector>
using namespace std;

struct GraphNode
{
	int label;
	vector<GraphNode*> neighbors;   //存储与顶点相邻的节点指针
};
int main()
{
	GraphNode G[4];       //创建长度为4的图顶点结构体数组
	//0、1、2、3四个顶点就对应了G[0]、G[1]、G[2]、G[3]四个结构体
	for (int i = 0; i < 4; i++)
	{
		G[i].label = i;  //顶点编号赋值为0、1、2、3  
	}
	G[0].neighbors.push_back(&G[2]);
	G[0].neighbors.push_back(&G[3]);

	G[1].neighbors.push_back(&G[0]);
	G[1].neighbors.push_back(&G[2]);
	//添加2到3的边
	G[2].neighbors.push_back(&G[3]);
	//添加3到0的边
	G[3].neighbors.push_back(&G[0]);
	cout << "Graph:" << endl;
	for (int i = 0; i < 4; i++)
	{
		cout << "Label[" << i << "]:";
		for (int j = 0; j < G[i].neighbors.size(); j++)
		{
			cout << G[i].neighbors[j]->label<<" ";
		}
		cout << endl;
	}
	getchar();
	return 0;
}
```

# 链表

## 链表求交点            

  视频地址：https://www.bilibili.com/video/BV1nf4y167d7?spm_id_from=333.999.0.0

