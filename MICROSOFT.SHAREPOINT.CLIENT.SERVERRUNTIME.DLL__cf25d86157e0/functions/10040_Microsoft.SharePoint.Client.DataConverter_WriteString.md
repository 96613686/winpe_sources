# Microsoft.SharePoint.Client.DataConverter::WriteString

- ea: `0x10040`
- end: `0x10056`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteString`
- size: `22`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10070`
- `0x34750`
- `0x34910`
- `0x34ae0`
- `0x34f80`
- `0x35170`

## callees

- `0x10040`
- `0x13720`

## string_xrefs

- `0x10043`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x10040  ldarg.0
0x10041  brtrue.s loc_1004E
0x10043  ldstr    aWriter// "writer"
0x10048  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1004d  throw
0x1004e  ldarg.0
0x1004f  ldarg.1
0x10050  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0x10055  ret
```
