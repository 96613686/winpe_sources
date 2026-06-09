# Microsoft.SharePoint.ServerStub.SPFolderServerStub::InvokeMethod_0

- ea: `0x5f250`
- end: `0x5f459`
- name: `Microsoft.SharePoint.ServerStub.SPFolderServerStub::InvokeMethod_0`
- size: `521`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x5f160`
- `0x5f180`
- `0x5f1a0`
- `0x5f1b0`
- `0x5f1d0`
- `0x5f1f0`
- `0x5f210`
- `0x5f230`
- `0x5f240`
- `0x5f250`

## string_xrefs

- `0x5f2b0`: `Update`
- `0x5f388`: `Update`
- `0x5f2ec`: `DeleteObject`
- `0x5f414`: `DeleteObject`
- `0x5f2bc`: `MoveTo`
- `0x5f3a4`: `MoveTo`
- `0x5f2c8`: `MoveToUsingPath`
- `0x5f3c0`: `MoveToUsingPath`
- `0x5f2e0`: `AddSubFolderUsingPath`
- `0x5f3f8`: `AddSubFolderUsingPath`

## pseudocode

```c

```

## disassembly

```asm
0x5f250  ldarg.s  4
0x5f252  brtrue.s loc_5F25F
0x5f254  ldstr    aProxycontext// "proxyContext"
0x5f259  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5f25e  throw
0x5f25f  ldarg.1
0x5f260  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder
0x5f265  stloc.0
0x5f266  ldloc.0
0x5f267  brtrue.s loc_5F274
0x5f269  ldstr    aTarget// "target"
0x5f26e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5f273  throw
0x5f274  ldarg.0
0x5f275  ldarg.2
0x5f276  ldarg.s  4
0x5f278  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5f27d  starg.s  2
0x5f27f  ldarg.2
0x5f280  dup
0x5f281  stloc.1
0x5f282  brfalse  loc_5F44B
0x5f287  volatile.
0x5f289  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60010df-1
0x5f28e  brtrue.s loc_5F30A
0x5f290  ldc.i4.s 9
0x5f292  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x5f297  dup
0x5f298  ldstr    aGetlistitemcha_0// "GetListItemChanges"
0x5f29d  ldc.i4.0
0x5f29e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5f2a3  dup
0x5f2a4  ldstr    aGetchanges// "GetChanges"
0x5f2a9  ldc.i4.1
0x5f2aa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5f2af  dup
0x5f2b0  ldstr    aUpdate// "Update"
0x5f2b5  ldc.i4.2
0x5f2b6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5f2bb  dup
0x5f2bc  ldstr    aMoveto// "MoveTo"
0x5f2c1  ldc.i4.3
0x5f2c2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5f2c7  dup
0x5f2c8  ldstr    aMovetousingpat// "MoveToUsingPath"
0x5f2cd  ldc.i4.4
0x5f2ce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5f2d3  dup
0x5f2d4  ldstr    aAddsubfolder// "AddSubFolder"
0x5f2d9  ldc.i4.5
0x5f2da  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5f2df  dup
0x5f2e0  ldstr    aAddsubfolderus// "AddSubFolderUsingPath"
0x5f2e5  ldc.i4.6
0x5f2e6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5f2eb  dup
0x5f2ec  ldstr    aDeleteobject// "DeleteObject"
0x5f2f1  ldc.i4.7
0x5f2f2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5f2f7  dup
0x5f2f8  ldstr    aRecycle// "Recycle"
0x5f2fd  ldc.i4.8
0x5f2fe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5f303  volatile.
0x5f305  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60010df-1
0x5f30a  volatile.
0x5f30c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60010df-1
0x5f311  ldloc.1
0x5f312  ldloca.s 2
0x5f314  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x5f319  brfalse  loc_5F44B
0x5f31e  ldloc.2
0x5f31f  switch   loc_5F34D, loc_5F368, loc_5F383, loc_5F39F, loc_5F3BB, loc_5F3D7, loc_5F3F3, loc_5F40F, loc_5F42B
0x5f348  br       loc_5F44B
0x5f34d  ldarg.s  5
0x5f34f  ldc.i4.0
0x5f350  stind.i1
0x5f351  ldarg.0
0x5f352  ldstr    aGetlistitemcha_0// "GetListItemChanges"
0x5f357  ldarg.s  4
0x5f359  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5f35e  ldloc.0
0x5f35f  ldarg.3
0x5f360  ldarg.s  4
0x5f362  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeCollection Microsoft.SharePoint.ServerStub.SPFolderServerStub::GetListItemChanges_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5f367  ret
0x5f368  ldarg.s  5
0x5f36a  ldc.i4.0
0x5f36b  stind.i1
0x5f36c  ldarg.0
0x5f36d  ldstr    aGetchanges// "GetChanges"
0x5f372  ldarg.s  4
0x5f374  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5f379  ldloc.0
0x5f37a  ldarg.3
0x5f37b  ldarg.s  4
0x5f37d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeCollection Microsoft.SharePoint.ServerStub.SPFolderServerStub::GetChanges_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5f382  ret
0x5f383  ldarg.s  5
0x5f385  ldc.i4.1
0x5f386  stind.i1
0x5f387  ldarg.0
0x5f388  ldstr    aUpdate// "Update"
0x5f38d  ldarg.s  4
0x5f38f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5f394  ldloc.0
0x5f395  ldarg.3
0x5f396  ldarg.s  4
0x5f398  call     void Microsoft.SharePoint.ServerStub.SPFolderServerStub::Update_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5f39d  ldnull
0x5f39e  ret
0x5f39f  ldarg.s  5
0x5f3a1  ldc.i4.1
0x5f3a2  stind.i1
0x5f3a3  ldarg.0
0x5f3a4  ldstr    aMoveto// "MoveTo"
0x5f3a9  ldarg.s  4
0x5f3ab  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5f3b0  ldloc.0
0x5f3b1  ldarg.3
0x5f3b2  ldarg.s  4
0x5f3b4  call     void Microsoft.SharePoint.ServerStub.SPFolderServerStub::MoveTo_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5f3b9  ldnull
0x5f3ba  ret
0x5f3bb  ldarg.s  5
0x5f3bd  ldc.i4.1
0x5f3be  stind.i1
0x5f3bf  ldarg.0
0x5f3c0  ldstr    aMovetousingpat// "MoveToUsingPath"
0x5f3c5  ldarg.s  4
0x5f3c7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5f3cc  ldloc.0
0x5f3cd  ldarg.3
0x5f3ce  ldarg.s  4
0x5f3d0  call     void Microsoft.SharePoint.ServerStub.SPFolderServerStub::MoveToUsingPath_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5f3d5  ldnull
0x5f3d6  ret
0x5f3d7  ldarg.s  5
0x5f3d9  ldc.i4.1
0x5f3da  stind.i1
0x5f3db  ldarg.0
0x5f3dc  ldstr    aAddsubfolder// "AddSubFolder"
0x5f3e1  ldarg.s  4
0x5f3e3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5f3e8  ldloc.0
0x5f3e9  ldarg.3
0x5f3ea  ldarg.s  4
0x5f3ec  call     void Microsoft.SharePoint.ServerStub.SPFolderServerStub::AddSubFolder_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5f3f1  ldnull
0x5f3f2  ret
0x5f3f3  ldarg.s  5
0x5f3f5  ldc.i4.1
0x5f3f6  stind.i1
0x5f3f7  ldarg.0
0x5f3f8  ldstr    aAddsubfolderus// "AddSubFolderUsingPath"
0x5f3fd  ldarg.s  4
0x5f3ff  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5f404  ldloc.0
0x5f405  ldarg.3
0x5f406  ldarg.s  4
0x5f408  call     void Microsoft.SharePoint.ServerStub.SPFolderServerStub::AddSubFolderUsingPath_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5f40d  ldnull
0x5f40e  ret
0x5f40f  ldarg.s  5
0x5f411  ldc.i4.1
0x5f412  stind.i1
0x5f413  ldarg.0
0x5f414  ldstr    aDeleteobject// "DeleteObject"
0x5f419  ldarg.s  4
0x5f41b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5f420  ldloc.0
0x5f421  ldarg.3
0x5f422  ldarg.s  4
0x5f424  call     void Microsoft.SharePoint.ServerStub.SPFolderServerStub::DeleteObject_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5f429  ldnull
0x5f42a  ret
0x5f42b  ldarg.s  5
0x5f42d  ldc.i4.0
0x5f42e  stind.i1
0x5f42f  ldarg.0
0x5f430  ldstr    aRecycle// "Recycle"
0x5f435  ldarg.s  4
0x5f437  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5f43c  ldloc.0
0x5f43d  ldarg.3
0x5f43e  ldarg.s  4
0x5f440  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.ServerStub.SPFolderServerStub::Recycle_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5f445  box      [mscorlib]System.Guid
0x5f44a  ret
0x5f44b  ldarg.0
0x5f44c  ldarg.1
0x5f44d  ldarg.2
0x5f44e  ldarg.3
0x5f44f  ldarg.s  4
0x5f451  ldarg.s  5
0x5f453  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x5f458  ret
```
