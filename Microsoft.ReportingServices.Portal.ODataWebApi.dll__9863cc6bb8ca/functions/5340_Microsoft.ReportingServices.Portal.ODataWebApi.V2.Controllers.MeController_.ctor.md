# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.MeController::.ctor

- ea: `0x5340`
- end: `0x5362`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.MeController::.ctor`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x7270`
- `0x7280`
- `0x7290`

## pseudocode

```c

```

## disassembly

```asm
0x5340  ldarg.0
0x5341  ldarg.1
0x5342  ldarg.2
0x5343  ldarg.3
0x5344  call     instance void Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.MeController::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository catalogRepository, class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IUserInfoService userInfoService)
0x5349  ldarg.0
0x534a  ldarg.0
0x534b  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.MeController::get_CatalogRepository()
0x5350  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.MeController::_catalogRepository
0x5355  ldarg.0
0x5356  ldarg.0
0x5357  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IUserInfoService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.MeController::get_UserInfoService()
0x535c  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IUserInfoService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.MeController::_userInfoService
0x5361  ret
```
