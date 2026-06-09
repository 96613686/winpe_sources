# Microsoft.SharePoint.SPStoredProceduresContent::proc_PatchLinkForFile

- ea: `0x13a6c0`
- end: `0x13aa9a`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::proc_PatchLinkForFile`
- size: `986`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x13a6c0`
- `0x8e5050`
- `0x8e50a0`
- `0x8e50b0`
- `0x8e5130`

## string_xrefs

- `0x13a88b`: `@OldLinkDirName`
- `0x13a8a9`: `@OldLinkDirName`
- `0x13a8c6`: `@OldLinkLeafName`
- `0x13a8e4`: `@OldLinkLeafName`
- `0x13a949`: `@NewLinkDirName`
- `0x13a967`: `@NewLinkDirName`
- `0x13a984`: `@NewLinkLeafName`
- `0x13a9a2`: `@NewLinkLeafName`
- `0x13aa54`: `@DocUpdateFlags`
- `0x13aa71`: `@DocUpdateFlags`
- `0x13a708`: `Length of parameter OldLinkDirName exceeds specified max for the column`
- `0x13a725`: `Length of parameter OldLinkLeafName exceeds specified max for the column`
- `0x13a742`: `Length of parameter NewLinkDirName exceeds specified max for the column`
- `0x13a75f`: `Length of parameter NewLinkLeafName exceeds specified max for the column`
- `0x13a771`: `dbo.proc_PatchLinkForFile`

## pseudocode

```c

```

## disassembly

