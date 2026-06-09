# Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::GenerateContent

- ea: `0xc1c0`
- end: `0xc2e6`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1::GenerateContent`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xc1c0`

## pseudocode

```c

```

## disassembly

```asm
0xc1c0  ldarg.1
0xc1c1  box      var<u1>
0xc1c6  brfalse  loc_C2DA
0xc1cb  ldarg.1
0xc1cc  box      var<u1>
0xc1d1  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0xc1d6  brtrue.s loc_C1E8
0xc1d8  ldarg.1
0xc1d9  box      var<u1>
0xc1de  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::GetContentStream()
0xc1e3  brfalse  loc_C2C9
0xc1e8  ldnull
0xc1e9  stloc.0
0xc1ea  ldarg.1
0xc1eb  box      var<u1>
0xc1f0  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_ContentType()
0xc1f5  ldloca.s 0
0xc1f7  call     bool [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::TryParse(string, class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue&)
0xc1fc  pop
0xc1fd  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor()
0xc202  stloc.1
0xc203  ldloc.1
0xc204  ldc.i4   0xC8
0xc209  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_StatusCode(valuetype [System]System.Net.HttpStatusCode)
0xc20e  ldarg.1
0xc20f  box      var<u1>
0xc214  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::GetContentStream()
0xc219  brfalse.s loc_C239
0xc21b  ldloc.1
0xc21c  ldarg.1
0xc21d  box      var<u1>
0xc222  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::GetContentStream()
0xc227  ldarg.0
0xc228  ldfld    int32 class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::StreamResponseBufferSizeInBytes
0xc22d  newobj   instance void [System.Net.Http]System.Net.Http.StreamContent::.ctor(class [mscorlib]System.IO.Stream, int32)
0xc232  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0xc237  br.s     loc_C24F
0xc239  ldloc.1
0xc23a  ldarg.1
0xc23b  box      var<u1>
0xc240  callvirt instance unsigned int8[] [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Content()
0xc245  newobj   instance void [System.Net.Http]System.Net.Http.ByteArrayContent::.ctor(unsigned int8[])
0xc24a  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0xc24f  ldarg.2
0xc250  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_Segments()
0xc255  call     T0x2B000045
0xc25a  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.ValueSegment
0xc25f  brfalse.s loc_C2C9
0xc261  ldstr    aAttachment// "attachment"
0xc266  stloc.2
0xc267  ldloc.0
0xc268  brfalse.s loc_C27B
0xc26a  ldloc.1
0xc26b  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0xc270  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0xc275  ldloc.0
0xc276  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentType(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue)
0xc27b  ldarg.1
0xc27c  box      var<u1>
0xc281  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0xc286  ldc.i4.6
0xc287  bne.un.s loc_C28F
0xc289  ldstr    aInline// "inline"
0xc28e  stloc.2
0xc28f  ldloc.1
0xc290  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0xc295  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0xc29a  ldloc.2
0xc29b  newobj   instance void [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue::.ctor(string)
0xc2a0  dup
0xc2a1  ldarg.0
0xc2a2  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogRepository
0xc2a7  ldarg.1
0xc2a8  box      var<u1>
0xc2ad  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItemDownloadFileName(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem)
0xc2b2  callvirt instance void [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue::set_FileName(string)
0xc2b7  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentDisposition(class [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue)
0xc2bc  ldarg.0
0xc2bd  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc2c2  ldloc.1
0xc2c3  callvirt instance class [System.Web.Http]System.Web.Http.Results.ResponseMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::ResponseMessage(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0xc2c8  ret
0xc2c9  ldarg.0
0xc2ca  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc2cf  ldc.i4   0xCC
0xc2d4  callvirt instance class [System.Web.Http]System.Web.Http.Results.StatusCodeResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::StatusCode(valuetype [System]System.Net.HttpStatusCode)
0xc2d9  ret
0xc2da  ldarg.0
0xc2db  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.EntitySetReflectionODataController`1<var<u1>> class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<var<u1>>::_catalogItemController
0xc2e0  callvirt instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<var<u1>>::NotFound()
0xc2e5  ret
```
