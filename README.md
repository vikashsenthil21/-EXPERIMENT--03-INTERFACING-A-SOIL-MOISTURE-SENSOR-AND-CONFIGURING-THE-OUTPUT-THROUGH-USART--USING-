## EXPERIMENT--03-INTERFACING-A-SOIL-MOISTURE-SENSOR-AND-CONFIGURING-THE-OUTPUT-THROUGH-USART- USING IOT DEVELOPMENT BOARD
# Aim:
To Interface a soil moisture sensor , configure  the ADC and transfer the data through serial port usign USART  
## Components required:
STM32 CUBE IDE, ARM IOT development board,  STM programmer tool, Serial port utility tool 
## Theory 
The full form of an ARM is an advanced reduced instruction set computer (RISC) machine, and it is a 32-bit processor architecture expanded by ARM holdings. The applications of an ARM processor include several microcontrollers as well as processors. The architecture of an ARM processor was licensed by many corporations for designing ARM processor-based SoC products and CPUs. This allows the corporations to manufacture their products using ARM architecture. Likewise, all main semiconductor companies will make ARM-based SOCs such as Samsung, Atmel, TI etc.
## Soil moisture sensor 
The soil moisture sensor is one kind of sensor used to gauge the volumetric content of water within the soil. As the straight gravimetric dimension of soil moisture needs eliminating, drying, as well as sample weighting. These sensors measure the volumetric water content not directly with the help of some other rules of soil like dielectric constant, electrical resistance, otherwise interaction with neutrons, and replacement of the moisture content.

The relation among the calculated property as well as moisture of soil should be adjusted & may change based on ecological factors like temperature, type of soil, otherwise electric conductivity. The microwave emission which is reflected can be influenced by the moisture of soil as well as mainly used in agriculture and remote sensing within hydrology.

<img height=30% width=40% src="https://user-images.githubusercontent.com/36288975/234777393-51ef4e67-bfe4-4aed-b3ca-02fdcb7216f2.png">




  Soil Moisture Sensor Pin Configuration
The FC-28 soil moisture sensor includes 4-pins as shown below 
VCC pin is used for power
A0 pin is an analog output
D0 pin is a digital output
GND pin is a Ground

<img height=30% width=40% src="https://user-images.githubusercontent.com/36288975/234777177-7000d50b-e82a-4ba6-ab1e-e8b9e0903f68.png">


 ## Procedure:
 1. click on STM 32 CUBE IDE, the following screen will appear 
<img height=30% width=40% src="https://user-images.githubusercontent.com/36288975/226189166-ac10578c-c059-40e7-8b80-9f84f64bf088.png">

 2. click on FILE, click on new stm 32 project 
<img height=30% width=40% src="https://user-images.githubusercontent.com/36288975/226189215-2d13ebfb-507f-44fc-b772-02232e97c0e3.png">
<img height=30% width=40% src="https://user-images.githubusercontent.com/36288975/226189230-bf2d90dd-9695-4aaf-b2a6-6d66454e81fc.png">
3. select the target to be programmed  as shown below and click on next 

<img height=30% width=40% src="https://user-images.githubusercontent.com/36288975/226189280-ed5dcf1d-dd8d-43ae-815d-491085f4863b.png">

4.select the program name 
<img height=30% width=40% src="https://user-images.githubusercontent.com/36288975/226189316-09832a30-4d1a-4d4f-b8ad-2dc28f137711.png">


5. corresponding ioc file will be generated automatically 
<img height=30% width=40% src="https://user-images.githubusercontent.com/36288975/226189378-3abbdee2-0df6-470f-a3cd-79c74e3d3ad8.png">

6.select the appropriate pins as gipo, in or out, USART or required options and configure 
<img height=20% width=30% src="https://user-images.githubusercontent.com/36288975/226189403-f7179f1a-3eae-4637-826b-ab4ec35ba1e1.png">
<img height=20% width=80% src="https://github.com/vikashsenthil21/-EXPERIMENT--03-INTERFACING-A-SOIL-MOISTURE-SENSOR-AND-CONFIGURING-THE-OUTPUT-THROUGH-USART--USING-/assets/119433834/ca7aa6af-2287-4fec-8711-1f35ffe5532e">

<img height=30% width=80% src="https://user-images.githubusercontent.com/36288975/234776631-d6a84ef4-904c-4eac-98ed-ab6253e9379c.png">

  
8.click on cntrl+S , automaticall C program will be generated 
<img height=30% width=40% src="https://user-images.githubusercontent.com/36288975/226189443-8b43451d-0b14-47e4-a20b-cc09c6ad8458.png">
<img height=50% width=80% src="https://user-images.githubusercontent.com/36288975/226189450-85ffa969-2ffb-4788-81e5-72d60fdda0f1.png">
``
9. edit the program and as per required 
``
![226189461-a573e62f-a109-4631-a250-a20925758fe0](https://github.com/vikashsenthil21/-EXPERIMENT--03-INTERFACING-A-SOIL-MOISTURE-SENSOR-AND-CONFIGURING-THE-OUTPUT-THROUGH-USART--USING-/assets/119433834/e1606415-750d-4892-88ce-c613dddb367e)


10. use project and build all 
<img height=30% width=40% src="https://user-images.githubusercontent.com/36288975/226189554-3f7101ac-3f41-48fc-abc7-480bd6218dec.png">
11. once the project is bulild 
<img height=30% width=40% src="https://user-images.githubusercontent.com/36288975/226189577-c61cc1eb-3990-4968-8aa6-aefffc766b70.png">

12. click on debug option 
<img height=30% width=40% src="https://user-images.githubusercontent.com/36288975/226189625-37daa9a3-62e9-42b5-a5ce-2ac63345905b.png">

13. connect the  ARM board to power supply and usb 


14. check for execution of the output using run option 



## STM 32 CUBE PROGRAM :
```
#include "main.h"
#include "stdio.h"
#if defined (__ICCARM__) || defined (__ARMCC_VERSION)
#define PUTCHAR_PROTOTYPE int fputc(int ch, FILE *f)
#elif defined(__GNUC__)

#define PUTCHAR_PROTOTYPE int __io_putchar(int ch)
#endif /* __ICCARM__ || __ARMCC_VERSION */

void SystemClock_Config(void);
static void MX_GPIO_Init(void);
static void MX_USART2_UART_Init(void);

int main(void)
{
  HAL_Init();
  SystemClock_Config();
  MX_GPIO_Init();
  MX_USART2_UART_Init();

  while (1)
  {
	  printf("VIKASH S\n");
	  HAL_Delay(500);

  }
 
}
PUTCHAR_PROTOTYPE
{

  HAL_UART_Transmit(&huart2, (uint8_t *)&ch, 1, 0xFFFF);

  return ch;
}






```


## Output screen shots of Serial port utility   :

<img height=30% width=40% src="https://github.com/vikashsenthil21/-EXPERIMENT--03-INTERFACING-A-SOIL-MOISTURE-SENSOR-AND-CONFIGURING-THE-OUTPUT-THROUGH-USART--USING-/assets/119433834/f2abfb4b-3e08-48bc-9702-c85edd434442">

## Result :
Interfacing a digital Input (Pushbutton ) with ARM microcontroller based IOT development is executed and the results are verified.
