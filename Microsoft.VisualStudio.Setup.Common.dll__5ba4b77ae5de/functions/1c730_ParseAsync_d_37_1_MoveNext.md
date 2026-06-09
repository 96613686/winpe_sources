# <ParseAsync>d__37`1::MoveNext

- ea: `0x1c730`
- end: `0x1c8ad`
- name: `<ParseAsync>d__37`1::MoveNext`
- size: `381`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0xc1a0`
- `0x11900`
- `0x11970`
- `0x11b30`
- `0x1c730`

## string_xrefs

- `0x1c743`: `services`

## pseudocode

```c

```

## disassembly

```asm
0x1c730  ldarg.0
0x1c731  ldfld    int32 valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::<>1__state
0x1c736  stloc.0
0x1c737  ldloc.0
0x1c738  brfalse  loc_1C7F4
0x1c73d  ldarg.0
0x1c73e  ldfld    class [mscorlib]System.IServiceProvider valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::services
0x1c743  ldstr    aServices// "services"
0x1c748  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1c74d  ldarg.0
0x1c74e  ldfld    string valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::path
0x1c753  ldstr    aPath_0// "path"
0x1c758  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1c75d  ldarg.0
0x1c75e  ldfld    class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>> valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::serializer
0x1c763  ldstr    aSerializer// "serializer"
0x1c768  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1c76d  ldarg.0
0x1c76e  ldfld    class [mscorlib]System.IServiceProvider valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::services
0x1c773  ldc.i4.1
0x1c774  call     T0x2B00003E
0x1c779  stloc.2
0x1c77a  ldarg.0
0x1c77b  ldfld    class [mscorlib]System.IServiceProvider valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::services
0x1c780  ldc.i4.0
0x1c781  call     T0x2B00003F
0x1c786  stloc.3
0x1c787  ldloc.2
0x1c788  ldarg.0
0x1c789  ldfld    string valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::path
0x1c78e  callvirt instance bool Microsoft.VisualStudio.Setup.Services.IFileSystem::FileExists(string path)
0x1c793  brtrue.s loc_1C7D1
0x1c795  ldstr    aFile// "File "
0x1c79a  ldarg.0
0x1c79b  ldfld    string valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::path
0x1c7a0  ldstr    aDoesNotExist// " does not exist."
0x1c7a5  call     string [mscorlib]System.String::Concat(string, string, string)
0x1c7aa  ldarg.0
0x1c7ab  ldfld    string valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::path
0x1c7b0  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor(string, string)
0x1c7b5  stloc.s  4
0x1c7b7  ldloc.3
0x1c7b8  brfalse.s loc_1C7CE
0x1c7ba  ldloc.3
0x1c7bb  ldloc.s  4
0x1c7bd  ldloc.s  4
0x1c7bf  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1c7c4  call     T0x2B000016
0x1c7c9  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception ex, string format, object[] args)
0x1c7ce  ldloc.s  4
0x1c7d0  throw
0x1c7d1  ldarg.0
0x1c7d2  ldfld    class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>> valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::serializer
0x1c7d7  ldarg.0
0x1c7d8  ldfld    string valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::path
0x1c7dd  callvirt instance void class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::set_Location(string)
0x1c7e2  ldarg.0
0x1c7e3  ldloc.2
0x1c7e4  ldarg.0
0x1c7e5  ldfld    string valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::path
0x1c7ea  callvirt instance class [mscorlib]System.IO.TextReader Microsoft.VisualStudio.Setup.Services.IFileSystem::OpenText(string path)
0x1c7ef  stfld    class [mscorlib]System.IO.TextReader valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::<reader>5__2
0x1c7f4  nop
0x1c7f5  ldloc.0
0x1c7f6  brfalse.s loc_1C840
0x1c7f8  ldarg.0
0x1c7f9  ldfld    class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>> valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::serializer
0x1c7fe  ldarg.0
0x1c7ff  ldfld    class [mscorlib]System.IO.TextReader valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::<reader>5__2
0x1c804  ldarg.0
0x1c805  ldfld    valuetype [mscorlib]System.Threading.CancellationToken valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::token
0x1c80a  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<var<u1>>::DeserializeAsync(!!T0, class [mscorlib]System.IO.TextReader)
0x1c80f  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<var<u1>>::GetAwaiter()
0x1c814  stloc.s  5
0x1c816  ldloca.s 5
0x1c818  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>::get_IsCompleted()
0x1c81d  brtrue.s loc_1C85D
0x1c81f  ldarg.0
0x1c820  ldc.i4.0
0x1c821  dup
0x1c822  stloc.0
0x1c823  stfld    int32 valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::<>1__state
0x1c828  ldarg.0
0x1c829  ldloc.s  5
0x1c82b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::<>u__1
0x1c830  ldarg.0
0x1c831  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::<>t__builder
0x1c836  ldloca.s 5
0x1c838  ldarg.0
0x1c839  call     T0x2B0000D8
0x1c83e  leave.s  loc_1C8AC
0x1c840  ldarg.0
0x1c841  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::<>u__1
0x1c846  stloc.s  5
0x1c848  ldarg.0
0x1c849  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::<>u__1
0x1c84e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>
0x1c854  ldarg.0
0x1c855  ldc.i4.m1
0x1c856  dup
0x1c857  stloc.0
0x1c858  stfld    int32 valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::<>1__state
0x1c85d  ldloca.s 5
0x1c85f  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>::GetResult()
0x1c864  stloc.1
0x1c865  leave.s  loc_1C898
0x1c867  ldloc.0
0x1c868  ldc.i4.0
0x1c869  bge.s    loc_1C87E
0x1c86b  ldarg.0
0x1c86c  ldfld    class [mscorlib]System.IO.TextReader valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::<reader>5__2
0x1c871  brfalse.s loc_1C87E
0x1c873  ldarg.0
0x1c874  ldfld    class [mscorlib]System.IO.TextReader valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::<reader>5__2
0x1c879  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c87e  endfinally
0x1c87f  stloc.s  6
0x1c881  ldarg.0
0x1c882  ldc.i4.s 0xFE
0x1c884  stfld    int32 valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::<>1__state
0x1c889  ldarg.0
0x1c88a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::<>t__builder
0x1c88f  ldloc.s  6
0x1c891  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetException(class [mscorlib]System.Exception)
0x1c896  leave.s  loc_1C8AC
0x1c898  ldarg.0
0x1c899  ldc.i4.s 0xFE
0x1c89b  stfld    int32 valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::<>1__state
0x1c8a0  ldarg.0
0x1c8a1  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <ParseAsync>d__37`1<var<u1>, !!T0>::<>t__builder
0x1c8a6  ldloc.1
0x1c8a7  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetResult(var<u1>)
0x1c8ac  ret
```
