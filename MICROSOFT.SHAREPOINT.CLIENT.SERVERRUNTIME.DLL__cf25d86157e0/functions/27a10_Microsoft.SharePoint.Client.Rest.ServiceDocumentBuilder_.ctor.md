# Microsoft.SharePoint.Client.Rest.ServiceDocumentBuilder::.ctor

- ea: `0x27a10`
- end: `0x27bd5`
- name: `Microsoft.SharePoint.Client.Rest.ServiceDocumentBuilder::.ctor`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x243a0`

## callees

- `0x2f10`
- `0xe010`
- `0x122c0`
- `0x152f0`
- `0x15620`
- `0x15640`
- `0x16920`
- `0x16b70`
- `0x16ca0`
- `0x27a10`
- `0x29450`
- `0x29470`
- `0x294b0`

## string_xrefs

- `0x27a99`: `Skip '{0}' in the service document as the ResourceType is unknown or ExcludedFromServiceDocument={1}`

## pseudocode

```c

```

## disassembly

```asm
0x27a10  ldarg.0
0x27a11  call     instance void [mscorlib]System.Object::.ctor()
0x27a16  ldarg.1
0x27a17  brtrue.s loc_27A24
0x27a19  ldstr    aProxycontext// "proxyContext"
0x27a1e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x27a23  throw
0x27a24  ldarg.1
0x27a25  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x27a2a  call     class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.SharePoint.Client.UrlSegmentAliasInfo> Microsoft.SharePoint.Client.ProxyMap::GetUrlSegmentAliasMap(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x27a2f  stloc.0
0x27a30  ldarg.1
0x27a31  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x27a36  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.EdmModelProvider> Microsoft.SharePoint.Client.ProxyMap::CreateEdmModelProviders(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost)
0x27a3b  stloc.1
0x27a3c  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWorkspace::.ctor()
0x27a41  stloc.2
0x27a42  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataResourceCollectionInfo>::.ctor()
0x27a47  stloc.3
0x27a48  ldloc.0
0x27a49  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.SharePoint.Client.UrlSegmentAliasInfo>>::GetEnumerator()
0x27a4e  stloc.s  0xD
0x27a50  br       loc_27B0D
0x27a55  ldloc.s  0xD
0x27a57  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.SharePoint.Client.UrlSegmentAliasInfo>>::get_Current()
0x27a5c  stloc.s  4
0x27a5e  ldloca.s 4
0x27a60  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.SharePoint.Client.UrlSegmentAliasInfo>::get_Key()
0x27a65  stloc.s  5
0x27a67  ldloca.s 4
0x27a69  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.SharePoint.Client.UrlSegmentAliasInfo>::get_Value()
0x27a6e  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.UrlSegmentAliasInfo::get_ResourceType()
0x27a73  stloc.s  6
0x27a75  ldloc.s  6
0x27a77  ldnull
0x27a78  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x27a7d  brtrue.s loc_27A8D
0x27a7f  ldloca.s 4
0x27a81  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.SharePoint.Client.UrlSegmentAliasInfo>::get_Value()
0x27a86  callvirt instance bool Microsoft.SharePoint.Client.UrlSegmentAliasInfo::get_ExcludedFromServiceDocument()
0x27a8b  brfalse.s loc_27ACA
0x27a8d  ldarg.1
0x27a8e  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x27a93  ldc.i4   0x64C557
0x27a98  ldc.i4.3
0x27a99  ldstr    aSkip0InTheServ// "Skip '{0}' in the service document as t"...
0x27a9e  ldc.i4.2
0x27a9f  newarr   [mscorlib]System.Object
0x27aa4  stloc.s  0xE
0x27aa6  ldloc.s  0xE
0x27aa8  ldc.i4.0
0x27aa9  ldloc.s  5
0x27aab  stelem.ref
0x27aac  ldloc.s  0xE
0x27aae  ldc.i4.1
0x27aaf  ldloca.s 4
0x27ab1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.SharePoint.Client.UrlSegmentAliasInfo>::get_Value()
0x27ab6  callvirt instance bool Microsoft.SharePoint.Client.UrlSegmentAliasInfo::get_ExcludedFromServiceDocument()
0x27abb  box      [mscorlib]System.Boolean
0x27ac0  stelem.ref
0x27ac1  ldloc.s  0xE
0x27ac3  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x27ac8  br.s     loc_27B0D
0x27aca  ldloc.s  6
0x27acc  ldarg.1
0x27acd  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x27ad2  call     class Microsoft.SharePoint.Client.ServerStub Microsoft.SharePoint.Client.ProxyMap::GetServerStub(class [mscorlib]System.Type type, class Microsoft.SharePoint.Client.ClientServiceHost processorSurrogate)
0x27ad7  stloc.s  7
0x27ad9  ldloc.s  7
0x27adb  brfalse.s loc_27B0D
0x27add  ldloc.s  7
0x27adf  callvirt instance bool Microsoft.SharePoint.Client.ServerStub::get_IsFeed()
0x27ae4  brfalse.s loc_27B0D
0x27ae6  ldloc.3
0x27ae7  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataResourceCollectionInfo::.ctor()
0x27aec  stloc.s  8
0x27aee  ldloc.s  8
0x27af0  ldloc.s  5
0x27af2  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataResourceCollectionInfo::set_Name(string)
0x27af7  ldloc.s  8
0x27af9  ldloc.s  5
0x27afb  ldc.i4.2
0x27afc  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x27b01  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataResourceCollectionInfo::set_Url(class [System]System.Uri)
0x27b06  ldloc.s  8
0x27b08  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataResourceCollectionInfo>::Add(var<u1>)
0x27b0d  ldloc.s  0xD
0x27b0f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x27b14  brtrue   loc_27A55
0x27b19  leave.s  loc_27B27
0x27b1b  ldloc.s  0xD
0x27b1d  brfalse.s loc_27B26
0x27b1f  ldloc.s  0xD
0x27b21  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27b26  endfinally
0x27b27  ldloc.1
0x27b28  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.EdmModelProvider>::GetEnumerator()
0x27b2d  stloc.s  0xF
0x27b2f  br.s     loc_27BAC
0x27b31  ldloc.s  0xF
0x27b33  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Client.EdmModelProvider>::get_Current()
0x27b38  stloc.s  9
0x27b3a  ldloc.s  9
0x27b3c  ldarg.1
0x27b3d  callvirt instance class Microsoft.SharePoint.Client.RESTfulODataServiceDocument Microsoft.SharePoint.Client.EdmModelProvider::GetServiceDocument(class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x27b42  stloc.s  0xA
0x27b44  ldloc.s  0xA
0x27b46  brfalse.s loc_27BAC
0x27b48  ldloc.s  0xA
0x27b4a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.RESTfulODataResourceInfo> Microsoft.SharePoint.Client.RESTfulODataServiceDocument::get_EntitySets()
0x27b4f  brfalse.s loc_27BAC
0x27b51  ldloc.s  0xA
0x27b53  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.RESTfulODataResourceInfo> Microsoft.SharePoint.Client.RESTfulODataServiceDocument::get_EntitySets()
0x27b58  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.SharePoint.Client.RESTfulODataResourceInfo>::GetEnumerator()
0x27b5d  stloc.s  0x10
0x27b5f  br.s     loc_27B95
0x27b61  ldloc.s  0x10
0x27b63  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Client.RESTfulODataResourceInfo>::get_Current()
0x27b68  stloc.s  0xB
0x27b6a  ldloc.3
0x27b6b  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataResourceCollectionInfo::.ctor()
0x27b70  stloc.s  0xC
0x27b72  ldloc.s  0xC
0x27b74  ldloc.s  0xB
0x27b76  callvirt instance string Microsoft.SharePoint.Client.RESTfulODataResourceInfo::get_Name()
0x27b7b  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataResourceCollectionInfo::set_Name(string)
0x27b80  ldloc.s  0xC
0x27b82  ldloc.s  0xB
0x27b84  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.RESTfulODataResourceInfo::get_Url()
0x27b89  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataResourceCollectionInfo::set_Url(class [System]System.Uri)
0x27b8e  ldloc.s  0xC
0x27b90  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataResourceCollectionInfo>::Add(var<u1>)
0x27b95  ldloc.s  0x10
0x27b97  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x27b9c  brtrue.s loc_27B61
0x27b9e  leave.s  loc_27BAC
0x27ba0  ldloc.s  0x10
0x27ba2  brfalse.s loc_27BAB
0x27ba4  ldloc.s  0x10
0x27ba6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27bab  endfinally
0x27bac  ldloc.s  0xF
0x27bae  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x27bb3  brtrue   loc_27B31
0x27bb8  leave.s  loc_27BC6
0x27bba  ldloc.s  0xF
0x27bbc  brfalse.s loc_27BC5
0x27bbe  ldloc.s  0xF
0x27bc0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27bc5  endfinally
0x27bc6  ldloc.2
0x27bc7  ldloc.3
0x27bc8  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWorkspace::set_Collections(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataResourceCollectionInfo>)
0x27bcd  ldarg.0
0x27bce  ldloc.2
0x27bcf  stfld    class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWorkspace Microsoft.SharePoint.Client.Rest.ServiceDocumentBuilder::m_serviceDocument
0x27bd4  ret
```
