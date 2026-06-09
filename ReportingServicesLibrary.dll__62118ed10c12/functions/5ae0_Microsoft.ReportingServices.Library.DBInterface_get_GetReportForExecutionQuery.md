# Microsoft.ReportingServices.Library.DBInterface::get_GetReportForExecutionQuery

- ea: `0x5ae0`
- end: `0x5b25`
- name: `Microsoft.ReportingServices.Library.DBInterface::get_GetReportForExecutionQuery`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x5b90`

## callees

- `0x5ae0`

## string_xrefs

- `0x5af2`: `TempDB`
- `0x5b0f`: `\nDECLARE @OwnerID uniqueidentifier\nif(@EditSessionID is not null)\nBEGIN\n    EXEC GetUserID @OwnerSid, @OwnerName, @AuthType, @OwnerID OUTPUT\nEND\n\nDECLARE @now AS datetime\nSET @now = GETDATE()\n\nIF ( NOT EXISTS (\n    SELECT TOP 1 1\n        FROM\n            ExtendedCatalog(@OwnerID, @Path, @EditSessionID) AS C\n            INNER JOIN {0}.dbo.ExecutionCache AS EC ON C.ItemID = EC.ReportID\n			INNER JOIN {0}.dbo.SnapshotData AS SN ON EC.SnapshotDataID = SN.SnapshotDataID A`

## pseudocode

```c

```

## disassembly

```asm
0x5ae0  ldsfld   string Microsoft.ReportingServices.Library.DBInterface::s_getReportForExecutionQuery
0x5ae5  brtrue.s loc_5B1F
0x5ae7  ldarg.0
0x5ae8  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_Connection()
0x5aed  callvirt instance string [System.Data]System.Data.Common.DbConnection::get_Database()
0x5af2  ldstr    aTempdb// "TempDB"
0x5af7  call     string [mscorlib]System.String::Concat(string, string)
0x5afc  stloc.0
0x5afd  ldarg.0
0x5afe  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x5b03  ldloc.0
0x5b04  callvirt instance string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::EscapeAndBracketDBName(string)
0x5b09  stloc.1
0x5b0a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5b0f  ldstr    aDeclareOwnerid// "\r\nDECLARE @OwnerID uniqueidentifier\r"...
0x5b14  ldloc.1
0x5b15  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x5b1a  stsfld   string Microsoft.ReportingServices.Library.DBInterface::s_getReportForExecutionQuery
0x5b1f  ldsfld   string Microsoft.ReportingServices.Library.DBInterface::s_getReportForExecutionQuery
0x5b24  ret
```
