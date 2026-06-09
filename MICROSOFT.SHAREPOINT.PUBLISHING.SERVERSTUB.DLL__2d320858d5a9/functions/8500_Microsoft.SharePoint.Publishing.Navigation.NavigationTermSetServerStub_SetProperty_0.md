# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetServerStub::SetProperty_0

- ea: `0x8500`
- end: `0x859e`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetServerStub::SetProperty_0`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x6010`
- `0x8500`

## string_xrefs

- `0x8550`: `LinkType`
- `0x8579`: `LinkType`

## pseudocode

```c

```

## disassembly

```asm
0x8500  ldarg.s  4
0x8502  brtrue.s loc_850F
0x8504  ldstr    aProxycontext// "proxyContext"
0x8509  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x850e  throw
0x850f  ldarg.1
0x8510  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet
0x8515  stloc.0
0x8516  ldloc.0
0x8517  brtrue.s loc_8524
0x8519  ldstr    aTarget// "target"
0x851e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8523  throw
0x8524  ldarg.2
0x8525  brtrue.s loc_8532
0x8527  ldstr    aPropname// "propName"
0x852c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8531  throw
0x8532  ldarg.0
0x8533  ldarg.2
0x8534  ldarg.s  4
0x8536  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x853b  starg.s  2
0x853d  ldarg.2
0x853e  dup
0x853f  stloc.1
0x8540  brfalse.s loc_8592
0x8542  ldloc.1
0x8543  ldstr    aIsnavigationte// "IsNavigationTermSet"
0x8548  call     bool [mscorlib]System.String::op_Equality(string, string)
0x854d  brtrue.s loc_855E
0x854f  ldloc.1
0x8550  ldstr    aLinktype// "LinkType"
0x8555  call     bool [mscorlib]System.String::op_Equality(string, string)
0x855a  brtrue.s loc_8578
0x855c  br.s     loc_8592
0x855e  ldarg.0
0x855f  ldstr    aIsnavigationte// "IsNavigationTermSet"
0x8564  ldarg.s  4
0x8566  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x856b  ldloc.0
0x856c  ldarg.3
0x856d  callvirt T0x2B000007
0x8572  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::set_IsNavigationTermSet(bool)
0x8577  ret
0x8578  ldarg.0
0x8579  ldstr    aLinktype// "LinkType"
0x857e  ldarg.s  4
0x8580  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8585  ldloc.0
0x8586  ldarg.3
0x8587  callvirt T0x2B000014
0x858c  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::set_LinkType(valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationLinkType)
0x8591  ret
0x8592  ldarg.0
0x8593  ldarg.1
0x8594  ldarg.2
0x8595  ldarg.3
0x8596  ldarg.s  4
0x8598  call     instance void Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::SetProperty(object target, string propName, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue node, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x859d  ret
```
