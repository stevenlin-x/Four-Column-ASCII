# Four Column ASCII Table:

Notes:

* In a four column ASCII table, the 32 characters on the first column of the table don't represent a written symbol: these characters such as Backspace, Newline, Escape, etc. are called control characters.

* In the terminal, you can type these control characters by holding the `CTRL` key in combination with another key (mnemonic: use a `CTRL` key combination for control characters).

    * In the VIM editor, for example, pressing `CTRL + [` in the terminal (which is `^[` in caret notation) is the same as pressing the `ESC` key. The character `[` and `ESC` are on the same row in a four column ASCII table (fifth row from bottom).

    * You might be wondering why pressing `CTRL + [` yields `ESC` and not other characters on the same row such as `;` and `{`. That's because pressing `CTRL` simply sets all bits but the last 5 to zero in the 7 bit ASCII for the character that you typed (i.e. the first two bits is set to zero and the last 5 bits remain the same). In essence, the `CTRL` character serves as the "bitwise AND": the result is 1 only if both operands are 1.

        ```
          10 11011 ([)
        & 00 11111 (CTRL)
        = 00 11011 (ESC)
        ```

* When the ASCII table is printed in rows of 32, looking up data becomes easier:

    * Upper case and lower case alphabet differs by only a single bit (e.g. 10 00001 => A and 11 00001 => a).

    * The character for the `CTRL` keyboard combination and the corresponding control character all exists on the same row. For example, the key combination `CTRL + [` corresponds to `ESC` in the same row (fifth row from bottom).

ASCII is a 7 bit encoding:

* The first two bits denote the group of the character (2^2 so 4 possible values)

* The remaining five bits describe a character (2^5 so 32 possible values)

| 00 | 01 | 10 | 11 |    |
| --- | --- | --- | --- | --- |
| NUL | Spc | @ | ` | 00000 |
| SOH | ! | A | a | 00001 |
| STX | " | B | b | 00010 |
| ETX | # | C | c | 00011 |
| EOT | $ | D | d | 00100 |
| ENQ | % | E | e | 00101 |
| ACK | & | F | f | 00110 |
| BEL | ' | G | g | 00111 |
| BS | ( | H | h | 01000 |
| TAB | ) | I | i | 01001 |
| LF | * | J | j | 01010 |
| VT | + | K | k | 01011 |
| FF | , | L | L | 01100 |
| CR | - | M | m | 01101 |
| SO | . | N | n | 01110 |
| SI | / | O | o | 01111 |
| DLE | 0 | P | p | 10000 |
| DC1 | 1 | Q | q | 10001 |
| DC2 | 2 | R | r | 10010 |
| DC3 | 3 | S | s | 10011 |
| DC4 | 4 | T | t | 10100 |
| NAK | 5 | U | u | 10101 |
| SYN | 6 | V | v | 10110 |
| ETB | 7 | W | w | 10111 |
| CAN | 8 | X | x | 11000 |
| EM | 9 | Y | y | 11001 |
| SUB |: |Z | z | 11010 |
| ESC | ; | [ | { | 11011 |
| FS | < | \ | \| | 11100 |
| GS | = | ] | } | 11101 |
| RS | > | ^ | ~ | 11110 |
| US | ? | _ | DEL | 11111 |

## References

1. [Four Column ASCII](https://garbagecollected.org/2017/01/31/four-column-ascii/)