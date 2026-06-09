# Microsoft.SharePoint.Client.DataConverter::WriteInt16Array

- ea: `0x10330`
- end: `0x10370`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteInt16Array`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10380`

## callees

- `0x10330`
- `0x13030`
- `0x13210`
- `0x13410`
- `0x13470`

## string_xrefs

- `0x10333`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x10330  ldarg.0
0x10331  brtrue.s loc_1033E
0x10333  ldstr    aWriter// "writer"
0x10338  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1033d  throw
0x1033e  ldarg.1
0x1033f  brtrue.s loc_10348
0x10341  ldarg.0
0x10342  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x10347  ret
0x10348  ldarg.0
0x10349  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x1034e  ldarg.1
0x1034f  stloc.1
0x10350  ldc.i4.0
0x10351  stloc.2
0x10352  br.s     loc_10363
0x10354  ldloc.1
0x10355  ldloc.2
0x10356  ldelem.i2
0x10357  stloc.0
0x10358  ldarg.0
0x10359  ldloc.0
0x1035a  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int32 value)
0x1035f  ldloc.2
0x10360  ldc.i4.1
0x10361  add
0x10362  stloc.2
0x10363  ldloc.2
0x10364  ldloc.1
0x10365  ldlen
0x10366  conv.i4
0x10367  blt.s    loc_10354
0x10369  ldarg.0
0x1036a  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x1036f  ret
```
