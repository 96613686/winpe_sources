# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::InvokeMethod

- ea: `0x5690`
- end: `0x574c`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::InvokeMethod`
- size: `188`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x62d0`
- `0x7a70`

## callees

- `0x5620`
- `0x5640`
- `0x5650`
- `0x5690`

## string_xrefs

- `0x56df`: `CreateTerm`
- `0x5728`: `CreateTerm`

## pseudocode

```c

```

## disassembly

```asm
0x5690  ldarg.s  4
0x5692  brtrue.s loc_569F
0x5694  ldstr    aProxycontext// "proxyContext"
0x5699  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x569e  throw
0x569f  ldarg.1
0x56a0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem
0x56a5  stloc.0
0x56a6  ldloc.0
0x56a7  brtrue.s loc_56B4
0x56a9  ldstr    aTarget// "target"
0x56ae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x56b3  throw
0x56b4  ldarg.0
0x56b5  ldarg.2
0x56b6  ldarg.s  4
0x56b8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x56bd  starg.s  2
0x56bf  ldarg.2
0x56c0  dup
0x56c1  stloc.1
0x56c2  brfalse.s loc_573E
0x56c4  ldloc.1
0x56c5  ldstr    aGetresolveddis// "GetResolvedDisplayUrl"
0x56ca  call     bool [mscorlib]System.String::op_Equality(string, string)
0x56cf  brtrue.s loc_56ED
0x56d1  ldloc.1
0x56d2  ldstr    aGettaxonomyter// "GetTaxonomyTermStore"
0x56d7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x56dc  brtrue.s loc_5708
0x56de  ldloc.1
0x56df  ldstr    aCreateterm// "CreateTerm"
0x56e4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x56e9  brtrue.s loc_5723
0x56eb  br.s     loc_573E
0x56ed  ldarg.s  5
0x56ef  ldc.i4.0
0x56f0  stind.i1
0x56f1  ldarg.0
0x56f2  ldstr    aGetresolveddis// "GetResolvedDisplayUrl"
0x56f7  ldarg.s  4
0x56f9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x56fe  ldloc.0
0x56ff  ldarg.3
0x5700  ldarg.s  4
0x5702  call     string Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::GetResolvedDisplayUrl_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5707  ret
0x5708  ldarg.s  5
0x570a  ldc.i4.0
0x570b  stind.i1
0x570c  ldarg.0
0x570d  ldstr    aGettaxonomyter// "GetTaxonomyTermStore"
0x5712  ldarg.s  4
0x5714  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5719  ldloc.0
0x571a  ldarg.3
0x571b  ldarg.s  4
0x571d  call     class [Microsoft.SharePoint.Taxonomy]Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::GetTaxonomyTermStore_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5722  ret
0x5723  ldarg.s  5
0x5725  ldc.i4.0
0x5726  stind.i1
0x5727  ldarg.0
0x5728  ldstr    aCreateterm// "CreateTerm"
0x572d  ldarg.s  4
0x572f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5734  ldloc.0
0x5735  ldarg.3
0x5736  ldarg.s  4
0x5738  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTerm Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::CreateTerm_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x573d  ret
0x573e  ldarg.0
0x573f  ldarg.1
0x5740  ldarg.2
0x5741  ldarg.3
0x5742  ldarg.s  4
0x5744  ldarg.s  5
0x5746  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x574b  ret
```
