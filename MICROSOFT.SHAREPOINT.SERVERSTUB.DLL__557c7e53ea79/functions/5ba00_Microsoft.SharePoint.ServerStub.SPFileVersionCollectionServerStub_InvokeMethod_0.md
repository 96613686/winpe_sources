# Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::InvokeMethod_0

- ea: `0x5ba00`
- end: `0x5bbad`
- name: `Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::InvokeMethod_0`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x5b930`
- `0x5b950`
- `0x5b970`
- `0x5b990`
- `0x5b9b0`
- `0x5b9d0`
- `0x5b9e0`
- `0x5ba00`

## string_xrefs

- `0x5ba83`: `DeleteAll`
- `0x5bb6c`: `DeleteAll`
- `0x5ba53`: `DeleteByID`
- `0x5bafc`: `DeleteByID`
- `0x5ba6b`: `DeleteByLabel`
- `0x5bb34`: `DeleteByLabel`

## pseudocode

```c

```

## disassembly

```asm
0x5ba00  ldarg.s  4
0x5ba02  brtrue.s loc_5BA0F
0x5ba04  ldstr    aProxycontext// "proxyContext"
0x5ba09  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5ba0e  throw
0x5ba0f  ldarg.1
0x5ba10  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersionCollection
0x5ba15  stloc.0
0x5ba16  ldloc.0
0x5ba17  brtrue.s loc_5BA24
0x5ba19  ldstr    aTarget// "target"
0x5ba1e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5ba23  throw
0x5ba24  ldarg.0
0x5ba25  ldarg.2
0x5ba26  ldarg.s  4
0x5ba28  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ba2d  starg.s  2
0x5ba2f  ldarg.2
0x5ba30  dup
0x5ba31  stloc.1
0x5ba32  brfalse  loc_5BB9F
0x5ba37  volatile.
0x5ba39  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001044-1
0x5ba3e  brtrue.s loc_5BAA1
0x5ba40  ldc.i4.7
0x5ba41  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x5ba46  dup
0x5ba47  ldstr    aGetbyid// "GetById"
0x5ba4c  ldc.i4.0
0x5ba4d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ba52  dup
0x5ba53  ldstr    aDeletebyid// "DeleteByID"
0x5ba58  ldc.i4.1
0x5ba59  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ba5e  dup
0x5ba5f  ldstr    aRecyclebyid// "RecycleByID"
0x5ba64  ldc.i4.2
0x5ba65  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ba6a  dup
0x5ba6b  ldstr    aDeletebylabel// "DeleteByLabel"
0x5ba70  ldc.i4.3
0x5ba71  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ba76  dup
0x5ba77  ldstr    aRecyclebylabel// "RecycleByLabel"
0x5ba7c  ldc.i4.4
0x5ba7d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ba82  dup
0x5ba83  ldstr    aDeleteall// "DeleteAll"
0x5ba88  ldc.i4.5
0x5ba89  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ba8e  dup
0x5ba8f  ldstr    aRestorebylabel// "RestoreByLabel"
0x5ba94  ldc.i4.6
0x5ba95  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ba9a  volatile.
0x5ba9c  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001044-1
0x5baa1  volatile.
0x5baa3  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001044-1
0x5baa8  ldloc.1
0x5baa9  ldloca.s 2
0x5baab  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x5bab0  brfalse  loc_5BB9F
0x5bab5  ldloc.2
0x5bab6  switch   loc_5BADC, loc_5BAF7, loc_5BB13, loc_5BB2F, loc_5BB4B, loc_5BB67, loc_5BB83
0x5bad7  br       loc_5BB9F
0x5badc  ldarg.s  5
0x5bade  ldc.i4.0
0x5badf  stind.i1
0x5bae0  ldarg.0
0x5bae1  ldstr    aGetbyid// "GetById"
0x5bae6  ldarg.s  4
0x5bae8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5baed  ldloc.0
0x5baee  ldarg.3
0x5baef  ldarg.s  4
0x5baf1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::GetById_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersionCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5baf6  ret
0x5baf7  ldarg.s  5
0x5baf9  ldc.i4.1
0x5bafa  stind.i1
0x5bafb  ldarg.0
0x5bafc  ldstr    aDeletebyid// "DeleteByID"
0x5bb01  ldarg.s  4
0x5bb03  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5bb08  ldloc.0
0x5bb09  ldarg.3
0x5bb0a  ldarg.s  4
0x5bb0c  call     void Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::DeleteByID_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersionCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5bb11  ldnull
0x5bb12  ret
0x5bb13  ldarg.s  5
0x5bb15  ldc.i4.1
0x5bb16  stind.i1
0x5bb17  ldarg.0
0x5bb18  ldstr    aRecyclebyid// "RecycleByID"
0x5bb1d  ldarg.s  4
0x5bb1f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5bb24  ldloc.0
0x5bb25  ldarg.3
0x5bb26  ldarg.s  4
0x5bb28  call     void Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::RecycleByID_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersionCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5bb2d  ldnull
0x5bb2e  ret
0x5bb2f  ldarg.s  5
0x5bb31  ldc.i4.1
0x5bb32  stind.i1
0x5bb33  ldarg.0
0x5bb34  ldstr    aDeletebylabel// "DeleteByLabel"
0x5bb39  ldarg.s  4
0x5bb3b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5bb40  ldloc.0
0x5bb41  ldarg.3
0x5bb42  ldarg.s  4
0x5bb44  call     void Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::DeleteByLabel_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersionCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5bb49  ldnull
0x5bb4a  ret
0x5bb4b  ldarg.s  5
0x5bb4d  ldc.i4.1
0x5bb4e  stind.i1
0x5bb4f  ldarg.0
0x5bb50  ldstr    aRecyclebylabel// "RecycleByLabel"
0x5bb55  ldarg.s  4
0x5bb57  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5bb5c  ldloc.0
0x5bb5d  ldarg.3
0x5bb5e  ldarg.s  4
0x5bb60  call     void Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::RecycleByLabel_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersionCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5bb65  ldnull
0x5bb66  ret
0x5bb67  ldarg.s  5
0x5bb69  ldc.i4.1
0x5bb6a  stind.i1
0x5bb6b  ldarg.0
0x5bb6c  ldstr    aDeleteall// "DeleteAll"
0x5bb71  ldarg.s  4
0x5bb73  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5bb78  ldloc.0
0x5bb79  ldarg.3
0x5bb7a  ldarg.s  4
0x5bb7c  call     void Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::DeleteAll_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersionCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5bb81  ldnull
0x5bb82  ret
0x5bb83  ldarg.s  5
0x5bb85  ldc.i4.1
0x5bb86  stind.i1
0x5bb87  ldarg.0
0x5bb88  ldstr    aRestorebylabel// "RestoreByLabel"
0x5bb8d  ldarg.s  4
0x5bb8f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5bb94  ldloc.0
0x5bb95  ldarg.3
0x5bb96  ldarg.s  4
0x5bb98  call     void Microsoft.SharePoint.ServerStub.SPFileVersionCollectionServerStub::RestoreByLabel_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersionCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5bb9d  ldnull
0x5bb9e  ret
0x5bb9f  ldarg.0
0x5bba0  ldarg.1
0x5bba1  ldarg.2
0x5bba2  ldarg.3
0x5bba3  ldarg.s  4
0x5bba5  ldarg.s  5
0x5bba7  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x5bbac  ret
```
