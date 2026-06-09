# Microsoft.VisualStudio.Setup.ElevationServiceManager::RunServiceAsync

- ea: `0xd20`
- end: `0xd57`
- name: `Microsoft.VisualStudio.Setup.ElevationServiceManager::RunServiceAsync`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0xd20  ldloca.s 0
0xd22  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::Create()
0xd27  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <RunServiceAsync>d__14::<>t__builder
0xd2c  ldloca.s 0
0xd2e  ldarg.0
0xd2f  stfld    class Microsoft.VisualStudio.Setup.ElevationServiceManager <RunServiceAsync>d__14::<>4__this
0xd34  ldloca.s 0
0xd36  ldc.i4.m1
0xd37  stfld    int32 <RunServiceAsync>d__14::<>1__state
0xd3c  ldloca.s 0
0xd3e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <RunServiceAsync>d__14::<>t__builder
0xd43  ldloca.s 0
0xd45  call     T0x2B000002
0xd4a  ldloca.s 0
0xd4c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <RunServiceAsync>d__14::<>t__builder
0xd51  call     instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::get_Task()
0xd56  ret
```
