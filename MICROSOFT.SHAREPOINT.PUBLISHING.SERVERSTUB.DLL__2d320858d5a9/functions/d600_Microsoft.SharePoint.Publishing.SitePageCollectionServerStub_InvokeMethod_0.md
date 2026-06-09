# Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::InvokeMethod_0

- ea: `0xd600`
- end: `0xd7b2`
- name: `Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::InvokeMethod_0`
- size: `434`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0xd510`
- `0xd530`
- `0xd550`
- `0xd570`
- `0xd5b0`
- `0xd5d0`
- `0xd5e0`
- `0xd600`

## string_xrefs

- `0xd647`: `Create`
- `0xd6e1`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0xd600  ldarg.s  4
0xd602  brtrue.s loc_D60F
0xd604  ldstr    aProxycontext// "proxyContext"
0xd609  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd60e  throw
0xd60f  ldarg.1
0xd610  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection
0xd615  stloc.0
0xd616  ldloc.0
0xd617  brtrue.s loc_D624
0xd619  ldstr    aTarget// "target"
0xd61e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd623  throw
0xd624  ldarg.0
0xd625  ldarg.2
0xd626  ldarg.s  4
0xd628  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd62d  starg.s  2
0xd62f  ldarg.2
0xd630  dup
0xd631  stloc.1
0xd632  brfalse  loc_D7A4
0xd637  volatile.
0xd639  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000270-1
0xd63e  brtrue.s loc_D6A1
0xd640  ldc.i4.7
0xd641  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xd646  dup
0xd647  ldstr    aCreate// "Create"
0xd64c  ldc.i4.0
0xd64d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd652  dup
0xd653  ldstr    aGetbyid// "GetById"
0xd658  ldc.i4.1
0xd659  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd65e  dup
0xd65f  ldstr    aGetbyurl// "GetByUrl"
0xd664  ldc.i4.2
0xd665  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd66a  dup
0xd66b  ldstr    aFeed// "Feed"
0xd670  ldc.i4.3
0xd671  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd676  dup
0xd677  ldstr    aIssitepage// "IsSitePage"
0xd67c  ldc.i4.4
0xd67d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd682  dup
0xd683  ldstr    aEnsuretitleres// "EnsureTitleResource"
0xd688  ldc.i4.5
0xd689  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd68e  dup
0xd68f  ldstr    aGetpagecolumns// "GetPageColumnState"
0xd694  ldc.i4.6
0xd695  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xd69a  volatile.
0xd69c  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000270-1
0xd6a1  volatile.
0xd6a3  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000270-1
0xd6a8  ldloc.1
0xd6a9  ldloca.s 2
0xd6ab  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xd6b0  brfalse  loc_D7A4
0xd6b5  ldloc.2
0xd6b6  switch   loc_D6DC, loc_D6F7, loc_D712, loc_D72D, loc_D748, loc_D768, loc_D784
0xd6d7  br       loc_D7A4
0xd6dc  ldarg.s  5
0xd6de  ldc.i4.0
0xd6df  stind.i1
0xd6e0  ldarg.0
0xd6e1  ldstr    aCreate// "Create"
0xd6e6  ldarg.s  4
0xd6e8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd6ed  ldloc.0
0xd6ee  ldarg.3
0xd6ef  ldarg.s  4
0xd6f1  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::Create_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xd6f6  ret
0xd6f7  ldarg.s  5
0xd6f9  ldc.i4.0
0xd6fa  stind.i1
0xd6fb  ldarg.0
0xd6fc  ldstr    aGetbyid// "GetById"
0xd701  ldarg.s  4
0xd703  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd708  ldloc.0
0xd709  ldarg.3
0xd70a  ldarg.s  4
0xd70c  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::GetById_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xd711  ret
0xd712  ldarg.s  5
0xd714  ldc.i4.0
0xd715  stind.i1
0xd716  ldarg.0
0xd717  ldstr    aGetbyurl// "GetByUrl"
0xd71c  ldarg.s  4
0xd71e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd723  ldloc.0
0xd724  ldarg.3
0xd725  ldarg.s  4
0xd727  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePage Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::GetByUrl_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xd72c  ret
0xd72d  ldarg.s  5
0xd72f  ldc.i4.0
0xd730  stind.i1
0xd731  ldarg.0
0xd732  ldstr    aFeed// "Feed"
0xd737  ldarg.s  4
0xd739  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd73e  ldloc.0
0xd73f  ldarg.3
0xd740  ldarg.s  4
0xd742  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageMetadataCollection Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::Feed_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xd747  ret
0xd748  ldarg.s  5
0xd74a  ldc.i4.0
0xd74b  stind.i1
0xd74c  ldarg.0
0xd74d  ldstr    aIssitepage// "IsSitePage"
0xd752  ldarg.s  4
0xd754  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd759  ldloc.0
0xd75a  ldarg.3
0xd75b  ldarg.s  4
0xd75d  call     bool Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::IsSitePage_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xd762  box      [mscorlib]System.Boolean
0xd767  ret
0xd768  ldarg.s  5
0xd76a  ldc.i4.1
0xd76b  stind.i1
0xd76c  ldarg.0
0xd76d  ldstr    aEnsuretitleres// "EnsureTitleResource"
0xd772  ldarg.s  4
0xd774  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd779  ldloc.0
0xd77a  ldarg.3
0xd77b  ldarg.s  4
0xd77d  call     void Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::EnsureTitleResource_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xd782  ldnull
0xd783  ret
0xd784  ldarg.s  5
0xd786  ldc.i4.0
0xd787  stind.i1
0xd788  ldarg.0
0xd789  ldstr    aGetpagecolumns// "GetPageColumnState"
0xd78e  ldarg.s  4
0xd790  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xd795  ldloc.0
0xd796  ldarg.3
0xd797  ldarg.s  4
0xd799  call     valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageColumnState Microsoft.SharePoint.Publishing.SitePageCollectionServerStub::GetPageColumnState_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xd79e  box      [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PageColumnState
0xd7a3  ret
0xd7a4  ldarg.0
0xd7a5  ldarg.1
0xd7a6  ldarg.2
0xd7a7  ldarg.3
0xd7a8  ldarg.s  4
0xd7aa  ldarg.s  5
0xd7ac  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0xd7b1  ret
```
