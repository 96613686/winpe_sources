# Microsoft.SharePoint.Client.JsonUtility::SerializeToJson_0

- ea: `0x13a40`
- end: `0x13a77`
- name: `Microsoft.SharePoint.Client.JsonUtility::SerializeToJson_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x13a00`

## callees

- `0x11ef0`
- `0x13000`
- `0x13880`
- `0x13a40`
- `0x14f70`

## string_xrefs

- `0x13a43`: `writer`

## pseudocode

```c

```

## disassembly

```asm
0x13a40  ldarg.1
0x13a41  brtrue.s loc_13A4E
0x13a43  ldstr    aWriter// "writer"
0x13a48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13a4d  throw
0x13a4e  ldarg.1
0x13a4f  newobj   instance void Microsoft.SharePoint.Client.JsonWriter::.ctor(class [mscorlib]System.IO.TextWriter writer)
0x13a54  stloc.0
0x13a55  newobj   instance void Microsoft.SharePoint.Client.ProxyContext::.ctor()
0x13a5a  stloc.1
0x13a5b  ldloc.0
0x13a5c  ldarg.0
0x13a5d  ldloc.1
0x13a5e  ldarg.2
0x13a5f  call     void Microsoft.SharePoint.Client.DataConverter::WriteAsJson(class Microsoft.SharePoint.Client.JsonWriter writer, object obj, class Microsoft.SharePoint.Client.ProxyContext proxyContext, class Microsoft.SharePoint.Client.JsonSerializationOptions options)
0x13a64  ldloc.0
0x13a65  callvirt instance void Microsoft.SharePoint.Client.JsonWriter::Flush()
0x13a6a  leave.s  loc_13A76
0x13a6c  ldloc.0
0x13a6d  brfalse.s loc_13A75
0x13a6f  ldloc.0
0x13a70  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13a75  endfinally
0x13a76  ret
```
