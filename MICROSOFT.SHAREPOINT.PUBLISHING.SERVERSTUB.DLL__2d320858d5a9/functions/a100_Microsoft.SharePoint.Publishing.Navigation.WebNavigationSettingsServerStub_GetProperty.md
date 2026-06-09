# Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::GetProperty

- ea: `0xa100`
- end: `0xa1d9`
- name: `Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::GetProperty`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa100`

## string_xrefs

- `0xa151`: `CreateFriendlyUrlsForNewPages`
- `0xa192`: `CreateFriendlyUrlsForNewPages`

## pseudocode

```c

```

## disassembly

```asm
0xa100  ldarg.2
0xa101  brtrue.s loc_A10E
0xa103  ldstr    aPropname// "propName"
0xa108  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa10d  throw
0xa10e  ldarg.3
0xa10f  brtrue.s loc_A11C
0xa111  ldstr    aProxycontext// "proxyContext"
0xa116  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa11b  throw
0xa11c  ldarg.1
0xa11d  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings
0xa122  stloc.0
0xa123  ldloc.0
0xa124  brtrue.s loc_A131
0xa126  ldstr    aTarget// "target"
0xa12b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa130  throw
0xa131  ldarg.0
0xa132  ldarg.2
0xa133  ldarg.3
0xa134  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa139  starg.s  2
0xa13b  ldarg.2
0xa13c  dup
0xa13d  stloc.1
0xa13e  brfalse  loc_A1CF
0xa143  ldloc.1
0xa144  ldstr    aAddnewpageston// "AddNewPagesToNavigation"
0xa149  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa14e  brtrue.s loc_A179
0xa150  ldloc.1
0xa151  ldstr    aCreatefriendly// "CreateFriendlyUrlsForNewPages"
0xa156  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa15b  brtrue.s loc_A191
0xa15d  ldloc.1
0xa15e  ldstr    aCurrentnavigat// "CurrentNavigation"
0xa163  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa168  brtrue.s loc_A1A9
0xa16a  ldloc.1
0xa16b  ldstr    aGlobalnavigati// "GlobalNavigation"
0xa170  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa175  brtrue.s loc_A1BC
0xa177  br.s     loc_A1CF
0xa179  ldarg.0
0xa17a  ldstr    aAddnewpageston// "AddNewPagesToNavigation"
0xa17f  ldarg.3
0xa180  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa185  ldloc.0
0xa186  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings::get_AddNewPagesToNavigation()
0xa18b  box      [mscorlib]System.Boolean
0xa190  ret
0xa191  ldarg.0
0xa192  ldstr    aCreatefriendly// "CreateFriendlyUrlsForNewPages"
0xa197  ldarg.3
0xa198  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa19d  ldloc.0
0xa19e  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings::get_CreateFriendlyUrlsForNewPages()
0xa1a3  box      [mscorlib]System.Boolean
0xa1a8  ret
0xa1a9  ldarg.0
0xa1aa  ldstr    aCurrentnavigat// "CurrentNavigation"
0xa1af  ldarg.3
0xa1b0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1b5  ldloc.0
0xa1b6  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettings [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings::get_CurrentNavigation()
0xa1bb  ret
0xa1bc  ldarg.0
0xa1bd  ldstr    aGlobalnavigati// "GlobalNavigation"
0xa1c2  ldarg.3
0xa1c3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1c8  ldloc.0
0xa1c9  callvirt instance class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.StandardNavigationSettings [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings::get_GlobalNavigation()
0xa1ce  ret
0xa1cf  ldarg.0
0xa1d0  ldarg.1
0xa1d1  ldarg.2
0xa1d2  ldarg.3
0xa1d3  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa1d8  ret
```
