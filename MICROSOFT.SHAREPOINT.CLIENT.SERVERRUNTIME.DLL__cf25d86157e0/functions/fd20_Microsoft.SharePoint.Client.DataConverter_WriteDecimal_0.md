# Microsoft.SharePoint.Client.DataConverter::WriteDecimal_0

- ea: `0xfd20`
- end: `0xfd4c`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteDecimal_0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xfd20`
- `0x13410`
- `0x13530`

## string_xrefs

- `0xfd23`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xfd20  ldarg.0
0xfd21  brtrue.s loc_FD2E
0xfd23  ldstr    aWriter// "writer"
0xfd28  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfd2d  throw
0xfd2e  ldarga.s 1
0xfd30  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Decimal>::get_HasValue()
0xfd35  brfalse.s loc_FD45
0xfd37  ldarg.0
0xfd38  ldarga.s 1
0xfd3a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Decimal>::GetValueOrDefault()
0xfd3f  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(valuetype [mscorlib]System.Decimal value)
0xfd44  ret
0xfd45  ldarg.0
0xfd46  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xfd4b  ret
```
