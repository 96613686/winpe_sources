# Microsoft.SharePoint.Client.DataConverter::WriteStringArray

- ea: `0x10d40`
- end: `0x10d80`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteStringArray`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x10d40`
- `0x13030`
- `0x13210`
- `0x13410`
- `0x13720`

## string_xrefs

- `0x10d43`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x10d40  ldarg.0
0x10d41  brtrue.s loc_10D4E
0x10d43  ldstr    aWriter// "writer"
0x10d48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10d4d  throw
0x10d4e  ldarg.1
0x10d4f  brtrue.s loc_10D58
0x10d51  ldarg.0
0x10d52  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x10d57  ret
0x10d58  ldarg.0
0x10d59  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x10d5e  ldarg.1
0x10d5f  stloc.1
0x10d60  ldc.i4.0
0x10d61  stloc.2
0x10d62  br.s     loc_10D73
0x10d64  ldloc.1
0x10d65  ldloc.2
0x10d66  ldelem.ref
0x10d67  stloc.0
0x10d68  ldarg.0
0x10d69  ldloc.0
0x10d6a  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0x10d6f  ldloc.2
0x10d70  ldc.i4.1
0x10d71  add
0x10d72  stloc.2
0x10d73  ldloc.2
0x10d74  ldloc.1
0x10d75  ldlen
0x10d76  conv.i4
0x10d77  blt.s    loc_10D64
0x10d79  ldarg.0
0x10d7a  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x10d7f  ret
```
