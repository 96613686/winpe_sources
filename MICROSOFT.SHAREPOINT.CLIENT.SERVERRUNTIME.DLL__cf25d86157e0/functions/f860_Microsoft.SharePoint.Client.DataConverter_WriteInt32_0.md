# Microsoft.SharePoint.Client.DataConverter::WriteInt32_0

- ea: `0xf860`
- end: `0xf88c`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteInt32_0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xf860`
- `0x13410`
- `0x13470`

## string_xrefs

- `0xf863`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf860  ldarg.0
0xf861  brtrue.s loc_F86E
0xf863  ldstr    aWriter// "writer"
0xf868  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf86d  throw
0xf86e  ldarga.s 1
0xf870  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xf875  brfalse.s loc_F885
0xf877  ldarg.0
0xf878  ldarga.s 1
0xf87a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0xf87f  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int32 value)
0xf884  ret
0xf885  ldarg.0
0xf886  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xf88b  ret
```
