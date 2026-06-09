# Microsoft.BIServer.BIService.ConsoleDriver::ListCmd

- ea: `0x16a0`
- end: `0x16d7`
- name: `Microsoft.BIServer.BIService.ConsoleDriver::ListCmd`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1520`

## callees

- `0xb00`
- `0x1620`
- `0x16a0`
- `0x1920`
- `0x1970`

## pseudocode

```c

```

## disassembly

```asm
0x16a0  ldstr    aProcessNames// "process names"
0x16a5  ldstr    aList// "list"
0x16aa  call     string[] Microsoft.BIServer.BIService.ConsoleDriver::GetParameters(string param, string action)
0x16af  stloc.0
0x16b0  ldloc.0
0x16b1  ldlen
0x16b2  brtrue.s loc_16C5
0x16b4  ldarg.0
0x16b5  ldfld    class Microsoft.BIServer.BIService.BIService Microsoft.BIServer.BIService.ConsoleDriver::_service
0x16ba  callvirt instance class Microsoft.BIServer.BIService.ManagedProcesses Microsoft.BIServer.BIService.BIService::get_ManagedProcesses()
0x16bf  callvirt instance void Microsoft.BIServer.BIService.ManagedProcesses::ListAllProcesses()
0x16c4  ret
0x16c5  ldarg.0
0x16c6  ldfld    class Microsoft.BIServer.BIService.BIService Microsoft.BIServer.BIService.ConsoleDriver::_service
0x16cb  callvirt instance class Microsoft.BIServer.BIService.ManagedProcesses Microsoft.BIServer.BIService.BIService::get_ManagedProcesses()
0x16d0  ldloc.0
0x16d1  callvirt instance void Microsoft.BIServer.BIService.ManagedProcesses::ListSpecifiedProcesses(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> tokens)
0x16d6  ret
```
