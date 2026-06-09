# <QueryAsync>d__3`1::MoveNext

- ea: `0x78c0`
- end: `0x798e`
- name: `<QueryAsync>d__3`1::MoveNext`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x67f0`
- `0x78c0`

## pseudocode

```c

```

## disassembly

```asm
0x78c0  ldarg.0
0x78c1  ldfld    int32 valuetype <QueryAsync>d__3`1<var<u1>>::<>1__state
0x78c6  stloc.0
0x78c7  ldloc.0
0x78c8  brfalse.s loc_78D5
0x78ca  ldarg.0
0x78cb  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection Microsoft.BIServer.Configuration.Catalog.CatalogAccessFactory::NewConnection()
0x78d0  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess valuetype <QueryAsync>d__3`1<var<u1>>::<sqlAccess>5__2
0x78d5  nop
0x78d6  ldloc.0
0x78d7  brfalse.s loc_791F
0x78d9  ldarg.0
0x78da  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess valuetype <QueryAsync>d__3`1<var<u1>>::<sqlAccess>5__2
0x78df  ldarg.0
0x78e0  ldfld    string valuetype <QueryAsync>d__3`1<var<u1>>::storedProcedureName
0x78e5  ldarg.0
0x78e6  ldfld    object valuetype <QueryAsync>d__3`1<var<u1>>::parameters
0x78eb  callvirt T0x2B000044
0x78f0  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>>::GetAwaiter()
0x78f5  stloc.2
0x78f6  ldloca.s 2
0x78f8  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>>::get_IsCompleted()
0x78fd  brtrue.s loc_793B
0x78ff  ldarg.0
0x7900  ldc.i4.0
0x7901  dup
0x7902  stloc.0
0x7903  stfld    int32 valuetype <QueryAsync>d__3`1<var<u1>>::<>1__state
0x7908  ldarg.0
0x7909  ldloc.2
0x790a  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>> valuetype <QueryAsync>d__3`1<var<u1>>::<>u__1
0x790f  ldarg.0
0x7910  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<var<u1>>> valuetype <QueryAsync>d__3`1<var<u1>>::<>t__builder
0x7915  ldloca.s 2
0x7917  ldarg.0
0x7918  call     T0x2B000045
0x791d  leave.s  loc_798D
0x791f  ldarg.0
0x7920  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>> valuetype <QueryAsync>d__3`1<var<u1>>::<>u__1
0x7925  stloc.2
0x7926  ldarg.0
0x7927  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>> valuetype <QueryAsync>d__3`1<var<u1>>::<>u__1
0x792c  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>>
0x7932  ldarg.0
0x7933  ldc.i4.m1
0x7934  dup
0x7935  stloc.0
0x7936  stfld    int32 valuetype <QueryAsync>d__3`1<var<u1>>::<>1__state
0x793b  ldloca.s 2
0x793d  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>>::GetResult()
0x7942  call     T0x2B000046
0x7947  stloc.1
0x7948  leave.s  loc_7979
0x794a  ldloc.0
0x794b  ldc.i4.0
0x794c  bge.s    loc_7961
0x794e  ldarg.0
0x794f  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess valuetype <QueryAsync>d__3`1<var<u1>>::<sqlAccess>5__2
0x7954  brfalse.s loc_7961
0x7956  ldarg.0
0x7957  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess valuetype <QueryAsync>d__3`1<var<u1>>::<sqlAccess>5__2
0x795c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7961  endfinally
0x7962  stloc.3
0x7963  ldarg.0
0x7964  ldc.i4.s 0xFE
0x7966  stfld    int32 valuetype <QueryAsync>d__3`1<var<u1>>::<>1__state
0x796b  ldarg.0
0x796c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<var<u1>>> valuetype <QueryAsync>d__3`1<var<u1>>::<>t__builder
0x7971  ldloc.3
0x7972  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<var<u1>>>::SetException(class [mscorlib]System.Exception)
0x7977  leave.s  loc_798D
0x7979  ldarg.0
0x797a  ldc.i4.s 0xFE
0x797c  stfld    int32 valuetype <QueryAsync>d__3`1<var<u1>>::<>1__state
0x7981  ldarg.0
0x7982  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<var<u1>>> valuetype <QueryAsync>d__3`1<var<u1>>::<>t__builder
0x7987  ldloc.1
0x7988  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<var<u1>>>::SetResult(var<u1>)
0x798d  ret
```
