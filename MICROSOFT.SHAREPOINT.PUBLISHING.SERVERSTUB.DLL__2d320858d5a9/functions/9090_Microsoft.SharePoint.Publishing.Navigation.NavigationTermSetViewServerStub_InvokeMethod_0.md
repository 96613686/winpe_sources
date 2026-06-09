# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::InvokeMethod_0

- ea: `0x9090`
- end: `0x90fa`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::InvokeMethod_0`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x9080`
- `0x9090`

## string_xrefs

- `0x90c5`: `GetCopy`
- `0x90d6`: `GetCopy`

## pseudocode

```c

```

## disassembly

```asm
0x9090  ldarg.s  4
0x9092  brtrue.s loc_909F
0x9094  ldstr    aProxycontext// "proxyContext"
0x9099  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x909e  throw
0x909f  ldarg.1
0x90a0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView
0x90a5  stloc.0
0x90a6  ldloc.0
0x90a7  brtrue.s loc_90B4
0x90a9  ldstr    aTarget// "target"
0x90ae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x90b3  throw
0x90b4  ldarg.0
0x90b5  ldarg.2
0x90b6  ldarg.s  4
0x90b8  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x90bd  starg.s  2
0x90bf  ldarg.2
0x90c0  dup
0x90c1  stloc.1
0x90c2  brfalse.s loc_90EC
0x90c4  ldloc.1
0x90c5  ldstr    aGetcopy// "GetCopy"
0x90ca  call     bool [mscorlib]System.String::op_Equality(string, string)
0x90cf  brfalse.s loc_90EC
0x90d1  ldarg.s  5
0x90d3  ldc.i4.0
0x90d4  stind.i1
0x90d5  ldarg.0
0x90d6  ldstr    aGetcopy// "GetCopy"
0x90db  ldarg.s  4
0x90dd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x90e2  ldloc.0
0x90e3  ldarg.3
0x90e4  ldarg.s  4
0x90e6  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::GetCopy_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x90eb  ret
0x90ec  ldarg.0
0x90ed  ldarg.1
0x90ee  ldarg.2
0x90ef  ldarg.3
0x90f0  ldarg.s  4
0x90f2  ldarg.s  5
0x90f4  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x90f9  ret
```
