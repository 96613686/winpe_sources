# Microsoft.SharePoint.ServerStub.SPRecycleBinItemCollectionServerStub::InvokeMethod_0

- ea: `0x71aa0`
- end: `0x71bb6`
- name: `Microsoft.SharePoint.ServerStub.SPRecycleBinItemCollectionServerStub::InvokeMethod_0`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x71a40`
- `0x71a60`
- `0x71a70`
- `0x71a80`
- `0x71a90`
- `0x71aa0`

## string_xrefs

- `0x71af2`: `DeleteAll`
- `0x71b59`: `DeleteAll`
- `0x71ae5`: `MoveAllToSecondStage`
- `0x71b3d`: `MoveAllToSecondStage`
- `0x71b0c`: `DeleteAllSecondStageItems`
- `0x71b91`: `DeleteAllSecondStageItems`

## pseudocode

```c

```

## disassembly

```asm
0x71aa0  ldarg.s  4
0x71aa2  brtrue.s loc_71AAF
0x71aa4  ldstr    aProxycontext// "proxyContext"
0x71aa9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x71aae  throw
0x71aaf  ldarg.1
0x71ab0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemCollection
0x71ab5  stloc.0
0x71ab6  ldloc.0
0x71ab7  brtrue.s loc_71AC4
0x71ab9  ldstr    aTarget// "target"
0x71abe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x71ac3  throw
0x71ac4  ldarg.0
0x71ac5  ldarg.2
0x71ac6  ldarg.s  4
0x71ac8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71acd  starg.s  2
0x71acf  ldarg.2
0x71ad0  dup
0x71ad1  stloc.1
0x71ad2  brfalse  loc_71BA8
0x71ad7  ldloc.1
0x71ad8  ldstr    aGetbyid// "GetById"
0x71add  call     bool [mscorlib]System.String::op_Equality(string, string)
0x71ae2  brtrue.s loc_71B1D
0x71ae4  ldloc.1
0x71ae5  ldstr    aMovealltosecon// "MoveAllToSecondStage"
0x71aea  call     bool [mscorlib]System.String::op_Equality(string, string)
0x71aef  brtrue.s loc_71B38
0x71af1  ldloc.1
0x71af2  ldstr    aDeleteall// "DeleteAll"
0x71af7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x71afc  brtrue.s loc_71B54
0x71afe  ldloc.1
0x71aff  ldstr    aRestoreall// "RestoreAll"
0x71b04  call     bool [mscorlib]System.String::op_Equality(string, string)
0x71b09  brtrue.s loc_71B70
0x71b0b  ldloc.1
0x71b0c  ldstr    aDeleteallsecon// "DeleteAllSecondStageItems"
0x71b11  call     bool [mscorlib]System.String::op_Equality(string, string)
0x71b16  brtrue.s loc_71B8C
0x71b18  br       loc_71BA8
0x71b1d  ldarg.s  5
0x71b1f  ldc.i4.0
0x71b20  stind.i1
0x71b21  ldarg.0
0x71b22  ldstr    aGetbyid// "GetById"
0x71b27  ldarg.s  4
0x71b29  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71b2e  ldloc.0
0x71b2f  ldarg.3
0x71b30  ldarg.s  4
0x71b32  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem Microsoft.SharePoint.ServerStub.SPRecycleBinItemCollectionServerStub::GetById_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x71b37  ret
0x71b38  ldarg.s  5
0x71b3a  ldc.i4.1
0x71b3b  stind.i1
0x71b3c  ldarg.0
0x71b3d  ldstr    aMovealltosecon// "MoveAllToSecondStage"
0x71b42  ldarg.s  4
0x71b44  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71b49  ldloc.0
0x71b4a  ldarg.3
0x71b4b  ldarg.s  4
0x71b4d  call     void Microsoft.SharePoint.ServerStub.SPRecycleBinItemCollectionServerStub::MoveAllToSecondStage_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x71b52  ldnull
0x71b53  ret
0x71b54  ldarg.s  5
0x71b56  ldc.i4.1
0x71b57  stind.i1
0x71b58  ldarg.0
0x71b59  ldstr    aDeleteall// "DeleteAll"
0x71b5e  ldarg.s  4
0x71b60  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71b65  ldloc.0
0x71b66  ldarg.3
0x71b67  ldarg.s  4
0x71b69  call     void Microsoft.SharePoint.ServerStub.SPRecycleBinItemCollectionServerStub::DeleteAll_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x71b6e  ldnull
0x71b6f  ret
0x71b70  ldarg.s  5
0x71b72  ldc.i4.1
0x71b73  stind.i1
0x71b74  ldarg.0
0x71b75  ldstr    aRestoreall// "RestoreAll"
0x71b7a  ldarg.s  4
0x71b7c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71b81  ldloc.0
0x71b82  ldarg.3
0x71b83  ldarg.s  4
0x71b85  call     void Microsoft.SharePoint.ServerStub.SPRecycleBinItemCollectionServerStub::RestoreAll_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x71b8a  ldnull
0x71b8b  ret
0x71b8c  ldarg.s  5
0x71b8e  ldc.i4.1
0x71b8f  stind.i1
0x71b90  ldarg.0
0x71b91  ldstr    aDeleteallsecon// "DeleteAllSecondStageItems"
0x71b96  ldarg.s  4
0x71b98  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71b9d  ldloc.0
0x71b9e  ldarg.3
0x71b9f  ldarg.s  4
0x71ba1  call     void Microsoft.SharePoint.ServerStub.SPRecycleBinItemCollectionServerStub::DeleteAllSecondStageItems_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x71ba6  ldnull
0x71ba7  ret
0x71ba8  ldarg.0
0x71ba9  ldarg.1
0x71baa  ldarg.2
0x71bab  ldarg.3
0x71bac  ldarg.s  4
0x71bae  ldarg.s  5
0x71bb0  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x71bb5  ret
```
