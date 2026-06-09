# Microsoft.SharePoint.SPStoredProceduresContent::proc_UpdateDocument

- ea: `0x157b80`
- end: `0x158b72`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::proc_UpdateDocument`
- size: `4082`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x157b80`
- `0x8e5050`
- `0x8e50a0`
- `0x8e50b0`
- `0x8e5130`

## string_xrefs

- `0x158020`: `@DocIncomingCreatedDTM`
- `0x15803d`: `@DocIncomingCreatedDTM`
- `0x158068`: `@DocIncomingDTM`
- `0x158085`: `@DocIncomingDTM`
- `0x1583fe`: `@Comment`
- `0x15841c`: `@Comment`
- `0x1582a8`: `@UpdateFlags`
- `0x1582c5`: `@UpdateFlags`
- `0x1584c9`: `@WelcomePageUrl`
- `0x1584e7`: `@WelcomePageUrl`
- `0x158504`: `@WelcomePageParameters`
- `0x158522`: `@WelcomePageParameters`
- `0x1587fc`: `@FileFragmentPartitionsToDelete`
- `0x15881a`: `@FileFragmentPartitionsToDelete`
- `0x158837`: `@PartitionsToDelete`
- `0x158855`: `@PartitionsToDelete`
- `0x157be5`: `Length of parameter Comment exceeds specified max for the column`
- `0x157c02`: `Length of parameter WelcomePageUrl exceeds specified max for the column`
- `0x157c4b`: `dbo.proc_UpdateDocument`

## pseudocode

```c

```

## disassembly

