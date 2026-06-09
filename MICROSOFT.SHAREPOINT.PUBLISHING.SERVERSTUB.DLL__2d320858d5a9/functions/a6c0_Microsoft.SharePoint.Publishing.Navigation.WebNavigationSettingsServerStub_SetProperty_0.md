# Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::SetProperty_0

- ea: `0xa6c0`
- end: `0xa75e`
- name: `Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::SetProperty_0`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa6c0`

## string_xrefs

- `0xa710`: `CreateFriendlyUrlsForNewPages`
- `0xa739`: `CreateFriendlyUrlsForNewPages`

## pseudocode

```c

```

## disassembly

```asm
0xa6c0  ldarg.s  4
0xa6c2  brtrue.s loc_A6CF
0xa6c4  ldstr    aProxycontext// "proxyContext"
0xa6c9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa6ce  throw
0xa6cf  ldarg.1
0xa6d0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings
0xa6d5  stloc.0
0xa6d6  ldloc.0
0xa6d7  brtrue.s loc_A6E4
0xa6d9  ldstr    aTarget// "target"
0xa6de  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa6e3  throw
0xa6e4  ldarg.2
0xa6e5  brtrue.s loc_A6F2
0xa6e7  ldstr    aPropname// "propName"
0xa6ec  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa6f1  throw
0xa6f2  ldarg.0
0xa6f3  ldarg.2
0xa6f4  ldarg.s  4
0xa6f6  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa6fb  starg.s  2
0xa6fd  ldarg.2
0xa6fe  dup
0xa6ff  stloc.1
0xa700  brfalse.s loc_A752
0xa702  ldloc.1
0xa703  ldstr    aAddnewpageston// "AddNewPagesToNavigation"
0xa708  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa70d  brtrue.s loc_A71E
0xa70f  ldloc.1
0xa710  ldstr    aCreatefriendly// "CreateFriendlyUrlsForNewPages"
0xa715  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa71a  brtrue.s loc_A738
0xa71c  br.s     loc_A752
0xa71e  ldarg.0
0xa71f  ldstr    aAddnewpageston// "AddNewPagesToNavigation"
0xa724  ldarg.s  4
0xa726  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa72b  ldloc.0
0xa72c  ldarg.3
0xa72d  callvirt T0x2B000007
0xa732  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings::set_AddNewPagesToNavigation(bool)
0xa737  ret
0xa738  ldarg.0
0xa739  ldstr    aCreatefriendly// "CreateFriendlyUrlsForNewPages"
0xa73e  ldarg.s  4
0xa740  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa745  ldloc.0
0xa746  ldarg.3
0xa747  callvirt T0x2B000007
0xa74c  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings::set_CreateFriendlyUrlsForNewPages(bool)
0xa751  ret
0xa752  ldarg.0
0xa753  ldarg.1
0xa754  ldarg.2
0xa755  ldarg.3
0xa756  ldarg.s  4
0xa758  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa75d  ret
```
