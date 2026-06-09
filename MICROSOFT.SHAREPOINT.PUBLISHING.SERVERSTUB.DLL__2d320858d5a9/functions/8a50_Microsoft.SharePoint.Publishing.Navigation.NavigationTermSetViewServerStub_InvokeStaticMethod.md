# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::InvokeStaticMethod

- ea: `0x8a50`
- end: `0x8a99`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::InvokeStaticMethod`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x8a40`
- `0x8a50`

## string_xrefs

- `0x8a6e`: `CreateEmptyInstance`
- `0x8a7f`: `CreateEmptyInstance`

## pseudocode

```c

```

## disassembly

```asm
0x8a50  ldarg.3
0x8a51  brtrue.s loc_8A5E
0x8a53  ldstr    aProxycontext// "proxyContext"
0x8a58  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8a5d  throw
0x8a5e  ldarg.0
0x8a5f  ldarg.1
0x8a60  ldarg.3
0x8a61  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8a66  starg.s  1
0x8a68  ldarg.1
0x8a69  dup
0x8a6a  stloc.0
0x8a6b  brfalse.s loc_8A92
0x8a6d  ldloc.0
0x8a6e  ldstr    aCreateemptyins// "CreateEmptyInstance"
0x8a73  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8a78  brfalse.s loc_8A92
0x8a7a  ldarg.s  4
0x8a7c  ldc.i4.0
0x8a7d  stind.i1
0x8a7e  ldarg.0
0x8a7f  ldstr    aCreateemptyins// "CreateEmptyInstance"
0x8a84  ldarg.3
0x8a85  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8a8a  ldarg.2
0x8a8b  ldarg.3
0x8a8c  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::CreateEmptyInstance_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x8a91  ret
0x8a92  ldarg.1
0x8a93  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x8a98  throw
```
