<img width="300" alt="Logo (4)" src="https://github.com/user-attachments/assets/a8c3e7ef-c88a-4c7a-8d6c-3ff36cd6a040" />

# bProg

bProg (byte Program interpreter) is a programming interpreter for ByteOS. It currently features semicolon support and the ability to execute byteOS commands. It can also output to USART/UART in normal or loop mode.

Functions:

bProg has three functions as of right now.

**output(uart)** - Outputs text to USART/UART. 
<br>
Example, in file `hello.bp`:
<br>
`output(uart) hi`
<br>
This outputs `hi` into USART/UART.

**output(uart, loop)** - Outputs text to USART/UART in a breakable loop.
<br>
Example, in file `hello.bp`:
<br>
`output(uart, loop) hi`
<br>
This outputs `hi` every time you press enter, until you type exit and press enter into USART/UART.

**execute(commands)** - Executes ByteOS commands
<br>
Example, in file `echo.bp`:
<br>
`execute(commands) echo hi`
<br>
This executes `echo hi`, outputting `hi`.

That is all of the functions.

As mentioned before, bProg supports semicolons.
<br>
Example, in file `echo.bp`:
<br>
`execute(commands) echo hi;output(uart) bye`
<br>
This executes `echo hi`, outputting `hi` and also outputs `bye` to USART/UART.

There is also one quirk, you must not use a space after a semicolon. 

This will work:
<br>
`execute(commands) echo hi;output(uart) bye`

This will not:
<br>
`execute(commands) echo hi; output(uart) bye`

This is because, instead of running `echo hi` and `output(uart) bye`, it will run `echo hi` and ` output(uart) bye` with a space at the start.
