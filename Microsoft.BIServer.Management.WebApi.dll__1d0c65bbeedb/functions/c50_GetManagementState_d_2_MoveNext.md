# <GetManagementState>d__2::MoveNext

- ea: `0xc50`
- end: `0xd32`
- name: `<GetManagementState>d__2::MoveNext`
- size: `226`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x7c0`
- `0xc50`

## pseudocode

```c

```

## disassembly

```asm
0xc50  ldarg.0
0xc51  ldfld    int32 <GetManagementState>d__2::<>1__state
0xc56  stloc.0
0xc57  ldarg.0
0xc58  ldfld    class Microsoft.BIServer.Management.WebApi.Controllers.StateController <GetManagementState>d__2::<>4__this
0xc5d  stloc.1
0xc5e  ldloc.0
0xc5f  brfalse.s loc_C82
0xc61  ldarg.0
0xc62  ldc.i4.2
0xc63  newarr   [mscorlib]System.String
0xc68  dup
0xc69  ldc.i4.0
0xc6a  ldstr    aGet// "GET"
0xc6f  stelem.ref
0xc70  dup
0xc71  ldc.i4.1
0xc72  ldstr    aManagementstat// "ManagementState"
0xc77  stelem.ref
0xc78  call     class [mscorlib]System.IDisposable [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[])
0xc7d  stfld    class [mscorlib]System.IDisposable <GetManagementState>d__2::<>7__wrap1
0xc82  nop
0xc83  ldloc.0
0xc84  brfalse.s loc_CBD
0xc86  ldloc.1
0xc87  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> Microsoft.BIServer.Management.WebApi.Controllers.StateController::ManagementStateInternal()
0xc8c  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::GetAwaiter()
0xc91  stloc.s  4
0xc93  ldloca.s 4
0xc95  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::get_IsCompleted()
0xc9a  brtrue.s loc_CDA
0xc9c  ldarg.0
0xc9d  ldc.i4.0
0xc9e  dup
0xc9f  stloc.0
0xca0  stfld    int32 <GetManagementState>d__2::<>1__state
0xca5  ldarg.0
0xca6  ldloc.s  4
0xca8  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <GetManagementState>d__2::<>u__1
0xcad  ldarg.0
0xcae  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetManagementState>d__2::<>t__builder
0xcb3  ldloca.s 4
0xcb5  ldarg.0
0xcb6  call     T0x2B00000D
0xcbb  leave.s  loc_D31
0xcbd  ldarg.0
0xcbe  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <GetManagementState>d__2::<>u__1
0xcc3  stloc.s  4
0xcc5  ldarg.0
0xcc6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState> <GetManagementState>d__2::<>u__1
0xccb  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>
0xcd1  ldarg.0
0xcd2  ldc.i4.m1
0xcd3  dup
0xcd4  stloc.0
0xcd5  stfld    int32 <GetManagementState>d__2::<>1__state
0xcda  ldloca.s 4
0xcdc  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ManagementState>::GetResult()
0xce1  stloc.3
0xce2  ldloc.1
0xce3  ldloc.3
0xce4  call     T0x2B00000C
0xce9  stloc.2
0xcea  leave.s  loc_D1D
0xcec  ldloc.0
0xced  ldc.i4.0
0xcee  bge.s    loc_D03
0xcf0  ldarg.0
0xcf1  ldfld    class [mscorlib]System.IDisposable <GetManagementState>d__2::<>7__wrap1
0xcf6  brfalse.s loc_D03
0xcf8  ldarg.0
0xcf9  ldfld    class [mscorlib]System.IDisposable <GetManagementState>d__2::<>7__wrap1
0xcfe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd03  endfinally
0xd04  stloc.s  5
0xd06  ldarg.0
0xd07  ldc.i4.s 0xFE
0xd09  stfld    int32 <GetManagementState>d__2::<>1__state
0xd0e  ldarg.0
0xd0f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetManagementState>d__2::<>t__builder
0xd14  ldloc.s  5
0xd16  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0xd1b  leave.s  loc_D31
0xd1d  ldarg.0
0xd1e  ldc.i4.s 0xFE
0xd20  stfld    int32 <GetManagementState>d__2::<>1__state
0xd25  ldarg.0
0xd26  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <GetManagementState>d__2::<>t__builder
0xd2b  ldloc.2
0xd2c  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0xd31  ret
```
