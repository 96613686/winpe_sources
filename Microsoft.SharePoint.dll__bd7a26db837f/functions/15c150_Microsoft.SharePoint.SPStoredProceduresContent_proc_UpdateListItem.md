# Microsoft.SharePoint.SPStoredProceduresContent::proc_UpdateListItem

- ea: `0x15c150`
- end: `0x15cd7d`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::proc_UpdateListItem`
- size: `3117`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x15c150`
- `0x8e5050`
- `0x8e50a0`
- `0x8e50b0`
- `0x8e5130`

## string_xrefs

- `0x15c3f4`: `@ExtraItemSize`
- `0x15c7f8`: `@tp_ThreadIndex`
- `0x15cacc`: `@tp_Created`
- `0x15c935`: `@tp_CopySource`
- `0x15c957`: `@tp_HasCopyDestinations`
- `0x15cd19`: `@AclVersion`
- `0x15c65d`: `@SystemUpdate`
- `0x15c9ad`: `@BumpLastDelete`
- `0x15c9d8`: `@CreateItemVersion`
- `0x15ccee`: `@AccessControlFlags`
- `0x15c199`: `Length of parameter tp_ThreadIndex exceeds specified max for the column`
- `0x15c1d0`: `Length of parameter tp_CopySource exceeds specified max for the column`
- `0x15c1ff`: `dbo.proc_UpdateListItem`

## pseudocode

```c

```

## disassembly

