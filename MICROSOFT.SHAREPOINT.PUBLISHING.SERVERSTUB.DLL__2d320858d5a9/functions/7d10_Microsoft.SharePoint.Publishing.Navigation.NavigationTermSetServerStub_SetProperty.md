# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetServerStub::SetProperty

- ea: `0x7d10`
- end: `0x7db2`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetServerStub::SetProperty`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5920`
- `0x7d10`

## string_xrefs

- `0x7d60`: `LinkType`
- `0x7d8b`: `LinkType`

## pseudocode

```c

```

## disassembly

```asm
0x7d10  ldarg.s  4
0x7d12  brtrue.s loc_7D1F
0x7d14  ldstr    aProxycontext// "proxyContext"
0x7d19  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7d1e  throw
0x7d1f  ldarg.1
0x7d20  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet
0x7d25  stloc.0
0x7d26  ldloc.0
0x7d27  brtrue.s loc_7D34
0x7d29  ldstr    aTarget// "target"
0x7d2e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7d33  throw
0x7d34  ldarg.2
0x7d35  brtrue.s loc_7D42
0x7d37  ldstr    aPropname// "propName"
0x7d3c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7d41  throw
0x7d42  ldarg.0
0x7d43  ldarg.2
0x7d44  ldarg.s  4
0x7d46  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7d4b  starg.s  2
0x7d4d  ldarg.2
0x7d4e  dup
0x7d4f  stloc.1
0x7d50  brfalse.s loc_7DA6
0x7d52  ldloc.1
0x7d53  ldstr    aIsnavigationte// "IsNavigationTermSet"
0x7d58  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7d5d  brtrue.s loc_7D6E
0x7d5f  ldloc.1
0x7d60  ldstr    aLinktype// "LinkType"
0x7d65  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7d6a  brtrue.s loc_7D8A
0x7d6c  br.s     loc_7DA6
0x7d6e  ldarg.0
0x7d6f  ldstr    aIsnavigationte// "IsNavigationTermSet"
0x7d74  ldarg.s  4
0x7d76  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7d7b  ldloc.0
0x7d7c  ldarg.3
0x7d7d  ldarg.s  4
0x7d7f  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7d84  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSet::set_IsNavigationTermSet(bool)
0x7d89  ret
0x7d8a  ldarg.0
0x7d8b  ldstr    aLinktype// "LinkType"
0x7d90  ldarg.s  4
0x7d92  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7d97  ldloc.0
0x7d98  ldarg.3
0x7d99  ldarg.s  4
0x7d9b  call     T0x2B000012
0x7da0  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::set_LinkType(valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationLinkType)
0x7da5  ret
0x7da6  ldarg.0
0x7da7  ldarg.1
0x7da8  ldarg.2
0x7da9  ldarg.3
0x7daa  ldarg.s  4
0x7dac  call     instance void Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::SetProperty(object target, string propName, class [System.Xml]System.Xml.XmlNode node, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x7db1  ret
```
