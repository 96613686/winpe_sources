# Microsoft.BIServer.BIService.BIService::get_ManagedProcesses

- ea: `0xb00`
- end: `0xb07`
- name: `Microsoft.BIServer.BIService.BIService::get_ManagedProcesses`
- size: `7`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x16a0`
- `0x1700`
- `0x1760`

## pseudocode

```c

```

## disassembly

```asm
0xb00  ldarg.0
0xb01  ldfld    class Microsoft.BIServer.BIService.ManagedProcesses Microsoft.BIServer.BIService.BIService::_managedProcesses
0xb06  ret
```
