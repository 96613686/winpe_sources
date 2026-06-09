# Microsoft.SharePoint.ServerStub.SPViewServerStub::InvokeMethod

- ea: `0x8c620`
- end: `0x8c79f`
- name: `Microsoft.SharePoint.ServerStub.SPViewServerStub::InvokeMethod`
- size: `383`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x8c560`
- `0x8c580`
- `0x8c590`
- `0x8c5a0`
- `0x8c5e0`
- `0x8c610`
- `0x8c620`

## string_xrefs

- `0x8c67f`: `Update`
- `0x8c728`: `Update`
- `0x8c6a3`: `DeleteObject`
- `0x8c77a`: `DeleteObject`
- `0x8c667`: `SetViewXml`
- `0x8c6f1`: `SetViewXml`
- `0x8c697`: `RemoveFromSpotlight`
- `0x8c75f`: `RemoveFromSpotlight`

## pseudocode

```c

```

## disassembly

```asm
0x8c620  ldarg.s  4
0x8c622  brtrue.s loc_8C62F
0x8c624  ldstr    aProxycontext// "proxyContext"
0x8c629  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8c62e  throw
0x8c62f  ldarg.1
0x8c630  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPView
0x8c635  stloc.0
0x8c636  ldloc.0
0x8c637  brtrue.s loc_8C644
0x8c639  ldstr    aTarget// "target"
0x8c63e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8c643  throw
0x8c644  ldarg.0
0x8c645  ldarg.2
0x8c646  ldarg.s  4
0x8c648  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c64d  starg.s  2
0x8c64f  ldarg.2
0x8c650  dup
0x8c651  stloc.1
0x8c652  brfalse  loc_8C791
0x8c657  volatile.
0x8c659  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001786-1
0x8c65e  brtrue.s loc_8C6B5
0x8c660  ldc.i4.6
0x8c661  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x8c666  dup
0x8c667  ldstr    aSetviewxml// "SetViewXml"
0x8c66c  ldc.i4.0
0x8c66d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c672  dup
0x8c673  ldstr    aRenderashtml// "RenderAsHtml"
0x8c678  ldc.i4.1
0x8c679  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c67e  dup
0x8c67f  ldstr    aUpdate// "Update"
0x8c684  ldc.i4.2
0x8c685  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c68a  dup
0x8c68b  ldstr    aAddtospotlight// "AddToSpotlight"
0x8c690  ldc.i4.3
0x8c691  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c696  dup
0x8c697  ldstr    aRemovefromspot// "RemoveFromSpotlight"
0x8c69c  ldc.i4.4
0x8c69d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c6a2  dup
0x8c6a3  ldstr    aDeleteobject// "DeleteObject"
0x8c6a8  ldc.i4.5
0x8c6a9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c6ae  volatile.
0x8c6b0  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001786-1
0x8c6b5  volatile.
0x8c6b7  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001786-1
0x8c6bc  ldloc.1
0x8c6bd  ldloca.s 2
0x8c6bf  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x8c6c4  brfalse  loc_8C791
0x8c6c9  ldloc.2
0x8c6ca  switch   loc_8C6EC, loc_8C708, loc_8C723, loc_8C73F, loc_8C75A, loc_8C775
0x8c6e7  br       loc_8C791
0x8c6ec  ldarg.s  5
0x8c6ee  ldc.i4.1
0x8c6ef  stind.i1
0x8c6f0  ldarg.0
0x8c6f1  ldstr    aSetviewxml// "SetViewXml"
0x8c6f6  ldarg.s  4
0x8c6f8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c6fd  ldloc.0
0x8c6fe  ldarg.3
0x8c6ff  ldarg.s  4
0x8c701  call     void Microsoft.SharePoint.ServerStub.SPViewServerStub::SetViewXml_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPView target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8c706  ldnull
0x8c707  ret
0x8c708  ldarg.s  5
0x8c70a  ldc.i4.0
0x8c70b  stind.i1
0x8c70c  ldarg.0
0x8c70d  ldstr    aRenderashtml// "RenderAsHtml"
0x8c712  ldarg.s  4
0x8c714  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c719  ldloc.0
0x8c71a  ldarg.3
0x8c71b  ldarg.s  4
0x8c71d  call     string Microsoft.SharePoint.ServerStub.SPViewServerStub::RenderAsHtml_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPView target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8c722  ret
0x8c723  ldarg.s  5
0x8c725  ldc.i4.1
0x8c726  stind.i1
0x8c727  ldarg.0
0x8c728  ldstr    aUpdate// "Update"
0x8c72d  ldarg.s  4
0x8c72f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c734  ldloc.0
0x8c735  ldarg.3
0x8c736  ldarg.s  4
0x8c738  call     void Microsoft.SharePoint.ServerStub.SPViewServerStub::Update_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPView target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8c73d  ldnull
0x8c73e  ret
0x8c73f  ldarg.s  5
0x8c741  ldc.i4.0
0x8c742  stind.i1
0x8c743  ldarg.0
0x8c744  ldstr    aAddtospotlight// "AddToSpotlight"
0x8c749  ldarg.s  4
0x8c74b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c750  ldloc.0
0x8c751  ldarg.3
0x8c752  ldarg.s  4
0x8c754  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSpotlightResult Microsoft.SharePoint.ServerStub.SPViewServerStub::AddToSpotlight_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPView target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8c759  ret
0x8c75a  ldarg.s  5
0x8c75c  ldc.i4.0
0x8c75d  stind.i1
0x8c75e  ldarg.0
0x8c75f  ldstr    aRemovefromspot// "RemoveFromSpotlight"
0x8c764  ldarg.s  4
0x8c766  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c76b  ldloc.0
0x8c76c  ldarg.3
0x8c76d  ldarg.s  4
0x8c76f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSpotlightResult Microsoft.SharePoint.ServerStub.SPViewServerStub::RemoveFromSpotlight_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPView target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8c774  ret
0x8c775  ldarg.s  5
0x8c777  ldc.i4.1
0x8c778  stind.i1
0x8c779  ldarg.0
0x8c77a  ldstr    aDeleteobject// "DeleteObject"
0x8c77f  ldarg.s  4
0x8c781  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c786  ldloc.0
0x8c787  ldarg.3
0x8c788  ldarg.s  4
0x8c78a  call     void Microsoft.SharePoint.ServerStub.SPViewServerStub::DeleteObject_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPView target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8c78f  ldnull
0x8c790  ret
0x8c791  ldarg.0
0x8c792  ldarg.1
0x8c793  ldarg.2
0x8c794  ldarg.3
0x8c795  ldarg.s  4
0x8c797  ldarg.s  5
0x8c799  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x8c79e  ret
```
