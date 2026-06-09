# Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponseValueTypeConverter::SetProperty

- ea: `0x1fc0`
- end: `0x2052`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponseValueTypeConverter::SetProperty`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1fc0`

## pseudocode

```c

```

## disassembly

```asm
0x1fc0  ldarg.s  4
0x1fc2  brtrue.s loc_1FCF
0x1fc4  ldstr    aProxycontext// "proxyContext"
0x1fc9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1fce  throw
0x1fcf  ldarg.1
0x1fd0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse
0x1fd5  stloc.0
0x1fd6  ldloc.0
0x1fd7  brtrue.s loc_1FE4
0x1fd9  ldstr    aTarget// "target"
0x1fde  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1fe3  throw
0x1fe4  ldarg.2
0x1fe5  brtrue.s loc_1FF2
0x1fe7  ldstr    aPropname// "propName"
0x1fec  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1ff1  throw
0x1ff2  ldarg.3
0x1ff3  brtrue.s loc_2000
0x1ff5  ldstr    aPropvalue// "propValue"
0x1ffa  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1fff  throw
0x2000  ldarg.0
0x2001  ldarg.2
0x2002  ldarg.s  4
0x2004  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2009  starg.s  2
0x200b  ldarg.2
0x200c  dup
0x200d  stloc.1
0x200e  brfalse.s loc_2046
0x2010  ldloc.1
0x2011  ldstr    aSitestatus// "SiteStatus"
0x2016  call     bool [mscorlib]System.String::op_Equality(string, string)
0x201b  brtrue.s loc_202C
0x201d  ldloc.1
0x201e  ldstr    aSiteurl// "SiteUrl"
0x2023  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2028  brtrue.s loc_2039
0x202a  br.s     loc_2046
0x202c  ldloc.0
0x202d  ldarg.3
0x202e  callvirt T0x2B00000A
0x2033  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse::set_SiteStatus(valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SiteStatus)
0x2038  ret
0x2039  ldloc.0
0x203a  ldarg.3
0x203b  callvirt T0x2B000001
0x2040  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse::set_SiteUrl(string)
0x2045  ret
0x2046  ldarg.0
0x2047  ldarg.1
0x2048  ldarg.2
0x2049  ldarg.3
0x204a  ldarg.s  4
0x204c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::SetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2051  ret
```
