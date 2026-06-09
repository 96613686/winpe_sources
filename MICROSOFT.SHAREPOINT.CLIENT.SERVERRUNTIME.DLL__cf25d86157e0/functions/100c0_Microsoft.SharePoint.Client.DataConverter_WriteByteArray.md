# Microsoft.SharePoint.Client.DataConverter::WriteByteArray

- ea: `0x100c0`
- end: `0x100d6`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteByteArray`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100f0`

## callees

- `0x100c0`
- `0x13770`

## string_xrefs

- `0x100c3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x100c0  ldarg.0
0x100c1  brtrue.s loc_100CE
0x100c3  ldstr    aWriter// "writer"
0x100c8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x100cd  throw
0x100ce  ldarg.0
0x100cf  ldarg.1
0x100d0  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(unsigned int8[] bytes)
0x100d5  ret
```
