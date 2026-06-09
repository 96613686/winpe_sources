# Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::AddBackupObjects

- ea: `0x66f50`
- end: `0x66f98`
- name: `Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase::AddBackupObjects`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x242a0`
- `0x2acd0`

## string_xrefs

- `0x66f6e`: `ServiceApplicationDatabaseName`
- `0x66f88`: `ServiceApplicationDatabaseDescription`

## pseudocode

```c

```

## disassembly

```asm
0x66f50  ldarg.1
0x66f51  ldstr    aParent// "parent"
0x66f56  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x66f5b  ldarg.1
0x66f5c  ldarg.0
0x66f5d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreObject [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreObject::AddChild(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.IBackupRestore)
0x66f62  stloc.0
0x66f63  ldloc.0
0x66f64  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreInformation [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreObject::get_Information()
0x66f69  ldstr    aSptypename// "SPTypeName"
0x66f6e  ldstr    aServiceapplica_3// "ServiceApplicationDatabaseName"
0x66f73  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x66f78  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreInformation::SetParameter(string, object)
0x66f7d  ldloc.0
0x66f7e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreInformation [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreObject::get_Information()
0x66f83  ldstr    aSpdescription// "SPDescription"
0x66f88  ldstr    aServiceapplica_4// "ServiceApplicationDatabaseDescription"
0x66f8d  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x66f92  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Backup.SPBackupRestoreInformation::SetParameter(string, object)
0x66f97  ret
```
