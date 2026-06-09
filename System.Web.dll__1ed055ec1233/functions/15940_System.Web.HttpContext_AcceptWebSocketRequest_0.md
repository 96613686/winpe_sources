# System.Web.HttpContext::AcceptWebSocketRequest_0

- ea: `0x15940`
- end: `0x15aea`
- name: `System.Web.HttpContext::AcceptWebSocketRequest_0`
- size: `426`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x4750`
- `0x15930`

## callees

- `0x8460`
- `0x86e0`
- `0x157f0`
- `0x15880`
- `0x158d0`
- `0x15940`
- `0x15af0`
- `0x16350`
- `0x16960`
- `0x17370`
- `0x18990`
- `0x189e0`
- `0x1f6e0`
- `0x1fe20`
- `0x34f20`
- `0x34fa0`
- `0x4d7a0`
- `0x4d7c0`
- `0x4df70`
- `0x50410`
- `0x164f40`

## string_xrefs

- `0x159a2`: `WebSockets_CannotBeCalledDuringBeginRequest`
- `0x15abe`: `Sec-WebSocket-Protocol`
- `0x159d7`: `WebSockets_CannotBeCalledDuringChildExecute`
- `0x15a7c`: `WebSockets_SubProtocolCannotBeNegotiated`

## pseudocode

```c

