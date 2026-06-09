# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::AddEntity_0

- ea: `0x6f60`
- end: `0x6fcd`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::AddEntity_0`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3140`

## callees

- `0x6f60`

## string_xrefs

- `0x6f7e`: `User {0} doesn't have permission to write comments on an item they don't have permissions to view ({1}).`

## pseudocode

```c

```

## disassembly

```asm
0x6f60  ldarg.0
0x6f61  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::_catalogRepository
0x6f66  ldarg.0
0x6f67  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x6f6c  ldarg.1
0x6f6d  ldarg.2
0x6f6e  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::CreateComment(class [mscorlib]System.Security.Principal.IPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment, class [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment&)
0x6f73  stloc.0
0x6f74  leave.s  loc_6FCB
0x6f76  pop
0x6f77  ldarg.0
0x6f78  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CommentsController::_logger
0x6f7d  ldc.i4.3
0x6f7e  ldstr    aUser0DoesnTHav_1// "User {0} doesn't have permission to wri"...
0x6f83  ldarg.0
0x6f84  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x6f89  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x6f8e  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x6f93  ldarg.1
0x6f94  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.Comment::get_ItemId()
0x6f99  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x6f9e  call     string [mscorlib]System.String::Format(string, object, object)
0x6fa3  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x6fa8  ldc.i4   0x193
0x6fad  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x6fb2  throw
0x6fb3  pop
0x6fb4  ldc.i4   0x194
0x6fb9  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x6fbe  throw
0x6fbf  pop
0x6fc0  ldc.i4   0x190
0x6fc5  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x6fca  throw
0x6fcb  ldloc.0
0x6fcc  ret
```
