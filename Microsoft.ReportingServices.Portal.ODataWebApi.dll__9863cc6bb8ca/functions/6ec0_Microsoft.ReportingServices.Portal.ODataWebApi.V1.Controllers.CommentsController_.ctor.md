# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::.ctor

- ea: `0x6ec0`
- end: `0x6ef2`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::.ctor`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x30d0`

## callees

- `0x6ec0`

## pseudocode

```c

```

## disassembly

```asm
0x6ec0  ldarg.0
0x6ec1  ldarg.2
0x6ec2  call     instance void class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment>::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x6ec7  ldarg.1
0x6ec8  brtrue.s loc_6ED5
0x6eca  ldstr    aCatalogreposit// "catalogRepository"
0x6ecf  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6ed4  throw
0x6ed5  ldarg.2
0x6ed6  brtrue.s loc_6EE3
0x6ed8  ldstr    aLogger// "logger"
0x6edd  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6ee2  throw
0x6ee3  ldarg.0
0x6ee4  ldarg.1
0x6ee5  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::_catalogRepository
0x6eea  ldarg.0
0x6eeb  ldarg.2
0x6eec  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::_logger
0x6ef1  ret
```
