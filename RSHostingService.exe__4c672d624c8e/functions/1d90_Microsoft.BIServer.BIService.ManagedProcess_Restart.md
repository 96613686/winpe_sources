# Microsoft.BIServer.BIService.ManagedProcess::Restart

- ea: `0x1d90`
- end: `0x1d97`
- name: `Microsoft.BIServer.BIService.ManagedProcess::Restart`
- size: `7`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1de0`

## pseudocode

```c

```

## disassembly

```asm
0x1d90  ldarg.0
0x1d91  call     instance void Microsoft.BIServer.BIService.ManagedProcess::Kill()
0x1d96  ret
```
