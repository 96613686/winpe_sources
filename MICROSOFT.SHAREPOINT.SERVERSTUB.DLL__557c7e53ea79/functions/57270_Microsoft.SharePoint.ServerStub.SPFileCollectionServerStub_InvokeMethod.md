# Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::InvokeMethod

- ea: `0x57270`
- end: `0x57442`
- name: `Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::InvokeMethod`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x57130`
- `0x57150`
- `0x57170`
- `0x57190`
- `0x571b0`
- `0x571e0`
- `0x57200`
- `0x57230`
- `0x57270`

## string_xrefs

- `0x5730b`: `AddUsingPath`
- `0x5741e`: `AddUsingPath`
- `0x572cf`: `GetByPathOrAddStub`
- `0x57397`: `GetByPathOrAddStub`
- `0x572e7`: `AddStubUsingPath`
- `0x573cd`: `AddStubUsingPath`
- `0x572ff`: `AddTemplateFile`
- `0x57403`: `AddTemplateFile`

## pseudocode

```c

```

## disassembly

```asm
0x57270  ldarg.s  4
0x57272  brtrue.s loc_5727F
0x57274  ldstr    aProxycontext// "proxyContext"
0x57279  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5727e  throw
0x5727f  ldarg.1
0x57280  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection
0x57285  stloc.0
0x57286  ldloc.0
0x57287  brtrue.s loc_57294
0x57289  ldstr    aTarget// "target"
0x5728e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x57293  throw
0x57294  ldarg.0
0x57295  ldarg.2
0x57296  ldarg.s  4
0x57298  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5729d  starg.s  2
0x5729f  ldarg.2
0x572a0  dup
0x572a1  stloc.1
0x572a2  brfalse  loc_57434
0x572a7  volatile.
0x572a9  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000fa6-1
0x572ae  brtrue.s loc_5731D
0x572b0  ldc.i4.8
0x572b1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x572b6  dup
0x572b7  ldstr    aGetbyurl// "GetByUrl"
0x572bc  ldc.i4.0
0x572bd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x572c2  dup
0x572c3  ldstr    aGetbyurloradds// "GetByUrlOrAddStub"
0x572c8  ldc.i4.1
0x572c9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x572ce  dup
0x572cf  ldstr    aGetbypathoradd// "GetByPathOrAddStub"
0x572d4  ldc.i4.2
0x572d5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x572da  dup
0x572db  ldstr    aAddstub// "AddStub"
0x572e0  ldc.i4.3
0x572e1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x572e6  dup
0x572e7  ldstr    aAddstubusingpa// "AddStubUsingPath"
0x572ec  ldc.i4.4
0x572ed  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x572f2  dup
0x572f3  ldstr    aAdd// "Add"
0x572f8  ldc.i4.5
0x572f9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x572fe  dup
0x572ff  ldstr    aAddtemplatefil// "AddTemplateFile"
0x57304  ldc.i4.6
0x57305  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5730a  dup
0x5730b  ldstr    aAddusingpath// "AddUsingPath"
0x57310  ldc.i4.7
0x57311  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x57316  volatile.
0x57318  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000fa6-1
0x5731d  volatile.
0x5731f  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000fa6-1
0x57324  ldloc.1
0x57325  ldloca.s 2
0x57327  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x5732c  brfalse  loc_57434
0x57331  ldloc.2
0x57332  switch   loc_5735C, loc_57377, loc_57392, loc_573AD, loc_573C8, loc_573E3, loc_573FE, loc_57419
0x57357  br       loc_57434
0x5735c  ldarg.s  5
0x5735e  ldc.i4.0
0x5735f  stind.i1
0x57360  ldarg.0
0x57361  ldstr    aGetbyurl// "GetByUrl"
0x57366  ldarg.s  4
0x57368  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5736d  ldloc.0
0x5736e  ldarg.3
0x5736f  ldarg.s  4
0x57371  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::GetByUrl_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x57376  ret
0x57377  ldarg.s  5
0x57379  ldc.i4.0
0x5737a  stind.i1
0x5737b  ldarg.0
0x5737c  ldstr    aGetbyurloradds// "GetByUrlOrAddStub"
0x57381  ldarg.s  4
0x57383  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x57388  ldloc.0
0x57389  ldarg.3
0x5738a  ldarg.s  4
0x5738c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::GetByUrlOrAddStub_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x57391  ret
0x57392  ldarg.s  5
0x57394  ldc.i4.0
0x57395  stind.i1
0x57396  ldarg.0
0x57397  ldstr    aGetbypathoradd// "GetByPathOrAddStub"
0x5739c  ldarg.s  4
0x5739e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x573a3  ldloc.0
0x573a4  ldarg.3
0x573a5  ldarg.s  4
0x573a7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::GetByPathOrAddStub_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x573ac  ret
0x573ad  ldarg.s  5
0x573af  ldc.i4.0
0x573b0  stind.i1
0x573b1  ldarg.0
0x573b2  ldstr    aAddstub// "AddStub"
0x573b7  ldarg.s  4
0x573b9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x573be  ldloc.0
0x573bf  ldarg.3
0x573c0  ldarg.s  4
0x573c2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::AddStub_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x573c7  ret
0x573c8  ldarg.s  5
0x573ca  ldc.i4.0
0x573cb  stind.i1
0x573cc  ldarg.0
0x573cd  ldstr    aAddstubusingpa// "AddStubUsingPath"
0x573d2  ldarg.s  4
0x573d4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x573d9  ldloc.0
0x573da  ldarg.3
0x573db  ldarg.s  4
0x573dd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::AddStubUsingPath_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x573e2  ret
0x573e3  ldarg.s  5
0x573e5  ldc.i4.0
0x573e6  stind.i1
0x573e7  ldarg.0
0x573e8  ldstr    aAdd// "Add"
0x573ed  ldarg.s  4
0x573ef  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x573f4  ldloc.0
0x573f5  ldarg.3
0x573f6  ldarg.s  4
0x573f8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::Add_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x573fd  ret
0x573fe  ldarg.s  5
0x57400  ldc.i4.0
0x57401  stind.i1
0x57402  ldarg.0
0x57403  ldstr    aAddtemplatefil// "AddTemplateFile"
0x57408  ldarg.s  4
0x5740a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5740f  ldloc.0
0x57410  ldarg.3
0x57411  ldarg.s  4
0x57413  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::AddTemplateFile_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x57418  ret
0x57419  ldarg.s  5
0x5741b  ldc.i4.0
0x5741c  stind.i1
0x5741d  ldarg.0
0x5741e  ldstr    aAddusingpath// "AddUsingPath"
0x57423  ldarg.s  4
0x57425  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5742a  ldloc.0
0x5742b  ldarg.3
0x5742c  ldarg.s  4
0x5742e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::AddUsingPath_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x57433  ret
0x57434  ldarg.0
0x57435  ldarg.1
0x57436  ldarg.2
0x57437  ldarg.3
0x57438  ldarg.s  4
0x5743a  ldarg.s  5
0x5743c  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x57441  ret
```
