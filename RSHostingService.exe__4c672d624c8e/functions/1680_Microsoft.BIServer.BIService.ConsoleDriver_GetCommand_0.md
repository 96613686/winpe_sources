# Microsoft.BIServer.BIService.ConsoleDriver::GetCommand_0

- ea: `0x1680`
- end: `0x1696`
- name: `Microsoft.BIServer.BIService.ConsoleDriver::GetCommand_0`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1520`
- `0x1670`

## pseudocode

```c

```

## disassembly

```asm
0x1680  call     string [mscorlib]System.Console::ReadLine()
0x1685  ldc.i4.1
0x1686  newarr   [mscorlib]System.Char
0x168b  dup
0x168c  ldc.i4.0
0x168d  ldc.i4.s 0x20
0x168f  stelem.i2
0x1690  callvirt instance string [mscorlib]System.String::Trim(char[])
0x1695  ret
```
