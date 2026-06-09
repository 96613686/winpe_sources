# Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::.ctor_3

- ea: `0x8680`
- end: `0x86b4`
- name: `Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::.ctor_3`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x8660`
- `0x8670`

## callees

- `0x86e0`
- `0xa2b0`
- `0xa370`
- `0xa380`
- `0xa390`

## pseudocode

```c

```

## disassembly

```asm
0x8680  ldarg.0
0x8681  call     instance void [mscorlib]System.Object::.ctor()
0x8686  ldarg.0
0x8687  ldarg.1
0x8688  callvirt instance class Microsoft.ReportingServices.Diagnostics.IPathTranslator Microsoft.ReportingServices.Diagnostics.ICatalogItemContext::get_PathTranslator()
0x868d  stfld    class Microsoft.ReportingServices.Diagnostics.IPathTranslator Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::m_pathTranslator
0x8692  ldarg.0
0x8693  ldarg.1
0x8694  callvirt instance class Microsoft.ReportingServices.Diagnostics.IPathManager Microsoft.ReportingServices.Diagnostics.ICatalogItemContext::get_PathManager()
0x8699  stfld    class Microsoft.ReportingServices.Diagnostics.IPathManager Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::m_pathManager
0x869e  ldarg.0
0x869f  ldarg.1
0x86a0  callvirt instance string Microsoft.ReportingServices.Diagnostics.ICatalogItemContext::get_HostRootUri()
0x86a5  ldarg.1
0x86a6  callvirt instance string Microsoft.ReportingServices.Diagnostics.ICatalogItemContext::get_HostSpecificItemPath()
0x86ab  ldc.i4.0
0x86ac  ldc.i4.1
0x86ad  ldarg.2
0x86ae  call     instance void Microsoft.ReportingServices.Diagnostics.CatalogItemUrlBuilder::Construct(string serverVirtualFolderUrl, string itemPath, bool alreadyEscaped, bool addItemPathAsQuery, bool isFolder)
0x86b3  ret
```
