# Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::InvokeMethod_0

- ea: `0x4f810`
- end: `0x4fa3d`
- name: `Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::InvokeMethod_0`
- size: `557`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4f670`
- `0x4f690`
- `0x4f6b0`
- `0x4f6d0`
- `0x4f710`
- `0x4f750`
- `0x4f790`
- `0x4f7b0`
- `0x4f7d0`
- `0x4f7f0`
- `0x4f810`

## string_xrefs

- `0x4f873`: `Create`
- `0x4f95c`: `Create`
- `0x4f897`: `AddFieldAsXml`
- `0x4f9ad`: `AddFieldAsXml`
- `0x4f8a3`: `CreateFieldAsXml`
- `0x4f9c8`: `CreateFieldAsXml`

## pseudocode

```c

```

## disassembly

```asm
0x4f810  ldarg.s  4
0x4f812  brtrue.s loc_4F81F
0x4f814  ldstr    aProxycontext// "proxyContext"
0x4f819  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4f81e  throw
0x4f81f  ldarg.1
0x4f820  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection
0x4f825  stloc.0
0x4f826  ldloc.0
0x4f827  brtrue.s loc_4F834
0x4f829  ldstr    aTarget// "target"
0x4f82e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4f833  throw
0x4f834  ldarg.0
0x4f835  ldarg.2
0x4f836  ldarg.s  4
0x4f838  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f83d  starg.s  2
0x4f83f  ldarg.2
0x4f840  dup
0x4f841  stloc.1
0x4f842  brfalse  loc_4FA2F
0x4f847  volatile.
0x4f849  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000e49-1
0x4f84e  brtrue   loc_4F8DA
0x4f853  ldc.i4.s 0xA
0x4f855  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x4f85a  dup
0x4f85b  ldstr    aAdd// "Add"
0x4f860  ldc.i4.0
0x4f861  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f866  dup
0x4f867  ldstr    aAddfield// "AddField"
0x4f86c  ldc.i4.1
0x4f86d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f872  dup
0x4f873  ldstr    aCreate// "Create"
0x4f878  ldc.i4.2
0x4f879  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f87e  dup
0x4f87f  ldstr    aAdddependentlo// "AddDependentLookup"
0x4f884  ldc.i4.3
0x4f885  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f88a  dup
0x4f88b  ldstr    aAdddependentlo_0// "AddDependentLookupField"
0x4f890  ldc.i4.4
0x4f891  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f896  dup
0x4f897  ldstr    aAddfieldasxml// "AddFieldAsXml"
0x4f89c  ldc.i4.5
0x4f89d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f8a2  dup
0x4f8a3  ldstr    aCreatefieldasx// "CreateFieldAsXml"
0x4f8a8  ldc.i4.6
0x4f8a9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f8ae  dup
0x4f8af  ldstr    aGetbyinternaln// "GetByInternalNameOrTitle"
0x4f8b4  ldc.i4.7
0x4f8b5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f8ba  dup
0x4f8bb  ldstr    aGetbytitle// "GetByTitle"
0x4f8c0  ldc.i4.8
0x4f8c1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f8c6  dup
0x4f8c7  ldstr    aGetbyid// "GetById"
0x4f8cc  ldc.i4.s 9
0x4f8ce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4f8d3  volatile.
0x4f8d5  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000e49-1
0x4f8da  volatile.
0x4f8dc  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000e49-1
0x4f8e1  ldloc.1
0x4f8e2  ldloca.s 2
0x4f8e4  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x4f8e9  brfalse  loc_4FA2F
0x4f8ee  ldloc.2
0x4f8ef  switch   loc_4F921, loc_4F93C, loc_4F957, loc_4F972, loc_4F98D, loc_4F9A8, loc_4F9C3, loc_4F9DE, loc_4F9F9, loc_4FA14
0x4f91c  br       loc_4FA2F
0x4f921  ldarg.s  5
0x4f923  ldc.i4.0
0x4f924  stind.i1
0x4f925  ldarg.0
0x4f926  ldstr    aAdd// "Add"
0x4f92b  ldarg.s  4
0x4f92d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f932  ldloc.0
0x4f933  ldarg.3
0x4f934  ldarg.s  4
0x4f936  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::Add_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f93b  ret
0x4f93c  ldarg.s  5
0x4f93e  ldc.i4.0
0x4f93f  stind.i1
0x4f940  ldarg.0
0x4f941  ldstr    aAddfield// "AddField"
0x4f946  ldarg.s  4
0x4f948  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f94d  ldloc.0
0x4f94e  ldarg.3
0x4f94f  ldarg.s  4
0x4f951  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::AddField_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f956  ret
0x4f957  ldarg.s  5
0x4f959  ldc.i4.0
0x4f95a  stind.i1
0x4f95b  ldarg.0
0x4f95c  ldstr    aCreate// "Create"
0x4f961  ldarg.s  4
0x4f963  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f968  ldloc.0
0x4f969  ldarg.3
0x4f96a  ldarg.s  4
0x4f96c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::Create_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f971  ret
0x4f972  ldarg.s  5
0x4f974  ldc.i4.0
0x4f975  stind.i1
0x4f976  ldarg.0
0x4f977  ldstr    aAdddependentlo// "AddDependentLookup"
0x4f97c  ldarg.s  4
0x4f97e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f983  ldloc.0
0x4f984  ldarg.3
0x4f985  ldarg.s  4
0x4f987  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::AddDependentLookup_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f98c  ret
0x4f98d  ldarg.s  5
0x4f98f  ldc.i4.0
0x4f990  stind.i1
0x4f991  ldarg.0
0x4f992  ldstr    aAdddependentlo_0// "AddDependentLookupField"
0x4f997  ldarg.s  4
0x4f999  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f99e  ldloc.0
0x4f99f  ldarg.3
0x4f9a0  ldarg.s  4
0x4f9a2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::AddDependentLookupField_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f9a7  ret
0x4f9a8  ldarg.s  5
0x4f9aa  ldc.i4.0
0x4f9ab  stind.i1
0x4f9ac  ldarg.0
0x4f9ad  ldstr    aAddfieldasxml// "AddFieldAsXml"
0x4f9b2  ldarg.s  4
0x4f9b4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f9b9  ldloc.0
0x4f9ba  ldarg.3
0x4f9bb  ldarg.s  4
0x4f9bd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::AddFieldAsXml_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f9c2  ret
0x4f9c3  ldarg.s  5
0x4f9c5  ldc.i4.0
0x4f9c6  stind.i1
0x4f9c7  ldarg.0
0x4f9c8  ldstr    aCreatefieldasx// "CreateFieldAsXml"
0x4f9cd  ldarg.s  4
0x4f9cf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f9d4  ldloc.0
0x4f9d5  ldarg.3
0x4f9d6  ldarg.s  4
0x4f9d8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::CreateFieldAsXml_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f9dd  ret
0x4f9de  ldarg.s  5
0x4f9e0  ldc.i4.0
0x4f9e1  stind.i1
0x4f9e2  ldarg.0
0x4f9e3  ldstr    aGetbyinternaln// "GetByInternalNameOrTitle"
0x4f9e8  ldarg.s  4
0x4f9ea  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4f9ef  ldloc.0
0x4f9f0  ldarg.3
0x4f9f1  ldarg.s  4
0x4f9f3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::GetByInternalNameOrTitle_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4f9f8  ret
0x4f9f9  ldarg.s  5
0x4f9fb  ldc.i4.0
0x4f9fc  stind.i1
0x4f9fd  ldarg.0
0x4f9fe  ldstr    aGetbytitle// "GetByTitle"
0x4fa03  ldarg.s  4
0x4fa05  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4fa0a  ldloc.0
0x4fa0b  ldarg.3
0x4fa0c  ldarg.s  4
0x4fa0e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::GetByTitle_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4fa13  ret
0x4fa14  ldarg.s  5
0x4fa16  ldc.i4.0
0x4fa17  stind.i1
0x4fa18  ldarg.0
0x4fa19  ldstr    aGetbyid// "GetById"
0x4fa1e  ldarg.s  4
0x4fa20  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4fa25  ldloc.0
0x4fa26  ldarg.3
0x4fa27  ldarg.s  4
0x4fa29  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPField Microsoft.SharePoint.ServerStub.SPFieldCollectionServerStub::GetById_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4fa2e  ret
0x4fa2f  ldarg.0
0x4fa30  ldarg.1
0x4fa31  ldarg.2
0x4fa32  ldarg.3
0x4fa33  ldarg.s  4
0x4fa35  ldarg.s  5
0x4fa37  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x4fa3c  ret
```
