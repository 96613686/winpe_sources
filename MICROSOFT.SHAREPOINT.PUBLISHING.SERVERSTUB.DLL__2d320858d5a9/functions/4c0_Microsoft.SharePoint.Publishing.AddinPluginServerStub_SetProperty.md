# Microsoft.SharePoint.Publishing.AddinPluginServerStub::SetProperty

- ea: `0x4c0`
- end: `0x58b`
- name: `Microsoft.SharePoint.Publishing.AddinPluginServerStub::SetProperty`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4c0`

## pseudocode

```c

```

## disassembly

```asm
0x4c0  ldarg.s  4
0x4c2  brtrue.s loc_4CF
0x4c4  ldstr    aProxycontext// "proxyContext"
0x4c9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4ce  throw
0x4cf  ldarg.1
0x4d0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin
0x4d5  stloc.0
0x4d6  ldloc.0
0x4d7  brtrue.s loc_4E4
0x4d9  ldstr    aTarget// "target"
0x4de  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4e3  throw
0x4e4  ldarg.2
0x4e5  brtrue.s loc_4F2
0x4e7  ldstr    aPropname// "propName"
0x4ec  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4f1  throw
0x4f2  ldarg.0
0x4f3  ldarg.2
0x4f4  ldarg.s  4
0x4f6  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4fb  starg.s  2
0x4fd  ldarg.2
0x4fe  dup
0x4ff  stloc.1
0x500  brfalse.s loc_57F
0x502  ldloc.1
0x503  ldstr    aDescription// "Description"
0x508  call     bool [mscorlib]System.String::op_Equality(string, string)
0x50d  brtrue.s loc_52B
0x50f  ldloc.1
0x510  ldstr    aMarkup// "Markup"
0x515  call     bool [mscorlib]System.String::op_Equality(string, string)
0x51a  brtrue.s loc_547
0x51c  ldloc.1
0x51d  ldstr    aTitle// "Title"
0x522  call     bool [mscorlib]System.String::op_Equality(string, string)
0x527  brtrue.s loc_563
0x529  br.s     loc_57F
0x52b  ldarg.0
0x52c  ldstr    aDescription// "Description"
0x531  ldarg.s  4
0x533  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x538  ldloc.0
0x539  ldarg.3
0x53a  ldarg.s  4
0x53c  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x541  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin::set_Description(string)
0x546  ret
0x547  ldarg.0
0x548  ldstr    aMarkup// "Markup"
0x54d  ldarg.s  4
0x54f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x554  ldloc.0
0x555  ldarg.3
0x556  ldarg.s  4
0x558  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x55d  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin::set_Markup(string)
0x562  ret
0x563  ldarg.0
0x564  ldstr    aTitle// "Title"
0x569  ldarg.s  4
0x56b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x570  ldloc.0
0x571  ldarg.3
0x572  ldarg.s  4
0x574  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x579  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin::set_Title(string)
0x57e  ret
0x57f  ldarg.0
0x580  ldarg.1
0x581  ldarg.2
0x582  ldarg.3
0x583  ldarg.s  4
0x585  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58a  ret
```
