# Microsoft.SharePoint.SPStoredProceduresContent::proc_UpdateCachedNav

- ea: `0x156100`
- end: `0x1563f9`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::proc_UpdateCachedNav`
- size: `761`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x156100`
- `0x8e5050`
- `0x8e50a0`
- `0x8e50b0`
- `0x8e5130`

## string_xrefs

- `0x1561f8`: `@CachedNavData`
- `0x156216`: `@CachedNavData`
- `0x156232`: `@CachedInheritedNavData`
- `0x156250`: `@CachedInheritedNavData`
- `0x15626d`: `@CachedNavScopeData`
- `0x15628b`: `@CachedNavScopeData`
- `0x1562a8`: `@NavParentCachedNavData`
- `0x1562c6`: `@NavParentCachedNavData`
- `0x1562e3`: `@NavParentCachedScopeData`
- `0x156301`: `@NavParentCachedScopeData`
- `0x156323`: `@CachedNavDirty`
- `0x156340`: `@CachedNavDirty`
- `0x15636b`: `@CachedDataVersion`
- `0x156388`: `@CachedDataVersion`
- `0x1563b3`: `@NavParentCachedDataVersion`
- `0x1563d0`: `@NavParentCachedDataVersion`
- `0x156107`: `dbo.proc_UpdateCachedNav`

## pseudocode

```c

```

## disassembly

