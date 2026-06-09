# Microsoft.SharePoint.Client.DataConverter::WriteGuid_0

- ea: `0xffc0`
- end: `0xffec`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteGuid_0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xffc0`
- `0x13410`
- `0x13740`

## string_xrefs

- `0xffc3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xffc0  ldarg.0
0xffc1  brtrue.s loc_FFCE
0xffc3  ldstr    aWriter// "writer"
0xffc8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xffcd  throw
0xffce  ldarga.s 1
0xffd0  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xffd5  brfalse.s loc_FFE5
0xffd7  ldarg.0
0xffd8  ldarga.s 1
0xffda  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0xffdf  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(valuetype [mscorlib]System.Guid guid)
0xffe4  ret
0xffe5  ldarg.0
0xffe6  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xffeb  ret
```
