# Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::ValidatePbiReportRenderingIsSupportedAndSetProperties

- ea: `0xce30`
- end: `0xceb6`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::ValidatePbiReportRenderingIsSupportedAndSetProperties`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x2fc0`
- `0x3a60`

## callees

- `0x700`
- `0x9f50`
- `0x9f70`
- `0x9f90`
- `0xa450`
- `0xce10`
- `0xce30`

## pseudocode

```c

```

## disassembly

```asm
0xce30  ldarg.0
0xce31  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::get_PbixReportHelper()
0xce36  ldarg.1
0xce37  ldarg.0
0xce38  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_portalConfigurationManager
0xce3d  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xce42  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_PowerBIUrl()
0xce47  ldarg.0
0xce48  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_logger
0xce4d  ldarg.0
0xce4e  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataController Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_catalogItemController
0xce53  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xce58  ldarg.0
0xce59  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_portalConfigurationManager
0xce5e  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xce63  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_ReportServerHostName()
0xce68  callvirt instance class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper::ValidateRenderingIsSupportedAndSetProperties(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport entity, string powerBiUri, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string reportServerHostName)
0xce6d  stloc.0
0xce6e  ldloc.0
0xce6f  callvirt instance bool Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::get_IsSupported()
0xce74  brtrue.s loc_CE88
0xce76  ldloc.0
0xce77  callvirt instance string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::get_ErrorMessage()
0xce7c  ldloc.0
0xce7d  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::get_ErrorCode()
0xce82  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.PowerBIReportNotSupportedException::.ctor(string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode)
0xce87  throw
0xce88  leave.s  loc_CEB5
0xce8a  stloc.1
0xce8b  ldarg.0
0xce8c  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_logger
0xce91  ldc.i4.1
0xce92  ldloc.1
0xce93  callvirt instance string [mscorlib]System.Exception::get_Message()
0xce98  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xce9d  ldloc.1
0xce9e  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.PowerBIReportNotSupportedException
0xcea3  brfalse.s loc_CEA7
0xcea5  rethrow
0xcea7  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_ErrorPbixUpload()
0xceac  ldc.i4.s 0x66
0xceae  ldloc.1
0xceaf  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.PowerBIReportNotSupportedException::.ctor(string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode, class [mscorlib]System.Exception)
0xceb4  throw
0xceb5  ret
```
