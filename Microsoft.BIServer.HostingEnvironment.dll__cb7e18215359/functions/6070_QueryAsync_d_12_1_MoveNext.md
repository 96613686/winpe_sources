# <QueryAsync>d__12`1::MoveNext

- ea: `0x6070`
- end: `0x6196`
- name: `<QueryAsync>d__12`1::MoveNext`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1490`
- `0x1be0`
- `0x2c30`
- `0x6070`

## string_xrefs

- `0x6157`: `Exception during db access`

## pseudocode

```c

```

## disassembly

```asm
0x6070  ldarg.0
0x6071  ldfld    int32 valuetype <QueryAsync>d__12`1<var<u1>>::<>1__state
0x6076  stloc.0
0x6077  ldarg.0
0x6078  ldfld    class Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection valuetype <QueryAsync>d__12`1<var<u1>>::<>4__this
0x607d  stloc.1
0x607e  ldloc.0
0x607f  pop
0x6080  nop
0x6081  ldloc.0
0x6082  brfalse.s loc_60BA
0x6084  ldloc.1
0x6085  ldarg.0
0x6086  ldfld    string valuetype <QueryAsync>d__12`1<var<u1>>::storedProcedure
0x608b  call     instance void Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::StartStatementMeter(string storedProcedure)
0x6090  ldarg.0
0x6091  ldc.i4.3
0x6092  newarr   [mscorlib]System.String
0x6097  dup
0x6098  ldc.i4.0
0x6099  ldstr    aSql// "SQL"
0x609e  stelem.ref
0x609f  dup
0x60a0  ldc.i4.1
0x60a1  ldarg.0
0x60a2  ldfld    string valuetype <QueryAsync>d__12`1<var<u1>>::storedProcedure
0x60a7  stelem.ref
0x60a8  dup
0x60a9  ldc.i4.2
0x60aa  ldstr    aAsync// "async"
0x60af  stelem.ref
0x60b0  call     class [mscorlib]System.IDisposable Microsoft.BIServer.HostingEnvironment.ScopeMeter::Use(string[] names)
0x60b5  stfld    class [mscorlib]System.IDisposable valuetype <QueryAsync>d__12`1<var<u1>>::<>7__wrap1
0x60ba  nop
0x60bb  ldloc.0
0x60bc  brfalse.s loc_6119
0x60be  ldloc.1
0x60bf  ldfld    class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::_connection
0x60c4  ldarg.0
0x60c5  ldfld    string valuetype <QueryAsync>d__12`1<var<u1>>::storedProcedure
0x60ca  ldarg.0
0x60cb  ldfld    object valuetype <QueryAsync>d__12`1<var<u1>>::parameters
0x60d0  ldnull
0x60d1  ldc.i4.4
0x60d2  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [System.Data]System.Data.CommandType>::.ctor(var<u1>)
0x60d7  stloc.s  4
0x60d9  ldsfld   int32 Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::DatabaseQueryTimeout
0x60de  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x60e3  ldloc.s  4
0x60e5  call     T0x2B00003F
0x60ea  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>>::GetAwaiter()
0x60ef  stloc.3
0x60f0  ldloca.s 3
0x60f2  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>>::get_IsCompleted()
0x60f7  brtrue.s loc_6135
0x60f9  ldarg.0
0x60fa  ldc.i4.0
0x60fb  dup
0x60fc  stloc.0
0x60fd  stfld    int32 valuetype <QueryAsync>d__12`1<var<u1>>::<>1__state
0x6102  ldarg.0
0x6103  ldloc.3
0x6104  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>> valuetype <QueryAsync>d__12`1<var<u1>>::<>u__1
0x6109  ldarg.0
0x610a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>> valuetype <QueryAsync>d__12`1<var<u1>>::<>t__builder
0x610f  ldloca.s 3
0x6111  ldarg.0
0x6112  call     T0x2B000041
0x6117  leave.s  loc_6195
0x6119  ldarg.0
0x611a  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>> valuetype <QueryAsync>d__12`1<var<u1>>::<>u__1
0x611f  stloc.3
0x6120  ldarg.0
0x6121  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>> valuetype <QueryAsync>d__12`1<var<u1>>::<>u__1
0x6126  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>>
0x612c  ldarg.0
0x612d  ldc.i4.m1
0x612e  dup
0x612f  stloc.0
0x6130  stfld    int32 valuetype <QueryAsync>d__12`1<var<u1>>::<>1__state
0x6135  ldloca.s 3
0x6137  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>>::GetResult()
0x613c  stloc.2
0x613d  leave.s  loc_6181
0x613f  ldloc.0
0x6140  ldc.i4.0
0x6141  bge.s    loc_6156
0x6143  ldarg.0
0x6144  ldfld    class [mscorlib]System.IDisposable valuetype <QueryAsync>d__12`1<var<u1>>::<>7__wrap1
0x6149  brfalse.s loc_6156
0x614b  ldarg.0
0x614c  ldfld    class [mscorlib]System.IDisposable valuetype <QueryAsync>d__12`1<var<u1>>::<>7__wrap1
0x6151  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6156  endfinally
0x6157  ldstr    aExceptionDurin// "Exception during db access"
0x615c  call     T0x2B00000A
0x6161  call     void Microsoft.BIServer.HostingEnvironment.Logger::Debug(class [mscorlib]System.Exception ex, string formatString, object[] formatParams)
0x6166  rethrow
0x6168  stloc.s  5
0x616a  ldarg.0
0x616b  ldc.i4.s 0xFE
0x616d  stfld    int32 valuetype <QueryAsync>d__12`1<var<u1>>::<>1__state
0x6172  ldarg.0
0x6173  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>> valuetype <QueryAsync>d__12`1<var<u1>>::<>t__builder
0x6178  ldloc.s  5
0x617a  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>>::SetException(class [mscorlib]System.Exception)
0x617f  leave.s  loc_6195
0x6181  ldarg.0
0x6182  ldc.i4.s 0xFE
0x6184  stfld    int32 valuetype <QueryAsync>d__12`1<var<u1>>::<>1__state
0x6189  ldarg.0
0x618a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>> valuetype <QueryAsync>d__12`1<var<u1>>::<>t__builder
0x618f  ldloc.2
0x6190  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>>::SetResult(var<u1>)
0x6195  ret
```
