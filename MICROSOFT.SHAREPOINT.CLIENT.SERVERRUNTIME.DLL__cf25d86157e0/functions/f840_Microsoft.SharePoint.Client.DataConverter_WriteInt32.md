# Microsoft.SharePoint.Client.DataConverter::WriteInt32

- ea: `0xf840`
- end: `0xf856`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteInt32`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf8a0`

## callees

- `0xf840`
- `0x13470`

## string_xrefs

- `0xf843`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf840  ldarg.0
0xf841  brtrue.s loc_F84E
0xf843  ldstr    aWriter// "writer"
0xf848  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf84d  throw
0xf84e  ldarg.0
0xf84f  ldarg.1
0xf850  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int32 value)
0xf855  ret
```
