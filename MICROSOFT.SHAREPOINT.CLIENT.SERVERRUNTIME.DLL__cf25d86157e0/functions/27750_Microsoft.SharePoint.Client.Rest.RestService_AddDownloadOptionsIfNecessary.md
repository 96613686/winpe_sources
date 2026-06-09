# Microsoft.SharePoint.Client.Rest.RestService::AddDownloadOptionsIfNecessary

- ea: `0x27750`
- end: `0x277e3`
- name: `Microsoft.SharePoint.Client.Rest.RestService::AddDownloadOptionsIfNecessary`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x26da0`

## callees

- `0x27750`

## string_xrefs

- `0x277a3`: `noopen`

## pseudocode

```c

```

## disassembly

```asm
0x27750  ldarg.1
0x27751  ldstr    aXml// "xml"
0x27756  ldc.i4.5
0x27757  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2775c  ldc.i4.0
0x2775d  bge      loc_277E2
0x27762  ldarg.1
0x27763  ldstr    aJson// "json"
0x27768  ldc.i4.5
0x27769  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2776e  ldc.i4.0
0x2776f  bge.s    loc_277E2
0x27771  ldarg.1
0x27772  ldstr    aJpeg// "jpeg"
0x27777  ldc.i4.5
0x27778  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2777d  ldc.i4.0
0x2777e  bge.s    loc_277E2
0x27780  ldarg.1
0x27781  ldstr    aPng// "png"
0x27786  ldc.i4.5
0x27787  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2778c  ldc.i4.0
0x2778d  bge.s    loc_277E2
0x2778f  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x27794  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x27799  callvirt instance class [System]System.Net.WebHeaderCollection [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::get_Headers()
0x2779e  ldstr    aXDownloadOptio// "X-Download-Options"
0x277a3  ldstr    aNoopen// "noopen"
0x277a8  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x277ad  ldstr    aAttachment// "attachment"
0x277b2  stloc.0
0x277b3  ldarg.2
0x277b4  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x277b9  brtrue.s loc_277C8
0x277bb  ldloc.0
0x277bc  ldstr    aFilename// "; filename="
0x277c1  ldarg.2
0x277c2  call     string [mscorlib]System.String::Concat(string, string, string)
0x277c7  stloc.0
0x277c8  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x277cd  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_OutgoingResponse()
0x277d2  callvirt instance class [System]System.Net.WebHeaderCollection [System.ServiceModel.Web]System.ServiceModel.Web.OutgoingWebResponseContext::get_Headers()
0x277d7  ldstr    aContentDisposi// "Content-Disposition"
0x277dc  ldloc.0
0x277dd  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x277e2  ret
```
