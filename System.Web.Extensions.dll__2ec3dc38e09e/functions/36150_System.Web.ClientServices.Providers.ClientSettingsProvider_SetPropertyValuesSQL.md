# System.Web.ClientServices.Providers.ClientSettingsProvider::SetPropertyValuesSQL

- ea: `0x36150`
- end: `0x36425`
- name: `System.Web.ClientServices.Providers.ClientSettingsProvider::SetPropertyValuesSQL`
- size: `725`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x355d0`
- `0x356e0`

## callees

- `0x36150`
- `0x36530`
- `0x36800`
- `0x37320`
- `0x37370`
- `0x37cf0`
- `0x37d00`
- `0x37d10`
- `0x37d20`
- `0x37d30`
- `0x37d40`
- `0x37d80`
- `0x37dd0`
- `0x380e0`

## string_xrefs

- `0x362c8`: `DELETE FROM Settings WHERE PropertyName = @PropName`

## pseudocode

```c

```

## disassembly

```asm
0x36150  call     class [mscorlib]System.Security.Principal.IPrincipal [mscorlib]System.Threading.Thread::get_CurrentPrincipal()
0x36155  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x3615a  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x3615f  stloc.0
0x36160  ldsfld   bool System.Web.ClientServices.Providers.ClientSettingsProvider::_UsingFileSystemStore
0x36165  brtrue.s loc_36171
0x36167  ldsfld   bool System.Web.ClientServices.Providers.ClientSettingsProvider::_UsingIsolatedStore
0x3616c  brfalse  loc_36279
0x36171  ldloc.0
0x36172  ldsfld   bool System.Web.ClientServices.Providers.ClientSettingsProvider::_UsingIsolatedStore
0x36177  call     class System.Web.ClientServices.Providers.ClientData System.Web.ClientServices.Providers.ClientDataManager::GetUserClientData(string username, bool useIsolatedStore)
0x3617c  stloc.1
0x3617d  ldloc.1
0x3617e  ldarg.1
0x3617f  callvirt instance int32 [System]System.Configuration.SettingsPropertyValueCollection::get_Count()
0x36184  newarr   [mscorlib]System.String
0x36189  callvirt instance void System.Web.ClientServices.Providers.ClientData::set_SettingsNames(string[] value)
0x3618e  ldloc.1
0x3618f  ldarg.1
0x36190  callvirt instance int32 [System]System.Configuration.SettingsPropertyValueCollection::get_Count()
0x36195  newarr   [mscorlib]System.String
0x3619a  callvirt instance void System.Web.ClientServices.Providers.ClientData::set_SettingsStoredAs(string[] value)
0x3619f  ldloc.1
0x361a0  ldarg.1
0x361a1  callvirt instance int32 [System]System.Configuration.SettingsPropertyValueCollection::get_Count()
0x361a6  newarr   [mscorlib]System.String
0x361ab  callvirt instance void System.Web.ClientServices.Providers.ClientData::set_SettingsValues(string[] value)
0x361b0  ldc.i4.0
0x361b1  stloc.2
0x361b2  ldarg.1
0x361b3  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.Configuration.SettingsPropertyValueCollection::GetEnumerator()
0x361b8  stloc.3
0x361b9  br       loc_36247
0x361be  ldloc.3
0x361bf  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x361c4  castclass [System]System.Configuration.SettingsPropertyValue
0x361c9  stloc.s  4
0x361cb  ldloc.1
0x361cc  callvirt instance string[] System.Web.ClientServices.Providers.ClientData::get_SettingsNames()
0x361d1  ldloc.2
0x361d2  ldloc.s  4
0x361d4  callvirt instance class [System]System.Configuration.SettingsProperty [System]System.Configuration.SettingsPropertyValue::get_Property()
0x361d9  callvirt instance string [System]System.Configuration.SettingsProperty::get_Name()
0x361de  stelem.ref
0x361df  ldloc.s  4
0x361e1  callvirt instance object [System]System.Configuration.SettingsPropertyValue::get_SerializedValue()
0x361e6  stloc.s  5
0x361e8  ldloc.s  5
0x361ea  brtrue.s loc_361FB
0x361ec  ldloc.1
0x361ed  callvirt instance string[] System.Web.ClientServices.Providers.ClientData::get_SettingsStoredAs()
0x361f2  ldloc.2
0x361f3  ldstr    aN// "N"
0x361f8  stelem.ref
0x361f9  br.s     loc_36243
0x361fb  ldloc.s  5
0x361fd  isinst   [mscorlib]System.String
0x36202  brfalse.s loc_36222
0x36204  ldloc.1
0x36205  callvirt instance string[] System.Web.ClientServices.Providers.ClientData::get_SettingsStoredAs()
0x3620a  ldloc.2
0x3620b  ldstr    aS_0// "S"
0x36210  stelem.ref
0x36211  ldloc.1
0x36212  callvirt instance string[] System.Web.ClientServices.Providers.ClientData::get_SettingsValues()
0x36217  ldloc.2
0x36218  ldloc.s  5
0x3621a  castclass [mscorlib]System.String
0x3621f  stelem.ref
0x36220  br.s     loc_36243
0x36222  ldloc.1
0x36223  callvirt instance string[] System.Web.ClientServices.Providers.ClientData::get_SettingsStoredAs()
0x36228  ldloc.2
0x36229  ldstr    aB// "B"
0x3622e  stelem.ref
0x3622f  ldloc.1
0x36230  callvirt instance string[] System.Web.ClientServices.Providers.ClientData::get_SettingsValues()
0x36235  ldloc.2
0x36236  ldloc.s  5
0x36238  castclass unsigned int8[]
0x3623d  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x36242  stelem.ref
0x36243  ldloc.2
0x36244  ldc.i4.1
0x36245  add
0x36246  stloc.2
0x36247  ldloc.3
0x36248  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3624d  brtrue   loc_361BE
0x36252  leave.s  loc_36268
0x36254  ldloc.3
0x36255  isinst   [mscorlib]System.IDisposable
0x3625a  stloc.s  6
0x3625c  ldloc.s  6
0x3625e  brfalse.s loc_36267
0x36260  ldloc.s  6
0x36262  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36267  endfinally
0x36268  ldarg.2
0x36269  brfalse.s loc_36272
0x3626b  ldloc.1
0x3626c  ldc.i4.1
0x3626d  callvirt instance void System.Web.ClientServices.Providers.ClientData::set_SettingsCacheIsMoreFresh(bool value)
0x36272  ldloc.1
0x36273  callvirt instance void System.Web.ClientServices.Providers.ClientData::Save()
0x36278  ret
0x36279  ldloc.0
0x3627a  ldarg.0
0x3627b  call     instance string System.Web.ClientServices.Providers.ClientSettingsProvider::GetConnectionString()
0x36280  ldarg.0
0x36281  ldfld    string System.Web.ClientServices.Providers.ClientSettingsProvider::_ConnectionStringProvider
0x36286  call     class [System.Data]System.Data.Common.DbConnection System.Web.ClientServices.Providers.SqlHelper::GetConnection(string username, string connectionString, string sqlProvider)
0x3628b  stloc.s  7
0x3628d  ldnull
0x3628e  stloc.s  8
0x36290  ldloc.s  7
0x36292  callvirt instance class [System.Data]System.Data.Common.DbTransaction [System.Data]System.Data.Common.DbConnection::BeginTransaction()
0x36297  stloc.s  8
0x36299  ldarg.1
0x3629a  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.Configuration.SettingsPropertyValueCollection::GetEnumerator()
0x3629f  stloc.s  9
0x362a1  br       loc_363CC
0x362a6  ldloc.s  9
0x362a8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x362ad  castclass [System]System.Configuration.SettingsPropertyValue
0x362b2  stloc.s  0xA
0x362b4  ldloc.s  7
0x362b6  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x362bb  stloc.s  0xB
0x362bd  ldloc.s  0xB
0x362bf  ldloc.s  8
0x362c1  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x362c6  ldloc.s  0xB
0x362c8  ldstr    aDeleteFromSett// "DELETE FROM Settings WHERE PropertyName"...
0x362cd  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x362d2  ldloc.s  7
0x362d4  ldloc.s  0xB
0x362d6  ldstr    aPropname// "@PropName"
0x362db  ldloc.s  0xA
0x362dd  callvirt instance class [System]System.Configuration.SettingsProperty [System]System.Configuration.SettingsPropertyValue::get_Property()
0x362e2  callvirt instance string [System]System.Configuration.SettingsProperty::get_Name()
0x362e7  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x362ec  ldloc.s  0xB
0x362ee  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x362f3  pop
0x362f4  ldloc.s  7
0x362f6  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x362fb  stloc.s  0xB
0x362fd  ldloc.s  0xB
0x362ff  ldloc.s  8
0x36301  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_Transaction(class [System.Data]System.Data.Common.DbTransaction)
0x36306  ldloc.s  0xA
0x36308  callvirt instance object [System]System.Configuration.SettingsPropertyValue::get_SerializedValue()
0x3630d  stloc.s  0xC
0x3630f  ldloc.s  0xC
0x36311  brtrue.s loc_3633E
0x36313  ldloc.s  0xB
0x36315  ldstr    aInsertIntoSett// "INSERT INTO Settings (PropertyName, Pro"...
0x3631a  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x3631f  ldloc.s  7
0x36321  ldloc.s  0xB
0x36323  ldstr    aPropname// "@PropName"
0x36328  ldloc.s  0xA
0x3632a  callvirt instance class [System]System.Configuration.SettingsProperty [System]System.Configuration.SettingsPropertyValue::get_Property()
0x3632f  callvirt instance string [System]System.Configuration.SettingsProperty::get_Name()
0x36334  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x36339  br       loc_363C4
0x3633e  ldloc.s  0xC
0x36340  isinst   [mscorlib]System.String
0x36345  brfalse.s loc_36384
0x36347  ldloc.s  0xB
0x36349  ldstr    aInsertIntoSett_0// "INSERT INTO Settings (PropertyName, Pro"...
0x3634e  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x36353  ldloc.s  7
0x36355  ldloc.s  0xB
0x36357  ldstr    aPropname// "@PropName"
0x3635c  ldloc.s  0xA
0x3635e  callvirt instance class [System]System.Configuration.SettingsProperty [System]System.Configuration.SettingsPropertyValue::get_Property()
0x36363  callvirt instance string [System]System.Configuration.SettingsProperty::get_Name()
0x36368  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x3636d  ldloc.s  7
0x3636f  ldloc.s  0xB
0x36371  ldstr    aPropval// "@PropVal"
0x36376  ldloc.s  0xC
0x36378  castclass [mscorlib]System.String
0x3637d  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x36382  br.s     loc_363C4
0x36384  ldloc.s  0xB
0x36386  ldstr    aInsertIntoSett_1// "INSERT INTO Settings (PropertyName, Pro"...
0x3638b  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x36390  ldloc.s  7
0x36392  ldloc.s  0xB
0x36394  ldstr    aPropname// "@PropName"
0x36399  ldloc.s  0xA
0x3639b  callvirt instance class [System]System.Configuration.SettingsProperty [System]System.Configuration.SettingsPropertyValue::get_Property()
0x363a0  callvirt instance string [System]System.Configuration.SettingsProperty::get_Name()
0x363a5  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x363aa  ldloc.s  7
0x363ac  ldloc.s  0xB
0x363ae  ldstr    aPropval// "@PropVal"
0x363b3  ldloc.s  0xC
0x363b5  castclass unsigned int8[]
0x363ba  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x363bf  call     void System.Web.ClientServices.Providers.SqlHelper::AddParameter(class [System.Data]System.Data.Common.DbConnection conn, class [System.Data]System.Data.Common.DbCommand cmd, string paramName, object paramValue)
0x363c4  ldloc.s  0xB
0x363c6  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x363cb  pop
0x363cc  ldloc.s  9
0x363ce  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x363d3  brtrue   loc_362A6
0x363d8  leave.s  loc_363EF
0x363da  ldloc.s  9
0x363dc  isinst   [mscorlib]System.IDisposable
0x363e1  stloc.s  6
0x363e3  ldloc.s  6
0x363e5  brfalse.s loc_363EE
0x363e7  ldloc.s  6
0x363e9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x363ee  endfinally
0x363ef  leave.s  loc_3641A
0x363f1  pop
0x363f2  ldloc.s  8
0x363f4  brfalse.s loc_36400
0x363f6  ldloc.s  8
0x363f8  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Rollback()
0x363fd  ldnull
0x363fe  stloc.s  8
0x36400  rethrow
0x36402  ldloc.s  8
0x36404  brfalse.s loc_3640D
0x36406  ldloc.s  8
0x36408  callvirt instance void [System.Data]System.Data.Common.DbTransaction::Commit()
0x3640d  endfinally
0x3640e  ldloc.s  7
0x36410  brfalse.s loc_36419
0x36412  ldloc.s  7
0x36414  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36419  endfinally
0x3641a  ldarg.2
0x3641b  brfalse.s loc_36424
0x3641d  ldarg.0
0x3641e  ldc.i4.1
0x3641f  call     instance void System.Web.ClientServices.Providers.ClientSettingsProvider::SetIsCacheMoreFresh(bool fSet)
0x36424  ret
```
