# Microsoft.BIServer.BIService.ConsoleDriver::DoStart

- ea: `0x1700`
- end: `0x173b`
- name: `Microsoft.BIServer.BIService.ConsoleDriver::DoStart`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x16e0`
- `0x17a0`

## callees

- `0xb00`
- `0x1700`
- `0x18a0`
- `0x19f0`

## pseudocode

```c

```

## disassembly

```asm
0x1700  ldarg.1
0x1701  ldlen
0x1702  brtrue.s loc_1715
0x1704  ldarg.0
0x1705  ldfld    class Microsoft.BIServer.BIService.BIService Microsoft.BIServer.BIService.ConsoleDriver::_service
0x170a  callvirt instance class Microsoft.BIServer.BIService.ManagedProcesses Microsoft.BIServer.BIService.BIService::get_ManagedProcesses()
0x170f  callvirt instance void Microsoft.BIServer.BIService.ManagedProcesses::ThrottledStartProcesses()
0x1714  ret
0x1715  ldarg.1
0x1716  stloc.0
0x1717  ldc.i4.0
0x1718  stloc.1
0x1719  br.s     loc_1734
0x171b  ldloc.0
0x171c  ldloc.1
0x171d  ldelem.ref
0x171e  stloc.2
0x171f  ldarg.0
0x1720  ldfld    class Microsoft.BIServer.BIService.BIService Microsoft.BIServer.BIService.ConsoleDriver::_service
0x1725  callvirt instance class Microsoft.BIServer.BIService.ManagedProcesses Microsoft.BIServer.BIService.BIService::get_ManagedProcesses()
0x172a  ldloc.2
0x172b  callvirt instance void Microsoft.BIServer.BIService.ManagedProcesses::StartProcessByName(string procName)
0x1730  ldloc.1
0x1731  ldc.i4.1
0x1732  add
0x1733  stloc.1
0x1734  ldloc.1
0x1735  ldloc.0
0x1736  ldlen
0x1737  conv.i4
0x1738  blt.s    loc_171B
0x173a  ret
```
