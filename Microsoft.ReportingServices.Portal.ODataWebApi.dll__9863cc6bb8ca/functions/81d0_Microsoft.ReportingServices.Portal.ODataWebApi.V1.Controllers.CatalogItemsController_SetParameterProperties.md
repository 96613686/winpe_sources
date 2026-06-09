# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::SetParameterProperties

- ea: `0x81d0`
- end: `0x8268`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::SetParameterProperties`
- size: `152`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x81d0`

## string_xrefs

- `0x8222`: `Catalog item {0} is neither a report or a linked report`

## pseudocode

```c

```

## disassembly

```asm
0x81d0  ldarg.0
0x81d1  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x81d6  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0x81db  brfalse.s loc_81EA
0x81dd  ldarg.3
0x81de  ldstr    aParameterprope// "ParameterProperties"
0x81e3  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x81e8  brtrue.s loc_81F7
0x81ea  ldarg.0
0x81eb  ldarg.0
0x81ec  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::GetModelStateValidationErrors()
0x81f1  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::BadRequest(string)
0x81f6  ret
0x81f7  ldarg.0
0x81f8  ldarg.1
0x81f9  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.Report
0x81fe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8203  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x8208  callvirt instance var<u1> class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::GetEntity(!!T0, string)
0x820d  stloc.0
0x820e  ldloc.0
0x820f  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x8214  ldc.i4.2
0x8215  beq.s    loc_8233
0x8217  ldloc.0
0x8218  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x821d  ldc.i4.s 9
0x821f  beq.s    loc_8233
0x8221  ldarg.0
0x8222  ldstr    aCatalogItem0Is_1// "Catalog item {0} is neither a report or"...
0x8227  ldarg.1
0x8228  call     string [mscorlib]System.String::Format(string, object)
0x822d  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::BadRequest(string)
0x8232  ret
0x8233  ldarg.3
0x8234  ldstr    aParameterprope// "ParameterProperties"
0x8239  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x823e  castclass class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterProperties>
0x8243  stloc.1
0x8244  ldarg.0
0x8245  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_catalogRepository
0x824a  ldarg.0
0x824b  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x8250  ldloc.0
0x8251  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x8256  ldloc.1
0x8257  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::UpdateReportParameterDefinition(class [mscorlib]System.Security.Principal.IPrincipal, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterProperties>)
0x825c  ldarg.0
0x825d  ldc.i4   0xCC
0x8262  call     instance class [System.Web.Http]System.Web.Http.Results.StatusCodeResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x8267  ret
```
