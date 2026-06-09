# Microsoft.SharePoint.Client.DataConverter::WriteDateTime_0

- ea: `0xff00`
- end: `0xff2c`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteDateTime_0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xff00`
- `0x13410`
- `0x13590`

## string_xrefs

- `0xff03`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xff00  ldarg.0
0xff01  brtrue.s loc_FF0E
0xff03  ldstr    aWriter// "writer"
0xff08  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xff0d  throw
0xff0e  ldarga.s 1
0xff10  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0xff15  brfalse.s loc_FF25
0xff17  ldarg.0
0xff18  ldarga.s 1
0xff1a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::GetValueOrDefault()
0xff1f  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(valuetype [mscorlib]System.DateTime dateTime)
0xff24  ret
0xff25  ldarg.0
0xff26  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xff2b  ret
```
