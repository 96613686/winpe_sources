# Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_16_0_4_0::Upgrade

- ea: `0x68a10`
- end: `0x68a46`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.TaxonomyDatabaseAction_16_0_4_0::Upgrade`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x68a3b`: `Updated database with new SQL indexes.`
- `0x68a26`: `\n-- IX_ECMTermSetMembership_ParentTermId\n\nIF NOT EXISTS (SELECT TOP 1 1 FROM sys.indexes WHERE object_id = object_id(N'[dbo].[ECMTermSetMembership]') AND name = 'IX_ECMTermSetMembership_ParentTermId')\nBEGIN\n\n    CREATE NONCLUSTERED INDEX [IX_ECMTermSetMembership_ParentTermId] ON [dbo].[ECMTermSetMembership] ([ParentTermId]) \n\nEND\nGO\n\n\nIF (EXISTS (SELECT TOP 1 1 FROM sys.indexes WHERE fill_factor <> 100 AND name='IX_ECMTermSetMembership_ParentTermId' AND object_id=object_i`

## pseudocode

```c

```
