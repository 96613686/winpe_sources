# Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::InvokeStaticMethod

- ea: `0x11aa0`
- end: `0x11bf0`
- name: `Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::InvokeStaticMethod`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x119e0`
- `0x11a00`
- `0x11a20`
- `0x11a40`
- `0x11a60`
- `0x11a80`
- `0x11aa0`

## string_xrefs

- `0x11ae8`: `DeleteSettings`
- `0x11b8b`: `DeleteSettings`
- `0x11af4`: `GetPlugin`
- `0x11ba4`: `GetPlugin`
- `0x11b00`: `SetPlugin`
- `0x11bbc`: `SetPlugin`
- `0x11b0c`: `DeletePlugin`
- `0x11bd5`: `DeletePlugin`

## pseudocode

```c

```

## disassembly

```asm
0x11aa0  ldarg.3
0x11aa1  brtrue.s loc_11AAE
0x11aa3  ldstr    aProxycontext// "proxyContext"
0x11aa8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11aad  throw
0x11aae  ldarg.0
0x11aaf  ldarg.1
0x11ab0  ldarg.3
0x11ab1  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11ab6  starg.s  1
0x11ab8  ldarg.1
0x11ab9  dup
0x11aba  stloc.0
0x11abb  brfalse  loc_11BE9
0x11ac0  volatile.
0x11ac2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600031f-1
0x11ac7  brtrue.s loc_11B1E
0x11ac9  ldc.i4.6
0x11aca  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x11acf  dup
0x11ad0  ldstr    aGetsettings// "GetSettings"
0x11ad5  ldc.i4.0
0x11ad6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11adb  dup
0x11adc  ldstr    aSetsettings// "SetSettings"
0x11ae1  ldc.i4.1
0x11ae2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11ae7  dup
0x11ae8  ldstr    aDeletesettings// "DeleteSettings"
0x11aed  ldc.i4.2
0x11aee  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11af3  dup
0x11af4  ldstr    aGetplugin// "GetPlugin"
0x11af9  ldc.i4.3
0x11afa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11aff  dup
0x11b00  ldstr    aSetplugin// "SetPlugin"
0x11b05  ldc.i4.4
0x11b06  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11b0b  dup
0x11b0c  ldstr    aDeleteplugin// "DeletePlugin"
0x11b11  ldc.i4.5
0x11b12  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11b17  volatile.
0x11b19  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600031f-1
0x11b1e  volatile.
0x11b20  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600031f-1
0x11b25  ldloc.0
0x11b26  ldloca.s 1
0x11b28  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x11b2d  brfalse  loc_11BE9
0x11b32  ldloc.1
0x11b33  switch   loc_11B55, loc_11B6D, loc_11B86, loc_11B9F, loc_11BB7, loc_11BD0
0x11b50  br       loc_11BE9
0x11b55  ldarg.s  4
0x11b57  ldc.i4.0
0x11b58  stind.i1
0x11b59  ldarg.0
0x11b5a  ldstr    aGetsettings// "GetSettings"
0x11b5f  ldarg.3
0x11b60  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11b65  ldarg.2
0x11b66  ldarg.3
0x11b67  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::GetSettings_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11b6c  ret
0x11b6d  ldarg.s  4
0x11b6f  ldc.i4.1
0x11b70  stind.i1
0x11b71  ldarg.0
0x11b72  ldstr    aSetsettings// "SetSettings"
0x11b77  ldarg.3
0x11b78  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11b7d  ldarg.2
0x11b7e  ldarg.3
0x11b7f  call     void Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::SetSettings_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11b84  ldnull
0x11b85  ret
0x11b86  ldarg.s  4
0x11b88  ldc.i4.1
0x11b89  stind.i1
0x11b8a  ldarg.0
0x11b8b  ldstr    aDeletesettings// "DeleteSettings"
0x11b90  ldarg.3
0x11b91  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11b96  ldarg.2
0x11b97  ldarg.3
0x11b98  call     void Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::DeleteSettings_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11b9d  ldnull
0x11b9e  ret
0x11b9f  ldarg.s  4
0x11ba1  ldc.i4.0
0x11ba2  stind.i1
0x11ba3  ldarg.0
0x11ba4  ldstr    aGetplugin// "GetPlugin"
0x11ba9  ldarg.3
0x11baa  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11baf  ldarg.2
0x11bb0  ldarg.3
0x11bb1  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::GetPlugin_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11bb6  ret
0x11bb7  ldarg.s  4
0x11bb9  ldc.i4.1
0x11bba  stind.i1
0x11bbb  ldarg.0
0x11bbc  ldstr    aSetplugin// "SetPlugin"
0x11bc1  ldarg.3
0x11bc2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11bc7  ldarg.2
0x11bc8  ldarg.3
0x11bc9  call     void Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::SetPlugin_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11bce  ldnull
0x11bcf  ret
0x11bd0  ldarg.s  4
0x11bd2  ldc.i4.1
0x11bd3  stind.i1
0x11bd4  ldarg.0
0x11bd5  ldstr    aDeleteplugin// "DeletePlugin"
0x11bda  ldarg.3
0x11bdb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11be0  ldarg.2
0x11be1  ldarg.3
0x11be2  call     void Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::DeletePlugin_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11be7  ldnull
0x11be8  ret
0x11be9  ldarg.1
0x11bea  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x11bef  throw
```
