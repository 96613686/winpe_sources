# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::InvokeStaticMethod_0

- ea: `0x9170`
- end: `0x91b9`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::InvokeStaticMethod_0`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x9160`
- `0x9170`

## string_xrefs

- `0x918e`: `CreateEmptyInstance`
- `0x919f`: `CreateEmptyInstance`

## pseudocode

```c

```

## disassembly

```asm
0x9170  ldarg.3
0x9171  brtrue.s loc_917E
0x9173  ldstr    aProxycontext// "proxyContext"
0x9178  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x917d  throw
0x917e  ldarg.0
0x917f  ldarg.1
0x9180  ldarg.3
0x9181  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9186  starg.s  1
0x9188  ldarg.1
0x9189  dup
0x918a  stloc.0
0x918b  brfalse.s loc_91B2
0x918d  ldloc.0
0x918e  ldstr    aCreateemptyins// "CreateEmptyInstance"
0x9193  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9198  brfalse.s loc_91B2
0x919a  ldarg.s  4
0x919c  ldc.i4.0
0x919d  stind.i1
0x919e  ldarg.0
0x919f  ldstr    aCreateemptyins// "CreateEmptyInstance"
0x91a4  ldarg.3
0x91a5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x91aa  ldarg.2
0x91ab  ldarg.3
0x91ac  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::CreateEmptyInstance_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x91b1  ret
0x91b2  ldarg.1
0x91b3  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x91b8  throw
```
