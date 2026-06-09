# Microsoft.SharePoint.Client.DataConverter::WriteSByte

- ea: `0xf630`
- end: `0xf646`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteSByte`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf690`

## callees

- `0xf630`
- `0x13470`

## string_xrefs

- `0xf633`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf630  ldarg.0
0xf631  brtrue.s loc_F63E
0xf633  ldstr    aWriter// "writer"
0xf638  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf63d  throw
0xf63e  ldarg.0
0xf63f  ldarg.1
0xf640  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int32 value)
0xf645  ret
```
