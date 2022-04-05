
def editdistance(s1,s2):

    rows=len(s1)+1
     
    cols=len(s2)+1
    
    matrix=[[0 for x in range(cols)] for x in range(rows)]
    
    for i in range(1,rows):
    
        matrix[i][0]=i
        
        for i in range(1,cols):
        
            matrix[0][i]=i
            
            for i in range(1,cols):
            
                for j in range(1,rows):
                
                    if(s1[j-1]==s2[i-1]):
                    
                        cost=0;
                        
                    else:
                    
                        cost=1
                        
                        matrix[j][i]=min(matrix[j-1][i]+1,
                                         matrix[j][i-1]+1,
                                         matrix[j-1][i-1]+cost)
                                         
    print("Calculation matrix of edit distance:")
    
    for m in range (rows):
    
        print(matrix[m])
        
    print("Edit distance b/w these two strings '"+s1+"' and '"+s2+"' is:")
    
    return matrix[j][i]
    
s1=input("Enter the first string: ")

s2=input("Enter the second string: ")

print(editdistance(s1,s2))
