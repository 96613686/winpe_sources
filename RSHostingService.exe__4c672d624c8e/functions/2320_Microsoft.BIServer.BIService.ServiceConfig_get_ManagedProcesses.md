# Microsoft.BIServer.BIService.ServiceConfig::get_ManagedProcesses

- ea: `0x2320`
- end: `0x2327`
- name: `Microsoft.BIServer.BIService.ServiceConfig::get_ManagedProcesses`
- size: `7`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1a0`
- `0x920`
- `0xe50`
- `0xfd0`
- `0x10e0`
- `0x3390`

## pseudocode

```c

```

## disassembly

```asm
0x2320  ldarg.0
0x2321  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.BIServer.BIService.ProcessConfig> Microsoft.BIServer.BIService.ServiceConfig::_managedProcesses
0x2326  ret
```
