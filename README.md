#include<iostream>
#include<cstdlib>
#include<ctime>
using namespace std;

class Player{
    string name;
    int runs;
public:
    void create(string playername){
        name=playername;
        runs=0;
    }
    int bat(){
        int score=rand()%6+1;
        runs+=score;
        return score;
    }
    void celebrate(){
        cout<<name<<" celebrates hitting "<<endl;
    }
};

int main(){
    srand(time(0));
    Player Team1[3];
    Player Team2[3];
    int totalscoreteam1=0;
    int totalscoreteam2=0;
    cout<<"team 1 playing"<<endl;
    for(int i=0;i<3;i++){
        string name;
        cin>>name;
        Team1[i].create(name);
        int innings=3;
        while(innings>0){
            int score=Team1[i].bat();
            if(score==4||score==6){
                Team1[i].celebrate();
            }
            cout<<score<<endl;
            totalscoreteam1+=score;
            innings--;
        }
    }
    cout<<"team 1 total score is "<<totalscoreteam1<<endl;
    cout<<"team 2 playing"<<endl;
    for(int i=0;i<3;i++){
        string name;
        cin>>name;
        Team2[i].create(name);
        int innings=3;
        while(innings>0){
            int score=Team2[i].bat();
            if(score==4||score==6){
                Team2[i].celebrate();
            }
            cout<<score<<endl;
            totalscoreteam2+=score;
            innings--;
        }
    }
    cout<<"team 2 total score is "<<totalscoreteam2<<endl;
    if(totalscoreteam1>totalscoreteam2){
        cout<<"Team 1 wins"<<endl;
    }
    else if(totalscoreteam1==totalscoreteam2){
        cout<<"tie"<<endl;
    }
    else{
        cout<<"Team 2 wins"<<endl;
    }
}
