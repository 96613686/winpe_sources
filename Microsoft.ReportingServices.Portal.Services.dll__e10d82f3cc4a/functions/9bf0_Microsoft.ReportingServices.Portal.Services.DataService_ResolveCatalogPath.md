# Microsoft.ReportingServices.Portal.Services.DataService::ResolveCatalogPath

- ea: `0x9bf0`
- end: `0x9c2c`
- name: `Microsoft.ReportingServices.Portal.Services.DataService::ResolveCatalogPath`
- size: `60`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8f30`
- `0x91c0`
- `0x92e0`
- `0x93c0`
- `0x9450`

## callees

- `0x9bf0`

## pseudocode

```c

```

## disassembly

```asm
0x9bf0  ldnull
0x9bf1  stloc.1
0x9bf2  ldarg.1
0x9bf3  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSServiceStorageAccess::.ctor(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService)
0x9bf8  stloc.2
0x9bf9  ldarg.1
0x9bfa  callvirt instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_Storage()
0x9bff  ldarg.2
0x9c00  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [ReportingServicesLibrary]Microsoft.ReportingServices.Library.IDBInterface::GetPathById(valuetype [mscorlib]System.Guid)
0x9c05  stloc.0
0x9c06  leave.s  loc_9C12
0x9c08  ldloc.2
0x9c09  brfalse.s loc_9C11
0x9c0b  ldloc.2
0x9c0c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9c11  endfinally
0x9c12  ldloc.0
0x9c13  brfalse.s loc_9C2A
0x9c15  ldloc.0
0x9c16  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x9c1b  stloc.1
0x9c1c  ldloc.1
0x9c1d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9c22  brfalse.s loc_9C2A
0x9c24  ldstr    asc_25576// "/"
0x9c29  stloc.1
0x9c2a  ldloc.1
0x9c2b  ret
```
