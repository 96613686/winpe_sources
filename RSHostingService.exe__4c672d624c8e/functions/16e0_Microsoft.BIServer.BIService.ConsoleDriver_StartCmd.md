# Microsoft.BIServer.BIService.ConsoleDriver::StartCmd

- ea: `0x16e0`
- end: `0x16f8`
- name: `Microsoft.BIServer.BIService.ConsoleDriver::StartCmd`
- size: `24`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1520`

## callees

- `0x1620`
- `0x1700`

## pseudocode

```c

```

## disassembly

```asm
0x16e0  ldstr    aProcessNames// "process names"
0x16e5  ldstr    aStart// "start"
0x16ea  call     string[] Microsoft.BIServer.BIService.ConsoleDriver::GetParameters(string param, string action)
0x16ef  stloc.0
0x16f0  ldarg.0
0x16f1  ldloc.0
0x16f2  call     instance void Microsoft.BIServer.BIService.ConsoleDriver::DoStart(string[] names)
0x16f7  ret
```
