# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::PutEntity

- ea: `0x6fd0`
- end: `0x7025`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::PutEntity`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3150`

## callees

- `0x6fd0`

## pseudocode

```c

```

## disassembly

```asm
0x6fd0  ldarg.2
0x6fd1  ldarg.1
0x6fd2  call     int64 [mscorlib]System.Int64::Parse(string)
0x6fd7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::set_Id(int64)
0x6fdc  ldarg.0
0x6fdd  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::_catalogRepository
0x6fe2  ldarg.0
0x6fe3  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x6fe8  ldarg.2
0x6fe9  callvirt instance int64 [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_Id()
0x6fee  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::IsUserContextOwner(class [mscorlib]System.Security.Principal.IPrincipal, int64)
0x6ff3  brtrue.s loc_7000
0x6ff5  ldc.i4   0x193
0x6ffa  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x6fff  throw
0x7000  nop
0x7001  ldarg.0
0x7002  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::_catalogRepository
0x7007  ldarg.0
0x7008  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x700d  ldarg.2
0x700e  ldnull
0x700f  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::UpdateComment(class [mscorlib]System.Security.Principal.IPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment, string[])
0x7014  stloc.0
0x7015  leave.s  loc_7023
0x7017  pop
0x7018  ldc.i4   0x193
0x701d  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x7022  throw
0x7023  ldloc.0
0x7024  ret
```
