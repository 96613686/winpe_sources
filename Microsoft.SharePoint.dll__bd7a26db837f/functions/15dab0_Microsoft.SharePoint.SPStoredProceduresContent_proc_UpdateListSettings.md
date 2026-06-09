# Microsoft.SharePoint.SPStoredProceduresContent::proc_UpdateListSettings

- ea: `0x15dab0`
- end: `0x15e69f`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::proc_UpdateListSettings`
- size: `3055`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x15dab0`
- `0x8e5050`
- `0x8e50a0`
- `0x8e50b0`
- `0x8e5130`

## string_xrefs

- `0x15dd35`: `@ServerTemplate`
- `0x15dd52`: `@ServerTemplate`
- `0x15ddb8`: `@ReadSecurity`
- `0x15ddd5`: `@ReadSecurity`
- `0x15de00`: `@WriteSecurity`
- `0x15de1d`: `@WriteSecurity`
- `0x15dec8`: `@TemplateDirName`
- `0x15dee6`: `@TemplateDirName`
- `0x15df03`: `@TemplateLeafName`
- `0x15df21`: `@TemplateLeafName`
- `0x15e320`: `@AddOrRemoveFromNavBar`
- `0x15e33d`: `@AddOrRemoveFromNavBar`
- `0x15e48a`: `@RemoveSystemAlerts`
- `0x15e4a7`: `@RemoveSystemAlerts`
- `0x15dadf`: `Length of parameter TemplateDirName exceeds specified max for the column`
- `0x15dafc`: `Length of parameter TemplateLeafName exceeds specified max for the column`
- `0x15dbf6`: `dbo.proc_UpdateListSettings`

## pseudocode

```c

```

## disassembly

