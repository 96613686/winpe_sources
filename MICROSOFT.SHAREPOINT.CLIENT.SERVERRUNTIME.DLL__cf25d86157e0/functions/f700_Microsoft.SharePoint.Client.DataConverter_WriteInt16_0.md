# Microsoft.SharePoint.Client.DataConverter::WriteInt16_0

- ea: `0xf700`
- end: `0xf72c`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteInt16_0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xf700`
- `0x13410`
- `0x13470`

## string_xrefs

- `0xf703`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf700  ldarg.0
0xf701  brtrue.s loc_F70E
0xf703  ldstr    aWriter// "writer"
0xf708  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf70d  throw
0xf70e  ldarga.s 1
0xf710  call     instance bool valuetype [mscorlib]System.Nullable`1<int16>::get_HasValue()
0xf715  brfalse.s loc_F725
0xf717  ldarg.0
0xf718  ldarga.s 1
0xf71a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int16>::GetValueOrDefault()
0xf71f  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int32 value)
0xf724  ret
0xf725  ldarg.0
0xf726  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xf72b  ret
```
