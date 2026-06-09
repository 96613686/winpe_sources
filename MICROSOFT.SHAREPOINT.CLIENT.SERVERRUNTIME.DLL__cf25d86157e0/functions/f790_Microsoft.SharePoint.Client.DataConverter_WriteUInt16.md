# Microsoft.SharePoint.Client.DataConverter::WriteUInt16

- ea: `0xf790`
- end: `0xf7a6`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteUInt16`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf7f0`

## callees

- `0xf790`
- `0x13470`

## string_xrefs

- `0xf793`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf790  ldarg.0
0xf791  brtrue.s loc_F79E
0xf793  ldstr    aWriter// "writer"
0xf798  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf79d  throw
0xf79e  ldarg.0
0xf79f  ldarg.1
0xf7a0  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int32 value)
0xf7a5  ret
```
