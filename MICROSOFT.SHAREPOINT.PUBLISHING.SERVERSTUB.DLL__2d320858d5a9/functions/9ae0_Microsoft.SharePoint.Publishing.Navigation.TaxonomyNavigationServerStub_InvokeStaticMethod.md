# Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::InvokeStaticMethod

- ea: `0x9ae0`
- end: `0x9c61`
- name: `Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::InvokeStaticMethod`
- size: `385`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x99b0`
- `0x99d0`
- `0x9a10`
- `0x9a40`
- `0x9a60`
- `0x9a80`
- `0x9aa0`
- `0x9ae0`

## string_xrefs

- `0x9b40`: `FlushSiteFromCache`
- `0x9c14`: `FlushSiteFromCache`
- `0x9b4c`: `FlushWebFromCache`
- `0x9c2d`: `FlushWebFromCache`
- `0x9b58`: `FlushTermSetFromCache`
- `0x9c46`: `FlushTermSetFromCache`

## pseudocode

```c

```

## disassembly

```asm
0x9ae0  ldarg.3
0x9ae1  brtrue.s loc_9AEE
0x9ae3  ldstr    aProxycontext// "proxyContext"
0x9ae8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9aed  throw
0x9aee  ldarg.0
0x9aef  ldarg.1
0x9af0  ldarg.3
0x9af1  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9af6  starg.s  1
0x9af8  ldarg.1
0x9af9  dup
0x9afa  stloc.0
0x9afb  brfalse  loc_9C5A
0x9b00  volatile.
0x9b02  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600017a-1
0x9b07  brtrue.s loc_9B6A
0x9b09  ldc.i4.7
0x9b0a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x9b0f  dup
0x9b10  ldstr    aGetwebnavigati// "GetWebNavigationSettings"
0x9b15  ldc.i4.0
0x9b16  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b1b  dup
0x9b1c  ldstr    aGettermsetforw// "GetTermSetForWeb"
0x9b21  ldc.i4.1
0x9b22  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b27  dup
0x9b28  ldstr    aSetcrawlasfrie// "SetCrawlAsFriendlyUrlPage"
0x9b2d  ldc.i4.2
0x9b2e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b33  dup
0x9b34  ldstr    aGetnavigationl// "GetNavigationLcidForWeb"
0x9b39  ldc.i4.3
0x9b3a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b3f  dup
0x9b40  ldstr    aFlushsitefromc// "FlushSiteFromCache"
0x9b45  ldc.i4.4
0x9b46  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b4b  dup
0x9b4c  ldstr    aFlushwebfromca// "FlushWebFromCache"
0x9b51  ldc.i4.5
0x9b52  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b57  dup
0x9b58  ldstr    aFlushtermsetfr// "FlushTermSetFromCache"
0x9b5d  ldc.i4.6
0x9b5e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b63  volatile.
0x9b65  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600017a-1
0x9b6a  volatile.
0x9b6c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600017a-1
0x9b71  ldloc.0
0x9b72  ldloca.s 1
0x9b74  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x9b79  brfalse  loc_9C5A
0x9b7e  ldloc.1
0x9b7f  switch   loc_9BA5, loc_9BBD, loc_9BD5, loc_9BF2, loc_9C0F, loc_9C28, loc_9C41
0x9ba0  br       loc_9C5A
0x9ba5  ldarg.s  4
0x9ba7  ldc.i4.0
0x9ba8  stind.i1
0x9ba9  ldarg.0
0x9baa  ldstr    aGetwebnavigati// "GetWebNavigationSettings"
0x9baf  ldarg.3
0x9bb0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9bb5  ldarg.2
0x9bb6  ldarg.3
0x9bb7  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::GetWebNavigationSettings_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9bbc  ret
0x9bbd  ldarg.s  4
0x9bbf  ldc.i4.0
0x9bc0  stind.i1
0x9bc1  ldarg.0
0x9bc2  ldstr    aGettermsetforw// "GetTermSetForWeb"
0x9bc7  ldarg.3
0x9bc8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9bcd  ldarg.2
0x9bce  ldarg.3
0x9bcf  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::GetTermSetForWeb_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9bd4  ret
0x9bd5  ldarg.s  4
0x9bd7  ldc.i4.0
0x9bd8  stind.i1
0x9bd9  ldarg.0
0x9bda  ldstr    aSetcrawlasfrie// "SetCrawlAsFriendlyUrlPage"
0x9bdf  ldarg.3
0x9be0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9be5  ldarg.2
0x9be6  ldarg.3
0x9be7  call     bool Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::SetCrawlAsFriendlyUrlPage_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9bec  box      [mscorlib]System.Boolean
0x9bf1  ret
0x9bf2  ldarg.s  4
0x9bf4  ldc.i4.0
0x9bf5  stind.i1
0x9bf6  ldarg.0
0x9bf7  ldstr    aGetnavigationl// "GetNavigationLcidForWeb"
0x9bfc  ldarg.3
0x9bfd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9c02  ldarg.2
0x9c03  ldarg.3
0x9c04  call     int32 Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::GetNavigationLcidForWeb_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9c09  box      [mscorlib]System.Int32
0x9c0e  ret
0x9c0f  ldarg.s  4
0x9c11  ldc.i4.1
0x9c12  stind.i1
0x9c13  ldarg.0
0x9c14  ldstr    aFlushsitefromc// "FlushSiteFromCache"
0x9c19  ldarg.3
0x9c1a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9c1f  ldarg.2
0x9c20  ldarg.3
0x9c21  call     void Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::FlushSiteFromCache_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9c26  ldnull
0x9c27  ret
0x9c28  ldarg.s  4
0x9c2a  ldc.i4.1
0x9c2b  stind.i1
0x9c2c  ldarg.0
0x9c2d  ldstr    aFlushwebfromca// "FlushWebFromCache"
0x9c32  ldarg.3
0x9c33  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9c38  ldarg.2
0x9c39  ldarg.3
0x9c3a  call     void Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::FlushWebFromCache_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9c3f  ldnull
0x9c40  ret
0x9c41  ldarg.s  4
0x9c43  ldc.i4.1
0x9c44  stind.i1
0x9c45  ldarg.0
0x9c46  ldstr    aFlushtermsetfr// "FlushTermSetFromCache"
0x9c4b  ldarg.3
0x9c4c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9c51  ldarg.2
0x9c52  ldarg.3
0x9c53  call     void Microsoft.SharePoint.Publishing.Navigation.TaxonomyNavigationServerStub::FlushTermSetFromCache_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9c58  ldnull
0x9c59  ret
0x9c5a  ldarg.1
0x9c5b  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x9c60  throw
```
