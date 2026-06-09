# Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::InvokeStaticMethod_0

- ea: `0x9e00`
- end: `0x9f81`
- name: `Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::InvokeStaticMethod_0`
- size: `385`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x9cd0`
- `0x9cf0`
- `0x9d30`
- `0x9d60`
- `0x9d80`
- `0x9da0`
- `0x9dc0`
- `0x9e00`

## string_xrefs

- `0x9e60`: `FlushSiteFromCache`
- `0x9f34`: `FlushSiteFromCache`
- `0x9e6c`: `FlushWebFromCache`
- `0x9f4d`: `FlushWebFromCache`
- `0x9e78`: `FlushTermSetFromCache`
- `0x9f66`: `FlushTermSetFromCache`

## pseudocode

```c

```

## disassembly

```asm
0x9e00  ldarg.3
0x9e01  brtrue.s loc_9E0E
0x9e03  ldstr    aProxycontext// "proxyContext"
0x9e08  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9e0d  throw
0x9e0e  ldarg.0
0x9e0f  ldarg.1
0x9e10  ldarg.3
0x9e11  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9e16  starg.s  1
0x9e18  ldarg.1
0x9e19  dup
0x9e1a  stloc.0
0x9e1b  brfalse  loc_9F7A
0x9e20  volatile.
0x9e22  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000185-1
0x9e27  brtrue.s loc_9E8A
0x9e29  ldc.i4.7
0x9e2a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x9e2f  dup
0x9e30  ldstr    aGetwebnavigati// "GetWebNavigationSettings"
0x9e35  ldc.i4.0
0x9e36  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9e3b  dup
0x9e3c  ldstr    aGettermsetforw// "GetTermSetForWeb"
0x9e41  ldc.i4.1
0x9e42  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9e47  dup
0x9e48  ldstr    aSetcrawlasfrie// "SetCrawlAsFriendlyUrlPage"
0x9e4d  ldc.i4.2
0x9e4e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9e53  dup
0x9e54  ldstr    aGetnavigationl// "GetNavigationLcidForWeb"
0x9e59  ldc.i4.3
0x9e5a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9e5f  dup
0x9e60  ldstr    aFlushsitefromc// "FlushSiteFromCache"
0x9e65  ldc.i4.4
0x9e66  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9e6b  dup
0x9e6c  ldstr    aFlushwebfromca// "FlushWebFromCache"
0x9e71  ldc.i4.5
0x9e72  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9e77  dup
0x9e78  ldstr    aFlushtermsetfr// "FlushTermSetFromCache"
0x9e7d  ldc.i4.6
0x9e7e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9e83  volatile.
0x9e85  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000185-1
0x9e8a  volatile.
0x9e8c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000185-1
0x9e91  ldloc.0
0x9e92  ldloca.s 1
0x9e94  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x9e99  brfalse  loc_9F7A
0x9e9e  ldloc.1
0x9e9f  switch   loc_9EC5, loc_9EDD, loc_9EF5, loc_9F12, loc_9F2F, loc_9F48, loc_9F61
0x9ec0  br       loc_9F7A
0x9ec5  ldarg.s  4
0x9ec7  ldc.i4.0
0x9ec8  stind.i1
0x9ec9  ldarg.0
0x9eca  ldstr    aGetwebnavigati// "GetWebNavigationSettings"
0x9ecf  ldarg.3
0x9ed0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9ed5  ldarg.2
0x9ed6  ldarg.3
0x9ed7  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::GetWebNavigationSettings_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9edc  ret
0x9edd  ldarg.s  4
0x9edf  ldc.i4.0
0x9ee0  stind.i1
0x9ee1  ldarg.0
0x9ee2  ldstr    aGettermsetforw// "GetTermSetForWeb"
0x9ee7  ldarg.3
0x9ee8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9eed  ldarg.2
0x9eee  ldarg.3
0x9eef  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::GetTermSetForWeb_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9ef4  ret
0x9ef5  ldarg.s  4
0x9ef7  ldc.i4.0
0x9ef8  stind.i1
0x9ef9  ldarg.0
0x9efa  ldstr    aSetcrawlasfrie// "SetCrawlAsFriendlyUrlPage"
0x9eff  ldarg.3
0x9f00  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9f05  ldarg.2
0x9f06  ldarg.3
0x9f07  call     bool Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::SetCrawlAsFriendlyUrlPage_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9f0c  box      [mscorlib]System.Boolean
0x9f11  ret
0x9f12  ldarg.s  4
0x9f14  ldc.i4.0
0x9f15  stind.i1
0x9f16  ldarg.0
0x9f17  ldstr    aGetnavigationl// "GetNavigationLcidForWeb"
0x9f1c  ldarg.3
0x9f1d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9f22  ldarg.2
0x9f23  ldarg.3
0x9f24  call     int32 Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::GetNavigationLcidForWeb_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9f29  box      [mscorlib]System.Int32
0x9f2e  ret
0x9f2f  ldarg.s  4
0x9f31  ldc.i4.1
0x9f32  stind.i1
0x9f33  ldarg.0
0x9f34  ldstr    aFlushsitefromc// "FlushSiteFromCache"
0x9f39  ldarg.3
0x9f3a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9f3f  ldarg.2
0x9f40  ldarg.3
0x9f41  call     void Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::FlushSiteFromCache_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9f46  ldnull
0x9f47  ret
0x9f48  ldarg.s  4
0x9f4a  ldc.i4.1
0x9f4b  stind.i1
0x9f4c  ldarg.0
0x9f4d  ldstr    aFlushwebfromca// "FlushWebFromCache"
0x9f52  ldarg.3
0x9f53  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9f58  ldarg.2
0x9f59  ldarg.3
0x9f5a  call     void Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::FlushWebFromCache_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9f5f  ldnull
0x9f60  ret
0x9f61  ldarg.s  4
0x9f63  ldc.i4.1
0x9f64  stind.i1
0x9f65  ldarg.0
0x9f66  ldstr    aFlushtermsetfr// "FlushTermSetFromCache"
0x9f6b  ldarg.3
0x9f6c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9f71  ldarg.2
0x9f72  ldarg.3
0x9f73  call     void Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::FlushTermSetFromCache_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9f78  ldnull
0x9f79  ret
0x9f7a  ldarg.1
0x9f7b  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x9f80  throw
```
