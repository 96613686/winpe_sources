# Microsoft.SharePoint.Client.DataConverter::WriteSingleArray

- ea: `0x10870`
- end: `0x108b1`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteSingleArray`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x108d0`

## callees

- `0x10870`
- `0x13030`
- `0x13210`
- `0x13410`
- `0x134f0`

## string_xrefs

- `0x10873`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x10870  ldarg.0
0x10871  brtrue.s loc_1087E
0x10873  ldstr    aWriter// "writer"
0x10878  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1087d  throw
0x1087e  ldarg.1
0x1087f  brtrue.s loc_10888
0x10881  ldarg.0
0x10882  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x10887  ret
0x10888  ldarg.0
0x10889  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x1088e  ldarg.1
0x1088f  stloc.1
0x10890  ldc.i4.0
0x10891  stloc.2
0x10892  br.s     loc_108A4
0x10894  ldloc.1
0x10895  ldloc.2
0x10896  ldelem.r4
0x10897  conv.r4
0x10898  stloc.0
0x10899  ldarg.0
0x1089a  ldloc.0
0x1089b  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(float32 value)
0x108a0  ldloc.2
0x108a1  ldc.i4.1
0x108a2  add
0x108a3  stloc.2
0x108a4  ldloc.2
0x108a5  ldloc.1
0x108a6  ldlen
0x108a7  conv.i4
0x108a8  blt.s    loc_10894
0x108aa  ldarg.0
0x108ab  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x108b0  ret
```
