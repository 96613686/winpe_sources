# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1::GenerateContent

- ea: `0x2260`
- end: `0x2321`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1::GenerateContent`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2260`

## pseudocode

```c

```

## disassembly

```asm
0x2260  ldarg.1
0x2261  brfalse  loc_231A
0x2266  ldarg.1
0x2267  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x226c  brfalse  loc_230E
0x2271  ldnull
0x2272  stloc.0
0x2273  ldarg.1
0x2274  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_ContentType()
0x2279  ldloca.s 0
0x227b  call     bool [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::TryParse(string, class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue&)
0x2280  pop
0x2281  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor()
0x2286  stloc.1
0x2287  ldloc.1
0x2288  ldc.i4   0xC8
0x228d  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x2292  ldloc.1
0x2293  ldarg.1
0x2294  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0x2299  newobj   instance void [System.Net.Http]System.Net.Http.ByteArrayContent::.ctor(unsigned int8[])
0x229e  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x22a3  ldarg.2
0x22a4  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_Segments()
0x22a9  call     T0x2B000045
0x22ae  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.ValueSegment
0x22b3  brfalse.s loc_230E
0x22b5  ldstr    aAttachment// "attachment"
0x22ba  stloc.2
0x22bb  ldloc.0
0x22bc  brfalse.s loc_22CF
0x22be  ldloc.1
0x22bf  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x22c4  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x22c9  ldloc.0
0x22ca  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentType(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue)
0x22cf  ldarg.1
0x22d0  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x22d5  ldc.i4.6
0x22d6  bne.un.s loc_22DE
0x22d8  ldstr    aInline// "inline"
0x22dd  stloc.2
0x22de  ldloc.1
0x22df  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x22e4  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x22e9  ldloc.2
0x22ea  newobj   instance void [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue::.ctor(string)
0x22ef  dup
0x22f0  ldarg.0
0x22f1  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.CatalogItemController`1<var<u1>>::_catalogRepository
0x22f6  ldarg.1
0x22f7  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItemDownloadFileName(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem)
0x22fc  callvirt instance void [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue::set_FileName(string)
0x2301  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentDisposition(class [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue)
0x2306  ldarg.0
0x2307  ldloc.1
0x2308  call     instance class [System.Web.Http]System.Web.Http.Results.ResponseMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::ResponseMessage(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0x230d  ret
0x230e  ldarg.0
0x230f  ldc.i4   0xCC
0x2314  call     instance class [System.Web.Http]System.Web.Http.Results.StatusCodeResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x2319  ret
0x231a  ldarg.0
0x231b  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::NotFound()
0x2320  ret
```
