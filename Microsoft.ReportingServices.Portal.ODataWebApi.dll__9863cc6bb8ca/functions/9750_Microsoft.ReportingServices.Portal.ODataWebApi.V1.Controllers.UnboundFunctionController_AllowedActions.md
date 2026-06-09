# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::AllowedActions

- ea: `0x9750`
- end: `0x9774`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::AllowedActions`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6120`

## callees

- `0x9990`

## pseudocode

```c

```

## disassembly

```asm
0x9750  ldarg.0
0x9751  ldarg.1
0x9752  call     instance string Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::CleanPath(string path)
0x9757  starg.s  1
0x9759  ldarg.0
0x975a  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::_catalogRepository
0x975f  ldarg.0
0x9760  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x9765  ldarg.1
0x9766  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetAllowedActions(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x976b  stloc.0
0x976c  ldarg.0
0x976d  ldloc.0
0x976e  callvirt T0x2B0000D6
0x9773  ret
```
