# Microsoft.SharePoint.Publishing.SharePointHomeServiceManagerServerStub::InvokeMethod_0

- ea: `0xcdc0`
- end: `0xce2a`
- name: `Microsoft.SharePoint.Publishing.SharePointHomeServiceManagerServerStub::InvokeMethod_0`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xcda0`
- `0xcdc0`

## pseudocode

```c

```

## disassembly

```asm
0xcdc0  ldarg.s  4
0xcdc2  brtrue.s loc_CDCF
0xcdc4  ldstr    aProxycontext// "proxyContext"
0xcdc9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xcdce  throw
0xcdcf  ldarg.1
0xcdd0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager
0xcdd5  stloc.0
0xcdd6  ldloc.0
0xcdd7  brtrue.s loc_CDE4
0xcdd9  ldstr    aTarget// "target"
0xcdde  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xcde3  throw
0xcde4  ldarg.0
0xcde5  ldarg.2
0xcde6  ldarg.s  4
0xcde8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xcded  starg.s  2
0xcdef  ldarg.2
0xcdf0  dup
0xcdf1  stloc.1
0xcdf2  brfalse.s loc_CE1C
0xcdf4  ldloc.1
0xcdf5  ldstr    aGetacronymsand// "GetAcronymsAndColors"
0xcdfa  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcdff  brfalse.s loc_CE1C
0xce01  ldarg.s  5
0xce03  ldc.i4.0
0xce04  stind.i1
0xce05  ldarg.0
0xce06  ldstr    aGetacronymsand// "GetAcronymsAndColors"
0xce0b  ldarg.s  4
0xce0d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xce12  ldloc.0
0xce13  ldarg.3
0xce14  ldarg.s  4
0xce16  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager/AcronymInformation[] Microsoft.SharePoint.Publishing.SharePointHomeServiceManagerServerStub::GetAcronymsAndColors_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SharePointHomeServiceManager target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0xce1b  ret
0xce1c  ldarg.0
0xce1d  ldarg.1
0xce1e  ldarg.2
0xce1f  ldarg.3
0xce20  ldarg.s  4
0xce22  ldarg.s  5
0xce24  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0xce29  ret
```
