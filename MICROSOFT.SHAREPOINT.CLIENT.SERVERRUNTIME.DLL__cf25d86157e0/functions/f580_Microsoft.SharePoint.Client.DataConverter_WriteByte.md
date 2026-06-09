# Microsoft.SharePoint.Client.DataConverter::WriteByte

- ea: `0xf580`
- end: `0xf596`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteByte`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf5e0`

## callees

- `0xf580`
- `0x13470`

## string_xrefs

- `0xf583`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf580  ldarg.0
0xf581  brtrue.s loc_F58E
0xf583  ldstr    aWriter// "writer"
0xf588  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf58d  throw
0xf58e  ldarg.0
0xf58f  ldarg.1
0xf590  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int32 value)
0xf595  ret
```
