# <Invoke>d__5::MoveNext

- ea: `0x41f0`
- end: `0x443c`
- name: `<Invoke>d__5::MoveNext`
- size: `588`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x21f0`
- `0x2220`
- `0x2330`
- `0x41f0`

## pseudocode

```c

```

## disassembly

```asm
0x41f0  ldarg.0
0x41f1  ldfld    int32 <Invoke>d__5::<>1__state
0x41f6  stloc.0
0x41f7  ldarg.0
0x41f8  ldfld    class Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware <Invoke>d__5::<>4__this
0x41fd  stloc.1
0x41fe  ldloc.0
0x41ff  switch   loc_4288, loc_4311, loc_4381, loc_43E9
0x4214  ldarg.0
0x4215  ldarg.0
0x4216  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> <Invoke>d__5::environment
0x421b  newobj   instance void [Microsoft.Owin]Microsoft.Owin.OwinContext::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>)
0x4220  stfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__5::<context>5__2
0x4225  ldarg.0
0x4226  ldarg.0
0x4227  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__5::<context>5__2
0x422c  call     class [System.Web.Cors]System.Web.Cors.CorsRequestContext Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::GetCorsRequestContext(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context)
0x4231  stfld    class [System.Web.Cors]System.Web.Cors.CorsRequestContext <Invoke>d__5::<corsRequestContext>5__3
0x4236  ldnull
0x4237  stloc.2
0x4238  ldarg.0
0x4239  ldfld    class [System.Web.Cors]System.Web.Cors.CorsRequestContext <Invoke>d__5::<corsRequestContext>5__3
0x423e  brfalse.s loc_42AC
0x4240  ldloc.1
0x4241  ldfld    class [Microsoft.Owin.Cors]Microsoft.Owin.Cors.ICorsPolicyProvider Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::_corsPolicyProvider
0x4246  ldarg.0
0x4247  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__5::<context>5__2
0x424c  callvirt instance class [Microsoft.Owin]Microsoft.Owin.IOwinRequest [Microsoft.Owin]Microsoft.Owin.IOwinContext::get_Request()
0x4251  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Web.Cors]System.Web.Cors.CorsPolicy> [Microsoft.Owin.Cors]Microsoft.Owin.Cors.ICorsPolicyProvider::GetCorsPolicyAsync(class [Microsoft.Owin]Microsoft.Owin.IOwinRequest)
0x4256  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Web.Cors]System.Web.Cors.CorsPolicy>::GetAwaiter()
0x425b  stloc.3
0x425c  ldloca.s 3
0x425e  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Cors]System.Web.Cors.CorsPolicy>::get_IsCompleted()
0x4263  brtrue.s loc_42A4
0x4265  ldarg.0
0x4266  ldc.i4.0
0x4267  dup
0x4268  stloc.0
0x4269  stfld    int32 <Invoke>d__5::<>1__state
0x426e  ldarg.0
0x426f  ldloc.3
0x4270  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Cors]System.Web.Cors.CorsPolicy> <Invoke>d__5::<>u__1
0x4275  ldarg.0
0x4276  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__5::<>t__builder
0x427b  ldloca.s 3
0x427d  ldarg.0
0x427e  call     T0x2B00001E
0x4283  leave    loc_443B
0x4288  ldarg.0
0x4289  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Cors]System.Web.Cors.CorsPolicy> <Invoke>d__5::<>u__1
0x428e  stloc.3
0x428f  ldarg.0
0x4290  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Cors]System.Web.Cors.CorsPolicy> <Invoke>d__5::<>u__1
0x4295  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Cors]System.Web.Cors.CorsPolicy>
0x429b  ldarg.0
0x429c  ldc.i4.m1
0x429d  dup
0x429e  stloc.0
0x429f  stfld    int32 <Invoke>d__5::<>1__state
0x42a4  ldloca.s 3
0x42a6  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Web.Cors]System.Web.Cors.CorsPolicy>::GetResult()
0x42ab  stloc.2
0x42ac  ldloc.2
0x42ad  brfalse  loc_43A7
0x42b2  ldarg.0
0x42b3  ldfld    class [System.Web.Cors]System.Web.Cors.CorsRequestContext <Invoke>d__5::<corsRequestContext>5__3
0x42b8  brfalse  loc_43A7
0x42bd  ldarg.0
0x42be  ldfld    class [System.Web.Cors]System.Web.Cors.CorsRequestContext <Invoke>d__5::<corsRequestContext>5__3
0x42c3  callvirt instance bool [System.Web.Cors]System.Web.Cors.CorsRequestContext::get_IsPreflight()
0x42c8  brfalse.s loc_433A
0x42ca  ldloc.1
0x42cb  ldarg.0
0x42cc  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__5::<context>5__2
0x42d1  ldloc.2
0x42d2  ldarg.0
0x42d3  ldfld    class [System.Web.Cors]System.Web.Cors.CorsRequestContext <Invoke>d__5::<corsRequestContext>5__3
0x42d8  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::HandleCorsPreflightRequestAsync(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context, class [System.Web.Cors]System.Web.Cors.CorsPolicy policy, class [System.Web.Cors]System.Web.Cors.CorsRequestContext corsRequestContext)
0x42dd  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x42e2  stloc.s  4
0x42e4  ldloca.s 4
0x42e6  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x42eb  brtrue.s loc_432E
0x42ed  ldarg.0
0x42ee  ldc.i4.1
0x42ef  dup
0x42f0  stloc.0
0x42f1  stfld    int32 <Invoke>d__5::<>1__state
0x42f6  ldarg.0
0x42f7  ldloc.s  4
0x42f9  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Invoke>d__5::<>u__2
0x42fe  ldarg.0
0x42ff  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__5::<>t__builder
0x4304  ldloca.s 4
0x4306  ldarg.0
0x4307  call     T0x2B00001F
0x430c  leave    loc_443B
0x4311  ldarg.0
0x4312  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Invoke>d__5::<>u__2
0x4317  stloc.s  4
0x4319  ldarg.0
0x431a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Invoke>d__5::<>u__2
0x431f  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x4325  ldarg.0
0x4326  ldc.i4.m1
0x4327  dup
0x4328  stloc.0
0x4329  stfld    int32 <Invoke>d__5::<>1__state
0x432e  ldloca.s 4
0x4330  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x4335  br       loc_440D
0x433a  ldloc.1
0x433b  ldarg.0
0x433c  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__5::<context>5__2
0x4341  ldloc.2
0x4342  ldarg.0
0x4343  ldfld    class [System.Web.Cors]System.Web.Cors.CorsRequestContext <Invoke>d__5::<corsRequestContext>5__3
0x4348  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::HandleCorsRequestAsync(class [Microsoft.Owin]Microsoft.Owin.IOwinContext context, class [System.Web.Cors]System.Web.Cors.CorsPolicy policy, class [System.Web.Cors]System.Web.Cors.CorsRequestContext corsRequestContext)
0x434d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x4352  stloc.s  4
0x4354  ldloca.s 4
0x4356  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x435b  brtrue.s loc_439E
0x435d  ldarg.0
0x435e  ldc.i4.2
0x435f  dup
0x4360  stloc.0
0x4361  stfld    int32 <Invoke>d__5::<>1__state
0x4366  ldarg.0
0x4367  ldloc.s  4
0x4369  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Invoke>d__5::<>u__2
0x436e  ldarg.0
0x436f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__5::<>t__builder
0x4374  ldloca.s 4
0x4376  ldarg.0
0x4377  call     T0x2B00001F
0x437c  leave    loc_443B
0x4381  ldarg.0
0x4382  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Invoke>d__5::<>u__2
0x4387  stloc.s  4
0x4389  ldarg.0
0x438a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Invoke>d__5::<>u__2
0x438f  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x4395  ldarg.0
0x4396  ldc.i4.m1
0x4397  dup
0x4398  stloc.0
0x4399  stfld    int32 <Invoke>d__5::<>1__state
0x439e  ldloca.s 4
0x43a0  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x43a5  br.s     loc_440D
0x43a7  ldloc.1
0x43a8  ldfld    class [mscorlib]System.Func`2<class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Threading.Tasks.Task> Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::_next
0x43ad  ldarg.0
0x43ae  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> <Invoke>d__5::environment
0x43b3  callvirt instance var<u1> class [mscorlib]System.Func`2<class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Threading.Tasks.Task>::Invoke(void)
0x43b8  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x43bd  stloc.s  4
0x43bf  ldloca.s 4
0x43c1  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x43c6  brtrue.s loc_4406
0x43c8  ldarg.0
0x43c9  ldc.i4.3
0x43ca  dup
0x43cb  stloc.0
0x43cc  stfld    int32 <Invoke>d__5::<>1__state
0x43d1  ldarg.0
0x43d2  ldloc.s  4
0x43d4  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Invoke>d__5::<>u__2
0x43d9  ldarg.0
0x43da  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__5::<>t__builder
0x43df  ldloca.s 4
0x43e1  ldarg.0
0x43e2  call     T0x2B00001F
0x43e7  leave.s  loc_443B
0x43e9  ldarg.0
0x43ea  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Invoke>d__5::<>u__2
0x43ef  stloc.s  4
0x43f1  ldarg.0
0x43f2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Invoke>d__5::<>u__2
0x43f7  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x43fd  ldarg.0
0x43fe  ldc.i4.m1
0x43ff  dup
0x4400  stloc.0
0x4401  stfld    int32 <Invoke>d__5::<>1__state
0x4406  ldloca.s 4
0x4408  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x440d  leave.s  loc_4428
0x440f  stloc.s  5
0x4411  ldarg.0
0x4412  ldc.i4.s 0xFE
0x4414  stfld    int32 <Invoke>d__5::<>1__state
0x4419  ldarg.0
0x441a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__5::<>t__builder
0x441f  ldloc.s  5
0x4421  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x4426  leave.s  loc_443B
0x4428  ldarg.0
0x4429  ldc.i4.s 0xFE
0x442b  stfld    int32 <Invoke>d__5::<>1__state
0x4430  ldarg.0
0x4431  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__5::<>t__builder
0x4436  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x443b  ret
```
