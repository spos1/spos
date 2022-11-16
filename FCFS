#include <iostream>
#include <string>
using namespace std;
class process
{
public:
string name;
int cputime, arrivaltime, turnaroundtime, waitingtime, finishtime, arrivaltimegantt;
process()
{
name = "p0";
cputime = 0;
finishtime = 0;
waitingtime = 0;
turnaroundtime = 0;
arrivaltime = 0;
}
void set();
};
void process::set()
{
cout << "Enter the process name: ";
cin >> name;
cout << "Enter the cputime: ";
cin >> cputime;
}
int main()
{
process p[10], gantt[10], u;
int n, i, currenttime = 0;
cout << "Enter the number of process: ";
cin >> n;
for (i = 0; i < n; i++)
{
p[i].set();
}
for (i = 0; i < n; i++)
{
gantt[i] = p[i];
currenttime += p[i].cputime;
gantt[i].finishtime = currenttime;
gantt[i].arrivaltimegantt = gantt[i - 1].finishtime;
gantt[i].turnaroundtime = gantt[i].finishtime - gantt[i].arrivaltime;
gantt[i].waitingtime = gantt[i].turnaroundtime - gantt[i].cputime;
}
// Gantt Chart
cout << "\n********* Gantt Chart *********";
cout << "\n|";
for (i = 0; i < n; i++)
{
cout << " " << gantt[i].name << "\t|";
}
cout << "\n";
cout << "0";
for (i = 0; i < n; i++)
{
cout << "\t" << gantt[i].finishtime;
}
cout << "\n";
// TurnAround Time
int tsum = 0, wsum = 0;
cout << "*\n******** Turnaround time *********" << endl;
cout << "Process | Turnaround Time" << endl;
for (i = 0; i < n; i++)
{
cout << " " << gantt[i].name << " | " << gantt[i].turnaroundtime << endl;
tsum += gantt[i].turnaroundtime;
}
cout << "\n********* Wating time *********" << endl;
cout << "Process | Waiting Time" << endl;
for (i = 0; i < n; i++)
{
cout << " " << gantt[i].name << " | " << gantt[i].waitingtime << endl;
wsum += gantt[i].waitingtime;
}
float tavg, wavg;
tavg = float(tsum / n);
wavg = float(wsum / n);
cout << "\n";
cout << "Average Turnaround time: " << tavg << endl;
cout << "Average waiting time: " << wavg << endl;
}
