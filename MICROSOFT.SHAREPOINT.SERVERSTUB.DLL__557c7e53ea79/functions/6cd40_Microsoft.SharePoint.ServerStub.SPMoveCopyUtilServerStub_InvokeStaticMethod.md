# Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::InvokeStaticMethod

- ea: `0x6cd40`
- end: `0x6cee4`
- name: `Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::InvokeStaticMethod`
- size: `420`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x6cb00`
- `0x6cb50`
- `0x6cba0`
- `0x6cbf0`
- `0x6cc40`
- `0x6cc80`
- `0x6ccc0`
- `0x6cd00`
- `0x6cd40`

## string_xrefs

- `0x6cd70`: `MoveFile`
- `0x6ce1a`: `MoveFile`
- `0x6cd7c`: `MoveFileByPath`
- `0x6ce33`: `MoveFileByPath`
- `0x6cd88`: `CopyFile`
- `0x6ce4c`: `CopyFile`
- `0x6cd94`: `CopyFileByPath`
- `0x6ce65`: `CopyFileByPath`
- `0x6cda0`: `MoveFolder`
- `0x6ce7e`: `MoveFolder`
- `0x6cdac`: `MoveFolderByPath`
- `0x6ce97`: `MoveFolderByPath`
- `0x6cdb8`: `CopyFolder`
- `0x6ceb0`: `CopyFolder`
- `0x6cdc4`: `CopyFolderByPath`
- `0x6cec9`: `CopyFolderByPath`

## pseudocode

```c

