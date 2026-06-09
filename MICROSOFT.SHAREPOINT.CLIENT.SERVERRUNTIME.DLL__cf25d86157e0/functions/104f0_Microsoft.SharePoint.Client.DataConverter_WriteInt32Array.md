# Microsoft.SharePoint.Client.DataConverter::WriteInt32Array

- ea: `0x104f0`
- end: `0x10530`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteInt32Array`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10540`

## callees

- `0x104f0`
- `0x13030`
- `0x13210`
- `0x13410`
- `0x13470`

## string_xrefs

- `0x104f3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x104f0  ldarg.0
0x104f1  brtrue.s loc_104FE
0x104f3  ldstr    aWriter// "writer"
0x104f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x104fd  throw
0x104fe  ldarg.1
0x104ff  brtrue.s loc_10508
0x10501  ldarg.0
0x10502  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x10507  ret
0x10508  ldarg.0
0x10509  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x1050e  ldarg.1
0x1050f  stloc.1
0x10510  ldc.i4.0
0x10511  stloc.2
0x10512  br.s     loc_10523
0x10514  ldloc.1
0x10515  ldloc.2
0x10516  ldelem.i4
0x10517  stloc.0
0x10518  ldarg.0
0x10519  ldloc.0
0x1051a  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int32 value)
0x1051f  ldloc.2
0x10520  ldc.i4.1
0x10521  add
0x10522  stloc.2
0x10523  ldloc.2
0x10524  ldloc.1
0x10525  ldlen
0x10526  conv.i4
0x10527  blt.s    loc_10514
0x10529  ldarg.0
0x1052a  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x1052f  ret
```
