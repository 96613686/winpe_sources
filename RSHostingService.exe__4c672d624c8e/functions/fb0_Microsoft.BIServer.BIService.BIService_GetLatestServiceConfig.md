# Microsoft.BIServer.BIService.BIService::GetLatestServiceConfig

- ea: `0xfb0`
- end: `0xfd0`
- name: `Microsoft.BIServer.BIService.BIService::GetLatestServiceConfig`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3110`

## callees

- `0x10e0`
- `0x21c0`

## pseudocode

```c

```

## disassembly

```asm
0xfb0  call     class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::get_Current()
0xfb5  callvirt instance void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ConfigReader::ReloadCurrent()
0xfba  ldarg.0
0xfbb  ldfld    string Microsoft.BIServer.BIService.BIService::_serviceConfigFilePath
0xfc0  newobj   instance void Microsoft.BIServer.BIService.ServiceConfig::.ctor(string serviceConfigFilePath)
0xfc5  stloc.0
0xfc6  ldarg.0
0xfc7  ldloc.0
0xfc8  ldarg.1
0xfc9  call     instance void Microsoft.BIServer.BIService.BIService::UpdateManagedProcessConfigs(class Microsoft.BIServer.BIService.ServiceConfig serviceConfig, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState managementState)
0xfce  ldloc.0
0xfcf  ret
```
