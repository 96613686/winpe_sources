# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.DataSetsController::GetAggregatedValue

- ea: `0x4cb0`
- end: `0x4d8b`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.DataSetsController::GetAggregatedValue`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x690`
- `0x6f0`
- `0x4cb0`

## string_xrefs

- `0x4d74`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x4cb0  ldarg.1
0x4cb1  ldloca.s 0
0x4cb3  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x4cb8  brtrue.s loc_4CC1
0x4cba  ldarg.0
0x4cbb  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::NotFound()
0x4cc0  ret
0x4cc1  ldarg.s  4
0x4cc3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4cc8  brfalse.s loc_4CD6
0x4cca  ldarg.0
0x4ccb  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_PropertyNullException()
0x4cd0  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::BadRequest(string)
0x4cd5  ret
0x4cd6  ldtoken  [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItemAggregation
0x4cdb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ce0  ldarg.s  5
0x4ce2  box      [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItemAggregation
0x4ce7  call     bool [mscorlib]System.Enum::IsDefined(class [mscorlib]System.Type, object)
0x4cec  brfalse.s loc_4CF2
0x4cee  ldarg.s  5
0x4cf0  brtrue.s loc_4CFE
0x4cf2  ldarg.0
0x4cf3  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_InvalidAggregation()
0x4cf8  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::BadRequest(string)
0x4cfd  ret
0x4cfe  ldarg.3
0x4cff  dup
0x4d00  brtrue.s loc_4D08
0x4d02  pop
0x4d03  newobj   instance void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataActionParameters::.ctor()
0x4d08  starg.s  3
0x4d0a  ldarg.3
0x4d0b  ldstr    aParameters// "Parameters"
0x4d10  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x4d15  brtrue.s loc_4D23
0x4d17  ldc.i4.0
0x4d18  newarr   [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter
0x4d1d  stloc.s  4
0x4d1f  ldloc.s  4
0x4d21  br.s     loc_4D33
0x4d23  ldarg.3
0x4d24  ldstr    aParameters// "Parameters"
0x4d29  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x4d2e  isinst   class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>
0x4d33  stloc.1
0x4d34  ldarg.0
0x4d35  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::get_DataService()
0x4d3a  ldarg.0
0x4d3b  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x4d40  ldloc.0
0x4d41  ldloc.1
0x4d42  ldarg.s  4
0x4d44  ldarg.s  5
0x4d46  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService::GetDataSetAggregatedValuesJson(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>, string, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItemAggregation)
0x4d4b  stloc.2
0x4d4c  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor()
0x4d51  dup
0x4d52  ldc.i4   0xC8
0x4d57  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x4d5c  dup
0x4d5d  ldloc.2
0x4d5e  newobj   instance void [System.Net.Http]System.Net.Http.StringContent::.ctor(string)
0x4d63  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x4d68  stloc.3
0x4d69  ldloc.3
0x4d6a  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x4d6f  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x4d74  ldstr    aApplicationJso// "application/json"
0x4d79  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x4d7e  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentType(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue)
0x4d83  ldarg.0
0x4d84  ldloc.3
0x4d85  call     instance class [System.Web.Http]System.Web.Http.Results.ResponseMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::ResponseMessage(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0x4d8a  ret
```
