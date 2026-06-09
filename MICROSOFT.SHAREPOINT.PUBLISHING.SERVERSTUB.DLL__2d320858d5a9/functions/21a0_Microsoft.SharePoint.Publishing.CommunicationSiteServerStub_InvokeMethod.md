# Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::InvokeMethod

- ea: `0x21a0`
- end: `0x2234`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::InvokeMethod`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x2160`
- `0x2180`
- `0x21a0`

## string_xrefs

- `0x21d5`: `Create`
- `0x21f5`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x21a0  ldarg.s  4
0x21a2  brtrue.s loc_21AF
0x21a4  ldstr    aProxycontext// "proxyContext"
0x21a9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x21ae  throw
0x21af  ldarg.1
0x21b0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSite
0x21b5  stloc.0
0x21b6  ldloc.0
0x21b7  brtrue.s loc_21C4
0x21b9  ldstr    aTarget// "target"
0x21be  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x21c3  throw
0x21c4  ldarg.0
0x21c5  ldarg.2
0x21c6  ldarg.s  4
0x21c8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x21cd  starg.s  2
0x21cf  ldarg.2
0x21d0  dup
0x21d1  stloc.1
0x21d2  brfalse.s loc_2226
0x21d4  ldloc.1
0x21d5  ldstr    aCreate// "Create"
0x21da  call     bool [mscorlib]System.String::op_Equality(string, string)
0x21df  brtrue.s loc_21F0
0x21e1  ldloc.1
0x21e2  ldstr    aStatus// "Status"
0x21e7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x21ec  brtrue.s loc_220B
0x21ee  br.s     loc_2226
0x21f0  ldarg.s  5
0x21f2  ldc.i4.0
0x21f3  stind.i1
0x21f4  ldarg.0
0x21f5  ldstr    aCreate// "Create"
0x21fa  ldarg.s  4
0x21fc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2201  ldloc.0
0x2202  ldarg.3
0x2203  ldarg.s  4
0x2205  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::Create_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSite target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x220a  ret
0x220b  ldarg.s  5
0x220d  ldc.i4.0
0x220e  stind.i1
0x220f  ldarg.0
0x2210  ldstr    aStatus// "Status"
0x2215  ldarg.s  4
0x2217  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x221c  ldloc.0
0x221d  ldarg.3
0x221e  ldarg.s  4
0x2220  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::Status_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSite target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2225  ret
0x2226  ldarg.0
0x2227  ldarg.1
0x2228  ldarg.2
0x2229  ldarg.3
0x222a  ldarg.s  4
0x222c  ldarg.s  5
0x222e  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x2233  ret
```
