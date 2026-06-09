# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::.ctor

- ea: `0x8d70`
- end: `0x8db7`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::.ctor`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x8d70`

## string_xrefs

- `0x8d7a`: `systemService`
- `0x8d88`: `portalConfigurationManager`

## pseudocode

```c

```

## disassembly

```asm
0x8d70  ldarg.0
0x8d71  ldarg.1
0x8d72  call     instance void class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.SingletonReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportServerInfo>::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x8d77  ldarg.2
0x8d78  brtrue.s loc_8D85
0x8d7a  ldstr    aSystemservice// "systemService"
0x8d7f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8d84  throw
0x8d85  ldarg.3
0x8d86  brtrue.s loc_8D93
0x8d88  ldstr    aPortalconfigur// "portalConfigurationManager"
0x8d8d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8d92  throw
0x8d93  ldarg.1
0x8d94  brtrue.s loc_8DA1
0x8d96  ldstr    aLogger// "logger"
0x8d9b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8da0  throw
0x8da1  ldarg.0
0x8da2  ldarg.2
0x8da3  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::_systemService
0x8da8  ldarg.0
0x8da9  ldarg.3
0x8daa  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::_portalConfigurationManager
0x8daf  ldarg.0
0x8db0  ldarg.1
0x8db1  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.ReportServerInfoController::_logger
0x8db6  ret
```
