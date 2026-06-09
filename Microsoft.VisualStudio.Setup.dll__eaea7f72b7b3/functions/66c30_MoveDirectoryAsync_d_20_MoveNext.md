# <MoveDirectoryAsync>d__20::MoveNext

- ea: `0x66c30`
- end: `0x66eec`
- name: `<MoveDirectoryAsync>d__20::MoveNext`
- size: `700`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x6fa0`
- `0x7260`
- `0x7280`
- `0xffb0`
- `0x66c30`

## string_xrefs

- `0x66cc1`: `Directory "`
- `0x66e42`: `Deleting directory: {0}`
- `0x66e8b`: `A reboot is required to delete directory: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x66c30  ldarg.0
0x66c31  ldfld    int32 <MoveDirectoryAsync>d__20::<>1__state
0x66c36  stloc.0
0x66c37  ldarg.0
0x66c38  ldfld    class Microsoft.VisualStudio.Setup.Copier <MoveDirectoryAsync>d__20::<>4__this
0x66c3d  stloc.1
0x66c3e  ldloc.0
0x66c3f  brfalse  loc_66D7B
0x66c44  ldloc.0
0x66c45  ldc.i4.1
0x66c46  beq      loc_66E12
0x66c4b  ldarg.0
0x66c4c  ldfld    string <MoveDirectoryAsync>d__20::source
0x66c51  ldstr    aSource// "source"
0x66c56  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x66c5b  ldarg.0
0x66c5c  ldfld    string <MoveDirectoryAsync>d__20::destination
0x66c61  ldstr    aDestination// "destination"
0x66c66  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x66c6b  ldarg.0
0x66c6c  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <MoveDirectoryAsync>d__20::cancellationToken
0x66c71  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x66c76  ldarg.0
0x66c77  ldloc.1
0x66c78  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Copier::fileSystem
0x66c7d  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_CurrentDirectory()
0x66c82  ldarg.0
0x66c83  ldfld    string <MoveDirectoryAsync>d__20::source
0x66c88  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x66c8d  stfld    string <MoveDirectoryAsync>d__20::source
0x66c92  ldarg.0
0x66c93  ldloc.1
0x66c94  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Copier::fileSystem
0x66c99  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_CurrentDirectory()
0x66c9e  ldarg.0
0x66c9f  ldfld    string <MoveDirectoryAsync>d__20::destination
0x66ca4  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x66ca9  stfld    string <MoveDirectoryAsync>d__20::destination
0x66cae  ldloc.1
0x66caf  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Copier::fileSystem
0x66cb4  ldarg.0
0x66cb5  ldfld    string <MoveDirectoryAsync>d__20::source
0x66cba  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::DirectoryExists(string)
0x66cbf  brtrue.s loc_66CDC
0x66cc1  ldstr    aDirectory_2// "Directory \""
0x66cc6  ldarg.0
0x66cc7  ldfld    string <MoveDirectoryAsync>d__20::source
0x66ccc  ldstr    aNotFound// "\" not found"
0x66cd1  call     string [mscorlib]System.String::Concat(string, string, string)
0x66cd6  newobj   instance void [mscorlib]System.IO.DirectoryNotFoundException::.ctor(string)
0x66cdb  throw
0x66cdc  ldarg.0
0x66cdd  ldloc.1
0x66cde  ldflda   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) int32 Microsoft.VisualStudio.Setup.Copier::operationId
0x66ce3  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x66ce8  stfld    int32 <MoveDirectoryAsync>d__20::<operationId>5__2
0x66ced  ldc.r8   0.0
0x66cf6  stloc.2
0x66cf7  ldloc.1
0x66cf8  ldc.i4.1
0x66cf9  ldarg.0
0x66cfa  ldfld    int32 <MoveDirectoryAsync>d__20::<operationId>5__2
0x66cff  ldloca.s 2
0x66d01  call     instance void Microsoft.VisualStudio.Setup.Copier::OnProgress(valuetype Microsoft.VisualStudio.Setup.CopierOperation operation, int32 operationId, float64& progress)
0x66d06  ldarg.0
0x66d07  ldfld    string <MoveDirectoryAsync>d__20::source
0x66d0c  call     string [mscorlib]System.IO.Path::GetPathRoot(string)
0x66d11  ldarg.0
0x66d12  ldfld    string <MoveDirectoryAsync>d__20::destination
0x66d17  call     string [mscorlib]System.IO.Path::GetPathRoot(string)
0x66d1c  stloc.3
0x66d1d  ldloc.3
0x66d1e  ldc.i4.5
0x66d1f  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x66d24  brfalse  loc_66DBF
0x66d29  ldloc.1
0x66d2a  ldarg.0
0x66d2b  ldfld    string <MoveDirectoryAsync>d__20::source
0x66d30  ldarg.0
0x66d31  ldfld    string <MoveDirectoryAsync>d__20::destination
0x66d36  ldarg.0
0x66d37  ldfld    bool <MoveDirectoryAsync>d__20::atomicMove
0x66d3c  ldarg.0
0x66d3d  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <MoveDirectoryAsync>d__20::cancellationToken
0x66d42  call     instance class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.VisualStudio.Setup.Copier::MoveDirectoryAsyncInternal(string source, string destination, bool throwOnFailure, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x66d47  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::GetAwaiter()
0x66d4c  stloc.s  5
0x66d4e  ldloca.s 5
0x66d50  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::get_IsCompleted()
0x66d55  brtrue.s loc_66D98
0x66d57  ldarg.0
0x66d58  ldc.i4.0
0x66d59  dup
0x66d5a  stloc.0
0x66d5b  stfld    int32 <MoveDirectoryAsync>d__20::<>1__state
0x66d60  ldarg.0
0x66d61  ldloc.s  5
0x66d63  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <MoveDirectoryAsync>d__20::<>u__1
0x66d68  ldarg.0
0x66d69  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <MoveDirectoryAsync>d__20::<>t__builder
0x66d6e  ldloca.s 5
0x66d70  ldarg.0
0x66d71  call     T0x2B0002D2
0x66d76  leave    loc_66EEB
0x66d7b  ldarg.0
0x66d7c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <MoveDirectoryAsync>d__20::<>u__1
0x66d81  stloc.s  5
0x66d83  ldarg.0
0x66d84  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool> <MoveDirectoryAsync>d__20::<>u__1
0x66d89  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>
0x66d8f  ldarg.0
0x66d90  ldc.i4.m1
0x66d91  dup
0x66d92  stloc.0
0x66d93  stfld    int32 <MoveDirectoryAsync>d__20::<>1__state
0x66d98  ldloca.s 5
0x66d9a  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool>::GetResult()
0x66d9f  brfalse.s loc_66DBF
0x66da1  ldc.r8   1.0
0x66daa  stloc.2
0x66dab  ldloc.1
0x66dac  ldc.i4.1
0x66dad  ldarg.0
0x66dae  ldfld    int32 <MoveDirectoryAsync>d__20::<operationId>5__2
0x66db3  ldloca.s 2
0x66db5  call     instance void Microsoft.VisualStudio.Setup.Copier::OnProgress(valuetype Microsoft.VisualStudio.Setup.CopierOperation operation, int32 operationId, float64& progress)
0x66dba  leave    loc_66ED8
0x66dbf  ldloc.1
0x66dc0  ldarg.0
0x66dc1  ldfld    string <MoveDirectoryAsync>d__20::source
0x66dc6  ldarg.0
0x66dc7  ldfld    string <MoveDirectoryAsync>d__20::destination
0x66dcc  ldc.i4.1
0x66dcd  ldarg.0
0x66dce  ldfld    int32 <MoveDirectoryAsync>d__20::<operationId>5__2
0x66dd3  ldarg.0
0x66dd4  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <MoveDirectoryAsync>d__20::cancellationToken
0x66dd9  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Copier::InvokeAsync(string source, string destination, valuetype Microsoft.VisualStudio.Setup.CopierOperation operation, int32 operationId, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x66dde  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x66de3  stloc.s  6
0x66de5  ldloca.s 6
0x66de7  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x66dec  brtrue.s loc_66E2F
0x66dee  ldarg.0
0x66def  ldc.i4.1
0x66df0  dup
0x66df1  stloc.0
0x66df2  stfld    int32 <MoveDirectoryAsync>d__20::<>1__state
0x66df7  ldarg.0
0x66df8  ldloc.s  6
0x66dfa  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <MoveDirectoryAsync>d__20::<>u__2
0x66dff  ldarg.0
0x66e00  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <MoveDirectoryAsync>d__20::<>t__builder
0x66e05  ldloca.s 6
0x66e07  ldarg.0
0x66e08  call     T0x2B0002D3
0x66e0d  leave    loc_66EEB
0x66e12  ldarg.0
0x66e13  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <MoveDirectoryAsync>d__20::<>u__2
0x66e18  stloc.s  6
0x66e1a  ldarg.0
0x66e1b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <MoveDirectoryAsync>d__20::<>u__2
0x66e20  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x66e26  ldarg.0
0x66e27  ldc.i4.m1
0x66e28  dup
0x66e29  stloc.0
0x66e2a  stfld    int32 <MoveDirectoryAsync>d__20::<>1__state
0x66e2f  ldloca.s 6
0x66e31  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x66e36  ldloc.1
0x66e37  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Copier::logger
0x66e3c  dup
0x66e3d  brtrue.s loc_66E42
0x66e3f  pop
0x66e40  br.s     loc_66E5B
0x66e42  ldstr    aDeletingDirect_2// "Deleting directory: {0}"
0x66e47  ldc.i4.1
0x66e48  newarr   [mscorlib]System.Object
0x66e4d  dup
0x66e4e  ldc.i4.0
0x66e4f  ldarg.0
0x66e50  ldfld    string <MoveDirectoryAsync>d__20::source
0x66e55  stelem.ref
0x66e56  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x66e5b  ldloc.1
0x66e5c  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Copier::fileSystem
0x66e61  ldarg.0
0x66e62  ldfld    string <MoveDirectoryAsync>d__20::source
0x66e67  ldloca.s 4
0x66e69  ldc.i4.1
0x66e6a  ldc.i4.1
0x66e6b  ldc.i4.2
0x66e6c  ldc.i4   0x1F4
0x66e71  ldnull
0x66e72  call     bool Microsoft.VisualStudio.Setup.Extensions::DeleteDirectoryWithRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string path, [out] bool& rebootRequired, [opt] bool rebootOK, [opt] bool recursive, [opt] int32 retryCount, [opt] int32 retryDelay, [opt] class [mscorlib]System.Func`3<class [mscorlib]System.Exception, int32, bool> errorAction)
0x66e77  ldc.i4.0
0x66e78  ceq
0x66e7a  ldloc.s  4
0x66e7c  and
0x66e7d  brfalse.s loc_66EA4
0x66e7f  ldloc.1
0x66e80  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Copier::logger
0x66e85  dup
0x66e86  brtrue.s loc_66E8B
0x66e88  pop
0x66e89  br.s     loc_66EA4
0x66e8b  ldstr    aARebootIsRequi_0// "A reboot is required to delete director"...
0x66e90  ldc.i4.1
0x66e91  newarr   [mscorlib]System.Object
0x66e96  dup
0x66e97  ldc.i4.0
0x66e98  ldarg.0
0x66e99  ldfld    string <MoveDirectoryAsync>d__20::source
0x66e9e  stelem.ref
0x66e9f  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x66ea4  ldc.r8   1.0
0x66ead  stloc.2
0x66eae  ldloc.1
0x66eaf  ldc.i4.1
0x66eb0  ldarg.0
0x66eb1  ldfld    int32 <MoveDirectoryAsync>d__20::<operationId>5__2
0x66eb6  ldloca.s 2
0x66eb8  call     instance void Microsoft.VisualStudio.Setup.Copier::OnProgress(valuetype Microsoft.VisualStudio.Setup.CopierOperation operation, int32 operationId, float64& progress)
0x66ebd  leave.s  loc_66ED8
0x66ebf  stloc.s  7
0x66ec1  ldarg.0
0x66ec2  ldc.i4.s 0xFE
0x66ec4  stfld    int32 <MoveDirectoryAsync>d__20::<>1__state
0x66ec9  ldarg.0
0x66eca  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <MoveDirectoryAsync>d__20::<>t__builder
0x66ecf  ldloc.s  7
0x66ed1  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x66ed6  leave.s  loc_66EEB
0x66ed8  ldarg.0
0x66ed9  ldc.i4.s 0xFE
0x66edb  stfld    int32 <MoveDirectoryAsync>d__20::<>1__state
0x66ee0  ldarg.0
0x66ee1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <MoveDirectoryAsync>d__20::<>t__builder
0x66ee6  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x66eeb  ret
```
