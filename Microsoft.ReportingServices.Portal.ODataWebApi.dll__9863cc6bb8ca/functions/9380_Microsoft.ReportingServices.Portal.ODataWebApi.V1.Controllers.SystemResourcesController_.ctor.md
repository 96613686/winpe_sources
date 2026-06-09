# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SystemResourcesController::.ctor

- ea: `0x9380`
- end: `0x93b2`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SystemResourcesController::.ctor`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5f80`

## callees

- `0x9380`

## string_xrefs

- `0x938a`: `systemResourceService`

## pseudocode

```c

```

## disassembly

```asm
0x9380  ldarg.0
0x9381  ldarg.2
0x9382  call     instance void class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.SystemResource>::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x9387  ldarg.1
0x9388  brtrue.s loc_9395
0x938a  ldstr    aSystemresource_1// "systemResourceService"
0x938f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9394  throw
0x9395  ldarg.2
0x9396  brtrue.s loc_93A3
0x9398  ldstr    aLogger// "logger"
0x939d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x93a2  throw
0x93a3  ldarg.0
0x93a4  ldarg.1
0x93a5  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.ISystemResourceService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SystemResourcesController::_systemResourceService
0x93aa  ldarg.0
0x93ab  ldarg.2
0x93ac  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.SystemResourcesController::_logger
0x93b1  ret
```
