# Microsoft.ReportingServices.Portal.WebHost.Owin.LocalRequestMiddleware::Invoke

- ea: `0x2860`
- end: `0x28a1`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.LocalRequestMiddleware::Invoke`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2860  ldloca.s 0
0x2862  ldarg.0
0x2863  stfld    class Microsoft.ReportingServices.Portal.WebHost.Owin.LocalRequestMiddleware <Invoke>d__1::<>4__this
0x2868  ldloca.s 0
0x286a  ldarg.1
0x286b  stfld    class [Microsoft.Owin]Microsoft.Owin.IOwinContext <Invoke>d__1::portalContext
0x2870  ldloca.s 0
0x2872  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::Create()
0x2877  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__1::<>t__builder
0x287c  ldloca.s 0
0x287e  ldc.i4.m1
0x287f  stfld    int32 <Invoke>d__1::<>1__state
0x2884  ldloc.0
0x2885  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__1::<>t__builder
0x288a  stloc.1
0x288b  ldloca.s 1
0x288d  ldloca.s 0
0x288f  call     T0x2B00000B
0x2894  ldloca.s 0
0x2896  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__1::<>t__builder
0x289b  call     instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::get_Task()
0x28a0  ret
```
