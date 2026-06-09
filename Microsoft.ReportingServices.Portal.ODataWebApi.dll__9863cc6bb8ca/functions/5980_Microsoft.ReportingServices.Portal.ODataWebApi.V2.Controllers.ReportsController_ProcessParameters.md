# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ReportsController::ProcessParameters

- ea: `0x5980`
- end: `0x5a43`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.ReportsController::ProcessParameters`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x5980`

## string_xrefs

- `0x59d1`: `Catalog item {0} is neither a report nor linked report nor data set`

## pseudocode

```c

```

## disassembly

```asm
0x5980  ldarg.0
0x5981  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x5986  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0x598b  brfalse.s loc_599A
0x598d  ldarg.3
0x598e  ldstr    aParametervalue_0// "ParameterValues"
0x5993  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5998  brtrue.s loc_59A7
0x599a  ldarg.0
0x599b  ldarg.0
0x599c  call     instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::GetModelStateValidationErrors()
0x59a1  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::BadRequest(string)
0x59a6  ret
0x59a7  ldarg.0
0x59a8  call     instance class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::get_CatalogItemControllerHelper()
0x59ad  ldarg.1
0x59ae  callvirt instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::GetCatalogItemByKey(string)
0x59b3  stloc.0
0x59b4  ldloc.0
0x59b5  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x59ba  ldc.i4.2
0x59bb  beq.s    loc_59E2
0x59bd  ldloc.0
0x59be  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x59c3  ldc.i4.s 9
0x59c5  beq.s    loc_59E2
0x59c7  ldloc.0
0x59c8  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x59cd  ldc.i4.4
0x59ce  beq.s    loc_59E2
0x59d0  ldarg.0
0x59d1  ldstr    aCatalogItem0Is_0// "Catalog item {0} is neither a report no"...
0x59d6  ldarg.1
0x59d7  call     string [mscorlib]System.String::Format(string, object)
0x59dc  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::BadRequest(string)
0x59e1  ret
0x59e2  ldarg.3
0x59e3  ldstr    aParametervalue_0// "ParameterValues"
0x59e8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x59ed  castclass class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>
0x59f2  stloc.1
0x59f3  ldarg.0
0x59f4  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Report>::get_CatalogRepository()
0x59f9  ldarg.0
0x59fa  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x59ff  ldloc.0
0x5a00  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Path()
0x5a05  ldloc.1
0x5a06  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition> [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetReportParameterDefinitionsWithQueryAndCurrentValues(class [mscorlib]System.Security.Principal.IPrincipal, string, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ParameterValue>)
0x5a0b  stloc.2
0x5a0c  ldloc.0
0x5a0d  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x5a12  ldc.i4.4
0x5a13  bne.un.s loc_5A3B
0x5a15  ldloc.2
0x5a16  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition, class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition> <>c::<>9__37_0
0x5a1b  dup
0x5a1c  brtrue.s loc_5A35
0x5a1e  pop
0x5a1f  ldsfld   class <>c <>c::<>9
0x5a24  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition <>c::<ProcessParameters>b__37_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition parameter)
0x5a2a  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition, class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition>::.ctor(object, native int)
0x5a2f  dup
0x5a30  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition, class [Microsoft.ReportingServices.Portal.Interfaces]Model.ReportParameterDefinition> <>c::<>9__37_0
0x5a35  call     T0x2B000086
0x5a3a  stloc.2
0x5a3b  ldarg.0
0x5a3c  ldloc.2
0x5a3d  callvirt T0x2B000087
0x5a42  ret
```
