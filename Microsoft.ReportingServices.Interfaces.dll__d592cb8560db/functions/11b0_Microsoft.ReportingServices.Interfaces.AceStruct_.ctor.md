# Microsoft.ReportingServices.Interfaces.AceStruct::.ctor

- ea: `0x11b0`
- end: `0x120b`
- name: `Microsoft.ReportingServices.Interfaces.AceStruct::.ctor`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0xf50`
- `0xfb0`
- `0x1010`
- `0x1070`
- `0x10d0`
- `0x1130`
- `0x1190`

## pseudocode

```c

```

## disassembly

```asm
0x11b0  ldarg.0
0x11b1  call     instance void [mscorlib]System.Object::.ctor()
0x11b6  ldarg.0
0x11b7  ldarg.1
0x11b8  stfld    string Microsoft.ReportingServices.Interfaces.AceStruct::PrincipalName
0x11bd  ldarg.0
0x11be  newobj   instance void Microsoft.ReportingServices.Interfaces.CatalogOperationsCollection::.ctor()
0x11c3  stfld    class Microsoft.ReportingServices.Interfaces.CatalogOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::CatalogOperations
0x11c8  ldarg.0
0x11c9  newobj   instance void Microsoft.ReportingServices.Interfaces.ReportOperationsCollection::.ctor()
0x11ce  stfld    class Microsoft.ReportingServices.Interfaces.ReportOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::ReportOperations
0x11d3  ldarg.0
0x11d4  newobj   instance void Microsoft.ReportingServices.Interfaces.FolderOperationsCollection::.ctor()
0x11d9  stfld    class Microsoft.ReportingServices.Interfaces.FolderOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::FolderOperations
0x11de  ldarg.0
0x11df  newobj   instance void Microsoft.ReportingServices.Interfaces.ResourceOperationsCollection::.ctor()
0x11e4  stfld    class Microsoft.ReportingServices.Interfaces.ResourceOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::ResourceOperations
0x11e9  ldarg.0
0x11ea  newobj   instance void Microsoft.ReportingServices.Interfaces.DatasourceOperationsCollection::.ctor()
0x11ef  stfld    class Microsoft.ReportingServices.Interfaces.DatasourceOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::DatasourceOperations
0x11f4  ldarg.0
0x11f5  newobj   instance void Microsoft.ReportingServices.Interfaces.ModelOperationsCollection::.ctor()
0x11fa  stfld    class Microsoft.ReportingServices.Interfaces.ModelOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::ModelOperations
0x11ff  ldarg.0
0x1200  newobj   instance void Microsoft.ReportingServices.Interfaces.ModelItemOperationsCollection::.ctor()
0x1205  stfld    class Microsoft.ReportingServices.Interfaces.ModelItemOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::ModelItemOperations
0x120a  ret
```
