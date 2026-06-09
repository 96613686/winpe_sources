# Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::WriteDictionaryStart

- ea: `0x7400`
- end: `0x740f`
- name: `Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.PersistenceBinaryWriter::WriteDictionaryStart`
- size: `15`
- prototype: ``
- caller_count: `23`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x4140`
- `0x41a0`
- `0x4220`
- `0x42a0`
- `0x4320`
- `0x43b0`
- `0x4440`
- `0x44d0`
- `0x4550`
- `0x45e0`
- `0x4670`
- `0x4700`
- `0x4780`
- `0x4830`
- `0x48c0`
- `0x4940`
- `0x49b0`
- `0x4a20`
- `0x4aa0`
- `0x4b30`
- `0x4bb0`
- `0x4c30`
- `0x4cb0`

## pseudocode

```c

```

## disassembly

```asm
0x7400  ldarg.0
0x7401  ldarg.1
0x7402  call     instance void [mscorlib]System.IO.BinaryWriter::Write7BitEncodedInt(int32)
0x7407  ldarg.0
0x7408  ldarg.2
0x7409  call     instance void [mscorlib]System.IO.BinaryWriter::Write7BitEncodedInt(int32)
0x740e  ret
```
