# Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::Invoke

- ea: `0x21a0`
- end: `0x21e1`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware::Invoke`
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
0x21a0  ldloca.s 0
0x21a2  ldarg.0
0x21a3  stfld    class Microsoft.ReportingServices.Portal.WebHost.Owin.PortalCorsMiddleware <Invoke>d__5::<>4__this
0x21a8  ldloca.s 0
0x21aa  ldarg.1
0x21ab  stfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> <Invoke>d__5::environment
0x21b0  ldloca.s 0
0x21b2  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::Create()
0x21b7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__5::<>t__builder
0x21bc  ldloca.s 0
0x21be  ldc.i4.m1
0x21bf  stfld    int32 <Invoke>d__5::<>1__state
0x21c4  ldloc.0
0x21c5  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__5::<>t__builder
0x21ca  stloc.1
0x21cb  ldloca.s 1
0x21cd  ldloca.s 0
0x21cf  call     T0x2B000009
0x21d4  ldloca.s 0
0x21d6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Invoke>d__5::<>t__builder
0x21db  call     instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::get_Task()
0x21e0  ret
```
