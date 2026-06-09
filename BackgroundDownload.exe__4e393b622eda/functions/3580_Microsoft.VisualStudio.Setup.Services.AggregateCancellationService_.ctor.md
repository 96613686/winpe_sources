# Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::.ctor

- ea: `0x3580`
- end: `0x35c8`
- name: `Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::.ctor`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x4de0`

## callees

- `0x3580`

## pseudocode

```c

```

## disassembly

```asm
0x3580  ldarg.0
0x3581  ldarg.1
0x3582  stfld    class Microsoft.VisualStudio.Setup.Services.ICancellationService[] Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::<cancellationServices>P
0x3587  ldarg.0
0x3588  ldarg.0
0x3589  ldfld    class Microsoft.VisualStudio.Setup.Services.ICancellationService[] Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::<cancellationServices>P
0x358e  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Services.ICancellationService, valuetype [mscorlib]System.Threading.CancellationToken> <>c::<>9__0_0
0x3593  dup
0x3594  brtrue.s loc_35AD
0x3596  pop
0x3597  ldsfld   class <>c <>c::<>9
0x359c  ldftn    instance valuetype [mscorlib]System.Threading.CancellationToken <>c::<.ctor>b__0_0(class Microsoft.VisualStudio.Setup.Services.ICancellationService s)
0x35a2  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Services.ICancellationService, valuetype [mscorlib]System.Threading.CancellationToken>::.ctor(object, native int)
0x35a7  dup
0x35a8  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Services.ICancellationService, valuetype [mscorlib]System.Threading.CancellationToken> <>c::<>9__0_0
0x35ad  call     T0x2B000043
0x35b2  call     T0x2B000044
0x35b7  call     class [mscorlib]System.Threading.CancellationTokenSource [mscorlib]System.Threading.CancellationTokenSource::CreateLinkedTokenSource(valuetype [mscorlib]System.Threading.CancellationToken[])
0x35bc  stfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Services.AggregateCancellationService::cancellationTokenSource
0x35c1  ldarg.0
0x35c2  call     instance void [mscorlib]System.Object::.ctor()
0x35c7  ret
```
