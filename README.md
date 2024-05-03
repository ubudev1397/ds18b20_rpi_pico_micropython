Overview of the Scripts

    i2c_lcd.py
        This script provides an implementation for controlling an HD44780 character LCD via an I2C interface, using a PCF8574 I/O expander.
        It includes a class, I2cLcd, that inherits from LcdApi in lcd_api.py.
        The class offers methods for configuring and interacting with the LCD. This includes setting text, controlling the cursor, and enabling/disabling the backlight.
        The script demonstrates a microcontroller-based setup where the LCD is controlled over the I2C bus using specific bit manipulations.

    lcd_api.py
        This script provides a general API for controlling an HD44780 LCD.
        The class LcdApi offers an interface for interacting with the LCD display, including methods for clearing the screen, moving the cursor, and writing data.
        The actual implementation of lower-level functions, such as hal_write_command and hal_write_data, is expected to be provided by a derived class. This makes it a base class for other more specific implementations like I2cLcd.

    main.py
        This script serves as the main entry point, setting up and using the LCD and temperature sensor.
        It initializes the I2C bus and creates an instance of I2cLcd.
        The script then displays a static message on the LCD and reads temperature data from a DS18B20 sensor connected via the 1-Wire protocol.
        The temperature is then displayed on the LCD in a loop, continuously updating the screen.

How to Run and Test

To run and test this code on a Raspberry Pi Pico (or similar device):

    Set Up the Environment:
        Ensure you have MicroPython installed on your Raspberry Pi Pico. You can use tools like Thonny or uPyCraft to interface with your device.
        Make sure the necessary hardware (LCD display and DS18B20 sensor) is connected to the correct pins as specified in main.py.

    Upload the Files:
        Upload the scripts (i2c_lcd.py, lcd_api.py, main.py) to your Raspberry Pi Pico.

    Run the Code:
        Execute the main.py script to start the program.
        Monitor the output on the LCD and verify the temperature readings.

    Debug:
        If you encounter issues, you can insert print statements to debug.
        Ensure the I2C address and pin configurations match your hardware setup.

    Modify:
        You can customize the displayed text or make changes to how the temperature is shown. Adjust the code in main.py as needed.
