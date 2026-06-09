# Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::CheckConnection

- ea: `0xcaa0`
- end: `0xcbb9`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::CheckConnection`
- size: `281`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xa460`
- `0xa470`
- `0xcaa0`

## pseudocode

```c

```

## disassembly

```asm
0xcaa0  ldnull
0xcaa1  stloc.0
0xcaa2  ldarg.1
0xcaa3  brfalse.s loc_CAB4
0xcaa5  ldarg.1
0xcaa6  ldstr    aDatasource// "dataSource"
0xcaab  ldloca.s 0
0xcaad  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0xcab2  brtrue.s loc_CACB
0xcab4  ldarg.0
0xcab5  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcaba  ldarg.0
0xcabb  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcac0  callvirt instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::GetModelStateValidationErrors()
0xcac5  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest(string)
0xcaca  ret
0xcacb  ldloc.0
0xcacc  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource
0xcad1  stloc.1
0xcad2  ldloc.1
0xcad3  brtrue.s loc_CAEC
0xcad5  ldarg.0
0xcad6  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcadb  ldarg.0
0xcadc  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcae1  callvirt instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::GetModelStateValidationErrors()
0xcae6  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest(string)
0xcaeb  ret
0xcaec  ldloc.1
0xcaed  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataSourceSubType()
0xcaf2  ldsfld   string [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.ODataExtensions.DataModelDataSourceExtensions::DataSourceSubTypeName
0xcaf7  ldc.i4.5
0xcaf8  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xcafd  brfalse  loc_CB94
0xcb02  ldloc.1
0xcb03  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0xcb08  brtrue.s loc_CB21
0xcb0a  ldarg.0
0xcb0b  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcb10  ldarg.0
0xcb11  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcb16  callvirt instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::GetModelStateValidationErrors()
0xcb1b  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::BadRequest(string)
0xcb20  ret
0xcb21  ldarg.0
0xcb22  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::get_PbixReportHelper()
0xcb27  ldloc.1
0xcb28  callvirt instance bool Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper::CanBeTestedByMashup(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource dataSource)
0xcb2d  stloc.3
0xcb2e  ldloc.1
0xcb2f  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::get_DataModelDataSource()
0xcb34  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::get_Type()
0xcb39  ldc.i4.3
0xcb3a  ceq
0xcb3c  ldloc.3
0xcb3d  or
0xcb3e  brfalse.s loc_CB8D
0xcb40  ldarg.0
0xcb41  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_pbixReportHelper
0xcb46  ldarg.0
0xcb47  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_portalConfigurationManager
0xcb4c  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xcb51  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_PowerBIUrl()
0xcb56  ldarg.0
0xcb57  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_logger
0xcb5c  ldarg.0
0xcb5d  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcb62  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xcb67  ldloc.1
0xcb68  ldarg.0
0xcb69  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_portalConfigurationManager
0xcb6e  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xcb73  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_ReportServerHostName()
0xcb78  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSourceCheckResult Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper::TestDataSource(string powerBiUri, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource dataSource, string reportServerHostName)
0xcb7d  stloc.s  4
0xcb7f  ldarg.0
0xcb80  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcb85  ldloc.s  4
0xcb87  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::CreateOk(object)
0xcb8c  ret
0xcb8d  ldloc.1
0xcb8e  call     class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.ODataExtensions.DataModelDataSourceExtensions::ToDataSourceWithDecryptedSecret(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource)
0xcb93  stloc.1
0xcb94  ldarg.0
0xcb95  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogRepository
0xcb9a  ldarg.0
0xcb9b  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcba0  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xcba5  ldloc.1
0xcba6  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSourceCheckResult [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::TestDataSource(class [mscorlib]System.Security.Principal.IPrincipal, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource)
0xcbab  stloc.2
0xcbac  ldarg.0
0xcbad  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xcbb2  ldloc.2
0xcbb3  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::CreateOk(object)
0xcbb8  ret
```
