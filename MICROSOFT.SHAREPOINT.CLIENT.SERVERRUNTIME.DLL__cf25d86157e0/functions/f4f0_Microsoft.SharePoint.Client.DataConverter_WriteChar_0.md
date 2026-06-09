# Microsoft.SharePoint.Client.DataConverter::WriteChar_0

- ea: `0xf4f0`
- end: `0xf51c`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteChar_0`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xf4f0`
- `0x13410`
- `0x13460`

## string_xrefs

- `0xf4f3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf4f0  ldarg.0
0xf4f1  brtrue.s loc_F4FE
0xf4f3  ldstr    aWriter// "writer"
0xf4f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf4fd  throw
0xf4fe  ldarga.s 1
0xf500  call     instance bool valuetype [mscorlib]System.Nullable`1<char>::get_HasValue()
0xf505  brfalse.s loc_F515
0xf507  ldarg.0
0xf508  ldarga.s 1
0xf50a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<char>::GetValueOrDefault()
0xf50f  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(char value)
0xf514  ret
0xf515  ldarg.0
0xf516  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0xf51b  ret
```
