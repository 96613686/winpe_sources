# System.Web.Caching.SqlCacheDependencyAdmin::SetupNotifications

- ea: `0x18ac50`
- end: `0x18af87`
- name: `System.Web.Caching.SqlCacheDependencyAdmin::SetupNotifications`
- size: `823`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x18af90`
- `0x18afa0`
- `0x18afb0`
- `0x18afc0`
- `0x18aff0`
- `0x18b000`

## callees

- `0x18990`
- `0x189c0`
- `0x24630`
- `0x34f20`
- `0x34fa0`
- `0x18a0c0`
- `0x18ab50`
- `0x18ac50`

## string_xrefs

- `0x18acb6`: `Cache_null_table`
- `0x18ac75`: `Cache_null_table_in_tables`
- `0x18aca1`: `Cache_null_table_in_tables`
- `0x18ace8`: `dbo.AspNet_SqlCacheUnRegisterTableStoredProcedure`
- `0x18acef`: `dbo.AspNet_SqlCacheRegisterTableStoredProcedure`
- `0x18ad3e`: `/* Create notification table */ \nIF NOT EXISTS (SELECT name FROM sysobjects WITH (NOLOCK) WHERE name = '{0}' AND type = 'U') \n   IF NOT EXISTS (SELECT name FROM sysobjects WITH (TABLOCKX) WHERE name = '{0}' AND type = 'U') \n      CREATE TABLE dbo.{0} (\n      tableName             NVARCHAR(450) NOT NULL PRIMARY KEY,\n      notificationCreated   DATETIME NOT NULL DEFAULT(GETDATE()),\n      changeId              INT NOT NULL DEFAULT(0)\n      )\n\n/* Create polling SP */\nIF NOT EXISTS (SELECT `
- `0x18ad4b`: `AspNet_SqlCacheTablesForChangeNotification`
- `0x18ada7`: `AspNet_SqlCacheTablesForChangeNotification`
- `0x18ad53`: `AspNet_SqlCachePollingStoredProcedure`
- `0x18adaf`: `AspNet_SqlCachePollingStoredProcedure`
- `0x18ad5b`: `AspNet_SqlCacheRegisterTableStoredProcedure`
- `0x18adb7`: `AspNet_SqlCacheRegisterTableStoredProcedure`
- `0x18ad63`: `_AspNet_SqlCacheNotification_Trigger`
- `0x18ad6b`: `AspNet_SqlCacheUnRegisterTableStoredProcedure`
- `0x18adbf`: `AspNet_SqlCacheUnRegisterTableStoredProcedure`
- `0x18ad73`: `AspNet_SqlCacheQueryRegisteredTablesStoredProcedure`
- `0x18adc7`: `AspNet_SqlCacheQueryRegisteredTablesStoredProcedure`
- `0x18ad7b`: `AspNet_SqlCacheUpdateChangeIdStoredProcedure`
- `0x18adcf`: `AspNet_SqlCacheUpdateChangeIdStoredProcedure`
- `0x18ad9a`: `/* Remove notification table */ \nIF EXISTS (SELECT name FROM sysobjects WITH (NOLOCK) WHERE name = '{0}' AND type = 'U') \n    IF EXISTS (SELECT name FROM sysobjects WITH (TABLOCKX) WHERE name = '{0}' AND type = 'U') \n    BEGIN\n      /* First, unregister all registered tables */ \n      DECLARE tables_cursor CURSOR FOR \n      SELECT tableName FROM dbo.{0} \n      DECLARE @tableName AS NVARCHAR(450) \n\n      OPEN tables_cursor \n\n      /* Perform the first fetch. */ \n      FETCH NEXT FROM `
- `0x18ae56`: `Cant_disable_table_sql_cache_dep`
- `0x18af19`: `Cache_dep_table_not_found`
- `0x18af43`: `Cant_connect_sql_cache_dep_database_admin_cmdtxt`
- `0x18af60`: `Cant_connect_sql_cache_dep_database_admin`

## pseudocode

```c

```

## disassembly

```asm
0x18ac50  ldnull
0x18ac51  stloc.0
0x18ac52  ldnull
0x18ac53  stloc.1
0x18ac54  ldarg.0
0x18ac55  ldc.i4.s 9
0x18ac57  and
0x18ac58  ldc.i4.0
0x18ac59  cgt.un
0x18ac5b  stloc.2
0x18ac5c  ldarg.0
0x18ac5d  ldc.i4.2
0x18ac5e  and
0x18ac5f  ldc.i4.0
0x18ac60  cgt.un
0x18ac62  stloc.3
0x18ac63  ldloc.2
0x18ac64  brfalse.s loc_18ACCB
0x18ac66  ldarg.0
0x18ac67  ldc.i4.8
0x18ac68  and
0x18ac69  ldc.i4.0
0x18ac6a  cgt.un
0x18ac6c  stloc.s  4
0x18ac6e  ldarg.1
0x18ac6f  brtrue.s loc_18AC95
0x18ac71  ldloc.s  4
0x18ac73  brfalse.s loc_18AC8A
0x18ac75  ldstr    aCacheNullTable_0// "Cache_null_table_in_tables"
0x18ac7a  call     string System.Web.SR::GetString(string name)
0x18ac7f  ldstr    aTables// "tables"
0x18ac84  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x18ac89  throw
0x18ac8a  ldstr    aTable_0// "table"
0x18ac8f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x18ac94  throw
0x18ac95  ldarg.1
0x18ac96  callvirt instance int32 [mscorlib]System.String::get_Length()
0x18ac9b  brtrue.s loc_18ACCB
0x18ac9d  ldloc.s  4
0x18ac9f  brfalse.s loc_18ACB6
0x18aca1  ldstr    aCacheNullTable_0// "Cache_null_table_in_tables"
0x18aca6  call     string System.Web.SR::GetString(string name)
0x18acab  ldstr    aTables// "tables"
0x18acb0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x18acb5  throw
0x18acb6  ldstr    aCacheNullTable// "Cache_null_table"
0x18acbb  call     string System.Web.SR::GetString(string name)
0x18acc0  ldstr    aTable_0// "table"
0x18acc5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x18acca  throw
0x18accb  nop
0x18accc  ldarg.2
0x18accd  newobj   instance void [System.Data]System.Data.SqlClient.SqlConnection::.ctor(string)
0x18acd2  stloc.0
0x18acd3  ldloc.0
0x18acd4  callvirt instance void [System.Data]System.Data.Common.DbConnection::Open()
0x18acd9  ldnull
0x18acda  ldloc.0
0x18acdb  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x18ace0  stloc.1
0x18ace1  ldloc.2
0x18ace2  brfalse.s loc_18AD35
0x18ace4  ldloc.1
0x18ace5  ldloc.3
0x18ace6  brfalse.s loc_18ACEF
0x18ace8  ldstr    aDboAspnetSqlca_0// "dbo.AspNet_SqlCacheUnRegisterTableStore"...
0x18aced  br.s     loc_18ACF4
0x18acef  ldstr    aDboAspnetSqlca_1// "dbo.AspNet_SqlCacheRegisterTableStoredP"...
0x18acf4  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x18acf9  ldloc.1
0x18acfa  ldc.i4.4
0x18acfb  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x18ad00  ldloc.1
0x18ad01  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18ad06  ldstr    aTablename_0// "@tableName"
0x18ad0b  ldc.i4.s 0xC
0x18ad0d  ldarg.1
0x18ad0e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x18ad13  newobj   instance void [System.Data]System.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x18ad18  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(class [System.Data]System.Data.SqlClient.SqlParameter)
0x18ad1d  pop
0x18ad1e  ldloc.1
0x18ad1f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x18ad24  ldc.i4.0
0x18ad25  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::get_Item(int32)
0x18ad2a  ldarg.1
0x18ad2b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x18ad30  br       loc_18ADE6
0x18ad35  ldloc.3
0x18ad36  brtrue.s loc_18AD94
0x18ad38  ldloc.1
0x18ad39  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18ad3e  ldstr    aCreateNotifica// "/* Create notification table */ \nIF NO"...
0x18ad43  ldc.i4.7
0x18ad44  newarr   [mscorlib]System.Object
0x18ad49  dup
0x18ad4a  ldc.i4.0
0x18ad4b  ldstr    aAspnetSqlcache// "AspNet_SqlCacheTablesForChangeNotificat"...
0x18ad50  stelem.ref
0x18ad51  dup
0x18ad52  ldc.i4.1
0x18ad53  ldstr    aAspnetSqlcache_0// "AspNet_SqlCachePollingStoredProcedure"
0x18ad58  stelem.ref
0x18ad59  dup
0x18ad5a  ldc.i4.2
0x18ad5b  ldstr    aAspnetSqlcache_1// "AspNet_SqlCacheRegisterTableStoredProce"...
0x18ad60  stelem.ref
0x18ad61  dup
0x18ad62  ldc.i4.3
0x18ad63  ldstr    aAspnetSqlcache_2// "_AspNet_SqlCacheNotification_Trigger"
0x18ad68  stelem.ref
0x18ad69  dup
0x18ad6a  ldc.i4.4
0x18ad6b  ldstr    aAspnetSqlcache_3// "AspNet_SqlCacheUnRegisterTableStoredPro"...
0x18ad70  stelem.ref
0x18ad71  dup
0x18ad72  ldc.i4.5
0x18ad73  ldstr    aAspnetSqlcache_4// "AspNet_SqlCacheQueryRegisteredTablesSto"...
0x18ad78  stelem.ref
0x18ad79  dup
0x18ad7a  ldc.i4.6
0x18ad7b  ldstr    aAspnetSqlcache_5// "AspNet_SqlCacheUpdateChangeIdStoredProc"...
0x18ad80  stelem.ref
0x18ad81  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18ad86  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x18ad8b  ldloc.1
0x18ad8c  ldc.i4.1
0x18ad8d  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x18ad92  br.s     loc_18ADE6
0x18ad94  ldloc.1
0x18ad95  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18ad9a  ldstr    aRemoveNotifica// "/* Remove notification table */ \nIF EX"...
0x18ad9f  ldc.i4.6
0x18ada0  newarr   [mscorlib]System.Object
0x18ada5  dup
0x18ada6  ldc.i4.0
0x18ada7  ldstr    aAspnetSqlcache// "AspNet_SqlCacheTablesForChangeNotificat"...
0x18adac  stelem.ref
0x18adad  dup
0x18adae  ldc.i4.1
0x18adaf  ldstr    aAspnetSqlcache_0// "AspNet_SqlCachePollingStoredProcedure"
0x18adb4  stelem.ref
0x18adb5  dup
0x18adb6  ldc.i4.2
0x18adb7  ldstr    aAspnetSqlcache_1// "AspNet_SqlCacheRegisterTableStoredProce"...
0x18adbc  stelem.ref
0x18adbd  dup
0x18adbe  ldc.i4.3
0x18adbf  ldstr    aAspnetSqlcache_3// "AspNet_SqlCacheUnRegisterTableStoredPro"...
0x18adc4  stelem.ref
0x18adc5  dup
0x18adc6  ldc.i4.4
0x18adc7  ldstr    aAspnetSqlcache_4// "AspNet_SqlCacheQueryRegisteredTablesSto"...
0x18adcc  stelem.ref
0x18adcd  dup
0x18adce  ldc.i4.5
0x18adcf  ldstr    aAspnetSqlcache_5// "AspNet_SqlCacheUpdateChangeIdStoredProc"...
0x18add4  stelem.ref
0x18add5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x18adda  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x18addf  ldloc.1
0x18ade0  ldc.i4.1
0x18ade1  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x18ade6  ldloc.1
0x18ade7  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x18adec  pop
0x18aded  ldloc.1
0x18adee  ldsfld   string [mscorlib]System.String::Empty
0x18adf3  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x18adf8  call     bool System.Web.HttpRuntime::get_IsAspNetAppDomain()
0x18adfd  brfalse.s loc_18AE04
0x18adff  call     void System.Web.Caching.SqlCacheDependencyManager::UpdateAllDatabaseNotifState()
0x18ae04  leave    loc_18AF86
0x18ae09  stloc.s  5
0x18ae0b  ldloc.s  5
0x18ae0d  isinst   [System.Data]System.Data.SqlClient.SqlException
0x18ae12  stloc.s  6
0x18ae14  ldc.i4.1
0x18ae15  stloc.s  7
0x18ae17  ldloc.s  6
0x18ae19  brfalse  loc_18AF33
0x18ae1e  ldloc.s  6
0x18ae20  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x18ae25  ldc.i4   0xAFC
0x18ae2a  bne.un.s loc_18AE6E
0x18ae2c  ldloc.3
0x18ae2d  brtrue.s loc_18AE53
0x18ae2f  ldarg.1
0x18ae30  brfalse.s loc_18AE51
0x18ae32  ldstr    aDatabaseNotEna// "Database_not_enabled_for_notification"
0x18ae37  ldc.i4.1
0x18ae38  newarr   [mscorlib]System.Object
0x18ae3d  dup
0x18ae3e  ldc.i4.0
0x18ae3f  ldloc.0
0x18ae40  callvirt instance string [System.Data]System.Data.Common.DbConnection::get_Database()
0x18ae45  stelem.ref
0x18ae46  call     string System.Web.SR::GetString(string name, object[] args)
0x18ae4b  newobj   instance void System.Web.Caching.DatabaseNotEnabledForNotificationException::.ctor(string message)
0x18ae50  throw
0x18ae51  rethrow
0x18ae53  ldarg.1
0x18ae54  brfalse.s loc_18AE66
0x18ae56  ldstr    aCantDisableTab// "Cant_disable_table_sql_cache_dep"
0x18ae5b  call     string System.Web.SR::GetString(string name)
0x18ae60  newobj   instance void System.Web.Caching.DatabaseNotEnabledForNotificationException::.ctor(string message)
0x18ae65  throw
0x18ae66  ldc.i4.0
0x18ae67  stloc.s  7
0x18ae69  br       loc_18AF33
0x18ae6e  ldloc.s  6
0x18ae70  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x18ae75  ldc.i4   0xE5
0x18ae7a  beq.s    loc_18AEA6
0x18ae7c  ldloc.s  6
0x18ae7e  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x18ae83  ldc.i4   0x106
0x18ae88  beq.s    loc_18AEA6
0x18ae8a  ldloc.s  6
0x18ae8c  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x18ae91  ldc.i4   0xAC8
0x18ae96  beq.s    loc_18AEA6
0x18ae98  ldloc.s  6
0x18ae9a  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x18ae9f  ldc.i4   0x1205
0x18aea4  bne.un.s loc_18AEF8
0x18aea6  ldloc.3
0x18aea7  brtrue.s loc_18AEBE
0x18aea9  ldarg.1
0x18aeaa  brfalse.s loc_18AEB5
0x18aeac  ldstr    aPermissionDeni_0// "Permission_denied_table_enable_notifica"...
0x18aeb1  stloc.s  9
0x18aeb3  br.s     loc_18AED1
0x18aeb5  ldstr    aPermissionDeni_1// "Permission_denied_database_enable_notif"...
0x18aeba  stloc.s  9
0x18aebc  br.s     loc_18AED1
0x18aebe  ldarg.1
0x18aebf  brfalse.s loc_18AECA
0x18aec1  ldstr    aPermissionDeni_2// "Permission_denied_table_disable_notific"...
0x18aec6  stloc.s  9
0x18aec8  br.s     loc_18AED1
0x18aeca  ldstr    aPermissionDeni_3// "Permission_denied_database_disable_noti"...
0x18aecf  stloc.s  9
0x18aed1  ldarg.1
0x18aed2  brfalse.s loc_18AEEB
0x18aed4  ldloc.s  9
0x18aed6  ldc.i4.1
0x18aed7  newarr   [mscorlib]System.Object
0x18aedc  dup
0x18aedd  ldc.i4.0
0x18aede  ldarg.1
0x18aedf  stelem.ref
0x18aee0  call     string System.Web.SR::GetString(string name, object[] args)
0x18aee5  newobj   instance void System.Web.HttpException::.ctor(string message)
0x18aeea  throw
0x18aeeb  ldloc.s  9
0x18aeed  call     string System.Web.SR::GetString(string name)
0x18aef2  newobj   instance void System.Web.HttpException::.ctor(string message)
0x18aef7  throw
0x18aef8  ldloc.s  6
0x18aefa  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x18aeff  ldc.i4   0xC350
0x18af04  bne.un.s loc_18AF33
0x18af06  ldloc.s  6
0x18af08  callvirt instance string [mscorlib]System.Exception::get_Message()
0x18af0d  ldstr    a00000001// "00000001"
0x18af12  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18af17  brfalse.s loc_18AF33
0x18af19  ldstr    aCacheDepTableN// "Cache_dep_table_not_found"
0x18af1e  ldc.i4.1
0x18af1f  newarr   [mscorlib]System.Object
0x18af24  dup
0x18af25  ldc.i4.0
0x18af26  ldarg.1
0x18af27  stelem.ref
0x18af28  call     string System.Web.SR::GetString(string name, object[] args)
0x18af2d  newobj   instance void System.Web.HttpException::.ctor(string message)
0x18af32  throw
0x18af33  ldloc.1
0x18af34  brfalse.s loc_18AF60
0x18af36  ldloc.1
0x18af37  callvirt instance string [System.Data]System.Data.Common.DbCommand::get_CommandText()
0x18af3c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x18af41  brfalse.s loc_18AF60
0x18af43  ldstr    aCantConnectSql_2// "Cant_connect_sql_cache_dep_database_adm"...
0x18af48  ldc.i4.1
0x18af49  newarr   [mscorlib]System.Object
0x18af4e  dup
0x18af4f  ldc.i4.0
0x18af50  ldloc.1
0x18af51  callvirt instance string [System.Data]System.Data.Common.DbCommand::get_CommandText()
0x18af56  stelem.ref
0x18af57  call     string System.Web.SR::GetString(string name, object[] args)
0x18af5c  stloc.s  8
0x18af5e  br.s     loc_18AF6C
0x18af60  ldstr    aCantConnectSql_3// "Cant_connect_sql_cache_dep_database_adm"...
0x18af65  call     string System.Web.SR::GetString(string name)
0x18af6a  stloc.s  8
0x18af6c  ldloc.s  7
  ... truncated ...
```
