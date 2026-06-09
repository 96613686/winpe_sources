# Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::PbiParse

- ea: `0xcf30`
- end: `0xcfb7`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::PbiParse`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0xdc20`

## callees

- `0x700`
- `0x9f50`
- `0x9f70`
- `0x9f90`
- `0xa480`
- `0xce10`
- `0xcf30`

## pseudocode

```c

```

## disassembly

```asm
0xcf30  ldarg.0
0xcf31  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::get_PbixReportHelper()
0xcf36  ldarg.1
0xcf37  ldarg.2
0xcf38  ldarg.0
0xcf39  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_portalConfigurationManager
0xcf3e  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xcf43  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_PowerBIUrl()
0xcf48  ldarg.0
0xcf49  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_logger
0xcf4e  ldarg.0
0xcf4f  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataController Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_catalogItemController
0xcf54  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xcf59  ldarg.0
0xcf5a  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_portalConfigurationManager
0xcf5f  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xcf64  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_ReportServerHostName()
0xcf69  callvirt instance class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper::PbiParse(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport entity, class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles files, string powerBiUri, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string reportServerHostName)
0xcf6e  stloc.0
0xcf6f  ldloc.0
0xcf70  callvirt instance bool Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::get_IsSupported()
0xcf75  brtrue.s loc_CF89
0xcf77  ldloc.0
0xcf78  callvirt instance string Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::get_ErrorMessage()
0xcf7d  ldloc.0
0xcf7e  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::get_ErrorCode()
0xcf83  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.PowerBIReportNotSupportedException::.ctor(string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode)
0xcf88  throw
0xcf89  leave.s  loc_CFB6
0xcf8b  stloc.1
0xcf8c  ldarg.0
0xcf8d  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_logger
0xcf92  ldc.i4.1
0xcf93  ldloc.1
0xcf94  callvirt instance string [mscorlib]System.Exception::get_Message()
0xcf99  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xcf9e  ldloc.1
0xcf9f  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.PowerBIReportNotSupportedException
0xcfa4  brfalse.s loc_CFA8
0xcfa6  rethrow
0xcfa8  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_ErrorPbixUpload()
0xcfad  ldc.i4.s 0x66
0xcfaf  ldloc.1
0xcfb0  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.PowerBIReportNotSupportedException::.ctor(string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Enums.ErrorCode, class [mscorlib]System.Exception)
0xcfb5  throw
0xcfb6  ret
```
