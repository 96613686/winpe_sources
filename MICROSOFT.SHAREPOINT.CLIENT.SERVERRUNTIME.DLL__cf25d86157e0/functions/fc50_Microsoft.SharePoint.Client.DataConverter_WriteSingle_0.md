# Microsoft.SharePoint.Client.DataConverter::WriteSingle_0

- ea: `0xfc50`
- end: `0xfc7d`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteSingle_0`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xfc50`
- `0x13410`
- `0x13510`

## string_xrefs

- `0xfc53`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xfc50  ldarg.0
0xfc51  brtrue.s loc_FC5E
0xfc53  ldstr    aWriter// "writer"
0xfc58  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfc5d  throw
0xfc5e  ldarga.s 1
0xfc60  call     instance bool valuetype [mscorlib]System.Nullable`1<float32>::get_HasValue()
0xfc65  brfalse.s loc_FC76
0xfc67  ldarg.0
0xfc68  ldarga.s 1
0xfc6a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<float32>::GetValueOrDefault()
0xfc6f  conv.r8
0xfc70  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(float64 value)
0xfc75  ret
0xfc76  ldarg.0
0xfc77  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xfc7c  ret
```
