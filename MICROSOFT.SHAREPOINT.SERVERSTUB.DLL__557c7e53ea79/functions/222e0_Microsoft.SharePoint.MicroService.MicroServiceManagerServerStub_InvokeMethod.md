# Microsoft.SharePoint.MicroService.MicroServiceManagerServerStub::InvokeMethod

- ea: `0x222e0`
- end: `0x223d1`
- name: `Microsoft.SharePoint.MicroService.MicroServiceManagerServerStub::InvokeMethod`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x22240`
- `0x22260`
- `0x22280`
- `0x222c0`
- `0x222e0`

## string_xrefs

- `0x22318`: `GetServiceUrls`
- `0x22352`: `GetServiceUrls`
- `0x22325`: `GetServiceInternalUrls`
- `0x2236d`: `GetServiceInternalUrls`
- `0x22332`: `AddMicroserviceWorkItem`
- `0x22388`: `AddMicroserviceWorkItem`
- `0x2233f`: `DeleteMicroserviceWorkItem`
- `0x223a8`: `DeleteMicroserviceWorkItem`

## pseudocode

```c

```

## disassembly

```asm
0x222e0  ldarg.s  4
0x222e2  brtrue.s loc_222EF
0x222e4  ldstr    aProxycontext// "proxyContext"
0x222e9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x222ee  throw
0x222ef  ldarg.1
0x222f0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.MicroService.MicroServiceManager
0x222f5  stloc.0
0x222f6  ldloc.0
0x222f7  brtrue.s loc_22304
0x222f9  ldstr    aTarget// "target"
0x222fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x22303  throw
0x22304  ldarg.0
0x22305  ldarg.2
0x22306  ldarg.s  4
0x22308  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2230d  starg.s  2
0x2230f  ldarg.2
0x22310  dup
0x22311  stloc.1
0x22312  brfalse  loc_223C3
0x22317  ldloc.1
0x22318  ldstr    aGetserviceurls// "GetServiceUrls"
0x2231d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22322  brtrue.s loc_2234D
0x22324  ldloc.1
0x22325  ldstr    aGetserviceinte// "GetServiceInternalUrls"
0x2232a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2232f  brtrue.s loc_22368
0x22331  ldloc.1
0x22332  ldstr    aAddmicroservic// "AddMicroserviceWorkItem"
0x22337  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2233c  brtrue.s loc_22383
0x2233e  ldloc.1
0x2233f  ldstr    aDeletemicroser// "DeleteMicroserviceWorkItem"
0x22344  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22349  brtrue.s loc_223A3
0x2234b  br.s     loc_223C3
0x2234d  ldarg.s  5
0x2234f  ldc.i4.0
0x22350  stind.i1
0x22351  ldarg.0
0x22352  ldstr    aGetserviceurls// "GetServiceUrls"
0x22357  ldarg.s  4
0x22359  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x2235e  ldloc.0
0x2235f  ldarg.3
0x22360  ldarg.s  4
0x22362  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.MicroService.MicroServiceManagerServerStub::GetServiceUrls_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.MicroService.MicroServiceManager target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x22367  ret
0x22368  ldarg.s  5
0x2236a  ldc.i4.0
0x2236b  stind.i1
0x2236c  ldarg.0
0x2236d  ldstr    aGetserviceinte// "GetServiceInternalUrls"
0x22372  ldarg.s  4
0x22374  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x22379  ldloc.0
0x2237a  ldarg.3
0x2237b  ldarg.s  4
0x2237d  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.MicroService.MicroServiceManagerServerStub::GetServiceInternalUrls_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.MicroService.MicroServiceManager target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x22382  ret
0x22383  ldarg.s  5
0x22385  ldc.i4.0
0x22386  stind.i1
0x22387  ldarg.0
0x22388  ldstr    aAddmicroservic// "AddMicroserviceWorkItem"
0x2238d  ldarg.s  4
0x2238f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x22394  ldloc.0
0x22395  ldarg.3
0x22396  ldarg.s  4
0x22398  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.MicroService.MicroServiceManagerServerStub::AddMicroserviceWorkItem_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.MicroService.MicroServiceManager target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x2239d  box      [mscorlib]System.Guid
0x223a2  ret
0x223a3  ldarg.s  5
0x223a5  ldc.i4.0
0x223a6  stind.i1
0x223a7  ldarg.0
0x223a8  ldstr    aDeletemicroser// "DeleteMicroserviceWorkItem"
0x223ad  ldarg.s  4
0x223af  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x223b4  ldloc.0
0x223b5  ldarg.3
0x223b6  ldarg.s  4
0x223b8  call     bool Microsoft.SharePoint.MicroService.MicroServiceManagerServerStub::DeleteMicroserviceWorkItem_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.MicroService.MicroServiceManager target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x223bd  box      [mscorlib]System.Boolean
0x223c2  ret
0x223c3  ldarg.0
0x223c4  ldarg.1
0x223c5  ldarg.2
0x223c6  ldarg.3
0x223c7  ldarg.s  4
0x223c9  ldarg.s  5
0x223cb  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::InvokeMethod(object, string, class [System.Xml]System.Xml.XmlNodeList, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext, bool&)
0x223d0  ret
```
