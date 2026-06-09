# Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::InvokeMethod

- ea: `0xa060`
- end: `0xa0f6`
- name: `Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::InvokeMethod`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xa030`
- `0xa050`
- `0xa060`

## string_xrefs

- `0xa095`: `Update`
- `0xa0b5`: `Update`

## pseudocode

```c

```

## disassembly

```asm
0xa060  ldarg.s  4
0xa062  brtrue.s loc_A06F
0xa064  ldstr    aProxycontext// "proxyContext"
0xa069  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa06e  throw
0xa06f  ldarg.1
0xa070  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings
0xa075  stloc.0
0xa076  ldloc.0
0xa077  brtrue.s loc_A084
0xa079  ldstr    aTarget// "target"
0xa07e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa083  throw
0xa084  ldarg.0
0xa085  ldarg.2
0xa086  ldarg.s  4
0xa088  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa08d  starg.s  2
0xa08f  ldarg.2
0xa090  dup
0xa091  stloc.1
0xa092  brfalse.s loc_A0E8
0xa094  ldloc.1
0xa095  ldstr    aUpdate// "Update"
0xa09a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa09f  brtrue.s loc_A0B0
0xa0a1  ldloc.1
0xa0a2  ldstr    aResettodefault// "ResetToDefaults"
0xa0a7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa0ac  brtrue.s loc_A0CC
0xa0ae  br.s     loc_A0E8
0xa0b0  ldarg.s  5
0xa0b2  ldc.i4.1
0xa0b3  stind.i1
0xa0b4  ldarg.0
0xa0b5  ldstr    aUpdate// "Update"
0xa0ba  ldarg.s  4
0xa0bc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa0c1  ldloc.0
0xa0c2  ldarg.3
0xa0c3  ldarg.s  4
0xa0c5  call     void Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::Update_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa0ca  ldnull
0xa0cb  ret
0xa0cc  ldarg.s  5
0xa0ce  ldc.i4.1
0xa0cf  stind.i1
0xa0d0  ldarg.0
0xa0d1  ldstr    aResettodefault// "ResetToDefaults"
0xa0d6  ldarg.s  4
0xa0d8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xa0dd  ldloc.0
0xa0de  ldarg.3
0xa0df  ldarg.s  4
0xa0e1  call     void Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettingsServerStub::ResetToDefaults_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.WebNavigationSettings target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xa0e6  ldnull
0xa0e7  ret
0xa0e8  ldarg.0
0xa0e9  ldarg.1
0xa0ea  ldarg.2
0xa0eb  ldarg.3
0xa0ec  ldarg.s  4
0xa0ee  ldarg.s  5
0xa0f0  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0xa0f5  ret
```