```asm
0x156100  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlCommand::.ctor()
0x156105  stloc.0
0x156106  ldloc.0
0x156107  ldstr    aDboProcUpdatec_0// "dbo.proc_UpdateCachedNav"
0x15610c  callvirt instance void Microsoft.SharePoint.Utilities.SPSqlCommand::SetStoredProcedure(string strProc)
0x156111  ldarga.s 0
0x156113  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x156118  brtrue.s loc_156138
0x15611a  ldloc.0
0x15611b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x156120  ldstr    aSiteid_1// "@SiteId"
0x156125  ldc.i4.s 0xE
0x156127  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15612c  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x156131  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x156136  br.s     loc_15615B
0x156138  ldloc.0
0x156139  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15613e  ldstr    aSiteid_1// "@SiteId"
0x156143  ldc.i4.s 0xE
0x156145  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15614a  ldarga.s 0
0x15614c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x156151  box      [mscorlib]System.Guid
0x156156  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15615b  ldarga.s 1
0x15615d  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x156162  brtrue.s loc_156182
0x156164  ldloc.0
0x156165  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15616a  ldstr    aWebid_0// "@WebId"
0x15616f  ldc.i4.s 0xE
0x156171  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x156176  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15617b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x156180  br.s     loc_1561A5
0x156182  ldloc.0
0x156183  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x156188  ldstr    aWebid_0// "@WebId"
0x15618d  ldc.i4.s 0xE
0x15618f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x156194  ldarga.s 1
0x156196  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x15619b  box      [mscorlib]System.Guid
0x1561a0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1561a5  ldarga.s 2
0x1561a7  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x1561ac  brtrue.s loc_1561CC
0x1561ae  ldloc.0
0x1561af  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x1561b4  ldstr    aNavparentwebid// "@NavParentWebId"
0x1561b9  ldc.i4.s 0xE
0x1561bb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x1561c0  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1561c5  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1561ca  br.s     loc_1561EF
0x1561cc  ldloc.0
0x1561cd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x1561d2  ldstr    aNavparentwebid// "@NavParentWebId"
0x1561d7  ldc.i4.s 0xE
0x1561d9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x1561de  ldarga.s 2
0x1561e0  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x1561e5  box      [mscorlib]System.Guid
0x1561ea  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1561ef  ldarg.3
0x1561f0  brtrue.s loc_156210
0x1561f2  ldloc.0
0x1561f3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x1561f8  ldstr    aCachednavdata// "@CachedNavData"
0x1561fd  ldc.i4.s 0x15
0x1561ff  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x156204  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x156209  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15620e  br.s     loc_156228
0x156210  ldloc.0
0x156211  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x156216  ldstr    aCachednavdata// "@CachedNavData"
0x15621b  ldc.i4.s 0x15
0x15621d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x156222  ldarg.3
0x156223  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x156228  ldarg.s  4
0x15622a  brtrue.s loc_15624A
0x15622c  ldloc.0
0x15622d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x156232  ldstr    aCachedinherite// "@CachedInheritedNavData"
0x156237  ldc.i4.s 0x15
0x156239  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15623e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x156243  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x156248  br.s     loc_156263
0x15624a  ldloc.0
0x15624b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x156250  ldstr    aCachedinherite// "@CachedInheritedNavData"
0x156255  ldc.i4.s 0x15
0x156257  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15625c  ldarg.s  4
0x15625e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x156263  ldarg.s  5
0x156265  brtrue.s loc_156285
0x156267  ldloc.0
0x156268  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15626d  ldstr    aCachednavscope// "@CachedNavScopeData"
0x156272  ldc.i4.s 0xC
0x156274  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x156279  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15627e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x156283  br.s     loc_15629E
0x156285  ldloc.0
0x156286  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15628b  ldstr    aCachednavscope// "@CachedNavScopeData"
0x156290  ldc.i4.s 0xC
0x156292  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x156297  ldarg.s  5
0x156299  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15629e  ldarg.s  6
0x1562a0  brtrue.s loc_1562C0
0x1562a2  ldloc.0
0x1562a3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x1562a8  ldstr    aNavparentcache// "@NavParentCachedNavData"
0x1562ad  ldc.i4.s 0x15
0x1562af  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x1562b4  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1562b9  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1562be  br.s     loc_1562D9
0x1562c0  ldloc.0
0x1562c1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x1562c6  ldstr    aNavparentcache// "@NavParentCachedNavData"
0x1562cb  ldc.i4.s 0x15
0x1562cd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x1562d2  ldarg.s  6
0x1562d4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1562d9  ldarg.s  7
0x1562db  brtrue.s loc_1562FB
0x1562dd  ldloc.0
0x1562de  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x1562e3  ldstr    aNavparentcache_0// "@NavParentCachedScopeData"
0x1562e8  ldc.i4.s 0xC
0x1562ea  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x1562ef  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1562f4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1562f9  br.s     loc_156314
0x1562fb  ldloc.0
0x1562fc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x156301  ldstr    aNavparentcache_0// "@NavParentCachedScopeData"
0x156306  ldc.i4.s 0xC
0x156308  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15630d  ldarg.s  7
0x15630f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x156314  ldarga.s 8
0x156316  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x15631b  brtrue.s loc_15633A
0x15631d  ldloc.0
0x15631e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x156323  ldstr    aCachednavdirty// "@CachedNavDirty"
0x156328  ldc.i4.8
0x156329  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15632e  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x156333  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x156338  br.s     loc_15635C
0x15633a  ldloc.0
0x15633b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x156340  ldstr    aCachednavdirty// "@CachedNavDirty"
0x156345  ldc.i4.8
0x156346  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x15634b  ldarga.s 8
0x15634d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x156352  box      [mscorlib]System.Int32
0x156357  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x15635c  ldarga.s 9
0x15635e  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x156363  brtrue.s loc_156382
0x156365  ldloc.0
0x156366  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x15636b  ldstr    aCacheddatavers// "@CachedDataVersion"
0x156370  ldc.i4.8
0x156371  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x156376  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15637b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x156380  br.s     loc_1563A4
0x156382  ldloc.0
0x156383  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x156388  ldstr    aCacheddatavers// "@CachedDataVersion"
0x15638d  ldc.i4.8
0x15638e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x156393  ldarga.s 9
0x156395  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x15639a  box      [mscorlib]System.Int32
0x15639f  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1563a4  ldarga.s 0xA
0x1563a6  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x1563ab  brtrue.s loc_1563CA
0x1563ad  ldloc.0
0x1563ae  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x1563b3  ldstr    aNavparentcache_1// "@NavParentCachedDataVersion"
0x1563b8  ldc.i4.8
0x1563b9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x1563be  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1563c3  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1563c8  br.s     loc_1563EC
0x1563ca  ldloc.0
0x1563cb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection Microsoft.SharePoint.Utilities.SPSqlCommand::get_Parameters()
0x1563d0  ldstr    aNavparentcache_1// "@NavParentCachedDataVersion"
0x1563d5  ldc.i4.8
0x1563d6  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x1563db  ldarga.s 0xA
0x1563dd  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x1563e2  box      [mscorlib]System.Int32
0x1563e7  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x1563ec  leave.s  loc_1563F7
0x1563ee  pop
0x1563ef  ldloc.0
0x1563f0  callvirt instance void Microsoft.SharePoint.Utilities.SPSqlCommand::Dispose()
0x1563f5  rethrow
0x1563f7  ldloc.0
0x1563f8  ret
```
