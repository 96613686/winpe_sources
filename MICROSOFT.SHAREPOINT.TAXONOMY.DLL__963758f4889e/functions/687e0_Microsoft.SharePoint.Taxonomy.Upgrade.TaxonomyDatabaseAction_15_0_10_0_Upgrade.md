# Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_15_0_10_0::Upgrade

- ea: `0x687e0`
- end: `0x68816`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_15_0_10_0::Upgrade`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x687f6`: `\nIF EXISTS (SELECT * FROM sysindexes WHERE id = object_id('[dbo].[ECMTerm]') AND name = 'IX_ECMTerm_PartitionIdUniqueIdId') DROP INDEX [dbo].[ECMTerm].[IX_ECMTerm_PartitionIdUniqueIdId]\nGO\n\nIF EXISTS (SELECT TOP 1 1 FROM sys.objects WHERE object_id = object_id(N'[dbo].[TVF_ECMTerm_PartitionIdUniqueIdId]') AND type = 'IF')\n    DROP FUNCTION [dbo].[TVF_ECMTerm_PartitionIdUniqueIdId]\nGO\n\nALTER TABLE [dbo].[ECMTermSetMembership] ALTER COLUMN PinSourceTermSetId int null\n\nDECLARE @`
- `0x6880b`: `Updated ECMTerm and ECMTermSetMembership tables.`

## pseudocode

```c

```
