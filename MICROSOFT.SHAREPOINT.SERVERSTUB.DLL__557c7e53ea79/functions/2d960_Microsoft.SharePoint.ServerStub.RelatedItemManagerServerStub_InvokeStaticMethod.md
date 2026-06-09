# Microsoft.SharePoint.ServerStub.RelatedItemManagerServerStub::InvokeStaticMethod

- ea: `0x2d960`
- end: `0x2dab0`
- name: `Microsoft.SharePoint.ServerStub.RelatedItemManagerServerStub::InvokeStaticMethod`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x2d740`
- `0x2d770`
- `0x2d7a0`
- `0x2d830`
- `0x2d880`
- `0x2d8d0`
- `0x2d960`

## string_xrefs

- `0x2d9a8`: `AddSingleLink`
- `0x2da4a`: `AddSingleLink`
- `0x2d9b4`: `AddSingleLinkToUrl`
- `0x2da63`: `AddSingleLinkToUrl`
- `0x2d9c0`: `AddSingleLinkFromUrl`
- `0x2da7c`: `AddSingleLinkFromUrl`
- `0x2d9cc`: `DeleteSingleLink`
- `0x2da95`: `DeleteSingleLink`

## pseudocode

```c

```

## disassembly

```asm
0x2d960  ldarg.3
0x2d961  brtrue.s loc_2D96E
0x2d963  ldstr    aProxycontext// "proxyContext"
0x2d968  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2d96d  throw
0x2d96e  ldarg.0
0x2d96f  ldarg.1
0x2d970  ldarg.3
0x2d971  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2d976  starg.s  1
0x2d978  ldarg.1
0x2d979  dup
0x2d97a  stloc.0
0x2d97b  brfalse  loc_2DAA9
0x2d980  volatile.
0x2d982  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60008a8-1
0x2d987  brtrue.s loc_2D9DE
0x2d989  ldc.i4.6
0x2d98a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x2d98f  dup
0x2d990  ldstr    aGetrelateditem// "GetRelatedItems"
0x2d995  ldc.i4.0
0x2d996  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2d99b  dup
0x2d99c  ldstr    aGetpageonerela// "GetPageOneRelatedItems"
0x2d9a1  ldc.i4.1
0x2d9a2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2d9a7  dup
0x2d9a8  ldstr    aAddsinglelink// "AddSingleLink"
0x2d9ad  ldc.i4.2
0x2d9ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2d9b3  dup
0x2d9b4  ldstr    aAddsinglelinkt// "AddSingleLinkToUrl"
0x2d9b9  ldc.i4.3
0x2d9ba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2d9bf  dup
0x2d9c0  ldstr    aAddsinglelinkf// "AddSingleLinkFromUrl"
0x2d9c5  ldc.i4.4
0x2d9c6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2d9cb  dup
0x2d9cc  ldstr    aDeletesingleli// "DeleteSingleLink"
0x2d9d1  ldc.i4.5
0x2d9d2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2d9d7  volatile.
0x2d9d9  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60008a8-1
0x2d9de  volatile.
0x2d9e0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60008a8-1
0x2d9e5  ldloc.0
0x2d9e6  ldloca.s 1
0x2d9e8  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x2d9ed  brfalse  loc_2DAA9
0x2d9f2  ldloc.1
0x2d9f3  switch   loc_2DA15, loc_2DA2D, loc_2DA45, loc_2DA5E, loc_2DA77, loc_2DA90
0x2da10  br       loc_2DAA9
0x2da15  ldarg.s  4
0x2da17  ldc.i4.0
0x2da18  stind.i1
0x2da19  ldarg.0
0x2da1a  ldstr    aGetrelateditem// "GetRelatedItems"
0x2da1f  ldarg.3
0x2da20  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2da25  ldarg.2
0x2da26  ldarg.3
0x2da27  call     class [Microsoft.SharePoint]Microsoft.SharePoint.RelatedItem[] Microsoft.SharePoint.ServerStub.RelatedItemManagerServerStub::GetRelatedItems_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2da2c  ret
0x2da2d  ldarg.s  4
0x2da2f  ldc.i4.0
0x2da30  stind.i1
0x2da31  ldarg.0
0x2da32  ldstr    aGetpageonerela// "GetPageOneRelatedItems"
0x2da37  ldarg.3
0x2da38  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2da3d  ldarg.2
0x2da3e  ldarg.3
0x2da3f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.RelatedItem[] Microsoft.SharePoint.ServerStub.RelatedItemManagerServerStub::GetPageOneRelatedItems_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2da44  ret
0x2da45  ldarg.s  4
0x2da47  ldc.i4.1
0x2da48  stind.i1
0x2da49  ldarg.0
0x2da4a  ldstr    aAddsinglelink// "AddSingleLink"
0x2da4f  ldarg.3
0x2da50  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2da55  ldarg.2
0x2da56  ldarg.3
0x2da57  call     void Microsoft.SharePoint.ServerStub.RelatedItemManagerServerStub::AddSingleLink_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2da5c  ldnull
0x2da5d  ret
0x2da5e  ldarg.s  4
0x2da60  ldc.i4.1
0x2da61  stind.i1
0x2da62  ldarg.0
0x2da63  ldstr    aAddsinglelinkt// "AddSingleLinkToUrl"
0x2da68  ldarg.3
0x2da69  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2da6e  ldarg.2
0x2da6f  ldarg.3
0x2da70  call     void Microsoft.SharePoint.ServerStub.RelatedItemManagerServerStub::AddSingleLinkToUrl_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2da75  ldnull
0x2da76  ret
0x2da77  ldarg.s  4
0x2da79  ldc.i4.1
0x2da7a  stind.i1
0x2da7b  ldarg.0
0x2da7c  ldstr    aAddsinglelinkf// "AddSingleLinkFromUrl"
0x2da81  ldarg.3
0x2da82  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2da87  ldarg.2
0x2da88  ldarg.3
0x2da89  call     void Microsoft.SharePoint.ServerStub.RelatedItemManagerServerStub::AddSingleLinkFromUrl_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2da8e  ldnull
0x2da8f  ret
0x2da90  ldarg.s  4
0x2da92  ldc.i4.1
0x2da93  stind.i1
0x2da94  ldarg.0
0x2da95  ldstr    aDeletesingleli// "DeleteSingleLink"
0x2da9a  ldarg.3
0x2da9b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2daa0  ldarg.2
0x2daa1  ldarg.3
0x2daa2  call     void Microsoft.SharePoint.ServerStub.RelatedItemManagerServerStub::DeleteSingleLink_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2daa7  ldnull
0x2daa8  ret
0x2daa9  ldarg.1
0x2daaa  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x2daaf  throw
```
