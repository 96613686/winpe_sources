# Microsoft.SharePoint.Publishing.VariationsServerStub::InvokeStaticMethod_0

- ea: `0x13580`
- end: `0x13616`
- name: `Microsoft.SharePoint.Publishing.VariationsServerStub::InvokeStaticMethod_0`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x13510`
- `0x13520`
- `0x13550`
- `0x13580`

## string_xrefs

- `0x135b8`: `UpdateListItems`
- `0x135fb`: `UpdateListItems`

## pseudocode

```c

```

## disassembly

```asm
0x13580  ldarg.3
0x13581  brtrue.s loc_1358E
0x13583  ldstr    aProxycontext// "proxyContext"
0x13588  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1358d  throw
0x1358e  ldarg.0
0x1358f  ldarg.1
0x13590  ldarg.3
0x13591  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x13596  starg.s  1
0x13598  ldarg.1
0x13599  dup
0x1359a  stloc.0
0x1359b  brfalse.s loc_1360F
0x1359d  ldloc.0
0x1359e  ldstr    aGetlabels// "GetLabels"
0x135a3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x135a8  brtrue.s loc_135C6
0x135aa  ldloc.0
0x135ab  ldstr    aGetpeerurl// "GetPeerUrl"
0x135b0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x135b5  brtrue.s loc_135DE
0x135b7  ldloc.0
0x135b8  ldstr    aUpdatelistitem// "UpdateListItems"
0x135bd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x135c2  brtrue.s loc_135F6
0x135c4  br.s     loc_1360F
0x135c6  ldarg.s  4
0x135c8  ldc.i4.0
0x135c9  stind.i1
0x135ca  ldarg.0
0x135cb  ldstr    aGetlabels// "GetLabels"
0x135d0  ldarg.3
0x135d1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x135d6  ldarg.2
0x135d7  ldarg.3
0x135d8  call     class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.VariationLabel> Microsoft.SharePoint.Publishing.VariationsServerStub::GetLabels_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x135dd  ret
0x135de  ldarg.s  4
0x135e0  ldc.i4.0
0x135e1  stind.i1
0x135e2  ldarg.0
0x135e3  ldstr    aGetpeerurl// "GetPeerUrl"
0x135e8  ldarg.3
0x135e9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x135ee  ldarg.2
0x135ef  ldarg.3
0x135f0  call     string Microsoft.SharePoint.Publishing.VariationsServerStub::GetPeerUrl_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x135f5  ret
0x135f6  ldarg.s  4
0x135f8  ldc.i4.1
0x135f9  stind.i1
0x135fa  ldarg.0
0x135fb  ldstr    aUpdatelistitem// "UpdateListItems"
0x13600  ldarg.3
0x13601  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x13606  ldarg.2
0x13607  ldarg.3
0x13608  call     void Microsoft.SharePoint.Publishing.VariationsServerStub::UpdateListItems_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x1360d  ldnull
0x1360e  ret
0x1360f  ldarg.1
0x13610  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x13615  throw
```
