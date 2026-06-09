# Microsoft.SharePoint.ServerStub.RelatedItemManagerServerStub::InvokeStaticMethod_0

- ea: `0x2dd10`
- end: `0x2de60`
- name: `Microsoft.SharePoint.ServerStub.RelatedItemManagerServerStub::InvokeStaticMethod_0`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x2db10`
- `0x2db40`
- `0x2db70`
- `0x2dbf0`
- `0x2dc40`
- `0x2dc90`
- `0x2dd10`

## string_xrefs

- `0x2dd58`: `AddSingleLink`
- `0x2ddfa`: `AddSingleLink`
- `0x2dd64`: `AddSingleLinkToUrl`
- `0x2de13`: `AddSingleLinkToUrl`
- `0x2dd70`: `AddSingleLinkFromUrl`
- `0x2de2c`: `AddSingleLinkFromUrl`
- `0x2dd7c`: `DeleteSingleLink`
- `0x2de45`: `DeleteSingleLink`

## pseudocode

```c

```

## disassembly

```asm
0x2dd10  ldarg.3
0x2dd11  brtrue.s loc_2DD1E
0x2dd13  ldstr    aProxycontext// "proxyContext"
0x2dd18  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2dd1d  throw
0x2dd1e  ldarg.0
0x2dd1f  ldarg.1
0x2dd20  ldarg.3
0x2dd21  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2dd26  starg.s  1
0x2dd28  ldarg.1
0x2dd29  dup
0x2dd2a  stloc.0
0x2dd2b  brfalse  loc_2DE59
0x2dd30  volatile.
0x2dd32  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60008b2-1
0x2dd37  brtrue.s loc_2DD8E
0x2dd39  ldc.i4.6
0x2dd3a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x2dd3f  dup
0x2dd40  ldstr    aGetrelateditem// "GetRelatedItems"
0x2dd45  ldc.i4.0
0x2dd46  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2dd4b  dup
0x2dd4c  ldstr    aGetpageonerela// "GetPageOneRelatedItems"
0x2dd51  ldc.i4.1
0x2dd52  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2dd57  dup
0x2dd58  ldstr    aAddsinglelink// "AddSingleLink"
0x2dd5d  ldc.i4.2
0x2dd5e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2dd63  dup
0x2dd64  ldstr    aAddsinglelinkt// "AddSingleLinkToUrl"
0x2dd69  ldc.i4.3
0x2dd6a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2dd6f  dup
0x2dd70  ldstr    aAddsinglelinkf// "AddSingleLinkFromUrl"
0x2dd75  ldc.i4.4
0x2dd76  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2dd7b  dup
0x2dd7c  ldstr    aDeletesingleli// "DeleteSingleLink"
0x2dd81  ldc.i4.5
0x2dd82  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x2dd87  volatile.
0x2dd89  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60008b2-1
0x2dd8e  volatile.
0x2dd90  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60008b2-1
0x2dd95  ldloc.0
0x2dd96  ldloca.s 1
0x2dd98  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x2dd9d  brfalse  loc_2DE59
0x2dda2  ldloc.1
0x2dda3  switch   loc_2DDC5, loc_2DDDD, loc_2DDF5, loc_2DE0E, loc_2DE27, loc_2DE40
0x2ddc0  br       loc_2DE59
0x2ddc5  ldarg.s  4
0x2ddc7  ldc.i4.0
0x2ddc8  stind.i1
0x2ddc9  ldarg.0
0x2ddca  ldstr    aGetrelateditem// "GetRelatedItems"
0x2ddcf  ldarg.3
0x2ddd0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2ddd5  ldarg.2
0x2ddd6  ldarg.3
0x2ddd7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.RelatedItem[] Microsoft.SharePoint.ServerStub.RelatedItemManagerServerStub::GetRelatedItems_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2dddc  ret
0x2dddd  ldarg.s  4
0x2dddf  ldc.i4.0
0x2dde0  stind.i1
0x2dde1  ldarg.0
0x2dde2  ldstr    aGetpageonerela// "GetPageOneRelatedItems"
0x2dde7  ldarg.3
0x2dde8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2dded  ldarg.2
0x2ddee  ldarg.3
0x2ddef  call     class [Microsoft.SharePoint]Microsoft.SharePoint.RelatedItem[] Microsoft.SharePoint.ServerStub.RelatedItemManagerServerStub::GetPageOneRelatedItems_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2ddf4  ret
0x2ddf5  ldarg.s  4
0x2ddf7  ldc.i4.1
0x2ddf8  stind.i1
0x2ddf9  ldarg.0
0x2ddfa  ldstr    aAddsinglelink// "AddSingleLink"
0x2ddff  ldarg.3
0x2de00  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2de05  ldarg.2
0x2de06  ldarg.3
0x2de07  call     void Microsoft.SharePoint.ServerStub.RelatedItemManagerServerStub::AddSingleLink_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2de0c  ldnull
0x2de0d  ret
0x2de0e  ldarg.s  4
0x2de10  ldc.i4.1
0x2de11  stind.i1
0x2de12  ldarg.0
0x2de13  ldstr    aAddsinglelinkt// "AddSingleLinkToUrl"
0x2de18  ldarg.3
0x2de19  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2de1e  ldarg.2
0x2de1f  ldarg.3
0x2de20  call     void Microsoft.SharePoint.ServerStub.RelatedItemManagerServerStub::AddSingleLinkToUrl_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2de25  ldnull
0x2de26  ret
0x2de27  ldarg.s  4
0x2de29  ldc.i4.1
0x2de2a  stind.i1
0x2de2b  ldarg.0
0x2de2c  ldstr    aAddsinglelinkf// "AddSingleLinkFromUrl"
0x2de31  ldarg.3
0x2de32  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2de37  ldarg.2
0x2de38  ldarg.3
0x2de39  call     void Microsoft.SharePoint.ServerStub.RelatedItemManagerServerStub::AddSingleLinkFromUrl_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2de3e  ldnull
0x2de3f  ret
0x2de40  ldarg.s  4
0x2de42  ldc.i4.1
0x2de43  stind.i1
0x2de44  ldarg.0
0x2de45  ldstr    aDeletesingleli// "DeleteSingleLink"
0x2de4a  ldarg.3
0x2de4b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2de50  ldarg.2
0x2de51  ldarg.3
0x2de52  call     void Microsoft.SharePoint.ServerStub.RelatedItemManagerServerStub::DeleteSingleLink_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2de57  ldnull
0x2de58  ret
0x2de59  ldarg.1
0x2de5a  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x2de5f  throw
```
