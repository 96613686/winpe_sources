# Microsoft.ReportingServices.Library.QueuePollWorker::SetHeartbeat

- ea: `0x1590`
- end: `0x168b`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::SetHeartbeat`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1e10`

## callees

- `0x13e0`
- `0x1530`
- `0x1540`
- `0x1590`
- `0x17c0`
- `0x2020`
- `0x2040`

## string_xrefs

- `0x1664`: `\n                                                    Update \n                                                        [{0}] \n                                                    set \n                                                        [ProcessHeartbeat] = GETUTCDATE()\n                                                    where \n                                                        [{1}] in ({2})`

## pseudocode

```c

```

## disassembly

```asm
0x1590  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1595  stloc.0
0x1596  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x159b  stloc.1
0x159c  ldarg.0
0x159d  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x15a2  stloc.2
0x15a3  ldc.i4.0
0x15a4  stloc.3
0x15a5  ldloc.2
0x15a6  ldloca.s 3
0x15a8  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x15ad  ldarg.0
0x15ae  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x15b3  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x15b8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x15bd  stloc.s  4
0x15bf  br.s     loc_162C
0x15c1  ldloc.s  4
0x15c3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x15c8  castclass Microsoft.ReportingServices.Library.QueueItem
0x15cd  stloc.s  5
0x15cf  ldloc.1
0x15d0  ldloc.s  5
0x15d2  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.QueueItem::get_TimeEntered()
0x15d7  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x15dc  ldarg.0
0x15dd  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.QueuePollWorker::get_HeartbeatInterval()
0x15e2  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x15e7  brfalse.s loc_162C
0x15e9  ldloc.0
0x15ea  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x15ef  brfalse.s loc_15FD
0x15f1  ldloc.0
0x15f2  ldstr    asc_A654// ","
0x15f7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x15fc  pop
0x15fd  ldloc.0
0x15fe  ldc.i4.s 0x27
0x1600  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x1605  pop
0x1606  ldloc.0
0x1607  ldloc.s  5
0x1609  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.QueueItem::get_ID()
0x160e  stloc.s  6
0x1610  ldloca.s 6
0x1612  constrained. [mscorlib]System.Guid
0x1618  callvirt instance string [mscorlib]System.Object::ToString()
0x161d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1622  pop
0x1623  ldloc.0
0x1624  ldc.i4.s 0x27
0x1626  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x162b  pop
0x162c  ldloc.s  4
0x162e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1633  brtrue.s loc_15C1
0x1635  leave.s  loc_1656
0x1637  ldloc.s  4
0x1639  isinst   [mscorlib]System.IDisposable
0x163e  stloc.s  7
0x1640  ldloc.s  7
0x1642  brfalse.s loc_164B
0x1644  ldloc.s  7
0x1646  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x164b  endfinally
0x164c  ldloc.3
0x164d  brfalse.s loc_1655
0x164f  ldloc.2
0x1650  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1655  endfinally
0x1656  ldloc.0
0x1657  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x165c  ldc.i4.0
0x165d  ble.s    loc_168A
0x165f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1664  ldstr    aUpdate// "\r\n                                   "...
0x1669  ldarg.0
0x166a  callvirt instance string Microsoft.ReportingServices.Library.QueuePollWorker::get_QueueTableName()
0x166f  ldarg.0
0x1670  callvirt instance string Microsoft.ReportingServices.Library.QueuePollWorker::get_QueueIDColumnName()
0x1675  ldloc.0
0x1676  callvirt instance string [mscorlib]System.Object::ToString()
0x167b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x1680  stloc.s  8
0x1682  ldarg.0
0x1683  ldloc.s  8
0x1685  call     instance void Microsoft.ReportingServices.Library.QueuePollWorker::IssueTextQuey(string query)
0x168a  ret
```
