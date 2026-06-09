# System.Web.DataAccess.SqlConnectionHelper::EnsureDBFile

- ea: `0x4c6d0`
- end: `0x4c911`
- name: `System.Web.DataAccess.SqlConnectionHelper::EnsureDBFile`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x4c580`

## callees

- `0x24240`
- `0x29e60`
- `0x34fa0`
- `0x4c630`
- `0x4c6d0`
- `0x4c920`

## string_xrefs

- `0x4c739`: `|DATADIRECTORY|`
- `0x4c758`: `|DATADIRECTORY|`
- `0x4c763`: `|DATADIRECTORY|`
- `0x4c891`: `Provider_can_not_create_file_in_this_trust_level`

## pseudocode

```c

```

## disassembly

```asm
0x4c6d0  ldnull
0x4c6d1  stloc.0
0x4c6d2  ldnull
0x4c6d3  stloc.1
0x4c6d4  call     string System.Web.DataAccess.SqlConnectionHelper::GetDataDirectory()
0x4c6d9  stloc.2
0x4c6da  ldc.i4.1
0x4c6db  stloc.3
0x4c6dc  ldc.i4.1
0x4c6dd  stloc.s  4
0x4c6df  ldarg.0
0x4c6e0  ldc.i4.1
0x4c6e1  newarr   [mscorlib]System.Char
0x4c6e6  dup
0x4c6e7  ldc.i4.0
0x4c6e8  ldc.i4.s 0x3B
0x4c6ea  stelem.i2
0x4c6eb  ldc.i4.1
0x4c6ec  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x4c6f1  stloc.s  5
0x4c6f3  ldarg.0
0x4c6f4  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x4c6f9  ldstr    aLocaldb// "(LOCALDB)"
0x4c6fe  callvirt instance bool [mscorlib]System.String::Contains(string)
0x4c703  ldc.i4.0
0x4c704  ceq
0x4c706  stloc.s  6
0x4c708  ldc.i4.1
0x4c709  stloc.s  7
0x4c70b  ldloc.s  5
0x4c70d  stloc.s  8
0x4c70f  ldc.i4.0
0x4c710  stloc.s  9
0x4c712  br       loc_4C859
0x4c717  ldloc.s  8
0x4c719  ldloc.s  9
0x4c71b  ldelem.ref
0x4c71c  stloc.s  0xA
0x4c71e  ldloc.s  0xA
0x4c720  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4c725  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x4c72a  callvirt instance string [mscorlib]System.String::Trim()
0x4c72f  stloc.s  0xB
0x4c731  ldloc.3
0x4c732  brfalse  loc_4C7BC
0x4c737  ldloc.s  0xB
0x4c739  ldstr    aDatadirectory_0// "|DATADIRECTORY|"
0x4c73e  callvirt instance bool [mscorlib]System.String::Contains(string)
0x4c743  brfalse.s loc_4C7BC
0x4c745  ldc.i4.0
0x4c746  stloc.3
0x4c747  ldarg.0
0x4c748  ldloc.s  0xA
0x4c74a  ldstr    aPoolingFalse// "Pooling=false"
0x4c74f  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x4c754  starg.s  0
0x4c756  ldloc.s  0xB
0x4c758  ldstr    aDatadirectory_0// "|DATADIRECTORY|"
0x4c75d  ldc.i4.4
0x4c75e  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x4c763  ldstr    aDatadirectory_0// "|DATADIRECTORY|"
0x4c768  call     instance int32 [mscorlib]System.String::get_Length()
0x4c76d  add
0x4c76e  stloc.s  0xC
0x4c770  ldloc.s  0xB
0x4c772  ldloc.s  0xC
0x4c774  callvirt instance string [mscorlib]System.String::Substring(int32)
0x4c779  callvirt instance string [mscorlib]System.String::Trim()
0x4c77e  stloc.0
0x4c77f  br.s     loc_4C789
0x4c781  ldloc.0
0x4c782  ldc.i4.1
0x4c783  callvirt instance string [mscorlib]System.String::Substring(int32)
0x4c788  stloc.0
0x4c789  ldloc.0
0x4c78a  ldstr    asc_1B3DEA// "\\"
0x4c78f  ldc.i4.4
0x4c790  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x4c795  brtrue.s loc_4C781
0x4c797  ldloc.0
0x4c798  ldstr    asc_1C320C// ".."
0x4c79d  callvirt instance bool [mscorlib]System.String::Contains(string)
0x4c7a2  brfalse.s loc_4C7A8
0x4c7a4  ldnull
0x4c7a5  stloc.0
0x4c7a6  br.s     loc_4C7B0
0x4c7a8  ldloc.2
0x4c7a9  ldloc.0
0x4c7aa  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x4c7af  stloc.1
0x4c7b0  ldloc.s  4
0x4c7b2  brtrue   loc_4C853
0x4c7b7  br       loc_4C864
0x4c7bc  ldloc.s  4
0x4c7be  brfalse.s loc_4C7F5
0x4c7c0  ldloc.s  0xB
0x4c7c2  ldstr    aInitialCatalog_0// "INITIAL CATALOG"
0x4c7c7  ldc.i4.4
0x4c7c8  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x4c7cd  brtrue.s loc_4C7DE
0x4c7cf  ldloc.s  0xB
0x4c7d1  ldstr    aDatabase_1// "DATABASE"
0x4c7d6  ldc.i4.4
0x4c7d7  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x4c7dc  brfalse.s loc_4C7F5
0x4c7de  ldc.i4.0
0x4c7df  stloc.s  4
0x4c7e1  ldarg.0
0x4c7e2  ldloc.s  0xA
0x4c7e4  ldstr    aDatabaseMaster// "Database=master"
0x4c7e9  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x4c7ee  starg.s  0
0x4c7f0  ldloc.3
0x4c7f1  brtrue.s loc_4C853
0x4c7f3  br.s     loc_4C864
0x4c7f5  ldloc.s  6
0x4c7f7  brfalse.s loc_4C83D
0x4c7f9  ldloc.s  0xB
0x4c7fb  ldstr    aUserInstance// "USER INSTANCE"
0x4c800  ldc.i4.4
0x4c801  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x4c806  brfalse.s loc_4C83D
0x4c808  ldc.i4.0
0x4c809  stloc.s  6
0x4c80b  ldloc.s  0xB
0x4c80d  ldc.i4.s 0x3D
0x4c80f  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x4c814  stloc.s  0xD
0x4c816  ldloc.s  0xD
0x4c818  ldc.i4.0
0x4c819  bge.s    loc_4C81C
0x4c81b  ret
0x4c81c  ldloc.s  0xB
0x4c81e  ldloc.s  0xD
0x4c820  ldc.i4.1
0x4c821  add
0x4c822  callvirt instance string [mscorlib]System.String::Substring(int32)
0x4c827  callvirt instance string [mscorlib]System.String::Trim()
0x4c82c  stloc.s  0xE
0x4c82e  ldloc.s  0xE
0x4c830  ldstr    aTrue_0// "TRUE"
0x4c835  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x4c83a  brfalse.s loc_4C853
0x4c83c  ret
0x4c83d  ldloc.s  7
0x4c83f  brfalse.s loc_4C853
0x4c841  ldloc.s  0xB
0x4c843  ldstr    aConnectTimeout// "CONNECT TIMEOUT"
0x4c848  ldc.i4.4
0x4c849  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x4c84e  brfalse.s loc_4C853
0x4c850  ldc.i4.0
0x4c851  stloc.s  7
0x4c853  ldloc.s  9
0x4c855  ldc.i4.1
0x4c856  add
0x4c857  stloc.s  9
0x4c859  ldloc.s  9
0x4c85b  ldloc.s  8
0x4c85d  ldlen
0x4c85e  conv.i4
0x4c85f  blt      loc_4C717
0x4c864  ldloc.s  6
0x4c866  brfalse.s loc_4C869
0x4c868  ret
0x4c869  ldloc.1
0x4c86a  brtrue.s loc_4C87C
0x4c86c  ldstr    aSqlexpressFile// "SqlExpress_file_not_found_in_connection"...
0x4c871  call     string System.Web.SR::GetString(string name)
0x4c876  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x4c87b  throw
0x4c87c  ldloc.1
0x4c87d  call     bool [mscorlib]System.IO.File::Exists(string)
0x4c882  brfalse.s loc_4C885
0x4c884  ret
0x4c885  ldc.i4   0x1F4
0x4c88a  call     bool System.Web.HttpRuntime::HasAspNetHostingPermission(valuetype [System]System.Web.AspNetHostingPermissionLevel level)
0x4c88f  brtrue.s loc_4C8A1
0x4c891  ldstr    aProviderCanNot// "Provider_can_not_create_file_in_this_tr"...
0x4c896  call     string System.Web.SR::GetString(string name)
0x4c89b  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x4c8a0  throw
0x4c8a1  ldarg.0
0x4c8a2  ldstr    aDatabaseMaster// "Database=master"
0x4c8a7  callvirt instance bool [mscorlib]System.String::Contains(string)
0x4c8ac  brtrue.s loc_4C8BB
0x4c8ae  ldarg.0
0x4c8af  ldstr    aDatabaseMaster_0// ";Database=master"
0x4c8b4  call     string [mscorlib]System.String::Concat(string, string)
0x4c8b9  starg.s  0
0x4c8bb  ldloc.s  7
0x4c8bd  brfalse.s loc_4C8CC
0x4c8bf  ldarg.0
0x4c8c0  ldstr    aConnectTimeout_0// ";Connect Timeout=45"
0x4c8c5  call     string [mscorlib]System.String::Concat(string, string)
0x4c8ca  starg.s  0
0x4c8cc  newobj   instance void System.Web.ApplicationImpersonationContext::.ctor()
0x4c8d1  stloc.s  0xF
0x4c8d3  ldsfld   object System.Web.DataAccess.SqlConnectionHelper::s_lock
0x4c8d8  stloc.s  0x10
0x4c8da  ldc.i4.0
0x4c8db  stloc.s  0x11
0x4c8dd  ldloc.s  0x10
0x4c8df  ldloca.s 0x11
0x4c8e1  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x4c8e6  ldloc.1
0x4c8e7  call     bool [mscorlib]System.IO.File::Exists(string)
0x4c8ec  brtrue.s loc_4C8F6
0x4c8ee  ldloc.1
0x4c8ef  ldloc.2
0x4c8f0  ldarg.0
0x4c8f1  call     void System.Web.DataAccess.SqlConnectionHelper::CreateMdfFile(string fullFileName, string dataDir, string connectionString)
0x4c8f6  leave.s  loc_4C910
0x4c8f8  ldloc.s  0x11
0x4c8fa  brfalse.s loc_4C903
0x4c8fc  ldloc.s  0x10
0x4c8fe  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x4c903  endfinally
0x4c904  ldloc.s  0xF
0x4c906  brfalse.s loc_4C90F
0x4c908  ldloc.s  0xF
0x4c90a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4c90f  endfinally
0x4c910  ret
```
