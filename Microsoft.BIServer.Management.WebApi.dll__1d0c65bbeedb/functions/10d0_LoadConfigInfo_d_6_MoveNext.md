# <LoadConfigInfo>d__6::MoveNext

- ea: `0x10d0`
- end: `0x116b`
- name: `<LoadConfigInfo>d__6::MoveNext`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x10d0`

## pseudocode

```c

```

## disassembly

```asm
0x10d0  ldarg.0
0x10d1  ldfld    int32 <LoadConfigInfo>d__6::<>1__state
0x10d6  stloc.0
0x10d7  ldloc.0
0x10d8  brfalse.s loc_1119
0x10da  ldarg.0
0x10db  ldfld    class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess <LoadConfigInfo>d__6::sqlAccess
0x10e0  newobj   instance void [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.ConfigurationInfoDataAccessor::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Storage.ISqlAccess)
0x10e5  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> [Microsoft.ReportingServices.CatalogAccess]Microsoft.ReportingServices.CatalogAccess.ConfigurationInfoDataAccessor::GetConfigInfoValuesAsync()
0x10ea  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>::GetAwaiter()
0x10ef  stloc.2
0x10f0  ldloca.s 2
0x10f2  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>::get_IsCompleted()
0x10f7  brtrue.s loc_1135
0x10f9  ldarg.0
0x10fa  ldc.i4.0
0x10fb  dup
0x10fc  stloc.0
0x10fd  stfld    int32 <LoadConfigInfo>d__6::<>1__state
0x1102  ldarg.0
0x1103  ldloc.2
0x1104  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> <LoadConfigInfo>d__6::<>u__1
0x1109  ldarg.0
0x110a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> <LoadConfigInfo>d__6::<>t__builder
0x110f  ldloca.s 2
0x1111  ldarg.0
0x1112  call     T0x2B000011
0x1117  leave.s  loc_116A
0x1119  ldarg.0
0x111a  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> <LoadConfigInfo>d__6::<>u__1
0x111f  stloc.2
0x1120  ldarg.0
0x1121  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> <LoadConfigInfo>d__6::<>u__1
0x1126  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>
0x112c  ldarg.0
0x112d  ldc.i4.m1
0x112e  dup
0x112f  stloc.0
0x1130  stfld    int32 <LoadConfigInfo>d__6::<>1__state
0x1135  ldloca.s 2
0x1137  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>::GetResult()
0x113c  stloc.1
0x113d  leave.s  loc_1156
0x113f  stloc.3
0x1140  ldarg.0
0x1141  ldc.i4.s 0xFE
0x1143  stfld    int32 <LoadConfigInfo>d__6::<>1__state
0x1148  ldarg.0
0x1149  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> <LoadConfigInfo>d__6::<>t__builder
0x114e  ldloc.3
0x114f  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>::SetException(class [mscorlib]System.Exception)
0x1154  leave.s  loc_116A
0x1156  ldarg.0
0x1157  ldc.i4.s 0xFE
0x1159  stfld    int32 <LoadConfigInfo>d__6::<>1__state
0x115e  ldarg.0
0x115f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>> <LoadConfigInfo>d__6::<>t__builder
0x1164  ldloc.1
0x1165  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>>::SetResult(var<u1>)
0x116a  ret
```
