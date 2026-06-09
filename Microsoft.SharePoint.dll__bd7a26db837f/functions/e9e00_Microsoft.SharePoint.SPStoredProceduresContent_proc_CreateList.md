# Microsoft.SharePoint.SPStoredProceduresContent::proc_CreateList

- ea: `0xe9e00`
- end: `0xea9fc`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::proc_CreateList`
- size: `3068`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0xe9e00`
- `0x8e5050`
- `0x8e50a0`
- `0x8e50b0`
- `0x8e5130`

## string_xrefs

- `0xea9b1`: `@ComplianceTag`
- `0xea9d3`: `@ComplianceFlags`
- `0xea2d3`: `@ServerTemplate`
- `0xea2f0`: `@ServerTemplate`
- `0xea241`: `@bCreateAttachmentsSubFolder`
- `0xea25e`: `@bCreateAttachmentsSubFolder`
- `0xea31b`: `@DocLibTemplate`
- `0xea339`: `@DocLibTemplate`
- `0xea3db`: `@ReadSecurity`
- `0xea3f8`: `@ReadSecurity`
- `0xea423`: `@WriteSecurity`
- `0xea440`: `@WriteSecurity`
- `0xea960`: `@TimeCreated`
- `0xe9f69`: `Length of parameter ComplianceTag exceeds specified max for the column`
- `0xe9f7b`: `dbo.proc_CreateList`

## pseudocode

```c

```

## disassembly

