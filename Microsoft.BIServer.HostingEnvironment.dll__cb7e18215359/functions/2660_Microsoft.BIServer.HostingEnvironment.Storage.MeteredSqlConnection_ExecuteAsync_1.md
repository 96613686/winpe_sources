# Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::ExecuteAsync_1

- ea: `0x2660`
- end: `0x26b1`
- name: `Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection::ExecuteAsync_1`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x5d10`
- `0x6700`

## pseudocode

```c

```

## disassembly

```asm
0x2660  ldloca.s 0
0x2662  ldarg.0
0x2663  stfld    class Microsoft.BIServer.HostingEnvironment.Storage.MeteredSqlConnection <ExecuteAsync>d__10::<>4__this
0x2668  ldloca.s 0
0x266a  ldarg.1
0x266b  stfld    string <ExecuteAsync>d__10::storedProcedure
0x2670  ldloca.s 0
0x2672  ldarg.2
0x2673  stfld    class [System.Data]System.Data.IDbTransaction <ExecuteAsync>d__10::transaction
0x2678  ldloca.s 0
0x267a  ldarg.3
0x267b  stfld    object <ExecuteAsync>d__10::parameters
0x2680  ldloca.s 0
0x2682  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::Create()
0x2687  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__10::<>t__builder
0x268c  ldloca.s 0
0x268e  ldc.i4.m1
0x268f  stfld    int32 <ExecuteAsync>d__10::<>1__state
0x2694  ldloc.0
0x2695  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__10::<>t__builder
0x269a  stloc.1
0x269b  ldloca.s 1
0x269d  ldloca.s 0
0x269f  call     T0x2B000017
0x26a4  ldloca.s 0
0x26a6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32> <ExecuteAsync>d__10::<>t__builder
0x26ab  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<int32>::get_Task()
0x26b0  ret
```