```asm
0x13a6c0  ldarg.2
0x13a6c1  brfalse.s loc_13A6DB
0x13a6c3  ldarg.2
0x13a6c4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13a6c9  ldc.i4   0x190
0x13a6ce  ble.s    loc_13A6DB
0x13a6d0  ldstr    aLengthOfParame_39// "Length of parameter DirName exceeds spe"...
0x13a6d5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x13a6da  throw
0x13a6db  ldarg.3
0x13a6dc  brfalse.s loc_13A6F6
0x13a6de  ldarg.3
0x13a6df  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13a6e4  ldc.i4   0x190
0x13a6e9  ble.s    loc_13A6F6
0x13a6eb  ldstr    aLengthOfParame_40// "Length of parameter LeafName exceeds sp"...
0x13a6f0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x13a6f5  throw
0x13a6f6  ldarg.s  4
0x13a6f8  brfalse.s loc_13A713
0x13a6fa  ldarg.s  4
0x13a6fc  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13a701  ldc.i4   0x190
0x13a706  ble.s    loc_13A713
0x13a708  ldstr    aLengthOfParame_284// "Length of parameter OldLinkDirName exce"...
0x13a70d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x13a712  throw
0x13a713  ldarg.s  5
0x13a715  brfalse.s loc_13A730
0x13a717  ldarg.s  5
0x13a719  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13a71e  ldc.i4   0x190
0x13a723  ble.s    loc_13A730
0x13a725  ldstr    aLengthOfParame_285// "Length of parameter OldLinkLeafName exc"...
0x13a72a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x13a72f  throw
0x13a730  ldarg.s  7
0x13a732  brfalse.s loc_13A74D
0x13a734  ldarg.s  7
0x13a736  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13a73b  ldc.i4   0x190
0x13a740  ble.s    loc_13A74D
0x13a742  ldstr    aLengthOfParame_286// "Length of parameter NewLinkDirName exce"...
0x13a747  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x13a74c  throw
0x13a74d  ldarg.s  8
0x13a74f  brfalse.s loc_13A76A
0x13a751  ldarg.s  8
0x13a753  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13a758  ldc.i4   0x190
0x13a75d  ble.s    loc_13A76A
0x13a75f  ldstr    aLengthOfParame_287// "Length of parameter NewLinkLeafName exc"...
0x13a764  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x13a769  throw
0x13a76a  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlCommand::.ctor()
0x13a76f  stloc.0
0x13a770  ldloc.0
0x13a771  ldstr    aDboProcPatchli// "dbo.proc_PatchLinkForFile"
0x13a776  callvirt instance void Microsoft.SharePoint.Utilities.SPSqlCommand::SetStoredProcedure(string strProc)
0x13a77b  ldarga.s 0
0x13a77d  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x13a782  brtrue.s loc_13A7A2
0x13a784  ldloc.0
0x13a785  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a78a  ldstr    aSiteid_1// "@SiteId"
0x13a78f  ldc.i4.s 0xE
0x13a791  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a796  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x13a79b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a7a0  br.s     loc_13A7C5
0x13a7a2  ldloc.0
0x13a7a3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a7a8  ldstr    aSiteid_1// "@SiteId"
0x13a7ad  ldc.i4.s 0xE
0x13a7af  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a7b4  ldarga.s 0
0x13a7b6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x13a7bb  box      [mscorlib]System.Guid
0x13a7c0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a7c5  ldarga.s 1
0x13a7c7  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x13a7cc  brtrue.s loc_13A7EC
0x13a7ce  ldloc.0
0x13a7cf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a7d4  ldstr    aWebid_0// "@WebId"
0x13a7d9  ldc.i4.s 0xE
0x13a7db  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a7e0  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x13a7e5  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a7ea  br.s     loc_13A80F
0x13a7ec  ldloc.0
0x13a7ed  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a7f2  ldstr    aWebid_0// "@WebId"
0x13a7f7  ldc.i4.s 0xE
0x13a7f9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a7fe  ldarga.s 1
0x13a800  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x13a805  box      [mscorlib]System.Guid
0x13a80a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a80f  ldarg.2
0x13a810  brtrue.s loc_13A830
0x13a812  ldloc.0
0x13a813  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a818  ldstr    aDirname_0// "@DirName"
0x13a81d  ldc.i4.s 0xC
0x13a81f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a824  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x13a829  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a82e  br.s     loc_13A848
0x13a830  ldloc.0
0x13a831  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a836  ldstr    aDirname_0// "@DirName"
0x13a83b  ldc.i4.s 0xC
0x13a83d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a842  ldarg.2
0x13a843  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a848  ldarg.3
0x13a849  brtrue.s loc_13A869
0x13a84b  ldloc.0
0x13a84c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a851  ldstr    aLeafname// "@LeafName"
0x13a856  ldc.i4.s 0xC
0x13a858  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a85d  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x13a862  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a867  br.s     loc_13A881
0x13a869  ldloc.0
0x13a86a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a86f  ldstr    aLeafname// "@LeafName"
0x13a874  ldc.i4.s 0xC
0x13a876  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a87b  ldarg.3
0x13a87c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a881  ldarg.s  4
0x13a883  brtrue.s loc_13A8A3
0x13a885  ldloc.0
0x13a886  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a88b  ldstr    aOldlinkdirname// "@OldLinkDirName"
0x13a890  ldc.i4.s 0xC
0x13a892  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a897  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x13a89c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a8a1  br.s     loc_13A8BC
0x13a8a3  ldloc.0
0x13a8a4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a8a9  ldstr    aOldlinkdirname// "@OldLinkDirName"
0x13a8ae  ldc.i4.s 0xC
0x13a8b0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a8b5  ldarg.s  4
0x13a8b7  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a8bc  ldarg.s  5
0x13a8be  brtrue.s loc_13A8DE
0x13a8c0  ldloc.0
0x13a8c1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a8c6  ldstr    aOldlinkleafnam// "@OldLinkLeafName"
0x13a8cb  ldc.i4.s 0xC
0x13a8cd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a8d2  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x13a8d7  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a8dc  br.s     loc_13A8F7
0x13a8de  ldloc.0
0x13a8df  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a8e4  ldstr    aOldlinkleafnam// "@OldLinkLeafName"
0x13a8e9  ldc.i4.s 0xC
0x13a8eb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a8f0  ldarg.s  5
0x13a8f2  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a8f7  ldarga.s 6
0x13a8f9  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x13a8fe  brtrue.s loc_13A91D
0x13a900  ldloc.0
0x13a901  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a906  ldstr    aOldserverrel// "@OldServerRel"
0x13a90b  ldc.i4.2
0x13a90c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a911  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x13a916  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a91b  br.s     loc_13A93F
0x13a91d  ldloc.0
0x13a91e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a923  ldstr    aOldserverrel// "@OldServerRel"
0x13a928  ldc.i4.2
0x13a929  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a92e  ldarga.s 6
0x13a930  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x13a935  box      [mscorlib]System.Boolean
0x13a93a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a93f  ldarg.s  7
0x13a941  brtrue.s loc_13A961
0x13a943  ldloc.0
0x13a944  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a949  ldstr    aNewlinkdirname// "@NewLinkDirName"
0x13a94e  ldc.i4.s 0xC
0x13a950  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a955  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x13a95a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a95f  br.s     loc_13A97A
0x13a961  ldloc.0
0x13a962  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a967  ldstr    aNewlinkdirname// "@NewLinkDirName"
0x13a96c  ldc.i4.s 0xC
0x13a96e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a973  ldarg.s  7
0x13a975  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a97a  ldarg.s  8
0x13a97c  brtrue.s loc_13A99C
0x13a97e  ldloc.0
0x13a97f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a984  ldstr    aNewlinkleafnam// "@NewLinkLeafName"
0x13a989  ldc.i4.s 0xC
0x13a98b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a990  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x13a995  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a99a  br.s     loc_13A9B5
0x13a99c  ldloc.0
0x13a99d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a9a2  ldstr    aNewlinkleafnam// "@NewLinkLeafName"
0x13a9a7  ldc.i4.s 0xC
0x13a9a9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a9ae  ldarg.s  8
0x13a9b0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a9b5  ldarga.s 9
0x13a9b7  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x13a9bc  brtrue.s loc_13A9DB
0x13a9be  ldloc.0
0x13a9bf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a9c4  ldstr    aNewserverrel// "@NewServerRel"
0x13a9c9  ldc.i4.2
0x13a9ca  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a9cf  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x13a9d4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a9d9  br.s     loc_13A9FD
0x13a9db  ldloc.0
0x13a9dc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13a9e1  ldstr    aNewserverrel// "@NewServerRel"
0x13a9e6  ldc.i4.2
0x13a9e7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13a9ec  ldarga.s 9
0x13a9ee  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x13a9f3  box      [mscorlib]System.Boolean
0x13a9f8  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13a9fd  ldarga.s 0xA
0x13a9ff  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x13aa04  brtrue.s loc_13AA23
0x13aa06  ldloc.0
0x13aa07  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13aa0c  ldstr    aPatchprefix// "@PatchPrefix"
0x13aa11  ldc.i4.2
0x13aa12  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13aa17  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x13aa1c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13aa21  br.s     loc_13AA45
0x13aa23  ldloc.0
0x13aa24  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13aa29  ldstr    aPatchprefix// "@PatchPrefix"
0x13aa2e  ldc.i4.2
0x13aa2f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13aa34  ldarga.s 0xA
0x13aa36  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x13aa3b  box      [mscorlib]System.Boolean
0x13aa40  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13aa45  ldarga.s 0xB
0x13aa47  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x13aa4c  brtrue.s loc_13AA6B
0x13aa4e  ldloc.0
0x13aa4f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13aa54  ldstr    aDocupdateflags// "@DocUpdateFlags"
0x13aa59  ldc.i4.8
0x13aa5a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13aa5f  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x13aa64  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13aa69  br.s     loc_13AA8D
0x13aa6b  ldloc.0
0x13aa6c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x13aa71  ldstr    aDocupdateflags// "@DocUpdateFlags"
0x13aa76  ldc.i4.8
0x13aa77  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x13aa7c  ldarga.s 0xB
0x13aa7e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x13aa83  box      [mscorlib]System.Int32
0x13aa88  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x13aa8d  leave.s  loc_13AA98
0x13aa8f  pop
0x13aa90  ldloc.0
0x13aa91  callvirt instance void Microsoft.SharePoint.Utilities.SPSqlCommand::Dispose()
0x13aa96  rethrow
0x13aa98  ldloc.0
0x13aa99  ret
```
