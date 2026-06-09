# Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::InvokeStaticMethod_0

- ea: `0x11d10`
- end: `0x11e60`
- name: `Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::InvokeStaticMethod_0`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x11c50`
- `0x11c70`
- `0x11c90`
- `0x11cb0`
- `0x11cd0`
- `0x11cf0`
- `0x11d10`

## string_xrefs

- `0x11d58`: `DeleteSettings`
- `0x11dfb`: `DeleteSettings`
- `0x11d64`: `GetPlugin`
- `0x11e14`: `GetPlugin`
- `0x11d70`: `SetPlugin`
- `0x11e2c`: `SetPlugin`
- `0x11d7c`: `DeletePlugin`
- `0x11e45`: `DeletePlugin`

## pseudocode

```c

```

## disassembly

```asm
0x11d10  ldarg.3
0x11d11  brtrue.s loc_11D1E
0x11d13  ldstr    aProxycontext// "proxyContext"
0x11d18  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11d1d  throw
0x11d1e  ldarg.0
0x11d1f  ldarg.1
0x11d20  ldarg.3
0x11d21  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11d26  starg.s  1
0x11d28  ldarg.1
0x11d29  dup
0x11d2a  stloc.0
0x11d2b  brfalse  loc_11E59
0x11d30  volatile.
0x11d32  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000329-1
0x11d37  brtrue.s loc_11D8E
0x11d39  ldc.i4.6
0x11d3a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x11d3f  dup
0x11d40  ldstr    aGetsettings// "GetSettings"
0x11d45  ldc.i4.0
0x11d46  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11d4b  dup
0x11d4c  ldstr    aSetsettings// "SetSettings"
0x11d51  ldc.i4.1
0x11d52  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11d57  dup
0x11d58  ldstr    aDeletesettings// "DeleteSettings"
0x11d5d  ldc.i4.2
0x11d5e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11d63  dup
0x11d64  ldstr    aGetplugin// "GetPlugin"
0x11d69  ldc.i4.3
0x11d6a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11d6f  dup
0x11d70  ldstr    aSetplugin// "SetPlugin"
0x11d75  ldc.i4.4
0x11d76  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11d7b  dup
0x11d7c  ldstr    aDeleteplugin// "DeletePlugin"
0x11d81  ldc.i4.5
0x11d82  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x11d87  volatile.
0x11d89  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000329-1
0x11d8e  volatile.
0x11d90  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000329-1
0x11d95  ldloc.0
0x11d96  ldloca.s 1
0x11d98  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x11d9d  brfalse  loc_11E59
0x11da2  ldloc.1
0x11da3  switch   loc_11DC5, loc_11DDD, loc_11DF6, loc_11E0F, loc_11E27, loc_11E40
0x11dc0  br       loc_11E59
0x11dc5  ldarg.s  4
0x11dc7  ldc.i4.0
0x11dc8  stind.i1
0x11dc9  ldarg.0
0x11dca  ldstr    aGetsettings// "GetSettings"
0x11dcf  ldarg.3
0x11dd0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11dd5  ldarg.2
0x11dd6  ldarg.3
0x11dd7  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinSettings Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::GetSettings_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11ddc  ret
0x11ddd  ldarg.s  4
0x11ddf  ldc.i4.1
0x11de0  stind.i1
0x11de1  ldarg.0
0x11de2  ldstr    aSetsettings// "SetSettings"
0x11de7  ldarg.3
0x11de8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11ded  ldarg.2
0x11dee  ldarg.3
0x11def  call     void Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::SetSettings_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11df4  ldnull
0x11df5  ret
0x11df6  ldarg.s  4
0x11df8  ldc.i4.1
0x11df9  stind.i1
0x11dfa  ldarg.0
0x11dfb  ldstr    aDeletesettings// "DeleteSettings"
0x11e00  ldarg.3
0x11e01  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11e06  ldarg.2
0x11e07  ldarg.3
0x11e08  call     void Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::DeleteSettings_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11e0d  ldnull
0x11e0e  ret
0x11e0f  ldarg.s  4
0x11e11  ldc.i4.0
0x11e12  stind.i1
0x11e13  ldarg.0
0x11e14  ldstr    aGetplugin// "GetPlugin"
0x11e19  ldarg.3
0x11e1a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11e1f  ldarg.2
0x11e20  ldarg.3
0x11e21  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::GetPlugin_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11e26  ret
0x11e27  ldarg.s  4
0x11e29  ldc.i4.1
0x11e2a  stind.i1
0x11e2b  ldarg.0
0x11e2c  ldstr    aSetplugin// "SetPlugin"
0x11e31  ldarg.3
0x11e32  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11e37  ldarg.2
0x11e38  ldarg.3
0x11e39  call     void Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::SetPlugin_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11e3e  ldnull
0x11e3f  ret
0x11e40  ldarg.s  4
0x11e42  ldc.i4.1
0x11e43  stind.i1
0x11e44  ldarg.0
0x11e45  ldstr    aDeleteplugin// "DeletePlugin"
0x11e4a  ldarg.3
0x11e4b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x11e50  ldarg.2
0x11e51  ldarg.3
0x11e52  call     void Microsoft.SharePoint.Publishing.SiteServicesAddinsServerStub::DeletePlugin_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x11e57  ldnull
0x11e58  ret
0x11e59  ldarg.1
0x11e5a  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x11e5f  throw
```