```asm
0x157b80  ldarg.2
0x157b81  brfalse.s loc_157B9B
0x157b83  ldarg.2
0x157b84  callvirt instance int32 [mscorlib]System.String::get_Length()
0x157b89  ldc.i4   0x190
0x157b8e  ble.s    loc_157B9B
0x157b90  ldstr    aLengthOfParame_41// "Length of parameter DocDirName exceeds "...
0x157b95  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x157b9a  throw
0x157b9b  ldarg.3
0x157b9c  brfalse.s loc_157BB6
0x157b9e  ldarg.3
0x157b9f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x157ba4  ldc.i4   0x190
0x157ba9  ble.s    loc_157BB6
0x157bab  ldstr    aLengthOfParame_42// "Length of parameter DocLeafName exceeds"...
0x157bb0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x157bb5  throw
0x157bb6  ldarg.s  0x19
0x157bb8  brfalse.s loc_157BD3
0x157bba  ldarg.s  0x19
0x157bbc  callvirt instance int32 [mscorlib]System.String::get_Length()
0x157bc1  ldc.i4   0xFF
0x157bc6  ble.s    loc_157BD3
0x157bc8  ldstr    aLengthOfParame_52// "Length of parameter ProgId exceeds spec"...
0x157bcd  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x157bd2  throw
0x157bd3  ldarg.s  0x1C
0x157bd5  brfalse.s loc_157BF0
0x157bd7  ldarg.s  0x1C
0x157bd9  callvirt instance int32 [mscorlib]System.String::get_Length()
0x157bde  ldc.i4   0x3FF
0x157be3  ble.s    loc_157BF0
0x157be5  ldstr    aLengthOfParame_54// "Length of parameter Comment exceeds spe"...
0x157bea  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x157bef  throw
0x157bf0  ldarg.s  0x1F
0x157bf2  brfalse.s loc_157C0D
0x157bf4  ldarg.s  0x1F
0x157bf6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x157bfb  ldc.i4   0x190
0x157c00  ble.s    loc_157C0D
0x157c02  ldstr    aLengthOfParame_355// "Length of parameter WelcomePageUrl exce"...
0x157c07  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x157c0c  throw
0x157c0d  ldarg.s  0x23
0x157c0f  brfalse.s loc_157C2A
0x157c11  ldarg.s  0x23
0x157c13  callvirt instance int32 [mscorlib]System.String::get_Length()
0x157c18  ldc.i4   0xFF
0x157c1d  ble.s    loc_157C2A
0x157c1f  ldstr    aLengthOfParame_53// "Length of parameter VirusInfo exceeds s"...
0x157c24  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x157c29  throw
0x157c2a  ldarg.s  0x37
0x157c2c  brfalse.s loc_157C44
0x157c2e  ldarg.s  0x37
0x157c30  ldlen
0x157c31  conv.i4
0x157c32  ldc.i4   0x400
0x157c37  ble.s    loc_157C44
0x157c39  ldstr    aLengthOfParame_56// "Length of parameter StreamHash exceeds "...
0x157c3e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x157c43  throw
0x157c44  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlCommand::.ctor()
0x157c49  stloc.0
0x157c4a  ldloc.0
0x157c4b  ldstr    aDboProcUpdated_8// "dbo.proc_UpdateDocument"
0x157c50  callvirt instance void Microsoft.SharePoint.Utilities.SPSqlCommand::SetStoredProcedure(string strProc)
0x157c55  ldarga.s 0
0x157c57  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x157c5c  brtrue.s loc_157C7C
0x157c5e  ldloc.0
0x157c5f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157c64  ldstr    aDocsiteid// "@DocSiteId"
0x157c69  ldc.i4.s 0xE
0x157c6b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157c70  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x157c75  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157c7a  br.s     loc_157C9F
0x157c7c  ldloc.0
0x157c7d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157c82  ldstr    aDocsiteid// "@DocSiteId"
0x157c87  ldc.i4.s 0xE
0x157c89  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157c8e  ldarga.s 0
0x157c90  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x157c95  box      [mscorlib]System.Guid
0x157c9a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157c9f  ldarga.s 1
0x157ca1  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x157ca6  brtrue.s loc_157CC6
0x157ca8  ldloc.0
0x157ca9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157cae  ldstr    aDocwebid// "@DocWebId"
0x157cb3  ldc.i4.s 0xE
0x157cb5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157cba  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x157cbf  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157cc4  br.s     loc_157CE9
0x157cc6  ldloc.0
0x157cc7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157ccc  ldstr    aDocwebid// "@DocWebId"
0x157cd1  ldc.i4.s 0xE
0x157cd3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157cd8  ldarga.s 1
0x157cda  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x157cdf  box      [mscorlib]System.Guid
0x157ce4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157ce9  ldarg.2
0x157cea  brtrue.s loc_157D0A
0x157cec  ldloc.0
0x157ced  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157cf2  ldstr    aDocdirname// "@DocDirName"
0x157cf7  ldc.i4.s 0xC
0x157cf9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157cfe  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x157d03  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157d08  br.s     loc_157D22
0x157d0a  ldloc.0
0x157d0b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157d10  ldstr    aDocdirname// "@DocDirName"
0x157d15  ldc.i4.s 0xC
0x157d17  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157d1c  ldarg.2
0x157d1d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157d22  ldarg.3
0x157d23  brtrue.s loc_157D43
0x157d25  ldloc.0
0x157d26  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157d2b  ldstr    aDocleafname// "@DocLeafName"
0x157d30  ldc.i4.s 0xC
0x157d32  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157d37  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x157d3c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157d41  br.s     loc_157D5B
0x157d43  ldloc.0
0x157d44  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157d49  ldstr    aDocleafname// "@DocLeafName"
0x157d4e  ldc.i4.s 0xC
0x157d50  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157d55  ldarg.3
0x157d56  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157d5b  ldarga.s 4
0x157d5d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x157d62  brtrue.s loc_157D81
0x157d64  ldloc.0
0x157d65  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157d6a  ldstr    aSendingcontent// "@SendingContent"
0x157d6f  ldc.i4.2
0x157d70  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157d75  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x157d7a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157d7f  br.s     loc_157DA3
0x157d81  ldloc.0
0x157d82  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157d87  ldstr    aSendingcontent// "@SendingContent"
0x157d8c  ldc.i4.2
0x157d8d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157d92  ldarga.s 4
0x157d94  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x157d99  box      [mscorlib]System.Boolean
0x157d9e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157da3  ldarg.s  5
0x157da5  brtrue.s loc_157DC5
0x157da7  ldloc.0
0x157da8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157dad  ldstr    aDocmetainfo// "@DocMetaInfo"
0x157db2  ldc.i4.s 0x15
0x157db4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157db9  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x157dbe  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157dc3  br.s     loc_157DDE
0x157dc5  ldloc.0
0x157dc6  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157dcb  ldstr    aDocmetainfo// "@DocMetaInfo"
0x157dd0  ldc.i4.s 0x15
0x157dd2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157dd7  ldarg.s  5
0x157dd9  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157dde  ldarga.s 6
0x157de0  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x157de5  brtrue.s loc_157E04
0x157de7  ldloc.0
0x157de8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157ded  ldstr    aDocsize// "@DocSize"
0x157df2  ldc.i4.8
0x157df3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157df8  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x157dfd  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157e02  br.s     loc_157E26
0x157e04  ldloc.0
0x157e05  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157e0a  ldstr    aDocsize// "@DocSize"
0x157e0f  ldc.i4.8
0x157e10  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157e15  ldarga.s 6
0x157e17  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x157e1c  box      [mscorlib]System.Int32
0x157e21  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157e26  ldarga.s 7
0x157e28  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x157e2d  brtrue.s loc_157E4C
0x157e2f  ldloc.0
0x157e30  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157e35  ldstr    aDocmetainfosiz// "@DocMetaInfoSize"
0x157e3a  ldc.i4.8
0x157e3b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157e40  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x157e45  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157e4a  br.s     loc_157E6E
0x157e4c  ldloc.0
0x157e4d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157e52  ldstr    aDocmetainfosiz// "@DocMetaInfoSize"
0x157e57  ldc.i4.8
0x157e58  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157e5d  ldarga.s 7
0x157e5f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x157e64  box      [mscorlib]System.Int32
0x157e69  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157e6e  ldarg.s  8
0x157e70  brtrue.s loc_157E90
0x157e72  ldloc.0
0x157e73  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157e78  ldstr    aDocfileformatm// "@DocFileFormatMetaInfo"
0x157e7d  ldc.i4.s 0x15
0x157e7f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157e84  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x157e89  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157e8e  br.s     loc_157EA9
0x157e90  ldloc.0
0x157e91  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157e96  ldstr    aDocfileformatm// "@DocFileFormatMetaInfo"
0x157e9b  ldc.i4.s 0x15
0x157e9d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157ea2  ldarg.s  8
0x157ea4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157ea9  ldarga.s 9
0x157eab  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x157eb0  brtrue.s loc_157ECF
0x157eb2  ldloc.0
0x157eb3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157eb8  ldstr    aDocfileformatm_0// "@DocFileFormatMetaInfoSize"
0x157ebd  ldc.i4.8
0x157ebe  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157ec3  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x157ec8  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157ecd  br.s     loc_157EF1
0x157ecf  ldloc.0
0x157ed0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157ed5  ldstr    aDocfileformatm_0// "@DocFileFormatMetaInfoSize"
0x157eda  ldc.i4.8
0x157edb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157ee0  ldarga.s 9
0x157ee2  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x157ee7  box      [mscorlib]System.Int32
0x157eec  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157ef1  ldarga.s 0xA
0x157ef3  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x157ef8  brtrue.s loc_157F17
0x157efa  ldloc.0
0x157efb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157f00  ldstr    aDocdirty// "@DocDirty"
0x157f05  ldc.i4.2
0x157f06  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157f0b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x157f10  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157f15  br.s     loc_157F39
0x157f17  ldloc.0
0x157f18  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157f1d  ldstr    aDocdirty// "@DocDirty"
0x157f22  ldc.i4.2
0x157f23  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157f28  ldarga.s 0xA
0x157f2a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x157f2f  box      [mscorlib]System.Boolean
0x157f34  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157f39  ldarga.s 0xB
0x157f3b  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x157f40  brtrue.s loc_157F5F
0x157f42  ldloc.0
0x157f43  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157f48  ldstr    aDocetagversion// "@DocETagVersion"
0x157f4d  ldc.i4.8
0x157f4e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157f53  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x157f58  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157f5d  br.s     loc_157F81
0x157f5f  ldloc.0
0x157f60  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x157f65  ldstr    aDocetagversion// "@DocETagVersion"
0x157f6a  ldc.i4.8
0x157f6b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x157f70  ldarga.s 0xB
0x157f72  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x157f77  box      [mscorlib]System.Int32
0x157f7c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x157f81  ldarga.s 0xC
0x157f83  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x157f88  brtrue.s loc_157FA7
  ... truncated ...
```
