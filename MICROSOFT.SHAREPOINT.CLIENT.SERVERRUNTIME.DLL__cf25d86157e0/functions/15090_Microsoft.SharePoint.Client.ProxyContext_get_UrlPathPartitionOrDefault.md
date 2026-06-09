# Microsoft.SharePoint.Client.ProxyContext::get_UrlPathPartitionOrDefault

- ea: `0x15090`
- end: `0x150cb`
- name: `Microsoft.SharePoint.Client.ProxyContext::get_UrlPathPartitionOrDefault`
- size: `59`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x48d0`
- `0x19f80`
- `0x1b600`

## callees

- `0xe010`
- `0x15070`
- `0x15090`
- `0x152f0`

## string_xrefs

- `0x150a4`: `UrlPathPartition was not initialized for the callstack {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x15090  ldarg.0
0x15091  call     instance string Microsoft.SharePoint.Client.ProxyContext::get_UrlPathPartition()
0x15096  brtrue.s loc_150C4
0x15098  ldarg.0
0x15099  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x1509e  ldc.i4   0x64C54F
0x150a3  ldc.i4.1
0x150a4  ldstr    aUrlpathpartiti// "UrlPathPartition was not initialized fo"...
0x150a9  ldc.i4.1
0x150aa  newarr   [mscorlib]System.Object
0x150af  stloc.0
0x150b0  ldloc.0
0x150b1  ldc.i4.0
0x150b2  newobj   instance void [mscorlib]System.Diagnostics.StackTrace::.ctor()
0x150b7  stelem.ref
0x150b8  ldloc.0
0x150b9  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x150be  ldsfld   string [mscorlib]System.String::Empty
0x150c3  ret
0x150c4  ldarg.0
0x150c5  call     instance string Microsoft.SharePoint.Client.ProxyContext::get_UrlPathPartition()
0x150ca  ret
```
