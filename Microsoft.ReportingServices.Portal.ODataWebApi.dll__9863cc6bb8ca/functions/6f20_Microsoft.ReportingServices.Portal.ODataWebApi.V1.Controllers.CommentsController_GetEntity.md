# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::GetEntity

- ea: `0x6f20`
- end: `0x6f4a`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::GetEntity`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3120`

## callees

- `0x6f20`

## pseudocode

```c

```

## disassembly

```asm
0x6f20  ldarg.1
0x6f21  call     int64 [mscorlib]System.Int64::Parse(string)
0x6f26  stloc.0
0x6f27  ldarg.0
0x6f28  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::_catalogRepository
0x6f2d  ldarg.0
0x6f2e  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x6f33  ldloc.0
0x6f34  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetComment(class [mscorlib]System.Security.Principal.IPrincipal, int64)
0x6f39  stloc.1
0x6f3a  leave.s  loc_6F48
0x6f3c  pop
0x6f3d  ldc.i4   0x193
0x6f42  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x6f47  throw
0x6f48  ldloc.1
0x6f49  ret
```
