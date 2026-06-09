# <GetDbState>d__0::MoveNext

- ea: `0xb30`
- end: `0xc30`
- name: `<GetDbState>d__0::MoveNext`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x7c0`
- `0xb30`

## pseudocode

```c

```

## disassembly

```asm
0xb30  ldarg.0
0xb31  ldfld    int32 <GetDbState>d__0::<>1__state
0xb36  stloc.0
0xb37  ldarg.0
0xb38  ldfld    class Microsoft.BIServer.Management.WebApi.Controllers.StateController <GetDbState>d__0::<>4__this
0xb3d  stloc.1
0xb3e  ldloc.0
0xb3f  pop
0xb40  nop
0xb41  ldloc.0
0xb42  brfalse.s loc_B65
0xb44  ldarg.0
0xb45  ldc.i4.2
0xb46  newarr   [mscorlib]System.String
0xb4b  dup
0xb4c  ldc.i4.0
0xb4d  ldstr    aGet// "GET"
0xb52  stelem.ref
0xb53  dup
0xb54  ldc.i4.1
0xb55  ldstr    aDbstate// "DBState"
0xb5a  stelem.ref
0xb5b  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0xb60  stfld    class [mscorlib]System.IDisposable <GetDbState>d__0::<>7__wrap1
0xb65  nop
0xb66  ldloc.0
0xb67  brfalse.s loc_BA3
0xb69  ldloc.1
0xb6a  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> Microsoft.BIServer.Management.WebApi.Controllers.StateController::ManagementStateInternal()
0xb6f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::GetAwaiter()
0xb74  stloc.s  4
0xb76  ldloca.s 4
0xb78  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::get_IsCompleted()
0xb7d  brtrue.s loc_BC0
0xb7f  ldarg.0
0xb80  ldc.i4.0
0xb81  dup
0xb82  stloc.0
0xb83  stfld    int32 <GetDbState>d__0::<>1__state
0xb88  ldarg.0
0xb89  ldloc.s  4
0xb8b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <GetDbState>d__0::<>u__1
0xb90  ldarg.0
0xb91  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetDbState>d__0::<>t__builder
0xb96  ldloca.s 4
0xb98  ldarg.0
0xb99  call     T0x2B00000B
0xb9e  leave    loc_C2F
0xba3  ldarg.0
0xba4  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <GetDbState>d__0::<>u__1
0xba9  stloc.s  4
0xbab  ldarg.0
0xbac  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <GetDbState>d__0::<>u__1
0xbb1  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>
0xbb7  ldarg.0
0xbb8  ldc.i4.m1
0xbb9  dup
0xbba  stloc.0
0xbbb  stfld    int32 <GetDbState>d__0::<>1__state
0xbc0  ldloca.s 4
0xbc2  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::GetResult()
0xbc7  stloc.3
0xbc8  ldloc.1
0xbc9  ldloc.3
0xbca  call     T0x2B00000C
0xbcf  stloc.2
0xbd0  leave.s  loc_C1B
0xbd2  ldloc.0
0xbd3  ldc.i4.0
0xbd4  bge.s    loc_BE9
0xbd6  ldarg.0
0xbd7  ldfld    class [mscorlib]System.IDisposable <GetDbState>d__0::<>7__wrap1
0xbdc  brfalse.s loc_BE9
0xbde  ldarg.0
0xbdf  ldfld    class [mscorlib]System.IDisposable <GetDbState>d__0::<>7__wrap1
0xbe4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbe9  endfinally
0xbea  callvirt instance string [mscorlib]System.Exception::get_Message()
0xbef  call     T0x2B000002
0xbf4  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0xbf9  ldloc.1
0xbfa  callvirt instance class [System.Web.Http]System.Web.Http.Results.BadRequestResult [System.Web.Http]System.Web.Http.ApiController::BadRequest()
0xbff  stloc.2
0xc00  leave.s  loc_C1B
0xc02  stloc.s  5
0xc04  ldarg.0
0xc05  ldc.i4.s 0xFE
0xc07  stfld    int32 <GetDbState>d__0::<>1__state
0xc0c  ldarg.0
0xc0d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetDbState>d__0::<>t__builder
0xc12  ldloc.s  5
0xc14  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0xc19  leave.s  loc_C2F
0xc1b  ldarg.0
0xc1c  ldc.i4.s 0xFE
0xc1e  stfld    int32 <GetDbState>d__0::<>1__state
0xc23  ldarg.0
0xc24  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetDbState>d__0::<>t__builder
0xc29  ldloc.2
0xc2a  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0xc2f  ret
```
