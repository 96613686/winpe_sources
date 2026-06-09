# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.MeController::.ctor

- ea: `0x7290`
- end: `0x72c2`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.MeController::.ctor`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5340`

## callees

- `0x7290`

## string_xrefs

- `0x72a8`: `userInfoService`

## pseudocode

```c

```

## disassembly

```asm
0x7290  ldarg.0
0x7291  ldarg.1
0x7292  call     instance void class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.SingletonReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.User>::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger)
0x7297  ldarg.2
0x7298  brtrue.s loc_72A5
0x729a  ldstr    aCatalogreposit// "catalogRepository"
0x729f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x72a4  throw
0x72a5  ldarg.3
0x72a6  brtrue.s loc_72B3
0x72a8  ldstr    aUserinfoservic// "userInfoService"
0x72ad  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x72b2  throw
0x72b3  ldarg.0
0x72b4  ldarg.3
0x72b5  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IUserInfoService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.MeController::_userInfoService
0x72ba  ldarg.0
0x72bb  ldarg.2
0x72bc  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.MeController::_catalogRepository
0x72c1  ret
```
