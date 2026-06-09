# Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::InvokeMethod_0

- ea: `0x5d6e0`
- end: `0x5d85c`
- name: `Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::InvokeMethod_0`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x5d600`
- `0x5d620`
- `0x5d640`
- `0x5d660`
- `0x5d690`
- `0x5d6c0`
- `0x5d6e0`

## string_xrefs

- `0x5d763`: `Create`
- `0x5d838`: `Create`
- `0x5d74b`: `AddUsingPath`
- `0x5d802`: `AddUsingPath`
- `0x5d733`: `GetByPath`
- `0x5d7cc`: `GetByPath`
- `0x5d757`: `AddWithOverwrite`
- `0x5d81d`: `AddWithOverwrite`

## pseudocode

```c

```

## disassembly

```asm
0x5d6e0  ldarg.s  4
0x5d6e2  brtrue.s loc_5D6EF
0x5d6e4  ldstr    aProxycontext// "proxyContext"
0x5d6e9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5d6ee  throw
0x5d6ef  ldarg.1
0x5d6f0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFolderCollection
0x5d6f5  stloc.0
0x5d6f6  ldloc.0
0x5d6f7  brtrue.s loc_5D704
0x5d6f9  ldstr    aTarget// "target"
0x5d6fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5d703  throw
0x5d704  ldarg.0
0x5d705  ldarg.2
0x5d706  ldarg.s  4
0x5d708  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d70d  starg.s  2
0x5d70f  ldarg.2
0x5d710  dup
0x5d711  stloc.1
0x5d712  brfalse  loc_5D84E
0x5d717  volatile.
0x5d719  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600109e-1
0x5d71e  brtrue.s loc_5D775
0x5d720  ldc.i4.6
0x5d721  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x5d726  dup
0x5d727  ldstr    aGetbyurl// "GetByUrl"
0x5d72c  ldc.i4.0
0x5d72d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5d732  dup
0x5d733  ldstr    aGetbypath// "GetByPath"
0x5d738  ldc.i4.1
0x5d739  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5d73e  dup
0x5d73f  ldstr    aAdd// "Add"
0x5d744  ldc.i4.2
0x5d745  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5d74a  dup
0x5d74b  ldstr    aAddusingpath// "AddUsingPath"
0x5d750  ldc.i4.3
0x5d751  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5d756  dup
0x5d757  ldstr    aAddwithoverwri// "AddWithOverwrite"
0x5d75c  ldc.i4.4
0x5d75d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5d762  dup
0x5d763  ldstr    aCreate// "Create"
0x5d768  ldc.i4.5
0x5d769  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5d76e  volatile.
0x5d770  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600109e-1
0x5d775  volatile.
0x5d777  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600109e-1
0x5d77c  ldloc.1
0x5d77d  ldloca.s 2
0x5d77f  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x5d784  brfalse  loc_5D84E
0x5d789  ldloc.2
0x5d78a  switch   loc_5D7AC, loc_5D7C7, loc_5D7E2, loc_5D7FD, loc_5D818, loc_5D833
0x5d7a7  br       loc_5D84E
0x5d7ac  ldarg.s  5
0x5d7ae  ldc.i4.0
0x5d7af  stind.i1
0x5d7b0  ldarg.0
0x5d7b1  ldstr    aGetbyurl// "GetByUrl"
0x5d7b6  ldarg.s  4
0x5d7b8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d7bd  ldloc.0
0x5d7be  ldarg.3
0x5d7bf  ldarg.s  4
0x5d7c1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::GetByUrl_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolderCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5d7c6  ret
0x5d7c7  ldarg.s  5
0x5d7c9  ldc.i4.0
0x5d7ca  stind.i1
0x5d7cb  ldarg.0
0x5d7cc  ldstr    aGetbypath// "GetByPath"
0x5d7d1  ldarg.s  4
0x5d7d3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d7d8  ldloc.0
0x5d7d9  ldarg.3
0x5d7da  ldarg.s  4
0x5d7dc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::GetByPath_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolderCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5d7e1  ret
0x5d7e2  ldarg.s  5
0x5d7e4  ldc.i4.0
0x5d7e5  stind.i1
0x5d7e6  ldarg.0
0x5d7e7  ldstr    aAdd// "Add"
0x5d7ec  ldarg.s  4
0x5d7ee  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d7f3  ldloc.0
0x5d7f4  ldarg.3
0x5d7f5  ldarg.s  4
0x5d7f7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::Add_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolderCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5d7fc  ret
0x5d7fd  ldarg.s  5
0x5d7ff  ldc.i4.0
0x5d800  stind.i1
0x5d801  ldarg.0
0x5d802  ldstr    aAddusingpath// "AddUsingPath"
0x5d807  ldarg.s  4
0x5d809  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d80e  ldloc.0
0x5d80f  ldarg.3
0x5d810  ldarg.s  4
0x5d812  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::AddUsingPath_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolderCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5d817  ret
0x5d818  ldarg.s  5
0x5d81a  ldc.i4.0
0x5d81b  stind.i1
0x5d81c  ldarg.0
0x5d81d  ldstr    aAddwithoverwri// "AddWithOverwrite"
0x5d822  ldarg.s  4
0x5d824  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d829  ldloc.0
0x5d82a  ldarg.3
0x5d82b  ldarg.s  4
0x5d82d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::AddWithOverwrite_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolderCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5d832  ret
0x5d833  ldarg.s  5
0x5d835  ldc.i4.0
0x5d836  stind.i1
0x5d837  ldarg.0
0x5d838  ldstr    aCreate// "Create"
0x5d83d  ldarg.s  4
0x5d83f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d844  ldloc.0
0x5d845  ldarg.3
0x5d846  ldarg.s  4
0x5d848  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::Create_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolderCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5d84d  ret
0x5d84e  ldarg.0
0x5d84f  ldarg.1
0x5d850  ldarg.2
0x5d851  ldarg.3
0x5d852  ldarg.s  4
0x5d854  ldarg.s  5
0x5d856  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x5d85b  ret
```
