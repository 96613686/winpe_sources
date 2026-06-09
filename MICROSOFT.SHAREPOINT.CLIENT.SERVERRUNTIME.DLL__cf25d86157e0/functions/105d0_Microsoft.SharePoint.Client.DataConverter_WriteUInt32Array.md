# Microsoft.SharePoint.Client.DataConverter::WriteUInt32Array

- ea: `0x105d0`
- end: `0x10610`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteUInt32Array`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10620`

## callees

- `0x105d0`
- `0x13030`
- `0x13210`
- `0x13410`
- `0x13490`

## string_xrefs

- `0x105d3`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x105d0  ldarg.0
0x105d1  brtrue.s loc_105DE
0x105d3  ldstr    aWriter// "writer"
0x105d8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x105dd  throw
0x105de  ldarg.1
0x105df  brtrue.s loc_105E8
0x105e1  ldarg.0
0x105e2  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x105e7  ret
0x105e8  ldarg.0
0x105e9  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x105ee  ldarg.1
0x105ef  stloc.1
0x105f0  ldc.i4.0
0x105f1  stloc.2
0x105f2  br.s     loc_10603
0x105f4  ldloc.1
0x105f5  ldloc.2
0x105f6  ldelem.u4
0x105f7  stloc.0
0x105f8  ldarg.0
0x105f9  ldloc.0
0x105fa  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(unsigned int32 value)
0x105ff  ldloc.2
0x10600  ldc.i4.1
0x10601  add
0x10602  stloc.2
0x10603  ldloc.2
0x10604  ldloc.1
0x10605  ldlen
0x10606  conv.i4
0x10607  blt.s    loc_105F4
0x10609  ldarg.0
0x1060a  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x1060f  ret
```
