# Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::SetProperty

- ea: `0xa1e0`
- end: `0xa282`
- name: `Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::SetProperty`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa1e0`

## string_xrefs

- `0xa230`: `CreateFriendlyUrlsForNewPages`
- `0xa25b`: `CreateFriendlyUrlsForNewPages`

## pseudocode

```c

```

## disassembly

```asm
0xa1e0  ldarg.s  4
0xa1e2  brtrue.s loc_A1EF
0xa1e4  ldstr    aProxycontext// "proxyContext"
0xa1e9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa1ee  throw
0xa1ef  ldarg.1
0xa1f0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings
0xa1f5  stloc.0
0xa1f6  ldloc.0
0xa1f7  brtrue.s loc_A204
0xa1f9  ldstr    aTarget// "target"
0xa1fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa203  throw
0xa204  ldarg.2
0xa205  brtrue.s loc_A212
0xa207  ldstr    aPropname// "propName"
0xa20c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa211  throw
0xa212  ldarg.0
0xa213  ldarg.2
0xa214  ldarg.s  4
0xa216  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa21b  starg.s  2
0xa21d  ldarg.2
0xa21e  dup
0xa21f  stloc.1
0xa220  brfalse.s loc_A276
0xa222  ldloc.1
0xa223  ldstr    aAddnewpageston// "AddNewPagesToNavigation"
0xa228  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa22d  brtrue.s loc_A23E
0xa22f  ldloc.1
0xa230  ldstr    aCreatefriendly// "CreateFriendlyUrlsForNewPages"
0xa235  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa23a  brtrue.s loc_A25A
0xa23c  br.s     loc_A276
0xa23e  ldarg.0
0xa23f  ldstr    aAddnewpageston// "AddNewPagesToNavigation"
0xa244  ldarg.s  4
0xa246  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa24b  ldloc.0
0xa24c  ldarg.3
0xa24d  ldarg.s  4
0xa24f  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa254  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings::set_AddNewPagesToNavigation(bool)
0xa259  ret
0xa25a  ldarg.0
0xa25b  ldstr    aCreatefriendly// "CreateFriendlyUrlsForNewPages"
0xa260  ldarg.s  4
0xa262  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa267  ldloc.0
0xa268  ldarg.3
0xa269  ldarg.s  4
0xa26b  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa270  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings::set_CreateFriendlyUrlsForNewPages(bool)
0xa275  ret
0xa276  ldarg.0
0xa277  ldarg.1
0xa278  ldarg.2
0xa279  ldarg.3
0xa27a  ldarg.s  4
0xa27c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa281  ret
```
