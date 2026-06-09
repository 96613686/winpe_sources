# Microsoft.ReportingServices.DataExtensions.CommandWrapper::GetStoredProcedureParameters_0

- ea: `0x2c90`
- end: `0x2f4c`
- name: `Microsoft.ReportingServices.DataExtensions.CommandWrapper::GetStoredProcedureParameters_0`
- size: `700`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x2c80`

## callees

- `0x2c90`
- `0x30e0`

## string_xrefs

- `0x2da2`: `Oracle.ManagedDataAccess.Client.OracleCommand`
- `0x2dc5`: `Oracle.ManagedDataAccess.Client.OracleCommandBuilder`
- `0x2e76`: `OracleDbType`

## pseudocode

```c

```

## disassembly

```asm
0x2c90  ldarg.1
0x2c91  ldnull
0x2c92  stind.ref
0x2c93  ldarg.0
0x2c94  call     instance class [System.Data]System.Data.IDbCommand Microsoft.ReportingServices.DataExtensions.CommandWrapper::get_UnderlyingCommand()
0x2c99  stloc.0
0x2c9a  ldc.i4.4
0x2c9b  ldloc.0
0x2c9c  callvirt instance valuetype [System.Data]System.Data.CommandType [System.Data]System.Data.IDbCommand::get_CommandType()
0x2ca1  beq.s    loc_2CA5
0x2ca3  ldnull
0x2ca4  ret
0x2ca5  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x2caa  stloc.1
0x2cab  ldloc.0
0x2cac  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2cb1  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x2cb6  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(int32)
0x2cbb  stloc.2
0x2cbc  ldloc.0
0x2cbd  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2cc2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x2cc7  stloc.s  5
0x2cc9  br.s     loc_2CE2
0x2ccb  ldloc.s  5
0x2ccd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2cd2  castclass [System.Data]System.Data.IDataParameter
0x2cd7  stloc.s  6
0x2cd9  ldloc.2
0x2cda  ldloc.s  6
0x2cdc  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x2ce1  pop
0x2ce2  ldloc.s  5
0x2ce4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2ce9  brtrue.s loc_2CCB
0x2ceb  leave.s  loc_2D02
0x2ced  ldloc.s  5
0x2cef  isinst   [mscorlib]System.IDisposable
0x2cf4  stloc.s  7
0x2cf6  ldloc.s  7
0x2cf8  brfalse.s loc_2D01
0x2cfa  ldloc.s  7
0x2cfc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2d01  endfinally
0x2d02  ldloc.0
0x2d03  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2d08  callvirt instance void [mscorlib]System.Collections.IList::Clear()
0x2d0d  ldloc.0
0x2d0e  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x2d13  stloc.3
0x2d14  ldloc.3
0x2d15  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2d1a  ldc.i4.2
0x2d1b  blt.s    loc_2D4F
0x2d1d  ldloc.3
0x2d1e  ldc.i4.0
0x2d1f  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2d24  ldc.i4.s 0x5B
0x2d26  bne.un.s loc_2D4F
0x2d28  ldloc.3
0x2d29  ldloc.3
0x2d2a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2d2f  ldc.i4.1
0x2d30  sub
0x2d31  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2d36  ldc.i4.s 0x5D
0x2d38  bne.un.s loc_2D4F
0x2d3a  ldloc.0
0x2d3b  ldloc.3
0x2d3c  ldc.i4.1
0x2d3d  ldloc.3
0x2d3e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2d43  ldc.i4.2
0x2d44  sub
0x2d45  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2d4a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2d4f  ldc.i4.0
0x2d50  stloc.s  4
0x2d52  ldloc.0
0x2d53  isinst   [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand
0x2d58  brfalse.s loc_2D6A
0x2d5a  ldloc.0
0x2d5b  castclass [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand
0x2d60  call     void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommandBuilder::DeriveParameters(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand)
0x2d65  br       loc_2E0D
0x2d6a  ldloc.0
0x2d6b  isinst   [System.Data]System.Data.OleDb.OleDbCommand
0x2d70  brfalse.s loc_2D82
0x2d72  ldloc.0
0x2d73  castclass [System.Data]System.Data.OleDb.OleDbCommand
0x2d78  call     void [System.Data]System.Data.OleDb.OleDbCommandBuilder::DeriveParameters(class [System.Data]System.Data.OleDb.OleDbCommand)
0x2d7d  br       loc_2E0D
0x2d82  ldloc.0
0x2d83  isinst   [System.Data]System.Data.Odbc.OdbcCommand
0x2d88  brfalse.s loc_2D97
0x2d8a  ldloc.0
0x2d8b  castclass [System.Data]System.Data.Odbc.OdbcCommand
0x2d90  call     void [System.Data]System.Data.Odbc.OdbcCommandBuilder::DeriveParameters(class [System.Data]System.Data.Odbc.OdbcCommand)
0x2d95  br.s     loc_2E0D
0x2d97  ldloc.0
0x2d98  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2d9d  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2da2  ldstr    aOracleManagedd// "Oracle.ManagedDataAccess.Client.OracleC"...
0x2da7  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2dac  brfalse.s loc_2DF0
0x2dae  ldc.i4.1
0x2daf  newarr   [mscorlib]System.Object
0x2db4  dup
0x2db5  ldc.i4.0
0x2db6  ldloc.0
0x2db7  stelem.ref
0x2db8  stloc.s  8
0x2dba  ldloc.0
0x2dbb  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2dc0  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x2dc5  ldstr    aOracleManagedd_0// "Oracle.ManagedDataAccess.Client.OracleC"...
0x2dca  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x2dcf  ldstr    aDeriveparamete// "DeriveParameters"
0x2dd4  ldc.i4.s 0x18
0x2dd6  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string, valuetype [mscorlib]System.Reflection.BindingFlags)
0x2ddb  ldnull
0x2ddc  ldloc.s  8
0x2dde  callvirt instance object [mscorlib]System.Reflection.MethodBase::Invoke(object, object[])
0x2de3  pop
0x2de4  ldarg.1
0x2de5  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x2dea  stind.ref
0x2deb  ldc.i4.1
0x2dec  stloc.s  4
0x2dee  br.s     loc_2E0D
0x2df0  ldloc.0
0x2df1  isinst   [System.Data.OracleClient]System.Data.OracleClient.OracleCommand
0x2df6  brfalse.s loc_2E0D
0x2df8  ldloc.0
0x2df9  castclass [System.Data.OracleClient]System.Data.OracleClient.OracleCommand
0x2dfe  call     void [System.Data.OracleClient]System.Data.OracleClient.OracleCommandBuilder::DeriveParameters(class [System.Data.OracleClient]System.Data.OracleClient.OracleCommand)
0x2e03  ldarg.1
0x2e04  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x2e09  stind.ref
0x2e0a  ldc.i4.1
0x2e0b  stloc.s  4
0x2e0d  ldloc.0
0x2e0e  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x2e13  ldloc.3
0x2e14  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2e19  brfalse.s loc_2E22
0x2e1b  ldloc.0
0x2e1c  ldloc.3
0x2e1d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2e22  ldloc.0
0x2e23  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2e28  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x2e2d  stloc.s  5
0x2e2f  br       loc_2ED6
0x2e34  ldloc.s  5
0x2e36  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2e3b  castclass [System.Data]System.Data.IDataParameter
0x2e40  stloc.s  9
0x2e42  ldc.i4.0
0x2e43  stloc.s  0xA
0x2e45  ldloc.0
0x2e46  isinst   [System.Data.OracleClient]System.Data.OracleClient.OracleCommand
0x2e4b  brfalse.s loc_2E67
0x2e4d  ldloc.s  4
0x2e4f  brfalse.s loc_2E62
0x2e51  ldloc.s  9
0x2e53  castclass [System.Data.OracleClient]System.Data.OracleClient.OracleParameter
0x2e58  callvirt instance valuetype [System.Data.OracleClient]System.Data.OracleClient.OracleType [System.Data.OracleClient]System.Data.OracleClient.OracleParameter::get_OracleType()
0x2e5d  ldc.i4.5
0x2e5e  ceq
0x2e60  br.s     loc_2E63
0x2e62  ldc.i4.0
0x2e63  stloc.s  0xA
0x2e65  br.s     loc_2E93
0x2e67  ldc.i4.s 0x79
0x2e69  stloc.s  0xB
0x2e6b  ldloc.s  4
0x2e6d  brfalse.s loc_2E93
0x2e6f  ldloc.s  9
0x2e71  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2e76  ldstr    aOracledbtype// "OracleDbType"
0x2e7b  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x2e80  ldloc.s  9
0x2e82  ldnull
0x2e83  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x2e88  unbox.any [mscorlib]System.Int32
0x2e8d  ldloc.s  0xB
0x2e8f  ceq
0x2e91  stloc.s  0xA
0x2e93  ldloc.s  0xA
0x2e95  brtrue.s loc_2EB6
0x2e97  ldloc.s  9
0x2e99  callvirt instance valuetype [System.Data]System.Data.ParameterDirection [System.Data]System.Data.IDataParameter::get_Direction()
0x2e9e  ldc.i4.1
0x2e9f  beq.s    loc_2EAB
0x2ea1  ldloc.s  9
0x2ea3  callvirt instance valuetype [System.Data]System.Data.ParameterDirection [System.Data]System.Data.IDataParameter::get_Direction()
0x2ea8  ldc.i4.3
0x2ea9  bne.un.s loc_2EB6
0x2eab  ldloc.1
0x2eac  ldloc.s  9
0x2eae  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x2eb3  pop
0x2eb4  br.s     loc_2ED6
0x2eb6  ldloc.s  0xA
0x2eb8  brfalse.s loc_2ED6
0x2eba  ldloc.s  9
0x2ebc  callvirt instance valuetype [System.Data]System.Data.ParameterDirection [System.Data]System.Data.IDataParameter::get_Direction()
0x2ec1  ldc.i4.3
0x2ec2  bne.un.s loc_2ECC
0x2ec4  ldloc.s  9
0x2ec6  ldc.i4.2
0x2ec7  callvirt instance void [System.Data]System.Data.IDataParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x2ecc  ldarg.1
0x2ecd  ldind.ref
0x2ece  ldloc.s  9
0x2ed0  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x2ed5  pop
0x2ed6  ldloc.s  5
0x2ed8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2edd  brtrue   loc_2E34
0x2ee2  leave.s  loc_2EF9
0x2ee4  ldloc.s  5
0x2ee6  isinst   [mscorlib]System.IDisposable
0x2eeb  stloc.s  7
0x2eed  ldloc.s  7
0x2eef  brfalse.s loc_2EF8
0x2ef1  ldloc.s  7
0x2ef3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ef8  endfinally
0x2ef9  ldloc.0
0x2efa  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2eff  callvirt instance void [mscorlib]System.Collections.IList::Clear()
0x2f04  ldloc.2
0x2f05  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x2f0a  stloc.s  5
0x2f0c  br.s     loc_2F2A
0x2f0e  ldloc.s  5
0x2f10  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2f15  castclass [System.Data]System.Data.IDataParameter
0x2f1a  stloc.s  0xC
0x2f1c  ldloc.0
0x2f1d  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2f22  ldloc.s  0xC
0x2f24  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x2f29  pop
0x2f2a  ldloc.s  5
0x2f2c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2f31  brtrue.s loc_2F0E
0x2f33  leave.s  loc_2F4A
0x2f35  ldloc.s  5
0x2f37  isinst   [mscorlib]System.IDisposable
0x2f3c  stloc.s  7
0x2f3e  ldloc.s  7
0x2f40  brfalse.s loc_2F49
0x2f42  ldloc.s  7
0x2f44  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f49  endfinally
0x2f4a  ldloc.1
0x2f4b  ret
```
