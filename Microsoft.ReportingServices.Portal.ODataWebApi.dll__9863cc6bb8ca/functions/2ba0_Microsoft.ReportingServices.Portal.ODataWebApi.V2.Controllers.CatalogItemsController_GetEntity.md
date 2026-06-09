# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::GetEntity

- ea: `0x2ba0`
- end: `0x2c45`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::GetEntity`
- size: `165`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x2ba0`
- `0x76f0`

## pseudocode

```c

```

## disassembly

```asm
0x2ba0  ldsfld   string [mscorlib]System.String::Empty
0x2ba5  stloc.0
0x2ba6  ldarg.0
0x2ba7  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::get_CatalogItemControllerHelper()
0x2bac  ldarg.1
0x2bad  ldloca.s 0
0x2baf  callvirt instance bool class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::IsRequestByPath(string, string&)
0x2bb4  stloc.1
0x2bb5  ldloca.s 2
0x2bb7  initobj  [mscorlib]System.Guid
0x2bbd  ldloc.1
0x2bbe  brtrue.s loc_2BCC
0x2bc0  ldarg.1
0x2bc1  ldloca.s 2
0x2bc3  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x2bc8  brtrue.s loc_2BCC
0x2bca  ldnull
0x2bcb  ret
0x2bcc  ldarg.2
0x2bcd  ldsfld   string Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::DataSourceClassName
0x2bd2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2bd7  brfalse.s loc_2C02
0x2bd9  ldloc.1
0x2bda  brtrue.s loc_2BEF
0x2bdc  ldarg.0
0x2bdd  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_catalogRepository
0x2be2  ldarg.0
0x2be3  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x2be8  ldloc.2
0x2be9  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetDataSource(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x2bee  ret
0x2bef  ldarg.0
0x2bf0  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_catalogRepository
0x2bf5  ldarg.0
0x2bf6  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x2bfb  ldloc.0
0x2bfc  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetDataSource(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x2c01  ret
0x2c02  ldarg.2
0x2c03  ldsfld   string Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::DataSetClassName
0x2c08  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2c0d  brfalse.s loc_2C38
0x2c0f  ldloc.1
0x2c10  brtrue.s loc_2C25
0x2c12  ldarg.0
0x2c13  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_catalogRepository
0x2c18  ldarg.0
0x2c19  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x2c1e  ldloc.2
0x2c1f  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetDataSet(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid)
0x2c24  ret
0x2c25  ldarg.0
0x2c26  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemsController::_catalogRepository
0x2c2b  ldarg.0
0x2c2c  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x2c31  ldloc.0
0x2c32  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetDataSet(class [mscorlib]System.Security.Principal.IPrincipal, string)
0x2c37  ret
0x2c38  ldarg.0
0x2c39  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::get_CatalogItemControllerHelper()
0x2c3e  ldarg.1
0x2c3f  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::GetCatalogItemByKey(string)
0x2c44  ret
```
