# Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::ProcessOneOperation

- ea: `0x206e0`
- end: `0x20a51`
- name: `Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::ProcessOneOperation`
- size: `881`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x20510`

## callees

- `0x98e0`
- `0xe010`
- `0xe080`
- `0xe100`
- `0xe6c0`
- `0x12df0`
- `0x152a0`
- `0x187a0`
- `0x18af0`
- `0x20240`
- `0x206d0`
- `0x206e0`
- `0x20a60`
- `0x21e10`
- `0x222f0`
- `0x22910`
- `0x271f0`
- `0x29560`
- `0x297e0`

## string_xrefs

- `0x2086d`: `Url '{0}' is not based on the service uri '{1}'`
- `0x20943`: `Method={0}, Path={1}, Query={2}, accept={3}, ifMatch={4}`

## pseudocode

```c

```

## disassembly

```asm
0x206e0  ldarg.1
0x206e1  ldstr    aAccept// "ACCEPT"
0x206e6  callvirt instance string [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchOperationRequestMessage::GetHeader(string)
0x206eb  stloc.0
0x206ec  ldarg.1
0x206ed  ldstr    aContentType// "CONTENT-TYPE"
0x206f2  callvirt instance string [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchOperationRequestMessage::GetHeader(string)
0x206f7  stloc.1
0x206f8  ldarg.1
0x206f9  ldstr    aIfMatch// "IF-MATCH"
0x206fe  callvirt instance string [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchOperationRequestMessage::GetHeader(string)
0x20703  stloc.2
0x20704  ldarg.1
0x20705  ldstr    aIfNoneMatch// "IF-NONE-MATCH"
0x2070a  callvirt instance string [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchOperationRequestMessage::GetHeader(string)
0x2070f  stloc.3
0x20710  ldarg.1
0x20711  callvirt instance string [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchOperationRequestMessage::get_Method()
0x20716  stloc.s  4
0x20718  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2071d  ldstr    aContenttype0Ac// "ContentType '{0}' AcceptHeader '{1}' If"...
0x20722  ldc.i4.4
0x20723  newarr   [mscorlib]System.Object
0x20728  stloc.s  0x14
0x2072a  ldloc.s  0x14
0x2072c  ldc.i4.0
0x2072d  ldloc.1
0x2072e  stelem.ref
0x2072f  ldloc.s  0x14
0x20731  ldc.i4.1
0x20732  ldloc.0
0x20733  stelem.ref
0x20734  ldloc.s  0x14
0x20736  ldc.i4.2
0x20737  ldloc.2
0x20738  stelem.ref
0x20739  ldloc.s  0x14
0x2073b  ldc.i4.3
0x2073c  ldloc.s  4
0x2073e  stelem.ref
0x2073f  ldloc.s  0x14
0x20741  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x20746  stloc.s  5
0x20748  ldarg.0
0x20749  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x2074e  ldstr    aBatchoperation// "BatchOperation "
0x20753  ldarga.s 3
0x20755  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2075a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2075f  call     string [mscorlib]System.String::Concat(string, string)
0x20764  ldc.i4.1
0x20765  ldloc.s  5
0x20767  callvirt instance class Microsoft.SharePoint.Client.IClientServiceMonitoredScope Microsoft.SharePoint.Client.ClientServiceHost::CreateMonitoredScope(string name, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType, string description)
0x2076c  stloc.s  6
0x2076e  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x20773  callvirt instance void Microsoft.SharePoint.Client.RESTfulOperationContext::Reset()
0x20778  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x2077d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x20782  stloc.s  8
0x20784  ldarg.1
0x20785  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchOperationRequestMessage::get_Headers()
0x2078a  brfalse.s loc_20806
0x2078c  ldarg.1
0x2078d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchOperationRequestMessage::get_Headers()
0x20792  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0x20797  stloc.s  0x15
0x20799  br.s     loc_207EF
0x2079b  ldloc.s  0x15
0x2079d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0x207a2  stloc.s  9
0x207a4  ldloc.s  8
0x207a6  ldloca.s 9
0x207a8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x207ad  ldloca.s 9
0x207af  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x207b4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x207b9  ldarg.0
0x207ba  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x207bf  ldc.i4   0x59E21A
0x207c4  ldc.i4.2
0x207c5  ldstr    aHeader01// "Header {0}={1}"
0x207ca  ldc.i4.2
0x207cb  newarr   [mscorlib]System.Object
0x207d0  stloc.s  0x16
0x207d2  ldloc.s  0x16
0x207d4  ldc.i4.0
0x207d5  ldloca.s 9
0x207d7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x207dc  stelem.ref
0x207dd  ldloc.s  0x16
0x207df  ldc.i4.1
0x207e0  ldloca.s 9
0x207e2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x207e7  stelem.ref
0x207e8  ldloc.s  0x16
0x207ea  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x207ef  ldloc.s  0x15
0x207f1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x207f6  brtrue.s loc_2079B
0x207f8  leave.s  loc_20806
0x207fa  ldloc.s  0x15
0x207fc  brfalse.s loc_20805
0x207fe  ldloc.s  0x15
0x20800  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20805  endfinally
0x20806  ldarg.1
0x20807  ldstr    aContentId// "CONTENT-ID"
0x2080c  callvirt instance string [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchOperationRequestMessage::GetHeader(string)
0x20811  stloc.s  0xA
0x20813  ldarg.1
0x20814  callvirt instance class [System]System.Uri [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchOperationRequestMessage::get_Url()
0x20819  stloc.s  0xB
0x2081b  ldarg.0
0x2081c  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x20821  ldc.i4   0x59E21B
0x20826  ldc.i4.2
0x20827  ldstr    aUrl0// "Url={0}"
0x2082c  ldc.i4.1
0x2082d  newarr   [mscorlib]System.Object
0x20832  stloc.s  0x17
0x20834  ldloc.s  0x17
0x20836  ldc.i4.0
0x20837  ldloc.s  0xB
0x20839  stelem.ref
0x2083a  ldloc.s  0x17
0x2083c  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x20841  ldloc.s  0xB
0x20843  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x20848  brfalse  loc_208E4
0x2084d  ldarg.0
0x2084e  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x20853  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.ClientServiceHost::get_ServiceBaseUriWithPathPartition()
0x20858  ldloc.s  0xB
0x2085a  callvirt instance bool [System]System.Uri::IsBaseOf(class [System]System.Uri)
0x2085f  brtrue.s loc_2089C
0x20861  ldarg.0
0x20862  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x20867  ldc.i4   0x59E21C
0x2086c  ldc.i4.1
0x2086d  ldstr    aUrl0IsNotBased// "Url '{0}' is not based on the service u"...
0x20872  ldc.i4.2
0x20873  newarr   [mscorlib]System.Object
0x20878  stloc.s  0x18
0x2087a  ldloc.s  0x18
0x2087c  ldc.i4.0
0x2087d  ldloc.s  0xB
0x2087f  stelem.ref
0x20880  ldloc.s  0x18
0x20882  ldc.i4.1
0x20883  ldarg.0
0x20884  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x20889  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.ClientServiceHost::get_ServiceBaseUriWithPathPartition()
0x2088e  stelem.ref
0x2088f  ldloc.s  0x18
0x20891  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x20896  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x2089b  throw
0x2089c  ldloc.s  0xB
0x2089e  ldc.i4.s 0x10
0x208a0  ldc.i4.2
0x208a1  callvirt instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x208a6  stloc.s  0xC
0x208a8  ldarg.0
0x208a9  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x208ae  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.ClientServiceHost::get_ServiceBaseUriWithPathPartition()
0x208b3  ldc.i4.s 0x10
0x208b5  ldc.i4.2
0x208b6  callvirt instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x208bb  stloc.s  0xE
0x208bd  ldloc.s  0xC
0x208bf  ldloc.s  0xE
0x208c1  ldc.i4.5
0x208c2  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x208c7  brfalse.s loc_208D9
0x208c9  ldloc.s  0xC
0x208cb  ldloc.s  0xE
0x208cd  callvirt instance int32 [mscorlib]System.String::get_Length()
0x208d2  callvirt instance string [mscorlib]System.String::Substring(int32)
0x208d7  stloc.s  0xC
0x208d9  ldloc.s  0xB
0x208db  callvirt instance string [System]System.Uri::get_Query()
0x208e0  stloc.s  0xD
0x208e2  br.s     loc_20937
0x208e4  ldloc.s  0xB
0x208e6  callvirt instance string [System]System.Uri::get_OriginalString()
0x208eb  ldc.i4.s 0x3F
0x208ed  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x208f2  stloc.s  0xF
0x208f4  ldloc.s  0xF
0x208f6  ldc.i4.0
0x208f7  ble.s    loc_2091E
0x208f9  ldloc.s  0xB
0x208fb  callvirt instance string [System]System.Uri::get_OriginalString()
0x20900  ldc.i4.0
0x20901  ldloc.s  0xF
0x20903  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x20908  stloc.s  0xC
0x2090a  ldloc.s  0xB
0x2090c  callvirt instance string [System]System.Uri::get_OriginalString()
0x20911  ldloc.s  0xF
0x20913  ldc.i4.1
0x20914  add
0x20915  callvirt instance string [mscorlib]System.String::Substring(int32)
0x2091a  stloc.s  0xD
0x2091c  br.s     loc_2092E
0x2091e  ldloc.s  0xB
0x20920  callvirt instance string [System]System.Uri::get_OriginalString()
0x20925  stloc.s  0xC
0x20927  ldsfld   string [mscorlib]System.String::Empty
0x2092c  stloc.s  0xD
0x2092e  ldloc.s  0xC
0x20930  call     string [System]System.Uri::UnescapeDataString(string)
0x20935  stloc.s  0xC
0x20937  ldarg.0
0x20938  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x2093d  ldc.i4   0x59E21D
0x20942  ldc.i4.2
0x20943  ldstr    aMethod0Path1Qu// "Method={0}, Path={1}, Query={2}, accept"...
0x20948  ldc.i4.5
0x20949  newarr   [mscorlib]System.Object
0x2094e  stloc.s  0x19
0x20950  ldloc.s  0x19
0x20952  ldc.i4.0
0x20953  ldloc.s  4
0x20955  stelem.ref
0x20956  ldloc.s  0x19
0x20958  ldc.i4.1
0x20959  ldloc.s  0xC
0x2095b  stelem.ref
0x2095c  ldloc.s  0x19
0x2095e  ldc.i4.2
0x2095f  ldloc.s  0xD
0x20961  stelem.ref
0x20962  ldloc.s  0x19
0x20964  ldc.i4.3
0x20965  ldloc.0
0x20966  stelem.ref
0x20967  ldloc.s  0x19
0x20969  ldc.i4.4
0x2096a  ldloc.2
0x2096b  stelem.ref
0x2096c  ldloc.s  0x19
0x2096e  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x20973  ldloc.s  0xD
0x20975  call     class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpUtility::ParseQueryString(string)
0x2097a  stloc.s  0x10
0x2097c  ldarg.1
0x2097d  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchOperationRequestMessage::GetStream()
0x20982  stloc.s  0x11
0x20984  ldloc.s  0x11
0x20986  ldarg.0
0x20987  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x2098c  ldarg.0
0x2098d  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x20992  ldloc.s  4
0x20994  ldloc.0
0x20995  ldloc.s  0xC
0x20997  ldloc.s  0x10
0x20999  ldloc.2
0x2099a  ldloc.3
0x2099b  ldloc.s  8
0x2099d  ldarg.0
0x2099e  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class [mscorlib]System.IDisposable> Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::m_pendingDisposableContainer
0x209a3  newobj   instance void Microsoft.SharePoint.Client.Rest.RestRequestProcessor::.ctor(class [mscorlib]System.IO.Stream inputStream, class Microsoft.SharePoint.Client.ClientServiceHost host, class Microsoft.SharePoint.Client.ProxyContext proxyContext, string httpMethod, string accept, string path, class [System]System.Collections.Specialized.NameValueCollection queryStrings, string etagIfMatch, string etagIfNoneMatch, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> headers, class [mscorlib]System.Collections.Generic.IList`1<class [mscorlib]System.IDisposable> pendingDisposableQueue)
0x209a8  stloc.s  0x12
0x209aa  ldarg.0
0x209ab  ldloc.s  0x12
0x209ad  call     instance void Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::set_CurrentRequestProcessor(class Microsoft.SharePoint.Client.Rest.RestRequestProcessor value)
0x209b2  ldarg.0
0x209b3  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x209b8  ldarg.0
0x209b9  ldfld    valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::m_dtTimeout
0x209be  call     void Microsoft.SharePoint.Client.Utility::ThrowIfTimeout(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost, valuetype [mscorlib]System.DateTime dtTimeout)
0x209c3  ldloc.s  0x12
0x209c5  callvirt instance class Microsoft.SharePoint.Client.RestRequestResult Microsoft.SharePoint.Client.Rest.RestRequestProcessor::Process()
0x209ca  stloc.s  7
0x209cc  ldloc.s  0xA
0x209ce  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x209d3  brtrue.s loc_209F8
0x209d5  ldarg.0
0x209d6  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x209db  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Client.ProxyContext::get_RESTfulBatchResultObjects()
0x209e0  ldstr    asc_3E5F2// "$"
0x209e5  ldloc.s  0xA
0x209e7  call     string [mscorlib]System.String::Concat(string, string)
0x209ec  ldloc.s  0x12
0x209ee  callvirt instance object Microsoft.SharePoint.Client.Rest.RestRequestProcessor::get_ResultEntity()
0x209f3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x209f8  leave.s  loc_20A02
0x209fa  ldarg.0
0x209fb  ldnull
0x209fc  call     instance void Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::set_CurrentRequestProcessor(class Microsoft.SharePoint.Client.Rest.RestRequestProcessor value)
0x20a01  endfinally
0x20a02  leave.s  loc_20A10
0x20a04  ldloc.s  0x11
0x20a06  brfalse.s loc_20A0F
0x20a08  ldloc.s  0x11
0x20a0a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20a0f  endfinally
0x20a10  leave.s  loc_20A39
  ... truncated ...
```
