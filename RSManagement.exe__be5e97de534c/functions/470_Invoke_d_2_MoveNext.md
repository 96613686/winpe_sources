# <Invoke>d__2::MoveNext

- ea: `0x470`
- end: `0x837`
- name: `<Invoke>d__2::MoveNext`
- size: `967`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x270`
- `0x470`

## string_xrefs

- `0x522`: `User-Agent`

## pseudocode

```c

```

## disassembly

```asm
0x470  ldarg.0
0x471  ldfld    int32 <Invoke>d__2::<>1__state
0x476  stloc.0
0x477  ldarg.0
0x478  ldfld    class Microsoft.BIServer.Management.WebHost.RequestLoggingMiddleWare <Invoke>d__2::<>4__this
0x47d  stloc.1
0x47e  ldloc.0
0x47f  brfalse.s loc_4D0
0x481  ldarg.0
0x482  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x487  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x48c  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Method()
0x491  stloc.2
0x492  ldarg.0
0x493  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x498  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x49d  callvirt instance valuetype [Microsoft.Owin]Microsoft.Owin.PathString [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Path()
0x4a2  stloc.3
0x4a3  ldarg.0
0x4a4  ldc.i4.3
0x4a5  newarr   [mscorlib]System.String
0x4aa  dup
0x4ab  ldc.i4.0
0x4ac  ldstr    aOwin// "owin"
0x4b1  stelem.ref
0x4b2  dup
0x4b3  ldc.i4.1
0x4b4  ldloc.2
0x4b5  stelem.ref
0x4b6  dup
0x4b7  ldc.i4.2
0x4b8  ldloca.s 3
0x4ba  constrained. [Microsoft.Owin]Microsoft.Owin.PathString
0x4c0  callvirt instance string [mscorlib]System.Object::ToString()
0x4c5  stelem.ref
0x4c6  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0x4cb  stfld    class [mscorlib]System.IDisposable <Invoke>d__2::<>7__wrap1
0x4d0  nop
0x4d1  ldloc.0
0x4d2  brfalse  loc_5C9
0x4d7  ldarg.0
0x4d8  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x4dd  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x4e2  ldstr    aRequestid// "RequestId"
0x4e7  call     string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.IOwinRequestExtensions::GetHeaderValue(class [Microsoft.Owin]Microsoft.Owin.IOwinRequest, string)
0x4ec  stloc.s  4
0x4ee  ldloc.s  4
0x4f0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f5  brfalse.s loc_517
0x4f7  ldstr    aS0// "s_{0}"
0x4fc  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x501  stloc.s  7
0x503  ldloca.s 7
0x505  constrained. [mscorlib]System.Guid
0x50b  callvirt instance string [mscorlib]System.Object::ToString()
0x510  call     string [mscorlib]System.String::Format(string, object)
0x515  stloc.s  4
0x517  ldarg.0
0x518  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x51d  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x522  ldstr    aUserAgent// "User-Agent"
0x527  call     string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.IOwinRequestExtensions::GetHeaderValue(class [Microsoft.Owin]Microsoft.Owin.IOwinRequest, string)
0x52c  call     string [System]System.Net.WebUtility::UrlDecode(string)
0x531  stloc.s  5
0x533  ldloc.s  4
0x535  ldarg.0
0x536  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x53b  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x540  ldstr    aXSsrsClientses// "X-SSRS-ClientSessionId"
0x545  call     string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.IOwinRequestExtensions::GetHeaderValue(class [Microsoft.Owin]Microsoft.Owin.IOwinRequest, string)
0x54a  ldloc.s  5
0x54c  ldstr    aPowerBi// "Power BI"
0x551  callvirt instance bool [mscorlib]System.String::Contains(string)
0x556  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext::.ctor(string, string, bool)
0x55b  stloc.s  6
0x55d  ldarg.0
0x55e  ldsfld   string [mscorlib]System.String::Empty
0x563  stfld    string <Invoke>d__2::<user>5__3
0x568  ldarg.0
0x569  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x56e  callvirt instance class [Microsoft.Owin]Microsoft.Owin.Security.IAuthenticationManager [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Authentication()
0x573  brfalse.s loc_5BE
0x575  ldarg.0
0x576  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x57b  callvirt instance class [Microsoft.Owin]Microsoft.Owin.Security.IAuthenticationManager [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Authentication()
0x580  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Owin]Microsoft.Owin.Security.IAuthenticationManager::get_User()
0x585  brfalse.s loc_5BE
0x587  ldarg.0
0x588  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x58d  callvirt instance class [Microsoft.Owin]Microsoft.Owin.Security.IAuthenticationManager [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Authentication()
0x592  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Owin]Microsoft.Owin.Security.IAuthenticationManager::get_User()
0x597  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0x59c  brfalse.s loc_5BE
0x59e  ldarg.0
0x59f  ldarg.0
0x5a0  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x5a5  callvirt instance class [Microsoft.Owin]Microsoft.Owin.Security.IAuthenticationManager [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Authentication()
0x5aa  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Owin]Microsoft.Owin.Security.IAuthenticationManager::get_User()
0x5af  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0x5b4  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x5b9  stfld    string <Invoke>d__2::<user>5__3
0x5be  ldarg.0
0x5bf  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x5c4  stfld    class [System]System.Diagnostics.Stopwatch <Invoke>d__2::<stopwatch>5__4
0x5c9  nop
0x5ca  ldloc.0
0x5cb  brfalse  loc_667
0x5d0  ldloc.s  6
0x5d2  callvirt instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Request.RequestContext::SaveOnCallContext()
0x5d7  ldloc.1
0x5d8  ldarg.0
0x5d9  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x5de  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x5e3  ldstr    aReceivedReques// "Received request {0} {1} {2}"
0x5e8  ldc.i4.3
0x5e9  newarr   [mscorlib]System.Object
0x5ee  dup
0x5ef  ldc.i4.0
0x5f0  ldarg.0
0x5f1  ldfld    string <Invoke>d__2::<user>5__3
0x5f6  stelem.ref
0x5f7  dup
0x5f8  ldc.i4.1
0x5f9  ldarg.0
0x5fa  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x5ff  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x604  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Method()
0x609  stelem.ref
0x60a  dup
0x60b  ldc.i4.2
0x60c  ldarg.0
0x60d  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x612  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x617  callvirt instance class [System]System.Uri [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Uri()
0x61c  stelem.ref
0x61d  call     instance void Microsoft.BIServer.Management.WebHost.RequestLoggingMiddleWare::Log(class [Microsoft.Owin]Microsoft.Owin.IOwinRequest request, string formatString, object[] formatParams)
0x622  ldloc.1
0x623  call     instance class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::get_Next()
0x628  ldarg.0
0x629  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x62e  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::Invoke(class [Microsoft.Owin]Microsoft.Owin.IOwinContext)
0x633  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x638  stloc.s  8
0x63a  ldloca.s 8
0x63c  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x641  brtrue.s loc_684
0x643  ldarg.0
0x644  ldc.i4.0
0x645  dup
0x646  stloc.0
0x647  stfld    int32 <Invoke>d__2::<>1__state
0x64c  ldarg.0
0x64d  ldloc.s  8
0x64f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Invoke>d__2::<>u__1
0x654  ldarg.0
0x655  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__2::<>t__builder
0x65a  ldloca.s 8
0x65c  ldarg.0
0x65d  call     T0x2B000004
0x662  leave    loc_836
0x667  ldarg.0
0x668  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Invoke>d__2::<>u__1
0x66d  stloc.s  8
0x66f  ldarg.0
0x670  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Invoke>d__2::<>u__1
0x675  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x67b  ldarg.0
0x67c  ldc.i4.m1
0x67d  dup
0x67e  stloc.0
0x67f  stfld    int32 <Invoke>d__2::<>1__state
0x684  ldloca.s 8
0x686  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x68b  ldarg.0
0x68c  ldfld    class [System]System.Diagnostics.Stopwatch <Invoke>d__2::<stopwatch>5__4
0x691  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x696  ldloc.1
0x697  ldarg.0
0x698  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x69d  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x6a2  ldstr    aSendingRespons// "Sending response. Response code {0} {1}"...
0x6a7  ldc.i4.3
0x6a8  newarr   [mscorlib]System.Object
0x6ad  dup
0x6ae  ldc.i4.0
0x6af  ldarg.0
0x6b0  ldfld    string <Invoke>d__2::<user>5__3
0x6b5  stelem.ref
0x6b6  dup
0x6b7  ldc.i4.1
0x6b8  ldarg.0
0x6b9  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x6be  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinResponse [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Response()
0x6c3  callvirt instance int32 [Microsoft.Owin]Microsoft.Owin.IOwinResponse::get_StatusCode()
0x6c8  box      [mscorlib]System.Int32
0x6cd  stelem.ref
0x6ce  dup
0x6cf  ldc.i4.2
0x6d0  ldarg.0
0x6d1  ldfld    class [System]System.Diagnostics.Stopwatch <Invoke>d__2::<stopwatch>5__4
0x6d6  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x6db  box      [mscorlib]System.TimeSpan
0x6e0  stelem.ref
0x6e1  call     instance void Microsoft.BIServer.Management.WebHost.RequestLoggingMiddleWare::Log(class [Microsoft.Owin]Microsoft.Owin.IOwinRequest request, string formatString, object[] formatParams)
0x6e6  leave    loc_7D9
0x6eb  ldarg.0
0x6ec  ldfld    class [System]System.Diagnostics.Stopwatch <Invoke>d__2::<stopwatch>5__4
0x6f1  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x6f6  ldstr    a04123GConnecti// "{0} {4}: {1} {2} - {3:g}\r\nConnection "...
0x6fb  ldc.i4.5
0x6fc  newarr   [mscorlib]System.Object
0x701  dup
0x702  ldc.i4.0
0x703  ldarg.0
0x704  ldfld    string <Invoke>d__2::<user>5__3
0x709  stelem.ref
0x70a  dup
0x70b  ldc.i4.1
0x70c  ldarg.0
0x70d  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x712  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x717  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Method()
0x71c  stelem.ref
0x71d  dup
0x71e  ldc.i4.2
0x71f  ldarg.0
0x720  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x725  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x72a  callvirt instance valuetype [Microsoft.Owin]Microsoft.Owin.PathString [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Path()
0x72f  box      [Microsoft.Owin]Microsoft.Owin.PathString
0x734  stelem.ref
0x735  dup
0x736  ldc.i4.3
0x737  ldarg.0
0x738  ldfld    class [System]System.Diagnostics.Stopwatch <Invoke>d__2::<stopwatch>5__4
0x73d  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x742  box      [mscorlib]System.TimeSpan
0x747  stelem.ref
0x748  dup
0x749  ldc.i4.4
0x74a  ldarg.0
0x74b  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x750  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x755  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_RemoteIpAddress()
0x75a  stelem.ref
0x75b  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(class [mscorlib]System.Exception, string, object[])
0x760  leave.s  loc_7D9
0x762  ldarg.0
0x763  ldfld    class [System]System.Diagnostics.Stopwatch <Invoke>d__2::<stopwatch>5__4
0x768  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x76d  ldstr    a04123GExceptio// "{0} {4}: {1} {2} - {3:g}\r\nException"
0x772  ldc.i4.5
0x773  newarr   [mscorlib]System.Object
0x778  dup
0x779  ldc.i4.0
0x77a  ldarg.0
0x77b  ldfld    string <Invoke>d__2::<user>5__3
0x780  stelem.ref
0x781  dup
0x782  ldc.i4.1
0x783  ldarg.0
0x784  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x789  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x78e  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Method()
0x793  stelem.ref
0x794  dup
0x795  ldc.i4.2
0x796  ldarg.0
0x797  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x79c  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x7a1  callvirt instance valuetype [Microsoft.Owin]Microsoft.Owin.PathString [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_Path()
0x7a6  box      [Microsoft.Owin]Microsoft.Owin.PathString
0x7ab  stelem.ref
0x7ac  dup
0x7ad  ldc.i4.3
0x7ae  ldarg.0
0x7af  ldfld    class [System]System.Diagnostics.Stopwatch <Invoke>d__2::<stopwatch>5__4
0x7b4  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x7b9  box      [mscorlib]System.TimeSpan
0x7be  stelem.ref
0x7bf  dup
0x7c0  ldc.i4.4
0x7c1  ldarg.0
0x7c2  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__2::context
0x7c7  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x7cc  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IOwinRequest::get_RemoteIpAddress()
0x7d1  stelem.ref
0x7d2  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(class [mscorlib]System.Exception, string, object[])
0x7d7  rethrow
0x7d9  ldarg.0
0x7da  ldnull
0x7db  stfld    string <Invoke>d__2::<user>5__3
0x7e0  ldarg.0
0x7e1  ldnull
0x7e2  stfld    class [System]System.Diagnostics.Stopwatch <Invoke>d__2::<stopwatch>5__4
0x7e7  leave.s  loc_801
0x7e9  ldloc.0
0x7ea  ldc.i4.0
0x7eb  bge.s    loc_800
0x7ed  ldarg.0
  ... truncated ...
```
