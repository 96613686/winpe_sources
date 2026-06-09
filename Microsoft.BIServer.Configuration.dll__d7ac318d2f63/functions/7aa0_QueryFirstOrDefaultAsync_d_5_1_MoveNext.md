# <QueryFirstOrDefaultAsync>d__5`1::MoveNext

- ea: `0x7aa0`
- end: `0x7b69`
- name: `<QueryFirstOrDefaultAsync>d__5`1::MoveNext`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x67f0`
- `0x7aa0`

## pseudocode

```c

```

## disassembly

```asm
0x7aa0  ldarg.0
0x7aa1  ldfld    int32 valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::<>1__state
0x7aa6  stloc.0
0x7aa7  ldloc.0
0x7aa8  brfalse.s loc_7AB5
0x7aaa  ldarg.0
0x7aab  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection Microsoft.BIServer.Configuration.Catalog.CatalogAccessFactory::NewConnection()
0x7ab0  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::<sqlAccess>5__2
0x7ab5  nop
0x7ab6  ldloc.0
0x7ab7  brfalse.s loc_7AFF
0x7ab9  ldarg.0
0x7aba  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::<sqlAccess>5__2
0x7abf  ldarg.0
0x7ac0  ldfld    string valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::storedProcedureName
0x7ac5  ldarg.0
0x7ac6  ldfld    object valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::parameters
0x7acb  callvirt T0x2B000049
0x7ad0  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<var<u1>>::GetAwaiter()
0x7ad5  stloc.2
0x7ad6  ldloca.s 2
0x7ad8  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>::get_IsCompleted()
0x7add  brtrue.s loc_7B1B
0x7adf  ldarg.0
0x7ae0  ldc.i4.0
0x7ae1  dup
0x7ae2  stloc.0
0x7ae3  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::<>1__state
0x7ae8  ldarg.0
0x7ae9  ldloc.2
0x7aea  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::<>u__1
0x7aef  ldarg.0
0x7af0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::<>t__builder
0x7af5  ldloca.s 2
0x7af7  ldarg.0
0x7af8  call     T0x2B00004A
0x7afd  leave.s  loc_7B68
0x7aff  ldarg.0
0x7b00  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::<>u__1
0x7b05  stloc.2
0x7b06  ldarg.0
0x7b07  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::<>u__1
0x7b0c  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>
0x7b12  ldarg.0
0x7b13  ldc.i4.m1
0x7b14  dup
0x7b15  stloc.0
0x7b16  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::<>1__state
0x7b1b  ldloca.s 2
0x7b1d  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>::GetResult()
0x7b22  stloc.1
0x7b23  leave.s  loc_7B54
0x7b25  ldloc.0
0x7b26  ldc.i4.0
0x7b27  bge.s    loc_7B3C
0x7b29  ldarg.0
0x7b2a  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::<sqlAccess>5__2
0x7b2f  brfalse.s loc_7B3C
0x7b31  ldarg.0
0x7b32  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::<sqlAccess>5__2
0x7b37  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7b3c  endfinally
0x7b3d  stloc.3
0x7b3e  ldarg.0
0x7b3f  ldc.i4.s 0xFE
0x7b41  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::<>1__state
0x7b46  ldarg.0
0x7b47  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::<>t__builder
0x7b4c  ldloc.3
0x7b4d  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetException(class [mscorlib]System.Exception)
0x7b52  leave.s  loc_7B68
0x7b54  ldarg.0
0x7b55  ldc.i4.s 0xFE
0x7b57  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::<>1__state
0x7b5c  ldarg.0
0x7b5d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__5`1<var<u1>>::<>t__builder
0x7b62  ldloc.1
0x7b63  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetResult(var<u1>)
0x7b68  ret
```
