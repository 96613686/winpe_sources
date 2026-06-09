# Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::UpdateDataModelParametersInAS

- ea: `0xcec0`
- end: `0xcf22`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::UpdateDataModelParametersInAS`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xdf90`

## callees

- `0x700`
- `0xa490`
- `0xce10`
- `0xcec0`

## pseudocode

```c

```

## disassembly

```asm
0xcec0  ldarg.0
0xcec1  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::get_PbixReportHelper()
0xcec6  ldarg.1
0xcec7  ldarg.2
0xcec8  ldarg.0
0xcec9  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_portalConfigurationManager
0xcece  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xced3  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_PowerBIUrl()
0xced8  ldarg.0
0xced9  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_logger
0xcede  ldarg.0
0xcedf  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataController Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_catalogItemController
0xcee4  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xcee9  ldarg.0
0xceea  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_portalConfigurationManager
0xceef  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xcef4  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_ReportServerHostName()
0xcef9  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper::UpdateDataModelParametersInPowerBI(valuetype [mscorlib]System.Guid catalogId, class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelParameter> dataModelParameters, string powerBiUri, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string reportServerHostName)
0xcefe  stloc.0
0xceff  leave.s  loc_CF20
0xcf01  stloc.1
0xcf02  ldarg.0
0xcf03  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_logger
0xcf08  ldc.i4.1
0xcf09  ldloc.1
0xcf0a  callvirt instance string [mscorlib]System.Exception::get_Message()
0xcf0f  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xcf14  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_ErrorPbixUpload()
0xcf19  ldloc.1
0xcf1a  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.InvalidDataModelParameterException::.ctor(string, class [mscorlib]System.Exception)
0xcf1f  throw
0xcf20  ldloc.0
0xcf21  ret
```
