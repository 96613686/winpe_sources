# Microsoft.SharePoint.Client.Rest.RestService::SerializeToOData

- ea: `0x27830`
- end: `0x279c9`
- name: `Microsoft.SharePoint.Client.Rest.RestService::SerializeToOData`
- size: `409`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xba0`
- `0x2f10`
- `0x4d50`
- `0x5120`
- `0x147c0`
- `0x147e0`
- `0x14f70`
- `0x15040`
- `0x15060`
- `0x150e0`
- `0x152f0`
- `0x16920`
- `0x19990`
- `0x1e990`
- `0x1ee90`
- `0x1f3a0`
- `0x20100`
- `0x23f30`
- `0x274f0`
- `0x27830`

## string_xrefs

- `0x27848`: `writer`
- `0x27839`: `baseUri`
- `0x278dc`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x27830  ldarg.2
0x27831  ldnull
0x27832  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x27837  brfalse.s loc_27844
0x27839  ldstr    aBaseuri// "baseUri"
0x2783e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x27843  throw
0x27844  ldarg.s  4
0x27846  brtrue.s loc_27853
0x27848  ldstr    aWriter// "writer"
0x2784d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x27852  throw
0x27853  ldarg.3
0x27854  brtrue.s loc_2785D
0x27856  newobj   instance void Microsoft.SharePoint.Client.ODataSerializationOptions::.ctor()
0x2785b  starg.s  3
0x2785d  newobj   instance void Microsoft.SharePoint.Client.ProxyContext::.ctor()
0x27862  stloc.0
0x27863  ldnull
0x27864  stloc.1
0x27865  ldarg.1
0x27866  brfalse.s loc_2787C
0x27868  ldarg.1
0x27869  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2786e  stloc.2
0x2786f  ldloc.2
0x27870  ldloc.0
0x27871  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x27876  call     class Microsoft.SharePoint.Client.ServerStub Microsoft.SharePoint.Client.ProxyMap::GetServerStub(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x2787b  stloc.1
0x2787c  ldloc.1
0x2787d  brtrue.s loc_27883
0x2787f  ldc.i4.2
0x27880  stloc.3
0x27881  br.s     loc_27890
0x27883  ldloc.1
0x27884  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::get_IsFeed()
0x27889  brtrue.s loc_2788E
0x2788b  ldc.i4.1
0x2788c  br.s     loc_2788F
0x2788e  ldc.i4.0
0x2788f  stloc.3
0x27890  ldloc.0
0x27891  newobj   instance void Microsoft.SharePoint.Client.Rest.ODataSerializer::.ctor()
0x27896  callvirt instance void Microsoft.SharePoint.Client.ProxyContext::set_ODataSerializer(class Microsoft.SharePoint.Client.RESTfulODataSerializer value)
0x2789b  ldloc.0
0x2789c  ldc.i4.2
0x2789d  callvirt instance void Microsoft.SharePoint.Client.ProxyContext::set_MetadataLevel(valuetype Microsoft.SharePoint.Client.ODataMetadataLevel value)
0x278a2  ldarg.3
0x278a3  callvirt instance string Microsoft.SharePoint.Client.ODataSerializationOptions::get_Query()
0x278a8  dup
0x278a9  brtrue.s loc_278B1
0x278ab  pop
0x278ac  ldsfld   string [mscorlib]System.String::Empty
0x278b1  call     class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpUtility::ParseQueryString(string)
0x278b6  stloc.s  4
0x278b8  ldloc.s  4
0x278ba  ldloc.0
0x278bb  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x278c0  call     class Microsoft.SharePoint.Client.RESTfulQuery Microsoft.SharePoint.Client.Rest.RestRequestProcessor::CreateRestQueryFromQueryStrings(class [System]System.Collections.Specialized.NameValueCollection queryStrings, class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x278c5  stloc.s  5
0x278c7  ldnull
0x278c8  stloc.s  6
0x278ca  newobj   instance void Microsoft.SharePoint.Utilities.ChunkStreamBuilder::.ctor()
0x278cf  stloc.s  7
0x278d1  ldloc.s  7
0x278d3  newobj   instance void Microsoft.SharePoint.Client.Rest.OutputChunkStream::.ctor(class Microsoft.SharePoint.Utilities.ChunkStreamBuilder sb)
0x278d8  stloc.s  8
0x278da  ldloc.s  8
0x278dc  ldstr    aApplicationJso_0// "application/json"
0x278e1  ldarg.2
0x278e2  ldloc.3
0x278e3  ldloc.0
0x278e4  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x278e9  ldloc.s  5
0x278eb  ldloca.s 6
0x278ed  call     class [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter Microsoft.SharePoint.Client.Rest.RestService::CreateODataMessageWriter(class [mscorlib]System.IO.Stream stream, string acceptHeaderValue, class [System]System.Uri serviceBaseUri, valuetype [Microsoft.Data.OData]Microsoft.Data.OData.ODataPayloadKind payloadKind, class Microsoft.SharePoint.Client.ClientServiceHost serviceHost, class Microsoft.SharePoint.Client.RESTfulQuery query, [out] class Microsoft.SharePoint.Client.Rest.RestResponseMessage& responseMessage)
0x278f2  stloc.s  9
0x278f4  ldloc.1
0x278f5  brtrue.s loc_27923
0x278f7  ldloc.s  9
0x278f9  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty::.ctor()
0x278fe  stloc.s  0xA
0x27900  ldloc.s  0xA
0x27902  ldstr    aValue// "value"
0x27907  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty::set_Name(string)
0x2790c  ldloc.s  0xA
0x2790e  ldarg.1
0x2790f  ldloc.0
0x27910  call     object Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::ToODataValue(object value, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x27915  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty::set_Value(object)
0x2791a  ldloc.s  0xA
0x2791c  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter::WriteProperty(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty)
0x27921  br.s     loc_2796B
0x27923  ldloc.1
0x27924  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::get_IsFeed()
0x27929  brfalse.s loc_27936
0x2792b  ldloc.s  9
0x2792d  callvirt instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter::CreateODataFeedWriter()
0x27932  stloc.s  0xB
0x27934  br.s     loc_2793F
0x27936  ldloc.s  9
0x27938  callvirt instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter::CreateODataEntryWriter()
0x2793d  stloc.s  0xB
0x2793f  ldloc.1
0x27940  ldarg.1
0x27941  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.ServerStub::GetObjectUrlPath(object target)
0x27946  stloc.s  0xC
0x27948  ldloc.0
0x27949  ldloc.0
0x2794a  ldc.i4.0
0x2794b  ldarg.1
0x2794c  newobj   instance void Microsoft.SharePoint.Client.Rest.AggregatedEdmModel::.ctor(class Microsoft.SharePoint.Client.ProxyContext proxyContext, valuetype Microsoft.SharePoint.Client.EdmModelUsage usage, [opt] object target)
0x27951  callvirt instance void Microsoft.SharePoint.Client.ProxyContext::set_EdmModel(object value)
0x27956  ldarg.1
0x27957  ldloc.1
0x27958  ldloc.s  0xC
0x2795a  ldloc.s  0xB
0x2795c  ldloc.s  5
0x2795e  ldloc.0
0x2795f  call     void Microsoft.SharePoint.Client.Rest.ODataSerializeUtility::Write(object value, class Microsoft.SharePoint.Client.ServerStub serverStub, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x27964  ldloc.s  0xB
0x27966  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter::Flush()
0x2796b  leave.s  loc_27979
0x2796d  ldloc.s  9
0x2796f  brfalse.s loc_27978
0x27971  ldloc.s  9
0x27973  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27978  endfinally
0x27979  ldc.i4   0x400
0x2797e  newarr   [mscorlib]System.Char
0x27983  stloc.s  0xD
0x27985  ldloc.s  7
0x27987  callvirt instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Utilities.ChunkStreamBuilder::CreateReadonlyStream()
0x2798c  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x27991  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding)
0x27996  stloc.s  0xE
0x27998  br.s     loc_279A6
0x2799a  ldarg.s  4
0x2799c  ldloc.s  0xD
0x2799e  ldc.i4.0
0x2799f  ldloc.s  0xF
0x279a1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char[], int32, int32)
0x279a6  ldloc.s  0xE
0x279a8  ldloc.s  0xD
0x279aa  ldc.i4.0
0x279ab  ldloc.s  0xD
0x279ad  ldlen
0x279ae  conv.i4
0x279af  callvirt instance int32 [mscorlib]System.IO.TextReader::Read(char[], int32, int32)
0x279b4  dup
0x279b5  stloc.s  0xF
0x279b7  ldc.i4.0
0x279b8  bgt.s    loc_2799A
0x279ba  leave.s  loc_279C8
0x279bc  ldloc.s  0xE
0x279be  brfalse.s loc_279C7
0x279c0  ldloc.s  0xE
0x279c2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x279c7  endfinally
0x279c8  ret
```
