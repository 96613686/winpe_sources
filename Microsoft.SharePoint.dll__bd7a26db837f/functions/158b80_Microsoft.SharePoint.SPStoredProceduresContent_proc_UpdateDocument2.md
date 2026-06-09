# Microsoft.SharePoint.SPStoredProceduresContent::proc_UpdateDocument2

- ea: `0x158b80`
- end: `0x159b72`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::proc_UpdateDocument2`
- size: `4082`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x158b80`
- `0x8e5050`
- `0x8e50a0`
- `0x8e50b0`
- `0x8e5130`

## string_xrefs

- `0x159020`: `@DocIncomingCreatedDTM`
- `0x15903d`: `@DocIncomingCreatedDTM`
- `0x159068`: `@DocIncomingDTM`
- `0x159085`: `@DocIncomingDTM`
- `0x1593fe`: `@Comment`
- `0x15941c`: `@Comment`
- `0x1592a8`: `@UpdateFlags`
- `0x1592c5`: `@UpdateFlags`
- `0x1594c9`: `@WelcomePageUrl`
- `0x1594e7`: `@WelcomePageUrl`
- `0x159504`: `@WelcomePageParameters`
- `0x159522`: `@WelcomePageParameters`
- `0x1597fc`: `@FileFragmentPartitionsToDelete`
- `0x15981a`: `@FileFragmentPartitionsToDelete`
- `0x159837`: `@PartitionsToDelete`
- `0x159855`: `@PartitionsToDelete`
- `0x158be5`: `Length of parameter Comment exceeds specified max for the column`
- `0x158c02`: `Length of parameter WelcomePageUrl exceeds specified max for the column`
- `0x158c4b`: `dbo.proc_UpdateDocument2`

## pseudocode

```c

```

## disassembly

