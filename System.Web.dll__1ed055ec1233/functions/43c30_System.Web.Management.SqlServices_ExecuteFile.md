# System.Web.Management.SqlServices::ExecuteFile

- ea: `0x43c30`
- end: `0x43da1`
- name: `System.Web.Management.SqlServices::ExecuteFile`
- size: `369`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x43c10`
- `0x43f80`

## callees

- `0x24460`
- `0x34f20`
- `0x34fa0`
- `0x43650`
- `0x43a00`
- `0x43c30`
- `0x58d50`

## string_xrefs

- `0x43d12`: `sp_delete_job`
- `0x43d2f`: `SQL_Services_Error_Deleting_Session_Job`
- `0x43d50`: `SQL_Services_Error_Executing_Command`

## pseudocode

```c

```

## disassembly

```asm
0x43c30  call     string System.Web.HttpRuntime::get_AspInstallDirectory()
0x43c35  ldarg.0
0x43c36  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x43c3b  stloc.0
0x43c3c  ldloc.0
0x43c3d  call     string [mscorlib]System.IO.File::ReadAllText(string)
0x43c42  stloc.1
0x43c43  ldnull
0x43c44  stloc.3
0x43c45  ldarg.0
0x43c46  ldsfld   string System.Web.Management.SqlServices::INSTALL_COMMON_SQL
0x43c4b  callvirt instance bool [mscorlib]System.String::Equals(string)
0x43c50  brfalse.s loc_43C61
0x43c52  ldloc.1
0x43c53  ldarg.2
0x43c54  ldarg.3
0x43c55  ldarg.s  5
0x43c57  ldarg.s  7
0x43c59  call     string System.Web.Management.SqlServices::FixContent(string content, string database, string dbFileName, bool sessionState, valuetype System.Web.Management.SessionStateType sessionStatetype)
0x43c5e  stloc.1
0x43c5f  br.s     loc_43C6E
0x43c61  ldloc.1
0x43c62  ldarg.2
0x43c63  ldnull
0x43c64  ldarg.s  5
0x43c66  ldarg.s  7
0x43c68  call     string System.Web.Management.SqlServices::FixContent(string content, string database, string dbFileName, bool sessionState, valuetype System.Web.Management.SessionStateType sessionStatetype)
0x43c6d  stloc.1
0x43c6e  ldloc.1
0x43c6f  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x43c74  stloc.2
0x43c75  ldnull
0x43c76  ldarg.s  4
0x43c78  newobj   instance void [System.Data]System.Data.SqlClient.SqlCommand::.ctor(string, class [System.Data]System.Data.SqlClient.SqlConnection)
0x43c7d  stloc.s  5
0x43c7f  ldc.i4.0
0x43c80  stloc.s  6
0x43c82  ldloc.2
0x43c83  callvirt instance string [mscorlib]System.IO.TextReader::ReadLine()
0x43c88  stloc.s  4
0x43c8a  ldloc.s  4
0x43c8c  brtrue.s loc_43C93
0x43c8e  ldc.i4.1
0x43c8f  stloc.s  6
0x43c91  br.s     loc_43CC3
0x43c93  ldloc.s  4
0x43c95  callvirt instance string [mscorlib]System.String::Trim()
0x43c9a  ldstr    aGo// "GO"
0x43c9f  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x43ca4  brfalse.s loc_43CAB
0x43ca6  ldc.i4.1
0x43ca7  stloc.s  6
0x43ca9  br.s     loc_43CC3
0x43cab  ldloc.3
0x43cac  brfalse.s loc_43CBA
0x43cae  ldloc.3
0x43caf  ldstr    asc_1BD14C// "\n"
0x43cb4  call     string [mscorlib]System.String::Concat(string, string)
0x43cb9  stloc.3
0x43cba  ldloc.3
0x43cbb  ldloc.s  4
0x43cbd  call     string [mscorlib]System.String::Concat(string, string)
0x43cc2  stloc.3
0x43cc3  ldloc.s  6
0x43cc5  ldloc.3
0x43cc6  ldnull
0x43cc7  cgt.un
0x43cc9  and
0x43cca  brfalse  loc_43D99
0x43ccf  ldloc.s  5
0x43cd1  ldloc.3
0x43cd2  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x43cd7  ldloc.s  5
0x43cd9  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x43cde  pop
0x43cdf  leave    loc_43D97
0x43ce4  stloc.s  7
0x43ce6  ldloc.s  7
0x43ce8  isinst   [System.Data]System.Data.SqlClient.SqlException
0x43ced  stloc.s  8
0x43cef  ldloc.s  8
0x43cf1  brfalse  loc_43D92
0x43cf6  ldc.i4.m1
0x43cf7  stloc.s  9
0x43cf9  ldloc.3
0x43cfa  ldstr    aSpAddCategory// "sp_add_category"
0x43cff  ldc.i4.4
0x43d00  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x43d05  ldc.i4.m1
0x43d06  ble.s    loc_43D11
0x43d08  ldc.i4   0x37B5
0x43d0d  stloc.s  9
0x43d0f  br.s     loc_43D45
0x43d11  ldloc.3
0x43d12  ldstr    aSpDeleteJob// "sp_delete_job"
0x43d17  ldc.i4.4
0x43d18  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x43d1d  ldc.i4.m1
0x43d1e  ble.s    loc_43D45
0x43d20  ldc.i4   0x37B6
0x43d25  stloc.s  9
0x43d27  ldarg.s  5
0x43d29  brfalse.s loc_43D45
0x43d2b  ldarg.s  6
0x43d2d  brtrue.s loc_43D45
0x43d2f  ldstr    aSqlServicesErr// "SQL_Services_Error_Deleting_Session_Job"
0x43d34  call     string System.Web.SR::GetString(string name)
0x43d39  ldarg.1
0x43d3a  ldarg.2
0x43d3b  ldarg.0
0x43d3c  ldloc.3
0x43d3d  ldloc.s  8
0x43d3f  newobj   instance void System.Web.Management.SqlExecutionException::.ctor(string message, string server, string database, string sqlFile, string commands, class [System.Data]System.Data.SqlClient.SqlException sqlException)
0x43d44  throw
0x43d45  ldloc.s  8
0x43d47  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x43d4c  ldloc.s  9
0x43d4e  beq.s    loc_43D92
0x43d50  ldstr    aSqlServicesErr_0// "SQL_Services_Error_Executing_Command"
0x43d55  ldc.i4.3
0x43d56  newarr   [mscorlib]System.Object
0x43d5b  dup
0x43d5c  ldc.i4.0
0x43d5d  ldarg.0
0x43d5e  stelem.ref
0x43d5f  dup
0x43d60  ldc.i4.1
0x43d61  ldloc.s  8
0x43d63  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x43d68  stloc.s  0xA
0x43d6a  ldloca.s 0xA
0x43d6c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x43d71  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x43d76  stelem.ref
0x43d77  dup
0x43d78  ldc.i4.2
0x43d79  ldloc.s  8
0x43d7b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x43d80  stelem.ref
0x43d81  call     string System.Web.SR::GetString(string name, object[] args)
0x43d86  ldarg.1
0x43d87  ldarg.2
0x43d88  ldarg.0
0x43d89  ldloc.3
0x43d8a  ldloc.s  8
0x43d8c  newobj   instance void System.Web.Management.SqlExecutionException::.ctor(string message, string server, string database, string sqlFile, string commands, class [System.Data]System.Data.SqlClient.SqlException sqlException)
0x43d91  throw
0x43d92  leave.s  loc_43D97
0x43d94  pop
0x43d95  rethrow
0x43d97  ldnull
0x43d98  stloc.3
0x43d99  ldloc.s  4
0x43d9b  brtrue   loc_43C7F
0x43da0  ret
```
