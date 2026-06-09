# Microsoft.SharePoint.Client.DataConverter::WriteInt64_0

- ea: `0xf9d0`
- end: `0xf9fc`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteInt64_0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xf9d0`
- `0x13410`
- `0x134b0`

## string_xrefs

- `0xf9d3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf9d0  ldarg.0
0xf9d1  brtrue.s loc_F9DE
0xf9d3  ldstr    aWriter// "writer"
0xf9d8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf9dd  throw
0xf9de  ldarga.s 1
0xf9e0  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0xf9e5  brfalse.s loc_F9F5
0xf9e7  ldarg.0
0xf9e8  ldarga.s 1
0xf9ea  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::GetValueOrDefault()
0xf9ef  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int64 value)
0xf9f4  ret
0xf9f5  ldarg.0
0xf9f6  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xf9fb  ret
```
