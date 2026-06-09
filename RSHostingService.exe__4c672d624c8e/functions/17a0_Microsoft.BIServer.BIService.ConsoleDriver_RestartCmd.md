# Microsoft.BIServer.BIService.ConsoleDriver::RestartCmd

- ea: `0x17a0`
- end: `0x17bf`
- name: `Microsoft.BIServer.BIService.ConsoleDriver::RestartCmd`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1520`

## callees

- `0x1620`
- `0x1700`
- `0x1760`

## pseudocode

```c

```

## disassembly

```asm
0x17a0  ldstr    aProcessNames// "process names"
0x17a5  ldstr    aKill// "kill"
0x17aa  call     string[] Microsoft.BIServer.BIService.ConsoleDriver::GetParameters(string param, string action)
0x17af  stloc.0
0x17b0  ldarg.0
0x17b1  ldloc.0
0x17b2  call     instance void Microsoft.BIServer.BIService.ConsoleDriver::DoKill(string[] names)
0x17b7  ldarg.0
0x17b8  ldloc.0
0x17b9  call     instance void Microsoft.BIServer.BIService.ConsoleDriver::DoStart(string[] names)
0x17be  ret
```
