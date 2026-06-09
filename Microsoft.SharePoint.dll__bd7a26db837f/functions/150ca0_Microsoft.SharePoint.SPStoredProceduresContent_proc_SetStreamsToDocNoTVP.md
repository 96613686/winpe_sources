# Microsoft.SharePoint.SPStoredProceduresContent::proc_SetStreamsToDocNoTVP

- ea: `0x150ca0`
- end: `0x1529dd`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::proc_SetStreamsToDocNoTVP`
- size: `7485`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x150ca0`
- `0x8e5050`
- `0x8e50a0`
- `0x8e50b0`
- `0x8e5130`

## string_xrefs

- `0x15297a`: `@DeleteAllStreams`
- `0x152997`: `@DeleteAllStreams`
- `0x15207a`: `@BSNToDelete0`
- `0x152097`: `@BSNToDelete0`
- `0x1520c2`: `@BSNToDelete1`
- `0x1520df`: `@BSNToDelete1`
- `0x15210a`: `@BSNToDelete2`
- `0x152127`: `@BSNToDelete2`
- `0x152152`: `@BSNToDelete3`
- `0x15216f`: `@BSNToDelete3`
- `0x15219a`: `@BSNToDelete4`
- `0x1521b7`: `@BSNToDelete4`
- `0x1521e2`: `@BSNToDelete5`
- `0x1521ff`: `@BSNToDelete5`
- `0x15222a`: `@BSNToDelete6`
- `0x152247`: `@BSNToDelete6`
- `0x152272`: `@BSNToDelete7`
- `0x15228f`: `@BSNToDelete7`
- `0x1522ba`: `@BSNToDelete8`
- `0x1522d7`: `@BSNToDelete8`
- `0x152302`: `@BSNToDelete9`
- `0x15231f`: `@BSNToDelete9`
- `0x15234a`: `@BSNToDelete10`
- `0x152367`: `@BSNToDelete10`
- `0x152392`: `@BSNToDelete11`
- `0x1523af`: `@BSNToDelete11`
- `0x1523da`: `@BSNToDelete12`
- `0x1523f7`: `@BSNToDelete12`
- `0x152422`: `@BSNToDelete13`
- `0x15243f`: `@BSNToDelete13`
- `0x15246a`: `@BSNToDelete14`
- `0x152487`: `@BSNToDelete14`
- `0x1524b2`: `@BSNToDelete15`
- `0x1524cf`: `@BSNToDelete15`
- `0x1524fa`: `@BSNToDelete16`
- `0x152517`: `@BSNToDelete16`
- `0x152542`: `@BSNToDelete17`
- `0x15255f`: `@BSNToDelete17`
- `0x15258a`: `@BSNToDelete18`
- `0x1525a7`: `@BSNToDelete18`
- `0x1525d2`: `@BSNToDelete19`
- `0x1525ef`: `@BSNToDelete19`
- `0x15261a`: `@BSNToDelete20`
- `0x152637`: `@BSNToDelete20`
- `0x152662`: `@BSNToDelete21`
- `0x15267f`: `@BSNToDelete21`
- `0x1526aa`: `@BSNToDelete22`
- `0x1526c7`: `@BSNToDelete22`
- `0x1526f2`: `@BSNToDelete23`
- `0x15270f`: `@BSNToDelete23`
- `0x15273a`: `@BSNToDelete24`
- `0x152757`: `@BSNToDelete24`
- `0x152782`: `@BSNToDelete25`
- `0x15279f`: `@BSNToDelete25`
- `0x1527ca`: `@BSNToDelete26`
- `0x1527e7`: `@BSNToDelete26`
- `0x152812`: `@BSNToDelete27`
- `0x15282f`: `@BSNToDelete27`
- `0x15285a`: `@BSNToDelete28`
- `0x152877`: `@BSNToDelete28`
- `0x1528a2`: `@BSNToDelete29`
- `0x1528bf`: `@BSNToDelete29`
- `0x1528ea`: `@BSNToDelete30`
- `0x152907`: `@BSNToDelete30`
- `0x152932`: `@BSNToDelete31`
- `0x15294f`: `@BSNToDelete31`

## pseudocode

```c

```

## disassembly

