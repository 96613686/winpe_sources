# Microsoft.SharePoint.Client.DataConverter::WriteTimeSpan_0

- ea: `0xfde0`
- end: `0xfe0c`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteTimeSpan_0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xfde0`
- `0x13410`
- `0x13550`

## string_xrefs

- `0xfde3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xfde0  ldarg.0
0xfde1  brtrue.s loc_FDEE
0xfde3  ldstr    aWriter// "writer"
0xfde8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfded  throw
0xfdee  ldarga.s 1
0xfdf0  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan>::get_HasValue()
0xfdf5  brfalse.s loc_FE05
0xfdf7  ldarg.0
0xfdf8  ldarga.s 1
0xfdfa  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan>::GetValueOrDefault()
0xfdff  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(valuetype [mscorlib]System.TimeSpan value)
0xfe04  ret
0xfe05  ldarg.0
0xfe06  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xfe0b  ret
```
