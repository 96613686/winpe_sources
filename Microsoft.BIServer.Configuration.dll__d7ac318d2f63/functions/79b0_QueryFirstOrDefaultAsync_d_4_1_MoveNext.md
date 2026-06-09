# <QueryFirstOrDefaultAsync>d__4`1::MoveNext

- ea: `0x79b0`
- end: `0x7a73`
- name: `<QueryFirstOrDefaultAsync>d__4`1::MoveNext`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x67f0`
- `0x79b0`

## pseudocode

```c

```

## disassembly

```asm
0x79b0  ldarg.0
0x79b1  ldfld    int32 valuetype <QueryFirstOrDefaultAsync>d__4`1<var<u1>>::<>1__state
0x79b6  stloc.0
0x79b7  ldloc.0
0x79b8  brfalse.s loc_79C5
0x79ba  ldarg.0
0x79bb  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection Microsoft.BIServer.Configuration.Catalog.CatalogAccessFactory::NewConnection()
0x79c0  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess valuetype <QueryFirstOrDefaultAsync>d__4`1<var<u1>>::<sqlAccess>5__2
0x79c5  nop
0x79c6  ldloc.0
0x79c7  brfalse.s loc_7A09
0x79c9  ldarg.0
0x79ca  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess valuetype <QueryFirstOrDefaultAsync>d__4`1<var<u1>>::<sqlAccess>5__2
0x79cf  ldarg.0
0x79d0  ldfld    string valuetype <QueryFirstOrDefaultAsync>d__4`1<var<u1>>::storedProcedureName
0x79d5  callvirt T0x2B000047
0x79da  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<var<u1>>::GetAwaiter()
0x79df  stloc.2
0x79e0  ldloca.s 2
0x79e2  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>::get_IsCompleted()
0x79e7  brtrue.s loc_7A25
0x79e9  ldarg.0
0x79ea  ldc.i4.0
0x79eb  dup
0x79ec  stloc.0
0x79ed  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__4`1<var<u1>>::<>1__state
0x79f2  ldarg.0
0x79f3  ldloc.2
0x79f4  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__4`1<var<u1>>::<>u__1
0x79f9  ldarg.0
0x79fa  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__4`1<var<u1>>::<>t__builder
0x79ff  ldloca.s 2
0x7a01  ldarg.0
0x7a02  call     T0x2B000048
0x7a07  leave.s  loc_7A72
0x7a09  ldarg.0
0x7a0a  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__4`1<var<u1>>::<>u__1
0x7a0f  stloc.2
0x7a10  ldarg.0
0x7a11  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__4`1<var<u1>>::<>u__1
0x7a16  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>
0x7a1c  ldarg.0
0x7a1d  ldc.i4.m1
0x7a1e  dup
0x7a1f  stloc.0
0x7a20  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__4`1<var<u1>>::<>1__state
0x7a25  ldloca.s 2
0x7a27  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>>::GetResult()
0x7a2c  stloc.1
0x7a2d  leave.s  loc_7A5E
0x7a2f  ldloc.0
0x7a30  ldc.i4.0
0x7a31  bge.s    loc_7A46
0x7a33  ldarg.0
0x7a34  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess valuetype <QueryFirstOrDefaultAsync>d__4`1<var<u1>>::<sqlAccess>5__2
0x7a39  brfalse.s loc_7A46
0x7a3b  ldarg.0
0x7a3c  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess valuetype <QueryFirstOrDefaultAsync>d__4`1<var<u1>>::<sqlAccess>5__2
0x7a41  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7a46  endfinally
0x7a47  stloc.3
0x7a48  ldarg.0
0x7a49  ldc.i4.s 0xFE
0x7a4b  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__4`1<var<u1>>::<>1__state
0x7a50  ldarg.0
0x7a51  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__4`1<var<u1>>::<>t__builder
0x7a56  ldloc.3
0x7a57  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetException(class [mscorlib]System.Exception)
0x7a5c  leave.s  loc_7A72
0x7a5e  ldarg.0
0x7a5f  ldc.i4.s 0xFE
0x7a61  stfld    int32 valuetype <QueryFirstOrDefaultAsync>d__4`1<var<u1>>::<>1__state
0x7a66  ldarg.0
0x7a67  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype <QueryFirstOrDefaultAsync>d__4`1<var<u1>>::<>t__builder
0x7a6c  ldloc.1
0x7a6d  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>>::SetResult(var<u1>)
0x7a72  ret
```
