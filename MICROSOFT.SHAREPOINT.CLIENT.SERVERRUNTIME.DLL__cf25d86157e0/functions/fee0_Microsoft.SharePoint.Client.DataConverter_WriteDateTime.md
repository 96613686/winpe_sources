# Microsoft.SharePoint.Client.DataConverter::WriteDateTime

- ea: `0xfee0`
- end: `0xfef6`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteDateTime`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xff40`

## callees

- `0xfee0`
- `0x13590`

## string_xrefs

- `0xfee3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0xfee0  ldarg.0
0xfee1  brtrue.s loc_FEEE
0xfee3  ldstr    aWriter// "writer"
0xfee8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfeed  throw
0xfeee  ldarg.0
0xfeef  ldarg.1
0xfef0  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(valuetype [mscorlib]System.DateTime dateTime)
0xfef5  ret
```