```

## disassembly

```asm
0x6cd40  ldarg.3
0x6cd41  brtrue.s loc_6CD4E
0x6cd43  ldstr    aProxycontext// "proxyContext"
0x6cd48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6cd4d  throw
0x6cd4e  ldarg.0
0x6cd4f  ldarg.1
0x6cd50  ldarg.3
0x6cd51  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6cd56  starg.s  1
0x6cd58  ldarg.1
0x6cd59  dup
0x6cd5a  stloc.0
0x6cd5b  brfalse  loc_6CEDD
0x6cd60  volatile.
0x6cd62  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001324-1
0x6cd67  brtrue.s loc_6CDD6
0x6cd69  ldc.i4.8
0x6cd6a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x6cd6f  dup
0x6cd70  ldstr    aMovefile// "MoveFile"
0x6cd75  ldc.i4.0
0x6cd76  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6cd7b  dup
0x6cd7c  ldstr    aMovefilebypath// "MoveFileByPath"
0x6cd81  ldc.i4.1
0x6cd82  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6cd87  dup
0x6cd88  ldstr    aCopyfile// "CopyFile"
0x6cd8d  ldc.i4.2
0x6cd8e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6cd93  dup
0x6cd94  ldstr    aCopyfilebypath// "CopyFileByPath"
0x6cd99  ldc.i4.3
0x6cd9a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6cd9f  dup
0x6cda0  ldstr    aMovefolder// "MoveFolder"
0x6cda5  ldc.i4.4
0x6cda6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6cdab  dup
0x6cdac  ldstr    aMovefolderbypa// "MoveFolderByPath"
0x6cdb1  ldc.i4.5
0x6cdb2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6cdb7  dup
0x6cdb8  ldstr    aCopyfolder// "CopyFolder"
0x6cdbd  ldc.i4.6
0x6cdbe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6cdc3  dup
0x6cdc4  ldstr    aCopyfolderbypa// "CopyFolderByPath"
0x6cdc9  ldc.i4.7
0x6cdca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x6cdcf  volatile.
0x6cdd1  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001324-1
0x6cdd6  volatile.
0x6cdd8  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001324-1
0x6cddd  ldloc.0
0x6cdde  ldloca.s 1
0x6cde0  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x6cde5  brfalse  loc_6CEDD
0x6cdea  ldloc.1
0x6cdeb  switch   loc_6CE15, loc_6CE2E, loc_6CE47, loc_6CE60, loc_6CE79, loc_6CE92, loc_6CEAB, loc_6CEC4
0x6ce10  br       loc_6CEDD
0x6ce15  ldarg.s  4
0x6ce17  ldc.i4.1
0x6ce18  stind.i1
0x6ce19  ldarg.0
0x6ce1a  ldstr    aMovefile// "MoveFile"
0x6ce1f  ldarg.3
0x6ce20  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6ce25  ldarg.2
0x6ce26  ldarg.3
0x6ce27  call     void Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::MoveFile_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6ce2c  ldnull
0x6ce2d  ret
0x6ce2e  ldarg.s  4
0x6ce30  ldc.i4.1
0x6ce31  stind.i1
0x6ce32  ldarg.0
0x6ce33  ldstr    aMovefilebypath// "MoveFileByPath"
0x6ce38  ldarg.3
0x6ce39  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6ce3e  ldarg.2
0x6ce3f  ldarg.3
0x6ce40  call     void Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::MoveFileByPath_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6ce45  ldnull
0x6ce46  ret
0x6ce47  ldarg.s  4
0x6ce49  ldc.i4.1
0x6ce4a  stind.i1
0x6ce4b  ldarg.0
0x6ce4c  ldstr    aCopyfile// "CopyFile"
0x6ce51  ldarg.3
0x6ce52  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6ce57  ldarg.2
0x6ce58  ldarg.3
0x6ce59  call     void Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::CopyFile_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6ce5e  ldnull
0x6ce5f  ret
0x6ce60  ldarg.s  4
0x6ce62  ldc.i4.1
0x6ce63  stind.i1
0x6ce64  ldarg.0
0x6ce65  ldstr    aCopyfilebypath// "CopyFileByPath"
0x6ce6a  ldarg.3
0x6ce6b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6ce70  ldarg.2
0x6ce71  ldarg.3
0x6ce72  call     void Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::CopyFileByPath_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6ce77  ldnull
0x6ce78  ret
0x6ce79  ldarg.s  4
0x6ce7b  ldc.i4.1
0x6ce7c  stind.i1
0x6ce7d  ldarg.0
0x6ce7e  ldstr    aMovefolder// "MoveFolder"
0x6ce83  ldarg.3
0x6ce84  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6ce89  ldarg.2
0x6ce8a  ldarg.3
0x6ce8b  call     void Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::MoveFolder_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6ce90  ldnull
0x6ce91  ret
0x6ce92  ldarg.s  4
0x6ce94  ldc.i4.1
0x6ce95  stind.i1
0x6ce96  ldarg.0
0x6ce97  ldstr    aMovefolderbypa// "MoveFolderByPath"
0x6ce9c  ldarg.3
0x6ce9d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6cea2  ldarg.2
0x6cea3  ldarg.3
0x6cea4  call     void Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::MoveFolderByPath_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6cea9  ldnull
0x6ceaa  ret
0x6ceab  ldarg.s  4
0x6cead  ldc.i4.1
0x6ceae  stind.i1
0x6ceaf  ldarg.0
0x6ceb0  ldstr    aCopyfolder// "CopyFolder"
0x6ceb5  ldarg.3
0x6ceb6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6cebb  ldarg.2
0x6cebc  ldarg.3
0x6cebd  call     void Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::CopyFolder_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6cec2  ldnull
0x6cec3  ret
0x6cec4  ldarg.s  4
0x6cec6  ldc.i4.1
0x6cec7  stind.i1
0x6cec8  ldarg.0
0x6cec9  ldstr    aCopyfolderbypa// "CopyFolderByPath"
0x6cece  ldarg.3
0x6cecf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6ced4  ldarg.2
0x6ced5  ldarg.3
0x6ced6  call     void Microsoft.SharePoint.ServerStub.SPMoveCopyUtilServerStub::CopyFolderByPath_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6cedb  ldnull
0x6cedc  ret
0x6cedd  ldarg.1
0x6cede  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x6cee3  throw
```
