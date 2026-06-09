# System.Web.Caching.SqlCacheDependencyManager::EnsureTableIsRegisteredAndPolled

- ea: `0x18a940`
- end: `0x18ab1b`
- name: `System.Web.Caching.SqlCacheDependencyManager::EnsureTableIsRegisteredAndPolled`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x189eb0`

## callees

- `0xbdc0`
- `0x15e20`
- `0x16e20`
- `0x18990`
- `0x189c0`
- `0x18a60`
- `0x243e0`
- `0x34f20`
- `0x186590`
- `0x1868f0`
- `0x18a0c0`
- `0x18a110`
- `0x18a2a0`
- `0x18a400`
- `0x18a940`
- `0x18ab20`

## string_xrefs

- `0x18a9e3`: `Cant_connect_sql_cache_dep_database_polling`
- `0x18aaad`: `Cant_connect_sql_cache_dep_database_polling`

## pseudocode

```c

```

## disassembly

```asm
0x18a940  ldc.i4.0
0x18a941  stloc.0
0x18a942  call     class System.Web.Caching.Cache System.Web.HttpRuntime::get_Cache()
0x18a947  callvirt instance class System.Web.Caching.CacheStoreProvider System.Web.Caching.Cache::get_InternalCache()
0x18a94c  ldarg.0
0x18a94d  ldarg.1
0x18a94e  call     string System.Web.Caching.SqlCacheDependencyManager::GetMoniterKey(string database, string table)
0x18a953  callvirt instance object System.Web.Caching.CacheStoreProvider::Get(string key)
0x18a958  brfalse.s loc_18A95B
0x18a95a  ret
0x18a95b  ldarg.0
0x18a95c  call     void System.Web.Caching.SqlCacheDependencyManager::InitPolling(string database)
0x18a961  ldsfld   class [mscorlib]System.Collections.Hashtable System.Web.Caching.SqlCacheDependencyManager::s_DatabaseNotifStates
0x18a966  ldarg.0
0x18a967  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x18a96c  castclass System.Web.Caching.DatabaseNotifState
0x18a971  stloc.1
0x18a972  ldloc.1
0x18a973  ldfld    bool System.Web.Caching.DatabaseNotifState::_init
0x18a978  brtrue   loc_18A9FD
0x18a97d  call     class System.Web.HttpContext System.Web.HttpContext::get_Current()
0x18a982  stloc.3
0x18a983  ldloc.3
0x18a984  brtrue.s loc_18A98B
0x18a986  ldc.i4.s 0x1E
0x18a988  stloc.2
0x18a989  br.s     loc_18A9A4
0x18a98b  ldloc.3
0x18a98c  callvirt instance valuetype [mscorlib]System.TimeSpan System.Web.HttpContext::get_Timeout()
0x18a991  stloc.s  5
0x18a993  ldloca.s 5
0x18a995  call     instance int32 [mscorlib]System.TimeSpan::get_Seconds()
0x18a99a  ldc.i4.3
0x18a99b  div
0x18a99c  ldc.i4.s 0x1E
0x18a99e  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x18a9a3  stloc.2
0x18a9a4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x18a9a9  stloc.s  6
0x18a9ab  ldloca.s 6
0x18a9ad  ldc.i4.0
0x18a9ae  ldc.i4.0
0x18a9af  ldloc.2
0x18a9b0  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x18a9b5  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Add(valuetype [mscorlib]System.TimeSpan)
0x18a9ba  stloc.s  4
0x18a9bc  ldloc.1
0x18a9bd  ldfld    bool System.Web.Caching.DatabaseNotifState::_init
0x18a9c2  brtrue.s loc_18A9FD
0x18a9c4  ldc.i4   0xFA
0x18a9c9  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x18a9ce  call     bool [mscorlib]System.Diagnostics.Debugger::get_IsAttached()
0x18a9d3  brtrue.s loc_18A9BC
0x18a9d5  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x18a9da  ldloc.s  4
0x18a9dc  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x18a9e1  brfalse.s loc_18A9BC
0x18a9e3  ldstr    aCantConnectSql_1// "Cant_connect_sql_cache_dep_database_pol"...
0x18a9e8  ldc.i4.1
0x18a9e9  newarr   [mscorlib]System.Object
0x18a9ee  dup
0x18a9ef  ldc.i4.0
0x18a9f0  ldarg.0
0x18a9f1  stelem.ref
0x18a9f2  call     string System.Web.SR::GetString(string name, object[] args)
0x18a9f7  newobj   instance void System.Web.HttpException::.ctor(string message)
0x18a9fc  throw
0x18a9fd  ldc.i4.0
0x18a9fe  stloc.s  0xA
0x18aa00  ldloc.1
0x18aa01  stloc.s  0xB
0x18aa03  ldc.i4.0
0x18aa04  stloc.s  0xC
0x18aa06  ldloc.s  0xB
0x18aa08  ldloca.s 0xC
0x18aa0a  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x18aa0f  ldloc.1
0x18aa10  ldfld    class [mscorlib]System.Exception System.Web.Caching.DatabaseNotifState::_pollExpt
0x18aa15  stloc.s  9
0x18aa17  ldloc.s  9
0x18aa19  brfalse.s loc_18AA23
0x18aa1b  ldloc.1
0x18aa1c  ldfld    int32 System.Web.Caching.DatabaseNotifState::_pollSqlError
0x18aa21  stloc.s  0xA
0x18aa23  ldloc.1
0x18aa24  ldfld    valuetype [mscorlib]System.DateTime System.Web.Caching.DatabaseNotifState::_utcTablesUpdated
0x18aa29  stloc.s  7
0x18aa2b  ldloc.1
0x18aa2c  ldfld    bool System.Web.Caching.DatabaseNotifState::_notifEnabled
0x18aa31  stloc.s  8
0x18aa33  leave.s  loc_18AA41
0x18aa35  ldloc.s  0xC
0x18aa37  brfalse.s loc_18AA40
0x18aa39  ldloc.s  0xB
0x18aa3b  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x18aa40  endfinally
0x18aa41  ldloc.s  9
0x18aa43  ldnull
0x18aa44  ceq
0x18aa46  ldloc.s  8
0x18aa48  and
0x18aa49  brfalse.s loc_18AA5A
0x18aa4b  ldloc.1
0x18aa4c  ldfld    class [mscorlib]System.Collections.Hashtable System.Web.Caching.DatabaseNotifState::_tables
0x18aa51  ldarg.1
0x18aa52  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x18aa57  brfalse.s loc_18AA5A
0x18aa59  ret
0x18aa5a  ldloc.0
0x18aa5b  brtrue.s loc_18AA82
0x18aa5d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x18aa62  ldloc.s  7
0x18aa64  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x18aa69  ldsfld   valuetype [mscorlib]System.TimeSpan System.Web.Caching.SqlCacheDependencyManager::OneSec
0x18aa6e  call     bool [mscorlib]System.TimeSpan::op_GreaterThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x18aa73  brfalse.s loc_18AA82
0x18aa75  ldarg.0
0x18aa76  call     void System.Web.Caching.SqlCacheDependencyManager::UpdateDatabaseNotifState(string database)
0x18aa7b  ldc.i4.1
0x18aa7c  stloc.0
0x18aa7d  br       loc_18A9FD
0x18aa82  ldloc.s  0xA
0x18aa84  ldc.i4   0xAFC
0x18aa89  bne.un.s loc_18AA8E
0x18aa8b  ldnull
0x18aa8c  stloc.s  9
0x18aa8e  ldloc.s  9
0x18aa90  brfalse.s loc_18AADF
0x18aa92  ldloc.s  0xA
0x18aa94  ldc.i4   0xE5
0x18aa99  beq.s    loc_18AAA4
0x18aa9b  ldloc.s  0xA
0x18aa9d  ldc.i4   0x106
0x18aaa2  bne.un.s loc_18AAAD
0x18aaa4  ldstr    aPermissionDeni// "Permission_denied_database_polling"
0x18aaa9  stloc.s  0xD
0x18aaab  br.s     loc_18AAB4
0x18aaad  ldstr    aCantConnectSql_1// "Cant_connect_sql_cache_dep_database_pol"...
0x18aab2  stloc.s  0xD
0x18aab4  ldloc.s  0xD
0x18aab6  ldc.i4.1
0x18aab7  newarr   [mscorlib]System.Object
0x18aabc  dup
0x18aabd  ldc.i4.0
0x18aabe  ldarg.0
0x18aabf  stelem.ref
0x18aac0  call     string System.Web.SR::GetString(string name, object[] args)
0x18aac5  ldloc.s  9
0x18aac7  newobj   instance void System.Web.HttpException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x18aacc  stloc.s  0xE
0x18aace  ldloc.s  0xE
0x18aad0  ldloc.s  0xE
0x18aad2  newobj   instance void System.Web.UseLastUnhandledErrorFormatter::.ctor(class [mscorlib]System.Exception e)
0x18aad7  callvirt instance void System.Web.HttpException::SetFormatter(class System.Web.ErrorFormatter errorFormatter)
0x18aadc  ldloc.s  0xE
0x18aade  throw
0x18aadf  ldloc.s  8
0x18aae1  brtrue.s loc_18AAFD
0x18aae3  ldstr    aDatabaseNotEna// "Database_not_enabled_for_notification"
0x18aae8  ldc.i4.1
0x18aae9  newarr   [mscorlib]System.Object
0x18aaee  dup
0x18aaef  ldc.i4.0
0x18aaf0  ldarg.0
0x18aaf1  stelem.ref
0x18aaf2  call     string System.Web.SR::GetString(string name, object[] args)
0x18aaf7  newobj   instance void System.Web.Caching.DatabaseNotEnabledForNotificationException::.ctor(string message)
0x18aafc  throw
0x18aafd  ldstr    aTableNotEnable// "Table_not_enabled_for_notification"
0x18ab02  ldc.i4.2
0x18ab03  newarr   [mscorlib]System.Object
0x18ab08  dup
0x18ab09  ldc.i4.0
0x18ab0a  ldarg.1
0x18ab0b  stelem.ref
0x18ab0c  dup
0x18ab0d  ldc.i4.1
0x18ab0e  ldarg.0
0x18ab0f  stelem.ref
0x18ab10  call     string System.Web.SR::GetString(string name, object[] args)
0x18ab15  newobj   instance void System.Web.Caching.TableNotEnabledForNotificationException::.ctor(string message)
0x18ab1a  throw
```
