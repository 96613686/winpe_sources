# Microsoft.BIServer.BIService.BIService::ServiceWatchdog

- ea: `0xc10`
- end: `0xc51`
- name: `Microsoft.BIServer.BIService.BIService::ServiceWatchdog`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xbb0`

## pseudocode

```c

```

## disassembly

```asm
0xc10  ldloca.s 0
0xc12  ldarg.0
0xc13  stfld    class Microsoft.BIServer.BIService.BIService <ServiceWatchdog>d__30::<>4__this
0xc18  ldloca.s 0
0xc1a  ldarg.1
0xc1b  stfld    valuetype [mscorlib]System.Threading.CancellationToken <ServiceWatchdog>d__30::cancellationToken
0xc20  ldloca.s 0
0xc22  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::Create()
0xc27  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ServiceWatchdog>d__30::<>t__builder
0xc2c  ldloca.s 0
0xc2e  ldc.i4.m1
0xc2f  stfld    int32 <ServiceWatchdog>d__30::<>1__state
0xc34  ldloc.0
0xc35  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ServiceWatchdog>d__30::<>t__builder
0xc3a  stloc.1
0xc3b  ldloca.s 1
0xc3d  ldloca.s 0
0xc3f  call     T0x2B000007
0xc44  ldloca.s 0
0xc46  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ServiceWatchdog>d__30::<>t__builder
0xc4b  call     instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::get_Task()
0xc50  ret
```
