# Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::GetUpdatedPackagesInformation

- ea: `0x19cf0`
- end: `0x19db7`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::GetUpdatedPackagesInformation`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c2c0`

## callees

- `0x178f0`
- `0x17960`
- `0x19bd0`
- `0x19cf0`
- `0x1a050`
- `0x256d0`
- `0x38a20`

## string_xrefs

- `0x19d5b`: `@LastUpdateTime`
- `0x19d6d`: `@LastUpdateTime`

## pseudocode

```c

```

## disassembly

```asm
0x19cf0  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x19cf5  stloc.0
0x19cf6  ldarg.2
0x19cf7  call     valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.Internal.CommonValidator::GetValidDBTime(valuetype [mscorlib]System.DateTime time)
0x19cfc  stloc.1
0x19cfd  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor()
0x19d02  stloc.2
0x19d03  ldloc.2
0x19d04  ldc.i4.4
0x19d05  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x19d0a  ldloc.2
0x19d0b  ldarg.0
0x19d0c  ldstr    aProcEcmGetpack_0// "proc_ECM_GetPackagesInformation"
0x19d11  call     instance string Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase::GetScopedProcedureName(string procedureName)
0x19d16  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x19d1b  ldloc.2
0x19d1c  ldarg.0
0x19d1d  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::get_CommandTimeOut()
0x19d22  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x19d27  ldloc.2
0x19d28  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x19d2d  ldstr    aPartitionid// "@PartitionId"
0x19d32  ldc.i4.s 0xE
0x19d34  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x19d39  pop
0x19d3a  ldloc.2
0x19d3b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x19d40  ldstr    aPartitionid// "@PartitionId"
0x19d45  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x19d4a  ldarg.1
0x19d4b  box      [mscorlib]System.Guid
0x19d50  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x19d55  ldloc.2
0x19d56  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x19d5b  ldstr    aLastupdatetime// "@LastUpdateTime"
0x19d60  ldc.i4.4
0x19d61  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x19d66  pop
0x19d67  ldloc.2
0x19d68  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x19d6d  ldstr    aLastupdatetime// "@LastUpdateTime"
0x19d72  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(string)
0x19d77  ldloc.1
0x19d78  box      [mscorlib]System.DateTime
0x19d7d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x19d82  ldarg.0
0x19d83  ldc.i4.0
0x19d84  call     instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomySqlSession Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase::CreateSqlSession(valuetype Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseConnectionType connectionType)
0x19d89  stloc.3
0x19d8a  ldloc.3
0x19d8b  ldloc.2
0x19d8c  callvirt instance class [System.Data]System.Data.SqlClient.SqlDataReader Microsoft.SharePoint.Taxonomy.Internal.TaxonomySqlSession::ExecuteReader(class [System.Data]System.Data.SqlClient.SqlCommand command)
0x19d91  stloc.s  4
0x19d93  ldloc.s  4
0x19d95  ldloc.0
0x19d96  call     void Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::GeneratePackageMetaFile(class [System.Data]System.Data.SqlClient.SqlDataReader reader, class [mscorlib]System.IO.MemoryStream stream)
0x19d9b  leave.s  loc_19DA9
0x19d9d  ldloc.s  4
0x19d9f  brfalse.s loc_19DA8
0x19da1  ldloc.s  4
0x19da3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19da8  endfinally
0x19da9  leave.s  loc_19DB5
0x19dab  ldloc.2
0x19dac  brfalse.s loc_19DB4
0x19dae  ldloc.2
0x19daf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19db4  endfinally
0x19db5  ldloc.0
0x19db6  ret
```
