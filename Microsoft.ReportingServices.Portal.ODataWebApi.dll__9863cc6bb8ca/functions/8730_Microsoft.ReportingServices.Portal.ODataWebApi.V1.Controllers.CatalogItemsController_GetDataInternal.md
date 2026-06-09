# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::GetDataInternal

- ea: `0x8730`
- end: `0x8843`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::GetDataInternal`
- size: `275`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x8520`
- `0x8540`
- `0x86f0`
- `0x8710`

## callees

- `0x8730`

## string_xrefs

- `0x882c`: `application/json`
- `0x8793`: `CanCompress`
- `0x880b`: `DataSetJsonCached`

## pseudocode

```c

```

## disassembly

```asm
0x8730  ldarg.1
0x8731  ldloca.s 0
0x8733  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x8738  brtrue.s loc_8741
0x873a  ldarg.0
0x873b  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::NotFound()
0x8740  ret
0x8741  ldarg.2
0x8742  dup
0x8743  brtrue.s loc_874B
0x8745  pop
0x8746  newobj   instance void [Microsoft.AspNet.OData]Microsoft.AspNet.OData.ODataActionParameters::.ctor()
0x874b  starg.s  2
0x874d  ldarg.2
0x874e  ldstr    aParameters// "Parameters"
0x8753  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x8758  brtrue.s loc_8766
0x875a  ldc.i4.0
0x875b  newarr   [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter
0x8760  stloc.s  4
0x8762  ldloc.s  4
0x8764  br.s     loc_8776
0x8766  ldarg.2
0x8767  ldstr    aParameters// "Parameters"
0x876c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x8771  isinst   class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>
0x8776  stloc.1
0x8777  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor()
0x877c  dup
0x877d  ldc.i4   0xC8
0x8782  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x8787  stloc.2
0x8788  ldarg.0
0x8789  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x878e  call     class [Microsoft.Owin]Microsoft.Owin.IOwinContext [System.Web.Http.Owin]System.Net.Http.OwinHttpRequestMessageExtensions::GetOwinContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x8793  ldstr    aCancompress// "CanCompress"
0x8798  callvirt T0x2B00007A
0x879d  brfalse.s loc_87E0
0x879f  ldarg.0
0x87a0  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_dataService
0x87a5  ldarg.0
0x87a6  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x87ab  ldloc.0
0x87ac  ldloc.1
0x87ad  ldarg.3
0x87ae  ldloca.s 3
0x87b0  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService::GetCompressedDataSetTableJson(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>, valuetype [mscorlib]System.Nullable`1<int32>, bool&)
0x87b5  stloc.s  5
0x87b7  ldloc.2
0x87b8  ldloc.s  5
0x87ba  newobj   instance void [System.Net.Http]System.Net.Http.ByteArrayContent::.ctor(unsigned int8[])
0x87bf  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x87c4  ldloc.2
0x87c5  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x87ca  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x87cf  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<string> [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentEncoding()
0x87d4  ldstr    aGzip// "gzip"
0x87d9  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x87de  br.s     loc_8805
0x87e0  ldarg.0
0x87e1  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_dataService
0x87e6  ldarg.0
0x87e7  call     instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web.Http]System.Web.Http.ApiController::get_User()
0x87ec  ldloc.0
0x87ed  ldloc.1
0x87ee  ldarg.3
0x87ef  ldloca.s 3
0x87f1  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Services.IDataService::GetDataSetTableJson(class [mscorlib]System.Security.Principal.IPrincipal, valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter>, valuetype [mscorlib]System.Nullable`1<int32>, bool&)
0x87f6  stloc.s  6
0x87f8  ldloc.2
0x87f9  ldloc.s  6
0x87fb  newobj   instance void [System.Net.Http]System.Net.Http.StringContent::.ctor(string)
0x8800  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x8805  ldloc.2
0x8806  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x880b  ldstr    aDatasetjsoncac// "DataSetJsonCached"
0x8810  ldloca.s 3
0x8812  call     instance string [mscorlib]System.Boolean::ToString()
0x8817  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x881c  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Add(string, string)
0x8821  ldloc.2
0x8822  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x8827  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x882c  ldstr    aApplicationJso// "application/json"
0x8831  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x8836  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentType(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue)
0x883b  ldarg.0
0x883c  ldloc.2
0x883d  call     instance class [System.Web.Http]System.Web.Http.Results.ResponseMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::ResponseMessage(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0x8842  ret
```
