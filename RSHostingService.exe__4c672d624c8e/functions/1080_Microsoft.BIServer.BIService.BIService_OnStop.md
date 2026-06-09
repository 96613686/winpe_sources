# Microsoft.BIServer.BIService.BIService::OnStop

- ea: `0x1080`
- end: `0x1092`
- name: `Microsoft.BIServer.BIService.BIService::OnStop`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xbe0`
- `0x18e0`

## pseudocode

```c

```

## disassembly

```asm
0x1080  ldarg.0
0x1081  call     instance void Microsoft.BIServer.BIService.BIService::StopServiceWatchdog()
0x1086  ldarg.0
0x1087  ldfld    class Microsoft.BIServer.BIService.ManagedProcesses Microsoft.BIServer.BIService.BIService::_managedProcesses
0x108c  callvirt instance void Microsoft.BIServer.BIService.ManagedProcesses::StopProcesses()
0x1091  ret
```
