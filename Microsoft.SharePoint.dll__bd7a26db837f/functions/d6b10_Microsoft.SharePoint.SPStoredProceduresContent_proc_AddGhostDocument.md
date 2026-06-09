# Microsoft.SharePoint.SPStoredProceduresContent::proc_AddGhostDocument

- ea: `0xd6b10`
- end: `0xd7199`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::proc_AddGhostDocument`
- size: `1673`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0xd6b10`
- `0x8e5050`
- `0x8e50a0`
- `0x8e50b0`
- `0x8e5130`

## string_xrefs

- `0xd6ea6`: `@Overwrite`
- `0xd6f5a`: `@HasDeleteListItemsRight`
- `0xd6f77`: `@HasDeleteListItemsRight`
- `0xd6fa2`: `@UpdateSiteQuota`
- `0xd6fbf`: `@UpdateSiteQuota`
- `0xd7011`: `@SetupPathVersion`
- `0xd702f`: `@SetupPathVersion`
- `0xd7056`: `@SetupPath`
- `0xd7074`: `@SetupPath`
- `0xd7091`: `@SetupPathUser`
- `0xd70af`: `@SetupPathUser`
- `0xd7128`: `@fCheckQuotaAndWriteLock`
- `0xd7153`: `@fCheckIfWebWelcomePage`
- `0xd6b5a`: `Length of parameter SetupPath exceeds specified max for the column`
- `0xd6b77`: `Length of parameter SetupPathUser exceeds specified max for the column`

## pseudocode

```c

```

## disassembly

