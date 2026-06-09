# Microsoft.SharePoint.ServerStub.SPHubSiteServerStub::InvokeMethod

- ea: `0x63160`
- end: `0x6321f`
- name: `Microsoft.SharePoint.ServerStub.SPHubSiteServerStub::InvokeMethod`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x63130`
- `0x63140`
- `0x63150`
- `0x63160`

## string_xrefs

- `0x631a2`: `Update`
- `0x631de`: `Update`
- `0x63195`: `Delete`
- `0x631c2`: `Delete`
- `0x631af`: `UpdateWithFieldValues`
- `0x631fa`: `UpdateWithFieldValues`

## pseudocode

```c

```

## disassembly

```asm
0x63160  ldarg.s  4
0x63162  brtrue.s loc_6316F
0x63164  ldstr    aProxycontext// "proxyContext"
0x63169  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6316e  throw
0x6316f  ldarg.1
0x63170  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPHubSite
0x63175  stloc.0
0x63176  ldloc.0
0x63177  brtrue.s loc_63184
0x63179  ldstr    aTarget// "target"
0x6317e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x63183  throw
0x63184  ldarg.0
0x63185  ldarg.2
0x63186  ldarg.s  4
0x63188  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6318d  starg.s  2
0x6318f  ldarg.2
0x63190  dup
0x63191  stloc.1
0x63192  brfalse.s loc_63211
0x63194  ldloc.1
0x63195  ldstr    aDelete// "Delete"
0x6319a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6319f  brtrue.s loc_631BD
0x631a1  ldloc.1
0x631a2  ldstr    aUpdate// "Update"
0x631a7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x631ac  brtrue.s loc_631D9
0x631ae  ldloc.1
0x631af  ldstr    aUpdatewithfiel// "UpdateWithFieldValues"
0x631b4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x631b9  brtrue.s loc_631F5
0x631bb  br.s     loc_63211
0x631bd  ldarg.s  5
0x631bf  ldc.i4.1
0x631c0  stind.i1
0x631c1  ldarg.0
0x631c2  ldstr    aDelete// "Delete"
0x631c7  ldarg.s  4
0x631c9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x631ce  ldloc.0
0x631cf  ldarg.3
0x631d0  ldarg.s  4
0x631d2  call     void Microsoft.SharePoint.ServerStub.SPHubSiteServerStub::Delete_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPHubSite target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x631d7  ldnull
0x631d8  ret
0x631d9  ldarg.s  5
0x631db  ldc.i4.1
0x631dc  stind.i1
0x631dd  ldarg.0
0x631de  ldstr    aUpdate// "Update"
0x631e3  ldarg.s  4
0x631e5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x631ea  ldloc.0
0x631eb  ldarg.3
0x631ec  ldarg.s  4
0x631ee  call     void Microsoft.SharePoint.ServerStub.SPHubSiteServerStub::Update_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPHubSite target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x631f3  ldnull
0x631f4  ret
0x631f5  ldarg.s  5
0x631f7  ldc.i4.1
0x631f8  stind.i1
0x631f9  ldarg.0
0x631fa  ldstr    aUpdatewithfiel// "UpdateWithFieldValues"
0x631ff  ldarg.s  4
0x63201  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x63206  ldloc.0
0x63207  ldarg.3
0x63208  ldarg.s  4
0x6320a  call     void Microsoft.SharePoint.ServerStub.SPHubSiteServerStub::UpdateWithFieldValues_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPHubSite target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x6320f  ldnull
0x63210  ret
0x63211  ldarg.0
0x63212  ldarg.1
0x63213  ldarg.2
0x63214  ldarg.3
0x63215  ldarg.s  4
0x63217  ldarg.s  5
0x63219  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x6321e  ret
```
