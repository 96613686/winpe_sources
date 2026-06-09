# Microsoft.VisualStudio.Setup.CompositionRoot::AddBackgroundDownloadServicesAsync

- ea: `0x23a0`
- end: `0x23df`
- name: `Microsoft.VisualStudio.Setup.CompositionRoot::AddBackgroundDownloadServicesAsync`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x5090`

## pseudocode

```c

```

## disassembly

```asm
0x23a0  ldloca.s 0
0x23a2  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::Create()
0x23a7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <AddBackgroundDownloadServicesAsync>d__3::<>t__builder
0x23ac  ldloca.s 0
0x23ae  ldarg.0
0x23af  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ServiceProvider <AddBackgroundDownloadServicesAsync>d__3::services
0x23b4  ldloca.s 0
0x23b6  ldarg.1
0x23b7  stfld    class Microsoft.VisualStudio.Setup.CommandLine <AddBackgroundDownloadServicesAsync>d__3::commandLine
0x23bc  ldloca.s 0
0x23be  ldc.i4.m1
0x23bf  stfld    int32 <AddBackgroundDownloadServicesAsync>d__3::<>1__state
0x23c4  ldloca.s 0
0x23c6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <AddBackgroundDownloadServicesAsync>d__3::<>t__builder
0x23cb  ldloca.s 0
0x23cd  call     T0x2B000032
0x23d2  ldloca.s 0
0x23d4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <AddBackgroundDownloadServicesAsync>d__3::<>t__builder
0x23d9  call     instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::get_Task()
0x23de  ret
```
