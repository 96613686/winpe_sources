# <>c::<Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable.Deserialize>b__27_0

- ea: `0x3a9c0`
- end: `0x3aa17`
- name: `<>c::<Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable.Deserialize>b__27_0`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xdd50`
- `0x3a9c0`

## string_xrefs

- `0x3a9db`: `ComputedColumnExpression`

## pseudocode

```c

```

## disassembly

```asm
0x3a9c0  ldarg.1
0x3a9c1  ldstr    aDbcolumnname// "DbColumnName"
0x3a9c6  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x3a9cb  brfalse.s loc_3AA15
0x3a9cd  ldarg.1
0x3a9ce  ldstr    aDbdatatype// "DbDataType"
0x3a9d3  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x3a9d8  brfalse.s loc_3AA15
0x3a9da  ldarg.1
0x3a9db  ldstr    aComputedcolumn// "ComputedColumnExpression"
0x3a9e0  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x3a9e5  brfalse.s loc_3AA15
0x3a9e7  ldarg.1
0x3a9e8  ldstr    aNullablekey// "NullableKey"
0x3a9ed  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x3a9f2  brfalse.s loc_3AA15
0x3a9f4  ldarg.1
0x3a9f5  ldstr    aIsblob// "IsBlob"
0x3a9fa  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x3a9ff  brfalse.s loc_3AA15
0x3aa01  ldarg.1
0x3aa02  ldstr    aDatasize// "DataSize"
0x3aa07  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x3aa0c  brfalse.s loc_3AA15
0x3aa0e  ldarg.1
0x3aa0f  call     bool Microsoft.ReportingServices.Modeling.DsvItem::AllowExtendedPropertyForBinaryDeserialization(string name)
0x3aa14  ret
0x3aa15  ldc.i4.1
0x3aa16  ret
```
