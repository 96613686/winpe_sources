# Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ReadRequestODataObject

- ea: `0x22c70`
- end: `0x22f5a`
- name: `Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ReadRequestODataObject`
- size: `746`
- prototype: ``
- caller_count: `3`
- callee_count: `30`
- tags: `broker_com_uri`

## callers

- `0x23100`
- `0x23690`
- `0x23760`

## callees

- `0xb40`
- `0x98e0`
- `0xe000`
- `0xe010`
- `0xe940`
- `0xe9d0`
- `0x12440`
- `0x124e0`
- `0x12df0`
- `0x12e20`
- `0x13d00`
- `0x16f10`
- `0x1a940`
- `0x1ab20`
- `0x1b600`
- `0x1d640`
- `0x20240`
- `0x20310`
- `0x20390`
- `0x22c70`
- `0x23de0`
- `0x26470`
- `0x26490`
- `0x264f0`
- `0x26510`
- `0x26550`
- `0x26570`
- `0x265a0`
- `0x265b0`
- `0x265d0`

## string_xrefs

- `0x22edf`: `OData Exception Reading Entity Body: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x22c70  ldarg.0
0x22c71  ldfld    class RequestODataObject Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_requestODataObject
0x22c76  brtrue   loc_22F53
0x22c7b  ldarg.0
0x22c7c  ldarg.0
0x22c7d  call     instance class [mscorlib]System.IO.Stream Microsoft.SharePoint.Client.Rest.RestRequestProcessor::ReadInputStream()
0x22c82  ldarg.0
0x22c83  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_headers
0x22c88  ldarg.0
0x22c89  ldfld    string Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_httpMethod
0x22c8e  ldarg.2
0x22c8f  call     instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageReader Microsoft.SharePoint.Client.Rest.RestRequestProcessorBase::CreateODataMessageReader(class [mscorlib]System.IO.Stream inputStream, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> headers, string httpMethod, [opt] object target)
0x22c94  stloc.0
0x22c95  ldnull
0x22c96  stloc.1
0x22c97  ldarg.0
0x22c98  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_headers
0x22c9d  ldstr    aContentType_0// "Content-Type"
0x22ca2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Item(void)
0x22ca7  call     bool Microsoft.SharePoint.Client.ODataMetadataHelper::IsJsonLight(string contentType)
0x22cac  brfalse.s loc_22CFC
0x22cae  ldarg.1
0x22caf  ldarg.2
0x22cb0  ldarg.0
0x22cb1  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x22cb6  callvirt instance string Microsoft.SharePoint.Client.ServerStub::GetEntityTypeFullName(object value, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x22cbb  stloc.3
0x22cbc  ldarg.0
0x22cbd  ldarg.2
0x22cbe  call     instance class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel Microsoft.SharePoint.Client.Rest.RestRequestProcessorBase::GetEdmModel(object target)
0x22cc3  ldloc.3
0x22cc4  callvirt instance class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmSchemaType [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmModel::FindDeclaredType(string)
0x22cc9  isinst   [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType
0x22cce  stloc.s  4
0x22cd0  ldarg.0
0x22cd1  call     instance class Microsoft.SharePoint.Client.ProxyContext Microsoft.SharePoint.Client.RESTfulRequestProcessor::get_ProxyContext()
0x22cd6  call     class Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::GetInstance(class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x22cdb  stloc.s  5
0x22cdd  ldloc.s  5
0x22cdf  ldloc.s  5
0x22ce1  callvirt instance class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntityContainer Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::get_EntityContainer()
0x22ce6  ldloc.s  4
0x22ce8  callvirt instance class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntitySet Microsoft.SharePoint.Client.Rest.ClientCallableEdmModelBuilder::GetOrCreateEntitySet(class [Microsoft.Data.Edm]Microsoft.Data.Edm.Library.EdmEntityContainer entityContainer, class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType edmEntityType)
0x22ced  stloc.s  6
0x22cef  ldloc.0
0x22cf0  ldloc.s  6
0x22cf2  ldloc.s  4
0x22cf4  callvirt instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataReader [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageReader::CreateODataEntryReader(class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntitySet, class [Microsoft.Data.Edm]Microsoft.Data.Edm.IEdmEntityType)
0x22cf9  stloc.2
0x22cfa  br.s     loc_22D03
0x22cfc  ldloc.0
0x22cfd  callvirt instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataReader [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageReader::CreateODataEntryReader()
0x22d02  stloc.2
0x22d03  leave.s  loc_22D67
0x22d05  stloc.s  7
0x22d07  ldarg.0
0x22d08  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x22d0d  ldc.i4   0x58955B
0x22d12  ldc.i4.1
0x22d13  ldloc.s  7
0x22d15  callvirt instance string [mscorlib]System.Object::ToString()
0x22d1a  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x22d1f  ldstr    aInvalidhttphea// "InvalidHttpHeader"
0x22d24  ldc.i4.1
0x22d25  newarr   [mscorlib]System.Object
0x22d2a  stloc.s  0x16
0x22d2c  ldloc.s  0x16
0x22d2e  ldc.i4.0
0x22d2f  ldstr    aContentType_0// "Content-Type"
0x22d34  stelem.ref
0x22d35  ldloc.s  0x16
0x22d37  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x22d3c  newobj   instance void Microsoft.SharePoint.Client.ClientServiceException::.ctor(string message)
0x22d41  stloc.s  8
0x22d43  ldloc.s  8
0x22d45  newobj   instance void Microsoft.SharePoint.Client.ErrorInformation::.ctor()
0x22d4a  stloc.s  9
0x22d4c  ldloc.s  9
0x22d4e  ldc.i4   0x19F
0x22d53  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode>::.ctor(var<u1>)
0x22d58  callvirt instance void Microsoft.SharePoint.Client.ErrorInformation::set_HttpStatusCode(valuetype [mscorlib]System.Nullable`1<valuetype [System]System.Net.HttpStatusCode> value)
0x22d5d  ldloc.s  9
0x22d5f  callvirt instance void Microsoft.SharePoint.Client.ClientServiceException::set_ErrorInformation(class Microsoft.SharePoint.Client.ErrorInformation value)
0x22d64  ldloc.s  8
0x22d66  throw
0x22d67  ldnull
0x22d68  stloc.s  0xA
0x22d6a  newobj   instance void class [System]System.Collections.Generic.Stack`1<class ODataItemBase>::.ctor()
0x22d6f  stloc.s  0xB
0x22d71  br       loc_22EBC
0x22d76  ldloc.2
0x22d77  callvirt instance valuetype [Microsoft.Data.OData]Microsoft.Data.OData.ODataReaderState [Microsoft.Data.OData]Microsoft.Data.OData.ODataReader::get_State()
0x22d7c  stloc.s  0x17
0x22d7e  ldloc.s  0x17
0x22d80  ldc.i4.1
0x22d81  sub
0x22d82  switch   loc_22DA4, loc_22DF0, loc_22DFD, loc_22E71, loc_22E7B, loc_22EB4
0x22d9f  br       loc_22EBC
0x22da4  ldloc.2
0x22da5  callvirt instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataItem [Microsoft.Data.OData]Microsoft.Data.OData.ODataReader::get_Item()
0x22daa  castclass [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed
0x22daf  newobj   instance void ODataFeedWithEntries::.ctor(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataFeed item)
0x22db4  stloc.s  0xC
0x22db6  ldloc.s  0xB
0x22db8  callvirt instance int32 class [System]System.Collections.Generic.Stack`1<class ODataItemBase>::get_Count()
0x22dbd  ldc.i4.0
0x22dbe  ble.s    loc_22DDE
0x22dc0  ldloc.s  0xB
0x22dc2  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class ODataItemBase>::Peek()
0x22dc7  castclass ODataNavigationLinkWithItems
0x22dcc  stloc.s  0xD
0x22dce  ldloc.s  0xD
0x22dd0  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class ODataItemBase> ODataNavigationLinkWithItems::get_NestedItems()
0x22dd5  ldloc.s  0xC
0x22dd7  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class ODataItemBase>::Add(var<u1>)
0x22ddc  br.s     loc_22DE2
0x22dde  ldloc.s  0xC
0x22de0  stloc.s  0xA
0x22de2  ldloc.s  0xB
0x22de4  ldloc.s  0xC
0x22de6  callvirt instance void class [System]System.Collections.Generic.Stack`1<class ODataItemBase>::Push(var<u1>)
0x22deb  br       loc_22EBC
0x22df0  ldloc.s  0xB
0x22df2  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class ODataItemBase>::Pop()
0x22df7  pop
0x22df8  br       loc_22EBC
0x22dfd  ldloc.2
0x22dfe  callvirt instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataItem [Microsoft.Data.OData]Microsoft.Data.OData.ODataReader::get_Item()
0x22e03  castclass [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry
0x22e08  stloc.s  0xE
0x22e0a  ldnull
0x22e0b  stloc.s  0xF
0x22e0d  ldloc.s  0xE
0x22e0f  brfalse.s loc_22E1A
0x22e11  ldloc.s  0xE
0x22e13  newobj   instance void ODataEntryWithNavigationLinks::.ctor(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry item)
0x22e18  stloc.s  0xF
0x22e1a  ldloc.s  0xB
0x22e1c  callvirt instance int32 class [System]System.Collections.Generic.Stack`1<class ODataItemBase>::get_Count()
0x22e21  brtrue.s loc_22E29
0x22e23  ldloc.s  0xF
0x22e25  stloc.s  0xA
0x22e27  br.s     loc_22E66
0x22e29  ldloc.s  0xB
0x22e2b  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class ODataItemBase>::Peek()
0x22e30  stloc.s  0x10
0x22e32  ldloc.s  0x10
0x22e34  isinst   ODataFeedWithEntries
0x22e39  stloc.s  0x11
0x22e3b  ldloc.s  0x11
0x22e3d  brfalse.s loc_22E4F
0x22e3f  ldloc.s  0x11
0x22e41  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class ODataEntryWithNavigationLinks> ODataFeedWithEntries::get_Entries()
0x22e46  ldloc.s  0xF
0x22e48  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class ODataEntryWithNavigationLinks>::Add(var<u1>)
0x22e4d  br.s     loc_22E66
0x22e4f  ldloc.s  0x10
0x22e51  castclass ODataNavigationLinkWithItems
0x22e56  stloc.s  0x12
0x22e58  ldloc.s  0x12
0x22e5a  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class ODataItemBase> ODataNavigationLinkWithItems::get_NestedItems()
0x22e5f  ldloc.s  0xF
0x22e61  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class ODataItemBase>::Add(var<u1>)
0x22e66  ldloc.s  0xB
0x22e68  ldloc.s  0xF
0x22e6a  callvirt instance void class [System]System.Collections.Generic.Stack`1<class ODataItemBase>::Push(var<u1>)
0x22e6f  br.s     loc_22EBC
0x22e71  ldloc.s  0xB
0x22e73  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class ODataItemBase>::Pop()
0x22e78  pop
0x22e79  br.s     loc_22EBC
0x22e7b  ldloc.2
0x22e7c  callvirt instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataItem [Microsoft.Data.OData]Microsoft.Data.OData.ODataReader::get_Item()
0x22e81  castclass [Microsoft.Data.OData]Microsoft.Data.OData.ODataNavigationLink
0x22e86  newobj   instance void ODataNavigationLinkWithItems::.ctor(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataNavigationLink item)
0x22e8b  stloc.s  0x13
0x22e8d  ldloc.s  0xB
0x22e8f  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class ODataItemBase>::Peek()
0x22e94  castclass ODataEntryWithNavigationLinks
0x22e99  stloc.s  0x14
0x22e9b  ldloc.s  0x14
0x22e9d  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class ODataNavigationLinkWithItems> ODataEntryWithNavigationLinks::get_NavigationLinks()
0x22ea2  ldloc.s  0x13
0x22ea4  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class ODataNavigationLinkWithItems>::Add(var<u1>)
0x22ea9  ldloc.s  0xB
0x22eab  ldloc.s  0x13
0x22ead  callvirt instance void class [System]System.Collections.Generic.Stack`1<class ODataItemBase>::Push(var<u1>)
0x22eb2  br.s     loc_22EBC
0x22eb4  ldloc.s  0xB
0x22eb6  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<class ODataItemBase>::Pop()
0x22ebb  pop
0x22ebc  ldloc.2
0x22ebd  callvirt instance bool [Microsoft.Data.OData]Microsoft.Data.OData.ODataReader::Read()
0x22ec2  brtrue   loc_22D76
0x22ec7  ldloc.s  0xA
0x22ec9  isinst   ODataEntryWithNavigationLinks
0x22ece  stloc.1
0x22ecf  leave.s  loc_22F06
0x22ed1  stloc.s  0x15
0x22ed3  ldarg.0
0x22ed4  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x22ed9  ldc.i4   0x1E025F
0x22ede  ldc.i4.1
0x22edf  ldstr    aOdataException// "OData Exception Reading Entity Body: {0"...
0x22ee4  ldc.i4.1
0x22ee5  newarr   [mscorlib]System.Object
0x22eea  stloc.s  0x18
0x22eec  ldloc.s  0x18
0x22eee  ldc.i4.0
0x22eef  ldloc.s  0x15
0x22ef1  stelem.ref
0x22ef2  ldloc.s  0x18
0x22ef4  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x22ef9  ldloc.s  0x15
0x22efb  callvirt instance string [mscorlib]System.Exception::get_Message()
0x22f00  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0x22f05  throw
0x22f06  ldloc.1
0x22f07  brtrue.s loc_22F25
0x22f09  ldarg.0
0x22f0a  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x22f0f  ldc.i4   0x1C50CB
0x22f14  ldc.i4.1
0x22f15  ldstr    aThereIsNoEntit// "There is no entity data in the request "...
0x22f1a  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x22f1f  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x22f24  throw
0x22f25  ldarg.0
0x22f26  ldloc.1
0x22f27  callvirt instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry ODataEntryWithNavigationLinks::get_Entry()
0x22f2c  ldarg.0
0x22f2d  ldloc.1
0x22f2e  call     T0x2B00003F
0x22f33  newobj   instance void RequestODataEntry::.ctor(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry entry, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.SharePoint.Client.ClientValue> clientValueProperties)
0x22f38  stfld    class RequestODataObject Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_requestODataObject
0x22f3d  ldarg.0
0x22f3e  ldarg.0
0x22f3f  ldfld    class RequestODataObject Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_requestODataObject
0x22f44  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.SharePoint.Client.ClientValue> RequestODataObject::get_ClientValueProperties()
0x22f49  newobj   instance void Microsoft.SharePoint.Client.NamedClientValueCollection::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.SharePoint.Client.ClientValue> values)
0x22f4e  stfld    class Microsoft.SharePoint.Client.NamedClientValueCollection Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_requestValues
0x22f53  ldarg.0
0x22f54  ldfld    class RequestODataObject Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_requestODataObject
0x22f59  ret
```
