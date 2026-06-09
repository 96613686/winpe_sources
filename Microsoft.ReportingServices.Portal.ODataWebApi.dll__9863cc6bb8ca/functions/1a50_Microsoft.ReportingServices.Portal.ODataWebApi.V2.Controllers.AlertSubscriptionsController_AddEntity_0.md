# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.AlertSubscriptionsController::AddEntity_0

- ea: `0x1a50`
- end: `0x1b2c`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.AlertSubscriptionsController::AddEntity_0`
- size: `220`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a50`

## pseudocode

```c

```

## disassembly

```asm
0x1a50  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::get_Current()
0x1a55  ldc.i4.2
0x1a56  ldc.i4.0
0x1a57  callvirt instance bool [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.HostingState::IsConfigSwitchEnabled(valuetype [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSwitches, bool)
0x1a5c  brfalse  loc_1B21
0x1a61  ldc.i4.0
0x1a62  stloc.0
0x1a63  ldarg.0
0x1a64  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.AlertSubscriptionsController::_catalogRepository
0x1a69  ldarg.0
0x1a6a  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x1a6f  ldarg.1
0x1a70  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.AlertSubscription::get_ItemId()
0x1a75  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItemTypeByGuid(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x1a7a  stloc.1
0x1a7b  ldloc.1
0x1a7c  brfalse.s loc_1A96
0x1a7e  ldloc.1
0x1a7f  ldc.i4.1
0x1a80  beq.s    loc_1A96
0x1a82  ldloc.1
0x1a83  ldc.i4.3
0x1a84  beq.s    loc_1A96
0x1a86  ldloc.1
0x1a87  ldc.i4.4
0x1a88  beq.s    loc_1A96
0x1a8a  ldloc.1
0x1a8b  ldc.i4.5
0x1a8c  beq.s    loc_1A96
0x1a8e  ldloc.1
0x1a8f  ldc.i4.6
0x1a90  beq.s    loc_1A96
0x1a92  ldloc.1
0x1a93  ldc.i4.7
0x1a94  bne.un.s loc_1AA1
0x1a96  ldc.i4   0x190
0x1a9b  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x1aa0  throw
0x1aa1  ldarg.0
0x1aa2  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x1aa7  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x1aac  call     valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.Extensions.IdentityExtensions::ToAuthenticationType(class [mscorlib]System.Security.Principal.IIdentity)
0x1ab1  stloc.2
0x1ab2  ldarg.0
0x1ab3  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.AlertSubscriptionsController::_catalogRepository
0x1ab8  ldarg.0
0x1ab9  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x1abe  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x1ac3  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x1ac8  ldloc.2
0x1ac9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetUserId(string, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType)
0x1ace  stloc.3
0x1acf  ldarg.0
0x1ad0  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.AlertSubscriptionsController::_catalogRepository
0x1ad5  ldloc.3
0x1ad6  ldarg.1
0x1ad7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.AlertSubscription::get_ItemId()
0x1adc  ldarg.1
0x1add  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.AlertSubscription::get_AlertType()
0x1ae2  ldarg.2
0x1ae3  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::AddEmailAlertSubscription(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, class [Microsoft.ReportingServices.Portal.Interfaces]Model.AlertSubscription&)
0x1ae8  pop
0x1ae9  ldc.i4.1
0x1aea  stloc.0
0x1aeb  leave.s  loc_1B1F
0x1aed  pop
0x1aee  ldarg.0
0x1aef  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.AlertSubscriptionsController::_logger
0x1af4  ldc.i4.3
0x1af5  ldstr    aUser0DoesnTHav// "User {0} doesn't have permission to add"...
0x1afa  ldarg.0
0x1afb  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x1b00  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x1b05  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x1b0a  call     string [mscorlib]System.String::Format(string, object)
0x1b0f  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1b14  ldc.i4   0x193
0x1b19  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x1b1e  throw
0x1b1f  ldloc.0
0x1b20  ret
0x1b21  ldc.i4   0x1F5
0x1b26  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x1b2b  throw
```
