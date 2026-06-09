# Microsoft.SharePoint.Publishing.PublishingSiteServerStub::InvokeStaticMethod

- ea: `0xbf60`
- end: `0xbfaa`
- name: `Microsoft.SharePoint.Publishing.PublishingSiteServerStub::InvokeStaticMethod`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xbf40`
- `0xbf60`

## string_xrefs

- `0xbf7e`: `CreatePageLayout`
- `0xbf8f`: `CreatePageLayout`

## pseudocode

```c

```

## disassembly

```asm
0xbf60  ldarg.3
0xbf61  brtrue.s loc_BF6E
0xbf63  ldstr    aProxycontext// "proxyContext"
0xbf68  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xbf6d  throw
0xbf6e  ldarg.0
0xbf6f  ldarg.1
0xbf70  ldarg.3
0xbf71  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xbf76  starg.s  1
0xbf78  ldarg.1
0xbf79  dup
0xbf7a  stloc.0
0xbf7b  brfalse.s loc_BFA3
0xbf7d  ldloc.0
0xbf7e  ldstr    aCreatepagelayo// "CreatePageLayout"
0xbf83  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbf88  brfalse.s loc_BFA3
0xbf8a  ldarg.s  4
0xbf8c  ldc.i4.1
0xbf8d  stind.i1
0xbf8e  ldarg.0
0xbf8f  ldstr    aCreatepagelayo// "CreatePageLayout"
0xbf94  ldarg.3
0xbf95  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xbf9a  ldarg.2
0xbf9b  ldarg.3
0xbf9c  call     void Microsoft.SharePoint.Publishing.PublishingSiteServerStub::CreatePageLayout_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xbfa1  ldnull
0xbfa2  ret
0xbfa3  ldarg.1
0xbfa4  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xbfa9  throw
```
