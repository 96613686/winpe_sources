# Microsoft.SharePoint.Taxonomy.MetadataWebService::GetApplicationTypeDescription

- ea: `0x630f0`
- end: `0x63122`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebService::GetApplicationTypeDescription`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x2acd0`
- `0x630f0`

## string_xrefs

- `0x63108`: `ServiceApplicationName`
- `0x63112`: `MetadataServiceApplicationDescription`

## pseudocode

```c

```

## disassembly

```asm
0x630f0  ldarg.1
0x630f1  ldtoken  Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication
0x630f6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x630fb  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x63100  brfalse.s loc_63108
0x63102  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0x63107  throw
0x63108  ldstr    aServiceapplica// "ServiceApplicationName"
0x6310d  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x63112  ldstr    aMetadataservic// "MetadataServiceApplicationDescription"
0x63117  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x6311c  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedTypeDescription::.ctor(string, string)
0x63121  ret
```
