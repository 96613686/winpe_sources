# Microsoft.SharePoint.Client.DataConverter::WriteUInt64

- ea: `0xfa70`
- end: `0xfa86`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteUInt64`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xfad0`

## callees

- `0xfa70`
- `0x134d0`

## string_xrefs

- `0xfa73`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xfa70  ldarg.0
0xfa71  brtrue.s loc_FA7E
0xfa73  ldstr    aWriter// "writer"
0xfa78  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfa7d  throw
0xfa7e  ldarg.0
0xfa7f  ldarg.1
0xfa80  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(unsigned int64 value)
0xfa85  ret
```
