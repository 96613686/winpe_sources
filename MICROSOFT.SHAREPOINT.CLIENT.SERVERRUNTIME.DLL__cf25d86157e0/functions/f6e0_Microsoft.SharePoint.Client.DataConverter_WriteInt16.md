# Microsoft.SharePoint.Client.DataConverter::WriteInt16

- ea: `0xf6e0`
- end: `0xf6f6`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteInt16`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf740`

## callees

- `0xf6e0`
- `0x13470`

## string_xrefs

- `0xf6e3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf6e0  ldarg.0
0xf6e1  brtrue.s loc_F6EE
0xf6e3  ldstr    aWriter// "writer"
0xf6e8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf6ed  throw
0xf6ee  ldarg.0
0xf6ef  ldarg.1
0xf6f0  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int32 value)
0xf6f5  ret
```
