# Microsoft.ReportingServices.Interfaces.AceStruct::.ctor_0

- ea: `0x1210`
- end: `0x1277`
- name: `Microsoft.ReportingServices.Interfaces.AceStruct::.ctor_0`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1210  ldarg.0
0x1211  call     instance void [mscorlib]System.Object::.ctor()
0x1216  ldarg.0
0x1217  ldarg.1
0x1218  ldfld    string Microsoft.ReportingServices.Interfaces.AceStruct::PrincipalName
0x121d  stfld    string Microsoft.ReportingServices.Interfaces.AceStruct::PrincipalName
0x1222  ldarg.0
0x1223  ldarg.1
0x1224  ldfld    class Microsoft.ReportingServices.Interfaces.CatalogOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::CatalogOperations
0x1229  stfld    class Microsoft.ReportingServices.Interfaces.CatalogOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::CatalogOperations
0x122e  ldarg.0
0x122f  ldarg.1
0x1230  ldfld    class Microsoft.ReportingServices.Interfaces.ReportOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::ReportOperations
0x1235  stfld    class Microsoft.ReportingServices.Interfaces.ReportOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::ReportOperations
0x123a  ldarg.0
0x123b  ldarg.1
0x123c  ldfld    class Microsoft.ReportingServices.Interfaces.FolderOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::FolderOperations
0x1241  stfld    class Microsoft.ReportingServices.Interfaces.FolderOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::FolderOperations
0x1246  ldarg.0
0x1247  ldarg.1
0x1248  ldfld    class Microsoft.ReportingServices.Interfaces.ResourceOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::ResourceOperations
0x124d  stfld    class Microsoft.ReportingServices.Interfaces.ResourceOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::ResourceOperations
0x1252  ldarg.0
0x1253  ldarg.1
0x1254  ldfld    class Microsoft.ReportingServices.Interfaces.DatasourceOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::DatasourceOperations
0x1259  stfld    class Microsoft.ReportingServices.Interfaces.DatasourceOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::DatasourceOperations
0x125e  ldarg.0
0x125f  ldarg.1
0x1260  ldfld    class Microsoft.ReportingServices.Interfaces.ModelOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::ModelOperations
0x1265  stfld    class Microsoft.ReportingServices.Interfaces.ModelOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::ModelOperations
0x126a  ldarg.0
0x126b  ldarg.1
0x126c  ldfld    class Microsoft.ReportingServices.Interfaces.ModelItemOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::ModelItemOperations
0x1271  stfld    class Microsoft.ReportingServices.Interfaces.ModelItemOperationsCollection Microsoft.ReportingServices.Interfaces.AceStruct::ModelItemOperations
0x1276  ret
```
