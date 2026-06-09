# Microsoft.SharePoint.Client.Rest.RestService::InitUrlPathPartitionAndAdjustPath

- ea: `0x277f0`
- end: `0x2782d`
- name: `Microsoft.SharePoint.Client.Rest.RestService::InitUrlPathPartitionAndAdjustPath`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x267f0`

## callees

- `0xe010`
- `0xe070`
- `0x16760`

## string_xrefs

- `0x27803`: `Set partition='{0}' and adjust path from '{1}' to '{2}'`

## pseudocode

```c

```

## disassembly

```asm
0x277f0  ldarg.1
0x277f1  ldarg.2
0x277f2  ldind.ref
0x277f3  ldloca.s 0
0x277f5  ldloca.s 1
0x277f7  call     void Microsoft.SharePoint.Client.ProxyMap::GetUrlPathPartitionAndAdjustedPath(class Microsoft.SharePoint.Client.ClientServiceHost serviceHost, string path, [out] string& partition, [out] string& newPath)
0x277fc  ldarg.1
0x277fd  ldc.i4   0x64C554
0x27802  ldc.i4.3
0x27803  ldstr    aSetPartition0A// "Set partition='{0}' and adjust path fro"...
0x27808  ldc.i4.3
0x27809  newarr   [mscorlib]System.Object
0x2780e  stloc.2
0x2780f  ldloc.2
0x27810  ldc.i4.0
0x27811  ldloc.0
0x27812  stelem.ref
0x27813  ldloc.2
0x27814  ldc.i4.1
0x27815  ldarg.2
0x27816  ldind.ref
0x27817  stelem.ref
0x27818  ldloc.2
0x27819  ldc.i4.2
0x2781a  ldloc.1
0x2781b  stelem.ref
0x2781c  ldloc.2
0x2781d  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x27822  ldarg.1
0x27823  ldloc.0
0x27824  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::set_RESTfulRequestPathPartition(string value)
0x27829  ldarg.2
0x2782a  ldloc.1
0x2782b  stind.ref
0x2782c  ret
```
