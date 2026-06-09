# Microsoft.SharePoint.Client.ClientServiceHost::get_UrlPathPartitionOrDefault

- ea: `0xe0b0`
- end: `0xe0e6`
- name: `Microsoft.SharePoint.Client.ClientServiceHost::get_UrlPathPartitionOrDefault`
- size: `54`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xe080`
- `0x15f10`
- `0x15f50`
- `0x15fb0`

## callees

- `0xe010`
- `0xe0b0`

## string_xrefs

- `0xe0bf`: `UrlPathPartition was not initialized for the callstack {0}.`

## pseudocode

```c

```

## disassembly

```asm
0xe0b0  ldarg.0
0xe0b1  ldfld    string Microsoft.SharePoint.Client.ClientServiceHost::m_urlPathPartition
0xe0b6  brtrue.s loc_E0DF
0xe0b8  ldarg.0
0xe0b9  ldc.i4   0x64C54E
0xe0be  ldc.i4.1
0xe0bf  ldstr    aUrlpathpartiti// "UrlPathPartition was not initialized fo"...
0xe0c4  ldc.i4.1
0xe0c5  newarr   [mscorlib]System.Object
0xe0ca  stloc.0
0xe0cb  ldloc.0
0xe0cc  ldc.i4.0
0xe0cd  newobj   instance void [mscorlib]System.Diagnostics.StackTrace::.ctor()
0xe0d2  stelem.ref
0xe0d3  ldloc.0
0xe0d4  call     instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0xe0d9  ldsfld   string [mscorlib]System.String::Empty
0xe0de  ret
0xe0df  ldarg.0
0xe0e0  ldfld    string Microsoft.SharePoint.Client.ClientServiceHost::m_urlPathPartition
0xe0e5  ret
```
