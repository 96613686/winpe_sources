# <PatchSystemProperties>d__17::MoveNext

- ea: `0xe970`
- end: `0xeab5`
- name: `<PatchSystemProperties>d__17::MoveNext`
- size: `325`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0xe970`

## pseudocode

```c

```

## disassembly

```asm
0xe970  ldarg.0
0xe971  ldfld    int32 <PatchSystemProperties>d__17::<>1__state
0xe976  stloc.0
0xe977  ldarg.0
0xe978  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SystemController <PatchSystemProperties>d__17::<>4__this
0xe97d  stloc.1
0xe97e  ldloc.0
0xe97f  brfalse  loc_EA2D
0xe984  ldloc.1
0xe985  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0xe98a  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Content()
0xe98f  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> [System.Net.Http]System.Net.Http.HttpContent::ReadAsStringAsync()
0xe994  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<string>::get_Result()
0xe999  stloc.3
0xe99a  ldarg.0
0xe99b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>::.ctor()
0xe9a0  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> <PatchSystemProperties>d__17::<properties>5__2
0xe9a5  ldloc.3
0xe9a6  ldarg.0
0xe9a7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> <PatchSystemProperties>d__17::<properties>5__2
0xe9ac  call     void [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::PopulateObject(string, object)
0xe9b1  leave.s  loc_E9DE
0xe9b3  stloc.s  5
0xe9b5  ldloc.1
0xe9b6  call     instance class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.System>::get_Logger()
0xe9bb  ldc.i4.4
0xe9bc  ldstr    aInvalidPayload// "Invalid payload: {0}"
0xe9c1  ldloc.s  5
0xe9c3  callvirt instance string [mscorlib]System.Exception::get_Message()
0xe9c8  call     string [mscorlib]System.String::Format(string, object)
0xe9cd  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe9d2  ldloc.1
0xe9d3  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.System>::BadRequest()
0xe9d8  stloc.2
0xe9d9  leave    loc_EAA0
0xe9de  ldloc.1
0xe9df  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SystemController::_systemService
0xe9e4  ldarg.0
0xe9e5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> <PatchSystemProperties>d__17::<properties>5__2
0xe9ea  ldstr    aOfficeonlinedi// "OfficeOnlineDiscoveryUrl"
0xe9ef  ldstr    aExcelwopiclien// "ExcelWopiClientUrl"
0xe9f4  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::ValidateWopiUrlProperty(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>, string, string)
0xe9f9  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>>::GetAwaiter()
0xe9fe  stloc.s  6
0xea00  ldloca.s 6
0xea02  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>>::get_IsCompleted()
0xea07  brtrue.s loc_EA4A
0xea09  ldarg.0
0xea0a  ldc.i4.0
0xea0b  dup
0xea0c  stloc.0
0xea0d  stfld    int32 <PatchSystemProperties>d__17::<>1__state
0xea12  ldarg.0
0xea13  ldloc.s  6
0xea15  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>> <PatchSystemProperties>d__17::<>u__1
0xea1a  ldarg.0
0xea1b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <PatchSystemProperties>d__17::<>t__builder
0xea20  ldloca.s 6
0xea22  ldarg.0
0xea23  call     T0x2B000109
0xea28  leave    loc_EAB4
0xea2d  ldarg.0
0xea2e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>> <PatchSystemProperties>d__17::<>u__1
0xea33  stloc.s  6
0xea35  ldarg.0
0xea36  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>> <PatchSystemProperties>d__17::<>u__1
0xea3b  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>>
0xea41  ldarg.0
0xea42  ldc.i4.m1
0xea43  dup
0xea44  stloc.0
0xea45  stfld    int32 <PatchSystemProperties>d__17::<>1__state
0xea4a  ldloca.s 6
0xea4c  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>>::GetResult()
0xea51  stloc.s  4
0xea53  ldloc.1
0xea54  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SystemController::_systemService
0xea59  ldarg.0
0xea5a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> <PatchSystemProperties>d__17::<properties>5__2
0xea5f  ldstr    aPowerbimigrate// "PowerBIMigrateUrl"
0xea64  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::ValidatePowerBIMigrateUrl(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>, string)
0xea69  pop
0xea6a  ldloc.1
0xea6b  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.SystemController::_systemService
0xea70  ldloc.1
0xea71  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xea76  ldloc.s  4
0xea78  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::UpdateSystemProperties(class [mscorlib]System.Security.Principal.IPrincipal, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>)
0xea7d  pop
0xea7e  ldloc.1
0xea7f  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.System>::Ok()
0xea84  stloc.2
0xea85  leave.s  loc_EAA0
0xea87  stloc.s  7
0xea89  ldarg.0
0xea8a  ldc.i4.s 0xFE
0xea8c  stfld    int32 <PatchSystemProperties>d__17::<>1__state
0xea91  ldarg.0
0xea92  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <PatchSystemProperties>d__17::<>t__builder
0xea97  ldloc.s  7
0xea99  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0xea9e  leave.s  loc_EAB4
0xeaa0  ldarg.0
0xeaa1  ldc.i4.s 0xFE
0xeaa3  stfld    int32 <PatchSystemProperties>d__17::<>1__state
0xeaa8  ldarg.0
0xeaa9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <PatchSystemProperties>d__17::<>t__builder
0xeaae  ldloc.2
0xeaaf  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0xeab4  ret
```
