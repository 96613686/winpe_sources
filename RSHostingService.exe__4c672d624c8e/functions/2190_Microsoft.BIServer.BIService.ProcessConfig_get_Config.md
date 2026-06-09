# Microsoft.BIServer.BIService.ProcessConfig::get_Config

- ea: `0x2190`
- end: `0x2197`
- name: `Microsoft.BIServer.BIService.ProcessConfig::get_Config`
- size: `7`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xe50`
- `0xfd0`
- `0x10e0`
- `0x1c50`
- `0x2860`
- `0x2970`
- `0x2b00`
- `0x3390`

## pseudocode

```c

```

## disassembly

```asm
0x2190  ldarg.0
0x2191  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::<Config>k__BackingField
0x2196  ret
```
