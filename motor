#include <IRremote.h>
int enA = 9;
int in1 = 8;
int in2 = 7;
int in3 = 12;
int in4 = 2;

void setup() {
  // Set all the motor control pins to outputs
  IR.enableIRIn();
  Serial.begin(115200);
  Serial.println("start");
  pinMode(in3, OUTPUT);
  pinMode(in4, OUTPUT);
  pinMode(in1, OUTPUT);
  pinMode(in2, OUTPUT);
  // Turn off motors - Initial state
  digitalWrite(in1, HIGH);
  digitalWrite(in2, HIGH);
  digitalWrite(in3, HIGH);
  digitalWrite(in4, HIGH);

  Serial.println("finish");
}

void loop(){
  if(IR.decode()){
   Serial.println( IR.decodedIRData.decodedRawData, HEX);
   if(IR.decodedIRData.decodedRawData == 0xF30CFF00){
    digitalWrite(in1, HIGH);
    digitalWrite(in2, LOW);
    digitalWrite(in3, HIGH);
    digitalWrite(in4, LOW); 
    IR.decodedIRData.decodedRawData=0;
    }

   if(IR.decodedIRData.decodedRawData == 0xE718FF00){
    digitalWrite(in1,LOW);
    digitalWrite(in2,HIGH);
    digitalWrite(in3,LOW);
    digitalWrite(in4,HIGH);
    IR.decodedIRData.decodedRawData = 0;
    }

   if(IR.decodedIRData.decodedRawData == 0xA15EFF00){
    digitalWrite(in1,HIGH);
    digitalWrite(in2,HIGH);
    digitalWrite(in3,HIGH);
    digitalWrite(in4,HIGH);
    IR.decodedIRData.decodedRawData = 0;
    }

   delay(15);
   IR.resume();

  }
}
