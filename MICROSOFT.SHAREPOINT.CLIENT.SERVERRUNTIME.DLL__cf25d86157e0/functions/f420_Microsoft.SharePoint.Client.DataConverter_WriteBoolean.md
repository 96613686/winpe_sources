# Microsoft.SharePoint.Client.DataConverter::WriteBoolean

- ea: `0xf420`
- end: `0xf436`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteBoolean`
- size: `22`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf480`
- `0x34750`
- `0x34ae0`
- `0x34f80`
- `0x35170`

## callees

- `0xf420`
- `0x13420`

## string_xrefs

- `0xf423`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf420  ldarg.0
0xf421  brtrue.s loc_F42E
0xf423  ldstr    aWriter// "writer"
0xf428  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf42d  throw
0xf42e  ldarg.0
0xf42f  ldarg.1
0xf430  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(bool value)
0xf435  ret
```
