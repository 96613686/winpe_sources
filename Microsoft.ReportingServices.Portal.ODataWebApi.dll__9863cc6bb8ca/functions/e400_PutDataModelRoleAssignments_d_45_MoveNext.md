# <PutDataModelRoleAssignments>d__45::MoveNext

- ea: `0xe400`
- end: `0xe53e`
- name: `<PutDataModelRoleAssignments>d__45::MoveNext`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xe400`

## pseudocode

```c

```

## disassembly

```asm
0xe400  ldarg.0
0xe401  ldfld    int32 <PutDataModelRoleAssignments>d__45::<>1__state
0xe406  stloc.0
0xe407  ldarg.0
0xe408  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController <PutDataModelRoleAssignments>d__45::<>4__this
0xe40d  stloc.1
0xe40e  ldloc.0
0xe40f  brfalse  loc_E4DE
0xe414  ldloc.1
0xe415  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::_systemService
0xe41a  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::IsBiServer()
0xe41f  brtrue.s loc_E42D
0xe421  ldloc.1
0xe422  call     instance class [System.Web.Http]System.Web.Http.Results.StatusCodeResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::NotAllowed()
0xe427  stloc.2
0xe428  leave    loc_E529
0xe42d  ldloc.1
0xe42e  ldarg.0
0xe42f  ldfld    string <PutDataModelRoleAssignments>d__45::Id
0xe434  ldnull
0xe435  callvirt instance var<u1> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::GetEntity(!!T0, string)
0xe43a  stloc.3
0xe43b  ldloc.1
0xe43c  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0xe441  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Content()
0xe446  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> [System.Net.Http]System.Net.Http.HttpContent::ReadAsStringAsync()
0xe44b  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<string>::get_Result()
0xe450  stloc.s  4
0xe452  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>::.ctor()
0xe457  stloc.s  5
0xe459  ldloc.s  4
0xe45b  ldloc.s  5
0xe45d  call     void [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::PopulateObject(string, object)
0xe462  leave.s  loc_E494
0xe464  stloc.s  6
0xe466  ldloc.1
0xe467  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_Logger()
0xe46c  ldc.i4.4
0xe46d  ldstr    aInvalidPayload// "Invalid payload: {0}"
0xe472  ldloc.s  6
0xe474  callvirt instance string [mscorlib]System.Exception::get_Message()
0xe479  call     string [mscorlib]System.String::Format(string, object)
0xe47e  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe483  ldloc.1
0xe484  ldc.i4   0x190
0xe489  call     instance class [System.Web.Http]System.Web.Http.Results.StatusCodeResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::StatusCode(valuetype [System]System.Net.HttpStatusCode)
0xe48e  stloc.2
0xe48f  leave    loc_E529
0xe494  ldloc.1
0xe495  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::get_CatalogRepository()
0xe49a  ldloc.1
0xe49b  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xe4a0  ldloc.3
0xe4a1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0xe4a6  ldloc.s  5
0xe4a8  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::UpdateDataModelRoleAssignmentsAsync(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>)
0xe4ad  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0xe4b2  stloc.s  7
0xe4b4  ldloca.s 7
0xe4b6  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0xe4bb  brtrue.s loc_E4FB
0xe4bd  ldarg.0
0xe4be  ldc.i4.0
0xe4bf  dup
0xe4c0  stloc.0
0xe4c1  stfld    int32 <PutDataModelRoleAssignments>d__45::<>1__state
0xe4c6  ldarg.0
0xe4c7  ldloc.s  7
0xe4c9  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <PutDataModelRoleAssignments>d__45::<>u__1
0xe4ce  ldarg.0
0xe4cf  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <PutDataModelRoleAssignments>d__45::<>t__builder
0xe4d4  ldloca.s 7
0xe4d6  ldarg.0
0xe4d7  call     T0x2B000104
0xe4dc  leave.s  loc_E53D
0xe4de  ldarg.0
0xe4df  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <PutDataModelRoleAssignments>d__45::<>u__1
0xe4e4  stloc.s  7
0xe4e6  ldarg.0
0xe4e7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <PutDataModelRoleAssignments>d__45::<>u__1
0xe4ec  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0xe4f2  ldarg.0
0xe4f3  ldc.i4.m1
0xe4f4  dup
0xe4f5  stloc.0
0xe4f6  stfld    int32 <PutDataModelRoleAssignments>d__45::<>1__state
0xe4fb  ldloca.s 7
0xe4fd  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0xe502  ldloc.1
0xe503  ldc.i4   0xC8
0xe508  call     instance class [System.Web.Http]System.Web.Http.Results.StatusCodeResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport>::StatusCode(valuetype [System]System.Net.HttpStatusCode)
0xe50d  stloc.2
0xe50e  leave.s  loc_E529
0xe510  stloc.s  8
0xe512  ldarg.0
0xe513  ldc.i4.s 0xFE
0xe515  stfld    int32 <PutDataModelRoleAssignments>d__45::<>1__state
0xe51a  ldarg.0
0xe51b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <PutDataModelRoleAssignments>d__45::<>t__builder
0xe520  ldloc.s  8
0xe522  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0xe527  leave.s  loc_E53D
0xe529  ldarg.0
0xe52a  ldc.i4.s 0xFE
0xe52c  stfld    int32 <PutDataModelRoleAssignments>d__45::<>1__state
0xe531  ldarg.0
0xe532  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <PutDataModelRoleAssignments>d__45::<>t__builder
0xe537  ldloc.2
0xe538  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0xe53d  ret
```
