# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::InvokeMethod

- ea: `0x86c0`
- end: `0x872a`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::InvokeMethod`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x86b0`
- `0x86c0`

## string_xrefs

- `0x86f5`: `GetCopy`
- `0x8706`: `GetCopy`

## pseudocode

```c

```

## disassembly

```asm
0x86c0  ldarg.s  4
0x86c2  brtrue.s loc_86CF
0x86c4  ldstr    aProxycontext// "proxyContext"
0x86c9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x86ce  throw
0x86cf  ldarg.1
0x86d0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView
0x86d5  stloc.0
0x86d6  ldloc.0
0x86d7  brtrue.s loc_86E4
0x86d9  ldstr    aTarget// "target"
0x86de  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x86e3  throw
0x86e4  ldarg.0
0x86e5  ldarg.2
0x86e6  ldarg.s  4
0x86e8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x86ed  starg.s  2
0x86ef  ldarg.2
0x86f0  dup
0x86f1  stloc.1
0x86f2  brfalse.s loc_871C
0x86f4  ldloc.1
0x86f5  ldstr    aGetcopy// "GetCopy"
0x86fa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x86ff  brfalse.s loc_871C
0x8701  ldarg.s  5
0x8703  ldc.i4.0
0x8704  stind.i1
0x8705  ldarg.0
0x8706  ldstr    aGetcopy// "GetCopy"
0x870b  ldarg.s  4
0x870d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8712  ldloc.0
0x8713  ldarg.3
0x8714  ldarg.s  4
0x8716  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::GetCopy_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x871b  ret
0x871c  ldarg.0
0x871d  ldarg.1
0x871e  ldarg.2
0x871f  ldarg.3
0x8720  ldarg.s  4
0x8722  ldarg.s  5
0x8724  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x8729  ret
```
