# Microsoft.SharePoint.Publishing.AddinPluginServerStub::SetProperty_0

- ea: `0x8b0`
- end: `0x975`
- name: `Microsoft.SharePoint.Publishing.AddinPluginServerStub::SetProperty_0`
- size: `197`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x8b0`

## pseudocode

```c

```

## disassembly

```asm
0x8b0  ldarg.s  4
0x8b2  brtrue.s loc_8BF
0x8b4  ldstr    aProxycontext// "proxyContext"
0x8b9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8be  throw
0x8bf  ldarg.1
0x8c0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin
0x8c5  stloc.0
0x8c6  ldloc.0
0x8c7  brtrue.s loc_8D4
0x8c9  ldstr    aTarget// "target"
0x8ce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8d3  throw
0x8d4  ldarg.2
0x8d5  brtrue.s loc_8E2
0x8d7  ldstr    aPropname// "propName"
0x8dc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8e1  throw
0x8e2  ldarg.0
0x8e3  ldarg.2
0x8e4  ldarg.s  4
0x8e6  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8eb  starg.s  2
0x8ed  ldarg.2
0x8ee  dup
0x8ef  stloc.1
0x8f0  brfalse.s loc_969
0x8f2  ldloc.1
0x8f3  ldstr    aDescription// "Description"
0x8f8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8fd  brtrue.s loc_91B
0x8ff  ldloc.1
0x900  ldstr    aMarkup// "Markup"
0x905  call     bool [mscorlib]System.String::op_Equality(string, string)
0x90a  brtrue.s loc_935
0x90c  ldloc.1
0x90d  ldstr    aTitle// "Title"
0x912  call     bool [mscorlib]System.String::op_Equality(string, string)
0x917  brtrue.s loc_94F
0x919  br.s     loc_969
0x91b  ldarg.0
0x91c  ldstr    aDescription// "Description"
0x921  ldarg.s  4
0x923  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x928  ldloc.0
0x929  ldarg.3
0x92a  callvirt T0x2B000001
0x92f  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin::set_Description(string)
0x934  ret
0x935  ldarg.0
0x936  ldstr    aMarkup// "Markup"
0x93b  ldarg.s  4
0x93d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x942  ldloc.0
0x943  ldarg.3
0x944  callvirt T0x2B000001
0x949  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin::set_Markup(string)
0x94e  ret
0x94f  ldarg.0
0x950  ldstr    aTitle// "Title"
0x955  ldarg.s  4
0x957  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x95c  ldloc.0
0x95d  ldarg.3
0x95e  callvirt T0x2B000001
0x963  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.AddinPlugin::set_Title(string)
0x968  ret
0x969  ldarg.0
0x96a  ldarg.1
0x96b  ldarg.2
0x96c  ldarg.3
0x96d  ldarg.s  4
0x96f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x974  ret
```
