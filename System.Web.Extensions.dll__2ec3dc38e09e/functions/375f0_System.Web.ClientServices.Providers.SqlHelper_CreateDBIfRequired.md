# System.Web.ClientServices.Providers.SqlHelper::CreateDBIfRequired

- ea: `0x375f0`
- end: `0x3774f`
- name: `System.Web.ClientServices.Providers.SqlHelper::CreateDBIfRequired`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x375d0`

## callees

- `0x2b2f0`
- `0x375f0`
- `0x37750`
- `0x377e0`
- `0x37880`

## string_xrefs

- `0x37698`: `CreateDatabase`
- `0x376d7`: `CREATE TABLE ApplicationProperties (PropertyName nvarchar(256), PropertyValue nvarchar(256))`
- `0x376ed`: `CREATE TABLE UserProperties (PropertyName nvarchar(256), PropertyValue nvarchar(256))`
- `0x37709`: `CREATE TABLE Roles (UserName nvarchar(256), RoleName nvarchar(256))`
- `0x37725`: `CREATE TABLE Settings (PropertyName nvarchar(256), PropertyStoredAs nvarchar(1), PropertyValue nvarchar(2048))`

## pseudocode

```c

```

## disassembly

```asm
0x375f0  ldarg.1
0x375f1  ldstr    aSqlCe// "|SQL/CE|"
0x375f6  callvirt instance bool [mscorlib]System.String::Contains(string)
0x375fb  brtrue.s loc_375FF
0x375fd  ldnull
0x375fe  ret
0x375ff  ldnull
0x37600  stloc.0
0x37601  ldarg.1
0x37602  ldc.i4.0
0x37603  call     class [System.Data]System.Data.Common.DbConnection System.Web.ClientServices.Providers.SqlHelper::CreateNewSqlCeConnection(string connectionString, bool openConn)
0x37608  stloc.0
0x37609  ldloc.0
0x3760a  callvirt instance string [System.Data]System.Data.Common.DbConnection::get_Database()
0x3760f  callvirt instance string [mscorlib]System.String::Trim()
0x37614  ldstr    aSqlCe// "|SQL/CE|"
0x37619  ldc.i4.5
0x3761a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x3761f  brfalse.s loc_3762E
0x37621  ldloc.0
0x37622  callvirt instance void [System.Data]System.Data.Common.DbConnection::Open()
0x37627  ldloc.0
0x37628  stloc.3
0x37629  leave    loc_3774D
0x3762e  ldloc.0
0x3762f  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x37634  ldnull
0x37635  stloc.0
0x37636  leave.s  loc_37647
0x37638  stloc.s  4
0x3763a  call     string System.Web.Resources.AtlasWeb::get_SqlHelper_SqlEverywhereNotInstalled()
0x3763f  ldloc.s  4
0x37641  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, class [mscorlib]System.Exception)
0x37646  throw
0x37647  ldarg.0
0x37648  ldstr    aDbSpf// "_DB.spf"
0x3764d  call     string System.Web.ClientServices.Providers.SqlHelper::GetFullDBFileName(string username, string extension)
0x37652  stloc.1
0x37653  ldloc.1
0x37654  call     bool [mscorlib]System.IO.File::Exists(string)
0x37659  ldc.i4.0
0x3765a  ceq
0x3765c  stloc.2
0x3765d  ldarg.1
0x3765e  ldstr    aSqlCe// "|SQL/CE|"
0x37663  ldloc.1
0x37664  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x37669  starg.s  1
0x3766b  ldloc.2
0x3766c  brfalse  loc_37745
0x37671  ldstr    aSqlceengine// "SqlCeEngine"
0x37676  call     class [mscorlib]System.Type System.Web.ClientServices.Providers.SqlHelper::GetSqlCeType(string typeName)
0x3767b  ldc.i4.1
0x3767c  newarr   [mscorlib]System.Object
0x37681  dup
0x37682  ldc.i4.0
0x37683  ldarg.1
0x37684  stelem.ref
0x37685  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type, object[])
0x3768a  castclass [mscorlib]System.IDisposable
0x3768f  stloc.s  5
0x37691  ldloc.s  5
0x37693  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x37698  ldstr    aCreatedatabase// "CreateDatabase"
0x3769d  ldc.i4   0x114
0x376a2  ldnull
0x376a3  ldloc.s  5
0x376a5  ldnull
0x376a6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x376ab  callvirt instance object [mscorlib]System.Type::InvokeMember(string, valuetype [mscorlib]System.Reflection.BindingFlags, class [mscorlib]System.Reflection.Binder, object, object[], class [mscorlib]System.Globalization.CultureInfo)
0x376b0  pop
0x376b1  leave.s  loc_376BF
0x376b3  ldloc.s  5
0x376b5  brfalse.s loc_376BE
0x376b7  ldloc.s  5
0x376b9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x376be  endfinally
0x376bf  ldarg.1
0x376c0  ldc.i4.1
0x376c1  call     class [System.Data]System.Data.Common.DbConnection System.Web.ClientServices.Providers.SqlHelper::CreateNewSqlCeConnection(string connectionString, bool openConn)
0x376c6  dup
0x376c7  stloc.0
0x376c8  stloc.s  6
0x376ca  ldloc.0
0x376cb  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x376d0  stloc.s  7
0x376d2  ldarg.0
0x376d3  brtrue.s loc_376EB
0x376d5  ldloc.s  7
0x376d7  ldstr    aCreateTableApp// "CREATE TABLE ApplicationProperties (Pro"...
0x376dc  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x376e1  ldloc.s  7
0x376e3  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x376e8  pop
0x376e9  leave.s  loc_37745
0x376eb  ldloc.s  7
0x376ed  ldstr    aCreateTableUse// "CREATE TABLE UserProperties (PropertyNa"...
0x376f2  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x376f7  ldloc.s  7
0x376f9  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x376fe  pop
0x376ff  ldloc.0
0x37700  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x37705  stloc.s  7
0x37707  ldloc.s  7
0x37709  ldstr    aCreateTableRol// "CREATE TABLE Roles (UserName nvarchar(2"...
0x3770e  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x37713  ldloc.s  7
0x37715  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x3771a  pop
0x3771b  ldloc.0
0x3771c  callvirt instance class [System.Data]System.Data.Common.DbCommand [System.Data]System.Data.Common.DbConnection::CreateCommand()
0x37721  stloc.s  7
0x37723  ldloc.s  7
0x37725  ldstr    aCreateTableSet// "CREATE TABLE Settings (PropertyName nva"...
0x3772a  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x3772f  ldloc.s  7
0x37731  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x37736  pop
0x37737  leave.s  loc_37745
0x37739  ldloc.s  6
0x3773b  brfalse.s loc_37744
0x3773d  ldloc.s  6
0x3773f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x37744  endfinally
0x37745  ldarg.1
0x37746  ldc.i4.1
0x37747  call     class [System.Data]System.Data.Common.DbConnection System.Web.ClientServices.Providers.SqlHelper::CreateNewSqlCeConnection(string connectionString, bool openConn)
0x3774c  ret
0x3774d  ldloc.3
0x3774e  ret
```
