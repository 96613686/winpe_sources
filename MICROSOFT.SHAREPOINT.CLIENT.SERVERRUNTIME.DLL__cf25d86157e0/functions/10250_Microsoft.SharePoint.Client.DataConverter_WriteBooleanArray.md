# Microsoft.SharePoint.Client.DataConverter::WriteBooleanArray

- ea: `0x10250`
- end: `0x10290`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteBooleanArray`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x102a0`

## callees

- `0x10250`
- `0x13030`
- `0x13210`
- `0x13410`
- `0x13420`

## string_xrefs

- `0x10253`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x10250  ldarg.0
0x10251  brtrue.s loc_1025E
0x10253  ldstr    aWriter// "writer"
0x10258  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1025d  throw
0x1025e  ldarg.1
0x1025f  brtrue.s loc_10268
0x10261  ldarg.0
0x10262  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x10267  ret
0x10268  ldarg.0
0x10269  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x1026e  ldarg.1
0x1026f  stloc.1
0x10270  ldc.i4.0
0x10271  stloc.2
0x10272  br.s     loc_10283
0x10274  ldloc.1
0x10275  ldloc.2
0x10276  ldelem.i1
0x10277  stloc.0
0x10278  ldarg.0
0x10279  ldloc.0
0x1027a  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(bool value)
0x1027f  ldloc.2
0x10280  ldc.i4.1
0x10281  add
0x10282  stloc.2
0x10283  ldloc.2
0x10284  ldloc.1
0x10285  ldlen
0x10286  conv.i4
0x10287  blt.s    loc_10274
0x10289  ldarg.0
0x1028a  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x1028f  ret
```
