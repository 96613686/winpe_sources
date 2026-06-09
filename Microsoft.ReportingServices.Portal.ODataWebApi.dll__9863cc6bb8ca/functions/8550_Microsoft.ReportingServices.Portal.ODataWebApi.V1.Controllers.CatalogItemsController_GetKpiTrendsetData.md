# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::GetKpiTrendsetData

- ea: `0x8550`
- end: `0x8603`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::GetKpiTrendsetData`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x690`
- `0x8550`

## string_xrefs

- `0x85ec`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x8550  ldarg.1
0x8551  ldloca.s 0
0x8553  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x8558  brtrue.s loc_8561
0x855a  ldarg.0
0x855b  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::NotFound()
0x8560  ret
0x8561  ldarg.s  4
0x8563  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8568  brfalse.s loc_8576
0x856a  ldarg.0
0x856b  call     string Microsoft.ReportingServices.Portal.ODataWebApi.SR::get_PropertyNullException()
0x8570  call     instance class [System.Web.Http]System.Web.Http.Results.BadRequestErrorMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::BadRequest(string)
0x8575  ret
0x8576  ldarg.3
0x8577  dup
0x8578  brtrue.s loc_8580
0x857a  pop
0x857b  newobj   instance void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataActionParameters::.ctor()
0x8580  starg.s  3
0x8582  ldarg.3
0x8583  ldstr    aParameters// "Parameters"
0x8588  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x858d  brtrue.s loc_859B
0x858f  ldc.i4.0
0x8590  newarr   [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter
0x8595  stloc.s  4
0x8597  ldloc.s  4
0x8599  br.s     loc_85AB
0x859b  ldarg.3
0x859c  ldstr    aParameters// "Parameters"
0x85a1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x85a6  isinst   class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>
0x85ab  stloc.1
0x85ac  ldarg.0
0x85ad  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_dataService
0x85b2  ldarg.0
0x85b3  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x85b8  ldloc.0
0x85b9  ldloc.1
0x85ba  ldarg.s  4
0x85bc  ldc.i4.s 0x1E
0x85be  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService::GetDataSetColumnJson(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>, string, int32)
0x85c3  stloc.2
0x85c4  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor()
0x85c9  dup
0x85ca  ldc.i4   0xC8
0x85cf  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x85d4  dup
0x85d5  ldloc.2
0x85d6  newobj   instance void [System.Net.Http]System.Net.Http.StringContent::.ctor(string)
0x85db  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x85e0  stloc.3
0x85e1  ldloc.3
0x85e2  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x85e7  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x85ec  ldstr    aApplicationJso// "application/json"
0x85f1  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x85f6  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentType(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue)
0x85fb  ldarg.0
0x85fc  ldloc.3
0x85fd  call     instance class [System.Web.Http]System.Web.Http.Results.ResponseMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::ResponseMessage(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0x8602  ret
```
