# Microsoft.BIServer.BIService.ManagedProcess::get_IsManagementProcess

- ea: `0x1be0`
- end: `0x1be7`
- name: `Microsoft.BIServer.BIService.ManagedProcess::get_IsManagementProcess`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800`
- `0x1850`

## pseudocode

```c

```

## disassembly

```asm
0x1be0  ldarg.0
0x1be1  ldfld    bool Microsoft.BIServer.BIService.ManagedProcess::_isManagementProcess
0x1be6  ret
```
