int msensor = A1; // moisture sensor is connected with the analog pin A1 of the Arduino
int led = 13; 
int msvalue = 0; // moisture sensor value 

void setup() {
  Serial.begin(9600);
  pinMode(msensor, INPUT);
  pinMode(led, OUTPUT);  
}

void loop() {
  msvalue = analogRead(msensor);
  Serial.println(msvalue);
  
  if (msvalue >= 500  )
{
  digitalWrite(led, LOW); 
  Serial.println(" --- No Sufficient water") ; 
  delay(1000); 
}

  if (msvalue <= 300  )
{
  digitalWrite(led, HIGH);
  Serial.println(" --- Adequate water available");     
  delay(1000); 
}



  delay(500);      
}
