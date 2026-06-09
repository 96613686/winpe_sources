# Microsoft.BIServer.BIService.BIService::HandleStatusChanges

- ea: `0xc60`
- end: `0xc99`
- name: `Microsoft.BIServer.BIService.BIService::HandleStatusChanges`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2ea0`

## pseudocode

```c

```

## disassembly

```asm
0xc60  ldloca.s 0
0xc62  ldarg.0
0xc63  stfld    class Microsoft.BIServer.BIService.BIService <HandleStatusChanges>d__31::<>4__this
0xc68  ldloca.s 0
0xc6a  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::Create()
0xc6f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleStatusChanges>d__31::<>t__builder
0xc74  ldloca.s 0
0xc76  ldc.i4.m1
0xc77  stfld    int32 <HandleStatusChanges>d__31::<>1__state
0xc7c  ldloc.0
0xc7d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleStatusChanges>d__31::<>t__builder
0xc82  stloc.1
0xc83  ldloca.s 1
0xc85  ldloca.s 0
0xc87  call     T0x2B000008
0xc8c  ldloca.s 0
0xc8e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleStatusChanges>d__31::<>t__builder
0xc93  call     instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::get_Task()
0xc98  ret
```
