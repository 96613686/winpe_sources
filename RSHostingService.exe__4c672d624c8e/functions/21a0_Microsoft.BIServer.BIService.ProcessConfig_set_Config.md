# Microsoft.BIServer.BIService.ProcessConfig::set_Config

- ea: `0x21a0`
- end: `0x21a8`
- name: `Microsoft.BIServer.BIService.ProcessConfig::set_Config`
- size: `8`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xce0`
- `0x10e0`
- `0x20b0`
- `0x3390`

## pseudocode

```c

```

## disassembly

```asm
0x21a0  ldarg.0
0x21a1  ldarg.1
0x21a2  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::<Config>k__BackingField
0x21a7  ret
```
