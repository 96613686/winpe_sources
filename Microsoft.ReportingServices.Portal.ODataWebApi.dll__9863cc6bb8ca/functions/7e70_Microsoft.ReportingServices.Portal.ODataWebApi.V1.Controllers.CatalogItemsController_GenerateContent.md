# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::GenerateContent

- ea: `0x7e70`
- end: `0x7f44`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::GenerateContent`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2ee0`
- `0x7f50`

## callees

- `0x7e70`

## pseudocode

```c

```

## disassembly

```asm
0x7e70  ldarg.1
0x7e71  brfalse  loc_7F3D
0x7e76  ldarg.1
0x7e77  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::GetContentStream()
0x7e7c  stloc.0
0x7e7d  ldloc.0
0x7e7e  brfalse  loc_7F31
0x7e83  ldnull
0x7e84  stloc.1
0x7e85  ldarg.1
0x7e86  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_ContentType()
0x7e8b  ldloca.s 1
0x7e8d  call     bool [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::TryParse(string, class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue&)
0x7e92  pop
0x7e93  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor()
0x7e98  dup
0x7e99  ldc.i4   0xC8
0x7e9e  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x7ea3  dup
0x7ea4  ldloc.0
0x7ea5  ldarg.0
0x7ea6  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_catalogItemControllerHelper
0x7eab  ldfld    int32 class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::StreamResponseBufferSizeInBytes
0x7eb0  newobj   instance void [System.Net.Http]System.Net.Http.StreamContent::.ctor(class [mscorlib]System.IO.Stream, int32)
0x7eb5  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x7eba  stloc.2
0x7ebb  ldarg.2
0x7ebc  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [Microsoft.AspNet.OData]Microsoft.AspNet.OData.Routing.ODataPath::get_Segments()
0x7ec1  call     T0x2B000045
0x7ec6  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.ValueSegment
0x7ecb  brfalse.s loc_7F31
0x7ecd  ldstr    aAttachment// "attachment"
0x7ed2  stloc.3
0x7ed3  ldloc.1
0x7ed4  brfalse.s loc_7EE7
0x7ed6  ldloc.2
0x7ed7  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x7edc  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x7ee1  ldloc.1
0x7ee2  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentType(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue)
0x7ee7  ldarg.1
0x7ee8  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Type()
0x7eed  ldc.i4.6
0x7eee  bne.un.s loc_7EF6
0x7ef0  ldstr    aInline// "inline"
0x7ef5  stloc.3
0x7ef6  ldloc.2
0x7ef7  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x7efc  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x7f01  ldloc.3
0x7f02  newobj   instance void [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue::.ctor(string)
0x7f07  dup
0x7f08  ldarg.0
0x7f09  ldfld    class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem> Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_catalogItemControllerHelper
0x7f0e  ldarg.0
0x7f0f  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.CatalogItemsController::_catalogRepository
0x7f14  ldarg.1
0x7f15  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Repositories.ICatalogRepository::GetCatalogItemDownloadFileName(class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem)
0x7f1a  callvirt instance string class Microsoft.ReportingServices.Portal.ODataWebApi.Common.CatalogItemControllerHelper`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::EncodeFileNameForMimeHeader(string)
0x7f1f  callvirt instance void [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue::set_FileName(string)
0x7f24  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentDisposition(class [System.Net.Http]System.Net.Http.Headers.ContentDispositionHeaderValue)
0x7f29  ldarg.0
0x7f2a  ldloc.2
0x7f2b  call     instance class [System.Web.Http]System.Web.Http.Results.ResponseMessageResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::ResponseMessage(class [System.Net.Http]System.Net.Http.HttpResponseMessage)
0x7f30  ret
0x7f31  ldarg.0
0x7f32  ldc.i4   0xCC
0x7f37  call     instance class [System.Web.Http]System.Web.Http.Results.StatusCodeResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x7f3c  ret
0x7f3d  ldarg.0
0x7f3e  call     instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult class Microsoft.ReportingServices.Portal.ODataWebApi.Controllers.Reflection.ReflectionODataController`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem>::NotFound()
0x7f43  ret
```
