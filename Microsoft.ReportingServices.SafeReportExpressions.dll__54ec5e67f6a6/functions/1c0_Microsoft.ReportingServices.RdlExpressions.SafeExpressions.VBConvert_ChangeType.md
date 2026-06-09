# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VBConvert::ChangeType

- ea: `0x1c0`
- end: `0x1dc`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.VBConvert::ChangeType`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e0`

## callees

- `0x1c0`

## pseudocode

```c

```

## disassembly

```asm
0x1c0  ldarg.0
0x1c1  brtrue.s loc_1D4
0x1c3  ldarg.1
0x1c4  callvirt instance bool [mscorlib]System.Type::get_IsValueType()
0x1c9  brtrue.s loc_1CD
0x1cb  ldnull
0x1cc  ret
0x1cd  ldarg.1
0x1ce  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x1d3  ret
0x1d4  ldarg.0
0x1d5  ldarg.1
0x1d6  call     object [Microsoft.VisualBasic]Microsoft.VisualBasic.Conversion::CTypeDynamic(object, class [mscorlib]System.Type)
0x1db  ret
```
