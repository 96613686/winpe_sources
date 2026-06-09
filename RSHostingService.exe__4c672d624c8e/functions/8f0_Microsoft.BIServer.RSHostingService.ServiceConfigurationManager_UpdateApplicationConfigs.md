# Microsoft.BIServer.RSHostingService.ServiceConfigurationManager::UpdateApplicationConfigs

- ea: `0x8f0`
- end: `0x919`
- name: `Microsoft.BIServer.RSHostingService.ServiceConfigurationManager::UpdateApplicationConfigs`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xb80`

## callees

- `0x8f0`
- `0x920`

## string_xrefs

- `0x8f0`: `Updating application config files`
- `0x907`: `Error syncing configuration`

## pseudocode

```c

```

## disassembly

```asm
0x8f0  ldstr    aUpdatingApplic// "Updating application config files"
0x8f5  call     T0x2B000001
0x8fa  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x8ff  ldarg.0
0x900  call     instance void Microsoft.BIServer.RSHostingService.ServiceConfigurationManager::SyncMachineKey()
0x905  leave.s  loc_918
0x907  ldstr    aErrorSyncingCo// "Error syncing configuration"
0x90c  call     T0x2B000001
0x911  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(class [mscorlib]System.Exception, string, object[])
0x916  leave.s  loc_918
0x918  ret
```
