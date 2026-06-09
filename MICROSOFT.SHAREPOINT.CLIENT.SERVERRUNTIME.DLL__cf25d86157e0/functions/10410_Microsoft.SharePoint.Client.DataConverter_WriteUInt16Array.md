# Microsoft.SharePoint.Client.DataConverter::WriteUInt16Array

- ea: `0x10410`
- end: `0x10450`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteUInt16Array`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10460`

## callees

- `0x10410`
- `0x13030`
- `0x13210`
- `0x13410`
- `0x13470`

## string_xrefs

- `0x10413`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x10410  ldarg.0
0x10411  brtrue.s loc_1041E
0x10413  ldstr    aWriter// "writer"
0x10418  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1041d  throw
0x1041e  ldarg.1
0x1041f  brtrue.s loc_10428
0x10421  ldarg.0
0x10422  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x10427  ret
0x10428  ldarg.0
0x10429  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x1042e  ldarg.1
0x1042f  stloc.1
0x10430  ldc.i4.0
0x10431  stloc.2
0x10432  br.s     loc_10443
0x10434  ldloc.1
0x10435  ldloc.2
0x10436  ldelem.u2
0x10437  stloc.0
0x10438  ldarg.0
0x10439  ldloc.0
0x1043a  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int32 value)
0x1043f  ldloc.2
0x10440  ldc.i4.1
0x10441  add
0x10442  stloc.2
0x10443  ldloc.2
0x10444  ldloc.1
0x10445  ldlen
0x10446  conv.i4
0x10447  blt.s    loc_10434
0x10449  ldarg.0
0x1044a  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x1044f  ret
```
