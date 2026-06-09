# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::.ctor

- ea: `0x1130`
- end: `0x114e`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::.ctor`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1130  ldarg.0
0x1131  ldsfld   class [mscorlib]System.Random Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::Rng
0x1136  dup
0x1137  ldvirtftn instance int32 [mscorlib]System.Random::Next(int32)
0x113d  newobj   instance void class [mscorlib]System.Func`2<int32, int32>::.ctor(object, native int)
0x1142  stfld    class [mscorlib]System.Func`2<int32, int32> Microsoft.ReportingServices.Portal.WebHost.Services.Impl.LoggerScope::RandomNext
0x1147  ldarg.0
0x1148  call     instance void [mscorlib]System.Object::.ctor()
0x114d  ret
```
