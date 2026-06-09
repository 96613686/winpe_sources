# Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::InvokeMethod_0

- ea: `0x575f0`
- end: `0x577c2`
- name: `Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::InvokeMethod_0`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x574b0`
- `0x574d0`
- `0x574f0`
- `0x57510`
- `0x57530`
- `0x57560`
- `0x57580`
- `0x575b0`
- `0x575f0`

## string_xrefs

- `0x5768b`: `AddUsingPath`
- `0x5779e`: `AddUsingPath`
- `0x5764f`: `GetByPathOrAddStub`
- `0x57717`: `GetByPathOrAddStub`
- `0x57667`: `AddStubUsingPath`
- `0x5774d`: `AddStubUsingPath`
- `0x5767f`: `AddTemplateFile`
- `0x57783`: `AddTemplateFile`

## pseudocode

```c

```

## disassembly

```asm
0x575f0  ldarg.s  4
0x575f2  brtrue.s loc_575FF
0x575f4  ldstr    aProxycontext// "proxyContext"
0x575f9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x575fe  throw
0x575ff  ldarg.1
0x57600  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection
0x57605  stloc.0
0x57606  ldloc.0
0x57607  brtrue.s loc_57614
0x57609  ldstr    aTarget// "target"
0x5760e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x57613  throw
0x57614  ldarg.0
0x57615  ldarg.2
0x57616  ldarg.s  4
0x57618  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5761d  starg.s  2
0x5761f  ldarg.2
0x57620  dup
0x57621  stloc.1
0x57622  brfalse  loc_577B4
0x57627  volatile.
0x57629  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000fb2-1
0x5762e  brtrue.s loc_5769D
0x57630  ldc.i4.8
0x57631  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x57636  dup
0x57637  ldstr    aGetbyurl// "GetByUrl"
0x5763c  ldc.i4.0
0x5763d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x57642  dup
0x57643  ldstr    aGetbyurloradds// "GetByUrlOrAddStub"
0x57648  ldc.i4.1
0x57649  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5764e  dup
0x5764f  ldstr    aGetbypathoradd// "GetByPathOrAddStub"
0x57654  ldc.i4.2
0x57655  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5765a  dup
0x5765b  ldstr    aAddstub// "AddStub"
0x57660  ldc.i4.3
0x57661  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x57666  dup
0x57667  ldstr    aAddstubusingpa// "AddStubUsingPath"
0x5766c  ldc.i4.4
0x5766d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x57672  dup
0x57673  ldstr    aAdd// "Add"
0x57678  ldc.i4.5
0x57679  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5767e  dup
0x5767f  ldstr    aAddtemplatefil// "AddTemplateFile"
0x57684  ldc.i4.6
0x57685  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5768a  dup
0x5768b  ldstr    aAddusingpath// "AddUsingPath"
0x57690  ldc.i4.7
0x57691  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x57696  volatile.
0x57698  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000fb2-1
0x5769d  volatile.
0x5769f  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000fb2-1
0x576a4  ldloc.1
0x576a5  ldloca.s 2
0x576a7  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x576ac  brfalse  loc_577B4
0x576b1  ldloc.2
0x576b2  switch   loc_576DC, loc_576F7, loc_57712, loc_5772D, loc_57748, loc_57763, loc_5777E, loc_57799
0x576d7  br       loc_577B4
0x576dc  ldarg.s  5
0x576de  ldc.i4.0
0x576df  stind.i1
0x576e0  ldarg.0
0x576e1  ldstr    aGetbyurl// "GetByUrl"
0x576e6  ldarg.s  4
0x576e8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x576ed  ldloc.0
0x576ee  ldarg.3
0x576ef  ldarg.s  4
0x576f1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::GetByUrl_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x576f6  ret
0x576f7  ldarg.s  5
0x576f9  ldc.i4.0
0x576fa  stind.i1
0x576fb  ldarg.0
0x576fc  ldstr    aGetbyurloradds// "GetByUrlOrAddStub"
0x57701  ldarg.s  4
0x57703  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x57708  ldloc.0
0x57709  ldarg.3
0x5770a  ldarg.s  4
0x5770c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::GetByUrlOrAddStub_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x57711  ret
0x57712  ldarg.s  5
0x57714  ldc.i4.0
0x57715  stind.i1
0x57716  ldarg.0
0x57717  ldstr    aGetbypathoradd// "GetByPathOrAddStub"
0x5771c  ldarg.s  4
0x5771e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x57723  ldloc.0
0x57724  ldarg.3
0x57725  ldarg.s  4
0x57727  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::GetByPathOrAddStub_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5772c  ret
0x5772d  ldarg.s  5
0x5772f  ldc.i4.0
0x57730  stind.i1
0x57731  ldarg.0
0x57732  ldstr    aAddstub// "AddStub"
0x57737  ldarg.s  4
0x57739  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5773e  ldloc.0
0x5773f  ldarg.3
0x57740  ldarg.s  4
0x57742  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::AddStub_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x57747  ret
0x57748  ldarg.s  5
0x5774a  ldc.i4.0
0x5774b  stind.i1
0x5774c  ldarg.0
0x5774d  ldstr    aAddstubusingpa// "AddStubUsingPath"
0x57752  ldarg.s  4
0x57754  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x57759  ldloc.0
0x5775a  ldarg.3
0x5775b  ldarg.s  4
0x5775d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::AddStubUsingPath_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x57762  ret
0x57763  ldarg.s  5
0x57765  ldc.i4.0
0x57766  stind.i1
0x57767  ldarg.0
0x57768  ldstr    aAdd// "Add"
0x5776d  ldarg.s  4
0x5776f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x57774  ldloc.0
0x57775  ldarg.3
0x57776  ldarg.s  4
0x57778  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::Add_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5777d  ret
0x5777e  ldarg.s  5
0x57780  ldc.i4.0
0x57781  stind.i1
0x57782  ldarg.0
0x57783  ldstr    aAddtemplatefil// "AddTemplateFile"
0x57788  ldarg.s  4
0x5778a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5778f  ldloc.0
0x57790  ldarg.3
0x57791  ldarg.s  4
0x57793  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::AddTemplateFile_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x57798  ret
0x57799  ldarg.s  5
0x5779b  ldc.i4.0
0x5779c  stind.i1
0x5779d  ldarg.0
0x5779e  ldstr    aAddusingpath// "AddUsingPath"
0x577a3  ldarg.s  4
0x577a5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x577aa  ldloc.0
0x577ab  ldarg.3
0x577ac  ldarg.s  4
0x577ae  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileCollectionServerStub::AddUsingPath_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x577b3  ret
0x577b4  ldarg.0
0x577b5  ldarg.1
0x577b6  ldarg.2
0x577b7  ldarg.3
0x577b8  ldarg.s  4
0x577ba  ldarg.s  5
0x577bc  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x577c1  ret
```
