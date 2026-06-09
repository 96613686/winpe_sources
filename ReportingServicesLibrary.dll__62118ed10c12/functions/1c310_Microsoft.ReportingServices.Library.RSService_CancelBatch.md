# Microsoft.ReportingServices.Library.RSService::CancelBatch

- ea: `0x1c310`
- end: `0x1c372`
- name: `Microsoft.ReportingServices.Library.RSService::CancelBatch`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x3ebb0`

## callees

- `0xcda0`
- `0x1c310`
- `0x1e0e0`
- `0x1e210`
- `0x1e3e0`
- `0x1e460`

## string_xrefs

- `0x1c31d`: `Call to DeleteBatch( {0} )`
- `0x1c35e`: `Call to DeleteBatch completed`

## pseudocode

```c

```

## disassembly

```asm
0x1c310  ldarg.0
0x1c311  call     instance void Microsoft.ReportingServices.Library.RSService::WillDisconnectStorage()
0x1c316  ldarg.0
0x1c317  call     instance class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.RSService::get_Tracer()
0x1c31c  ldc.i4.4
0x1c31d  ldstr    aCallToDeleteba// "Call to DeleteBatch( {0} )"
0x1c322  ldc.i4.1
0x1c323  newarr   [mscorlib]System.Object
0x1c328  dup
0x1c329  ldc.i4.0
0x1c32a  ldarg.1
0x1c32b  box      [mscorlib]System.Guid
0x1c330  stelem.ref
0x1c331  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x1c336  ldarg.0
0x1c337  call     instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.RSService::get_Storage()
0x1c33c  ldarg.1
0x1c33d  callvirt instance bool Microsoft.ReportingServices.Library.IDBInterface::DeleteBatchRecords(valuetype [mscorlib]System.Guid batchId)
0x1c342  brtrue.s loc_1C357
0x1c344  ldarga.s 1
0x1c346  constrained. [mscorlib]System.Guid
0x1c34c  callvirt instance string [mscorlib]System.Object::ToString()
0x1c351  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.BatchNotFoundException::.ctor(string)
0x1c356  throw
0x1c357  ldarg.0
0x1c358  call     instance class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.RSService::get_Tracer()
0x1c35d  ldc.i4.4
0x1c35e  ldstr    aCallToDeleteba_0// "Call to DeleteBatch completed"
0x1c363  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1c368  leave.s  loc_1C371
0x1c36a  ldarg.0
0x1c36b  call     instance void Microsoft.ReportingServices.Library.RSService::DisconnectStorage()
0x1c370  endfinally
0x1c371  ret
```
