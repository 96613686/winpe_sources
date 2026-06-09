# Microsoft.ReportingServices.Library.CatalogQuery::ExecuteQuery

- ea: `0x20b0`
- end: `0x2188`
- name: `Microsoft.ReportingServices.Library.CatalogQuery::ExecuteQuery`
- size: `216`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x2090`
- `0x20a0`

## callees

- `0x20b0`
- `0x2190`
- `0x21b0`
- `0x2210`
- `0x2ff0`
- `0x70c0`
- `0x70e0`
- `0x7120`
- `0x7270`
- `0x72a0`
- `0x72f0`
- `0x7310`
- `0x7320`

## pseudocode

```c

```

## disassembly

```asm
0x20b0  ldarg.1
0x20b1  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string)
0x20b6  call     class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand command)
0x20bb  stloc.0
0x20bc  ldloc.0
0x20bd  ldarg.0
0x20be  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.CatalogQuery::get_Connection()
0x20c3  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_Connection(class [System.Data]System.Data.IDbConnection value)
0x20c8  ldloc.0
0x20c9  ldarg.0
0x20ca  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.CatalogQuery::get_Transaction()
0x20cf  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_Transaction(class [System.Data]System.Data.IDbTransaction value)
0x20d4  ldloc.0
0x20d5  ldarg.3
0x20d6  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType value)
0x20db  ldloc.0
0x20dc  call     int32 Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCommandTimeoutSeconds()
0x20e1  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32 value)
0x20e6  ldarg.2
0x20e7  brfalse.s loc_2157
0x20e9  ldarg.2
0x20ea  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0x20ef  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x20f4  stloc.2
0x20f5  br.s     loc_2139
0x20f7  ldloc.2
0x20f8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x20fd  castclass [mscorlib]System.String
0x2102  stloc.3
0x2103  ldarg.2
0x2104  ldloc.3
0x2105  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x210a  stloc.s  4
0x210c  ldloc.s  4
0x210e  isinst   [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter
0x2113  brfalse.s loc_212A
0x2115  ldloc.0
0x2116  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x211b  ldloc.s  4
0x211d  castclass [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter
0x2122  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x2127  pop
0x2128  br.s     loc_2139
0x212a  ldloc.0
0x212b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x2130  ldloc.3
0x2131  ldloc.s  4
0x2133  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2138  pop
0x2139  ldloc.2
0x213a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x213f  brtrue.s loc_20F7
0x2141  leave.s  loc_2157
0x2143  ldloc.2
0x2144  isinst   [mscorlib]System.IDisposable
0x2149  stloc.s  5
0x214b  ldloc.s  5
0x214d  brfalse.s loc_2156
0x214f  ldloc.s  5
0x2151  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2156  endfinally
0x2157  ldnull
0x2158  stloc.1
0x2159  ldarg.s  4
0x215b  brfalse.s loc_2166
0x215d  ldloc.0
0x215e  callvirt instance class [System.Data]System.Data.IDataReader Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x2163  stloc.1
0x2164  br.s     loc_216D
0x2166  ldloc.0
0x2167  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x216c  pop
0x216d  ldloc.1
0x216e  stloc.s  6
0x2170  leave.s  loc_2185
0x2172  ldloc.0
0x2173  brfalse.s loc_217B
0x2175  ldloc.0
0x2176  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x217b  endfinally
0x217c  pop
0x217d  ldarg.0
0x217e  call     instance void Microsoft.ReportingServices.Library.CatalogQuery::AbortTransaction()
0x2183  rethrow
0x2185  ldloc.s  6
0x2187  ret
```
