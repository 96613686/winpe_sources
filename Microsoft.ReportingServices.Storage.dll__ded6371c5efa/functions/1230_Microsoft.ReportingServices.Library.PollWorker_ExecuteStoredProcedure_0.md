# Microsoft.ReportingServices.Library.PollWorker::ExecuteStoredProcedure_0

- ea: `0x1230`
- end: `0x12db`
- name: `Microsoft.ReportingServices.Library.PollWorker::ExecuteStoredProcedure_0`
- size: `171`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1220`
- `0x2300`
- `0x2550`

## callees

- `0x10f0`
- `0x11f0`
- `0x1230`
- `0x30f0`
- `0x31b0`
- `0x32e0`
- `0x32f0`
- `0x70e0`
- `0x7320`

## pseudocode

```c

```

## disassembly

```asm
0x1230  ldc.i4.1
0x1231  ldc.i4   0x1000
0x1236  newobj   instance void Microsoft.ReportingServices.Library.ConnectionManager::.ctor(valuetype Microsoft.ReportingServices.Library.ConnectionTransactionType transactionType, valuetype [System.Data]System.Data.IsolationLevel defaultIsolationLevel)
0x123b  stloc.0
0x123c  ldloc.0
0x123d  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x1242  ldarg.0
0x1243  callvirt instance string Microsoft.ReportingServices.Library.PollWorker::get_PollCatalog()
0x1248  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x124d  brtrue.s loc_125B
0x124f  ldloc.0
0x1250  ldarg.0
0x1251  callvirt instance string Microsoft.ReportingServices.Library.PollWorker::get_PollCatalog()
0x1256  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::ChangeDatabase(string database)
0x125b  nop
0x125c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1261  ldstr    a0// "{0}"
0x1266  ldarg.1
0x1267  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x126c  starg.s  1
0x126e  ldarg.1
0x126f  ldloc.0
0x1270  call     class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.PollWorker::NewStandardSqlCommand(string storedProcedureName, class Microsoft.ReportingServices.Library.ConnectionManager connManager)
0x1275  stloc.1
0x1276  ldarg.2
0x1277  brfalse.s loc_12C0
0x1279  ldarg.2
0x127a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Keys()
0x127f  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, object>::GetEnumerator()
0x1284  stloc.2
0x1285  br.s     loc_12A7
0x1287  ldloca.s 2
0x1289  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, object>::get_Current()
0x128e  stloc.3
0x128f  ldarg.2
0x1290  ldloc.3
0x1291  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x1296  stloc.s  4
0x1298  ldloc.1
0x1299  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x129e  ldloc.3
0x129f  ldloc.s  4
0x12a1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x12a6  pop
0x12a7  ldloca.s 2
0x12a9  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, object>::MoveNext()
0x12ae  brtrue.s loc_1287
0x12b0  leave.s  loc_12C0
0x12b2  ldloca.s 2
0x12b4  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, object>
0x12ba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12bf  endfinally
0x12c0  ldloc.1
0x12c1  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x12c6  pop
0x12c7  leave.s  loc_12DA
0x12c9  ldloc.1
0x12ca  brfalse.s loc_12D2
0x12cc  ldloc.1
0x12cd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12d2  endfinally
0x12d3  ldloc.0
0x12d4  callvirt instance void Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x12d9  endfinally
0x12da  ret
```