```asm
0x150ca0  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlCommand::.ctor()
0x150ca5  stloc.0
0x150ca6  ldloc.0
0x150ca7  ldstr    aDboProcSetstre_0// "dbo.proc_SetStreamsToDocNoTVP"
0x150cac  callvirt instance void Microsoft.SharePoint.Utilities.SPSqlCommand::SetStoredProcedure(string strProc)
0x150cb1  ldarga.s 0
0x150cb3  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x150cb8  brtrue.s loc_150CD8
0x150cba  ldloc.0
0x150cbb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150cc0  ldstr    aSiteid_1// "@SiteId"
0x150cc5  ldc.i4.s 0xE
0x150cc7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150ccc  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x150cd1  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150cd6  br.s     loc_150CFB
0x150cd8  ldloc.0
0x150cd9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150cde  ldstr    aSiteid_1// "@SiteId"
0x150ce3  ldc.i4.s 0xE
0x150ce5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150cea  ldarga.s 0
0x150cec  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x150cf1  box      [mscorlib]System.Guid
0x150cf6  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150cfb  ldarga.s 1
0x150cfd  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x150d02  brtrue.s loc_150D22
0x150d04  ldloc.0
0x150d05  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150d0a  ldstr    aDocid_1// "@DocId"
0x150d0f  ldc.i4.s 0xE
0x150d11  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150d16  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x150d1b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150d20  br.s     loc_150D45
0x150d22  ldloc.0
0x150d23  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150d28  ldstr    aDocid_1// "@DocId"
0x150d2d  ldc.i4.s 0xE
0x150d2f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150d34  ldarga.s 1
0x150d36  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x150d3b  box      [mscorlib]System.Guid
0x150d40  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150d45  ldarga.s 2
0x150d47  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x150d4c  brtrue.s loc_150D6B
0x150d4e  ldloc.0
0x150d4f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150d54  ldstr    aHistversion// "@HistVersion"
0x150d59  ldc.i4.8
0x150d5a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150d5f  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x150d64  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150d69  br.s     loc_150D8D
0x150d6b  ldloc.0
0x150d6c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150d71  ldstr    aHistversion// "@HistVersion"
0x150d76  ldc.i4.8
0x150d77  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150d7c  ldarga.s 2
0x150d7e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x150d83  box      [mscorlib]System.Int32
0x150d88  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150d8d  ldarg.3
0x150d8e  stloc.1
0x150d8f  ldloca.s 1
0x150d91  call     instance bool valuetype [mscorlib]System.Nullable`1<unsigned int8>::get_HasValue()
0x150d96  brtrue.s loc_150DA3
0x150d98  ldloca.s 2
0x150d9a  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x150da0  ldloc.2
0x150da1  br.s     loc_150DAF
0x150da3  ldloca.s 1
0x150da5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<unsigned int8>::GetValueOrDefault()
0x150daa  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x150daf  stloc.3
0x150db0  ldloca.s 3
0x150db2  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x150db7  brtrue.s loc_150DD7
0x150db9  ldloc.0
0x150dba  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150dbf  ldstr    aLevel_1// "@Level"
0x150dc4  ldc.i4.s 0x14
0x150dc6  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150dcb  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x150dd0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150dd5  br.s     loc_150DFA
0x150dd7  ldloc.0
0x150dd8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150ddd  ldstr    aLevel_1// "@Level"
0x150de2  ldc.i4.s 0x14
0x150de4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150de9  ldarga.s 3
0x150deb  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<unsigned int8>::get_Value()
0x150df0  box      [mscorlib]System.Byte
0x150df5  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150dfa  ldarg.s  4
0x150dfc  stloc.s  4
0x150dfe  ldloca.s 4
0x150e00  call     instance bool valuetype [mscorlib]System.Nullable`1<unsigned int8>::get_HasValue()
0x150e05  brtrue.s loc_150E13
0x150e07  ldloca.s 5
0x150e09  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x150e0f  ldloc.s  5
0x150e11  br.s     loc_150E1F
0x150e13  ldloca.s 4
0x150e15  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<unsigned int8>::GetValueOrDefault()
0x150e1a  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x150e1f  stloc.s  6
0x150e21  ldloca.s 6
0x150e23  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x150e28  brtrue.s loc_150E48
0x150e2a  ldloc.0
0x150e2b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150e30  ldstr    aPartition_1// "@Partition"
0x150e35  ldc.i4.s 0x14
0x150e37  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150e3c  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x150e41  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150e46  br.s     loc_150E6B
0x150e48  ldloc.0
0x150e49  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150e4e  ldstr    aPartition_1// "@Partition"
0x150e53  ldc.i4.s 0x14
0x150e55  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150e5a  ldarga.s 4
0x150e5c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<unsigned int8>::get_Value()
0x150e61  box      [mscorlib]System.Byte
0x150e66  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150e6b  ldarga.s 5
0x150e6d  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x150e72  brtrue.s loc_150E91
0x150e74  ldloc.0
0x150e75  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150e7a  ldstr    aBsntoadd0// "@BSNToAdd0"
0x150e7f  ldc.i4.0
0x150e80  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150e85  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x150e8a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150e8f  br.s     loc_150EB3
0x150e91  ldloc.0
0x150e92  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150e97  ldstr    aBsntoadd0// "@BSNToAdd0"
0x150e9c  ldc.i4.0
0x150e9d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150ea2  ldarga.s 5
0x150ea4  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x150ea9  box      [mscorlib]System.Int64
0x150eae  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150eb3  ldarga.s 6
0x150eb5  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x150eba  brtrue.s loc_150ED9
0x150ebc  ldloc.0
0x150ebd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150ec2  ldstr    aStreamidtoadd0// "@StreamIdToAdd0"
0x150ec7  ldc.i4.0
0x150ec8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150ecd  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x150ed2  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150ed7  br.s     loc_150EFB
0x150ed9  ldloc.0
0x150eda  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150edf  ldstr    aStreamidtoadd0// "@StreamIdToAdd0"
0x150ee4  ldc.i4.0
0x150ee5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150eea  ldarga.s 6
0x150eec  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x150ef1  box      [mscorlib]System.Int64
0x150ef6  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150efb  ldarga.s 7
0x150efd  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x150f02  brtrue.s loc_150F21
0x150f04  ldloc.0
0x150f05  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150f0a  ldstr    aBsntoadd1// "@BSNToAdd1"
0x150f0f  ldc.i4.0
0x150f10  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150f15  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x150f1a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150f1f  br.s     loc_150F43
0x150f21  ldloc.0
0x150f22  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150f27  ldstr    aBsntoadd1// "@BSNToAdd1"
0x150f2c  ldc.i4.0
0x150f2d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150f32  ldarga.s 7
0x150f34  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x150f39  box      [mscorlib]System.Int64
0x150f3e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150f43  ldarga.s 8
0x150f45  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x150f4a  brtrue.s loc_150F69
0x150f4c  ldloc.0
0x150f4d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150f52  ldstr    aStreamidtoadd1// "@StreamIdToAdd1"
0x150f57  ldc.i4.0
0x150f58  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150f5d  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x150f62  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150f67  br.s     loc_150F8B
0x150f69  ldloc.0
0x150f6a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150f6f  ldstr    aStreamidtoadd1// "@StreamIdToAdd1"
0x150f74  ldc.i4.0
0x150f75  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150f7a  ldarga.s 8
0x150f7c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x150f81  box      [mscorlib]System.Int64
0x150f86  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150f8b  ldarga.s 9
0x150f8d  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x150f92  brtrue.s loc_150FB1
0x150f94  ldloc.0
0x150f95  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150f9a  ldstr    aBsntoadd2// "@BSNToAdd2"
0x150f9f  ldc.i4.0
0x150fa0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150fa5  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x150faa  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150faf  br.s     loc_150FD3
0x150fb1  ldloc.0
0x150fb2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150fb7  ldstr    aBsntoadd2// "@BSNToAdd2"
0x150fbc  ldc.i4.0
0x150fbd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150fc2  ldarga.s 9
0x150fc4  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x150fc9  box      [mscorlib]System.Int64
0x150fce  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150fd3  ldarga.s 0xA
0x150fd5  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x150fda  brtrue.s loc_150FF9
0x150fdc  ldloc.0
0x150fdd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150fe2  ldstr    aStreamidtoadd2// "@StreamIdToAdd2"
0x150fe7  ldc.i4.0
0x150fe8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x150fed  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x150ff2  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x150ff7  br.s     loc_15101B
0x150ff9  ldloc.0
0x150ffa  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x150fff  ldstr    aStreamidtoadd2// "@StreamIdToAdd2"
0x151004  ldc.i4.0
0x151005  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15100a  ldarga.s 0xA
0x15100c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x151011  box      [mscorlib]System.Int64
0x151016  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15101b  ldarga.s 0xB
0x15101d  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x151022  brtrue.s loc_151041
0x151024  ldloc.0
0x151025  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15102a  ldstr    aBsntoadd3// "@BSNToAdd3"
0x15102f  ldc.i4.0
0x151030  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x151035  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15103a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15103f  br.s     loc_151063
0x151041  ldloc.0
0x151042  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x151047  ldstr    aBsntoadd3// "@BSNToAdd3"
0x15104c  ldc.i4.0
0x15104d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x151052  ldarga.s 0xB
0x151054  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x151059  box      [mscorlib]System.Int64
0x15105e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x151063  ldarga.s 0xC
0x151065  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x15106a  brtrue.s loc_151089
0x15106c  ldloc.0
0x15106d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x151072  ldstr    aStreamidtoadd3// "@StreamIdToAdd3"
0x151077  ldc.i4.0
0x151078  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15107d  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x151082  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x151087  br.s     loc_1510AB
0x151089  ldloc.0
0x15108a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15108f  ldstr    aStreamidtoadd3// "@StreamIdToAdd3"
0x151094  ldc.i4.0
0x151095  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15109a  ldarga.s 0xC
0x15109c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int64>::get_Value()
0x1510a1  box      [mscorlib]System.Int64
0x1510a6  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1510ab  ldarga.s 0xD
0x1510ad  call     instance bool valuetype [mscorlib]System.Nullable`1<int64>::get_HasValue()
0x1510b2  brtrue.s loc_1510D1
0x1510b4  ldloc.0
0x1510b5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x1510ba  ldstr    aBsntoadd4// "@BSNToAdd4"
0x1510bf  ldc.i4.0
0x1510c0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x1510c5  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
  ... truncated ...
```
