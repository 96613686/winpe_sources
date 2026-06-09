# Microsoft.SharePoint.Client.DataConverter::WriteStringCollection

- ea: `0x10e40`
- end: `0x10e97`
- name: `Microsoft.SharePoint.Client.DataConverter::WriteStringCollection`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10eb0`

## callees

- `0x10e40`
- `0x13030`
- `0x13210`
- `0x13410`
- `0x13720`

## string_xrefs

- `0x10e43`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x10e40  ldarg.0
0x10e41  brtrue.s loc_10E4E
0x10e43  ldstr    aWriter// "writer"
0x10e48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10e4d  throw
0x10e4e  ldarg.1
0x10e4f  brtrue.s loc_10E58
0x10e51  ldarg.0
0x10e52  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteNullValue()
0x10e57  ret
0x10e58  ldarg.0
0x10e59  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::StartArrayScope()
0x10e5e  ldarg.1
0x10e5f  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0x10e64  stloc.1
0x10e65  br.s     loc_10E75
0x10e67  ldloc.1
0x10e68  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0x10e6d  stloc.0
0x10e6e  ldarg.0
0x10e6f  ldloc.0
0x10e70  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::WriteValue(string s)
0x10e75  ldloc.1
0x10e76  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0x10e7b  brtrue.s loc_10E67
0x10e7d  leave.s  loc_10E90
0x10e7f  ldloc.1
0x10e80  isinst   [mscorlib]System.IDisposable
0x10e85  stloc.2
0x10e86  ldloc.2
0x10e87  brfalse.s loc_10E8F
0x10e89  ldloc.2
0x10e8a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10e8f  endfinally
0x10e90  ldarg.0
0x10e91  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::EndScope()
0x10e96  ret
```
