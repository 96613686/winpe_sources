# Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponseValueTypeConverter::GetProperty

- ea: `0x1f40`
- end: `0x1fb9`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponseValueTypeConverter::GetProperty`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1f40`

## pseudocode

```c

```

## disassembly

```asm
0x1f40  ldarg.3
0x1f41  brtrue.s loc_1F4E
0x1f43  ldstr    aProxycontext// "proxyContext"
0x1f48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1f4d  throw
0x1f4e  ldarg.1
0x1f4f  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse
0x1f54  stloc.0
0x1f55  ldloc.0
0x1f56  brtrue.s loc_1F63
0x1f58  ldstr    aTarget// "target"
0x1f5d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1f62  throw
0x1f63  ldarg.2
0x1f64  brtrue.s loc_1F71
0x1f66  ldstr    aPropname// "propName"
0x1f6b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1f70  throw
0x1f71  ldarg.0
0x1f72  ldarg.2
0x1f73  ldarg.3
0x1f74  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1f79  starg.s  2
0x1f7b  ldarg.2
0x1f7c  dup
0x1f7d  stloc.1
0x1f7e  brfalse.s loc_1FAF
0x1f80  ldloc.1
0x1f81  ldstr    aSitestatus// "SiteStatus"
0x1f86  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1f8b  brtrue.s loc_1F9C
0x1f8d  ldloc.1
0x1f8e  ldstr    aSiteurl// "SiteUrl"
0x1f93  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1f98  brtrue.s loc_1FA8
0x1f9a  br.s     loc_1FAF
0x1f9c  ldloc.0
0x1f9d  callvirt instance valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SiteStatus [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse::get_SiteStatus()
0x1fa2  box      [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SiteStatus
0x1fa7  ret
0x1fa8  ldloc.0
0x1fa9  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse::get_SiteUrl()
0x1fae  ret
0x1faf  ldarg.0
0x1fb0  ldarg.1
0x1fb1  ldarg.2
0x1fb2  ldarg.3
0x1fb3  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x1fb8  ret
```
