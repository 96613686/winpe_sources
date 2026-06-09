# Microsoft.BIServer.BIService.ServiceConfig::get_ServiceProperties

- ea: `0x2350`
- end: `0x2357`
- name: `Microsoft.BIServer.BIService.ServiceConfig::get_ServiceProperties`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x10e0`
- `0x3390`

## pseudocode

```c

```

## disassembly

```asm
0x2350  ldarg.0
0x2351  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ServiceConfig::_serviceProperties
0x2356  ret
```
