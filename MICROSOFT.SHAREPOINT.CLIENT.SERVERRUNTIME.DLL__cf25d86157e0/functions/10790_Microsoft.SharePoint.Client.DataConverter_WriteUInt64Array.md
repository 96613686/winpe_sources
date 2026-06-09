# Microsoft.SharePoint.Client.DataConverter::WriteUInt64Array

- ea: `0x10790`
- end: `0x107d0`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteUInt64Array`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x107e0`

## callees

- `0x10790`
- `0x13030`
- `0x13210`
- `0x13410`
- `0x134d0`

## string_xrefs

- `0x10793`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x10790  ldarg.0
0x10791  brtrue.s loc_1079E
0x10793  ldstr    aWriter// "writer"
0x10798  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1079d  throw
0x1079e  ldarg.1
0x1079f  brtrue.s loc_107A8
0x107a1  ldarg.0
0x107a2  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x107a7  ret
0x107a8  ldarg.0
0x107a9  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x107ae  ldarg.1
0x107af  stloc.1
0x107b0  ldc.i4.0
0x107b1  stloc.2
0x107b2  br.s     loc_107C3
0x107b4  ldloc.1
0x107b5  ldloc.2
0x107b6  ldelem.i8
0x107b7  stloc.0
0x107b8  ldarg.0
0x107b9  ldloc.0
0x107ba  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(unsigned int64 value)
0x107bf  ldloc.2
0x107c0  ldc.i4.1
0x107c1  add
0x107c2  stloc.2
0x107c3  ldloc.2
0x107c4  ldloc.1
0x107c5  ldlen
0x107c6  conv.i4
0x107c7  blt.s    loc_107B4
0x107c9  ldarg.0
0x107ca  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x107cf  ret
```
