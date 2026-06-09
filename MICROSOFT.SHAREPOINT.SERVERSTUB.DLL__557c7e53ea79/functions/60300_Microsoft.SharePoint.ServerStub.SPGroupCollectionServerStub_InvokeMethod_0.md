# Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::InvokeMethod_0

- ea: `0x60300`
- end: `0x604aa`
- name: `Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::InvokeMethod_0`
- size: `426`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x60220`
- `0x60240`
- `0x60260`
- `0x60280`
- `0x602a0`
- `0x602c0`
- `0x602e0`
- `0x60300`

## string_xrefs

- `0x6036b`: `Create`
- `0x60432`: `Create`
- `0x6038f`: `Remove`
- `0x60485`: `Remove`
- `0x60383`: `RemoveById`
- `0x60469`: `RemoveById`
- `0x60377`: `RemoveByLoginName`
- `0x6044d`: `RemoveByLoginName`

## pseudocode

```c

```

## disassembly

```asm
0x60300  ldarg.s  4
0x60302  brtrue.s loc_6030F
0x60304  ldstr    aProxycontext// "proxyContext"
0x60309  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6030e  throw
0x6030f  ldarg.1
0x60310  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCollection
0x60315  stloc.0
0x60316  ldloc.0
0x60317  brtrue.s loc_60324
0x60319  ldstr    aTarget// "target"
0x6031e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x60323  throw
0x60324  ldarg.0
0x60325  ldarg.2
0x60326  ldarg.s  4
0x60328  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6032d  starg.s  2
0x6032f  ldarg.2
0x60330  dup
0x60331  stloc.1
0x60332  brfalse  loc_6049C
0x60337  volatile.
0x60339  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600111f-1
0x6033e  brtrue.s loc_603A1
0x60340  ldc.i4.7
0x60341  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x60346  dup
0x60347  ldstr    aGetbyname// "GetByName"
0x6034c  ldc.i4.0
0x6034d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x60352  dup
0x60353  ldstr    aGetbyid// "GetById"
0x60358  ldc.i4.1
0x60359  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6035e  dup
0x6035f  ldstr    aAdd// "Add"
0x60364  ldc.i4.2
0x60365  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6036a  dup
0x6036b  ldstr    aCreate// "Create"
0x60370  ldc.i4.3
0x60371  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x60376  dup
0x60377  ldstr    aRemovebyloginn// "RemoveByLoginName"
0x6037c  ldc.i4.4
0x6037d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x60382  dup
0x60383  ldstr    aRemovebyid// "RemoveById"
0x60388  ldc.i4.5
0x60389  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6038e  dup
0x6038f  ldstr    aRemove// "Remove"
0x60394  ldc.i4.6
0x60395  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6039a  volatile.
0x6039c  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600111f-1
0x603a1  volatile.
0x603a3  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600111f-1
0x603a8  ldloc.1
0x603a9  ldloca.s 2
0x603ab  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x603b0  brfalse  loc_6049C
0x603b5  ldloc.2
0x603b6  switch   loc_603DC, loc_603F7, loc_60412, loc_6042D, loc_60448, loc_60464, loc_60480
0x603d7  br       loc_6049C
0x603dc  ldarg.s  5
0x603de  ldc.i4.0
0x603df  stind.i1
0x603e0  ldarg.0
0x603e1  ldstr    aGetbyname// "GetByName"
0x603e6  ldarg.s  4
0x603e8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x603ed  ldloc.0
0x603ee  ldarg.3
0x603ef  ldarg.s  4
0x603f1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::GetByName_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x603f6  ret
0x603f7  ldarg.s  5
0x603f9  ldc.i4.0
0x603fa  stind.i1
0x603fb  ldarg.0
0x603fc  ldstr    aGetbyid// "GetById"
0x60401  ldarg.s  4
0x60403  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x60408  ldloc.0
0x60409  ldarg.3
0x6040a  ldarg.s  4
0x6040c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::GetById_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x60411  ret
0x60412  ldarg.s  5
0x60414  ldc.i4.0
0x60415  stind.i1
0x60416  ldarg.0
0x60417  ldstr    aAdd// "Add"
0x6041c  ldarg.s  4
0x6041e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x60423  ldloc.0
0x60424  ldarg.3
0x60425  ldarg.s  4
0x60427  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::Add_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6042c  ret
0x6042d  ldarg.s  5
0x6042f  ldc.i4.0
0x60430  stind.i1
0x60431  ldarg.0
0x60432  ldstr    aCreate// "Create"
0x60437  ldarg.s  4
0x60439  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6043e  ldloc.0
0x6043f  ldarg.3
0x60440  ldarg.s  4
0x60442  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroup Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::Create_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x60447  ret
0x60448  ldarg.s  5
0x6044a  ldc.i4.1
0x6044b  stind.i1
0x6044c  ldarg.0
0x6044d  ldstr    aRemovebyloginn// "RemoveByLoginName"
0x60452  ldarg.s  4
0x60454  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x60459  ldloc.0
0x6045a  ldarg.3
0x6045b  ldarg.s  4
0x6045d  call     void Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::RemoveByLoginName_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x60462  ldnull
0x60463  ret
0x60464  ldarg.s  5
0x60466  ldc.i4.1
0x60467  stind.i1
0x60468  ldarg.0
0x60469  ldstr    aRemovebyid// "RemoveById"
0x6046e  ldarg.s  4
0x60470  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x60475  ldloc.0
0x60476  ldarg.3
0x60477  ldarg.s  4
0x60479  call     void Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::RemoveById_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6047e  ldnull
0x6047f  ret
0x60480  ldarg.s  5
0x60482  ldc.i4.1
0x60483  stind.i1
0x60484  ldarg.0
0x60485  ldstr    aRemove// "Remove"
0x6048a  ldarg.s  4
0x6048c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x60491  ldloc.0
0x60492  ldarg.3
0x60493  ldarg.s  4
0x60495  call     void Microsoft.SharePoint.ServerStub.SPGroupCollectionServerStub::Remove_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPGroupCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6049a  ldnull
0x6049b  ret
0x6049c  ldarg.0
0x6049d  ldarg.1
0x6049e  ldarg.2
0x6049f  ldarg.3
0x604a0  ldarg.s  4
0x604a2  ldarg.s  5
0x604a4  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x604a9  ret
```
