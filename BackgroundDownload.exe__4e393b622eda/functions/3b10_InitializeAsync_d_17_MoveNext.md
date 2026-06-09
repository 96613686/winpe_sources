# <InitializeAsync>d__17::MoveNext

- ea: `0x3b10`
- end: `0x3be3`
- name: `<InitializeAsync>d__17::MoveNext`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1820`
- `0x1920`
- `0x19d0`
- `0x3b10`

## pseudocode

```c

```

## disassembly

```asm
0x3b10  ldarg.0
0x3b11  ldfld    int32 <InitializeAsync>d__17::<>1__state
0x3b16  stloc.0
0x3b17  ldarg.0
0x3b18  ldfld    class Microsoft.VisualStudio.Setup.BackgroundDownloader <InitializeAsync>d__17::<>4__this
0x3b1d  stloc.1
0x3b1e  ldloc.0
0x3b1f  brfalse.s loc_3B7C
0x3b21  ldloc.1
0x3b22  call     instance bool Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_IsDisposed()
0x3b27  brfalse.s loc_3B34
0x3b29  ldstr    aBackgrounddown_0// "BackgroundDownloader"
0x3b2e  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string)
0x3b33  throw
0x3b34  ldloc.1
0x3b35  call     instance bool Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_IsInitialized()
0x3b3a  brfalse.s loc_3B41
0x3b3c  leave    loc_3BCF
0x3b41  ldloc.1
0x3b42  ldarg.0
0x3b43  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InitializeAsync>d__17::cancellationToken
0x3b48  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.BackgroundDownloader::<>n__0(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x3b4d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x3b52  stloc.2
0x3b53  ldloca.s 2
0x3b55  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x3b5a  brtrue.s loc_3B98
0x3b5c  ldarg.0
0x3b5d  ldc.i4.0
0x3b5e  dup
0x3b5f  stloc.0
0x3b60  stfld    int32 <InitializeAsync>d__17::<>1__state
0x3b65  ldarg.0
0x3b66  ldloc.2
0x3b67  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InitializeAsync>d__17::<>u__1
0x3b6c  ldarg.0
0x3b6d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeAsync>d__17::<>t__builder
0x3b72  ldloca.s 2
0x3b74  ldarg.0
0x3b75  call     T0x2B000046
0x3b7a  leave.s  loc_3BE2
0x3b7c  ldarg.0
0x3b7d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InitializeAsync>d__17::<>u__1
0x3b82  stloc.2
0x3b83  ldarg.0
0x3b84  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <InitializeAsync>d__17::<>u__1
0x3b89  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x3b8f  ldarg.0
0x3b90  ldc.i4.m1
0x3b91  dup
0x3b92  stloc.0
0x3b93  stfld    int32 <InitializeAsync>d__17::<>1__state
0x3b98  ldloca.s 2
0x3b9a  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x3b9f  ldloc.1
0x3ba0  ldfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IProgressReceiver Microsoft.VisualStudio.Setup.BackgroundDownloader::progressReceiver
0x3ba5  ldloc.1
0x3ba6  ldftn    instance void Microsoft.VisualStudio.Setup.BackgroundDownloader::OnProgressReport(object sender, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs e)
0x3bac  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs>::.ctor(object, native int)
0x3bb1  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IProgressReceiver::add_OnReport(class [mscorlib]System.EventHandler`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProgressEventArgs>)
0x3bb6  leave.s  loc_3BCF
0x3bb8  stloc.3
0x3bb9  ldarg.0
0x3bba  ldc.i4.s 0xFE
0x3bbc  stfld    int32 <InitializeAsync>d__17::<>1__state
0x3bc1  ldarg.0
0x3bc2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeAsync>d__17::<>t__builder
0x3bc7  ldloc.3
0x3bc8  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x3bcd  leave.s  loc_3BE2
0x3bcf  ldarg.0
0x3bd0  ldc.i4.s 0xFE
0x3bd2  stfld    int32 <InitializeAsync>d__17::<>1__state
0x3bd7  ldarg.0
0x3bd8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InitializeAsync>d__17::<>t__builder
0x3bdd  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x3be2  ret
```
