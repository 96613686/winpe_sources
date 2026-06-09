# Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::InvokeMethod_0

- ea: `0x8c250`
- end: `0x8c42a`
- name: `Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::InvokeMethod_0`
- size: `474`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x8c150`
- `0x8c180`
- `0x8c1b0`
- `0x8c1d0`
- `0x8c1f0`
- `0x8c210`
- `0x8c230`
- `0x8c240`
- `0x8c250`

## string_xrefs

- `0x8c2c7`: `Remove`
- `0x8c3b1`: `Remove`
- `0x8c2df`: `RemoveAll`
- `0x8c3e9`: `RemoveAll`
- `0x8c297`: `MoveFieldTo`
- `0x8c341`: `MoveFieldTo`
- `0x8c2a3`: `MoveViewFieldTo`
- `0x8c35d`: `MoveViewFieldTo`
- `0x8c2d3`: `RemoveViewField`
- `0x8c3cd`: `RemoveViewField`
- `0x8c2eb`: `RemoveAllViewFields`
- `0x8c405`: `RemoveAllViewFields`

## pseudocode

```c

```

## disassembly

```asm
0x8c250  ldarg.s  4
0x8c252  brtrue.s loc_8C25F
0x8c254  ldstr    aProxycontext// "proxyContext"
0x8c259  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8c25e  throw
0x8c25f  ldarg.1
0x8c260  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection
0x8c265  stloc.0
0x8c266  ldloc.0
0x8c267  brtrue.s loc_8C274
0x8c269  ldstr    aTarget// "target"
0x8c26e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8c273  throw
0x8c274  ldarg.0
0x8c275  ldarg.2
0x8c276  ldarg.s  4
0x8c278  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c27d  starg.s  2
0x8c27f  ldarg.2
0x8c280  dup
0x8c281  stloc.1
0x8c282  brfalse  loc_8C41C
0x8c287  volatile.
0x8c289  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001774-1
0x8c28e  brtrue.s loc_8C2FD
0x8c290  ldc.i4.8
0x8c291  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x8c296  dup
0x8c297  ldstr    aMovefieldto// "MoveFieldTo"
0x8c29c  ldc.i4.0
0x8c29d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c2a2  dup
0x8c2a3  ldstr    aMoveviewfieldt// "MoveViewFieldTo"
0x8c2a8  ldc.i4.1
0x8c2a9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c2ae  dup
0x8c2af  ldstr    aAdd// "Add"
0x8c2b4  ldc.i4.2
0x8c2b5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c2ba  dup
0x8c2bb  ldstr    aAddviewfield// "AddViewField"
0x8c2c0  ldc.i4.3
0x8c2c1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c2c6  dup
0x8c2c7  ldstr    aRemove// "Remove"
0x8c2cc  ldc.i4.4
0x8c2cd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c2d2  dup
0x8c2d3  ldstr    aRemoveviewfiel// "RemoveViewField"
0x8c2d8  ldc.i4.5
0x8c2d9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c2de  dup
0x8c2df  ldstr    aRemoveall// "RemoveAll"
0x8c2e4  ldc.i4.6
0x8c2e5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c2ea  dup
0x8c2eb  ldstr    aRemoveallviewf// "RemoveAllViewFields"
0x8c2f0  ldc.i4.7
0x8c2f1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8c2f6  volatile.
0x8c2f8  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001774-1
0x8c2fd  volatile.
0x8c2ff  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001774-1
0x8c304  ldloc.1
0x8c305  ldloca.s 2
0x8c307  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x8c30c  brfalse  loc_8C41C
0x8c311  ldloc.2
0x8c312  switch   loc_8C33C, loc_8C358, loc_8C374, loc_8C390, loc_8C3AC, loc_8C3C8, loc_8C3E4, loc_8C400
0x8c337  br       loc_8C41C
0x8c33c  ldarg.s  5
0x8c33e  ldc.i4.1
0x8c33f  stind.i1
0x8c340  ldarg.0
0x8c341  ldstr    aMovefieldto// "MoveFieldTo"
0x8c346  ldarg.s  4
0x8c348  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c34d  ldloc.0
0x8c34e  ldarg.3
0x8c34f  ldarg.s  4
0x8c351  call     void Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::MoveFieldTo_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8c356  ldnull
0x8c357  ret
0x8c358  ldarg.s  5
0x8c35a  ldc.i4.1
0x8c35b  stind.i1
0x8c35c  ldarg.0
0x8c35d  ldstr    aMoveviewfieldt// "MoveViewFieldTo"
0x8c362  ldarg.s  4
0x8c364  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c369  ldloc.0
0x8c36a  ldarg.3
0x8c36b  ldarg.s  4
0x8c36d  call     void Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::MoveViewFieldTo_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8c372  ldnull
0x8c373  ret
0x8c374  ldarg.s  5
0x8c376  ldc.i4.1
0x8c377  stind.i1
0x8c378  ldarg.0
0x8c379  ldstr    aAdd// "Add"
0x8c37e  ldarg.s  4
0x8c380  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c385  ldloc.0
0x8c386  ldarg.3
0x8c387  ldarg.s  4
0x8c389  call     void Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::Add_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8c38e  ldnull
0x8c38f  ret
0x8c390  ldarg.s  5
0x8c392  ldc.i4.1
0x8c393  stind.i1
0x8c394  ldarg.0
0x8c395  ldstr    aAddviewfield// "AddViewField"
0x8c39a  ldarg.s  4
0x8c39c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c3a1  ldloc.0
0x8c3a2  ldarg.3
0x8c3a3  ldarg.s  4
0x8c3a5  call     void Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::AddViewField_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8c3aa  ldnull
0x8c3ab  ret
0x8c3ac  ldarg.s  5
0x8c3ae  ldc.i4.1
0x8c3af  stind.i1
0x8c3b0  ldarg.0
0x8c3b1  ldstr    aRemove// "Remove"
0x8c3b6  ldarg.s  4
0x8c3b8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c3bd  ldloc.0
0x8c3be  ldarg.3
0x8c3bf  ldarg.s  4
0x8c3c1  call     void Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::Remove_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8c3c6  ldnull
0x8c3c7  ret
0x8c3c8  ldarg.s  5
0x8c3ca  ldc.i4.1
0x8c3cb  stind.i1
0x8c3cc  ldarg.0
0x8c3cd  ldstr    aRemoveviewfiel// "RemoveViewField"
0x8c3d2  ldarg.s  4
0x8c3d4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c3d9  ldloc.0
0x8c3da  ldarg.3
0x8c3db  ldarg.s  4
0x8c3dd  call     void Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::RemoveViewField_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8c3e2  ldnull
0x8c3e3  ret
0x8c3e4  ldarg.s  5
0x8c3e6  ldc.i4.1
0x8c3e7  stind.i1
0x8c3e8  ldarg.0
0x8c3e9  ldstr    aRemoveall// "RemoveAll"
0x8c3ee  ldarg.s  4
0x8c3f0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c3f5  ldloc.0
0x8c3f6  ldarg.3
0x8c3f7  ldarg.s  4
0x8c3f9  call     void Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::RemoveAll_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8c3fe  ldnull
0x8c3ff  ret
0x8c400  ldarg.s  5
0x8c402  ldc.i4.1
0x8c403  stind.i1
0x8c404  ldarg.0
0x8c405  ldstr    aRemoveallviewf// "RemoveAllViewFields"
0x8c40a  ldarg.s  4
0x8c40c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c411  ldloc.0
0x8c412  ldarg.3
0x8c413  ldarg.s  4
0x8c415  call     void Microsoft.SharePoint.ServerStub.SPViewFieldCollectionServerStub::RemoveAllViewFields_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPViewFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8c41a  ldnull
0x8c41b  ret
0x8c41c  ldarg.0
0x8c41d  ldarg.1
0x8c41e  ldarg.2
0x8c41f  ldarg.3
0x8c420  ldarg.s  4
0x8c422  ldarg.s  5
0x8c424  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x8c429  ret
```
