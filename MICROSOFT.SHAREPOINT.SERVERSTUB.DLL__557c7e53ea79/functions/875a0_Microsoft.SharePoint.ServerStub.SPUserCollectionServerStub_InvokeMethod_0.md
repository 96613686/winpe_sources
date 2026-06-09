# Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::InvokeMethod_0

- ea: `0x875a0`
- end: `0x877a1`
- name: `Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::InvokeMethod_0`
- size: `513`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x87480`
- `0x874a0`
- `0x874c0`
- `0x874e0`
- `0x87500`
- `0x87520`
- `0x87540`
- `0x87560`
- `0x87580`
- `0x875a0`

## string_xrefs

- `0x8763c`: `Create`
- `0x87762`: `Create`
- `0x87618`: `Remove`
- `0x87710`: `Remove`
- `0x8760c`: `RemoveById`
- `0x876f4`: `RemoveById`
- `0x87600`: `RemoveByLoginName`
- `0x876d8`: `RemoveByLoginName`

## pseudocode

```c

```

## disassembly

```asm
0x875a0  ldarg.s  4
0x875a2  brtrue.s loc_875AF
0x875a4  ldstr    aProxycontext// "proxyContext"
0x875a9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x875ae  throw
0x875af  ldarg.1
0x875b0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection
0x875b5  stloc.0
0x875b6  ldloc.0
0x875b7  brtrue.s loc_875C4
0x875b9  ldstr    aTarget// "target"
0x875be  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x875c3  throw
0x875c4  ldarg.0
0x875c5  ldarg.2
0x875c6  ldarg.s  4
0x875c8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x875cd  starg.s  2
0x875cf  ldarg.2
0x875d0  dup
0x875d1  stloc.1
0x875d2  brfalse  loc_87793
0x875d7  volatile.
0x875d9  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60016a8-1
0x875de  brtrue.s loc_8765A
0x875e0  ldc.i4.s 9
0x875e2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x875e7  dup
0x875e8  ldstr    aGetbyid// "GetById"
0x875ed  ldc.i4.0
0x875ee  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x875f3  dup
0x875f4  ldstr    aGetbyemail// "GetByEmail"
0x875f9  ldc.i4.1
0x875fa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x875ff  dup
0x87600  ldstr    aRemovebyloginn// "RemoveByLoginName"
0x87605  ldc.i4.2
0x87606  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8760b  dup
0x8760c  ldstr    aRemovebyid// "RemoveById"
0x87611  ldc.i4.3
0x87612  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x87617  dup
0x87618  ldstr    aRemove// "Remove"
0x8761d  ldc.i4.4
0x8761e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x87623  dup
0x87624  ldstr    aAdd// "Add"
0x87629  ldc.i4.5
0x8762a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8762f  dup
0x87630  ldstr    aAdduser// "AddUser"
0x87635  ldc.i4.6
0x87636  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8763b  dup
0x8763c  ldstr    aCreate// "Create"
0x87641  ldc.i4.7
0x87642  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x87647  dup
0x87648  ldstr    aGetbyloginname// "GetByLoginName"
0x8764d  ldc.i4.8
0x8764e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x87653  volatile.
0x87655  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60016a8-1
0x8765a  volatile.
0x8765c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60016a8-1
0x87661  ldloc.1
0x87662  ldloca.s 2
0x87664  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x87669  brfalse  loc_87793
0x8766e  ldloc.2
0x8766f  switch   loc_8769D, loc_876B8, loc_876D3, loc_876EF, loc_8770B, loc_87727, loc_87742, loc_8775D, loc_87778
0x87698  br       loc_87793
0x8769d  ldarg.s  5
0x8769f  ldc.i4.0
0x876a0  stind.i1
0x876a1  ldarg.0
0x876a2  ldstr    aGetbyid// "GetById"
0x876a7  ldarg.s  4
0x876a9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x876ae  ldloc.0
0x876af  ldarg.3
0x876b0  ldarg.s  4
0x876b2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::GetById_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x876b7  ret
0x876b8  ldarg.s  5
0x876ba  ldc.i4.0
0x876bb  stind.i1
0x876bc  ldarg.0
0x876bd  ldstr    aGetbyemail// "GetByEmail"
0x876c2  ldarg.s  4
0x876c4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x876c9  ldloc.0
0x876ca  ldarg.3
0x876cb  ldarg.s  4
0x876cd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::GetByEmail_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x876d2  ret
0x876d3  ldarg.s  5
0x876d5  ldc.i4.1
0x876d6  stind.i1
0x876d7  ldarg.0
0x876d8  ldstr    aRemovebyloginn// "RemoveByLoginName"
0x876dd  ldarg.s  4
0x876df  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x876e4  ldloc.0
0x876e5  ldarg.3
0x876e6  ldarg.s  4
0x876e8  call     void Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::RemoveByLoginName_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x876ed  ldnull
0x876ee  ret
0x876ef  ldarg.s  5
0x876f1  ldc.i4.1
0x876f2  stind.i1
0x876f3  ldarg.0
0x876f4  ldstr    aRemovebyid// "RemoveById"
0x876f9  ldarg.s  4
0x876fb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x87700  ldloc.0
0x87701  ldarg.3
0x87702  ldarg.s  4
0x87704  call     void Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::RemoveById_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x87709  ldnull
0x8770a  ret
0x8770b  ldarg.s  5
0x8770d  ldc.i4.1
0x8770e  stind.i1
0x8770f  ldarg.0
0x87710  ldstr    aRemove// "Remove"
0x87715  ldarg.s  4
0x87717  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8771c  ldloc.0
0x8771d  ldarg.3
0x8771e  ldarg.s  4
0x87720  call     void Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::Remove_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x87725  ldnull
0x87726  ret
0x87727  ldarg.s  5
0x87729  ldc.i4.0
0x8772a  stind.i1
0x8772b  ldarg.0
0x8772c  ldstr    aAdd// "Add"
0x87731  ldarg.s  4
0x87733  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x87738  ldloc.0
0x87739  ldarg.3
0x8773a  ldarg.s  4
0x8773c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::Add_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x87741  ret
0x87742  ldarg.s  5
0x87744  ldc.i4.0
0x87745  stind.i1
0x87746  ldarg.0
0x87747  ldstr    aAdduser// "AddUser"
0x8774c  ldarg.s  4
0x8774e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x87753  ldloc.0
0x87754  ldarg.3
0x87755  ldarg.s  4
0x87757  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::AddUser_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8775c  ret
0x8775d  ldarg.s  5
0x8775f  ldc.i4.0
0x87760  stind.i1
0x87761  ldarg.0
0x87762  ldstr    aCreate// "Create"
0x87767  ldarg.s  4
0x87769  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8776e  ldloc.0
0x8776f  ldarg.3
0x87770  ldarg.s  4
0x87772  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::Create_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x87777  ret
0x87778  ldarg.s  5
0x8777a  ldc.i4.0
0x8777b  stind.i1
0x8777c  ldarg.0
0x8777d  ldstr    aGetbyloginname// "GetByLoginName"
0x87782  ldarg.s  4
0x87784  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x87789  ldloc.0
0x8778a  ldarg.3
0x8778b  ldarg.s  4
0x8778d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser Microsoft.SharePoint.ServerStub.SPUserCollectionServerStub::GetByLoginName_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x87792  ret
0x87793  ldarg.0
0x87794  ldarg.1
0x87795  ldarg.2
0x87796  ldarg.3
0x87797  ldarg.s  4
0x87799  ldarg.s  5
0x8779b  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x877a0  ret
```
