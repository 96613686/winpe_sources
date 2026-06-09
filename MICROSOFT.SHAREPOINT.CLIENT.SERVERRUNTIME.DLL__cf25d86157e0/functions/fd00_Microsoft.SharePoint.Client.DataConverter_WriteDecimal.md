# Microsoft.SharePoint.Client.DataConverter::WriteDecimal

- ea: `0xfd00`
- end: `0xfd16`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteDecimal`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xfd60`

## callees

- `0xfd00`
- `0x13530`

## string_xrefs

- `0xfd03`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xfd00  ldarg.0
0xfd01  brtrue.s loc_FD0E
0xfd03  ldstr    aWriter// "writer"
0xfd08  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfd0d  throw
0xfd0e  ldarg.0
0xfd0f  ldarg.1
0xfd10  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(valuetype [mscorlib]System.Decimal value)
0xfd15  ret
```
