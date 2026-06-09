# Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::CheckDataSourceConnection

- ea: `0xcfc0`
- end: `0xd03d`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::CheckDataSourceConnection`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x3d20`

## callees

- `0xa460`
- `0xa470`
- `0xcfc0`

## pseudocode

```c

```

## disassembly

```asm
0xcfc0  ldarg.0
0xcfc1  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_catalogRepository
0xcfc6  ldarg.0
0xcfc7  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataController Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_catalogItemController
0xcfcc  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xcfd1  ldarg.1
0xcfd2  ldarg.2
0xcfd3  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetDataSourceForTestConnection(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xcfd8  stloc.0
0xcfd9  ldarg.0
0xcfda  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_pbixReportHelper
0xcfdf  ldloc.0
0xcfe0  callvirt instance bool Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper::CanBeTestedByMashup(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource dataSource)
0xcfe5  brfalse.s loc_D025
0xcfe7  ldarg.0
0xcfe8  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_pbixReportHelper
0xcfed  ldarg.0
0xcfee  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_portalConfigurationManager
0xcff3  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xcff8  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_PowerBIUrl()
0xcffd  ldarg.0
0xcffe  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_logger
0xd003  ldarg.0
0xd004  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataController Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_catalogItemController
0xd009  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xd00e  ldloc.0
0xd00f  ldarg.0
0xd010  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_portalConfigurationManager
0xd015  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xd01a  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_ReportServerHostName()
0xd01f  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSourceCheckResult Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper::TestDataSource(string powerBiUri, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource dataSource, string reportServerHostName)
0xd024  ret
0xd025  ldarg.0
0xd026  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_catalogRepository
0xd02b  ldarg.0
0xd02c  ldfld    class [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataController Microsoft.ReportingServices.Portal.ODataWebApi.Common.PowerBIReportsControllerHelper::_catalogItemController
0xd031  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xd036  ldloc.0
0xd037  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSourceCheckResult [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::TestDataSource(class [mscorlib]System.Security.Principal.IPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource)
0xd03c  ret
```
