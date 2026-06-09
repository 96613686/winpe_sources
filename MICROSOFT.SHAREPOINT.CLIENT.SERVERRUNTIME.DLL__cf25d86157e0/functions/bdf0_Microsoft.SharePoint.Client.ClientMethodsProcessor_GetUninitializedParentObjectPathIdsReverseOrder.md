# Microsoft.SharePoint.Client.ClientMethodsProcessor::GetUninitializedParentObjectPathIdsReverseOrder

- ea: `0xbdf0`
- end: `0xc033`
- name: `Microsoft.SharePoint.Client.ClientMethodsProcessor::GetUninitializedParentObjectPathIdsReverseOrder`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0xbc60`

## callees

- `0x98e0`
- `0xa9c0`
- `0xbdf0`
- `0xe010`
- `0x12e20`
- `0x16f00`
- `0x17f80`

## string_xrefs

- `0xbe1d`: `Unknown object path id {0} in request {1}`
- `0xbf90`: `Circular reference for objectPathId {0} in request {1}`
- `0xbff0`: `Cannot find all parent elements for object path {0}, within {1} loops for request {2}`

## pseudocode

```c

```

## disassembly

```asm
0xbdf0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xbdf5  stloc.0
0xbdf6  ldarg.1
0xbdf7  stloc.1
0xbdf8  ldc.i4.0
0xbdf9  stloc.2
0xbdfa  ldc.i4.0
0xbdfb  stloc.3
0xbdfc  br       loc_BFD3
0xbe01  ldarg.0
0xbe02  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Xml]System.Xml.XmlElement> Microsoft.SharePoint.Client.ClientMethodsProcessor::m_pathIdToObjectPathMap
0xbe07  ldarg.1
0xbe08  ldloca.s 4
0xbe0a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Xml]System.Xml.XmlElement>::TryGetValue(var<u1>, !!T0)
0xbe0f  brtrue.s loc_BE50
0xbe11  ldarg.0
0xbe12  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0xbe17  ldc.i4   0x81220B
0xbe1c  ldc.i4.2
0xbe1d  ldstr    aUnknownObjectP// "Unknown object path id {0} in request {"...
0xbe22  ldc.i4.2
0xbe23  newarr   [mscorlib]System.Object
0xbe28  stloc.s  7
0xbe2a  ldloc.s  7
0xbe2c  ldc.i4.0
0xbe2d  ldarg.1
0xbe2e  stelem.ref
0xbe2f  ldloc.s  7
0xbe31  ldc.i4.1
0xbe32  ldarg.0
0xbe33  call     instance string Microsoft.SharePoint.Client.ClientMethodsProcessor::GetRequestMessageToLog()
0xbe38  stelem.ref
0xbe39  ldloc.s  7
0xbe3b  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0xbe40  ldstr    aClientrequesti// "ClientRequestInvalidRequestGenericError"
0xbe45  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId)
0xbe4a  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0xbe4f  throw
0xbe50  ldnull
0xbe51  stloc.s  5
0xbe53  ldloc.s  4
0xbe55  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xbe5a  dup
0xbe5b  stloc.s  8
0xbe5d  brfalse  loc_BF1E
0xbe62  volatile.
0xbe64  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{C5801E67-8F5D-4E19-96C7-23D022523FB4}::$$method0x6000306-1
0xbe69  brtrue.s loc_BEC0
0xbe6b  ldc.i4.6
0xbe6c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xbe71  dup
0xbe72  ldstr    aProperty// "Property"
0xbe77  ldc.i4.0
0xbe78  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbe7d  dup
0xbe7e  ldstr    aMethod// "Method"
0xbe83  ldc.i4.1
0xbe84  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbe89  dup
0xbe8a  ldstr    aStaticproperty// "StaticProperty"
0xbe8f  ldc.i4.2
0xbe90  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbe95  dup
0xbe96  ldstr    aIdentity// "Identity"
0xbe9b  ldc.i4.3
0xbe9c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbea1  dup
0xbea2  ldstr    aStaticmethod// "StaticMethod"
0xbea7  ldc.i4.4
0xbea8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbead  dup
0xbeae  ldstr    aConstructor// "Constructor"
0xbeb3  ldc.i4.5
0xbeb4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbeb9  volatile.
0xbebb  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{C5801E67-8F5D-4E19-96C7-23D022523FB4}::$$method0x6000306-1
0xbec0  volatile.
0xbec2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{C5801E67-8F5D-4E19-96C7-23D022523FB4}::$$method0x6000306-1
0xbec7  ldloc.s  8
0xbec9  ldloca.s 9
0xbecb  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xbed0  brfalse.s loc_BF1E
0xbed2  ldloc.s  9
0xbed4  switch   loc_BEF3, loc_BF06, loc_BF19, loc_BF19, loc_BF19, loc_BF19
0xbef1  br.s     loc_BF1E
0xbef3  ldloc.s  4
0xbef5  ldstr    aParentid// "ParentId"
0xbefa  call     string Microsoft.SharePoint.Client.Utility::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attrName)
0xbeff  stloc.s  5
0xbf01  ldc.i4.1
0xbf02  stloc.s  6
0xbf04  br.s     loc_BF63
0xbf06  ldloc.s  4
0xbf08  ldstr    aParentid// "ParentId"
0xbf0d  call     string Microsoft.SharePoint.Client.Utility::GetAttributeValue(class [System.Xml]System.Xml.XmlNode node, string attrName)
0xbf12  stloc.s  5
0xbf14  ldc.i4.1
0xbf15  stloc.s  6
0xbf17  br.s     loc_BF63
0xbf19  ldc.i4.0
0xbf1a  stloc.s  6
0xbf1c  br.s     loc_BF63
0xbf1e  ldarg.0
0xbf1f  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0xbf24  ldc.i4   0x81220C
0xbf29  ldc.i4.2
0xbf2a  ldstr    aUnknownElement// "Unknown element {0} in request {1}"
0xbf2f  ldc.i4.2
0xbf30  newarr   [mscorlib]System.Object
0xbf35  stloc.s  0xA
0xbf37  ldloc.s  0xA
0xbf39  ldc.i4.0
0xbf3a  ldloc.s  4
0xbf3c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0xbf41  stelem.ref
0xbf42  ldloc.s  0xA
0xbf44  ldc.i4.1
0xbf45  ldarg.0
0xbf46  call     instance string Microsoft.SharePoint.Client.ClientMethodsProcessor::GetRequestMessageToLog()
0xbf4b  stelem.ref
0xbf4c  ldloc.s  0xA
0xbf4e  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0xbf53  ldstr    aClientrequesti// "ClientRequestInvalidRequestGenericError"
0xbf58  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId)
0xbf5d  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0xbf62  throw
0xbf63  ldloc.s  6
0xbf65  brfalse.s loc_BF76
0xbf67  ldarg.0
0xbf68  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Client.ClientMethodsProcessor::m_pathIdToObjectMap
0xbf6d  ldloc.s  5
0xbf6f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0xbf74  brfalse.s loc_BF7A
0xbf76  ldc.i4.1
0xbf77  stloc.2
0xbf78  br.s     loc_BFE1
0xbf7a  ldloc.s  5
0xbf7c  ldloc.1
0xbf7d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf82  brfalse.s loc_BFC3
0xbf84  ldarg.0
0xbf85  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0xbf8a  ldc.i4   0x81220D
0xbf8f  ldc.i4.2
0xbf90  ldstr    aCircularRefere// "Circular reference for objectPathId {0}"...
0xbf95  ldc.i4.2
0xbf96  newarr   [mscorlib]System.Object
0xbf9b  stloc.s  0xB
0xbf9d  ldloc.s  0xB
0xbf9f  ldc.i4.0
0xbfa0  ldloc.1
0xbfa1  stelem.ref
0xbfa2  ldloc.s  0xB
0xbfa4  ldc.i4.1
0xbfa5  ldarg.0
0xbfa6  call     instance string Microsoft.SharePoint.Client.ClientMethodsProcessor::GetRequestMessageToLog()
0xbfab  stelem.ref
0xbfac  ldloc.s  0xB
0xbfae  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0xbfb3  ldstr    aClientrequesti// "ClientRequestInvalidRequestGenericError"
0xbfb8  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId)
0xbfbd  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0xbfc2  throw
0xbfc3  ldloc.0
0xbfc4  ldloc.s  5
0xbfc6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbfcb  ldloc.s  5
0xbfcd  starg.s  1
0xbfcf  ldloc.3
0xbfd0  ldc.i4.1
0xbfd1  add
0xbfd2  stloc.3
0xbfd3  ldloc.3
0xbfd4  ldc.i4   0x186A0
0xbfd9  bge.s    loc_BFE1
0xbfdb  ldloc.2
0xbfdc  brfalse  loc_BE01
0xbfe1  ldloc.2
0xbfe2  brtrue.s loc_C031
0xbfe4  ldarg.0
0xbfe5  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0xbfea  ldc.i4   0x81220E
0xbfef  ldc.i4.2
0xbff0  ldstr    aCannotFindAllP// "Cannot find all parent elements for obj"...
0xbff5  ldc.i4.3
0xbff6  newarr   [mscorlib]System.Object
0xbffb  stloc.s  0xC
0xbffd  ldloc.s  0xC
0xbfff  ldc.i4.0
0xc000  ldloc.1
0xc001  stelem.ref
0xc002  ldloc.s  0xC
0xc004  ldc.i4.1
0xc005  ldc.i4   0x186A0
0xc00a  box      [mscorlib]System.Int32
0xc00f  stelem.ref
0xc010  ldloc.s  0xC
0xc012  ldc.i4.2
0xc013  ldarg.0
0xc014  call     instance string Microsoft.SharePoint.Client.ClientMethodsProcessor::GetRequestMessageToLog()
0xc019  stelem.ref
0xc01a  ldloc.s  0xC
0xc01c  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0xc021  ldstr    aClientrequesti// "ClientRequestInvalidRequestGenericError"
0xc026  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId)
0xc02b  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor(string strMessage)
0xc030  throw
0xc031  ldloc.0
0xc032  ret
```
