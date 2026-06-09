# Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::CleanupLogsAsync

- ea: `0x1b70`
- end: `0x1baf`
- name: `Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::CleanupLogsAsync`
- size: `63`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3c10`
- `0x5530`

## pseudocode

```c

```

## disassembly

```asm
0x1b70  ldloca.s 0
0x1b72  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::Create()
0x1b77  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <CleanupLogsAsync>d__58::<>t__builder
0x1b7c  ldloca.s 0
0x1b7e  ldarg.0
0x1b7f  stfld    class Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase <CleanupLogsAsync>d__58::<>4__this
0x1b84  ldloca.s 0
0x1b86  ldarg.1
0x1b87  stfld    valuetype [mscorlib]System.Threading.CancellationToken <CleanupLogsAsync>d__58::cancellationToken
0x1b8c  ldloca.s 0
0x1b8e  ldc.i4.m1
0x1b8f  stfld    int32 <CleanupLogsAsync>d__58::<>1__state
0x1b94  ldloca.s 0
0x1b96  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <CleanupLogsAsync>d__58::<>t__builder
0x1b9b  ldloca.s 0
0x1b9d  call     T0x2B000016
0x1ba2  ldloca.s 0
0x1ba4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <CleanupLogsAsync>d__58::<>t__builder
0x1ba9  call     instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::get_Task()
0x1bae  ret
```
