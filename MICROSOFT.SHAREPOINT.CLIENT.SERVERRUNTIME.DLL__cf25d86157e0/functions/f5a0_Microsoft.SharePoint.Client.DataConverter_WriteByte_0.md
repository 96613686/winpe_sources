# Microsoft.SharePoint.Client.DataConverter::WriteByte_0

- ea: `0xf5a0`
- end: `0xf5cc`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteByte_0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xf5a0`
- `0x13410`
- `0x13470`

## string_xrefs

- `0xf5a3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf5a0  ldarg.0
0xf5a1  brtrue.s loc_F5AE
0xf5a3  ldstr    aWriter// "writer"
0xf5a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf5ad  throw
0xf5ae  ldarga.s 1
0xf5b0  call     instance bool valuetype [mscorlib]System.Nullable`1<unsigned int8>::get_HasValue()
0xf5b5  brfalse.s loc_F5C5
0xf5b7  ldarg.0
0xf5b8  ldarga.s 1
0xf5ba  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<unsigned int8>::GetValueOrDefault()
0xf5bf  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int32 value)
0xf5c4  ret
0xf5c5  ldarg.0
0xf5c6  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xf5cb  ret
```
