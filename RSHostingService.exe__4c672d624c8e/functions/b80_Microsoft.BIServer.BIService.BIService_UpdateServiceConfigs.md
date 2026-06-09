# Microsoft.BIServer.BIService.BIService::UpdateServiceConfigs

- ea: `0xb80`
- end: `0xba1`
- name: `Microsoft.BIServer.BIService.BIService::UpdateServiceConfigs`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x2dd0`

## callees

- `0x190`
- `0x1a0`
- `0x8e0`
- `0x8f0`

## pseudocode

```c

```

## disassembly

```asm
0xb80  ldarg.0
0xb81  ldfld    class Microsoft.BIServer.BIService.ServiceConfig Microsoft.BIServer.BIService.BIService::_serviceConfig
0xb86  newobj   instance void Microsoft.BIServer.RSHostingService.ServiceConfigurationManager::.ctor(class Microsoft.BIServer.BIService.ServiceConfig serviceConfig)
0xb8b  callvirt instance void Microsoft.BIServer.RSHostingService.ServiceConfigurationManager::UpdateApplicationConfigs()
0xb90  ldarg.0
0xb91  ldfld    class Microsoft.BIServer.BIService.ServiceConfig Microsoft.BIServer.BIService.BIService::_serviceConfig
0xb96  newobj   instance void Microsoft.BIServer.RSHostingService.PolicyConfigurationManager::.ctor(class Microsoft.BIServer.BIService.ServiceConfig serviceConfig)
0xb9b  callvirt instance void Microsoft.BIServer.RSHostingService.PolicyConfigurationManager::Upgrade()
0xba0  ret
```
