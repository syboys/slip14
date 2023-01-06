# slip14


Q.1 Write a Java Program to implement Command Design Pattern for Command Interface
with execute() . Use this to create variety of commands for LightOnCommand,
LightOffCommand, GarageDoorUpCommand, StereoOnWithCDComman.
Q.2. Write a python program to find all null values in a given dataset and remove them.

Q.3 Write node js script to interact with the filesystem, and serve a web page from a file .


Q.1 Write a Java Program to implement Command Design Pattern for Command Interface
with execute() . Use this to create variety of commands for LightOnCommand,
LightOffCommand, GarageDoorUpCommand, StereoOnWithCDComman.
:

interface Command {
 public void execute();
}
}
}
class StereoOn implements Command {
Stereo s;
public StereoOn(Stereo l) {
this.s = l;
}
public void execute() {
s.On();
}
}
 class SimpleRemoteControl {
 Command slot;

 public SimpleRemoteControl() {}

 public void setCommand(Command command) {
 slot = command;
 }

 public void buttonWasPressed() {
 slot.execute();
 }

}
public class Main {
 public static void main(String[] args) {
SimpleRemoteControl remote = new SimpleRemoteControl();
Light light = new Light();
LightOnCommand lightOn = new LightOnCommand(light);
remote.setCommand(lightOn);
remote.buttonWasPressed();
LightOffCommand lightOff = new LightOffCommand(light);
remote.setCommand(lightOff);
remote.buttonWasPressed();
GarageDoor garageDoor = new GarageDoor();
GarageDoorUpCommand garageDoorUp = new GarageDoorUpCommand(garageDoor);
 remote.setCommand(garageDoorUp);
remote.buttonWasPressed();

 Stereo s1=new Stereo();
 StereoOn s2 =new StereoOn(s1);
remote.setCommand(s2);
remote.buttonWasPressed();

 } 
 }
 
 
 Q.2. Write a python program to find all null values in a given dataset and remove them.
 :
 df = df.dropna(how='any',axis=0) 


#Recreate random DataFrame with Nan values
df = pd.DataFrame(index = pd.date_range('2017-01-01', '2017-01-10', freq='1d'))
# Average speed in miles per hour
df['A'] = np.random.randint(low=198, high=205, size=len(df.index))
df['B'] = np.random.random(size=len(df.index))*2

#Create dummy NaN value on 2 cells
df.iloc[2,1]=None
df.iloc[5,0]=None

print(df)
                A         B
2017-01-01  203.0  1.175224
2017-01-02  199.0  1.338474
2017-01-03  198.0       NaN
2017-01-04  198.0  0.652318
2017-01-05  199.0  1.577577
2017-01-06    NaN  0.234882
2017-01-07  203.0  1.732908
2017-01-08  204.0  1.473146
2017-01-09  198.0  1.109261
2017-01-10  202.0  1.745309

#Delete row with dummy value
df = df.dropna(how='any',axis=0)

print(df)

                A         B
2017-01-01  203.0  1.175224
2017-01-02  199.0  1.338474
2017-01-04  198.0  0.652318
2017-01-05  199.0  1.577577
2017-01-07  203.0  1.732908
2017-01-08  204.0  1.473146
2017-01-09  198.0  1.109261
2017-01-10  202.0  1.745309



Q.3 Write node js script to interact with the filesystem, and serve a web page from a file .
:  <html>
<body>
<h1>My Header</h1>
<p>My paragraph.</p>
</body>
</html>
var http = require('http');
var fs = require('fs');
http.createServer(function (req, res) {
fs.readFile('demofile1.html', function(err, data) {
 res.writeHead(200, {'Content-Type': 'text/html'});
 res.write(data);
 return res.end();
});
}).listen(8080);
