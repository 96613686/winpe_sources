# Microsoft.SharePoint.Client.DataConverter::WriteDouble_0

- ea: `0xfb90`
- end: `0xfbbc`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteDouble_0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xfb90`
- `0x13410`
- `0x13510`

## string_xrefs

- `0xfb93`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xfb90  ldarg.0
0xfb91  brtrue.s loc_FB9E
0xfb93  ldstr    aWriter// "writer"
0xfb98  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfb9d  throw
0xfb9e  ldarga.s 1
0xfba0  call     instance bool valuetype [mscorlib]System.Nullable`1<float64>::get_HasValue()
0xfba5  brfalse.s loc_FBB5
0xfba7  ldarg.0
0xfba8  ldarga.s 1
0xfbaa  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<float64>::GetValueOrDefault()
0xfbaf  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(float64 value)
0xfbb4  ret
0xfbb5  ldarg.0
0xfbb6  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xfbbb  ret
```
