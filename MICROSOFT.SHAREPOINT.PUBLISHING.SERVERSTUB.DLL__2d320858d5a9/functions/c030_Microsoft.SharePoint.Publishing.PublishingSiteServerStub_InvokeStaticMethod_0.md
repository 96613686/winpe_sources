# Microsoft.SharePoint.Publishing.PublishingSiteServerStub::InvokeStaticMethod_0

- ea: `0xc030`
- end: `0xc07a`
- name: `Microsoft.SharePoint.Publishing.PublishingSiteServerStub::InvokeStaticMethod_0`
- size: `74`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xc010`
- `0xc030`

## string_xrefs

- `0xc04e`: `CreatePageLayout`
- `0xc05f`: `CreatePageLayout`

## pseudocode

```c

```

## disassembly

```asm
0xc030  ldarg.3
0xc031  brtrue.s loc_C03E
0xc033  ldstr    aProxycontext// "proxyContext"
0xc038  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xc03d  throw
0xc03e  ldarg.0
0xc03f  ldarg.1
0xc040  ldarg.3
0xc041  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xc046  starg.s  1
0xc048  ldarg.1
0xc049  dup
0xc04a  stloc.0
0xc04b  brfalse.s loc_C073
0xc04d  ldloc.0
0xc04e  ldstr    aCreatepagelayo// "CreatePageLayout"
0xc053  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc058  brfalse.s loc_C073
0xc05a  ldarg.s  4
0xc05c  ldc.i4.1
0xc05d  stind.i1
0xc05e  ldarg.0
0xc05f  ldstr    aCreatepagelayo// "CreatePageLayout"
0xc064  ldarg.3
0xc065  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xc06a  ldarg.2
0xc06b  ldarg.3
0xc06c  call     void Microsoft.SharePoint.Publishing.PublishingSiteServerStub::CreatePageLayout_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xc071  ldnull
0xc072  ret
0xc073  ldarg.1
0xc074  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xc079  throw
```
