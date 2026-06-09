# Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::InvokeStaticMethod_0

- ea: `0x6d190`
- end: `0x6d334`
- name: `Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::InvokeStaticMethod_0`
- size: `420`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x6cf50`
- `0x6cfa0`
- `0x6cff0`
- `0x6d040`
- `0x6d090`
- `0x6d0d0`
- `0x6d110`
- `0x6d150`
- `0x6d190`

## string_xrefs

- `0x6d1c0`: `MoveFile`
- `0x6d26a`: `MoveFile`
- `0x6d1cc`: `MoveFileByPath`
- `0x6d283`: `MoveFileByPath`
- `0x6d1d8`: `CopyFile`
- `0x6d29c`: `CopyFile`
- `0x6d1e4`: `CopyFileByPath`
- `0x6d2b5`: `CopyFileByPath`
- `0x6d1f0`: `MoveFolder`
- `0x6d2ce`: `MoveFolder`
- `0x6d1fc`: `MoveFolderByPath`
- `0x6d2e7`: `MoveFolderByPath`
- `0x6d208`: `CopyFolder`
- `0x6d300`: `CopyFolder`
- `0x6d214`: `CopyFolderByPath`
- `0x6d319`: `CopyFolderByPath`

## pseudocode

```c

```

## disassembly

```asm
0x6d190  ldarg.3
0x6d191  brtrue.s loc_6D19E
0x6d193  ldstr    aProxycontext// "proxyContext"
0x6d198  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6d19d  throw
0x6d19e  ldarg.0
0x6d19f  ldarg.1
0x6d1a0  ldarg.3
0x6d1a1  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d1a6  starg.s  1
0x6d1a8  ldarg.1
0x6d1a9  dup
0x6d1aa  stloc.0
0x6d1ab  brfalse  loc_6D32D
0x6d1b0  volatile.
0x6d1b2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001330-1
0x6d1b7  brtrue.s loc_6D226
0x6d1b9  ldc.i4.8
0x6d1ba  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x6d1bf  dup
0x6d1c0  ldstr    aMovefile// "MoveFile"
0x6d1c5  ldc.i4.0
0x6d1c6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d1cb  dup
0x6d1cc  ldstr    aMovefilebypath// "MoveFileByPath"
0x6d1d1  ldc.i4.1
0x6d1d2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d1d7  dup
0x6d1d8  ldstr    aCopyfile// "CopyFile"
0x6d1dd  ldc.i4.2
0x6d1de  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d1e3  dup
0x6d1e4  ldstr    aCopyfilebypath// "CopyFileByPath"
0x6d1e9  ldc.i4.3
0x6d1ea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d1ef  dup
0x6d1f0  ldstr    aMovefolder// "MoveFolder"
0x6d1f5  ldc.i4.4
0x6d1f6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d1fb  dup
0x6d1fc  ldstr    aMovefolderbypa// "MoveFolderByPath"
0x6d201  ldc.i4.5
0x6d202  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d207  dup
0x6d208  ldstr    aCopyfolder// "CopyFolder"
0x6d20d  ldc.i4.6
0x6d20e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d213  dup
0x6d214  ldstr    aCopyfolderbypa// "CopyFolderByPath"
0x6d219  ldc.i4.7
0x6d21a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6d21f  volatile.
0x6d221  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001330-1
0x6d226  volatile.
0x6d228  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001330-1
0x6d22d  ldloc.0
0x6d22e  ldloca.s 1
0x6d230  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x6d235  brfalse  loc_6D32D
0x6d23a  ldloc.1
0x6d23b  switch   loc_6D265, loc_6D27E, loc_6D297, loc_6D2B0, loc_6D2C9, loc_6D2E2, loc_6D2FB, loc_6D314
0x6d260  br       loc_6D32D
0x6d265  ldarg.s  4
0x6d267  ldc.i4.1
0x6d268  stind.i1
0x6d269  ldarg.0
0x6d26a  ldstr    aMovefile// "MoveFile"
0x6d26f  ldarg.3
0x6d270  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d275  ldarg.2
0x6d276  ldarg.3
0x6d277  call     void Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::MoveFile_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6d27c  ldnull
0x6d27d  ret
0x6d27e  ldarg.s  4
0x6d280  ldc.i4.1
0x6d281  stind.i1
0x6d282  ldarg.0
0x6d283  ldstr    aMovefilebypath// "MoveFileByPath"
0x6d288  ldarg.3
0x6d289  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d28e  ldarg.2
0x6d28f  ldarg.3
0x6d290  call     void Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::MoveFileByPath_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6d295  ldnull
0x6d296  ret
0x6d297  ldarg.s  4
0x6d299  ldc.i4.1
0x6d29a  stind.i1
0x6d29b  ldarg.0
0x6d29c  ldstr    aCopyfile// "CopyFile"
0x6d2a1  ldarg.3
0x6d2a2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d2a7  ldarg.2
0x6d2a8  ldarg.3
0x6d2a9  call     void Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::CopyFile_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6d2ae  ldnull
0x6d2af  ret
0x6d2b0  ldarg.s  4
0x6d2b2  ldc.i4.1
0x6d2b3  stind.i1
0x6d2b4  ldarg.0
0x6d2b5  ldstr    aCopyfilebypath// "CopyFileByPath"
0x6d2ba  ldarg.3
0x6d2bb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d2c0  ldarg.2
0x6d2c1  ldarg.3
0x6d2c2  call     void Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::CopyFileByPath_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6d2c7  ldnull
0x6d2c8  ret
0x6d2c9  ldarg.s  4
0x6d2cb  ldc.i4.1
0x6d2cc  stind.i1
0x6d2cd  ldarg.0
0x6d2ce  ldstr    aMovefolder// "MoveFolder"
0x6d2d3  ldarg.3
0x6d2d4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d2d9  ldarg.2
0x6d2da  ldarg.3
0x6d2db  call     void Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::MoveFolder_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6d2e0  ldnull
0x6d2e1  ret
0x6d2e2  ldarg.s  4
0x6d2e4  ldc.i4.1
0x6d2e5  stind.i1
0x6d2e6  ldarg.0
0x6d2e7  ldstr    aMovefolderbypa// "MoveFolderByPath"
0x6d2ec  ldarg.3
0x6d2ed  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d2f2  ldarg.2
0x6d2f3  ldarg.3
0x6d2f4  call     void Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::MoveFolderByPath_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6d2f9  ldnull
0x6d2fa  ret
0x6d2fb  ldarg.s  4
0x6d2fd  ldc.i4.1
0x6d2fe  stind.i1
0x6d2ff  ldarg.0
0x6d300  ldstr    aCopyfolder// "CopyFolder"
0x6d305  ldarg.3
0x6d306  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d30b  ldarg.2
0x6d30c  ldarg.3
0x6d30d  call     void Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::CopyFolder_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6d312  ldnull
0x6d313  ret
0x6d314  ldarg.s  4
0x6d316  ldc.i4.1
0x6d317  stind.i1
0x6d318  ldarg.0
0x6d319  ldstr    aCopyfolderbypa// "CopyFolderByPath"
0x6d31e  ldarg.3
0x6d31f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6d324  ldarg.2
0x6d325  ldarg.3
0x6d326  call     void Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::CopyFolderByPath_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6d32b  ldnull
0x6d32c  ret
0x6d32d  ldarg.1
0x6d32e  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x6d333  throw
```
