# Microsoft.CommonSchema.Services.Logging.CorrelationVector::Equals

- ea: `0xd00`
- end: `0xd17`
- name: `Microsoft.CommonSchema.Services.Logging.CorrelationVector::Equals`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0xc90`
- `0xd00`

## pseudocode

```c

```

## disassembly

```asm
0xd00  ldarg.1
0xd01  brtrue.s loc_D05
0xd03  ldc.i4.0
0xd04  ret
0xd05  ldarg.0
0xd06  call     instance string Microsoft.CommonSchema.Services.Logging.CorrelationVector::get_Value()
0xd0b  ldarg.1
0xd0c  callvirt instance string Microsoft.CommonSchema.Services.Logging.CorrelationVector::get_Value()
0xd11  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd16  ret
```
