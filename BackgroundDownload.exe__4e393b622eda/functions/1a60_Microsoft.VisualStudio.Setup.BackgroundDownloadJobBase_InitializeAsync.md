# Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::InitializeAsync

- ea: `0x1a60`
- end: `0x1a9f`
- name: `Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::InitializeAsync`
- size: `63`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1820`
- `0x3c10`
- `0x4270`
- `0x5530`

## pseudocode

```c

```

## disassembly

```asm
0x1a60  ldloca.s 0
0x1a62  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::Create()
0x1a67  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeAsync>d__54::<>t__builder
0x1a6c  ldloca.s 0
0x1a6e  ldarg.0
0x1a6f  stfld    class Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase <InitializeAsync>d__54::<>4__this
0x1a74  ldloca.s 0
0x1a76  ldarg.1
0x1a77  stfld    valuetype [mscorlib]System.Threading.CancellationToken <InitializeAsync>d__54::cancellationToken
0x1a7c  ldloca.s 0
0x1a7e  ldc.i4.m1
0x1a7f  stfld    int32 <InitializeAsync>d__54::<>1__state
0x1a84  ldloca.s 0
0x1a86  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeAsync>d__54::<>t__builder
0x1a8b  ldloca.s 0
0x1a8d  call     T0x2B000014
0x1a92  ldloca.s 0
0x1a94  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeAsync>d__54::<>t__builder
0x1a99  call     instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::get_Task()
0x1a9e  ret
```
