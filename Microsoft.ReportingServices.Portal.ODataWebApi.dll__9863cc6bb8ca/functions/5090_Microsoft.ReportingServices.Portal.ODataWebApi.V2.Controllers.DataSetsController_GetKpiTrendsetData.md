# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.DataSetsController::GetKpiTrendsetData

- ea: `0x5090`
- end: `0x5143`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.DataSetsController::GetKpiTrendsetData`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x690`
- `0x5090`

## string_xrefs

- `0x512c`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x5090  ldarg.1
0x5091  ldloca.s 0
0x5093  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x5098  brtrue.s loc_50A1
0x509a  ldarg.0
0x509b  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::NotFound()
0x50a0  ret
0x50a1  ldarg.s  4
0x50a3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x50a8  brfalse.s loc_50B6
0x50aa  ldarg.0
0x50ab  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_PropertyNullException()
0x50b0  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::BadRequest(string)
0x50b5  ret
0x50b6  ldarg.3
0x50b7  dup
0x50b8  brtrue.s loc_50C0
0x50ba  pop
0x50bb  newobj   instance void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataActionParameters::.ctor()
0x50c0  starg.s  3
0x50c2  ldarg.3
0x50c3  ldstr    aParameters// "Parameters"
0x50c8  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x50cd  brtrue.s loc_50DB
0x50cf  ldc.i4.0
0x50d0  newarr   [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter
0x50d5  stloc.s  4
0x50d7  ldloc.s  4
0x50d9  br.s     loc_50EB
0x50db  ldarg.3
0x50dc  ldstr    aParameters// "Parameters"
0x50e1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x50e6  isinst   class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>
0x50eb  stloc.1
0x50ec  ldarg.0
0x50ed  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::get_DataService()
0x50f2  ldarg.0
0x50f3  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x50f8  ldloc.0
0x50f9  ldloc.1
0x50fa  ldarg.s  4
0x50fc  ldc.i4.s 0x1E
0x50fe  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService::GetDataSetColumnJson(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>, string, int32)
0x5103  stloc.2
0x5104  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor()
0x5109  dup
0x510a  ldc.i4   0xC8
0x510f  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x5114  dup
0x5115  ldloc.2
0x5116  newobj   instance void [System.Net.Http]System.Net.Http.StringContent::.ctor(string)
0x511b  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x5120  stloc.3
0x5121  ldloc.3
0x5122  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x5127  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x512c  ldstr    aApplicationJso// "application/json"
0x5131  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x5136  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentType(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue)
0x513b  ldarg.0
0x513c  ldloc.3
0x513d  call     instance class [System.Web.Http]System.Web.Http.Results.ResponseMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::ResponseMessage(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0x5142  ret
```
