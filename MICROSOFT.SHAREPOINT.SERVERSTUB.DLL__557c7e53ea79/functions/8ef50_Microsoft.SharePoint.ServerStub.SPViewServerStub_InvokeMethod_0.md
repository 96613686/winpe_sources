# Microsoft.SharePoint.ServerStub.SPViewServerStub::InvokeMethod_0

- ea: `0x8ef50`
- end: `0x8f0cf`
- name: `Microsoft.SharePoint.ServerStub.SPViewServerStub::InvokeMethod_0`
- size: `383`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x8ee90`
- `0x8eeb0`
- `0x8eec0`
- `0x8eed0`
- `0x8ef10`
- `0x8ef40`
- `0x8ef50`

## string_xrefs

- `0x8efaf`: `Update`
- `0x8f058`: `Update`
- `0x8efd3`: `DeleteObject`
- `0x8f0aa`: `DeleteObject`
- `0x8ef97`: `SetViewXml`
- `0x8f021`: `SetViewXml`
- `0x8efc7`: `RemoveFromSpotlight`
- `0x8f08f`: `RemoveFromSpotlight`

## pseudocode

```c

```

## disassembly

```asm
0x8ef50  ldarg.s  4
0x8ef52  brtrue.s loc_8EF5F
0x8ef54  ldstr    aProxycontext// "proxyContext"
0x8ef59  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8ef5e  throw
0x8ef5f  ldarg.1
0x8ef60  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPView
0x8ef65  stloc.0
0x8ef66  ldloc.0
0x8ef67  brtrue.s loc_8EF74
0x8ef69  ldstr    aTarget// "target"
0x8ef6e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8ef73  throw
0x8ef74  ldarg.0
0x8ef75  ldarg.2
0x8ef76  ldarg.s  4
0x8ef78  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8ef7d  starg.s  2
0x8ef7f  ldarg.2
0x8ef80  dup
0x8ef81  stloc.1
0x8ef82  brfalse  loc_8F0C1
0x8ef87  volatile.
0x8ef89  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001798-1
0x8ef8e  brtrue.s loc_8EFE5
0x8ef90  ldc.i4.6
0x8ef91  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x8ef96  dup
0x8ef97  ldstr    aSetviewxml// "SetViewXml"
0x8ef9c  ldc.i4.0
0x8ef9d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8efa2  dup
0x8efa3  ldstr    aRenderashtml// "RenderAsHtml"
0x8efa8  ldc.i4.1
0x8efa9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8efae  dup
0x8efaf  ldstr    aUpdate// "Update"
0x8efb4  ldc.i4.2
0x8efb5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8efba  dup
0x8efbb  ldstr    aAddtospotlight// "AddToSpotlight"
0x8efc0  ldc.i4.3
0x8efc1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8efc6  dup
0x8efc7  ldstr    aRemovefromspot// "RemoveFromSpotlight"
0x8efcc  ldc.i4.4
0x8efcd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8efd2  dup
0x8efd3  ldstr    aDeleteobject// "DeleteObject"
0x8efd8  ldc.i4.5
0x8efd9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8efde  volatile.
0x8efe0  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001798-1
0x8efe5  volatile.
0x8efe7  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001798-1
0x8efec  ldloc.1
0x8efed  ldloca.s 2
0x8efef  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x8eff4  brfalse  loc_8F0C1
0x8eff9  ldloc.2
0x8effa  switch   loc_8F01C, loc_8F038, loc_8F053, loc_8F06F, loc_8F08A, loc_8F0A5
0x8f017  br       loc_8F0C1
0x8f01c  ldarg.s  5
0x8f01e  ldc.i4.1
0x8f01f  stind.i1
0x8f020  ldarg.0
0x8f021  ldstr    aSetviewxml// "SetViewXml"
0x8f026  ldarg.s  4
0x8f028  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8f02d  ldloc.0
0x8f02e  ldarg.3
0x8f02f  ldarg.s  4
0x8f031  call     void Microsoft.SharePoint.ServerStub.SPViewServerStub::SetViewXml_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPView target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8f036  ldnull
0x8f037  ret
0x8f038  ldarg.s  5
0x8f03a  ldc.i4.0
0x8f03b  stind.i1
0x8f03c  ldarg.0
0x8f03d  ldstr    aRenderashtml// "RenderAsHtml"
0x8f042  ldarg.s  4
0x8f044  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8f049  ldloc.0
0x8f04a  ldarg.3
0x8f04b  ldarg.s  4
0x8f04d  call     string Microsoft.SharePoint.ServerStub.SPViewServerStub::RenderAsHtml_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPView target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8f052  ret
0x8f053  ldarg.s  5
0x8f055  ldc.i4.1
0x8f056  stind.i1
0x8f057  ldarg.0
0x8f058  ldstr    aUpdate// "Update"
0x8f05d  ldarg.s  4
0x8f05f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8f064  ldloc.0
0x8f065  ldarg.3
0x8f066  ldarg.s  4
0x8f068  call     void Microsoft.SharePoint.ServerStub.SPViewServerStub::Update_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPView target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8f06d  ldnull
0x8f06e  ret
0x8f06f  ldarg.s  5
0x8f071  ldc.i4.0
0x8f072  stind.i1
0x8f073  ldarg.0
0x8f074  ldstr    aAddtospotlight// "AddToSpotlight"
0x8f079  ldarg.s  4
0x8f07b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8f080  ldloc.0
0x8f081  ldarg.3
0x8f082  ldarg.s  4
0x8f084  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSpotlightResult Microsoft.SharePoint.ServerStub.SPViewServerStub::AddToSpotlight_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPView target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8f089  ret
0x8f08a  ldarg.s  5
0x8f08c  ldc.i4.0
0x8f08d  stind.i1
0x8f08e  ldarg.0
0x8f08f  ldstr    aRemovefromspot// "RemoveFromSpotlight"
0x8f094  ldarg.s  4
0x8f096  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8f09b  ldloc.0
0x8f09c  ldarg.3
0x8f09d  ldarg.s  4
0x8f09f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSpotlightResult Microsoft.SharePoint.ServerStub.SPViewServerStub::RemoveFromSpotlight_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPView target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8f0a4  ret
0x8f0a5  ldarg.s  5
0x8f0a7  ldc.i4.1
0x8f0a8  stind.i1
0x8f0a9  ldarg.0
0x8f0aa  ldstr    aDeleteobject// "DeleteObject"
0x8f0af  ldarg.s  4
0x8f0b1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8f0b6  ldloc.0
0x8f0b7  ldarg.3
0x8f0b8  ldarg.s  4
0x8f0ba  call     void Microsoft.SharePoint.ServerStub.SPViewServerStub::DeleteObject_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPView target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8f0bf  ldnull
0x8f0c0  ret
0x8f0c1  ldarg.0
0x8f0c2  ldarg.1
0x8f0c3  ldarg.2
0x8f0c4  ldarg.3
0x8f0c5  ldarg.s  4
0x8f0c7  ldarg.s  5
0x8f0c9  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x8f0ce  ret
```
