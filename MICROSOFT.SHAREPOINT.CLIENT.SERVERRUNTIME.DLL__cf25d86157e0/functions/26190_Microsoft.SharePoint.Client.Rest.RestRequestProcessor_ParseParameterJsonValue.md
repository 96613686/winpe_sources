# Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ParseParameterJsonValue

- ea: `0x26190`
- end: `0x26360`
- name: `Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ParseParameterJsonValue`
- size: `464`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x257f0`
- `0x25bb0`

## callees

- `0x8cf0`
- `0x8d30`
- `0x98e0`
- `0xe010`
- `0x12440`
- `0x16f10`
- `0x1b4c0`
- `0x1b600`
- `0x1dfb0`
- `0x20240`
- `0x20390`
- `0x26190`

## string_xrefs

- `0x26337`: `CannotDeserializeData`
- `0x2625d`: `application/json; odata=verbose`

## pseudocode

```c

```

## disassembly

```asm
0x26190  ldarg.3
0x26191  callvirt instance string [mscorlib]System.String::Trim()
0x26196  stloc.0
0x26197  ldstr    aSResultsSS// "^\\{\\s*(\\'|\")results(\\'|\")\\s*:\\s"...
0x2619c  stloc.1
0x2619d  ldloc.0
0x2619e  ldloc.1
0x2619f  ldc.i4.1
0x261a0  call     bool [System]System.Text.RegularExpressions.Regex::IsMatch(string, string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x261a5  brfalse.s loc_261FF
0x261a7  ldloc.0
0x261a8  ldstr    asc_424A6// "}"
0x261ad  ldc.i4.5
0x261ae  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x261b3  brfalse.s loc_261FF
0x261b5  ldloc.0
0x261b6  ldloc.1
0x261b7  ldstr    asc_3EE4E// ""
0x261bc  call     string [System]System.Text.RegularExpressions.Regex::Replace(string, string, string)
0x261c1  stloc.0
0x261c2  ldloc.0
0x261c3  ldc.i4.0
0x261c4  ldloc.0
0x261c5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x261ca  ldc.i4.1
0x261cb  sub
0x261cc  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x261d1  stloc.0
0x261d2  ldarg.0
0x261d3  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x261d8  ldc.i4   0x58955D
0x261dd  ldc.i4.2
0x261de  ldstr    aOriginalParame// "Original parameter value is {0}. It is "...
0x261e3  ldc.i4.2
0x261e4  newarr   [mscorlib]System.Object
0x261e9  stloc.s  0xC
0x261eb  ldloc.s  0xC
0x261ed  ldc.i4.0
0x261ee  ldarg.3
0x261ef  stelem.ref
0x261f0  ldloc.s  0xC
0x261f2  ldc.i4.1
0x261f3  ldloc.0
0x261f4  stelem.ref
0x261f5  ldloc.s  0xC
0x261f7  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x261fc  ldloc.0
0x261fd  starg.s  3
0x261ff  ldc.i4.5
0x26200  newarr   [mscorlib]System.String
0x26205  stloc.s  0xD
0x26207  ldloc.s  0xD
0x26209  ldc.i4.0
0x2620a  ldstr    asc_46AAC// "{ '"
0x2620f  stelem.ref
0x26210  ldloc.s  0xD
0x26212  ldc.i4.1
0x26213  ldarg.2
0x26214  callvirt instance string Microsoft.SharePoint.Client.ParameterInformation::get_Name()
0x26219  stelem.ref
0x2621a  ldloc.s  0xD
0x2621c  ldc.i4.2
0x2621d  ldstr    asc_46AB4// "':"
0x26222  stelem.ref
0x26223  ldloc.s  0xD
0x26225  ldc.i4.3
0x26226  ldarg.3
0x26227  stelem.ref
0x26228  ldloc.s  0xD
0x2622a  ldc.i4.4
0x2622b  ldstr    asc_424A6// "}"
0x26230  stelem.ref
0x26231  ldloc.s  0xD
0x26233  call     string [mscorlib]System.String::Concat(string[])
0x26238  stloc.2
0x26239  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x2623e  ldloc.2
0x2623f  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x26244  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x26249  stloc.3
0x2624a  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x2624f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x26254  stloc.s  4
0x26256  ldloc.s  4
0x26258  ldstr    aContentType_0// "Content-Type"
0x2625d  ldstr    aApplicationJso_1// "application/json; odata=verbose"
0x26262  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x26267  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x2626c  stloc.s  5
0x2626e  ldloc.s  5
0x26270  ldarg.2
0x26271  callvirt instance string Microsoft.SharePoint.Client.ParameterInformation::get_Name()
0x26276  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2627b  ldarg.0
0x2627c  ldloc.3
0x2627d  ldloc.s  4
0x2627f  ldarg.0
0x26280  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_httpMethod
0x26285  ldnull
0x26286  call     instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageReader Microsoft.SharePoint.Client.Rest.RestRequestProcessorBase::CreateODataMessageReader(class [mscorlib]System.IO.Stream inputStream, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> headers, string httpMethod, [opt] object target)
0x2628b  stloc.s  6
0x2628d  ldarg.0
0x2628e  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x26293  call     class Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::GetInstance(class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x26298  ldarg.1
0x26299  ldloc.s  5
0x2629b  ldarg.0
0x2629c  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x262a1  callvirt instance class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmFunctionImport Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::CreateFunctionImportForMethodBodyParser(class Microsoft.SharePoint.Client.MethodInformation clientMethod, class [mscorlib]System.Collections.Generic.List`1<string> parameterNames, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x262a6  stloc.s  7
0x262a8  ldloc.s  6
0x262aa  ldloc.s  7
0x262ac  callvirt instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataParameterReader [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageReader::CreateODataParameterReader(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmFunctionImport)
0x262b1  stloc.s  8
0x262b3  ldloc.s  8
0x262b5  callvirt instance bool [Microsoft.Data.OData]Microsoft.Data.OData.ODataParameterReader::Read()
0x262ba  pop
0x262bb  ldloc.s  8
0x262bd  callvirt instance valuetype [Microsoft.Data.OData]Microsoft.Data.OData.ODataParameterReaderState [Microsoft.Data.OData]Microsoft.Data.OData.ODataParameterReader::get_State()
0x262c2  ldc.i4.1
0x262c3  bne.un.s loc_262D8
0x262c5  ldloc.s  8
0x262c7  callvirt instance object [Microsoft.Data.OData]Microsoft.Data.OData.ODataParameterReader::get_Value()
0x262cc  ldarg.0
0x262cd  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x262d2  newobj   instance void Microsoft.SharePoint.Client.Rest.ODataPropertyClientValue::.ctor(object odataValue, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x262d7  ret
0x262d8  ldloc.s  8
0x262da  callvirt instance valuetype [Microsoft.Data.OData]Microsoft.Data.OData.ODataParameterReaderState [Microsoft.Data.OData]Microsoft.Data.OData.ODataParameterReader::get_State()
0x262df  ldc.i4.2
0x262e0  bne.un.s loc_26337
0x262e2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<object>::.ctor()
0x262e7  stloc.s  9
0x262e9  ldloc.s  8
0x262eb  callvirt instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataCollectionReader [Microsoft.Data.OData]Microsoft.Data.OData.ODataParameterReader::CreateCollectionReader()
0x262f0  stloc.s  0xA
0x262f2  br.s     loc_26310
0x262f4  ldloc.s  0xA
0x262f6  callvirt instance valuetype [Microsoft.Data.OData]Microsoft.Data.OData.ODataCollectionReaderState [Microsoft.Data.OData]Microsoft.Data.OData.ODataCollectionReader::get_State()
0x262fb  stloc.s  0xE
0x262fd  ldloc.s  0xE
0x262ff  ldc.i4.2
0x26300  bne.un.s loc_26310
0x26302  ldloc.s  9
0x26304  ldloc.s  0xA
0x26306  callvirt instance object [Microsoft.Data.OData]Microsoft.Data.OData.ODataCollectionReader::get_Item()
0x2630b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0x26310  ldloc.s  0xA
0x26312  callvirt instance bool [Microsoft.Data.OData]Microsoft.Data.OData.ODataCollectionReader::Read()
0x26317  brtrue.s loc_262F4
0x26319  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataCollectionValue::.ctor()
0x2631e  stloc.s  0xB
0x26320  ldloc.s  0xB
0x26322  ldloc.s  9
0x26324  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataCollectionValue::set_Items(class [mscorlib]System.Collections.IEnumerable)
0x26329  ldloc.s  0xB
0x2632b  ldarg.0
0x2632c  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x26331  newobj   instance void Microsoft.SharePoint.Client.Rest.ODataPropertyClientValue::.ctor(object odataValue, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x26336  ret
0x26337  ldstr    aCannotdeserial// "CannotDeserializeData"
0x2633c  ldc.i4.1
0x2633d  newarr   [mscorlib]System.Object
0x26342  stloc.s  0xF
0x26344  ldloc.s  0xF
0x26346  ldc.i4.0
0x26347  ldarg.2
0x26348  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ParameterInformation::get_ParameterType()
0x2634d  callvirt instance string [mscorlib]System.Type::get_FullName()
0x26352  stelem.ref
0x26353  ldloc.s  0xF
0x26355  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2635a  newobj   instance void Microsoft.SharePoint.Client.ClientServiceException::.ctor(string message)
0x2635f  throw
```
