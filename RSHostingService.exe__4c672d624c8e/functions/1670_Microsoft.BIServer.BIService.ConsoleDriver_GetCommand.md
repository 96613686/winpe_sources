# Microsoft.BIServer.BIService.ConsoleDriver::GetCommand

- ea: `0x1670`
- end: `0x167c`
- name: `Microsoft.BIServer.BIService.ConsoleDriver::GetCommand`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3970`

## callees

- `0x1680`

## pseudocode

```c

```

## disassembly

```asm
0x1670  ldarg.0
0x1671  call     void [mscorlib]System.Console::WriteLine(string)
0x1676  call     string Microsoft.BIServer.BIService.ConsoleDriver::GetCommand()
0x167b  ret
```
