# Microsoft.BIServer.RSHostingService.ServiceConfigurationManager::.ctor

- ea: `0x8e0`
- end: `0x8ee`
- name: `Microsoft.BIServer.RSHostingService.ServiceConfigurationManager::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xb80`

## pseudocode

```c

```

## disassembly

```asm
0x8e0  ldarg.0
0x8e1  call     instance void [mscorlib]System.Object::.ctor()
0x8e6  ldarg.0
0x8e7  ldarg.1
0x8e8  stfld    class Microsoft.BIServer.BIService.ServiceConfig Microsoft.BIServer.RSHostingService.ServiceConfigurationManager::serviceConfig
0x8ed  ret
```
