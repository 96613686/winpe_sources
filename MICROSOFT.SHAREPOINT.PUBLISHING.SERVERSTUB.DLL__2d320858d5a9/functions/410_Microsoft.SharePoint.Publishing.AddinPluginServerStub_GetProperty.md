# Microsoft.SharePoint.Publishing.AddinPluginServerStub::GetProperty

- ea: `0x410`
- end: `0x4bc`
- name: `Microsoft.SharePoint.Publishing.AddinPluginServerStub::GetProperty`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x410`

## pseudocode

```c

```

## disassembly

```asm
0x410  ldarg.2
0x411  brtrue.s loc_41E
0x413  ldstr    aPropname// "propName"
0x418  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x41d  throw
0x41e  ldarg.3
0x41f  brtrue.s loc_42C
0x421  ldstr    aProxycontext// "proxyContext"
0x426  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x42b  throw
0x42c  ldarg.1
0x42d  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin
0x432  stloc.0
0x433  ldloc.0
0x434  brtrue.s loc_441
0x436  ldstr    aTarget// "target"
0x43b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x440  throw
0x441  ldarg.0
0x442  ldarg.2
0x443  ldarg.3
0x444  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x449  starg.s  2
0x44b  ldarg.2
0x44c  dup
0x44d  stloc.1
0x44e  brfalse.s loc_4B2
0x450  ldloc.1
0x451  ldstr    aDescription// "Description"
0x456  call     bool [mscorlib]System.String::op_Equality(string, string)
0x45b  brtrue.s loc_479
0x45d  ldloc.1
0x45e  ldstr    aMarkup// "Markup"
0x463  call     bool [mscorlib]System.String::op_Equality(string, string)
0x468  brtrue.s loc_48C
0x46a  ldloc.1
0x46b  ldstr    aTitle// "Title"
0x470  call     bool [mscorlib]System.String::op_Equality(string, string)
0x475  brtrue.s loc_49F
0x477  br.s     loc_4B2
0x479  ldarg.0
0x47a  ldstr    aDescription// "Description"
0x47f  ldarg.3
0x480  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x485  ldloc.0
0x486  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin::get_Description()
0x48b  ret
0x48c  ldarg.0
0x48d  ldstr    aMarkup// "Markup"
0x492  ldarg.3
0x493  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x498  ldloc.0
0x499  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin::get_Markup()
0x49e  ret
0x49f  ldarg.0
0x4a0  ldstr    aTitle// "Title"
0x4a5  ldarg.3
0x4a6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ab  ldloc.0
0x4ac  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin::get_Title()
0x4b1  ret
0x4b2  ldarg.0
0x4b3  ldarg.1
0x4b4  ldarg.2
0x4b5  ldarg.3
0x4b6  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bb  ret
```
