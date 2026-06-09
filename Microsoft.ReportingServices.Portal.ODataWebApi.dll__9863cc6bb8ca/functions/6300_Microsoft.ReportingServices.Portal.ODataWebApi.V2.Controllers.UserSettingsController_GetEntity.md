# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UserSettingsController::GetEntity

- ea: `0x6300`
- end: `0x6362`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UserSettingsController::GetEntity`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x6300`

## string_xrefs

- `0x632a`: `User {0} doesn't have permission to access user settings of requested user ({1})`

## pseudocode

```c

```

## disassembly

```asm
0x6300  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_Current()
0x6305  ldc.i4.2
0x6306  ldc.i4.0
0x6307  callvirt instance bool [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::IsConfigSwitchEnabled(valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSwitches, bool)
0x630c  brfalse.s loc_6355
0x630e  ldarg.0
0x630f  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UserSettingsController::_catalogRepository
0x6314  ldarg.1
0x6315  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x631a  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.UserSettings [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetUserSettings(valuetype [mscorlib]System.Guid)
0x631f  stloc.0
0x6320  leave.s  loc_6360
0x6322  pop
0x6323  ldarg.0
0x6324  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.UserSettingsController::_logger
0x6329  ldc.i4.3
0x632a  ldstr    aUser0DoesnTHav_3// "User {0} doesn't have permission to acc"...
0x632f  ldarg.0
0x6330  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x6335  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x633a  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x633f  ldarg.1
0x6340  call     string [mscorlib]System.String::Format(string, object, object)
0x6345  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x634a  ldc.i4   0x193
0x634f  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x6354  throw
0x6355  ldc.i4   0x1F5
0x635a  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x635f  throw
0x6360  ldloc.0
0x6361  ret
```
