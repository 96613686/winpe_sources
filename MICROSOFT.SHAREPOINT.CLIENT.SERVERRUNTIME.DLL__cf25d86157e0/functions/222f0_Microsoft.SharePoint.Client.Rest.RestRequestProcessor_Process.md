# Microsoft.SharePoint.Client.Rest.RestRequestProcessor::Process

- ea: `0x222f0`
- end: `0x22907`
- name: `Microsoft.SharePoint.Client.Rest.RestRequestProcessor::Process`
- size: `1559`
- prototype: ``
- caller_count: `2`
- callee_count: `49`
- tags: `registry_config, broker_com_uri`

## callers

- `0x206e0`
- `0x22270`

## callees

- `0xba0`
- `0x2c20`
- `0x2d00`
- `0x2d70`
- `0x2f10`
- `0x98e0`
- `0xe000`
- `0xe010`
- `0xe080`
- `0xe110`
- `0xe6c0`
- `0x12df0`
- `0x15030`
- `0x15040`
- `0x15060`
- `0x152f0`
- `0x16920`
- `0x1d6b0`
- `0x1ee90`
- `0x1f380`
- `0x20240`
- `0x20310`
- `0x21690`
- `0x21820`
- `0x21bc0`
- `0x21c60`
- `0x21cc0`
- `0x21ce0`
- `0x21d20`
- `0x222f0`
- `0x22920`
- `0x229a0`
- `0x229d0`
- `0x22a00`
- `0x22bc0`
- `0x22c30`
- `0x23630`
- `0x23760`
- `0x23a20`
- `0x23c50`
- `0x23e20`
- `0x23f10`
- `0x242a0`
- `0x243a0`
- `0x24410`
- `0x26360`
- `0x26780`
- `0x274f0`
- `0x27510`

## string_xrefs

