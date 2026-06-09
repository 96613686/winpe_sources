# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CheckCommentPermissions

- ea: `0x65d0`
- end: `0x65e2`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CheckCommentPermissions`
- size: `18`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x61f0`
- `0x6240`
- `0x6490`
- `0x6530`

## callees

- `0x1a00`
- `0x65f0`

## pseudocode

```c

```

## disassembly

```asm
0x65d0  ldarg.1
0x65d1  ldarg.2
0x65d2  call     string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogPathFromGuid(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid key)
0x65d7  stloc.0
0x65d8  ldarg.0
0x65d9  ldarg.1
0x65da  ldloc.0
0x65db  ldarg.3
0x65dc  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::CheckCommentPermissions(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string path, bool checkDelete)
0x65e1  ret
```
