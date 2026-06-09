# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadListStart

- ea: `0x6dc0`
- end: `0x6dd7`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadListStart`
- size: `23`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1de0`
- `0x2310`
- `0x2350`
- `0x2390`
- `0x3000`
- `0x3050`
- `0x3090`
- `0x30d0`
- `0x3120`
- `0x3160`
- `0x31b0`
- `0x31f0`
- `0x3230`
- `0x3270`
- `0x32b0`
- `0x3a30`
- `0x3a80`
- `0x3ac0`
- `0x3be0`
- `0x3c30`

## callees

- `0x6dc0`
- `0x70f0`

## pseudocode

```c

```

## disassembly

```asm
0x6dc0  ldarg.0
0x6dc1  call     instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadObjectType()
0x6dc6  brtrue.s loc_6DCD
0x6dc8  ldarg.2
0x6dc9  ldc.i4.m1
0x6dca  stind.i4
0x6dcb  ldc.i4.0
0x6dcc  ret
0x6dcd  ldarg.2
0x6dce  ldarg.0
0x6dcf  call     instance int32 [mscorlib]System.IO.BinaryReader::Read7BitEncodedInt()
0x6dd4  stind.i4
0x6dd5  ldc.i4.1
0x6dd6  ret
```
