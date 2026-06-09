# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::SetProperty

- ea: `0x5920`
- end: `0x5997`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::SetProperty`
- size: `119`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x67c0`
- `0x7d10`

## callees

- `0x5920`

## string_xrefs

- `0x5963`: `LinkType`
- `0x5970`: `LinkType`

## pseudocode

```c

```

## disassembly

```asm
0x5920  ldarg.s  4
0x5922  brtrue.s loc_592F
0x5924  ldstr    aProxycontext// "proxyContext"
0x5929  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x592e  throw
0x592f  ldarg.1
0x5930  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem
0x5935  stloc.0
0x5936  ldloc.0
0x5937  brtrue.s loc_5944
0x5939  ldstr    aTarget// "target"
0x593e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5943  throw
0x5944  ldarg.2
0x5945  brtrue.s loc_5952
0x5947  ldstr    aPropname// "propName"
0x594c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5951  throw
0x5952  ldarg.0
0x5953  ldarg.2
0x5954  ldarg.s  4
0x5956  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x595b  starg.s  2
0x595d  ldarg.2
0x595e  dup
0x595f  stloc.1
0x5960  brfalse.s loc_598B
0x5962  ldloc.1
0x5963  ldstr    aLinktype// "LinkType"
0x5968  call     bool [mscorlib]System.String::op_Equality(string, string)
0x596d  brfalse.s loc_598B
0x596f  ldarg.0
0x5970  ldstr    aLinktype// "LinkType"
0x5975  ldarg.s  4
0x5977  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x597c  ldloc.0
0x597d  ldarg.3
0x597e  ldarg.s  4
0x5980  call     T0x2B000012
0x5985  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::set_LinkType(valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationLinkType)
0x598a  ret
0x598b  ldarg.0
0x598c  ldarg.1
0x598d  ldarg.2
0x598e  ldarg.3
0x598f  ldarg.s  4
0x5991  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5996  ret
```
