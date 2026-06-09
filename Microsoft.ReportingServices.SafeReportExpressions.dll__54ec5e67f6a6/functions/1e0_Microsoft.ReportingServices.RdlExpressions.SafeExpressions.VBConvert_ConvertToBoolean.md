# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VBConvert::ConvertToBoolean

- ea: `0x1e0`
- end: `0x21a`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VBConvert::ConvertToBoolean`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1560`

## callees

- `0x1c0`
- `0x1e0`

## pseudocode

```c

```

## disassembly

```asm
0x1e0  ldarg.0
0x1e1  brtrue.s loc_1E6
0x1e3  ldnull
0x1e4  br.s     loc_1EC
0x1e6  ldarg.0
0x1e7  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1ec  ldtoken  [mscorlib]System.String
0x1f1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1f6  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1fb  brfalse.s loc_213
0x1fd  ldarg.0
0x1fe  ldtoken  [mscorlib]System.Boolean
0x203  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x208  call     object Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VBConvert::ChangeType(object value, class [mscorlib]System.Type conversionType)
0x20d  unbox.any [mscorlib]System.Boolean
0x212  ret
0x213  ldarg.0
0x214  call     bool [mscorlib]System.Convert::ToBoolean(object)
0x219  ret
```
