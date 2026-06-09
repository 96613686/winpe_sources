# Microsoft.SharePoint.Client.DataConverter::WriteInt64Array

- ea: `0x106b0`
- end: `0x106f0`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteInt64Array`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10700`

## callees

- `0x106b0`
- `0x13030`
- `0x13210`
- `0x13410`
- `0x134b0`

## string_xrefs

- `0x106b3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x106b0  ldarg.0
0x106b1  brtrue.s loc_106BE
0x106b3  ldstr    aWriter// "writer"
0x106b8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x106bd  throw
0x106be  ldarg.1
0x106bf  brtrue.s loc_106C8
0x106c1  ldarg.0
0x106c2  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x106c7  ret
0x106c8  ldarg.0
0x106c9  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x106ce  ldarg.1
0x106cf  stloc.1
0x106d0  ldc.i4.0
0x106d1  stloc.2
0x106d2  br.s     loc_106E3
0x106d4  ldloc.1
0x106d5  ldloc.2
0x106d6  ldelem.i8
0x106d7  stloc.0
0x106d8  ldarg.0
0x106d9  ldloc.0
0x106da  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(int64 value)
0x106df  ldloc.2
0x106e0  ldc.i4.1
0x106e1  add
0x106e2  stloc.2
0x106e3  ldloc.2
0x106e4  ldloc.1
0x106e5  ldlen
0x106e6  conv.i4
0x106e7  blt.s    loc_106D4
0x106e9  ldarg.0
0x106ea  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x106ef  ret
```
