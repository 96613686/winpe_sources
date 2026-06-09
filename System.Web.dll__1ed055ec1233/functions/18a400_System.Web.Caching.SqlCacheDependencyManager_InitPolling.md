# System.Web.Caching.SqlCacheDependencyManager::InitPolling

- ea: `0x18a400`
- end: `0x18a593`
- name: `System.Web.Caching.SqlCacheDependencyManager::InitPolling`
- size: `403`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18a940`
- `0x18ab20`

## callees

- `0x34f20`
- `0x34fa0`
- `0x4c5e0`
- `0x156580`
- `0x156b40`
- `0x158020`
- `0x158050`
- `0x158390`
- `0x18a190`
- `0x18a3c0`
- `0x18a400`

## string_xrefs

- `0x18a413`: `Polling_not_enabled_for_sql_cache`
- `0x18a466`: `Polltime_zero_for_database_sql_cache`

## pseudocode

```c

```

## disassembly

```asm
0x18a400  call     class System.Web.Configuration.RuntimeConfig System.Web.Configuration.RuntimeConfig::GetAppConfig()
0x18a405  callvirt instance class System.Web.Configuration.SqlCacheDependencySection System.Web.Configuration.RuntimeConfig::get_SqlCacheDependency()
0x18a40a  stloc.0
0x18a40b  ldloc.0
0x18a40c  callvirt instance bool System.Web.Configuration.SqlCacheDependencySection::get_Enabled()
0x18a411  brtrue.s loc_18A457
0x18a413  ldstr    aPollingNotEnab// "Polling_not_enabled_for_sql_cache"
0x18a418  call     string System.Web.SR::GetString(string name)
0x18a41d  ldloc.0
0x18a41e  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x18a423  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x18a428  ldstr    aEnabled_0// "enabled"
0x18a42d  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x18a432  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x18a437  ldloc.0
0x18a438  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x18a43d  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x18a442  ldstr    aEnabled_0// "enabled"
0x18a447  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x18a44c  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x18a451  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x18a456  throw
0x18a457  ldarg.0
0x18a458  call     class System.Web.Configuration.SqlCacheDependencyDatabase System.Web.Caching.SqlCacheDependencyManager::GetDatabaseConfig(string database)
0x18a45d  stloc.1
0x18a45e  ldloc.1
0x18a45f  callvirt instance int32 System.Web.Configuration.SqlCacheDependencyDatabase::get_PollTime()
0x18a464  brtrue.s loc_18A4B4
0x18a466  ldstr    aPolltimeZeroFo// "Polltime_zero_for_database_sql_cache"
0x18a46b  ldc.i4.1
0x18a46c  newarr   [mscorlib]System.Object
0x18a471  dup
0x18a472  ldc.i4.0
0x18a473  ldarg.0
0x18a474  stelem.ref
0x18a475  call     string System.Web.SR::GetString(string name, object[] args)
0x18a47a  ldloc.1
0x18a47b  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x18a480  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x18a485  ldstr    aPolltime// "pollTime"
0x18a48a  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x18a48f  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x18a494  ldloc.1
0x18a495  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x18a49a  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x18a49f  ldstr    aPolltime// "pollTime"
0x18a4a4  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x18a4a9  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x18a4ae  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x18a4b3  throw
0x18a4b4  ldsfld   class [mscorlib]System.Collections.Hashtable System.Web.Caching.SqlCacheDependencyManager::s_DatabaseNotifStates
0x18a4b9  ldarg.0
0x18a4ba  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x18a4bf  brfalse.s loc_18A4C2
0x18a4c1  ret
0x18a4c2  ldloc.1
0x18a4c3  callvirt instance string System.Web.Configuration.SqlCacheDependencyDatabase::get_ConnectionStringName()
0x18a4c8  ldc.i4.1
0x18a4c9  ldc.i4.1
0x18a4ca  call     string System.Web.DataAccess.SqlConnectionHelper::GetConnectionString(string specifiedConnectionString, bool lookupConnectionString, bool appLevel)
0x18a4cf  stloc.2
0x18a4d0  ldloc.2
0x18a4d1  brfalse.s loc_18A4DC
0x18a4d3  ldloc.2
0x18a4d4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x18a4d9  ldc.i4.1
0x18a4da  bge.s    loc_18A52F
0x18a4dc  ldstr    aConnectionStri// "Connection_string_not_found"
0x18a4e1  ldc.i4.1
0x18a4e2  newarr   [mscorlib]System.Object
0x18a4e7  dup
0x18a4e8  ldc.i4.0
0x18a4e9  ldloc.1
0x18a4ea  callvirt instance string System.Web.Configuration.SqlCacheDependencyDatabase::get_ConnectionStringName()
0x18a4ef  stelem.ref
0x18a4f0  call     string System.Web.SR::GetString(string name, object[] args)
0x18a4f5  ldloc.1
0x18a4f6  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x18a4fb  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x18a500  ldstr    aConnectionstri// "connectionStringName"
0x18a505  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x18a50a  callvirt instance string [System.Configuration]System.Configuration.PropertyInformation::get_Source()
0x18a50f  ldloc.1
0x18a510  callvirt instance class [System.Configuration]System.Configuration.ElementInformation [System.Configuration]System.Configuration.ConfigurationElement::get_ElementInformation()
0x18a515  callvirt instance class [System.Configuration]System.Configuration.PropertyInformationCollection [System.Configuration]System.Configuration.ElementInformation::get_Properties()
0x18a51a  ldstr    aConnectionstri// "connectionStringName"
0x18a51f  callvirt instance class [System.Configuration]System.Configuration.PropertyInformation [System.Configuration]System.Configuration.PropertyInformationCollection::get_Item(string)
0x18a524  callvirt instance int32 [System.Configuration]System.Configuration.PropertyInformation::get_LineNumber()
0x18a529  newobj   instance void [System.Configuration]System.Configuration.ConfigurationErrorsException::.ctor(string, string, int32)
0x18a52e  throw
0x18a52f  ldsfld   class [mscorlib]System.Collections.Hashtable System.Web.Caching.SqlCacheDependencyManager::s_DatabaseNotifStates
0x18a534  stloc.3
0x18a535  ldc.i4.0
0x18a536  stloc.s  4
0x18a538  ldloc.3
0x18a539  ldloca.s 4
0x18a53b  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x18a540  ldsfld   class [mscorlib]System.Collections.Hashtable System.Web.Caching.SqlCacheDependencyManager::s_DatabaseNotifStates
0x18a545  ldarg.0
0x18a546  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x18a54b  brfalse.s loc_18A54F
0x18a54d  leave.s  loc_18A592
0x18a54f  ldarg.0
0x18a550  ldloc.2
0x18a551  ldloc.1
0x18a552  callvirt instance int32 System.Web.Configuration.SqlCacheDependencyDatabase::get_PollTime()
0x18a557  newobj   instance void System.Web.Caching.DatabaseNotifState::.ctor(string database, string connection, int32 polltime)
0x18a55c  stloc.s  5
0x18a55e  ldloc.s  5
0x18a560  ldsfld   class [mscorlib]System.Threading.TimerCallback System.Web.Caching.SqlCacheDependencyManager::s_timerCallback
0x18a565  ldloc.s  5
0x18a567  ldc.i4.0
0x18a568  ldloc.1
0x18a569  callvirt instance int32 System.Web.Configuration.SqlCacheDependencyDatabase::get_PollTime()
0x18a56e  newobj   instance void [mscorlib]System.Threading.Timer::.ctor(class [mscorlib]System.Threading.TimerCallback, object, int32, int32)
0x18a573  stfld    class [mscorlib]System.Threading.Timer System.Web.Caching.DatabaseNotifState::_timer
0x18a578  ldsfld   class [mscorlib]System.Collections.Hashtable System.Web.Caching.SqlCacheDependencyManager::s_DatabaseNotifStates
0x18a57d  ldarg.0
0x18a57e  ldloc.s  5
0x18a580  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x18a585  leave.s  loc_18A592
0x18a587  ldloc.s  4
0x18a589  brfalse.s loc_18A591
0x18a58b  ldloc.3
0x18a58c  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x18a591  endfinally
0x18a592  ret
```