```

## disassembly

```asm
0x15940  ldarg.1
0x15941  brtrue.s loc_1594E
0x15943  ldstr    aUserfunc// "userFunc"
0x15948  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1594d  throw
0x1594e  ldarg.0
0x1594f  call     instance bool System.Web.HttpContext::get_IsWebSocketRequestUpgrading()
0x15954  brfalse.s loc_15966
0x15956  ldstr    aWebsocketsAcce// "WebSockets_AcceptWebSocketRequestCanOnl"...
0x1595b  call     string System.Web.SR::GetString(string name)
0x15960  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x15965  throw
0x15966  call     void System.Web.Util.SynchronizationContextUtil::ValidateModeForWebSockets()
0x1596b  ldarg.0
0x1596c  call     instance valuetype WebSocketInitStatus System.Web.HttpContext::GetWebSocketInitStatus()
0x15971  stloc.2
0x15972  ldloc.2
0x15973  switch   loc_159F7, loc_15992, loc_159A2, loc_159B2, loc_159C2, loc_159D7
0x15990  br.s     loc_159E7
0x15992  ldstr    aRequiresIisInt// "Requires_Iis_Integrated_Mode"
0x15997  call     string System.Web.SR::GetString(string name)
0x1599c  newobj   instance void [mscorlib]System.PlatformNotSupportedException::.ctor(string)
0x159a1  throw
0x159a2  ldstr    aWebsocketsCann// "WebSockets_CannotBeCalledDuringBeginReq"...
0x159a7  call     string System.Web.SR::GetString(string name)
0x159ac  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x159b1  throw
0x159b2  ldstr    aWebsocketsWebs// "WebSockets_WebSocketModuleNotEnabled"
0x159b7  call     string System.Web.SR::GetString(string name)
0x159bc  newobj   instance void [mscorlib]System.PlatformNotSupportedException::.ctor(string)
0x159c1  throw
0x159c2  ldc.i4   0x190
0x159c7  ldstr    aWebsocketsNota// "WebSockets_NotAWebSocketRequest"
0x159cc  call     string System.Web.SR::GetString(string name)
0x159d1  newobj   instance void System.Web.HttpException::.ctor(int32 httpCode, string message)
0x159d6  throw
0x159d7  ldstr    aWebsocketsCann_0// "WebSockets_CannotBeCalledDuringChildExe"...
0x159dc  call     string System.Web.SR::GetString(string name)
0x159e1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x159e6  throw
0x159e7  ldstr    aWebsocketsUnkn// "WebSockets_UnknownErrorWhileAccepting"
0x159ec  call     string System.Web.SR::GetString(string name)
0x159f1  newobj   instance void System.Web.HttpException::.ctor(string message)
0x159f6  throw
0x159f7  ldarg.0
0x159f8  call     instance valuetype System.Web.RequestNotification System.Web.HttpContext::get_CurrentNotification()
0x159fd  ldc.i4   0x80
0x15a02  ble.s    loc_15A14
0x15a04  ldstr    aWebsocketsCann_1// "WebSockets_CannotBeCalledAfterHandlerEx"...
0x15a09  call     string System.Web.SR::GetString(string name)
0x15a0e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x15a13  throw
0x15a14  ldarg.0
0x15a15  ldfld    class System.Web.HttpWorkerRequest System.Web.HttpContext::_wr
0x15a1a  castclass System.Web.Hosting.IIS7WorkerRequest
0x15a1f  stloc.0
0x15a20  ldarg.2
0x15a21  brfalse.s loc_15A48
0x15a23  ldarg.2
0x15a24  callvirt instance bool System.Web.WebSockets.AspNetWebSocketOptions::get_RequireSameOrigin()
0x15a29  brfalse.s loc_15A48
0x15a2b  ldloc.0
0x15a2c  call     bool System.Web.WebSockets.WebSocketUtil::IsSameOriginRequest(class System.Web.HttpWorkerRequest workerRequest)
0x15a31  brtrue.s loc_15A48
0x15a33  ldc.i4   0x193
0x15a38  ldstr    aWebsocketsOrig// "WebSockets_OriginCheckFailed"
0x15a3d  call     string System.Web.SR::GetString(string name)
0x15a42  newobj   instance void System.Web.HttpException::.ctor(int32 httpCode, string message)
0x15a47  throw
0x15a48  ldnull
0x15a49  stloc.1
0x15a4a  ldarg.2
0x15a4b  brfalse.s loc_15A61
0x15a4d  ldarg.2
0x15a4e  callvirt instance string System.Web.WebSockets.AspNetWebSocketOptions::get_SubProtocol()
0x15a53  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15a58  brtrue.s loc_15A61
0x15a5a  ldarg.2
0x15a5b  callvirt instance string System.Web.WebSockets.AspNetWebSocketOptions::get_SubProtocol()
0x15a60  stloc.1
0x15a61  ldloc.1
0x15a62  brfalse.s loc_15A9B
0x15a64  ldarg.0
0x15a65  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> System.Web.HttpContext::get_WebSocketRequestedProtocols()
0x15a6a  stloc.3
0x15a6b  ldloc.3
0x15a6c  brfalse.s loc_15A7C
0x15a6e  ldloc.3
0x15a6f  ldloc.1
0x15a70  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_Ordinal()
0x15a75  call     T0x2B000027
0x15a7a  brtrue.s loc_15A9B
0x15a7c  ldstr    aWebsocketsSubp// "WebSockets_SubProtocolCannotBeNegotiate"...
0x15a81  ldc.i4.1
0x15a82  newarr   [mscorlib]System.Object
0x15a87  dup
0x15a88  ldc.i4.0
0x15a89  ldloc.1
0x15a8a  stelem.ref
0x15a8b  call     string System.Web.SR::GetString(string name, object[] args)
0x15a90  ldstr    aOptions// "options"
0x15a95  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x15a9a  throw
0x15a9b  ldloc.0
0x15a9c  callvirt instance void System.Web.Hosting.IIS7WorkerRequest::AcceptWebSocket()
0x15aa1  ldarg.0
0x15aa2  ldc.i4.1
0x15aa3  call     instance void System.Web.HttpContext::TransitionToWebSocketState(valuetype System.Web.WebSocketTransitionState newState)
0x15aa8  ldarg.0
0x15aa9  call     instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x15aae  ldc.i4.s 0x65
0x15ab0  callvirt instance void System.Web.HttpResponse::set_StatusCode(int32 value)
0x15ab5  ldloc.1
0x15ab6  brfalse.s loc_15AD0
0x15ab8  ldarg.0
0x15ab9  call     instance class System.Web.HttpResponse System.Web.HttpContext::get_Response()
0x15abe  ldstr    aSecWebsocketPr// "Sec-WebSocket-Protocol"
0x15ac3  ldloc.1
0x15ac4  callvirt instance void System.Web.HttpResponse::AppendHeader(string name, string value)
0x15ac9  ldarg.0
0x15aca  ldloc.1
0x15acb  stfld    string System.Web.HttpContext::_webSocketNegotiatedProtocol
0x15ad0  ldarg.0
0x15ad1  call     instance class System.Web.RootedObjects System.Web.HttpContext::get_RootedObjects()
0x15ad6  ldarg.0
0x15ad7  call     instance class System.Web.RootedObjects System.Web.HttpContext::get_RootedObjects()
0x15adc  ldarg.0
0x15add  ldarg.1
0x15ade  ldloc.1
0x15adf  newobj   instance void System.Web.WebSocketPipeline::.ctor(class System.Web.RootedObjects root, class System.Web.HttpContext httpContext, class [mscorlib]System.Func`2<class System.Web.WebSockets.AspNetWebSocketContext, class [mscorlib]System.Threading.Tasks.Task> userFunc, string subProtocol)
0x15ae4  callvirt instance void System.Web.RootedObjects::set_WebSocketPipeline(class System.Web.WebSocketPipeline value)
0x15ae9  ret
```
