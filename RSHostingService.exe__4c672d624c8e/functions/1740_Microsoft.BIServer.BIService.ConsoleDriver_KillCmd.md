# Microsoft.BIServer.BIService.ConsoleDriver::KillCmd

- ea: `0x1740`
- end: `0x1758`
- name: `Microsoft.BIServer.BIService.ConsoleDriver::KillCmd`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1520`

## callees

- `0x1620`
- `0x1760`

## pseudocode

```c

```

## disassembly

```asm
0x1740  ldstr    aProcessNames// "process names"
0x1745  ldstr    aKill// "kill"
0x174a  call     string[] Microsoft.BIServer.BIService.ConsoleDriver::GetParameters(string param, string action)
0x174f  stloc.0
0x1750  ldarg.0
0x1751  ldloc.0
0x1752  call     instance void Microsoft.BIServer.BIService.ConsoleDriver::DoKill(string[] names)
0x1757  ret
```
