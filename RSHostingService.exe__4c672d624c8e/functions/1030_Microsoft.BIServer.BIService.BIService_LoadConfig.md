# Microsoft.BIServer.BIService.BIService::LoadConfig

- ea: `0x1030`
- end: `0x103f`
- name: `Microsoft.BIServer.BIService.BIService::LoadConfig`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2ea0`

## callees

- `0x330`
- `0x360`
- `0x1030`

## pseudocode

```c

```

## disassembly

```asm
0x1030  call     bool Microsoft.BIServer.RSHostingService.RsTraceConfig::ValidateTraceConfigFileExists()
0x1035  brtrue.s loc_1039
0x1037  ldnull
0x1038  ret
0x1039  call     class Microsoft.BIServer.RSHostingService.RsTraceConfig Microsoft.BIServer.RSHostingService.RsTraceConfig::LoadFromFile()
0x103e  ret
```
