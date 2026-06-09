# Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::InvokeMethod_0

- ea: `0xa5d0`
- end: `0xa666`
- name: `Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::InvokeMethod_0`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xa5a0`
- `0xa5c0`
- `0xa5d0`

## string_xrefs

- `0xa605`: `Update`
- `0xa625`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0xa5d0  ldarg.s  4
0xa5d2  brtrue.s loc_A5DF
0xa5d4  ldstr    aProxycontext// "proxyContext"
0xa5d9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa5de  throw
0xa5df  ldarg.1
0xa5e0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings
0xa5e5  stloc.0
0xa5e6  ldloc.0
0xa5e7  brtrue.s loc_A5F4
0xa5e9  ldstr    aTarget// "target"
0xa5ee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa5f3  throw
0xa5f4  ldarg.0
0xa5f5  ldarg.2
0xa5f6  ldarg.s  4
0xa5f8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa5fd  starg.s  2
0xa5ff  ldarg.2
0xa600  dup
0xa601  stloc.1
0xa602  brfalse.s loc_A658
0xa604  ldloc.1
0xa605  ldstr    aUpdate// "Update"
0xa60a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa60f  brtrue.s loc_A620
0xa611  ldloc.1
0xa612  ldstr    aResettodefault// "ResetToDefaults"
0xa617  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa61c  brtrue.s loc_A63C
0xa61e  br.s     loc_A658
0xa620  ldarg.s  5
0xa622  ldc.i4.1
0xa623  stind.i1
0xa624  ldarg.0
0xa625  ldstr    aUpdate// "Update"
0xa62a  ldarg.s  4
0xa62c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa631  ldloc.0
0xa632  ldarg.3
0xa633  ldarg.s  4
0xa635  call     void Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::Update_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa63a  ldnull
0xa63b  ret
0xa63c  ldarg.s  5
0xa63e  ldc.i4.1
0xa63f  stind.i1
0xa640  ldarg.0
0xa641  ldstr    aResettodefault// "ResetToDefaults"
0xa646  ldarg.s  4
0xa648  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa64d  ldloc.0
0xa64e  ldarg.3
0xa64f  ldarg.s  4
0xa651  call     void Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::ResetToDefaults_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa656  ldnull
0xa657  ret
0xa658  ldarg.0
0xa659  ldarg.1
0xa65a  ldarg.2
0xa65b  ldarg.3
0xa65c  ldarg.s  4
0xa65e  ldarg.s  5
0xa660  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0xa665  ret
```
