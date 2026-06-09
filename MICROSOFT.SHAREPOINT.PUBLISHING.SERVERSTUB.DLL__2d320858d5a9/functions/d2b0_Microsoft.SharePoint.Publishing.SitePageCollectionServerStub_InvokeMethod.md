# Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::InvokeMethod

- ea: `0xd2b0`
- end: `0xd462`
- name: `Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::InvokeMethod`
- size: `434`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0xd1c0`
- `0xd1e0`
- `0xd200`
- `0xd220`
- `0xd260`
- `0xd280`
- `0xd290`
- `0xd2b0`

## string_xrefs

- `0xd2f7`: `Create`
- `0xd391`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0xd2b0  ldarg.s  4
0xd2b2  brtrue.s loc_D2BF
0xd2b4  ldstr    aProxycontext// "proxyContext"
0xd2b9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd2be  throw
0xd2bf  ldarg.1
0xd2c0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection
0xd2c5  stloc.0
0xd2c6  ldloc.0
0xd2c7  brtrue.s loc_D2D4
0xd2c9  ldstr    aTarget// "target"
0xd2ce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd2d3  throw
0xd2d4  ldarg.0
0xd2d5  ldarg.2
0xd2d6  ldarg.s  4
0xd2d8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd2dd  starg.s  2
0xd2df  ldarg.2
0xd2e0  dup
0xd2e1  stloc.1
0xd2e2  brfalse  loc_D454
0xd2e7  volatile.
0xd2e9  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000263-1
0xd2ee  brtrue.s loc_D351
0xd2f0  ldc.i4.7
0xd2f1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xd2f6  dup
0xd2f7  ldstr    aCreate// "Create"
0xd2fc  ldc.i4.0
0xd2fd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd302  dup
0xd303  ldstr    aGetbyid// "GetById"
0xd308  ldc.i4.1
0xd309  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd30e  dup
0xd30f  ldstr    aGetbyurl// "GetByUrl"
0xd314  ldc.i4.2
0xd315  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd31a  dup
0xd31b  ldstr    aFeed// "Feed"
0xd320  ldc.i4.3
0xd321  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd326  dup
0xd327  ldstr    aIssitepage// "IsSitePage"
0xd32c  ldc.i4.4
0xd32d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd332  dup
0xd333  ldstr    aEnsuretitleres// "EnsureTitleResource"
0xd338  ldc.i4.5
0xd339  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd33e  dup
0xd33f  ldstr    aGetpagecolumns// "GetPageColumnState"
0xd344  ldc.i4.6
0xd345  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd34a  volatile.
0xd34c  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000263-1
0xd351  volatile.
0xd353  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000263-1
0xd358  ldloc.1
0xd359  ldloca.s 2
0xd35b  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xd360  brfalse  loc_D454
0xd365  ldloc.2
0xd366  switch   loc_D38C, loc_D3A7, loc_D3C2, loc_D3DD, loc_D3F8, loc_D418, loc_D434
0xd387  br       loc_D454
0xd38c  ldarg.s  5
0xd38e  ldc.i4.0
0xd38f  stind.i1
0xd390  ldarg.0
0xd391  ldstr    aCreate// "Create"
0xd396  ldarg.s  4
0xd398  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd39d  ldloc.0
0xd39e  ldarg.3
0xd39f  ldarg.s  4
0xd3a1  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::Create_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xd3a6  ret
0xd3a7  ldarg.s  5
0xd3a9  ldc.i4.0
0xd3aa  stind.i1
0xd3ab  ldarg.0
0xd3ac  ldstr    aGetbyid// "GetById"
0xd3b1  ldarg.s  4
0xd3b3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd3b8  ldloc.0
0xd3b9  ldarg.3
0xd3ba  ldarg.s  4
0xd3bc  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::GetById_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xd3c1  ret
0xd3c2  ldarg.s  5
0xd3c4  ldc.i4.0
0xd3c5  stind.i1
0xd3c6  ldarg.0
0xd3c7  ldstr    aGetbyurl// "GetByUrl"
0xd3cc  ldarg.s  4
0xd3ce  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd3d3  ldloc.0
0xd3d4  ldarg.3
0xd3d5  ldarg.s  4
0xd3d7  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::GetByUrl_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xd3dc  ret
0xd3dd  ldarg.s  5
0xd3df  ldc.i4.0
0xd3e0  stind.i1
0xd3e1  ldarg.0
0xd3e2  ldstr    aFeed// "Feed"
0xd3e7  ldarg.s  4
0xd3e9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd3ee  ldloc.0
0xd3ef  ldarg.3
0xd3f0  ldarg.s  4
0xd3f2  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadataCollection Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::Feed_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xd3f7  ret
0xd3f8  ldarg.s  5
0xd3fa  ldc.i4.0
0xd3fb  stind.i1
0xd3fc  ldarg.0
0xd3fd  ldstr    aIssitepage// "IsSitePage"
0xd402  ldarg.s  4
0xd404  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd409  ldloc.0
0xd40a  ldarg.3
0xd40b  ldarg.s  4
0xd40d  call     bool Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::IsSitePage_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xd412  box      [mscorlib]System.Boolean
0xd417  ret
0xd418  ldarg.s  5
0xd41a  ldc.i4.1
0xd41b  stind.i1
0xd41c  ldarg.0
0xd41d  ldstr    aEnsuretitleres// "EnsureTitleResource"
0xd422  ldarg.s  4
0xd424  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd429  ldloc.0
0xd42a  ldarg.3
0xd42b  ldarg.s  4
0xd42d  call     void Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::EnsureTitleResource_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xd432  ldnull
0xd433  ret
0xd434  ldarg.s  5
0xd436  ldc.i4.0
0xd437  stind.i1
0xd438  ldarg.0
0xd439  ldstr    aGetpagecolumns// "GetPageColumnState"
0xd43e  ldarg.s  4
0xd440  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd445  ldloc.0
0xd446  ldarg.3
0xd447  ldarg.s  4
0xd449  call     valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageColumnState Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::GetPageColumnState_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xd44e  box      [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageColumnState
0xd453  ret
0xd454  ldarg.0
0xd455  ldarg.1
0xd456  ldarg.2
0xd457  ldarg.3
0xd458  ldarg.s  4
0xd45a  ldarg.s  5
0xd45c  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0xd461  ret
```
