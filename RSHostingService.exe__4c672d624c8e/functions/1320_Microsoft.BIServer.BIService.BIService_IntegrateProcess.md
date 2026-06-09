# Microsoft.BIServer.BIService.BIService::IntegrateProcess

- ea: `0x1320`
- end: `0x132d`
- name: `Microsoft.BIServer.BIService.BIService::IntegrateProcess`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3390`

## callees

- `0x19d0`

## pseudocode

```c

```

## disassembly

```asm
0x1320  ldarg.0
0x1321  ldfld    class Microsoft.BIServer.BIService.ManagedProcesses Microsoft.BIServer.BIService.BIService::_managedProcesses
0x1326  ldarg.1
0x1327  callvirt instance void Microsoft.BIServer.BIService.ManagedProcesses::Add(class Microsoft.BIServer.BIService.ManagedProcess workerProcess)
0x132c  ret
```
