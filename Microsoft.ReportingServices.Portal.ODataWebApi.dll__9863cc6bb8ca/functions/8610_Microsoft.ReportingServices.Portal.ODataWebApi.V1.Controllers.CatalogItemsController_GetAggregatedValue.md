# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::GetAggregatedValue

- ea: `0x8610`
- end: `0x86eb`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::GetAggregatedValue`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x690`
- `0x6f0`
- `0x8610`

## string_xrefs

- `0x86d4`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x8610  ldarg.1
0x8611  ldloca.s 0
0x8613  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x8618  brtrue.s loc_8621
0x861a  ldarg.0
0x861b  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::NotFound()
0x8620  ret
0x8621  ldarg.s  4
0x8623  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8628  brfalse.s loc_8636
0x862a  ldarg.0
0x862b  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_PropertyNullException()
0x8630  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::BadRequest(string)
0x8635  ret
0x8636  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItemAggregation
0x863b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8640  ldarg.s  5
0x8642  box      [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItemAggregation
0x8647  call     bool [mscorlib]System.Enum::IsDefined(class [mscorlib]System.Type, object)
0x864c  brfalse.s loc_8652
0x864e  ldarg.s  5
0x8650  brtrue.s loc_865E
0x8652  ldarg.0
0x8653  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_InvalidAggregation()
0x8658  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::BadRequest(string)
0x865d  ret
0x865e  ldarg.3
0x865f  dup
0x8660  brtrue.s loc_8668
0x8662  pop
0x8663  newobj   instance void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataActionParameters::.ctor()
0x8668  starg.s  3
0x866a  ldarg.3
0x866b  ldstr    aParameters// "Parameters"
0x8670  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x8675  brtrue.s loc_8683
0x8677  ldc.i4.0
0x8678  newarr   [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter
0x867d  stloc.s  4
0x867f  ldloc.s  4
0x8681  br.s     loc_8693
0x8683  ldarg.3
0x8684  ldstr    aParameters// "Parameters"
0x8689  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x868e  isinst   class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>
0x8693  stloc.1
0x8694  ldarg.0
0x8695  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_dataService
0x869a  ldarg.0
0x869b  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x86a0  ldloc.0
0x86a1  ldloc.1
0x86a2  ldarg.s  4
0x86a4  ldarg.s  5
0x86a6  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService::GetDataSetAggregatedValuesJson(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>, string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItemAggregation)
0x86ab  stloc.2
0x86ac  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor()
0x86b1  dup
0x86b2  ldc.i4   0xC8
0x86b7  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x86bc  dup
0x86bd  ldloc.2
0x86be  newobj   instance void [System.Net.Http]System.Net.Http.StringContent::.ctor(string)
0x86c3  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x86c8  stloc.3
0x86c9  ldloc.3
0x86ca  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x86cf  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x86d4  ldstr    aApplicationJso// "application/json"
0x86d9  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x86de  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentType(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue)
0x86e3  ldarg.0
0x86e4  ldloc.3
0x86e5  call     instance class [System.Web.Http]System.Web.Http.Results.ResponseMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::ResponseMessage(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0x86ea  ret
```
