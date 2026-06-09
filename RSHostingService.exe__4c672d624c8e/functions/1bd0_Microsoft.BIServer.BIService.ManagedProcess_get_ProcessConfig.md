# Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig

- ea: `0x1bd0`
- end: `0x1bd7`
- name: `Microsoft.BIServer.BIService.ManagedProcess::get_ProcessConfig`
- size: `7`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xce0`
- `0x19d0`
- `0x1c50`
- `0x1de0`
- `0x1f10`
- `0x2000`
- `0x3a90`

## pseudocode

```c

```

## disassembly

```asm
0x1bd0  ldarg.0
0x1bd1  ldfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ManagedProcess::_processConfig
0x1bd6  ret
```
