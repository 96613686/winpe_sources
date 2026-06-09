# Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ProcessMetadata

- ea: `0x242a0`
- end: `0x24395`
- name: `Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ProcessMetadata`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x222f0`

## callees

- `0x98e0`
- `0xe080`
- `0x16830`
- `0x16b90`
- `0x19990`
- `0x1ce70`
- `0x20240`
- `0x21bc0`
- `0x22c30`
- `0x23e20`
- `0x242a0`
- `0x26780`
- `0x27510`
- `0x29560`
- `0x29650`

## string_xrefs

- `0x242e0`: `application/xml`

## pseudocode

```c

```

## disassembly

```asm
0x242a0  ldnull
0x242a1  stloc.0
0x242a2  ldarg.0
0x242a3  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x242a8  ldloca.s 0
0x242aa  call     string Microsoft.SharePoint.Client.ProxyMap::GetMetadataDocumentName(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost, [out] class [mscorlib]System.Reflection.Assembly& assembly)
0x242af  stloc.1
0x242b0  ldarg.0
0x242b1  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_queryStrings
0x242b6  ldstr    aServergenerate// "servergeneratedmetadata"
0x242bb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x242c0  ldstr    a1// "1"
0x242c5  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x242ca  brfalse.s loc_242F8
0x242cc  ldloc.1
0x242cd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x242d2  brtrue.s loc_242F8
0x242d4  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x242d9  brfalse.s loc_242EA
0x242db  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x242e0  ldstr    aApplicationXml// "application/xml"
0x242e5  callvirt instance void Microsoft.SharePoint.Client.RESTfulOperationContext::set_ResponseStreamContentType(string value)
0x242ea  ldarg.0
0x242eb  ldloc.0
0x242ec  ldloc.1
0x242ed  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(string)
0x242f2  call     instance class Microsoft.SharePoint.Client.RestRequestResult Microsoft.SharePoint.Client.Rest.RestRequestProcessor::GetRestRequestResultWithStream(class [mscorlib]System.IO.Stream rawStream)
0x242f7  ret
0x242f8  ldarg.0
0x242f9  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x242fe  ldc.i4.1
0x242ff  ldnull
0x24300  newobj   instance void Microsoft.SharePoint.Client.Rest.AggregatedEdmModel::.ctor(class Microsoft.SharePoint.Client.ProxyContext proxyContext, valuetype Microsoft.SharePoint.Client.EdmModelUsage usage, [opt] object target)
0x24305  stloc.2
0x24306  ldarg.0
0x24307  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x2430c  call     class [System]System.Collections.Generic.ISet`1<string> Microsoft.SharePoint.Client.ProxyMap::GetExcludedFromMetadataDocumentTypeFullNames(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x24311  stloc.3
0x24312  ldloc.2
0x24313  ldloc.3
0x24314  ldarg.0
0x24315  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x2431a  newobj   instance void Microsoft.SharePoint.Client.Rest.FilteredEdmModelForMetadataDocument::.ctor(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel model, class [System]System.Collections.Generic.ISet`1<string> excludedTypeFullNames, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2431f  stloc.2
0x24320  ldarg.0
0x24321  ldfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_outputStream
0x24326  ldarg.0
0x24327  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_acceptHeaderValue
0x2432c  ldarg.0
0x2432d  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_host
0x24332  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.ClientServiceHost::get_ServiceBaseUriWithPathPartition()
0x24337  ldloc.2
0x24338  ldc.i4.s 9
0x2433a  ldarg.0
0x2433b  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x24340  ldarg.0
0x24341  ldfld    class Microsoft.SharePoint.Client.RESTfulQuery Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_query
0x24346  ldloca.s 4
0x24348  call     class [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter Microsoft.SharePoint.Client.Rest.RestService::CreateODataMessageWriter(class [mscorlib]System.IO.Stream stream, string orginalAcceptHeaderValue, class [System]System.Uri serviceBaseUri, class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel edmModel, valuetype [Microsoft.Data.OData]Microsoft.Data.OData.ODataPayloadKind payloadKind, class Microsoft.SharePoint.Client.ClientServiceHost serviceHost, class Microsoft.SharePoint.Client.RESTfulQuery query, [out] class Microsoft.SharePoint.Client.Rest.RestResponseMessage& responseMessage)
0x2434d  stloc.s  5
0x2434f  ldloc.2
0x24350  ldc.i4.1
0x24351  ldc.i4.0
0x24352  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32)
0x24357  call     void [Microsoft.Data.Edm]Microsoft.Data.Edm.Csdl.SerializationExtensionMethods::SetEdmxVersion(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel, class [mscorlib]System.Version)
0x2435c  ldloc.2
0x2435d  ldc.i4.3
0x2435e  ldc.i4.0
0x2435f  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32)
0x24364  call     void [Microsoft.Data.Edm]Microsoft.Data.Edm.Csdl.SerializationExtensionMethods::SetMaxDataServiceVersion(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel, class [mscorlib]System.Version)
0x24369  ldloc.s  5
0x2436b  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter::WriteMetadataDocument()
0x24370  ldloc.s  4
0x24372  callvirt instance string Microsoft.SharePoint.Client.Rest.RestResponseMessage::GetContentType()
0x24377  ldarg.0
0x24378  call     instance class Microsoft.SharePoint.Utilities.ChunkStreamBuilder Microsoft.SharePoint.Client.Rest.RestRequestProcessor::DetachStreamBuilder()
0x2437d  newobj   instance void Microsoft.SharePoint.Client.RestRequestResult::.ctor(string contentType, class Microsoft.SharePoint.Utilities.ChunkStreamBuilder streamBuilder)
0x24382  stloc.s  6
0x24384  leave.s  loc_24392
0x24386  ldloc.s  5
0x24388  brfalse.s loc_24391
0x2438a  ldloc.s  5
0x2438c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24391  endfinally
0x24392  ldloc.s  6
0x24394  ret
```
