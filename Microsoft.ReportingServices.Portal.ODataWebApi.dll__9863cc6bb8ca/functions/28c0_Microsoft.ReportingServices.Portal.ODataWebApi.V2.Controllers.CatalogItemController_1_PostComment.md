# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1::PostComment

- ea: `0x28c0`
- end: `0x2938`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1::PostComment`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x28c0`

## string_xrefs

- `0x28e7`: `User {0} doesn't have permission to write comments on an item they don't have permissions to view ({1}).`

## pseudocode

```c

```

## disassembly

```asm
0x28c0  ldarg.0
0x28c1  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::_catalogRepository
0x28c6  ldarg.0
0x28c7  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x28cc  ldarg.2
0x28cd  ldloca.s 0
0x28cf  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::CreateComment(class [mscorlib]System.Security.Principal.IPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment&)
0x28d4  pop
0x28d5  ldarg.0
0x28d6  ldloc.0
0x28d7  callvirt T0x2B00004A
0x28dc  stloc.1
0x28dd  leave.s  loc_2936
0x28df  pop
0x28e0  ldarg.0
0x28e1  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::_logger
0x28e6  ldc.i4.3
0x28e7  ldstr    aUser0DoesnTHav_1// "User {0} doesn't have permission to wri"...
0x28ec  ldarg.0
0x28ed  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x28f2  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x28f7  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x28fc  ldarg.1
0x28fd  call     string [mscorlib]System.String::Format(string, object, object)
0x2902  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x2907  ldc.i4   0x193
0x290c  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x2911  throw
0x2912  pop
0x2913  ldc.i4   0x194
0x2918  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x291d  throw
0x291e  pop
0x291f  ldc.i4   0x190
0x2924  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x2929  throw
0x292a  pop
0x292b  ldc.i4   0x190
0x2930  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x2935  throw
0x2936  ldloc.1
0x2937  ret
```
