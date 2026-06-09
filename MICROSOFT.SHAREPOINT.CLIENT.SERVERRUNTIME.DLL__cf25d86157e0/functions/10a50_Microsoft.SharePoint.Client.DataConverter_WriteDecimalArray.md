# Microsoft.SharePoint.Client.DataConverter::WriteDecimalArray

- ea: `0x10a50`
- end: `0x10a99`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteDecimalArray`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10ab0`

## callees

- `0x10a50`
- `0x13030`
- `0x13210`
- `0x13410`
- `0x13530`

## string_xrefs

- `0x10a53`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x10a50  ldarg.0
0x10a51  brtrue.s loc_10A5E
0x10a53  ldstr    aWriter// "writer"
0x10a58  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10a5d  throw
0x10a5e  ldarg.1
0x10a5f  brtrue.s loc_10A68
0x10a61  ldarg.0
0x10a62  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x10a67  ret
0x10a68  ldarg.0
0x10a69  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x10a6e  ldarg.1
0x10a6f  stloc.1
0x10a70  ldc.i4.0
0x10a71  stloc.2
0x10a72  br.s     loc_10A8C
0x10a74  ldloc.1
0x10a75  ldloc.2
0x10a76  ldelema  [mscorlib]System.Decimal
0x10a7b  ldobj    [mscorlib]System.Decimal
0x10a80  stloc.0
0x10a81  ldarg.0
0x10a82  ldloc.0
0x10a83  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(valuetype [mscorlib]System.Decimal value)
0x10a88  ldloc.2
0x10a89  ldc.i4.1
0x10a8a  add
0x10a8b  stloc.2
0x10a8c  ldloc.2
0x10a8d  ldloc.1
0x10a8e  ldlen
0x10a8f  conv.i4
0x10a90  blt.s    loc_10A74
0x10a92  ldarg.0
0x10a93  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x10a98  ret
```
