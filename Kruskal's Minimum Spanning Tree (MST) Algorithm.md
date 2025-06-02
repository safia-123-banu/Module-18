# Ex. No: 18B - Kruskal's Minimum Spanning Tree (MST) Algorithm

## AIM:
To write a Python program for **Kruskal's algorithm** to find the Minimum Spanning Tree (MST) of a given connected, undirected, and weighted graph.

## ALGORITHM:

**Step 1**: Sort all the edges of the graph in non-decreasing order of their weights.

**Step 2**: Initialize the `parent[]` and `rank[]` arrays for each vertex to keep track of the disjoint sets.

**Step 3**: Iterate through the sorted edges and pick the smallest edge. Check whether including this edge will form a cycle using the union-find method:
- If the vertices of the edge belong to different sets, include it in the MST.
- Perform a union of these two sets.

**Step 4**: Repeat Step 3 until the MST contains exactly `V-1` edges.

**Step 5**: Print the edges included in the MST and the total minimum cost.

## PYTHON PROGRAM

```
from collections import defaultdict

# This class represents a directed graph
# using adjacency list representation
class Graph:

	# Constructor
	def __init__(self):

		# default dictionary to store graph
		self.graph = defaultdict(list)

	# function to add an edge to graph
	def addEdge(self,u,v):
		self.graph[u].append(v)

	# Function to print a BFS of graph
	def BFS(self, s):

		# Mark all the vertices as not visited
		visited = [False] * (max(self.graph) + 1)

		# Create a queue for BFS
		queue = []

		# Mark the source node as
		# visited and enqueue it
		queue.append(s)
		visited[s] = True

		while queue:
		    s=queue.pop(0)
		    print(s,end=" ")
		    
		    for i in self.graph[s]:
		        if visited[i]==False:
		            queue.append(i)
		            visited[i]=True
		
		
		
		

# Create a graph given in
# the above diagram
n=int(input())
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)

print ("Following is Breadth First Traversal"
				" (starting from vertex {})".format(n))
g.BFS(n)

```

## OUTPUT
![image](https://github.com/user-attachments/assets/a7d87372-567c-4dec-ba3e-8f932a7465e1)


## RESULT
Thus the python program was initialised and executed successfully.
