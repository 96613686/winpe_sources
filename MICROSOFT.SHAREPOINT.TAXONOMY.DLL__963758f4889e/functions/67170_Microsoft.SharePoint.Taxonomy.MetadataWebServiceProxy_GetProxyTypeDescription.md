# Microsoft.SharePoint.Taxonomy.MetadataWebServiceProxy::GetProxyTypeDescription

- ea: `0x67170`
- end: `0x6718a`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceProxy::GetProxyTypeDescription`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2acd0`

## string_xrefs

- `0x67170`: `ServiceApplicationProxyName`
- `0x6717a`: `ServiceApplicationProxyDescription`

## pseudocode

```c

```

## disassembly

```asm
0x67170  ldstr    aServiceapplica_2// "ServiceApplicationProxyName"
0x67175  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x6717a  ldstr    aServiceapplica_5// "ServiceApplicationProxyDescription"
0x6717f  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x67184  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedTypeDescription::.ctor(string, string)
0x67189  ret
```
