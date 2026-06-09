# Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_15_0_24_0::Upgrade

- ea: `0x68760`
- end: `0x687ab`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_15_0_24_0::Upgrade`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x68780`: `\nDECLARE @EnsureGroup nvarchar(2000)\nDECLARE @EnsureGroupParam nvarchar(2000)\n\nDECLARE @EnsureTermSet nvarchar(2000)\nDECLARE @EnsureTermSetParam nvarchar(2000)\n\nSET @EnsureGroup = N'\n    MERGE INTO [dbo].[ECMGroup] AS target\n    USING \n       (SELECT PartitionId, @GroupGuid AS UniqueId\n    	FROM [dbo].[ECMServiceSettings]\n    	WHERE PartitionId <> ''00000000-0000-0000-0000-000000000000'') AS source \n    ON (source.UniqueId = target.UniqueId AND source.PartitionId = targ`
- `0x6878b`: `\nDECLARE @EnsureGroup nvarchar(2000)\nDECLARE @EnsureGroupParam nvarchar(2000)\n\nDECLARE @EnsureTermSet nvarchar(2000)\nDECLARE @EnsureTermSetParam nvarchar(2000)\n\nSET @EnsureGroup = N'\n    MERGE INTO [dbo].[ECMGroup] AS target\n    USING \n       (SELECT PartitionId, @GroupGuid AS UniqueId\n    	FROM [dbo].[ECMServiceSettings]\n    	WHERE PartitionId <> ''00000000-0000-0000-0000-000000000000'') AS source \n    ON (source.UniqueId = target.UniqueId AND source.PartitionId = targ`

## pseudocode

```c

```
