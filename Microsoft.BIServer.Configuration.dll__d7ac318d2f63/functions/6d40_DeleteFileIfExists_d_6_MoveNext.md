# <DeleteFileIfExists>d__6::MoveNext

- ea: `0x6d40`
- end: `0x6e58`
- name: `<DeleteFileIfExists>d__6::MoveNext`
- size: `280`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x810`
- `0x6d40`

## string_xrefs

- `0x6d74`: `Deleting scoped temp file : {0}`
- `0x6d9d`: `Failed to delete temp file {0}, will reschedule one retry`
- `0x6e12`: `Skipping delete of non-existant scoped temp file : {0}`

## pseudocode

```c

```

## disassembly

```asm
0x6d40  ldarg.0
0x6d41  ldfld    int32 <DeleteFileIfExists>d__6::<>1__state
0x6d46  stloc.0
0x6d47  ldarg.0
0x6d48  ldfld    class Microsoft.BIServer.Configuration.ScopedFileDelete <DeleteFileIfExists>d__6::<>4__this
0x6d4d  stloc.1
0x6d4e  ldloc.0
0x6d4f  brfalse  loc_6DED
0x6d54  ldloc.1
0x6d55  ldfld    string Microsoft.BIServer.Configuration.ScopedFileDelete::FullPath
0x6d5a  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6d5f  brtrue   loc_6E12
0x6d64  ldloc.1
0x6d65  ldfld    string Microsoft.BIServer.Configuration.ScopedFileDelete::FullPath
0x6d6a  call     bool [mscorlib]System.IO.File::Exists(string)
0x6d6f  brfalse  loc_6E12
0x6d74  ldstr    aDeletingScoped// "Deleting scoped temp file : {0}"
0x6d79  ldc.i4.1
0x6d7a  newarr   [mscorlib]System.Object
0x6d7f  dup
0x6d80  ldc.i4.0
0x6d81  ldloc.1
0x6d82  ldfld    string Microsoft.BIServer.Configuration.ScopedFileDelete::FullPath
0x6d87  stelem.ref
0x6d88  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Trace(string, object[])
0x6d8d  ldloc.1
0x6d8e  ldfld    string Microsoft.BIServer.Configuration.ScopedFileDelete::FullPath
0x6d93  call     void [mscorlib]System.IO.File::Delete(string)
0x6d98  leave    loc_6E44
0x6d9d  ldstr    aFailedToDelete// "Failed to delete temp file {0}, will re"...
0x6da2  ldc.i4.1
0x6da3  newarr   [mscorlib]System.Object
0x6da8  dup
0x6da9  ldc.i4.0
0x6daa  ldloc.1
0x6dab  ldfld    string Microsoft.BIServer.Configuration.ScopedFileDelete::FullPath
0x6db0  stelem.ref
0x6db1  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Debug(class [mscorlib]System.Exception, string, object[])
0x6db6  leave.s  loc_6DB8
0x6db8  ldloc.1
0x6db9  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.BIServer.Configuration.ScopedFileDelete::SingleDeleteRetry()
0x6dbe  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x6dc3  stloc.2
0x6dc4  ldloca.s 2
0x6dc6  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x6dcb  brtrue.s loc_6E09
0x6dcd  ldarg.0
0x6dce  ldc.i4.0
0x6dcf  dup
0x6dd0  stloc.0
0x6dd1  stfld    int32 <DeleteFileIfExists>d__6::<>1__state
0x6dd6  ldarg.0
0x6dd7  ldloc.2
0x6dd8  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <DeleteFileIfExists>d__6::<>u__1
0x6ddd  ldarg.0
0x6dde  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <DeleteFileIfExists>d__6::<>t__builder
0x6de3  ldloca.s 2
0x6de5  ldarg.0
0x6de6  call     T0x2B000040
0x6deb  leave.s  loc_6E57
0x6ded  ldarg.0
0x6dee  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <DeleteFileIfExists>d__6::<>u__1
0x6df3  stloc.2
0x6df4  ldarg.0
0x6df5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <DeleteFileIfExists>d__6::<>u__1
0x6dfa  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x6e00  ldarg.0
0x6e01  ldc.i4.m1
0x6e02  dup
0x6e03  stloc.0
0x6e04  stfld    int32 <DeleteFileIfExists>d__6::<>1__state
0x6e09  ldloca.s 2
0x6e0b  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x6e10  br.s     loc_6E2B
0x6e12  ldstr    aSkippingDelete// "Skipping delete of non-existant scoped "...
0x6e17  ldc.i4.1
0x6e18  newarr   [mscorlib]System.Object
0x6e1d  dup
0x6e1e  ldc.i4.0
0x6e1f  ldloc.1
0x6e20  ldfld    string Microsoft.BIServer.Configuration.ScopedFileDelete::FullPath
0x6e25  stelem.ref
0x6e26  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Trace(string, object[])
0x6e2b  leave.s  loc_6E44
0x6e2d  stloc.3
0x6e2e  ldarg.0
0x6e2f  ldc.i4.s 0xFE
0x6e31  stfld    int32 <DeleteFileIfExists>d__6::<>1__state
0x6e36  ldarg.0
0x6e37  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <DeleteFileIfExists>d__6::<>t__builder
0x6e3c  ldloc.3
0x6e3d  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x6e42  leave.s  loc_6E57
0x6e44  ldarg.0
0x6e45  ldc.i4.s 0xFE
0x6e47  stfld    int32 <DeleteFileIfExists>d__6::<>1__state
0x6e4c  ldarg.0
0x6e4d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <DeleteFileIfExists>d__6::<>t__builder
0x6e52  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x6e57  ret
```
