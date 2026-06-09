# Microsoft.SharePoint.Client.DataConverter::WriteGuid

- ea: `0xffa0`
- end: `0xffb6`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteGuid`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10000`

## callees

- `0xffa0`
- `0x13740`

## string_xrefs

- `0xffa3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xffa0  ldarg.0
0xffa1  brtrue.s loc_FFAE
0xffa3  ldstr    aWriter// "writer"
0xffa8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xffad  throw
0xffae  ldarg.0
0xffaf  ldarg.1
0xffb0  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(valuetype [mscorlib]System.Guid guid)
0xffb5  ret
```
