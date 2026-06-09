# Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ParseParametersFromBody

- ea: `0x25e80`
- end: `0x26005`
- name: `Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ParseParametersFromBody`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x25bb0`

## callees

- `0x4d50`
- `0x5000`
- `0x50f0`
- `0x5120`
- `0x8f50`
- `0x8ff0`
- `0x98e0`
- `0xe000`
- `0xf0a0`
- `0x1b4c0`
- `0x1b600`
- `0x1dfb0`
- `0x20240`
- `0x20390`
- `0x22120`
- `0x22130`
- `0x23de0`
- `0x25e80`
- `0x26010`

## string_xrefs

- `0x25ee5`: `The input stream is empty, do not need to read method parameters from POST body.`

## pseudocode

```c

```

## disassembly

```asm
0x25e80  ldarg.0
0x25e81  call     instance string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::get_HttpMethod()
0x25e86  ldstr    aPost// "POST"
0x25e8b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x25e90  brfalse  loc_26004
0x25e95  ldarg.1
0x25e96  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation> Microsoft.SharePoint.Client.MethodInformation::get_Parameters()
0x25e9b  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.SharePoint.Client.ParameterInformation>::get_Count()
0x25ea0  ldc.i4.0
0x25ea1  ble      loc_26004
0x25ea6  ldarg.3
0x25ea7  brfalse  loc_26004
0x25eac  ldarg.2
0x25ead  brfalse  loc_26004
0x25eb2  ldarg.0
0x25eb3  call     instance bool Microsoft.SharePoint.Client.Rest.RestRequestProcessor::get_HasPostBody()
0x25eb8  brfalse  loc_26004
0x25ebd  newobj   instance void Microsoft.SharePoint.Utilities.ChunkStreamBuilder::.ctor()
0x25ec2  stloc.0
0x25ec3  ldloc.0
0x25ec4  ldarg.0
0x25ec5  call     instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ReadInputStream()
0x25eca  callvirt instance void Microsoft.SharePoint.Utilities.ChunkStreamBuilder::CopyFrom(class [mscorlib]System.IO.Stream stream)
0x25ecf  ldloc.0
0x25ed0  callvirt instance int64 Microsoft.SharePoint.Utilities.ChunkStreamBuilder::get_Length()
0x25ed5  ldc.i4.0
0x25ed6  conv.i8
0x25ed7  bne.un.s loc_25EF0
0x25ed9  ldarg.0
0x25eda  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x25edf  ldc.i4   0x18801C
0x25ee4  ldc.i4.4
0x25ee5  ldstr    aTheInputStream_0// "The input stream is empty, do not need "...
0x25eea  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x25eef  ret
0x25ef0  ldarg.0
0x25ef1  ldloc.0
0x25ef2  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ParseParameterNamesFromPayload(class Microsoft.SharePoint.Utilities.ChunkStreamBuilder sb)
0x25ef7  stloc.1
0x25ef8  ldarg.0
0x25ef9  ldloc.0
0x25efa  callvirt instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.ChunkStreamBuilder::CreateReadonlyStream()
0x25eff  ldarg.0
0x25f00  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_headers
0x25f05  ldarg.0
0x25f06  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_httpMethod
0x25f0b  ldnull
0x25f0c  call     instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageReader Microsoft.SharePoint.Client.Rest.RestRequestProcessorBase::CreateODataMessageReader(class [mscorlib]System.IO.Stream inputStream, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> headers, string httpMethod, [opt] object target)
0x25f11  stloc.2
0x25f12  ldarg.0
0x25f13  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x25f18  call     class Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::GetInstance(class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x25f1d  stloc.3
0x25f1e  ldloc.3
0x25f1f  ldarg.1
0x25f20  ldloc.1
0x25f21  ldarg.0
0x25f22  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x25f27  callvirt instance class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmFunctionImport Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::CreateFunctionImportForMethodBodyParser(class Microsoft.SharePoint.Client.MethodInformation clientMethod, class [mscorlib]System.Collections.Generic.List`1<string> parameterNames, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x25f2c  stloc.s  4
0x25f2e  ldloc.2
0x25f2f  ldloc.s  4
0x25f31  callvirt instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataParameterReader [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageReader::CreateODataParameterReader(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmFunctionImport)
0x25f36  stloc.s  5
0x25f38  br       loc_25FF8
0x25f3d  ldloc.s  5
0x25f3f  callvirt instance valuetype [Microsoft.Data.OData]Microsoft.Data.OData.ODataParameterReaderState [Microsoft.Data.OData]Microsoft.Data.OData.ODataParameterReader::get_State()
0x25f44  stloc.s  0xC
0x25f46  ldloc.s  0xC
0x25f48  ldc.i4.1
0x25f49  sub
0x25f4a  switch   loc_25F5C, loc_25F8C
0x25f57  br       loc_25FF8
0x25f5c  ldarg.1
0x25f5d  ldloc.s  5
0x25f5f  callvirt instance string [Microsoft.Data.OData]Microsoft.Data.OData.ODataParameterReader::get_Name()
0x25f64  callvirt instance int32 Microsoft.SharePoint.Client.MethodInformation::GetParameterIndex(string parameterName)
0x25f69  stloc.s  6
0x25f6b  ldloc.s  5
0x25f6d  callvirt instance object [Microsoft.Data.OData]Microsoft.Data.OData.ODataParameterReader::get_Value()
0x25f72  ldarg.0
0x25f73  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x25f78  newobj   instance void Microsoft.SharePoint.Client.Rest.ODataPropertyClientValue::.ctor(object odataValue, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x25f7d  stloc.s  7
0x25f7f  ldarg.s  4
0x25f81  ldloc.s  6
0x25f83  ldloc.s  7
0x25f85  callvirt instance void Microsoft.SharePoint.Client.ClientValueCollection::Set(int32 index, class Microsoft.SharePoint.Client.ClientValue value)
0x25f8a  br.s     loc_25FF8
0x25f8c  ldarg.1
0x25f8d  ldloc.s  5
0x25f8f  callvirt instance string [Microsoft.Data.OData]Microsoft.Data.OData.ODataParameterReader::get_Name()
0x25f94  callvirt instance int32 Microsoft.SharePoint.Client.MethodInformation::GetParameterIndex(string parameterName)
0x25f99  stloc.s  8
0x25f9b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<object>::.ctor()
0x25fa0  stloc.s  9
0x25fa2  ldloc.s  5
0x25fa4  callvirt instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataCollectionReader [Microsoft.Data.OData]Microsoft.Data.OData.ODataParameterReader::CreateCollectionReader()
0x25fa9  stloc.s  0xA
0x25fab  br.s     loc_25FC9
0x25fad  ldloc.s  0xA
0x25faf  callvirt instance valuetype [Microsoft.Data.OData]Microsoft.Data.OData.ODataCollectionReaderState [Microsoft.Data.OData]Microsoft.Data.OData.ODataCollectionReader::get_State()
0x25fb4  stloc.s  0xD
0x25fb6  ldloc.s  0xD
0x25fb8  ldc.i4.2
0x25fb9  bne.un.s loc_25FC9
0x25fbb  ldloc.s  9
0x25fbd  ldloc.s  0xA
0x25fbf  callvirt instance object [Microsoft.Data.OData]Microsoft.Data.OData.ODataCollectionReader::get_Item()
0x25fc4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0x25fc9  ldloc.s  0xA
0x25fcb  callvirt instance bool [Microsoft.Data.OData]Microsoft.Data.OData.ODataCollectionReader::Read()
0x25fd0  brtrue.s loc_25FAD
0x25fd2  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataCollectionValue::.ctor()
0x25fd7  stloc.s  0xB
0x25fd9  ldloc.s  0xB
0x25fdb  ldloc.s  9
0x25fdd  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataCollectionValue::set_Items(class [mscorlib]System.Collections.IEnumerable)
0x25fe2  ldarg.s  4
0x25fe4  ldloc.s  8
0x25fe6  ldloc.s  0xB
0x25fe8  ldarg.0
0x25fe9  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x25fee  newobj   instance void Microsoft.SharePoint.Client.Rest.ODataPropertyClientValue::.ctor(object odataValue, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x25ff3  callvirt instance void Microsoft.SharePoint.Client.ClientValueCollection::Set(int32 index, class Microsoft.SharePoint.Client.ClientValue value)
0x25ff8  ldloc.s  5
0x25ffa  callvirt instance bool [Microsoft.Data.OData]Microsoft.Data.OData.ODataParameterReader::Read()
0x25fff  brtrue   loc_25F3D
0x26004  ret
```
