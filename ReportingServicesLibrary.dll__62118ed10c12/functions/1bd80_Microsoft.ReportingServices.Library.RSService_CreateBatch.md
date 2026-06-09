# Microsoft.ReportingServices.Library.RSService::CreateBatch

- ea: `0x1bd80`
- end: `0x1bde6`
- name: `Microsoft.ReportingServices.Library.RSService::CreateBatch`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x3eb80`

## callees

- `0xcbe0`
- `0x1bd80`
- `0x1e0e0`
- `0x1e210`
- `0x1e3e0`
- `0x1e460`
- `0x1e510`

## string_xrefs

- `0x1bd8d`: `Call to CreateBatch()`
- `0x1bdc0`: `Call to CreateBatch completed, returning {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1bd80  ldarg.0
0x1bd81  call     instance void Microsoft.ReportingServices.Library.RSService::WillDisconnectStorage()
0x1bd86  ldarg.0
0x1bd87  call     instance class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.RSService::get_Tracer()
0x1bd8c  ldc.i4.4
0x1bd8d  ldstr    aCallToCreateba// "Call to CreateBatch()"
0x1bd92  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1bd97  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1bd9c  stloc.0
0x1bd9d  ldarg.0
0x1bd9e  call     instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.RSService::get_Storage()
0x1bda3  ldloc.0
0x1bda4  ldarg.0
0x1bda5  call     instance string Microsoft.ReportingServices.Library.RSService::get_UserName()
0x1bdaa  ldc.i4.0
0x1bdab  ldnull
0x1bdac  ldnull
0x1bdad  ldnull
0x1bdae  ldnull
0x1bdaf  ldnull
0x1bdb0  ldnull
0x1bdb1  ldc.i4.0
0x1bdb2  ldnull
0x1bdb3  ldnull
0x1bdb4  callvirt instance void Microsoft.ReportingServices.Library.IDBInterface::AddBatchRecord(valuetype [mscorlib]System.Guid batchId, string userName, valuetype Microsoft.ReportingServices.Library.CatalogCommand action, string item, string itemParameterName, string parent, string parentParameterName, string param, string paramParameterName, bool boolParam, unsigned int8[] content, string properties)
0x1bdb9  ldarg.0
0x1bdba  call     instance class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.RSService::get_Tracer()
0x1bdbf  ldc.i4.4
0x1bdc0  ldstr    aCallToCreateba_0// "Call to CreateBatch completed, returnin"...
0x1bdc5  ldc.i4.1
0x1bdc6  newarr   [mscorlib]System.Object
0x1bdcb  dup
0x1bdcc  ldc.i4.0
0x1bdcd  ldloc.0
0x1bdce  box      [mscorlib]System.Guid
0x1bdd3  stelem.ref
0x1bdd4  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1bdd9  ldloc.0
0x1bdda  stloc.1
0x1bddb  leave.s  loc_1BDE4
0x1bddd  ldarg.0
0x1bdde  call     instance void Microsoft.ReportingServices.Library.RSService::DisconnectStorage()
0x1bde3  endfinally
0x1bde4  ldloc.1
0x1bde5  ret
```
