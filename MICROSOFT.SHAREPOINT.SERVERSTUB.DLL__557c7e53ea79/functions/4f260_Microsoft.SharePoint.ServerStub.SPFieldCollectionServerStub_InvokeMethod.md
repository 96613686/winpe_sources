# Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::InvokeMethod

- ea: `0x4f260`
- end: `0x4f48d`
- name: `Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::InvokeMethod`
- size: `557`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4f0c0`
- `0x4f0e0`
- `0x4f100`
- `0x4f120`
- `0x4f160`
- `0x4f1a0`
- `0x4f1e0`
- `0x4f200`
- `0x4f220`
- `0x4f240`
- `0x4f260`

## string_xrefs

- `0x4f2c3`: `Create`
- `0x4f3ac`: `Create`
- `0x4f2e7`: `AddFieldAsXml`
- `0x4f3fd`: `AddFieldAsXml`
- `0x4f2f3`: `CreateFieldAsXml`
- `0x4f418`: `CreateFieldAsXml`

## pseudocode

```c

```

## disassembly

```asm
0x4f260  ldarg.s  4
0x4f262  brtrue.s loc_4F26F
0x4f264  ldstr    aProxycontext// "proxyContext"
0x4f269  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4f26e  throw
0x4f26f  ldarg.1
0x4f270  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection
0x4f275  stloc.0
0x4f276  ldloc.0
0x4f277  brtrue.s loc_4F284
0x4f279  ldstr    aTarget// "target"
0x4f27e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4f283  throw
0x4f284  ldarg.0
0x4f285  ldarg.2
0x4f286  ldarg.s  4
0x4f288  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f28d  starg.s  2
0x4f28f  ldarg.2
0x4f290  dup
0x4f291  stloc.1
0x4f292  brfalse  loc_4F47F
0x4f297  volatile.
0x4f299  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000e37-1
0x4f29e  brtrue   loc_4F32A
0x4f2a3  ldc.i4.s 0xA
0x4f2a5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x4f2aa  dup
0x4f2ab  ldstr    aAdd// "Add"
0x4f2b0  ldc.i4.0
0x4f2b1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f2b6  dup
0x4f2b7  ldstr    aAddfield// "AddField"
0x4f2bc  ldc.i4.1
0x4f2bd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f2c2  dup
0x4f2c3  ldstr    aCreate// "Create"
0x4f2c8  ldc.i4.2
0x4f2c9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f2ce  dup
0x4f2cf  ldstr    aAdddependentlo// "AddDependentLookup"
0x4f2d4  ldc.i4.3
0x4f2d5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f2da  dup
0x4f2db  ldstr    aAdddependentlo_0// "AddDependentLookupField"
0x4f2e0  ldc.i4.4
0x4f2e1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f2e6  dup
0x4f2e7  ldstr    aAddfieldasxml// "AddFieldAsXml"
0x4f2ec  ldc.i4.5
0x4f2ed  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f2f2  dup
0x4f2f3  ldstr    aCreatefieldasx// "CreateFieldAsXml"
0x4f2f8  ldc.i4.6
0x4f2f9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f2fe  dup
0x4f2ff  ldstr    aGetbyinternaln// "GetByInternalNameOrTitle"
0x4f304  ldc.i4.7
0x4f305  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f30a  dup
0x4f30b  ldstr    aGetbytitle// "GetByTitle"
0x4f310  ldc.i4.8
0x4f311  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f316  dup
0x4f317  ldstr    aGetbyid// "GetById"
0x4f31c  ldc.i4.s 9
0x4f31e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f323  volatile.
0x4f325  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000e37-1
0x4f32a  volatile.
0x4f32c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000e37-1
0x4f331  ldloc.1
0x4f332  ldloca.s 2
0x4f334  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x4f339  brfalse  loc_4F47F
0x4f33e  ldloc.2
0x4f33f  switch   loc_4F371, loc_4F38C, loc_4F3A7, loc_4F3C2, loc_4F3DD, loc_4F3F8, loc_4F413, loc_4F42E, loc_4F449, loc_4F464
0x4f36c  br       loc_4F47F
0x4f371  ldarg.s  5
0x4f373  ldc.i4.0
0x4f374  stind.i1
0x4f375  ldarg.0
0x4f376  ldstr    aAdd// "Add"
0x4f37b  ldarg.s  4
0x4f37d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f382  ldloc.0
0x4f383  ldarg.3
0x4f384  ldarg.s  4
0x4f386  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::Add_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f38b  ret
0x4f38c  ldarg.s  5
0x4f38e  ldc.i4.0
0x4f38f  stind.i1
0x4f390  ldarg.0
0x4f391  ldstr    aAddfield// "AddField"
0x4f396  ldarg.s  4
0x4f398  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f39d  ldloc.0
0x4f39e  ldarg.3
0x4f39f  ldarg.s  4
0x4f3a1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::AddField_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f3a6  ret
0x4f3a7  ldarg.s  5
0x4f3a9  ldc.i4.0
0x4f3aa  stind.i1
0x4f3ab  ldarg.0
0x4f3ac  ldstr    aCreate// "Create"
0x4f3b1  ldarg.s  4
0x4f3b3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f3b8  ldloc.0
0x4f3b9  ldarg.3
0x4f3ba  ldarg.s  4
0x4f3bc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::Create_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f3c1  ret
0x4f3c2  ldarg.s  5
0x4f3c4  ldc.i4.0
0x4f3c5  stind.i1
0x4f3c6  ldarg.0
0x4f3c7  ldstr    aAdddependentlo// "AddDependentLookup"
0x4f3cc  ldarg.s  4
0x4f3ce  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f3d3  ldloc.0
0x4f3d4  ldarg.3
0x4f3d5  ldarg.s  4
0x4f3d7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::AddDependentLookup_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f3dc  ret
0x4f3dd  ldarg.s  5
0x4f3df  ldc.i4.0
0x4f3e0  stind.i1
0x4f3e1  ldarg.0
0x4f3e2  ldstr    aAdddependentlo_0// "AddDependentLookupField"
0x4f3e7  ldarg.s  4
0x4f3e9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f3ee  ldloc.0
0x4f3ef  ldarg.3
0x4f3f0  ldarg.s  4
0x4f3f2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::AddDependentLookupField_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f3f7  ret
0x4f3f8  ldarg.s  5
0x4f3fa  ldc.i4.0
0x4f3fb  stind.i1
0x4f3fc  ldarg.0
0x4f3fd  ldstr    aAddfieldasxml// "AddFieldAsXml"
0x4f402  ldarg.s  4
0x4f404  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f409  ldloc.0
0x4f40a  ldarg.3
0x4f40b  ldarg.s  4
0x4f40d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::AddFieldAsXml_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f412  ret
0x4f413  ldarg.s  5
0x4f415  ldc.i4.0
0x4f416  stind.i1
0x4f417  ldarg.0
0x4f418  ldstr    aCreatefieldasx// "CreateFieldAsXml"
0x4f41d  ldarg.s  4
0x4f41f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f424  ldloc.0
0x4f425  ldarg.3
0x4f426  ldarg.s  4
0x4f428  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::CreateFieldAsXml_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f42d  ret
0x4f42e  ldarg.s  5
0x4f430  ldc.i4.0
0x4f431  stind.i1
0x4f432  ldarg.0
0x4f433  ldstr    aGetbyinternaln// "GetByInternalNameOrTitle"
0x4f438  ldarg.s  4
0x4f43a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f43f  ldloc.0
0x4f440  ldarg.3
0x4f441  ldarg.s  4
0x4f443  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::GetByInternalNameOrTitle_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f448  ret
0x4f449  ldarg.s  5
0x4f44b  ldc.i4.0
0x4f44c  stind.i1
0x4f44d  ldarg.0
0x4f44e  ldstr    aGetbytitle// "GetByTitle"
0x4f453  ldarg.s  4
0x4f455  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f45a  ldloc.0
0x4f45b  ldarg.3
0x4f45c  ldarg.s  4
0x4f45e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::GetByTitle_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f463  ret
0x4f464  ldarg.s  5
0x4f466  ldc.i4.0
0x4f467  stind.i1
0x4f468  ldarg.0
0x4f469  ldstr    aGetbyid// "GetById"
0x4f46e  ldarg.s  4
0x4f470  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f475  ldloc.0
0x4f476  ldarg.3
0x4f477  ldarg.s  4
0x4f479  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::GetById_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f47e  ret
0x4f47f  ldarg.0
0x4f480  ldarg.1
0x4f481  ldarg.2
0x4f482  ldarg.3
0x4f483  ldarg.s  4
0x4f485  ldarg.s  5
0x4f487  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x4f48c  ret
```