```asm
0x15dab0  ldarg.s  5
0x15dab2  brfalse.s loc_15DACD
0x15dab4  ldarg.s  5
0x15dab6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15dabb  ldc.i4   0xFF
0x15dac0  ble.s    loc_15DACD
0x15dac2  ldstr    aLengthOfParame_102// "Length of parameter Title exceeds speci"...
0x15dac7  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15dacc  throw
0x15dacd  ldarg.s  0xA
0x15dacf  brfalse.s loc_15DAEA
0x15dad1  ldarg.s  0xA
0x15dad3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15dad8  ldc.i4   0x190
0x15dadd  ble.s    loc_15DAEA
0x15dadf  ldstr    aLengthOfParame_356// "Length of parameter TemplateDirName exc"...
0x15dae4  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15dae9  throw
0x15daea  ldarg.s  0xB
0x15daec  brfalse.s loc_15DB07
0x15daee  ldarg.s  0xB
0x15daf0  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15daf5  ldc.i4   0x190
0x15dafa  ble.s    loc_15DB07
0x15dafc  ldstr    aLengthOfParame_357// "Length of parameter TemplateLeafName ex"...
0x15db01  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15db06  throw
0x15db07  ldarg.s  0xE
0x15db09  brfalse.s loc_15DB24
0x15db0b  ldarg.s  0xE
0x15db0d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15db12  ldc.i4   0xFF
0x15db17  ble.s    loc_15DB24
0x15db19  ldstr    aLengthOfParame_155// "Length of parameter EventSinkAssembly e"...
0x15db1e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15db23  throw
0x15db24  ldarg.s  0xF
0x15db26  brfalse.s loc_15DB41
0x15db28  ldarg.s  0xF
0x15db2a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15db2f  ldc.i4   0xFF
0x15db34  ble.s    loc_15DB41
0x15db36  ldstr    aLengthOfParame_156// "Length of parameter EventSinkClass exce"...
0x15db3b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15db40  throw
0x15db41  ldarg.s  0x10
0x15db43  brfalse.s loc_15DB5E
0x15db45  ldarg.s  0x10
0x15db47  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15db4c  ldc.i4   0xFF
0x15db51  ble.s    loc_15DB5E
0x15db53  ldstr    aLengthOfParame_157// "Length of parameter EventSinkData excee"...
0x15db58  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15db5d  throw
0x15db5e  ldarg.s  0x12
0x15db60  brfalse.s loc_15DB7B
0x15db62  ldarg.s  0x12
0x15db64  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15db69  ldc.i4   0xFF
0x15db6e  ble.s    loc_15DB7B
0x15db70  ldstr    aLengthOfParame_153// "Length of parameter ImageUrl exceeds sp"...
0x15db75  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15db7a  throw
0x15db7b  ldarg.s  0x18
0x15db7d  brfalse.s loc_15DB98
0x15db7f  ldarg.s  0x18
0x15db81  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15db86  ldc.i4   0x80
0x15db8b  ble.s    loc_15DB98
0x15db8d  ldstr    aLengthOfParame_358// "Length of parameter EmailAlias exceeds "...
0x15db92  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15db97  throw
0x15db98  ldarg.s  0x19
0x15db9a  brfalse.s loc_15DBB5
0x15db9c  ldarg.s  0x19
0x15db9e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15dba3  ldc.i4   0x200
0x15dba8  ble.s    loc_15DBB5
0x15dbaa  ldstr    aLengthOfParame_154// "Length of parameter SendToLocation exce"...
0x15dbaf  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15dbb4  throw
0x15dbb5  ldarg.s  0x22
0x15dbb7  brfalse.s loc_15DBD2
0x15dbb9  ldarg.s  0x22
0x15dbbb  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15dbc0  ldc.i4   0x400
0x15dbc5  ble.s    loc_15DBD2
0x15dbc7  ldstr    aLengthOfParame_160// "Length of parameter ValidationFormula e"...
0x15dbcc  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15dbd1  throw
0x15dbd2  ldarg.s  0x23
0x15dbd4  brfalse.s loc_15DBEF
0x15dbd6  ldarg.s  0x23
0x15dbd8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15dbdd  ldc.i4   0x400
0x15dbe2  ble.s    loc_15DBEF
0x15dbe4  ldstr    aLengthOfParame_161// "Length of parameter ValidationMessage e"...
0x15dbe9  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x15dbee  throw
0x15dbef  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlCommand::.ctor()
0x15dbf4  stloc.0
0x15dbf5  ldloc.0
0x15dbf6  ldstr    aDboProcUpdatel_9// "dbo.proc_UpdateListSettings"
0x15dbfb  callvirt instance void Microsoft.SharePoint.Utilities.SPSqlCommand::SetStoredProcedure(string strProc)
0x15dc00  ldarga.s 0
0x15dc02  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x15dc07  brtrue.s loc_15DC27
0x15dc09  ldloc.0
0x15dc0a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15dc0f  ldstr    aSiteid_1// "@SiteId"
0x15dc14  ldc.i4.s 0xE
0x15dc16  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15dc1b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15dc20  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15dc25  br.s     loc_15DC4A
0x15dc27  ldloc.0
0x15dc28  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15dc2d  ldstr    aSiteid_1// "@SiteId"
0x15dc32  ldc.i4.s 0xE
0x15dc34  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15dc39  ldarga.s 0
0x15dc3b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x15dc40  box      [mscorlib]System.Guid
0x15dc45  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15dc4a  ldarga.s 1
0x15dc4c  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x15dc51  brtrue.s loc_15DC71
0x15dc53  ldloc.0
0x15dc54  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15dc59  ldstr    aWebid_0// "@WebId"
0x15dc5e  ldc.i4.s 0xE
0x15dc60  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15dc65  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15dc6a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15dc6f  br.s     loc_15DC94
0x15dc71  ldloc.0
0x15dc72  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15dc77  ldstr    aWebid_0// "@WebId"
0x15dc7c  ldc.i4.s 0xE
0x15dc7e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15dc83  ldarga.s 1
0x15dc85  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x15dc8a  box      [mscorlib]System.Guid
0x15dc8f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15dc94  ldarga.s 2
0x15dc96  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x15dc9b  brtrue.s loc_15DCBB
0x15dc9d  ldloc.0
0x15dc9e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15dca3  ldstr    aListid_0// "@ListId"
0x15dca8  ldc.i4.s 0xE
0x15dcaa  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15dcaf  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15dcb4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15dcb9  br.s     loc_15DCDE
0x15dcbb  ldloc.0
0x15dcbc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15dcc1  ldstr    aListid_0// "@ListId"
0x15dcc6  ldc.i4.s 0xE
0x15dcc8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15dccd  ldarga.s 2
0x15dccf  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x15dcd4  box      [mscorlib]System.Guid
0x15dcd9  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15dcde  ldarga.s 3
0x15dce0  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x15dce5  brtrue.s loc_15DD04
0x15dce7  ldloc.0
0x15dce8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15dced  ldstr    aBasetype// "@BaseType"
0x15dcf2  ldc.i4.8
0x15dcf3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15dcf8  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15dcfd  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15dd02  br.s     loc_15DD26
0x15dd04  ldloc.0
0x15dd05  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15dd0a  ldstr    aBasetype// "@BaseType"
0x15dd0f  ldc.i4.8
0x15dd10  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15dd15  ldarga.s 3
0x15dd17  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x15dd1c  box      [mscorlib]System.Int32
0x15dd21  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15dd26  ldarga.s 4
0x15dd28  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x15dd2d  brtrue.s loc_15DD4C
0x15dd2f  ldloc.0
0x15dd30  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15dd35  ldstr    aServertemplate// "@ServerTemplate"
0x15dd3a  ldc.i4.8
0x15dd3b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15dd40  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15dd45  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15dd4a  br.s     loc_15DD6E
0x15dd4c  ldloc.0
0x15dd4d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15dd52  ldstr    aServertemplate// "@ServerTemplate"
0x15dd57  ldc.i4.8
0x15dd58  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15dd5d  ldarga.s 4
0x15dd5f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x15dd64  box      [mscorlib]System.Int32
0x15dd69  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15dd6e  ldarg.s  5
0x15dd70  brtrue.s loc_15DD90
0x15dd72  ldloc.0
0x15dd73  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15dd78  ldstr    aTitle// "@Title"
0x15dd7d  ldc.i4.s 0xC
0x15dd7f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15dd84  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15dd89  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15dd8e  br.s     loc_15DDA9
0x15dd90  ldloc.0
0x15dd91  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15dd96  ldstr    aTitle// "@Title"
0x15dd9b  ldc.i4.s 0xC
0x15dd9d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15dda2  ldarg.s  5
0x15dda4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15dda9  ldarga.s 6
0x15ddab  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x15ddb0  brtrue.s loc_15DDCF
0x15ddb2  ldloc.0
0x15ddb3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15ddb8  ldstr    aReadsecurity// "@ReadSecurity"
0x15ddbd  ldc.i4.8
0x15ddbe  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15ddc3  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15ddc8  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15ddcd  br.s     loc_15DDF1
0x15ddcf  ldloc.0
0x15ddd0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15ddd5  ldstr    aReadsecurity// "@ReadSecurity"
0x15ddda  ldc.i4.8
0x15dddb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15dde0  ldarga.s 6
0x15dde2  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x15dde7  box      [mscorlib]System.Int32
0x15ddec  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15ddf1  ldarga.s 7
0x15ddf3  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x15ddf8  brtrue.s loc_15DE17
0x15ddfa  ldloc.0
0x15ddfb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15de00  ldstr    aWritesecurity// "@WriteSecurity"
0x15de05  ldc.i4.8
0x15de06  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15de0b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15de10  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15de15  br.s     loc_15DE39
0x15de17  ldloc.0
0x15de18  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15de1d  ldstr    aWritesecurity// "@WriteSecurity"
0x15de22  ldc.i4.8
0x15de23  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15de28  ldarga.s 7
0x15de2a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x15de2f  box      [mscorlib]System.Int32
0x15de34  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15de39  ldarga.s 8
0x15de3b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x15de40  brtrue.s loc_15DE60
0x15de42  ldloc.0
0x15de43  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15de48  ldstr    aNewdefaultview// "@NewDefaultView"
0x15de4d  ldc.i4.s 0xE
0x15de4f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15de54  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15de59  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15de5e  br.s     loc_15DE83
0x15de60  ldloc.0
0x15de61  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15de66  ldstr    aNewdefaultview// "@NewDefaultView"
0x15de6b  ldc.i4.s 0xE
0x15de6d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15de72  ldarga.s 8
0x15de74  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x15de79  box      [mscorlib]System.Guid
0x15de7e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15de83  ldarg.s  9
0x15de85  brtrue.s loc_15DEA5
0x15de87  ldloc.0
0x15de88  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15de8d  ldstr    aDescription_0// "@Description"
0x15de92  ldc.i4.s 0xC
0x15de94  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15de99  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15de9e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15dea3  br.s     loc_15DEBE
0x15dea5  ldloc.0
0x15dea6  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15deab  ldstr    aDescription_0// "@Description"
0x15deb0  ldc.i4.s 0xC
0x15deb2  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15deb7  ldarg.s  9
0x15deb9  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15debe  ldarg.s  0xA
0x15dec0  brtrue.s loc_15DEE0
  ... truncated ...
```
