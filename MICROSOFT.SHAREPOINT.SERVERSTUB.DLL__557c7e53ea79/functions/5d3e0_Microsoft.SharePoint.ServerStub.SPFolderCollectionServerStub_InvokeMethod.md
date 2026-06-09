# Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::InvokeMethod

- ea: `0x5d3e0`
- end: `0x5d55c`
- name: `Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::InvokeMethod`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x5d300`
- `0x5d320`
- `0x5d340`
- `0x5d360`
- `0x5d390`
- `0x5d3c0`
- `0x5d3e0`

## string_xrefs

- `0x5d463`: `Create`
- `0x5d538`: `Create`
- `0x5d44b`: `AddUsingPath`
- `0x5d502`: `AddUsingPath`
- `0x5d433`: `GetByPath`
- `0x5d4cc`: `GetByPath`
- `0x5d457`: `AddWithOverwrite`
- `0x5d51d`: `AddWithOverwrite`

## pseudocode

```c

```

## disassembly

```asm
0x5d3e0  ldarg.s  4
0x5d3e2  brtrue.s loc_5D3EF
0x5d3e4  ldstr    aProxycontext// "proxyContext"
0x5d3e9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5d3ee  throw
0x5d3ef  ldarg.1
0x5d3f0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFolderCollection
0x5d3f5  stloc.0
0x5d3f6  ldloc.0
0x5d3f7  brtrue.s loc_5D404
0x5d3f9  ldstr    aTarget// "target"
0x5d3fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5d403  throw
0x5d404  ldarg.0
0x5d405  ldarg.2
0x5d406  ldarg.s  4
0x5d408  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d40d  starg.s  2
0x5d40f  ldarg.2
0x5d410  dup
0x5d411  stloc.1
0x5d412  brfalse  loc_5D54E
0x5d417  volatile.
0x5d419  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001092-1
0x5d41e  brtrue.s loc_5D475
0x5d420  ldc.i4.6
0x5d421  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x5d426  dup
0x5d427  ldstr    aGetbyurl// "GetByUrl"
0x5d42c  ldc.i4.0
0x5d42d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5d432  dup
0x5d433  ldstr    aGetbypath// "GetByPath"
0x5d438  ldc.i4.1
0x5d439  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5d43e  dup
0x5d43f  ldstr    aAdd// "Add"
0x5d444  ldc.i4.2
0x5d445  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5d44a  dup
0x5d44b  ldstr    aAddusingpath// "AddUsingPath"
0x5d450  ldc.i4.3
0x5d451  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5d456  dup
0x5d457  ldstr    aAddwithoverwri// "AddWithOverwrite"
0x5d45c  ldc.i4.4
0x5d45d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5d462  dup
0x5d463  ldstr    aCreate// "Create"
0x5d468  ldc.i4.5
0x5d469  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5d46e  volatile.
0x5d470  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001092-1
0x5d475  volatile.
0x5d477  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001092-1
0x5d47c  ldloc.1
0x5d47d  ldloca.s 2
0x5d47f  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x5d484  brfalse  loc_5D54E
0x5d489  ldloc.2
0x5d48a  switch   loc_5D4AC, loc_5D4C7, loc_5D4E2, loc_5D4FD, loc_5D518, loc_5D533
0x5d4a7  br       loc_5D54E
0x5d4ac  ldarg.s  5
0x5d4ae  ldc.i4.0
0x5d4af  stind.i1
0x5d4b0  ldarg.0
0x5d4b1  ldstr    aGetbyurl// "GetByUrl"
0x5d4b6  ldarg.s  4
0x5d4b8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d4bd  ldloc.0
0x5d4be  ldarg.3
0x5d4bf  ldarg.s  4
0x5d4c1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::GetByUrl_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolderCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5d4c6  ret
0x5d4c7  ldarg.s  5
0x5d4c9  ldc.i4.0
0x5d4ca  stind.i1
0x5d4cb  ldarg.0
0x5d4cc  ldstr    aGetbypath// "GetByPath"
0x5d4d1  ldarg.s  4
0x5d4d3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d4d8  ldloc.0
0x5d4d9  ldarg.3
0x5d4da  ldarg.s  4
0x5d4dc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::GetByPath_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolderCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5d4e1  ret
0x5d4e2  ldarg.s  5
0x5d4e4  ldc.i4.0
0x5d4e5  stind.i1
0x5d4e6  ldarg.0
0x5d4e7  ldstr    aAdd// "Add"
0x5d4ec  ldarg.s  4
0x5d4ee  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d4f3  ldloc.0
0x5d4f4  ldarg.3
0x5d4f5  ldarg.s  4
0x5d4f7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::Add_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolderCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5d4fc  ret
0x5d4fd  ldarg.s  5
0x5d4ff  ldc.i4.0
0x5d500  stind.i1
0x5d501  ldarg.0
0x5d502  ldstr    aAddusingpath// "AddUsingPath"
0x5d507  ldarg.s  4
0x5d509  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d50e  ldloc.0
0x5d50f  ldarg.3
0x5d510  ldarg.s  4
0x5d512  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::AddUsingPath_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolderCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5d517  ret
0x5d518  ldarg.s  5
0x5d51a  ldc.i4.0
0x5d51b  stind.i1
0x5d51c  ldarg.0
0x5d51d  ldstr    aAddwithoverwri// "AddWithOverwrite"
0x5d522  ldarg.s  4
0x5d524  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d529  ldloc.0
0x5d52a  ldarg.3
0x5d52b  ldarg.s  4
0x5d52d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::AddWithOverwrite_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolderCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5d532  ret
0x5d533  ldarg.s  5
0x5d535  ldc.i4.0
0x5d536  stind.i1
0x5d537  ldarg.0
0x5d538  ldstr    aCreate// "Create"
0x5d53d  ldarg.s  4
0x5d53f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5d544  ldloc.0
0x5d545  ldarg.3
0x5d546  ldarg.s  4
0x5d548  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder Microsoft.SharePoint.ServerStub.SPFolderCollectionServerStub::Create_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolderCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5d54d  ret
0x5d54e  ldarg.0
0x5d54f  ldarg.1
0x5d550  ldarg.2
0x5d551  ldarg.3
0x5d552  ldarg.s  4
0x5d554  ldarg.s  5
0x5d556  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x5d55b  ret
```