```asm
0x15c150  ldarg.s  7
0x15c152  brfalse.s loc_15C16D
0x15c154  ldarg.s  7
0x15c156  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15c15b  ldc.i4   0xFF
0x15c160  ble.s    loc_15C16D
0x15c162  ldstr    aLengthOfParame_58// "Length of parameter ItemName exceeds sp"...
0x15c167  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15c16c  throw
0x15c16d  ldarg.s  0x1D
0x15c16f  brfalse.s loc_15C18A
0x15c171  ldarg.s  0x1D
0x15c173  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15c178  ldc.i4   0x200
0x15c17d  ble.s    loc_15C18A
0x15c17f  ldstr    aLengthOfParame_62// "Length of parameter tp_Ordering exceeds"...
0x15c184  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15c189  throw
0x15c18a  ldarg.s  0x1E
0x15c18c  brfalse.s loc_15C1A4
0x15c18e  ldarg.s  0x1E
0x15c190  ldlen
0x15c191  conv.i4
0x15c192  ldc.i4   0x200
0x15c197  ble.s    loc_15C1A4
0x15c199  ldstr    aLengthOfParame_63// "Length of parameter tp_ThreadIndex exce"...
0x15c19e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15c1a3  throw
0x15c1a4  ldarg.s  0x25
0x15c1a6  brfalse.s loc_15C1BE
0x15c1a8  ldarg.s  0x25
0x15c1aa  ldlen
0x15c1ab  conv.i4
0x15c1ac  ldc.i4   0x200
0x15c1b1  ble.s    loc_15C1BE
0x15c1b3  ldstr    aLengthOfParame_64// "Length of parameter tp_ContentTypeId ex"...
0x15c1b8  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15c1bd  throw
0x15c1be  ldarg.s  0x26
0x15c1c0  brfalse.s loc_15C1DB
0x15c1c2  ldarg.s  0x26
0x15c1c4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15c1c9  ldc.i4   0x190
0x15c1ce  ble.s    loc_15C1DB
0x15c1d0  ldstr    aLengthOfParame_65// "Length of parameter tp_CopySource excee"...
0x15c1d5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15c1da  throw
0x15c1db  ldarg.s  0x34
0x15c1dd  brfalse.s loc_15C1F8
0x15c1df  ldarg.s  0x34
0x15c1e1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15c1e6  ldc.i4   0xFF
0x15c1eb  ble.s    loc_15C1F8
0x15c1ed  ldstr    aLengthOfParame_66// "Length of parameter nvarchar1 exceeds s"...
0x15c1f2  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15c1f7  throw
0x15c1f8  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlCommand::.ctor()
0x15c1fd  stloc.0
0x15c1fe  ldloc.0
0x15c1ff  ldstr    aDboProcUpdatel_4// "dbo.proc_UpdateListItem"
0x15c204  callvirt instance void Microsoft.SharePoint.Utilities.SPSqlCommand::SetStoredProcedure(string strProc)
0x15c209  ldarga.s 0
0x15c20b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x15c210  brtrue.s loc_15C230
0x15c212  ldloc.0
0x15c213  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c218  ldstr    aSiteid_1// "@SiteId"
0x15c21d  ldc.i4.s 0xE
0x15c21f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c224  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15c229  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c22e  br.s     loc_15C253
0x15c230  ldloc.0
0x15c231  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c236  ldstr    aSiteid_1// "@SiteId"
0x15c23b  ldc.i4.s 0xE
0x15c23d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c242  ldarga.s 0
0x15c244  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x15c249  box      [mscorlib]System.Guid
0x15c24e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c253  ldarga.s 1
0x15c255  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x15c25a  brtrue.s loc_15C27A
0x15c25c  ldloc.0
0x15c25d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c262  ldstr    aWebid_0// "@WebId"
0x15c267  ldc.i4.s 0xE
0x15c269  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c26e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15c273  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c278  br.s     loc_15C29D
0x15c27a  ldloc.0
0x15c27b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c280  ldstr    aWebid_0// "@WebId"
0x15c285  ldc.i4.s 0xE
0x15c287  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c28c  ldarga.s 1
0x15c28e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x15c293  box      [mscorlib]System.Guid
0x15c298  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c29d  ldarga.s 2
0x15c29f  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x15c2a4  brtrue.s loc_15C2C4
0x15c2a6  ldloc.0
0x15c2a7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c2ac  ldstr    aListid_0// "@ListId"
0x15c2b1  ldc.i4.s 0xE
0x15c2b3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c2b8  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15c2bd  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c2c2  br.s     loc_15C2E7
0x15c2c4  ldloc.0
0x15c2c5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c2ca  ldstr    aListid_0// "@ListId"
0x15c2cf  ldc.i4.s 0xE
0x15c2d1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c2d6  ldarga.s 2
0x15c2d8  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x15c2dd  box      [mscorlib]System.Guid
0x15c2e2  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c2e7  ldarga.s 3
0x15c2e9  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x15c2ee  brtrue.s loc_15C30D
0x15c2f0  ldloc.0
0x15c2f1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c2f6  ldstr    aItemid// "@ItemId"
0x15c2fb  ldc.i4.8
0x15c2fc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c301  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15c306  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c30b  br.s     loc_15C32F
0x15c30d  ldloc.0
0x15c30e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c313  ldstr    aItemid// "@ItemId"
0x15c318  ldc.i4.8
0x15c319  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c31e  ldarga.s 3
0x15c320  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x15c325  box      [mscorlib]System.Int32
0x15c32a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c32f  ldarg.s  4
0x15c331  stloc.1
0x15c332  ldloca.s 1
0x15c334  call     instance bool valuetype [mscorlib]System.Nullable`1<unsigned int8>::get_HasValue()
0x15c339  brtrue.s loc_15C346
0x15c33b  ldloca.s 2
0x15c33d  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x15c343  ldloc.2
0x15c344  br.s     loc_15C352
0x15c346  ldloca.s 1
0x15c348  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<unsigned int8>::GetValueOrDefault()
0x15c34d  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x15c352  stloc.3
0x15c353  ldloca.s 3
0x15c355  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x15c35a  brtrue.s loc_15C37A
0x15c35c  ldloc.0
0x15c35d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c362  ldstr    aRowordinal// "@RowOrdinal"
0x15c367  ldc.i4.s 0x14
0x15c369  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c36e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15c373  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c378  br.s     loc_15C39D
0x15c37a  ldloc.0
0x15c37b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c380  ldstr    aRowordinal// "@RowOrdinal"
0x15c385  ldc.i4.s 0x14
0x15c387  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c38c  ldarga.s 4
0x15c38e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<unsigned int8>::get_Value()
0x15c393  box      [mscorlib]System.Byte
0x15c398  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c39d  ldarga.s 5
0x15c39f  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x15c3a4  brtrue.s loc_15C3C3
0x15c3a6  ldloc.0
0x15c3a7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c3ac  ldstr    aSize_0// "@Size"
0x15c3b1  ldc.i4.8
0x15c3b2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c3b7  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15c3bc  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c3c1  br.s     loc_15C3E5
0x15c3c3  ldloc.0
0x15c3c4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c3c9  ldstr    aSize_0// "@Size"
0x15c3ce  ldc.i4.8
0x15c3cf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c3d4  ldarga.s 5
0x15c3d6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x15c3db  box      [mscorlib]System.Int32
0x15c3e0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c3e5  ldarga.s 6
0x15c3e7  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x15c3ec  brfalse.s loc_15C410
0x15c3ee  ldloc.0
0x15c3ef  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c3f4  ldstr    aExtraitemsize// "@ExtraItemSize"
0x15c3f9  ldc.i4.8
0x15c3fa  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c3ff  ldarga.s 6
0x15c401  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x15c406  box      [mscorlib]System.Int32
0x15c40b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c410  ldarg.s  7
0x15c412  brfalse.s loc_15C42D
0x15c414  ldloc.0
0x15c415  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c41a  ldstr    aItemname// "@ItemName"
0x15c41f  ldc.i4.s 0xC
0x15c421  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c426  ldarg.s  7
0x15c428  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c42d  ldarga.s 8
0x15c42f  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x15c434  brfalse.s loc_15C458
0x15c436  ldloc.0
0x15c437  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c43c  ldstr    aUsenvarchar1it// "@UseNvarchar1ItemName"
0x15c441  ldc.i4.2
0x15c442  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c447  ldarga.s 8
0x15c449  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x15c44e  box      [mscorlib]System.Boolean
0x15c453  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c458  ldarg.s  9
0x15c45a  ldloc.0
0x15c45b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c460  ldstr    aItemdirname// "@ItemDirName"
0x15c465  ldc.i4.s 0xC
0x15c467  ldc.i4   0x190
0x15c46c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x15c471  stind.ref
0x15c472  ldarg.s  9
0x15c474  ldind.ref
0x15c475  ldc.i4.2
0x15c476  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x15c47b  ldarg.s  0xA
0x15c47d  ldloc.0
0x15c47e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c483  ldstr    aItemleafname// "@ItemLeafName"
0x15c488  ldc.i4.s 0xC
0x15c48a  ldc.i4   0x190
0x15c48f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x15c494  stind.ref
0x15c495  ldarg.s  0xA
0x15c497  ldind.ref
0x15c498  ldc.i4.2
0x15c499  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x15c49e  ldarga.s 0xB
0x15c4a0  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x15c4a5  brtrue.s loc_15C4C4
0x15c4a7  ldloc.0
0x15c4a8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c4ad  ldstr    aUserid_1// "@UserId"
0x15c4b2  ldc.i4.8
0x15c4b3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c4b8  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15c4bd  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c4c2  br.s     loc_15C4E6
0x15c4c4  ldloc.0
0x15c4c5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c4ca  ldstr    aUserid_1// "@UserId"
0x15c4cf  ldc.i4.8
0x15c4d0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c4d5  ldarga.s 0xB
0x15c4d7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x15c4dc  box      [mscorlib]System.Int32
0x15c4e1  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c4e6  ldarg.s  0xC
0x15c4e8  ldloc.0
0x15c4e9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c4ee  ldstr    aLevel_1// "@Level"
0x15c4f3  ldc.i4.s 0x14
0x15c4f5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c4fa  stind.ref
0x15c4fb  ldarg.s  0xC
0x15c4fd  ldind.ref
0x15c4fe  ldc.i4.2
0x15c4ff  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x15c504  ldarga.s 0xD
0x15c506  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x15c50b  brtrue.s loc_15C52A
0x15c50d  ldloc.0
0x15c50e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c513  ldstr    aTimenow// "@TimeNow"
0x15c518  ldc.i4.4
0x15c519  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c51e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15c523  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15c528  br.s     loc_15C54C
0x15c52a  ldloc.0
0x15c52b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15c530  ldstr    aTimenow// "@TimeNow"
0x15c535  ldc.i4.4
0x15c536  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15c53b  ldarga.s 0xD
0x15c53d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
  ... truncated ...
```
