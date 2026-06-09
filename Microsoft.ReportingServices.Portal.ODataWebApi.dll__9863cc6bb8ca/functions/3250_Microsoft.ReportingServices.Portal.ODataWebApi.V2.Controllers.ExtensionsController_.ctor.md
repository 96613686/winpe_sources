# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ExtensionsController::.ctor

- ea: `0x3250`
- end: `0x3282`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ExtensionsController::.ctor`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x3250`

## string_xrefs

- `0x325a`: `systemService`

## pseudocode

```c

```

## disassembly

```asm
0x3250  ldarg.0
0x3251  ldarg.2
0x3252  call     instance void class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Extension>::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x3257  ldarg.1
0x3258  brtrue.s loc_3265
0x325a  ldstr    aSystemservice// "systemService"
0x325f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3264  throw
0x3265  ldarg.2
0x3266  brtrue.s loc_3273
0x3268  ldstr    aLogger// "logger"
0x326d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3272  throw
0x3273  ldarg.0
0x3274  ldarg.1
0x3275  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ExtensionsController::_systemService
0x327a  ldarg.0
0x327b  ldarg.2
0x327c  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ExtensionsController::_logger
0x3281  ret
```
