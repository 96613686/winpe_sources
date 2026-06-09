# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::SetProperty_0

- ea: `0x6010`
- end: `0x6085`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItemServerStub::SetProperty_0`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x76e0`
- `0x8500`

## callees

- `0x6010`

## string_xrefs

- `0x6053`: `LinkType`
- `0x6060`: `LinkType`

## pseudocode

```c

```

## disassembly

```asm
0x6010  ldarg.s  4
0x6012  brtrue.s loc_601F
0x6014  ldstr    aProxycontext// "proxyContext"
0x6019  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x601e  throw
0x601f  ldarg.1
0x6020  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem
0x6025  stloc.0
0x6026  ldloc.0
0x6027  brtrue.s loc_6034
0x6029  ldstr    aTarget// "target"
0x602e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6033  throw
0x6034  ldarg.2
0x6035  brtrue.s loc_6042
0x6037  ldstr    aPropname// "propName"
0x603c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x6041  throw
0x6042  ldarg.0
0x6043  ldarg.2
0x6044  ldarg.s  4
0x6046  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x604b  starg.s  2
0x604d  ldarg.2
0x604e  dup
0x604f  stloc.1
0x6050  brfalse.s loc_6079
0x6052  ldloc.1
0x6053  ldstr    aLinktype// "LinkType"
0x6058  call     bool [mscorlib]System.String::op_Equality(string, string)
0x605d  brfalse.s loc_6079
0x605f  ldarg.0
0x6060  ldstr    aLinktype// "LinkType"
0x6065  ldarg.s  4
0x6067  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x606c  ldloc.0
0x606d  ldarg.3
0x606e  callvirt T0x2B000014
0x6073  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetItem::set_LinkType(valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationLinkType)
0x6078  ret
0x6079  ldarg.0
0x607a  ldarg.1
0x607b  ldarg.2
0x607c  ldarg.3
0x607d  ldarg.s  4
0x607f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::SetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x6084  ret
```
