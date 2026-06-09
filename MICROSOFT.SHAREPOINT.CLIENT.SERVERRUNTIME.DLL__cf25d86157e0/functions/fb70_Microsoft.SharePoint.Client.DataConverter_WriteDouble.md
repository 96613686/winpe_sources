# Microsoft.SharePoint.Client.DataConverter::WriteDouble

- ea: `0xfb70`
- end: `0xfb86`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteDouble`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xfbd0`
- `0xfc90`

## callees

- `0xfb70`
- `0x13510`

## string_xrefs

- `0xfb73`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xfb70  ldarg.0
0xfb71  brtrue.s loc_FB7E
0xfb73  ldstr    aWriter// "writer"
0xfb78  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfb7d  throw
0xfb7e  ldarg.0
0xfb7f  ldarg.1
0xfb80  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(float64 value)
0xfb85  ret
```
