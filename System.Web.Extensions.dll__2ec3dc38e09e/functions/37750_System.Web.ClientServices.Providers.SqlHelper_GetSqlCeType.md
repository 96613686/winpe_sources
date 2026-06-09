# System.Web.ClientServices.Providers.SqlHelper::GetSqlCeType

- ea: `0x37750`
- end: `0x377d1`
- name: `System.Web.ClientServices.Providers.SqlHelper::GetSqlCeType`
- size: `129`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x375f0`
- `0x377e0`
- `0x37830`

## callees

- `0x37750`

## string_xrefs

- `0x37779`: `, System.Data.SqlServerCe, Version=3.5.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91`
- `0x377bf`: `, System.Data.SqlServerCe, Version=3.5.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91`
- `0x3779c`: `, System.Data.SqlServerCe, Version=3.0.3600.0, Culture=neutral, PublicKeyToken=3be235df1c8d2ad3`

## pseudocode

```c

```

## disassembly

```asm
0x37750  ldstr    aSystemDataSqls// "System.Data.SqlServerCe."
0x37755  ldarg.0
0x37756  ldstr    aSystemDataSqls_0// ", System.Data.SqlServerCe"
0x3775b  call     string [mscorlib]System.String::Concat(string, string, string)
0x37760  ldc.i4.0
0x37761  ldc.i4.1
0x37762  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool, bool)
0x37767  stloc.0
0x37768  ldloc.0
0x37769  ldnull
0x3776a  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x3776f  brfalse.s loc_37773
0x37771  ldloc.0
0x37772  ret
0x37773  ldstr    aSystemDataSqls// "System.Data.SqlServerCe."
0x37778  ldarg.0
0x37779  ldstr    aSystemDataSqls_1// ", System.Data.SqlServerCe, Version=3.5."...
0x3777e  call     string [mscorlib]System.String::Concat(string, string, string)
0x37783  ldc.i4.0
0x37784  ldc.i4.1
0x37785  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool, bool)
0x3778a  stloc.0
0x3778b  ldloc.0
0x3778c  ldnull
0x3778d  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x37792  brfalse.s loc_37796
0x37794  ldloc.0
0x37795  ret
0x37796  ldstr    aSystemDataSqls// "System.Data.SqlServerCe."
0x3779b  ldarg.0
0x3779c  ldstr    aSystemDataSqls_2// ", System.Data.SqlServerCe, Version=3.0."...
0x377a1  call     string [mscorlib]System.String::Concat(string, string, string)
0x377a6  ldc.i4.0
0x377a7  ldc.i4.1
0x377a8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool, bool)
0x377ad  stloc.0
0x377ae  ldloc.0
0x377af  ldnull
0x377b0  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x377b5  brfalse.s loc_377B9
0x377b7  ldloc.0
0x377b8  ret
0x377b9  ldstr    aSystemDataSqls// "System.Data.SqlServerCe."
0x377be  ldarg.0
0x377bf  ldstr    aSystemDataSqls_1// ", System.Data.SqlServerCe, Version=3.5."...
0x377c4  call     string [mscorlib]System.String::Concat(string, string, string)
0x377c9  ldc.i4.1
0x377ca  ldc.i4.1
0x377cb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool, bool)
0x377d0  ret
```
