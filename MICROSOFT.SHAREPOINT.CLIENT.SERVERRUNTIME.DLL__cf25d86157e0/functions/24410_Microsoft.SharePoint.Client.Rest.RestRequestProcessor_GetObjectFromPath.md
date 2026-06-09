# Microsoft.SharePoint.Client.Rest.RestRequestProcessor::GetObjectFromPath

- ea: `0x24410`
- end: `0x2458a`
- name: `Microsoft.SharePoint.Client.Rest.RestRequestProcessor::GetObjectFromPath`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x222f0`

## callees

- `0x8f70`
- `0x98e0`
- `0x9e40`
- `0xe010`
- `0x1b970`
- `0x1b990`
- `0x1ba30`
- `0x1bd80`
- `0x1bef0`
- `0x24410`
- `0x24590`
- `0x24c40`
- `0x29560`
- `0x29770`

## string_xrefs

- `0x2441c`: `Get object from path {0}`

## pseudocode

```c

```

## disassembly

```asm
0x24410  ldarg.0
0x24411  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x24416  ldc.i4   0x1C50DB
0x2441b  ldc.i4.4
0x2441c  ldstr    aGetObjectFromP// "Get object from path {0}"
0x24421  ldc.i4.1
0x24422  newarr   [mscorlib]System.Object
0x24427  stloc.s  0xB
0x24429  ldloc.s  0xB
0x2442b  ldc.i4.0
0x2442c  ldarg.2
0x2442d  stelem.ref
0x2442e  ldloc.s  0xB
0x24430  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x24435  ldarg.2
0x24436  ldarg.3
0x24437  newobj   instance void Microsoft.SharePoint.Client.Rest.EdmExpressionParser::.ctor(string input, string inputForErrorMessage)
0x2443c  stloc.0
0x2443d  ldloc.0
0x2443e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode> Microsoft.SharePoint.Client.Rest.EdmExpressionParser::ParsePath()
0x24443  stloc.1
0x24444  ldloc.1
0x24445  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Count()
0x2444a  stloc.2
0x2444b  ldc.i4.0
0x2444c  stloc.3
0x2444d  ldloc.1
0x2444e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Count()
0x24453  ldc.i4.1
0x24454  ble.s    loc_24492
0x24456  ldloc.1
0x24457  ldloc.1
0x24458  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Count()
0x2445d  ldc.i4.1
0x2445e  sub
0x2445f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Item(!!T0)
0x24464  callvirt instance valuetype Microsoft.SharePoint.Client.Rest.EdmParserNodeType Microsoft.SharePoint.Client.Rest.EdmParserNode::get_NodeType()
0x24469  ldc.i4.1
0x2446a  bne.un.s loc_24492
0x2446c  ldloc.1
0x2446d  ldloc.1
0x2446e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Count()
0x24473  ldc.i4.1
0x24474  sub
0x24475  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Item(!!T0)
0x2447a  callvirt instance string Microsoft.SharePoint.Client.Rest.EdmParserNode::get_Value()
0x2447f  ldstr    aValue_1// "$value"
0x24484  ldc.i4.5
0x24485  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x2448a  brtrue.s loc_24492
0x2448c  ldc.i4.1
0x2448d  stloc.3
0x2448e  ldloc.2
0x2448f  ldc.i4.1
0x24490  sub
0x24491  stloc.2
0x24492  ldnull
0x24493  stloc.s  4
0x24495  ldc.i4.0
0x24496  stloc.s  6
0x24498  br       loc_24573
0x2449d  ldarg.2
0x2449e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x244a3  stloc.s  7
0x244a5  ldloc.s  6
0x244a7  ldc.i4.1
0x244a8  add
0x244a9  ldloc.1
0x244aa  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Count()
0x244af  bge.s    loc_244C2
0x244b1  ldloc.1
0x244b2  ldloc.s  6
0x244b4  ldc.i4.1
0x244b5  add
0x244b6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Item(!!T0)
0x244bb  callvirt instance int32 Microsoft.SharePoint.Client.Rest.EdmParserNode::get_TokenPosition()
0x244c0  stloc.s  7
0x244c2  ldarg.1
0x244c3  brfalse.s loc_244EE
0x244c5  ldloc.s  7
0x244c7  ldarg.2
0x244c8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x244cd  bge.s    loc_244E3
0x244cf  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x244d4  ldarg.2
0x244d5  ldloc.s  7
0x244d7  callvirt instance string [mscorlib]System.String::Substring(int32)
0x244dc  callvirt instance void Microsoft.SharePoint.Client.RESTfulOperationContext::set_WildcardPath(string value)
0x244e1  br.s     loc_244EE
0x244e3  call     class Microsoft.SharePoint.Client.RESTfulOperationContext Microsoft.SharePoint.Client.RESTfulOperationContext::get_Current()
0x244e8  ldnull
0x244e9  callvirt instance void Microsoft.SharePoint.Client.RESTfulOperationContext::set_WildcardPath(string value)
0x244ee  ldloc.1
0x244ef  ldloc.s  6
0x244f1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Client.Rest.EdmParserNode>::get_Item(!!T0)
0x244f6  stloc.s  8
0x244f8  ldloc.s  6
0x244fa  ldloc.2
0x244fb  ldc.i4.1
0x244fc  sub
0x244fd  ceq
0x244ff  stloc.s  9
0x24501  ldloc.s  6
0x24503  brtrue.s loc_24516
0x24505  ldarg.0
0x24506  ldarg.1
0x24507  ldloc.s  8
0x24509  ldloc.s  9
0x2450b  ldloca.s 5
0x2450d  call     instance class ObjectWithPathName Microsoft.SharePoint.Client.Rest.RestRequestProcessor::GetObjectFromPathRoot(bool mainRequestPath, class Microsoft.SharePoint.Client.Rest.EdmParserNode node, bool resourceEndpoint, [out] class Microsoft.SharePoint.Client.MethodInformation& methodInfo)
0x24512  stloc.s  4
0x24514  br.s     loc_2452D
0x24516  ldarg.0
0x24517  ldarg.1
0x24518  ldarg.2
0x24519  ldloc.s  4
0x2451b  ldfld    object ObjectWithPathName::Value
0x24520  ldloc.s  8
0x24522  ldloc.s  9
0x24524  ldloca.s 5
0x24526  call     instance class ObjectWithPathName Microsoft.SharePoint.Client.Rest.RestRequestProcessor::GetObjectFromPathMember(bool mainRequestPath, string path, object value, class Microsoft.SharePoint.Client.Rest.EdmParserNode node, bool resourceEndpoint, [out] class Microsoft.SharePoint.Client.MethodInformation& methodInfo)
0x2452b  stloc.s  4
0x2452d  ldloc.s  4
0x2452f  brfalse.s loc_2455D
0x24531  ldloc.s  4
0x24533  ldfld    object ObjectWithPathName::Value
0x24538  isinst   [mscorlib]System.IDisposable
0x2453d  stloc.s  0xA
0x2453f  ldloc.s  0xA
0x24541  brfalse.s loc_24550
0x24543  ldarg.0
0x24544  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class [mscorlib]System.IDisposable> Microsoft.SharePoint.Client.Rest.RestRequestProcessor::m_pendingDisposableQueue
0x24549  ldloc.s  0xA
0x2454b  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x24550  ldarg.0
0x24551  ldloc.s  4
0x24553  ldfld    object ObjectWithPathName::Value
0x24558  call     instance void Microsoft.SharePoint.Client.RequestProcessor::AddRequestedObject(object value)
0x2455d  ldarg.1
0x2455e  brfalse.s loc_2456D
0x24560  ldloc.s  5
0x24562  brfalse.s loc_2456D
0x24564  ldloc.s  5
0x24566  callvirt instance bool Microsoft.SharePoint.Client.MethodInformation::get_WildcardPath()
0x2456b  brtrue.s loc_2457B
0x2456d  ldloc.s  6
0x2456f  ldc.i4.1
0x24570  add
0x24571  stloc.s  6
0x24573  ldloc.s  6
0x24575  ldloc.2
0x24576  blt      loc_2449D
0x2457b  ldloc.s  4
0x2457d  brfalse.s loc_24587
0x2457f  ldloc.s  4
0x24581  ldloc.3
0x24582  stfld    bool ObjectWithPathName::PureValue
0x24587  ldloc.s  4
0x24589  ret
```
