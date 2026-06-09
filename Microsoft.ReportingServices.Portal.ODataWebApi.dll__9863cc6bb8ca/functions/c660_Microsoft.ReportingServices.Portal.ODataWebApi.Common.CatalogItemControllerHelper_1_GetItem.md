# Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::GetItem

- ea: `0xc660`
- end: `0xc7d2`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::GetItem`
- size: `370`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x9f50`
- `0xa440`
- `0xa450`
- `0xc660`

## pseudocode

```c

```

## disassembly

```asm
0xc660  ldsfld   string [mscorlib]System.String::Empty
0xc665  stloc.0
0xc666  ldarg.0
0xc667  ldarg.1
0xc668  ldloca.s 0
0xc66a  call     instance bool class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::IsRequestByPath(string, string&)
0xc66f  stloc.1
0xc670  ldloca.s 2
0xc672  initobj  [mscorlib]System.Guid
0xc678  ldloc.1
0xc679  brtrue.s loc_C687
0xc67b  ldarg.1
0xc67c  ldloca.s 2
0xc67e  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0xc683  brtrue.s loc_C687
0xc685  ldnull
0xc686  ret
0xc687  ldloc.1
0xc688  brtrue.s loc_C6A3
0xc68a  ldarg.0
0xc68b  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogRepository
0xc690  ldarg.0
0xc691  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc696  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xc69b  ldloc.2
0xc69c  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0xc6a1  br.s     loc_C6BA
0xc6a3  ldarg.0
0xc6a4  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogRepository
0xc6a9  ldarg.0
0xc6aa  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc6af  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xc6b4  ldloc.0
0xc6b5  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItem(class [mscorlib]System.Security.Principal.IPrincipal, string)
0xc6ba  stloc.3
0xc6bb  ldloc.3
0xc6bc  brfalse  loc_C7CD
0xc6c1  ldloc.3
0xc6c2  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0xc6c7  ldc.i4.s 0xB
0xc6c9  bne.un   loc_C7CD
0xc6ce  ldloc.3
0xc6cf  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport
0xc6d4  stloc.s  4
0xc6d6  ldarg.0
0xc6d7  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_systemService
0xc6dc  callvirt instance bool [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ISystemService::IsBiServer()
0xc6e1  brfalse  loc_C7CD
0xc6e6  ldarg.0
0xc6e7  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::get_PbixReportHelper()
0xc6ec  ldloc.s  4
0xc6ee  ldarg.0
0xc6ef  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_portalConfigurationManager
0xc6f4  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xc6f9  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_PowerBIUrl()
0xc6fe  newobj   instance void [System]System.Uri::.ctor(string)
0xc703  ldarg.0
0xc704  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_logger
0xc709  ldarg.0
0xc70a  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc70f  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xc714  ldarg.0
0xc715  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_portalConfigurationManager
0xc71a  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xc71f  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_ReportServerHostName()
0xc724  callvirt instance bool Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper::ShouldReShred(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport entity, class [System]System.Uri basePortalUrl, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string reportServerHostName)
0xc729  brfalse  loc_C7CD
0xc72e  ldnull
0xc72f  stloc.s  5
0xc731  ldarg.0
0xc732  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogRepository
0xc737  ldarg.0
0xc738  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc73d  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xc742  ldloc.3
0xc743  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Id()
0xc748  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItemWithContentTrusted(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0xc74d  castclass [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport
0xc752  stloc.s  5
0xc754  leave.s  loc_C75C
0xc756  pop
0xc757  ldloc.3
0xc758  stloc.s  6
0xc75a  leave.s  loc_C7CF
0xc75c  ldarg.0
0xc75d  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::get_PbixReportHelper()
0xc762  ldloc.s  5
0xc764  ldarg.0
0xc765  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_portalConfigurationManager
0xc76a  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xc76f  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_PowerBIUrl()
0xc774  ldarg.0
0xc775  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_logger
0xc77a  ldarg.0
0xc77b  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc780  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xc785  ldarg.0
0xc786  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_portalConfigurationManager
0xc78b  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfigurationManager::get_Current()
0xc790  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Configuration.IPortalConfiguration::get_ReportServerHostName()
0xc795  callvirt instance class Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IPbixReportHelper::ValidateRenderingIsSupportedAndSetProperties(class [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport entity, string powerBiUri, class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ILogger logger, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string reportServerHostName)
0xc79a  callvirt instance bool Microsoft.ReportingServices.Portal.ODataWebApi.Utils.IsRenderingSupportedResult::get_IsSupported()
0xc79f  brfalse.s loc_C7CD
0xc7a1  ldloc.s  4
0xc7a3  ldc.i4.1
0xc7a4  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::set_HasDataSources(bool)
0xc7a9  ldarg.0
0xc7aa  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogRepository
0xc7af  ldarg.0
0xc7b0  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc7b5  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0xc7ba  ldloc.s  5
0xc7bc  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0xc7c1  ldloc.s  5
0xc7c3  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Properties()
0xc7c8  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::SetItemPropertiesTrusted(class [mscorlib]System.Security.Principal.IPrincipal, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property>)
0xc7cd  ldloc.3
0xc7ce  ret
0xc7cf  ldloc.s  6
0xc7d1  ret
```
