# Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::InvokeMethod_0

- ea: `0x2320`
- end: `0x23b4`
- name: `Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::InvokeMethod_0`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x22e0`
- `0x2300`
- `0x2320`

## string_xrefs

- `0x2355`: `Create`
- `0x2375`: `Create`

## pseudocode

```c

```

## disassembly

```asm
0x2320  ldarg.s  4
0x2322  brtrue.s loc_232F
0x2324  ldstr    aProxycontext// "proxyContext"
0x2329  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x232e  throw
0x232f  ldarg.1
0x2330  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSite
0x2335  stloc.0
0x2336  ldloc.0
0x2337  brtrue.s loc_2344
0x2339  ldstr    aTarget// "target"
0x233e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2343  throw
0x2344  ldarg.0
0x2345  ldarg.2
0x2346  ldarg.s  4
0x2348  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x234d  starg.s  2
0x234f  ldarg.2
0x2350  dup
0x2351  stloc.1
0x2352  brfalse.s loc_23A6
0x2354  ldloc.1
0x2355  ldstr    aCreate// "Create"
0x235a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x235f  brtrue.s loc_2370
0x2361  ldloc.1
0x2362  ldstr    aStatus// "Status"
0x2367  call     bool [mscorlib]System.String::op_Equality(string, string)
0x236c  brtrue.s loc_238B
0x236e  br.s     loc_23A6
0x2370  ldarg.s  5
0x2372  ldc.i4.0
0x2373  stind.i1
0x2374  ldarg.0
0x2375  ldstr    aCreate// "Create"
0x237a  ldarg.s  4
0x237c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2381  ldloc.0
0x2382  ldarg.3
0x2383  ldarg.s  4
0x2385  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::Create_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSite target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x238a  ret
0x238b  ldarg.s  5
0x238d  ldc.i4.0
0x238e  stind.i1
0x238f  ldarg.0
0x2390  ldstr    aStatus// "Status"
0x2395  ldarg.s  4
0x2397  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x239c  ldloc.0
0x239d  ldarg.3
0x239e  ldarg.s  4
0x23a0  call     class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSiteCreationResponse Microsoft.SharePoint.Publishing.CommunicationSiteServerStub::Status_MethodProxy(class [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.CommunicationSite target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x23a5  ret
0x23a6  ldarg.0
0x23a7  ldarg.1
0x23a8  ldarg.2
0x23a9  ldarg.3
0x23aa  ldarg.s  4
0x23ac  ldarg.s  5
0x23ae  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x23b3  ret
```
