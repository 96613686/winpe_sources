# Microsoft.SharePoint.Client.DataConverter::WriteUInt16_0

- ea: `0xf7b0`
- end: `0xf7dc`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteUInt16_0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xf7b0`
- `0x13410`
- `0x13470`

## string_xrefs

- `0xf7b3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf7b0  ldarg.0
0xf7b1  brtrue.s loc_F7BE
0xf7b3  ldstr    aWriter// "writer"
0xf7b8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf7bd  throw
0xf7be  ldarga.s 1
0xf7c0  call     instance bool valuetype [mscorlib]System.Nullable`1<unsigned int16>::get_HasValue()
0xf7c5  brfalse.s loc_F7D5
0xf7c7  ldarg.0
0xf7c8  ldarga.s 1
0xf7ca  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<unsigned int16>::GetValueOrDefault()
0xf7cf  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int32 value)
0xf7d4  ret
0xf7d5  ldarg.0
0xf7d6  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xf7db  ret
```
