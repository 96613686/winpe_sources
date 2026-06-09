# Microsoft.BIServer.BIService.BIService::Reconfigure

- ea: `0x1040`
- end: `0x1079`
- name: `Microsoft.BIServer.BIService.BIService::Reconfigure`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2dd0`

## pseudocode

```c

```

## disassembly

```asm
0x1040  ldloca.s 0
0x1042  ldarg.0
0x1043  stfld    class Microsoft.BIServer.BIService.BIService <Reconfigure>d__44::<>4__this
0x1048  ldloca.s 0
0x104a  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::Create()
0x104f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Reconfigure>d__44::<>t__builder
0x1054  ldloca.s 0
0x1056  ldc.i4.m1
0x1057  stfld    int32 <Reconfigure>d__44::<>1__state
0x105c  ldloc.0
0x105d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Reconfigure>d__44::<>t__builder
0x1062  stloc.1
0x1063  ldloca.s 1
0x1065  ldloca.s 0
0x1067  call     T0x2B00000F
0x106c  ldloca.s 0
0x106e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <Reconfigure>d__44::<>t__builder
0x1073  call     instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::get_Task()
0x1078  ret
```
