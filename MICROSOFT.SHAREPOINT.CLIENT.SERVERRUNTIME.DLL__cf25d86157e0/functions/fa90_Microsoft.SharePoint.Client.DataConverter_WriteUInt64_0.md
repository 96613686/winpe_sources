# Microsoft.SharePoint.Client.DataConverter::WriteUInt64_0

- ea: `0xfa90`
- end: `0xfabc`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteUInt64_0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xfa90`
- `0x13410`
- `0x134d0`

## string_xrefs

- `0xfa93`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xfa90  ldarg.0
0xfa91  brtrue.s loc_FA9E
0xfa93  ldstr    aWriter// "writer"
0xfa98  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfa9d  throw
0xfa9e  ldarga.s 1
0xfaa0  call     instance bool valuetype [mscorlib]System.Nullable`1<unsigned int64>::get_HasValue()
0xfaa5  brfalse.s loc_FAB5
0xfaa7  ldarg.0
0xfaa8  ldarga.s 1
0xfaaa  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<unsigned int64>::GetValueOrDefault()
0xfaaf  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(unsigned int64 value)
0xfab4  ret
0xfab5  ldarg.0
0xfab6  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xfabb  ret
```
