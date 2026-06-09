# Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator::ConvertFirstDateLiteralToTernary

- ea: `0x80`
- end: `0xc7`
- name: `Microsoft.ReportingServices.RdlExpressions.SafeExpressions.ExpressionEvaluator::ConvertFirstDateLiteralToTernary`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x20`

## callees

- `0x80`

## pseudocode

```c

```

## disassembly

```asm
0x80  ldarg.1
0x81  ldstr    asc_4000// "#"
0x86  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x8b  brtrue.s loc_8F
0x8d  ldarg.1
0x8e  ret
0x8f  ldarg.1
0x90  ldstr    asc_4000// "#"
0x95  ldc.i4.1
0x96  callvirt instance int32 [mscorlib]System.String::IndexOf(string, int32)
0x9b  stloc.0
0x9c  ldloc.0
0x9d  ldc.i4.m1
0x9e  bne.un.s loc_A2
0xa0  ldarg.1
0xa1  ret
0xa2  ldloc.0
0xa3  ldc.i4.1
0xa4  add
0xa5  stloc.1
0xa6  ldarg.1
0xa7  ldc.i4.0
0xa8  ldloc.1
0xa9  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xae  stloc.2
0xaf  ldstr    aIfTrue// "If(True, "
0xb4  ldloc.2
0xb5  ldstr    aNothing// ", Nothing)"
0xba  ldarg.1
0xbb  ldloc.1
0xbc  callvirt instance string [mscorlib]System.String::Substring(int32)
0xc1  call     string [mscorlib]System.String::Concat(string, string, string, string)
0xc6  ret
```