```asm
0x158b80  ldarg.2
0x158b81  brfalse.s loc_158B9B
0x158b83  ldarg.2
0x158b84  callvirt instance int32 [mscorlib]System.String::get_Length()
0x158b89  ldc.i4   0x190
0x158b8e  ble.s    loc_158B9B
0x158b90  ldstr    aLengthOfParame_41// "Length of parameter DocDirName exceeds "...
0x158b95  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x158b9a  throw
0x158b9b  ldarg.3
0x158b9c  brfalse.s loc_158BB6
0x158b9e  ldarg.3
0x158b9f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x158ba4  ldc.i4   0x190
0x158ba9  ble.s    loc_158BB6
0x158bab  ldstr    aLengthOfParame_42// "Length of parameter DocLeafName exceeds"...
0x158bb0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x158bb5  throw
0x158bb6  ldarg.s  0x19
0x158bb8  brfalse.s loc_158BD3
0x158bba  ldarg.s  0x19
0x158bbc  callvirt instance int32 [mscorlib]System.String::get_Length()
0x158bc1  ldc.i4   0xFF
0x158bc6  ble.s    loc_158BD3
0x158bc8  ldstr    aLengthOfParame_52// "Length of parameter ProgId exceeds spec"...
0x158bcd  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x158bd2  throw
0x158bd3  ldarg.s  0x1C
0x158bd5  brfalse.s loc_158BF0
0x158bd7  ldarg.s  0x1C
0x158bd9  callvirt instance int32 [mscorlib]System.String::get_Length()
0x158bde  ldc.i4   0x3FF
0x158be3  ble.s    loc_158BF0
0x158be5  ldstr    aLengthOfParame_54// "Length of parameter Comment exceeds spe"...
0x158bea  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x158bef  throw
0x158bf0  ldarg.s  0x1F
0x158bf2  brfalse.s loc_158C0D
0x158bf4  ldarg.s  0x1F
0x158bf6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x158bfb  ldc.i4   0x190
0x158c00  ble.s    loc_158C0D
0x158c02  ldstr    aLengthOfParame_355// "Length of parameter WelcomePageUrl exce"...
0x158c07  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x158c0c  throw
0x158c0d  ldarg.s  0x23
0x158c0f  brfalse.s loc_158C2A
0x158c11  ldarg.s  0x23
0x158c13  callvirt instance int32 [mscorlib]System.String::get_Length()
0x158c18  ldc.i4   0xFF
0x158c1d  ble.s    loc_158C2A
0x158c1f  ldstr    aLengthOfParame_53// "Length of parameter VirusInfo exceeds s"...
0x158c24  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x158c29  throw
0x158c2a  ldarg.s  0x37
0x158c2c  brfalse.s loc_158C44
0x158c2e  ldarg.s  0x37
0x158c30  ldlen
0x158c31  conv.i4
0x158c32  ldc.i4   0x400
0x158c37  ble.s    loc_158C44
0x158c39  ldstr    aLengthOfParame_56// "Length of parameter StreamHash exceeds "...
0x158c3e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x158c43  throw
0x158c44  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlCommand::.ctor()
0x158c49  stloc.0
0x158c4a  ldloc.0
0x158c4b  ldstr    aDboProcUpdated_9// "dbo.proc_UpdateDocument2"
0x158c50  callvirt instance void Microsoft.SharePoint.Utilities.SPSqlCommand::SetStoredProcedure(string strProc)
0x158c55  ldarga.s 0
0x158c57  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x158c5c  brtrue.s loc_158C7C
0x158c5e  ldloc.0
0x158c5f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158c64  ldstr    aDocsiteid// "@DocSiteId"
0x158c69  ldc.i4.s 0xE
0x158c6b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158c70  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x158c75  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158c7a  br.s     loc_158C9F
0x158c7c  ldloc.0
0x158c7d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158c82  ldstr    aDocsiteid// "@DocSiteId"
0x158c87  ldc.i4.s 0xE
0x158c89  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158c8e  ldarga.s 0
0x158c90  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x158c95  box      [mscorlib]System.Guid
0x158c9a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158c9f  ldarga.s 1
0x158ca1  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x158ca6  brtrue.s loc_158CC6
0x158ca8  ldloc.0
0x158ca9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158cae  ldstr    aDocwebid// "@DocWebId"
0x158cb3  ldc.i4.s 0xE
0x158cb5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158cba  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x158cbf  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158cc4  br.s     loc_158CE9
0x158cc6  ldloc.0
0x158cc7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158ccc  ldstr    aDocwebid// "@DocWebId"
0x158cd1  ldc.i4.s 0xE
0x158cd3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158cd8  ldarga.s 1
0x158cda  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x158cdf  box      [mscorlib]System.Guid
0x158ce4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158ce9  ldarg.2
0x158cea  brtrue.s loc_158D0A
0x158cec  ldloc.0
0x158ced  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158cf2  ldstr    aDocdirname// "@DocDirName"
0x158cf7  ldc.i4.s 0xC
0x158cf9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158cfe  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x158d03  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158d08  br.s     loc_158D22
0x158d0a  ldloc.0
0x158d0b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158d10  ldstr    aDocdirname// "@DocDirName"
0x158d15  ldc.i4.s 0xC
0x158d17  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158d1c  ldarg.2
0x158d1d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158d22  ldarg.3
0x158d23  brtrue.s loc_158D43
0x158d25  ldloc.0
0x158d26  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158d2b  ldstr    aDocleafname// "@DocLeafName"
0x158d30  ldc.i4.s 0xC
0x158d32  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158d37  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x158d3c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158d41  br.s     loc_158D5B
0x158d43  ldloc.0
0x158d44  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158d49  ldstr    aDocleafname// "@DocLeafName"
0x158d4e  ldc.i4.s 0xC
0x158d50  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158d55  ldarg.3
0x158d56  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158d5b  ldarga.s 4
0x158d5d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x158d62  brtrue.s loc_158D81
0x158d64  ldloc.0
0x158d65  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158d6a  ldstr    aSendingcontent// "@SendingContent"
0x158d6f  ldc.i4.2
0x158d70  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158d75  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x158d7a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158d7f  br.s     loc_158DA3
0x158d81  ldloc.0
0x158d82  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158d87  ldstr    aSendingcontent// "@SendingContent"
0x158d8c  ldc.i4.2
0x158d8d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158d92  ldarga.s 4
0x158d94  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x158d99  box      [mscorlib]System.Boolean
0x158d9e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158da3  ldarg.s  5
0x158da5  brtrue.s loc_158DC5
0x158da7  ldloc.0
0x158da8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158dad  ldstr    aDocmetainfo// "@DocMetaInfo"
0x158db2  ldc.i4.s 0x15
0x158db4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158db9  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x158dbe  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158dc3  br.s     loc_158DDE
0x158dc5  ldloc.0
0x158dc6  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158dcb  ldstr    aDocmetainfo// "@DocMetaInfo"
0x158dd0  ldc.i4.s 0x15
0x158dd2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158dd7  ldarg.s  5
0x158dd9  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158dde  ldarga.s 6
0x158de0  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x158de5  brtrue.s loc_158E04
0x158de7  ldloc.0
0x158de8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158ded  ldstr    aDocsize// "@DocSize"
0x158df2  ldc.i4.0
0x158df3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158df8  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x158dfd  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158e02  br.s     loc_158E26
0x158e04  ldloc.0
0x158e05  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158e0a  ldstr    aDocsize// "@DocSize"
0x158e0f  ldc.i4.0
0x158e10  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158e15  ldarga.s 6
0x158e17  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x158e1c  box      [mscorlib]System.Int64
0x158e21  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158e26  ldarga.s 7
0x158e28  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x158e2d  brtrue.s loc_158E4C
0x158e2f  ldloc.0
0x158e30  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158e35  ldstr    aDocmetainfosiz// "@DocMetaInfoSize"
0x158e3a  ldc.i4.8
0x158e3b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158e40  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x158e45  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158e4a  br.s     loc_158E6E
0x158e4c  ldloc.0
0x158e4d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158e52  ldstr    aDocmetainfosiz// "@DocMetaInfoSize"
0x158e57  ldc.i4.8
0x158e58  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158e5d  ldarga.s 7
0x158e5f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x158e64  box      [mscorlib]System.Int32
0x158e69  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158e6e  ldarg.s  8
0x158e70  brtrue.s loc_158E90
0x158e72  ldloc.0
0x158e73  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158e78  ldstr    aDocfileformatm// "@DocFileFormatMetaInfo"
0x158e7d  ldc.i4.s 0x15
0x158e7f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158e84  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x158e89  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158e8e  br.s     loc_158EA9
0x158e90  ldloc.0
0x158e91  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158e96  ldstr    aDocfileformatm// "@DocFileFormatMetaInfo"
0x158e9b  ldc.i4.s 0x15
0x158e9d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158ea2  ldarg.s  8
0x158ea4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158ea9  ldarga.s 9
0x158eab  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x158eb0  brtrue.s loc_158ECF
0x158eb2  ldloc.0
0x158eb3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158eb8  ldstr    aDocfileformatm_0// "@DocFileFormatMetaInfoSize"
0x158ebd  ldc.i4.8
0x158ebe  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158ec3  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x158ec8  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158ecd  br.s     loc_158EF1
0x158ecf  ldloc.0
0x158ed0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158ed5  ldstr    aDocfileformatm_0// "@DocFileFormatMetaInfoSize"
0x158eda  ldc.i4.8
0x158edb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158ee0  ldarga.s 9
0x158ee2  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x158ee7  box      [mscorlib]System.Int32
0x158eec  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158ef1  ldarga.s 0xA
0x158ef3  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x158ef8  brtrue.s loc_158F17
0x158efa  ldloc.0
0x158efb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158f00  ldstr    aDocdirty// "@DocDirty"
0x158f05  ldc.i4.2
0x158f06  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158f0b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x158f10  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158f15  br.s     loc_158F39
0x158f17  ldloc.0
0x158f18  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158f1d  ldstr    aDocdirty// "@DocDirty"
0x158f22  ldc.i4.2
0x158f23  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158f28  ldarga.s 0xA
0x158f2a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x158f2f  box      [mscorlib]System.Boolean
0x158f34  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158f39  ldarga.s 0xB
0x158f3b  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x158f40  brtrue.s loc_158F5F
0x158f42  ldloc.0
0x158f43  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158f48  ldstr    aDocetagversion// "@DocETagVersion"
0x158f4d  ldc.i4.8
0x158f4e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158f53  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x158f58  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158f5d  br.s     loc_158F81
0x158f5f  ldloc.0
0x158f60  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x158f65  ldstr    aDocetagversion// "@DocETagVersion"
0x158f6a  ldc.i4.8
0x158f6b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x158f70  ldarga.s 0xB
0x158f72  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x158f77  box      [mscorlib]System.Int32
0x158f7c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x158f81  ldarga.s 0xC
0x158f83  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x158f88  brtrue.s loc_158FA7
  ... truncated ...
```
