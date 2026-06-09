# Microsoft.SharePoint.Client.DataConverter::WriteDateTimeArray

- ea: `0x10b60`
- end: `0x10ba9`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteDateTimeArray`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10bc0`

## callees

- `0x10b60`
- `0x13030`
- `0x13210`
- `0x13410`
- `0x13590`

## string_xrefs

- `0x10b63`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x10b60  ldarg.0
0x10b61  brtrue.s loc_10B6E
0x10b63  ldstr    aWriter// "writer"
0x10b68  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10b6d  throw
0x10b6e  ldarg.1
0x10b6f  brtrue.s loc_10B78
0x10b71  ldarg.0
0x10b72  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x10b77  ret
0x10b78  ldarg.0
0x10b79  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x10b7e  ldarg.1
0x10b7f  stloc.1
0x10b80  ldc.i4.0
0x10b81  stloc.2
0x10b82  br.s     loc_10B9C
0x10b84  ldloc.1
0x10b85  ldloc.2
0x10b86  ldelema  [mscorlib]System.DateTime
0x10b8b  ldobj    [mscorlib]System.DateTime
0x10b90  stloc.0
0x10b91  ldarg.0
0x10b92  ldloc.0
0x10b93  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(valuetype [mscorlib]System.DateTime dateTime)
0x10b98  ldloc.2
0x10b99  ldc.i4.1
0x10b9a  add
0x10b9b  stloc.2
0x10b9c  ldloc.2
0x10b9d  ldloc.1
0x10b9e  ldlen
0x10b9f  conv.i4
0x10ba0  blt.s    loc_10B84
0x10ba2  ldarg.0
0x10ba3  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x10ba8  ret
```
