# Microsoft.SharePoint.Client.DataConverter::WriteDoubleArray

- ea: `0x10960`
- end: `0x109a1`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteDoubleArray`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x109c0`

## callees

- `0x10960`
- `0x13030`
- `0x13210`
- `0x13410`
- `0x13510`

## string_xrefs

- `0x10963`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x10960  ldarg.0
0x10961  brtrue.s loc_1096E
0x10963  ldstr    aWriter// "writer"
0x10968  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1096d  throw
0x1096e  ldarg.1
0x1096f  brtrue.s loc_10978
0x10971  ldarg.0
0x10972  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x10977  ret
0x10978  ldarg.0
0x10979  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x1097e  ldarg.1
0x1097f  stloc.1
0x10980  ldc.i4.0
0x10981  stloc.2
0x10982  br.s     loc_10994
0x10984  ldloc.1
0x10985  ldloc.2
0x10986  ldelem.r8
0x10987  conv.r8
0x10988  stloc.0
0x10989  ldarg.0
0x1098a  ldloc.0
0x1098b  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(float64 value)
0x10990  ldloc.2
0x10991  ldc.i4.1
0x10992  add
0x10993  stloc.2
0x10994  ldloc.2
0x10995  ldloc.1
0x10996  ldlen
0x10997  conv.i4
0x10998  blt.s    loc_10984
0x1099a  ldarg.0
0x1099b  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x109a0  ret
```
