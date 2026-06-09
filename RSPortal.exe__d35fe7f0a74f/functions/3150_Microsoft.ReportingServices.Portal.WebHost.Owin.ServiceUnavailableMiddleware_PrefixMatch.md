# Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::PrefixMatch

- ea: `0x3150`
- end: `0x3173`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.ServiceUnavailableMiddleware::PrefixMatch`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3120`

## callees

- `0x4580`

## pseudocode

```c

```

## disassembly

```asm
0x3150  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x3155  stloc.0
0x3156  ldloc.0
0x3157  ldarg.1
0x3158  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <>c__DisplayClass4_0::reportServerPrefixes
0x315d  ldarg.0
0x315e  ldloc.0
0x315f  ldftn    instance bool <>c__DisplayClass4_0::<PrefixMatch>b__0(string x)
0x3165  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x316a  call     T0x2B00000F
0x316f  ldc.i4.0
0x3170  ceq
0x3172  ret
```
