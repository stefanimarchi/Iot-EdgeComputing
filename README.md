#Curso-Extens-o-IoT-Iniciantes Curso de Extensão IoT na prática para iniciantes
Repositório das aulas do curso de microbit e arduino. 

1) Projeto: Arduino uno com sensor ultrassonico e piezo.

int trigger_pin = 7;
int echo_pin = 6;
int buzzer_pin = 10;
int time;
int distance;
void setup()
{
  	Serial.begin (9600);
  	pinMode (trigger_pin, OUTPUT);
  	pinMode (echo_pin, INPUT);
  	pinMode (buzzer_pin, OUTPUT);
}
void loop()
{
  	digitalWrite (trigger_pin, HIGH);
  	delayMicroseconds (10);
  	digitalWrite (trigger_pin, LOW);
  	time = pulseIn (echo_pin, HIGH);
  	distance = (time * 0.034) / 2;

  if (distance <= 20)
  {
    Serial.print (" Distance= ");
    Serial.println (distance);
    digitalWrite (buzzer_pin, HIGH);
    delay (500);
  }
  else {
    Serial.print (" Distance= ");
    Serial.println (distance);
    digitalWrite (buzzer_pin, LOW); 
    delay (500);
  }
  
}

