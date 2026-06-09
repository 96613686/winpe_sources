# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::UpdateReportDataSets

- ea: `0x8850`
- end: `0x88fd`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::UpdateReportDataSets`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x8850`

## pseudocode

```c

```

## disassembly

```asm
0x8850  ldarg.0
0x8851  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x8856  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0x885b  brfalse.s loc_8875
0x885d  ldarg.2
0x885e  brfalse.s loc_8875
0x8860  ldarg.2
0x8861  ldstr    aDatasets_0// "dataSets"
0x8866  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x886b  brfalse.s loc_8875
0x886d  ldarg.1
0x886e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8873  brfalse.s loc_8882
0x8875  ldarg.0
0x8876  ldarg.0
0x8877  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::GetModelStateValidationErrors()
0x887c  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::BadRequest(string)
0x8881  ret
0x8882  ldarg.0
0x8883  ldarg.1
0x8884  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.Report
0x8889  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x888e  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x8893  callvirt instance var<u1> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::GetEntity(!!T0, string)
0x8898  stloc.0
0x8899  ldloc.0
0x889a  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x889f  ldc.i4.2
0x88a0  beq.s    loc_88C3
0x88a2  ldarg.0
0x88a3  ldstr    aCatalogItem0Is// "Catalog item {0} is not of type {1}"
0x88a8  ldarg.1
0x88a9  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.Report
0x88ae  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x88b3  callvirt instance string [mscorlib]System.Object::ToString()
0x88b8  call     string [mscorlib]System.String::Format(string, object, object)
0x88bd  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::BadRequest(string)
0x88c2  ret
0x88c3  ldarg.2
0x88c4  ldstr    aDatasets_0// "dataSets"
0x88c9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x88ce  castclass class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>
0x88d3  stloc.1
0x88d4  ldloc.1
0x88d5  brtrue.s loc_88DE
0x88d7  ldarg.0
0x88d8  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::BadRequest()
0x88dd  ret
0x88de  ldarg.0
0x88df  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_catalogRepository
0x88e4  ldarg.0
0x88e5  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x88ea  ldloc.0
0x88eb  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x88f0  ldloc.1
0x88f1  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::SetItemDataSets(class [mscorlib]System.Security.Principal.IPrincipal, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>)
0x88f6  ldarg.0
0x88f7  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::Ok()
0x88fc  ret
```
