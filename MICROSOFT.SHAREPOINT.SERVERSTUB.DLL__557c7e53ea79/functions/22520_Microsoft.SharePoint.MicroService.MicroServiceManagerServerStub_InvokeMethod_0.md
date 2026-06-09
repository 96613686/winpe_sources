# Microsoft.SharePoint.MicroService.MicroServiceManagerServerStub::InvokeMethod_0

- ea: `0x22520`
- end: `0x22611`
- name: `Microsoft.SharePoint.MicroService.MicroServiceManagerServerStub::InvokeMethod_0`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x22480`
- `0x224a0`
- `0x224c0`
- `0x22500`
- `0x22520`

## string_xrefs

- `0x22558`: `GetServiceUrls`
- `0x22592`: `GetServiceUrls`
- `0x22565`: `GetServiceInternalUrls`
- `0x225ad`: `GetServiceInternalUrls`
- `0x22572`: `AddMicroserviceWorkItem`
- `0x225c8`: `AddMicroserviceWorkItem`
- `0x2257f`: `DeleteMicroserviceWorkItem`
- `0x225e8`: `DeleteMicroserviceWorkItem`

## pseudocode

```c

```

## disassembly

```asm
0x22520  ldarg.s  4
0x22522  brtrue.s loc_2252F
0x22524  ldstr    aProxycontext// "proxyContext"
0x22529  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2252e  throw
0x2252f  ldarg.1
0x22530  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.MicroService.MicroServiceManager
0x22535  stloc.0
0x22536  ldloc.0
0x22537  brtrue.s loc_22544
0x22539  ldstr    aTarget// "target"
0x2253e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x22543  throw
0x22544  ldarg.0
0x22545  ldarg.2
0x22546  ldarg.s  4
0x22548  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2254d  starg.s  2
0x2254f  ldarg.2
0x22550  dup
0x22551  stloc.1
0x22552  brfalse  loc_22603
0x22557  ldloc.1
0x22558  ldstr    aGetserviceurls// "GetServiceUrls"
0x2255d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22562  brtrue.s loc_2258D
0x22564  ldloc.1
0x22565  ldstr    aGetserviceinte// "GetServiceInternalUrls"
0x2256a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2256f  brtrue.s loc_225A8
0x22571  ldloc.1
0x22572  ldstr    aAddmicroservic// "AddMicroserviceWorkItem"
0x22577  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2257c  brtrue.s loc_225C3
0x2257e  ldloc.1
0x2257f  ldstr    aDeletemicroser// "DeleteMicroserviceWorkItem"
0x22584  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22589  brtrue.s loc_225E3
0x2258b  br.s     loc_22603
0x2258d  ldarg.s  5
0x2258f  ldc.i4.0
0x22590  stind.i1
0x22591  ldarg.0
0x22592  ldstr    aGetserviceurls// "GetServiceUrls"
0x22597  ldarg.s  4
0x22599  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2259e  ldloc.0
0x2259f  ldarg.3
0x225a0  ldarg.s  4
0x225a2  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.MicroService.MicroServiceManagerServerStub::GetServiceUrls_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.MicroService.MicroServiceManager target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x225a7  ret
0x225a8  ldarg.s  5
0x225aa  ldc.i4.0
0x225ab  stind.i1
0x225ac  ldarg.0
0x225ad  ldstr    aGetserviceinte// "GetServiceInternalUrls"
0x225b2  ldarg.s  4
0x225b4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x225b9  ldloc.0
0x225ba  ldarg.3
0x225bb  ldarg.s  4
0x225bd  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.MicroService.MicroServiceManagerServerStub::GetServiceInternalUrls_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.MicroService.MicroServiceManager target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x225c2  ret
0x225c3  ldarg.s  5
0x225c5  ldc.i4.0
0x225c6  stind.i1
0x225c7  ldarg.0
0x225c8  ldstr    aAddmicroservic// "AddMicroserviceWorkItem"
0x225cd  ldarg.s  4
0x225cf  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x225d4  ldloc.0
0x225d5  ldarg.3
0x225d6  ldarg.s  4
0x225d8  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.MicroService.MicroServiceManagerServerStub::AddMicroserviceWorkItem_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.MicroService.MicroServiceManager target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x225dd  box      [mscorlib]System.Guid
0x225e2  ret
0x225e3  ldarg.s  5
0x225e5  ldc.i4.0
0x225e6  stind.i1
0x225e7  ldarg.0
0x225e8  ldstr    aDeletemicroser// "DeleteMicroserviceWorkItem"
0x225ed  ldarg.s  4
0x225ef  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x225f4  ldloc.0
0x225f5  ldarg.3
0x225f6  ldarg.s  4
0x225f8  call     bool Microsoft.SharePoint.MicroService.MicroServiceManagerServerStub::DeleteMicroserviceWorkItem_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.MicroService.MicroServiceManager target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x225fd  box      [mscorlib]System.Boolean
0x22602  ret
0x22603  ldarg.0
0x22604  ldarg.1
0x22605  ldarg.2
0x22606  ldarg.3
0x22607  ldarg.s  4
0x22609  ldarg.s  5
0x2260b  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x22610  ret
```
