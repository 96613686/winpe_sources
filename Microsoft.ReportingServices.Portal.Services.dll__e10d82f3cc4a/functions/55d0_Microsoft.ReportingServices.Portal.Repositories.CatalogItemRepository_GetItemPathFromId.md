# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetItemPathFromId

- ea: `0x55d0`
- end: `0x560d`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetItemPathFromId`
- size: `61`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2c20`
- `0x2c50`
- `0x4e30`
- `0x5be0`
- `0x5d90`
- `0x5ea0`

## callees

- `0x55d0`

## pseudocode

```c

```

## disassembly

```asm
0x55d0  ldarg.0
0x55d1  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSServiceStorageAccess::.ctor(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService)
0x55d6  stloc.1
0x55d7  ldarg.0
0x55d8  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_Storage()
0x55dd  ldarg.1
0x55de  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface::GetPathById(valuetype [mscorlib]System.Guid)
0x55e3  dup
0x55e4  brtrue.s loc_55F9
0x55e6  ldarga.s 1
0x55e8  constrained. [mscorlib]System.Guid
0x55ee  callvirt instance string [mscorlib]System.Object::ToString()
0x55f3  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ItemNotFoundException::.ctor(string)
0x55f8  throw
0x55f9  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x55fe  stloc.0
0x55ff  leave.s  loc_560B
0x5601  ldloc.1
0x5602  brfalse.s loc_560A
0x5604  ldloc.1
0x5605  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x560a  endfinally
0x560b  ldloc.0
0x560c  ret
```
