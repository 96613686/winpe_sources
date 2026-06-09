# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::DeleteEntity

- ea: `0x7040`
- end: `0x7081`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::DeleteEntity`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3170`

## callees

- `0x7040`

## pseudocode

```c

```

## disassembly

```asm
0x7040  ldarg.1
0x7041  call     int64 [mscorlib]System.Int64::Parse(string)
0x7046  stloc.0
0x7047  ldarg.0
0x7048  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::_catalogRepository
0x704d  ldarg.0
0x704e  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x7053  ldloc.0
0x7054  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::IsUserContextOwner(class [mscorlib]System.Security.Principal.IPrincipal, int64)
0x7059  stloc.1
0x705a  ldarg.0
0x705b  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::_catalogRepository
0x7060  ldarg.0
0x7061  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x7066  ldloc.0
0x7067  ldloc.1
0x7068  ldc.i4.0
0x7069  ceq
0x706b  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::DeleteComment(class [mscorlib]System.Security.Principal.IPrincipal, int64, bool)
0x7070  stloc.2
0x7071  leave.s  loc_707F
0x7073  pop
0x7074  ldc.i4   0x193
0x7079  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x707e  throw
0x707f  ldloc.2
0x7080  ret
```