```asm
0xd6b10  ldarg.3
0xd6b11  brfalse.s loc_D6B2B
0xd6b13  ldarg.3
0xd6b14  callvirt instance int32 [mscorlib]System.String::get_Length()
0xd6b19  ldc.i4   0x190
0xd6b1e  ble.s    loc_D6B2B
0xd6b20  ldstr    aLengthOfParame_41// "Length of parameter DocDirName exceeds "...
0xd6b25  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xd6b2a  throw
0xd6b2b  ldarg.s  4
0xd6b2d  brfalse.s loc_D6B48
0xd6b2f  ldarg.s  4
0xd6b31  callvirt instance int32 [mscorlib]System.String::get_Length()
0xd6b36  ldc.i4   0x190
0xd6b3b  ble.s    loc_D6B48
0xd6b3d  ldstr    aLengthOfParame_42// "Length of parameter DocLeafName exceeds"...
0xd6b42  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xd6b47  throw
0xd6b48  ldarg.s  0x11
0xd6b4a  brfalse.s loc_D6B65
0xd6b4c  ldarg.s  0x11
0xd6b4e  callvirt instance int32 [mscorlib]System.String::get_Length()
0xd6b53  ldc.i4   0xFF
0xd6b58  ble.s    loc_D6B65
0xd6b5a  ldstr    aLengthOfParame_60// "Length of parameter SetupPath exceeds s"...
0xd6b5f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xd6b64  throw
0xd6b65  ldarg.s  0x12
0xd6b67  brfalse.s loc_D6B82
0xd6b69  ldarg.s  0x12
0xd6b6b  callvirt instance int32 [mscorlib]System.String::get_Length()
0xd6b70  ldc.i4   0xFF
0xd6b75  ble.s    loc_D6B82
0xd6b77  ldstr    aLengthOfParame_61// "Length of parameter SetupPathUser excee"...
0xd6b7c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xd6b81  throw
0xd6b82  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlCommand::.ctor()
0xd6b87  stloc.0
0xd6b88  ldloc.0
0xd6b89  ldstr    aDboProcAddghos// "dbo.proc_AddGhostDocument"
0xd6b8e  callvirt instance void Microsoft.SharePoint.Utilities.SPSqlCommand::SetStoredProcedure(string strProc)
0xd6b93  ldarga.s 0
0xd6b95  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xd6b9a  brtrue.s loc_D6BBA
0xd6b9c  ldloc.0
0xd6b9d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6ba2  ldstr    aSiteid_1// "@SiteId"
0xd6ba7  ldc.i4.s 0xE
0xd6ba9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6bae  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd6bb3  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6bb8  br.s     loc_D6BDD
0xd6bba  ldloc.0
0xd6bbb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6bc0  ldstr    aSiteid_1// "@SiteId"
0xd6bc5  ldc.i4.s 0xE
0xd6bc7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6bcc  ldarga.s 0
0xd6bce  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xd6bd3  box      [mscorlib]System.Guid
0xd6bd8  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6bdd  ldarga.s 1
0xd6bdf  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xd6be4  brtrue.s loc_D6C04
0xd6be6  ldloc.0
0xd6be7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6bec  ldstr    aWebid_0// "@WebId"
0xd6bf1  ldc.i4.s 0xE
0xd6bf3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6bf8  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd6bfd  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6c02  br.s     loc_D6C27
0xd6c04  ldloc.0
0xd6c05  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6c0a  ldstr    aWebid_0// "@WebId"
0xd6c0f  ldc.i4.s 0xE
0xd6c11  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6c16  ldarga.s 1
0xd6c18  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xd6c1d  box      [mscorlib]System.Guid
0xd6c22  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6c27  ldarga.s 2
0xd6c29  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xd6c2e  brtrue.s loc_D6C4E
0xd6c30  ldloc.0
0xd6c31  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6c36  ldstr    aDocid_1// "@DocId"
0xd6c3b  ldc.i4.s 0xE
0xd6c3d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6c42  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd6c47  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6c4c  br.s     loc_D6C71
0xd6c4e  ldloc.0
0xd6c4f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6c54  ldstr    aDocid_1// "@DocId"
0xd6c59  ldc.i4.s 0xE
0xd6c5b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6c60  ldarga.s 2
0xd6c62  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xd6c67  box      [mscorlib]System.Guid
0xd6c6c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6c71  ldarg.3
0xd6c72  brtrue.s loc_D6C92
0xd6c74  ldloc.0
0xd6c75  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6c7a  ldstr    aDocdirname// "@DocDirName"
0xd6c7f  ldc.i4.s 0xC
0xd6c81  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6c86  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd6c8b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6c90  br.s     loc_D6CAA
0xd6c92  ldloc.0
0xd6c93  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6c98  ldstr    aDocdirname// "@DocDirName"
0xd6c9d  ldc.i4.s 0xC
0xd6c9f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6ca4  ldarg.3
0xd6ca5  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6caa  ldarg.s  4
0xd6cac  brtrue.s loc_D6CCC
0xd6cae  ldloc.0
0xd6caf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6cb4  ldstr    aDocleafname// "@DocLeafName"
0xd6cb9  ldc.i4.s 0xC
0xd6cbb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6cc0  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd6cc5  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6cca  br.s     loc_D6CE5
0xd6ccc  ldloc.0
0xd6ccd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6cd2  ldstr    aDocleafname// "@DocLeafName"
0xd6cd7  ldc.i4.s 0xC
0xd6cd9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6cde  ldarg.s  4
0xd6ce0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6ce5  ldarg.s  5
0xd6ce7  stloc.1
0xd6ce8  ldloca.s 1
0xd6cea  call     instance bool valuetype [mscorlib]System.Nullable`1<unsigned int8>::get_HasValue()
0xd6cef  brtrue.s loc_D6CFC
0xd6cf1  ldloca.s 2
0xd6cf3  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xd6cf9  ldloc.2
0xd6cfa  br.s     loc_D6D08
0xd6cfc  ldloca.s 1
0xd6cfe  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<unsigned int8>::GetValueOrDefault()
0xd6d03  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xd6d08  stloc.3
0xd6d09  ldloca.s 3
0xd6d0b  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xd6d10  brtrue.s loc_D6D30
0xd6d12  ldloc.0
0xd6d13  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6d18  ldstr    aLevel_1// "@Level"
0xd6d1d  ldc.i4.s 0x14
0xd6d1f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6d24  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd6d29  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6d2e  br.s     loc_D6D53
0xd6d30  ldloc.0
0xd6d31  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6d36  ldstr    aLevel_1// "@Level"
0xd6d3b  ldc.i4.s 0x14
0xd6d3d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6d42  ldarga.s 5
0xd6d44  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<unsigned int8>::get_Value()
0xd6d49  box      [mscorlib]System.Byte
0xd6d4e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6d53  ldarga.s 6
0xd6d55  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xd6d5a  brtrue.s loc_D6D79
0xd6d5c  ldloc.0
0xd6d5d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6d62  ldstr    aUiversion_1// "@UIVersion"
0xd6d67  ldc.i4.8
0xd6d68  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6d6d  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd6d72  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6d77  br.s     loc_D6D9B
0xd6d79  ldloc.0
0xd6d7a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6d7f  ldstr    aUiversion_1// "@UIVersion"
0xd6d84  ldc.i4.8
0xd6d85  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6d8a  ldarga.s 6
0xd6d8c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xd6d91  box      [mscorlib]System.Int32
0xd6d96  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6d9b  ldarga.s 7
0xd6d9d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xd6da2  brtrue.s loc_D6DC1
0xd6da4  ldloc.0
0xd6da5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6daa  ldstr    aEnableminorver// "@EnableMinorVersions"
0xd6daf  ldc.i4.2
0xd6db0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6db5  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd6dba  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6dbf  br.s     loc_D6DE3
0xd6dc1  ldloc.0
0xd6dc2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6dc7  ldstr    aEnableminorver// "@EnableMinorVersions"
0xd6dcc  ldc.i4.2
0xd6dcd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6dd2  ldarga.s 7
0xd6dd4  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xd6dd9  box      [mscorlib]System.Boolean
0xd6dde  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6de3  ldarga.s 8
0xd6de5  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xd6dea  brtrue.s loc_D6E09
0xd6dec  ldloc.0
0xd6ded  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6df2  ldstr    aDocsize// "@DocSize"
0xd6df7  ldc.i4.8
0xd6df8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6dfd  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd6e02  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6e07  br.s     loc_D6E2B
0xd6e09  ldloc.0
0xd6e0a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6e0f  ldstr    aDocsize// "@DocSize"
0xd6e14  ldc.i4.8
0xd6e15  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6e1a  ldarga.s 8
0xd6e1c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xd6e21  box      [mscorlib]System.Int32
0xd6e26  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6e2b  ldarga.s 9
0xd6e2d  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xd6e32  brtrue.s loc_D6E51
0xd6e34  ldloc.0
0xd6e35  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6e3a  ldstr    aDocflags// "@DocFlags"
0xd6e3f  ldc.i4.8
0xd6e40  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6e45  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd6e4a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6e4f  br.s     loc_D6E73
0xd6e51  ldloc.0
0xd6e52  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6e57  ldstr    aDocflags// "@DocFlags"
0xd6e5c  ldc.i4.8
0xd6e5d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6e62  ldarga.s 9
0xd6e64  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xd6e69  box      [mscorlib]System.Int32
0xd6e6e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6e73  ldarga.s 0xA
0xd6e75  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xd6e7a  brfalse.s loc_D6E9E
0xd6e7c  ldloc.0
0xd6e7d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6e82  ldstr    aOnrestore// "@OnRestore"
0xd6e87  ldc.i4.2
0xd6e88  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6e8d  ldarga.s 0xA
0xd6e8f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xd6e94  box      [mscorlib]System.Boolean
0xd6e99  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6e9e  ldarg.s  0xB
0xd6ea0  ldloc.0
0xd6ea1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6ea6  ldstr    aOverwrite// "@Overwrite"
0xd6eab  ldc.i4.2
0xd6eac  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6eb1  stind.ref
0xd6eb2  ldarg.s  0xB
0xd6eb4  ldind.ref
0xd6eb5  ldc.i4.2
0xd6eb6  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0xd6ebb  ldarga.s 0xC
0xd6ebd  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xd6ec2  brtrue.s loc_D6EE1
0xd6ec4  ldloc.0
0xd6ec5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6eca  ldstr    aUserid_1// "@UserId"
0xd6ecf  ldc.i4.8
0xd6ed0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6ed5  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xd6eda  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6edf  br.s     loc_D6F03
0xd6ee1  ldloc.0
0xd6ee2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6ee7  ldstr    aUserid_1// "@UserId"
0xd6eec  ldc.i4.8
0xd6eed  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6ef2  ldarga.s 0xC
0xd6ef4  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xd6ef9  box      [mscorlib]System.Int32
0xd6efe  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xd6f03  ldarga.s 0xD
0xd6f05  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xd6f0a  brtrue.s loc_D6F29
0xd6f0c  ldloc.0
0xd6f0d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xd6f12  ldstr    aAppprincipalid// "@AppPrincipalId"
0xd6f17  ldc.i4.8
0xd6f18  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xd6f1d  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
  ... truncated ...
```
