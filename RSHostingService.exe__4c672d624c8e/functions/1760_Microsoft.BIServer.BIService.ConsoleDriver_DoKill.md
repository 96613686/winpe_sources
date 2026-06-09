# Microsoft.BIServer.BIService.ConsoleDriver::DoKill

- ea: `0x1760`
- end: `0x179b`
- name: `Microsoft.BIServer.BIService.ConsoleDriver::DoKill`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1740`
- `0x17a0`

## callees

- `0xb00`
- `0x1760`
- `0x18e0`
- `0x1a20`

## pseudocode

```c

```

## disassembly

```asm
0x1760  ldarg.1
0x1761  ldlen
0x1762  brtrue.s loc_1775
0x1764  ldarg.0
0x1765  ldfld    class Microsoft.BIServer.BIService.BIService Microsoft.BIServer.BIService.ConsoleDriver::_service
0x176a  callvirt instance class Microsoft.BIServer.BIService.ManagedProcesses Microsoft.BIServer.BIService.BIService::get_ManagedProcesses()
0x176f  callvirt instance void Microsoft.BIServer.BIService.ManagedProcesses::StopProcesses()
0x1774  ret
0x1775  ldarg.1
0x1776  stloc.0
0x1777  ldc.i4.0
0x1778  stloc.1
0x1779  br.s     loc_1794
0x177b  ldloc.0
0x177c  ldloc.1
0x177d  ldelem.ref
0x177e  stloc.2
0x177f  ldarg.0
0x1780  ldfld    class Microsoft.BIServer.BIService.BIService Microsoft.BIServer.BIService.ConsoleDriver::_service
0x1785  callvirt instance class Microsoft.BIServer.BIService.ManagedProcesses Microsoft.BIServer.BIService.BIService::get_ManagedProcesses()
0x178a  ldloc.2
0x178b  callvirt instance void Microsoft.BIServer.BIService.ManagedProcesses::StopProcessByName(string procName)
0x1790  ldloc.1
0x1791  ldc.i4.1
0x1792  add
0x1793  stloc.1
0x1794  ldloc.1
0x1795  ldloc.0
0x1796  ldlen
0x1797  conv.i4
0x1798  blt.s    loc_177B
0x179a  ret
```
