# <ExecuteAsync>d__6::MoveNext

- ea: `0x7b90`
- end: `0x7c59`
- name: `<ExecuteAsync>d__6::MoveNext`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x67f0`
- `0x7b90`

## pseudocode

```c

```

## disassembly

```asm
0x7b90  ldarg.0
0x7b91  ldfld    int32 <ExecuteAsync>d__6::<>1__state
0x7b96  stloc.0
0x7b97  ldloc.0
0x7b98  brfalse.s loc_7BA5
0x7b9a  ldarg.0
0x7b9b  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection Microsoft.BIServer.Configuration.Catalog.CatalogAccessFactory::NewConnection()
0x7ba0  stfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess <ExecuteAsync>d__6::<sqlAccess>5__2
0x7ba5  nop
0x7ba6  ldloc.0
0x7ba7  brfalse.s loc_7BEF
0x7ba9  ldarg.0
0x7baa  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess <ExecuteAsync>d__6::<sqlAccess>5__2
0x7baf  ldarg.0
0x7bb0  ldfld    string <ExecuteAsync>d__6::storedProcedureName
0x7bb5  ldarg.0
0x7bb6  ldfld    object <ExecuteAsync>d__6::parameters
0x7bbb  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess::ExecuteAsync(string, object)
0x7bc0  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0x7bc5  stloc.2
0x7bc6  ldloca.s 2
0x7bc8  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0x7bcd  brtrue.s loc_7C0B
0x7bcf  ldarg.0
0x7bd0  ldc.i4.0
0x7bd1  dup
0x7bd2  stloc.0
0x7bd3  stfld    int32 <ExecuteAsync>d__6::<>1__state
0x7bd8  ldarg.0
0x7bd9  ldloc.2
0x7bda  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ExecuteAsync>d__6::<>u__1
0x7bdf  ldarg.0
0x7be0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__6::<>t__builder
0x7be5  ldloca.s 2
0x7be7  ldarg.0
0x7be8  call     T0x2B00004B
0x7bed  leave.s  loc_7C58
0x7bef  ldarg.0
0x7bf0  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ExecuteAsync>d__6::<>u__1
0x7bf5  stloc.2
0x7bf6  ldarg.0
0x7bf7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <ExecuteAsync>d__6::<>u__1
0x7bfc  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0x7c02  ldarg.0
0x7c03  ldc.i4.m1
0x7c04  dup
0x7c05  stloc.0
0x7c06  stfld    int32 <ExecuteAsync>d__6::<>1__state
0x7c0b  ldloca.s 2
0x7c0d  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0x7c12  stloc.1
0x7c13  leave.s  loc_7C44
0x7c15  ldloc.0
0x7c16  ldc.i4.0
0x7c17  bge.s    loc_7C2C
0x7c19  ldarg.0
0x7c1a  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess <ExecuteAsync>d__6::<sqlAccess>5__2
0x7c1f  brfalse.s loc_7C2C
0x7c21  ldarg.0
0x7c22  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess <ExecuteAsync>d__6::<sqlAccess>5__2
0x7c27  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7c2c  endfinally
0x7c2d  stloc.3
0x7c2e  ldarg.0
0x7c2f  ldc.i4.s 0xFE
0x7c31  stfld    int32 <ExecuteAsync>d__6::<>1__state
0x7c36  ldarg.0
0x7c37  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__6::<>t__builder
0x7c3c  ldloc.3
0x7c3d  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::SetException(class [mscorlib]System.Exception)
0x7c42  leave.s  loc_7C58
0x7c44  ldarg.0
0x7c45  ldc.i4.s 0xFE
0x7c47  stfld    int32 <ExecuteAsync>d__6::<>1__state
0x7c4c  ldarg.0
0x7c4d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__6::<>t__builder
0x7c52  ldloc.1
0x7c53  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::SetResult(var<u1>)
0x7c58  ret
```
