# Microsoft.SharePoint.Client.DataConverter::WriteUInt32

- ea: `0xf8f0`
- end: `0xf906`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteUInt32`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf950`

## callees

- `0xf8f0`
- `0x13490`

## string_xrefs

- `0xf8f3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xf8f0  ldarg.0
0xf8f1  brtrue.s loc_F8FE
0xf8f3  ldstr    aWriter// "writer"
0xf8f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf8fd  throw
0xf8fe  ldarg.0
0xf8ff  ldarg.1
0xf900  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(unsigned int32 value)
0xf905  ret
```
