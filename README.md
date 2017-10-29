# Arduino
Some Arduino Stuff

Um den Rainbird als Rasenbewässerung abzulösen werden die Bewässerungsventile mit dem Arduino geschaltet. Der Code hierfür ist hier in der Entwickung

const int relaisPin1 = 3;
const int relaisPin2 = 4;
//*************************************************************************************************
//Relais LOW schaltet ein!!!
//Dieses Script ist Produktiv!
//Aktiv seit Aug. 2017
//
//Wenn die Anlage für den Winter ausgeblasen werden muss dann dieses Programm laufen lassen. 
//Wichtig ist dabei, dass die kleinen Ventile an den Wechselstromventilen leicht geöffnet werden!!
//Wenn die Anlage wieder in Betrieb genommen wird wie folgt vorgehen:
// 1)
// 2)
// 3)
//*************************************************************************************************

void setup() {
  //pinMode(relaisPin1, OUTPUT); // Den PWM PIN "relaisPin" als Ausgangssignal setzen.
 // pinMode(relaisPin2, OUTPUT);
 Serial.begin(9600);
}

void loop() {
   pinMode(relaisPin1, OUTPUT);
     /* Zone 1  */
  digitalWrite(relaisPin1, HIGH); //Relais aus
    delay(600);  //500ms warten
  digitalWrite(relaisPin1, LOW);  //Relais ein
    delay(600000);// 10Minuten warten
  pinMode(relaisPin1, INPUT);
    digitalWrite(relaisPin1, HIGH); //Relais aus
  delay(7000);
  //---------------------------------------------------
  /*Zone 2 */
  pinMode(relaisPin2, OUTPUT);
  digitalWrite(relaisPin2, HIGH); //Relais aus
  delay(600);  //500ms warten
  digitalWrite(relaisPin2, LOW);  //Relais ein
  delay(300000);// 5 Minuten warten
  pinMode(relaisPin2, INPUT); 
  digitalWrite(relaisPin2, HIGH); //Relais aus
  delay(5000);
}
