# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.DataSetsController::GetData

- ea: `0x4d90`
- end: `0x4ea3`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.DataSetsController::GetData`
- size: `275`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5060`
- `0x5080`

## callees

- `0x4d90`

## string_xrefs

- `0x4e8c`: `application/json`
- `0x4df3`: `CanCompress`
- `0x4e6b`: `DataSetJsonCached`

## pseudocode

```c

```

## disassembly

```asm
0x4d90  ldarg.1
0x4d91  ldloca.s 0
0x4d93  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x4d98  brtrue.s loc_4DA1
0x4d9a  ldarg.0
0x4d9b  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::NotFound()
0x4da0  ret
0x4da1  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor()
0x4da6  dup
0x4da7  ldc.i4   0xC8
0x4dac  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x4db1  stloc.1
0x4db2  ldarg.2
0x4db3  dup
0x4db4  brtrue.s loc_4DBC
0x4db6  pop
0x4db7  newobj   instance void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataActionParameters::.ctor()
0x4dbc  starg.s  2
0x4dbe  ldarg.2
0x4dbf  ldstr    aParameters// "Parameters"
0x4dc4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x4dc9  brtrue.s loc_4DD7
0x4dcb  ldc.i4.0
0x4dcc  newarr   [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter
0x4dd1  stloc.s  4
0x4dd3  ldloc.s  4
0x4dd5  br.s     loc_4DE7
0x4dd7  ldarg.2
0x4dd8  ldstr    aParameters// "Parameters"
0x4ddd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x4de2  isinst   class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>
0x4de7  stloc.2
0x4de8  ldarg.0
0x4de9  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x4dee  call     class [Microsoft.Owin]Microsoft.Owin.IOwinContext [System.Web.Http.Owin]System.Net.Http.OwinHttpRequestMessageExtensions::GetOwinContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x4df3  ldstr    aCancompress// "CanCompress"
0x4df8  callvirt T0x2B00007A
0x4dfd  brfalse.s loc_4E40
0x4dff  ldarg.0
0x4e00  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::get_DataService()
0x4e05  ldarg.0
0x4e06  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x4e0b  ldloc.0
0x4e0c  ldloc.2
0x4e0d  ldarg.3
0x4e0e  ldloca.s 3
0x4e10  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService::GetCompressedDataSetTableJson(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>, valuetype [mscorlib]System.Nullable`1<int32>, bool&)
0x4e15  stloc.s  5
0x4e17  ldloc.1
0x4e18  ldloc.s  5
0x4e1a  newobj   instance void [System.Net.Http]System.Net.Http.ByteArrayContent::.ctor(unsigned int8[])
0x4e1f  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x4e24  ldloc.1
0x4e25  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x4e2a  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x4e2f  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<string> [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentEncoding()
0x4e34  ldstr    aGzip// "gzip"
0x4e39  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x4e3e  br.s     loc_4E65
0x4e40  ldarg.0
0x4e41  call     instance class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::get_DataService()
0x4e46  ldarg.0
0x4e47  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x4e4c  ldloc.0
0x4e4d  ldloc.2
0x4e4e  ldarg.3
0x4e4f  ldloca.s 3
0x4e51  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService::GetDataSetTableJson(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>, valuetype [mscorlib]System.Nullable`1<int32>, bool&)
0x4e56  stloc.s  6
0x4e58  ldloc.1
0x4e59  ldloc.s  6
0x4e5b  newobj   instance void [System.Net.Http]System.Net.Http.StringContent::.ctor(string)
0x4e60  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x4e65  ldloc.1
0x4e66  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x4e6b  ldstr    aDatasetjsoncac// "DataSetJsonCached"
0x4e70  ldloca.s 3
0x4e72  call     instance string [mscorlib]System.Boolean::ToString()
0x4e77  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x4e7c  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Add(string, string)
0x4e81  ldloc.1
0x4e82  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x4e87  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x4e8c  ldstr    aApplicationJso// "application/json"
0x4e91  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x4e96  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentType(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue)
0x4e9b  ldarg.0
0x4e9c  ldloc.1
0x4e9d  call     instance class [System.Web.Http]System.Web.Http.Results.ResponseMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSet>::ResponseMessage(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0x4ea2  ret
```
