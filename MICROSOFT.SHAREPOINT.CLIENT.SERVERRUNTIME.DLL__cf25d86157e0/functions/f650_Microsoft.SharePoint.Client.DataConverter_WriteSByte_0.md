# Microsoft.SharePoint.Client.DataConverter::WriteSByte_0

- ea: `0xf650`
- end: `0xf67c`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteSByte_0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xf650`
- `0x13410`
- `0x13470`

## string_xrefs

- `0xf653`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf650  ldarg.0
0xf651  brtrue.s loc_F65E
0xf653  ldstr    aWriter// "writer"
0xf658  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf65d  throw
0xf65e  ldarga.s 1
0xf660  call     instance bool valuetype [mscorlib]System.Nullable`1<int8>::get_HasValue()
0xf665  brfalse.s loc_F675
0xf667  ldarg.0
0xf668  ldarga.s 1
0xf66a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int8>::GetValueOrDefault()
0xf66f  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int32 value)
0xf674  ret
0xf675  ldarg.0
0xf676  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xf67b  ret
```
