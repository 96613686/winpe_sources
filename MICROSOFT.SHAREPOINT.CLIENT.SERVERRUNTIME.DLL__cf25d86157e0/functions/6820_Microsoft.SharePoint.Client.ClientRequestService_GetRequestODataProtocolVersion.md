# Microsoft.SharePoint.Client.ClientRequestService::GetRequestODataProtocolVersion

- ea: `0x6820`
- end: `0x69be`
- name: `Microsoft.SharePoint.Client.ClientRequestService::GetRequestODataProtocolVersion`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x69f0`

## callees

- `0x6820`
- `0xe000`
- `0xe010`
- `0x16850`
- `0x18900`

## string_xrefs

- `0x684b`: `DATASERVICEVERSION`
- `0x68c4`: `DATASERVICEVERSION`
- `0x692a`: `Overwrite protocol version to be V4`
- `0x699e`: `The partition's default odata protocol is {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6820  ldc.i4.0
0x6821  stloc.0
0x6822  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x6827  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.IncomingWebRequestContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_IncomingRequest()
0x682c  callvirt instance class [System]System.Net.WebHeaderCollection [System.ServiceModel.Web]System.ServiceModel.Web.IncomingWebRequestContext::get_Headers()
0x6831  ldstr    aOdataVersion// "ODATA-VERSION"
0x6836  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x683b  stloc.1
0x683c  call     class [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_Current()
0x6841  callvirt instance class [System.ServiceModel.Web]System.ServiceModel.Web.IncomingWebRequestContext [System.ServiceModel.Web]System.ServiceModel.Web.WebOperationContext::get_IncomingRequest()
0x6846  callvirt instance class [System]System.Net.WebHeaderCollection [System.ServiceModel.Web]System.ServiceModel.Web.IncomingWebRequestContext::get_Headers()
0x684b  ldstr    aDataservicever// "DATASERVICEVERSION"
0x6850  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6855  stloc.2
0x6856  ldloc.2
0x6857  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x685c  brtrue.s loc_68D6
0x685e  ldloc.2
0x685f  ldc.i4.1
0x6860  newarr   [mscorlib]System.Char
0x6865  stloc.s  6
0x6867  ldloc.s  6
0x6869  ldc.i4.0
0x686a  ldc.i4.s 0x3B
0x686c  stelem.i2
0x686d  ldloc.s  6
0x686f  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x6874  stloc.3
0x6875  ldloc.3
0x6876  brfalse.s loc_68AD
0x6878  ldloc.3
0x6879  ldlen
0x687a  conv.i4
0x687b  ldc.i4.0
0x687c  ble.s    loc_68AD
0x687e  ldloc.3
0x687f  ldc.i4.0
0x6880  ldelem.ref
0x6881  brfalse.s loc_68AD
0x6883  ldstr    a30// "3.0"
0x6888  ldloc.3
0x6889  ldc.i4.0
0x688a  ldelem.ref
0x688b  callvirt instance string [mscorlib]System.String::Trim()
0x6890  ldc.i4.5
0x6891  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x6896  brfalse.s loc_68AD
0x6898  ldarg.0
0x6899  ldc.i4   0x65C842
0x689e  ldc.i4.3
0x689f  ldstr    aHasOdatav3Requ// "Has ODataV3 request header"
0x68a4  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x68a9  ldc.i4.1
0x68aa  stloc.0
0x68ab  br.s     loc_68D6
0x68ad  ldarg.0
0x68ae  ldc.i4   0x65C843
0x68b3  ldc.i4.2
0x68b4  ldstr    aUnknownValueFo// "Unknown value for {0} header. Value={1}"
0x68b9  ldc.i4.2
0x68ba  newarr   [mscorlib]System.Object
0x68bf  stloc.s  7
0x68c1  ldloc.s  7
0x68c3  ldc.i4.0
0x68c4  ldstr    aDataservicever// "DATASERVICEVERSION"
0x68c9  stelem.ref
0x68ca  ldloc.s  7
0x68cc  ldc.i4.1
0x68cd  ldloc.2
0x68ce  stelem.ref
0x68cf  ldloc.s  7
0x68d1  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x68d6  ldloc.1
0x68d7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x68dc  brtrue   loc_6974
0x68e1  ldloc.1
0x68e2  ldc.i4.1
0x68e3  newarr   [mscorlib]System.Char
0x68e8  stloc.s  8
0x68ea  ldloc.s  8
0x68ec  ldc.i4.0
0x68ed  ldc.i4.s 0x3B
0x68ef  stelem.i2
0x68f0  ldloc.s  8
0x68f2  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x68f7  stloc.s  4
0x68f9  ldloc.s  4
0x68fb  brfalse.s loc_694B
0x68fd  ldloc.s  4
0x68ff  ldlen
0x6900  conv.i4
0x6901  ldc.i4.0
0x6902  ble.s    loc_694B
0x6904  ldloc.s  4
0x6906  ldc.i4.0
0x6907  ldelem.ref
0x6908  brfalse.s loc_694B
0x690a  ldstr    a40// "4.0"
0x690f  ldloc.s  4
0x6911  ldc.i4.0
0x6912  ldelem.ref
0x6913  callvirt instance string [mscorlib]System.String::Trim()
0x6918  ldc.i4.5
0x6919  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x691e  brfalse.s loc_694B
0x6920  ldloc.0
0x6921  brfalse.s loc_6936
0x6923  ldarg.0
0x6924  ldc.i4   0x65C844
0x6929  ldc.i4.2
0x692a  ldstr    aOverwriteProto// "Overwrite protocol version to be V4"
0x692f  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x6934  br.s     loc_6947
0x6936  ldarg.0
0x6937  ldc.i4   0x65C845
0x693c  ldc.i4.3
0x693d  ldstr    aHasOdatav4Requ// "Has ODATAV4 request header"
0x6942  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x6947  ldc.i4.2
0x6948  stloc.0
0x6949  br.s     loc_6974
0x694b  ldarg.0
0x694c  ldc.i4   0x65C846
0x6951  ldc.i4.2
0x6952  ldstr    aUnknownValueFo// "Unknown value for {0} header. Value={1}"
0x6957  ldc.i4.2
0x6958  newarr   [mscorlib]System.Object
0x695d  stloc.s  9
0x695f  ldloc.s  9
0x6961  ldc.i4.0
0x6962  ldstr    aOdataVersion// "ODATA-VERSION"
0x6967  stelem.ref
0x6968  ldloc.s  9
0x696a  ldc.i4.1
0x696b  ldloc.1
0x696c  stelem.ref
0x696d  ldloc.s  9
0x696f  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x6974  ldloc.0
0x6975  brtrue.s loc_69BC
0x6977  ldloc.2
0x6978  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x697d  brfalse.s loc_69BC
0x697f  ldloc.1
0x6980  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6985  brfalse.s loc_69BC
0x6987  call     string Microsoft.SharePoint.Client.Utility::GetWebOperationContextIncomingRequestQueryPath()
0x698c  stloc.s  5
0x698e  ldarg.0
0x698f  ldloc.s  5
0x6991  call     valuetype Microsoft.SharePoint.Client.ODataProtocolVersion Microsoft.SharePoint.Client.ProxyMap::GetDefaultODataProtocolVersion(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost, string path)
0x6996  stloc.0
0x6997  ldarg.0
0x6998  ldc.i4   0x65C847
0x699d  ldc.i4.3
0x699e  ldstr    aThePartitionSD// "The partition's default odata protocol "...
0x69a3  ldc.i4.1
0x69a4  newarr   [mscorlib]System.Object
0x69a9  stloc.s  0xA
0x69ab  ldloc.s  0xA
0x69ad  ldc.i4.0
0x69ae  ldloc.0
0x69af  box      Microsoft.SharePoint.Client.ODataProtocolVersion
0x69b4  stelem.ref
0x69b5  ldloc.s  0xA
0x69b7  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x69bc  ldloc.0
0x69bd  ret
```
