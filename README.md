# -6Companies30days
Q1 Image Smoother



class Solution {
    public int[][] imageSmoother(int[][] img) {
        int m=img.length;
        int n=img[0].length;
        int[][]res=new int[m][n];

        int[]dx={-1,-1,-1,0,0,0,1,1,1};
        int[]dy={-1,0,1,-1,0,1,-1,0,1};
        
        for(int i=0;i<m;i++){
            for(int j=0;j<n;j++){
int sum=0;
        int count=0;
                for(int k=0;k<9;k++){
                    int x=i+dx[k];
                    int y=j+dy[k];
                    if(x>=0 && x<m && y>=0 && y<n){
                    sum+=img[x][y];
                    count++;
                }
                
                }
                res[i][j]=sum/count;


            }
        }
        return res;
    }
}




Q2 Circle and Rectangle Overlapping

class Solution {
    public boolean checkOverlap(int radius, int xCenter, int yCenter, int x1, int y1, int x2, int y2) {
        int closest_x=Math.max(x1,(Math.min(xCenter,x2)));
        int closest_y=Math.max(y1,(Math.min(yCenter,y2)));
        int d1=xCenter-closest_x;
        int d2=yCenter-closest_y;
       


     
      int result;
        result=(d1*d1)+(d2*d2);
        
      return(result<=(radius*radius));
    

    }
}








Q3 Winner of The Game
class Solution {
    public int findTheWinner(int n, int k) {
        ArrayList<Integer>list=new ArrayList<>();
        for(int i=1;i<=n;i++){
            list.add(i);
        }
       int size= list.size();
        int index=0;
        while(size>1){
       
        index=((index+(k-1)) %size);
        list.remove(index);
        size--;

        }
        return list.get(0);
        
    }
}




Q4 Minimum moves to equal array elements 2
class Solution {
    public int minMoves2(int[] nums) {
        Arrays.sort(nums);
        int n=nums.length;
        int start_index=0;
        int end_index=(n-1);
        int mid=(start_index + end_index)/2;
        int moves=0;
        for(int i=0;i<n;i++){
             moves=moves+Math.abs(nums[i]-nums[mid]);
        }
        return moves;
       
    }
}



Q5 Delete n nodes after skipping m nodes
class Solution {
    static void linkdelete(Node head, int n, int m) {
       if(head==null){
           System.out.println("Nothing to delete");
       }
       Node current=head;
        while(current!=null){
            for(int i=0;i<m && current!=null;i++){
                current=current.next;
            }
            Node temp=current.next;
            for(int i=0;i<n && temp!=null;i++){
                temp=temp.next;
            }
            current.next=temp;
            current=temp;
            
        }
        
    }
}





Q6 First unique character in string
class Solution {
    public int firstUniqChar(String s) {
       
        int n=s.length();
        int[]frequency=new int[26];
        for(int i=0;i<n;i++){
            frequency[s.charAt(i)-'a']++;
        }
        for(int i=0;i<n;i++){
            if((frequency[s.charAt(i)-'a'])==1){
                return i;

            }
        }
        return -1;
    }
}
