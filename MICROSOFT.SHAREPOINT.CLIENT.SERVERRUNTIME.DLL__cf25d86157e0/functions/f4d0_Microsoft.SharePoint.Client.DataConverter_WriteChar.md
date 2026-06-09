# Microsoft.SharePoint.Client.DataConverter::WriteChar

- ea: `0xf4d0`
- end: `0xf4e6`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteChar`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf530`

## callees

- `0xf4d0`
- `0x13460`

## string_xrefs

- `0xf4d3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf4d0  ldarg.0
0xf4d1  brtrue.s loc_F4DE
0xf4d3  ldstr    aWriter// "writer"
0xf4d8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf4dd  throw
0xf4de  ldarg.0
0xf4df  ldarg.1
0xf4e0  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(char value)
0xf4e5  ret
```
