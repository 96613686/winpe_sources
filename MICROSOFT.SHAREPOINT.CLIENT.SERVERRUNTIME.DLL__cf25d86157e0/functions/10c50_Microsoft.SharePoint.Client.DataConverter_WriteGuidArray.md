# Microsoft.SharePoint.Client.DataConverter::WriteGuidArray

- ea: `0x10c50`
- end: `0x10c99`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteGuidArray`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10cb0`

## callees

- `0x10c50`
- `0x13030`
- `0x13210`
- `0x13410`
- `0x13740`

## string_xrefs

- `0x10c53`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x10c50  ldarg.0
0x10c51  brtrue.s loc_10C5E
0x10c53  ldstr    aWriter// "writer"
0x10c58  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10c5d  throw
0x10c5e  ldarg.1
0x10c5f  brtrue.s loc_10C68
0x10c61  ldarg.0
0x10c62  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x10c67  ret
0x10c68  ldarg.0
0x10c69  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x10c6e  ldarg.1
0x10c6f  stloc.1
0x10c70  ldc.i4.0
0x10c71  stloc.2
0x10c72  br.s     loc_10C8C
0x10c74  ldloc.1
0x10c75  ldloc.2
0x10c76  ldelema  [mscorlib]System.Guid
0x10c7b  ldobj    [mscorlib]System.Guid
0x10c80  stloc.0
0x10c81  ldarg.0
0x10c82  ldloc.0
0x10c83  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(valuetype [mscorlib]System.Guid guid)
0x10c88  ldloc.2
0x10c89  ldc.i4.1
0x10c8a  add
0x10c8b  stloc.2
0x10c8c  ldloc.2
0x10c8d  ldloc.1
0x10c8e  ldlen
0x10c8f  conv.i4
0x10c90  blt.s    loc_10C74
0x10c92  ldarg.0
0x10c93  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x10c98  ret
```
