# Microsoft.SharePoint.Client.DataConverter::WriteBoolean_0

- ea: `0xf440`
- end: `0xf46c`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteBoolean_0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xf440`
- `0x13410`
- `0x13420`

## string_xrefs

- `0xf443`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf440  ldarg.0
0xf441  brtrue.s loc_F44E
0xf443  ldstr    aWriter// "writer"
0xf448  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf44d  throw
0xf44e  ldarga.s 1
0xf450  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xf455  brfalse.s loc_F465
0xf457  ldarg.0
0xf458  ldarga.s 1
0xf45a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0xf45f  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(bool value)
0xf464  ret
0xf465  ldarg.0
0xf466  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xf46b  ret
```
