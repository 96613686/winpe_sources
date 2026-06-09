# Microsoft.BIServer.BIService.BIService::ReloadHostingState

- ea: `0x10a0`
- end: `0x10d9`
- name: `Microsoft.BIServer.BIService.BIService::ReloadHostingState`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x32c0`
- `0x3970`

## pseudocode

```c

```

## disassembly

```asm
0x10a0  ldloca.s 0
0x10a2  ldarg.0
0x10a3  stfld    class Microsoft.BIServer.BIService.BIService <ReloadHostingState>d__46::<>4__this
0x10a8  ldloca.s 0
0x10aa  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::Create()
0x10af  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ReloadHostingState>d__46::<>t__builder
0x10b4  ldloca.s 0
0x10b6  ldc.i4.m1
0x10b7  stfld    int32 <ReloadHostingState>d__46::<>1__state
0x10bc  ldloc.0
0x10bd  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ReloadHostingState>d__46::<>t__builder
0x10c2  stloc.1
0x10c3  ldloca.s 1
0x10c5  ldloca.s 0
0x10c7  call     T0x2B000010
0x10cc  ldloca.s 0
0x10ce  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <ReloadHostingState>d__46::<>t__builder
0x10d3  call     instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::get_Task()
0x10d8  ret
```