```asm
0xe9e00  ldarg.3
0xe9e01  brfalse.s loc_E9E1B
0xe9e03  ldarg.3
0xe9e04  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe9e09  ldc.i4   0x190
0xe9e0e  ble.s    loc_E9E1B
0xe9e10  ldstr    aLengthOfParame_39// "Length of parameter DirName exceeds spe"...
0xe9e15  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe9e1a  throw
0xe9e1b  ldarg.s  4
0xe9e1d  brfalse.s loc_E9E35
0xe9e1f  ldarg.s  4
0xe9e21  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe9e26  ldc.i4.s 0x32
0xe9e28  ble.s    loc_E9E35
0xe9e2a  ldstr    aLengthOfParame_152// "Length of parameter FolderNameBase exce"...
0xe9e2f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe9e34  throw
0xe9e35  ldarg.s  6
0xe9e37  brfalse.s loc_E9E52
0xe9e39  ldarg.s  6
0xe9e3b  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe9e40  ldc.i4   0xFF
0xe9e45  ble.s    loc_E9E52
0xe9e47  ldstr    aLengthOfParame_102// "Length of parameter Title exceeds speci"...
0xe9e4c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe9e51  throw
0xe9e52  ldarg.s  0xE
0xe9e54  brfalse.s loc_E9E6F
0xe9e56  ldarg.s  0xE
0xe9e58  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe9e5d  ldc.i4   0xFF
0xe9e62  ble.s    loc_E9E6F
0xe9e64  ldstr    aLengthOfParame_153// "Length of parameter ImageUrl exceeds sp"...
0xe9e69  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe9e6e  throw
0xe9e6f  ldarg.s  0xF
0xe9e71  brfalse.s loc_E9E8C
0xe9e73  ldarg.s  0xF
0xe9e75  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe9e7a  ldc.i4   0x200
0xe9e7f  ble.s    loc_E9E8C
0xe9e81  ldstr    aLengthOfParame_154// "Length of parameter SendToLocation exce"...
0xe9e86  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe9e8b  throw
0xe9e8c  ldarg.s  0x1E
0xe9e8e  brfalse.s loc_E9EA9
0xe9e90  ldarg.s  0x1E
0xe9e92  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe9e97  ldc.i4   0xFF
0xe9e9c  ble.s    loc_E9EA9
0xe9e9e  ldstr    aLengthOfParame_155// "Length of parameter EventSinkAssembly e"...
0xe9ea3  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe9ea8  throw
0xe9ea9  ldarg.s  0x1F
0xe9eab  brfalse.s loc_E9EC6
0xe9ead  ldarg.s  0x1F
0xe9eaf  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe9eb4  ldc.i4   0xFF
0xe9eb9  ble.s    loc_E9EC6
0xe9ebb  ldstr    aLengthOfParame_156// "Length of parameter EventSinkClass exce"...
0xe9ec0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe9ec5  throw
0xe9ec6  ldarg.s  0x20
0xe9ec8  brfalse.s loc_E9EE3
0xe9eca  ldarg.s  0x20
0xe9ecc  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe9ed1  ldc.i4   0xFF
0xe9ed6  ble.s    loc_E9EE3
0xe9ed8  ldstr    aLengthOfParame_157// "Length of parameter EventSinkData excee"...
0xe9edd  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe9ee2  throw
0xe9ee3  ldarg.s  0x23
0xe9ee5  brfalse.s loc_E9F00
0xe9ee7  ldarg.s  0x23
0xe9ee9  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe9eee  ldc.i4   0x208
0xe9ef3  ble.s    loc_E9F00
0xe9ef5  ldstr    aLengthOfParame_158// "Length of parameter TitleResource excee"...
0xe9efa  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe9eff  throw
0xe9f00  ldarg.s  0x24
0xe9f02  brfalse.s loc_E9F1D
0xe9f04  ldarg.s  0x24
0xe9f06  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe9f0b  ldc.i4   0x208
0xe9f10  ble.s    loc_E9F1D
0xe9f12  ldstr    aLengthOfParame_159// "Length of parameter DescriptionResource"...
0xe9f17  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe9f1c  throw
0xe9f1d  ldarg.s  0x25
0xe9f1f  brfalse.s loc_E9F3A
0xe9f21  ldarg.s  0x25
0xe9f23  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe9f28  ldc.i4   0x400
0xe9f2d  ble.s    loc_E9F3A
0xe9f2f  ldstr    aLengthOfParame_160// "Length of parameter ValidationFormula e"...
0xe9f34  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe9f39  throw
0xe9f3a  ldarg.s  0x26
0xe9f3c  brfalse.s loc_E9F57
0xe9f3e  ldarg.s  0x26
0xe9f40  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe9f45  ldc.i4   0x400
0xe9f4a  ble.s    loc_E9F57
0xe9f4c  ldstr    aLengthOfParame_161// "Length of parameter ValidationMessage e"...
0xe9f51  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe9f56  throw
0xe9f57  ldarg.s  0x2A
0xe9f59  brfalse.s loc_E9F74
0xe9f5b  ldarg.s  0x2A
0xe9f5d  callvirt instance int32 [mscorlib]System.String::get_Length()
0xe9f62  ldc.i4   0x1F4
0xe9f67  ble.s    loc_E9F74
0xe9f69  ldstr    aLengthOfParame_57// "Length of parameter ComplianceTag excee"...
0xe9f6e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe9f73  throw
0xe9f74  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlCommand::.ctor()
0xe9f79  stloc.0
0xe9f7a  ldloc.0
0xe9f7b  ldstr    aDboProcCreatel// "dbo.proc_CreateList"
0xe9f80  callvirt instance void Microsoft.SharePoint.Utilities.SPSqlCommand::SetStoredProcedure(string strProc)
0xe9f85  ldarga.s 0
0xe9f87  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xe9f8c  brtrue.s loc_E9FAC
0xe9f8e  ldloc.0
0xe9f8f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xe9f94  ldstr    aSiteid_1// "@SiteId"
0xe9f99  ldc.i4.s 0xE
0xe9f9b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xe9fa0  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xe9fa5  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xe9faa  br.s     loc_E9FCF
0xe9fac  ldloc.0
0xe9fad  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xe9fb2  ldstr    aSiteid_1// "@SiteId"
0xe9fb7  ldc.i4.s 0xE
0xe9fb9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xe9fbe  ldarga.s 0
0xe9fc0  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xe9fc5  box      [mscorlib]System.Guid
0xe9fca  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xe9fcf  ldarga.s 1
0xe9fd1  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xe9fd6  brtrue.s loc_E9FF6
0xe9fd8  ldloc.0
0xe9fd9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xe9fde  ldstr    aWebid_0// "@WebId"
0xe9fe3  ldc.i4.s 0xE
0xe9fe5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xe9fea  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xe9fef  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xe9ff4  br.s     loc_EA019
0xe9ff6  ldloc.0
0xe9ff7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xe9ffc  ldstr    aWebid_0// "@WebId"
0xea001  ldc.i4.s 0xE
0xea003  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xea008  ldarga.s 1
0xea00a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xea00f  box      [mscorlib]System.Guid
0xea014  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xea019  ldarga.s 2
0xea01b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0xea020  brtrue.s loc_EA040
0xea022  ldloc.0
0xea023  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xea028  ldstr    aListid_0// "@ListId"
0xea02d  ldc.i4.s 0xE
0xea02f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xea034  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xea039  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xea03e  br.s     loc_EA063
0xea040  ldloc.0
0xea041  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xea046  ldstr    aListid_0// "@ListId"
0xea04b  ldc.i4.s 0xE
0xea04d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xea052  ldarga.s 2
0xea054  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xea059  box      [mscorlib]System.Guid
0xea05e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xea063  ldarg.3
0xea064  brtrue.s loc_EA084
0xea066  ldloc.0
0xea067  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xea06c  ldstr    aDirname_0// "@DirName"
0xea071  ldc.i4.s 0xC
0xea073  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xea078  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xea07d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xea082  br.s     loc_EA09C
0xea084  ldloc.0
0xea085  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xea08a  ldstr    aDirname_0// "@DirName"
0xea08f  ldc.i4.s 0xC
0xea091  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xea096  ldarg.3
0xea097  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xea09c  ldarg.s  4
0xea09e  brtrue.s loc_EA0BE
0xea0a0  ldloc.0
0xea0a1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xea0a6  ldstr    aFoldernamebase// "@FolderNameBase"
0xea0ab  ldc.i4.s 0xC
0xea0ad  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xea0b2  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xea0b7  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xea0bc  br.s     loc_EA0D7
0xea0be  ldloc.0
0xea0bf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xea0c4  ldstr    aFoldernamebase// "@FolderNameBase"
0xea0c9  ldc.i4.s 0xC
0xea0cb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xea0d0  ldarg.s  4
0xea0d2  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xea0d7  ldarga.s 5
0xea0d9  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xea0de  brtrue.s loc_EA0FD
0xea0e0  ldloc.0
0xea0e1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xea0e6  ldstr    aBalternateurlo// "@bAlternateUrlOnCollision"
0xea0eb  ldc.i4.2
0xea0ec  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xea0f1  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xea0f6  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xea0fb  br.s     loc_EA11F
0xea0fd  ldloc.0
0xea0fe  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xea103  ldstr    aBalternateurlo// "@bAlternateUrlOnCollision"
0xea108  ldc.i4.2
0xea109  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xea10e  ldarga.s 5
0xea110  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0xea115  box      [mscorlib]System.Boolean
0xea11a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xea11f  ldarg.s  6
0xea121  brtrue.s loc_EA141
0xea123  ldloc.0
0xea124  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xea129  ldstr    aTitle// "@Title"
0xea12e  ldc.i4.s 0xC
0xea130  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xea135  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xea13a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xea13f  br.s     loc_EA15A
0xea141  ldloc.0
0xea142  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xea147  ldstr    aTitle// "@Title"
0xea14c  ldc.i4.s 0xC
0xea14e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xea153  ldarg.s  6
0xea155  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xea15a  ldarga.s 7
0xea15c  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xea161  brtrue.s loc_EA180
0xea163  ldloc.0
0xea164  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xea169  ldstr    aVersion_3// "@Version"
0xea16e  ldc.i4.8
0xea16f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xea174  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xea179  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xea17e  br.s     loc_EA1A2
0xea180  ldloc.0
0xea181  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xea186  ldstr    aVersion_3// "@Version"
0xea18b  ldc.i4.8
0xea18c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xea191  ldarga.s 7
0xea193  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xea198  box      [mscorlib]System.Int32
0xea19d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xea1a2  ldarga.s 8
0xea1a4  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xea1a9  brtrue.s loc_EA1C8
0xea1ab  ldloc.0
0xea1ac  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xea1b1  ldstr    aAuthor// "@Author"
0xea1b6  ldc.i4.8
0xea1b7  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xea1bc  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xea1c1  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xea1c6  br.s     loc_EA1EA
0xea1c8  ldloc.0
0xea1c9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xea1ce  ldstr    aAuthor// "@Author"
0xea1d3  ldc.i4.8
0xea1d4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0xea1d9  ldarga.s 8
0xea1db  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0xea1e0  box      [mscorlib]System.Int32
0xea1e5  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0xea1ea  ldarga.s 9
0xea1ec  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xea1f1  brtrue.s loc_EA210
0xea1f3  ldloc.0
0xea1f4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0xea1f9  ldstr    aBasetype// "@BaseType"
0xea1fe  ldc.i4.8
  ... truncated ...
```
