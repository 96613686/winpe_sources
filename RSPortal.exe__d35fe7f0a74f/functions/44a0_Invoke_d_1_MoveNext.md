# <Invoke>d__1::MoveNext

- ea: `0x44a0`
- end: `0x4556`
- name: `<Invoke>d__1::MoveNext`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x44a0`

## pseudocode

```c

```

## disassembly

```asm
0x44a0  ldarg.0
0x44a1  ldfld    int32 <Invoke>d__1::<>1__state
0x44a6  stloc.0
0x44a7  ldarg.0
0x44a8  ldfld    class Microsoft.ReportingServices.Portal.WebHost.Owin.LocalRequestMiddleware <Invoke>d__1::<>4__this
0x44ad  stloc.1
0x44ae  ldloc.0
0x44af  brfalse.s loc_4506
0x44b1  ldarg.0
0x44b2  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__1::portalContext
0x44b7  ldstr    aServerIslocal// "server.IsLocal"
0x44bc  callvirt T0x2B000020
0x44c1  call     void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.WebRequestUtil::DeclareClientRequestAsLocal(bool)
0x44c6  ldloc.1
0x44c7  call     instance class [Microsoft.Owin]Microsoft.Owin.OwinMiddleware [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::get_Next()
0x44cc  ldarg.0
0x44cd  ldfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__1::portalContext
0x44d2  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Owin]Microsoft.Owin.OwinMiddleware::Invoke(class [Microsoft.Owin]Microsoft.Owin.IOwinContext)
0x44d7  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x44dc  stloc.2
0x44dd  ldloca.s 2
0x44df  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x44e4  brtrue.s loc_4522
0x44e6  ldarg.0
0x44e7  ldc.i4.0
0x44e8  dup
0x44e9  stloc.0
0x44ea  stfld    int32 <Invoke>d__1::<>1__state
0x44ef  ldarg.0
0x44f0  ldloc.2
0x44f1  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Invoke>d__1::<>u__1
0x44f6  ldarg.0
0x44f7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__1::<>t__builder
0x44fc  ldloca.s 2
0x44fe  ldarg.0
0x44ff  call     T0x2B000021
0x4504  leave.s  loc_4555
0x4506  ldarg.0
0x4507  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Invoke>d__1::<>u__1
0x450c  stloc.2
0x450d  ldarg.0
0x450e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <Invoke>d__1::<>u__1
0x4513  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x4519  ldarg.0
0x451a  ldc.i4.m1
0x451b  dup
0x451c  stloc.0
0x451d  stfld    int32 <Invoke>d__1::<>1__state
0x4522  ldloca.s 2
0x4524  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x4529  leave.s  loc_4542
0x452b  stloc.3
0x452c  ldarg.0
0x452d  ldc.i4.s 0xFE
0x452f  stfld    int32 <Invoke>d__1::<>1__state
0x4534  ldarg.0
0x4535  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__1::<>t__builder
0x453a  ldloc.3
0x453b  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x4540  leave.s  loc_4555
0x4542  ldarg.0
0x4543  ldc.i4.s 0xFE
0x4545  stfld    int32 <Invoke>d__1::<>1__state
0x454a  ldarg.0
0x454b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__1::<>t__builder
0x4550  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x4555  ret
```
