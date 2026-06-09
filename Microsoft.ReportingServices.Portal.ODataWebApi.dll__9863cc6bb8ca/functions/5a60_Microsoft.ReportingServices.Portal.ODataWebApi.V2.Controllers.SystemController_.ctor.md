# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SystemController::.ctor

- ea: `0x5a60`
- end: `0x5aa7`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SystemController::.ctor`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5a60`

## string_xrefs

- `0x5a6a`: `systemService`
- `0x5a78`: `portalConfigurationManager`

## pseudocode

```c

```

## disassembly

```asm
0x5a60  ldarg.0
0x5a61  ldarg.1
0x5a62  call     instance void class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.SingletonReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.System>::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x5a67  ldarg.2
0x5a68  brtrue.s loc_5A75
0x5a6a  ldstr    aSystemservice// "systemService"
0x5a6f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5a74  throw
0x5a75  ldarg.3
0x5a76  brtrue.s loc_5A83
0x5a78  ldstr    aPortalconfigur// "portalConfigurationManager"
0x5a7d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5a82  throw
0x5a83  ldarg.1
0x5a84  brtrue.s loc_5A91
0x5a86  ldstr    aLogger// "logger"
0x5a8b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5a90  throw
0x5a91  ldarg.0
0x5a92  ldarg.2
0x5a93  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SystemController::_systemService
0x5a98  ldarg.0
0x5a99  ldarg.3
0x5a9a  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SystemController::_portalConfigurationManager
0x5a9f  ldarg.0
0x5aa0  ldarg.1
0x5aa1  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SystemController::_logger
0x5aa6  ret
```
