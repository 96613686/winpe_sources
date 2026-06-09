# Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::ExecuteReaderAsync

- ea: `0x2ae0`
- end: `0x2b31`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::ExecuteReaderAsync`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2ae0  ldloca.s 0
0x2ae2  ldarg.0
0x2ae3  stfld    class Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection <ExecuteReaderAsync>d__21::<>4__this
0x2ae8  ldloca.s 0
0x2aea  ldarg.1
0x2aeb  stfld    string <ExecuteReaderAsync>d__21::storedProcedure
0x2af0  ldloca.s 0
0x2af2  ldarg.2
0x2af3  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> <ExecuteReaderAsync>d__21::parameters
0x2af8  ldloca.s 0
0x2afa  ldarg.3
0x2afb  stfld    valuetype [System.Data]System.Data.CommandBehavior <ExecuteReaderAsync>d__21::commandBehavior
0x2b00  ldloca.s 0
0x2b02  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Data]System.Data.Common.DbDataReader>::Create()
0x2b07  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Data]System.Data.Common.DbDataReader> <ExecuteReaderAsync>d__21::<>t__builder
0x2b0c  ldloca.s 0
0x2b0e  ldc.i4.m1
0x2b0f  stfld    int32 <ExecuteReaderAsync>d__21::<>1__state
0x2b14  ldloc.0
0x2b15  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Data]System.Data.Common.DbDataReader> <ExecuteReaderAsync>d__21::<>t__builder
0x2b1a  stloc.1
0x2b1b  ldloca.s 1
0x2b1d  ldloca.s 0
0x2b1f  call     T0x2B00001D
0x2b24  ldloca.s 0
0x2b26  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Data]System.Data.Common.DbDataReader> <ExecuteReaderAsync>d__21::<>t__builder
0x2b2b  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Data]System.Data.Common.DbDataReader>::get_Task()
0x2b30  ret
```
