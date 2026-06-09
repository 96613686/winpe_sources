# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadDictionaryStart

- ea: `0x6de0`
- end: `0x6df7`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadDictionaryStart`
- size: `23`
- prototype: ``
- caller_count: `28`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2460`
- `0x24a0`
- `0x24e0`
- `0x2520`
- `0x2570`
- `0x2730`
- `0x2780`
- `0x27d0`
- `0x2820`
- `0x2880`
- `0x28f0`
- `0x2960`
- `0x29d0`
- `0x2a40`
- `0x2ab0`
- `0x2b00`
- `0x2b90`
- `0x2be0`
- `0x2c80`
- `0x2cf0`
- `0x2d40`
- `0x2d90`
- `0x2de0`
- `0x2e30`
- `0x2e80`
- `0x2ed0`
- `0x2f40`
- `0x2fb0`

## callees

- `0x6de0`
- `0x70f0`

## pseudocode

```c

```

## disassembly

```asm
0x6de0  ldarg.0
0x6de1  call     instance valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryReader::ReadObjectType()
0x6de6  brtrue.s loc_6DED
0x6de8  ldarg.2
0x6de9  ldc.i4.m1
0x6dea  stind.i4
0x6deb  ldc.i4.0
0x6dec  ret
0x6ded  ldarg.2
0x6dee  ldarg.0
0x6def  call     instance int32 [mscorlib]System.IO.BinaryReader::Read7BitEncodedInt()
0x6df4  stind.i4
0x6df5  ldc.i4.1
0x6df6  ret
```
