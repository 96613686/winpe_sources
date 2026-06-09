# Microsoft.SharePoint.Client.DataConverter::WriteUInt32_0

- ea: `0xf910`
- end: `0xf93c`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteUInt32_0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xf910`
- `0x13410`
- `0x13490`

## string_xrefs

- `0xf913`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf910  ldarg.0
0xf911  brtrue.s loc_F91E
0xf913  ldstr    aWriter// "writer"
0xf918  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf91d  throw
0xf91e  ldarga.s 1
0xf920  call     instance bool valuetype [mscorlib]System.Nullable`1<unsigned int32>::get_HasValue()
0xf925  brfalse.s loc_F935
0xf927  ldarg.0
0xf928  ldarga.s 1
0xf92a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<unsigned int32>::GetValueOrDefault()
0xf92f  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(unsigned int32 value)
0xf934  ret
0xf935  ldarg.0
0xf936  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xf93b  ret
```
