# Microsoft.SharePoint.Client.DataConverter::WriteTimeSpan

- ea: `0xfdc0`
- end: `0xfdd6`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteTimeSpan`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xfe20`

## callees

- `0xfdc0`
- `0x13550`

## string_xrefs

- `0xfdc3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xfdc0  ldarg.0
0xfdc1  brtrue.s loc_FDCE
0xfdc3  ldstr    aWriter// "writer"
0xfdc8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfdcd  throw
0xfdce  ldarg.0
0xfdcf  ldarg.1
0xfdd0  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(valuetype [mscorlib]System.TimeSpan value)
0xfdd5  ret
```