- `0x223fa`: `application/json`
- `0x224a1`: `application/json`
- `0x22692`: `application/json`
- `0x2270d`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x222f0  ldarg.0
0x222f1  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_originalPath
0x222f6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x222fb  brfalse.s loc_22304
0x222fd  ldarg.0
0x222fe  call     instance class Microsoft.SharePoint.Client.RestRequestResult Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ProcessServiceDocument()
0x22303  ret
0x22304  ldarg.0
0x22305  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_originalPath
0x2230a  ldstr    aMetadata// "$metadata"
0x2230f  ldc.i4.5
0x22310  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x22315  brfalse.s loc_2231E
0x22317  ldarg.0
0x22318  call     instance class Microsoft.SharePoint.Client.RestRequestResult Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ProcessMetadata()
0x2231d  ret
0x2231e  ldarg.0
0x2231f  ldarg.0
0x22320  call     instance class Microsoft.SharePoint.Client.RESTfulQuery Microsoft.SharePoint.Client.Rest.RestRequestProcessor::CreateRestQueryFromQueryStrings()
0x22325  stfld    class Microsoft.SharePoint.Client.RESTfulQuery Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_query
0x2232a  ldarg.0
0x2232b  ldc.i4.1
0x2232c  ldarg.0
0x2232d  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_path
0x22332  ldarg.0
0x22333  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_originalPath
0x22338  call     instance class ObjectWithPathName Microsoft.SharePoint.Client.Rest.RestRequestProcessor::GetObjectFromPath(bool mainRequestPath, string path, string pathForErrorMessage)
0x2233d  stloc.0
0x2233e  ldloc.0
0x2233f  brtrue.s loc_22378
0x22341  ldarg.0
0x22342  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x22347  ldc.i4   0x1C50C6
0x2234c  ldc.i4.2
0x2234d  ldstr    aCannotFindReso// "Cannot find resource at {0}"
0x22352  ldc.i4.1
0x22353  newarr   [mscorlib]System.Object
0x22358  stloc.s  0x18
0x2235a  ldloc.s  0x18
0x2235c  ldc.i4.0
0x2235d  ldarg.0
0x2235e  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_originalPath
0x22363  stelem.ref
0x22364  ldloc.s  0x18
0x22366  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x2236b  ldarg.0
0x2236c  ldarg.0
0x2236d  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_originalPath
0x22372  call     instance class Microsoft.SharePoint.Client.ResourceNotFoundException Microsoft.SharePoint.Client.Rest.RestRequestProcessor::CreateResourceNotFoundException(string resource)
0x22377  throw
0x22378  ldnull
0x22379  stloc.1
0x2237a  ldloc.0
0x2237b  ldfld    object ObjectWithPathName::Value
0x22380  brfalse.s loc_22399
0x22382  ldloc.0
0x22383  ldfld    object ObjectWithPathName::Value
0x22388  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2238d  ldarg.0
0x2238e  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_host
0x22393  call     class Microsoft.SharePoint.Client.ServerStub Microsoft.SharePoint.Client.ProxyMap::GetServerStub(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x22398  stloc.1
0x22399  ldarg.0
0x2239a  ldfld    class Microsoft.SharePoint.Client.RESTfulQuery Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_query
0x2239f  callvirt instance class Microsoft.SharePoint.Client.Rest.RestClientQueryableExpression Microsoft.SharePoint.Client.RESTfulQuery::get_QueryableExpression()
0x223a4  ldloc.0
0x223a5  ldfld    class [mscorlib]System.Type ObjectWithPathName::OfTypeFilter
0x223aa  callvirt instance void Microsoft.SharePoint.Client.Rest.RestClientQueryableExpression::set_OfTypeFilter(class [mscorlib]System.Type value)
0x223af  ldarg.0
0x223b0  ldloc.0
0x223b1  ldfld    object ObjectWithPathName::Value
0x223b6  ldloc.1
0x223b7  call     instance void Microsoft.SharePoint.Client.Rest.RestRequestProcessor::EvaluatePreconditions(object entity, class Microsoft.SharePoint.Client.ServerStub serverStub)
0x223bc  ldloc.0
0x223bd  ldfld    bool ObjectWithPathName::PureValue
0x223c2  brfalse  loc_22479
0x223c7  ldloc.1
0x223c8  brfalse.s loc_223D8
0x223ca  ldarg.0
0x223cb  ldloc.0
0x223cc  ldfld    object ObjectWithPathName::Value
0x223d1  ldloc.1
0x223d2  call     instance class Microsoft.SharePoint.Client.RestRequestResult Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ProcessMediaResourceStream(object target, class Microsoft.SharePoint.Client.ServerStub serverStub)
0x223d7  ret
0x223d8  ldloc.0
0x223d9  ldfld    object ObjectWithPathName::Value
0x223de  isinst   [mscorlib]System.IO.Stream
0x223e3  stloc.s  4
0x223e5  ldloc.s  4
0x223e7  brfalse.s loc_223F2
0x223e9  ldarg.0
0x223ea  ldloc.s  4
0x223ec  call     instance class Microsoft.SharePoint.Client.RestRequestResult Microsoft.SharePoint.Client.Rest.RestRequestProcessor::GetRestRequestResultWithStream(class [mscorlib]System.IO.Stream rawStream)
0x223f1  ret
0x223f2  ldarg.0
0x223f3  ldfld    bool Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_suppressEntityBody
0x223f8  brfalse.s loc_2240B
0x223fa  ldstr    aApplicationJso_0// "application/json"
0x223ff  ldarg.0
0x22400  call     instance class Microsoft.SharePoint.Utilities.ChunkStreamBuilder Microsoft.SharePoint.Client.Rest.RestRequestProcessor::DetachStreamBuilder()
0x22405  newobj   instance void Microsoft.SharePoint.Client.RestRequestResult::.ctor(string contentType, class Microsoft.SharePoint.Utilities.ChunkStreamBuilder streamBuilder)
0x2240a  ret
0x2240b  ldarg.0
0x2240c  ldfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_outputStream
0x22411  ldarg.0
0x22412  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_acceptHeaderValue
0x22417  ldarg.0
0x22418  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_host
0x2241d  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.ClientServiceHost::get_ServiceBaseUriWithPathPartition()
0x22422  ldc.i4.5
0x22423  ldarg.0
0x22424  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x22429  ldarg.0
0x2242a  ldfld    class Microsoft.SharePoint.Client.RESTfulQuery Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_query
0x2242f  ldloca.s 3
0x22431  call     class [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter Microsoft.SharePoint.Client.Rest.RestService::CreateODataMessageWriter(class [mscorlib]System.IO.Stream stream, string acceptHeaderValue, class [System]System.Uri serviceBaseUri, valuetype [Microsoft.Data.OData]Microsoft.Data.OData.ODataPayloadKind payloadKind, class Microsoft.SharePoint.Client.ClientServiceHost serviceHost, class Microsoft.SharePoint.Client.RESTfulQuery query, [out] class Microsoft.SharePoint.Client.Rest.RestResponseMessage& responseMessage)
0x22436  dup
0x22437  stloc.2
0x22438  stloc.s  0x19
0x2243a  ldloc.0
0x2243b  ldfld    object ObjectWithPathName::Value
0x22440  ldarg.0
0x22441  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x22446  call     object Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::ToODataValue(object value, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2244b  stloc.s  5
0x2244d  ldloc.2
0x2244e  ldloc.s  5
0x22450  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter::WriteValue(object)
0x22455  ldloc.3
0x22456  callvirt instance string Microsoft.SharePoint.Client.Rest.RestResponseMessage::GetContentType()
0x2245b  ldarg.0
0x2245c  call     instance class Microsoft.SharePoint.Utilities.ChunkStreamBuilder Microsoft.SharePoint.Client.Rest.RestRequestProcessor::DetachStreamBuilder()
0x22461  newobj   instance void Microsoft.SharePoint.Client.RestRequestResult::.ctor(string contentType, class Microsoft.SharePoint.Utilities.ChunkStreamBuilder streamBuilder)
0x22466  stloc.s  0x17
0x22468  leave    loc_22904
0x2246d  ldloc.s  0x19
0x2246f  brfalse.s loc_22478
0x22471  ldloc.s  0x19
0x22473  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22478  endfinally
0x22479  ldloc.0
0x2247a  ldfld    object ObjectWithPathName::Value
0x2247f  isinst   [mscorlib]System.IO.Stream
0x22484  stloc.s  6
0x22486  ldloc.s  6
0x22488  brfalse.s loc_22493
0x2248a  ldarg.0
0x2248b  ldloc.s  6
0x2248d  call     instance class Microsoft.SharePoint.Client.RestRequestResult Microsoft.SharePoint.Client.Rest.RestRequestProcessor::GetRestRequestResultWithStream(class [mscorlib]System.IO.Stream rawStream)
0x22492  ret
0x22493  ldloc.1
0x22494  brtrue   loc_2253A
0x22499  ldarg.0
0x2249a  ldfld    bool Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_suppressEntityBody
0x2249f  brfalse.s loc_224B2
0x224a1  ldstr    aApplicationJso_0// "application/json"
0x224a6  ldarg.0
0x224a7  call     instance class Microsoft.SharePoint.Utilities.ChunkStreamBuilder Microsoft.SharePoint.Client.Rest.RestRequestProcessor::DetachStreamBuilder()
0x224ac  newobj   instance void Microsoft.SharePoint.Client.RestRequestResult::.ctor(string contentType, class Microsoft.SharePoint.Utilities.ChunkStreamBuilder streamBuilder)
0x224b1  ret
0x224b2  ldarg.0
0x224b3  ldfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_outputStream
0x224b8  ldarg.0
0x224b9  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_acceptHeaderValue
0x224be  ldarg.0
0x224bf  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_host
0x224c4  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.ClientServiceHost::get_ServiceBaseUriWithPathPartition()
0x224c9  ldnull
0x224ca  ldc.i4.2
0x224cb  ldarg.0
0x224cc  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x224d1  ldarg.0
0x224d2  ldfld    class Microsoft.SharePoint.Client.RESTfulQuery Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_query
0x224d7  ldloca.s 3
0x224d9  call     class [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter Microsoft.SharePoint.Client.Rest.RestService::CreateODataMessageWriter(class [mscorlib]System.IO.Stream stream, string orginalAcceptHeaderValue, class [System]System.Uri serviceBaseUri, class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel edmModel, valuetype [Microsoft.Data.OData]Microsoft.Data.OData.ODataPayloadKind payloadKind, class Microsoft.SharePoint.Client.ClientServiceHost serviceHost, class Microsoft.SharePoint.Client.RESTfulQuery query, [out] class Microsoft.SharePoint.Client.Rest.RestResponseMessage& responseMessage)
0x224de  dup
0x224df  stloc.2
0x224e0  stloc.s  0x1A
0x224e2  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty::.ctor()
0x224e7  stloc.s  7
0x224e9  ldloc.s  7
0x224eb  ldloc.0
0x224ec  ldfld    string ObjectWithPathName::PathName
0x224f1  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty::set_Name(string)
0x224f6  ldloc.s  7
0x224f8  ldloc.0
0x224f9  ldfld    object ObjectWithPathName::Value
0x224fe  ldarg.0
0x224ff  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x22504  call     object Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::ToODataValue(object value, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x22509  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty::set_Value(object)
0x2250e  ldloc.2
0x2250f  ldloc.s  7
0x22511  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter::WriteProperty(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty)
0x22516  ldloc.3
0x22517  callvirt instance string Microsoft.SharePoint.Client.Rest.RestResponseMessage::GetContentType()
0x2251c  ldarg.0
0x2251d  call     instance class Microsoft.SharePoint.Utilities.ChunkStreamBuilder Microsoft.SharePoint.Client.Rest.RestRequestProcessor::DetachStreamBuilder()
0x22522  newobj   instance void Microsoft.SharePoint.Client.RestRequestResult::.ctor(string contentType, class Microsoft.SharePoint.Utilities.ChunkStreamBuilder streamBuilder)
0x22527  stloc.s  0x17
0x22529  leave    loc_22904
0x2252e  ldloc.s  0x1A
0x22530  brfalse.s loc_22539
0x22532  ldloc.s  0x1A
0x22534  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22539  endfinally
0x2253a  ldarg.0
0x2253b  ldloc.0
0x2253c  ldfld    object ObjectWithPathName::Value
0x22541  ldloc.1
0x22542  call     instance bool Microsoft.SharePoint.Client.Rest.RestRequestProcessor::TryDeleteEntity(object entity, class Microsoft.SharePoint.Client.ServerStub serverStub)
0x22547  brfalse.s loc_225BF
0x22549  ldarg.0
0x2254a  ldfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_outputStream
0x2254f  ldarg.0
0x22550  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_acceptHeaderValue
0x22555  ldarg.0
0x22556  ldfld    class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_host
0x2255b  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.ClientServiceHost::get_ServiceBaseUriWithPathPartition()
0x22560  ldnull
0x22561  ldc.i4.1
0x22562  ldarg.0
0x22563  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x22568  ldarg.0
0x22569  ldfld    class Microsoft.SharePoint.Client.RESTfulQuery Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_query
0x2256e  ldloca.s 3
0x22570  call     class [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter Microsoft.SharePoint.Client.Rest.RestService::CreateODataMessageWriter(class [mscorlib]System.IO.Stream stream, string orginalAcceptHeaderValue, class [System]System.Uri serviceBaseUri, class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel edmModel, valuetype [Microsoft.Data.OData]Microsoft.Data.OData.ODataPayloadKind payloadKind, class Microsoft.SharePoint.Client.ClientServiceHost serviceHost, class Microsoft.SharePoint.Client.RESTfulQuery query, [out] class Microsoft.SharePoint.Client.Rest.RestResponseMessage& responseMessage)
0x22575  dup
0x22576  stloc.2
0x22577  stloc.s  0x1B
0x22579  ldloc.3
0x2257a  callvirt instance string Microsoft.SharePoint.Client.Rest.RestResponseMessage::GetContentType()
0x2257f  ldarg.0
0x22580  call     instance class Microsoft.SharePoint.Utilities.ChunkStreamBuilder Microsoft.SharePoint.Client.Rest.RestRequestProcessor::DetachStreamBuilder()
0x22585  newobj   instance void Microsoft.SharePoint.Client.RestRequestResult::.ctor(string contentType, class Microsoft.SharePoint.Utilities.ChunkStreamBuilder streamBuilder)
0x2258a  stloc.s  8
0x2258c  ldloc.s  8
0x2258e  ldc.i4.1
0x2258f  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x22594  callvirt instance void Microsoft.SharePoint.Client.RestRequestResult::set_SuppressEntityBody(valuetype [mscorlib]System.Nullable`1<bool> value)
0x22599  ldloc.s  8
0x2259b  ldc.i4   0xC8
0x225a0  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::.ctor(var<u1>)
0x225a5  callvirt instance void Microsoft.SharePoint.Client.RestRequestResult::set_StatusCode(valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> value)
0x225aa  ldloc.s  8
0x225ac  stloc.s  0x17
0x225ae  leave    loc_22904
0x225b3  ldloc.s  0x1B
0x225b5  brfalse.s loc_225BE
0x225b7  ldloc.s  0x1B
0x225b9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x225be  endfinally
0x225bf  ldloc.0
0x225c0  ldfld    object ObjectWithPathName::Value
0x225c5  stloc.s  9
0x225c7  ldloca.s 0xA
0x225c9  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>
0x225cf  ldnull
0x225d0  stloc.s  0xC
0x225d2  ldarg.0
0x225d3  ldloc.0
0x225d4  ldfld    object ObjectWithPathName::Value
0x225d9  ldloc.1
0x225da  ldloca.s 0xC
0x225dc  call     instance bool Microsoft.SharePoint.Client.Rest.RestRequestProcessor::TryUpdateEntity(object entity, class Microsoft.SharePoint.Client.ServerStub serverStub, [out] object& updatedEntity)
0x225e1  brfalse.s loc_225FA
0x225e3  ldloc.1
0x225e4  ldloc.0
0x225e5  ldfld    object ObjectWithPathName::Value
0x225ea  callvirt instance string Microsoft.SharePoint.Client.ServerStub::GetObjectETagHttpHeaderValue(object value)
0x225ef  stloc.s  0xD
0x225f1  ldarg.0
0x225f2  ldloc.s  0xD
0x225f4  call     instance class Microsoft.SharePoint.Client.RestRequestResult Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ReturnUpdatedResult(string etag)
0x225f9  ret
0x225fa  ldc.i4.0
0x225fb  stloc.s  0xE
0x225fd  ldarg.0
0x225fe  ldloc.s  9
0x22600  ldloc.1
0x22601  ldloca.s 0xB
0x22603  call     instance bool Microsoft.SharePoint.Client.Rest.RestRequestProcessor::TryAddEntity(object entity, class Microsoft.SharePoint.Client.ServerStub serverStub, [out] object& newEntity)
0x22608  brfalse.s loc_22632
0x2260a  ldloc.s  0xB
0x2260c  stloc.s  9
0x2260e  ldloc.s  0xB
0x22610  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x22615  ldarg.0
0x22616  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x2261b  call     class Microsoft.SharePoint.Client.ServerStub Microsoft.SharePoint.Client.ProxyMap::GetServerStub(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x22620  stloc.1
0x22621  ldloca.s 0xA
0x22623  ldc.i4   0xC9
0x22628  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::.ctor(var<u1>)
0x2262d  ldc.i4.1
0x2262e  stloc.s  0xE
0x22630  br.s     loc_22679
0x22632  ldarg.0
0x22633  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_httpMethod
0x22638  ldstr    aPost// "POST"
  ... truncated ...
```
