# Microsoft.ReportingServices.Library.QueuePollWorker::ResetItemRows

- ea: `0x1690`
- end: `0x176d`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::ResetItemRows`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1ea0`

## callees

- `0x1530`
- `0x1540`
- `0x1690`
- `0x17c0`
- `0x2020`

## string_xrefs

- `0x1746`: `\n                                                    Update \n                                                        [{0}] \n                                                    set \n                                                        [ProcessStart] = NULL,\n                                                        [ProcessHeartbeat] = NULL\n                                                    where \n                                                        [{1}] in ({2})`

## pseudocode

```c

```

## disassembly

```asm
0x1690  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1695  stloc.0
0x1696  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x169b  pop
0x169c  ldarg.0
0x169d  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x16a2  stloc.1
0x16a3  ldc.i4.0
0x16a4  stloc.2
0x16a5  ldloc.1
0x16a6  ldloca.s 2
0x16a8  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x16ad  ldarg.0
0x16ae  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x16b3  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x16b8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x16bd  stloc.3
0x16be  br.s     loc_1710
0x16c0  ldloc.3
0x16c1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x16c6  castclass Microsoft.ReportingServices.Library.QueueItem
0x16cb  stloc.s  4
0x16cd  ldloc.0
0x16ce  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x16d3  brfalse.s loc_16E1
0x16d5  ldloc.0
0x16d6  ldstr    asc_A654// ","
0x16db  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x16e0  pop
0x16e1  ldloc.0
0x16e2  ldc.i4.s 0x27
0x16e4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x16e9  pop
0x16ea  ldloc.0
0x16eb  ldloc.s  4
0x16ed  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.QueueItem::get_ID()
0x16f2  stloc.s  5
0x16f4  ldloca.s 5
0x16f6  constrained. [mscorlib]System.Guid
0x16fc  callvirt instance string [mscorlib]System.Object::ToString()
0x1701  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1706  pop
0x1707  ldloc.0
0x1708  ldc.i4.s 0x27
0x170a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x170f  pop
0x1710  ldloc.3
0x1711  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1716  brtrue.s loc_16C0
0x1718  leave.s  loc_1738
0x171a  ldloc.3
0x171b  isinst   [mscorlib]System.IDisposable
0x1720  stloc.s  6
0x1722  ldloc.s  6
0x1724  brfalse.s loc_172D
0x1726  ldloc.s  6
0x1728  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x172d  endfinally
0x172e  ldloc.2
0x172f  brfalse.s loc_1737
0x1731  ldloc.1
0x1732  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1737  endfinally
0x1738  ldloc.0
0x1739  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x173e  ldc.i4.0
0x173f  ble.s    loc_176C
0x1741  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1746  ldstr    aUpdate_0// "\r\n                                   "...
0x174b  ldarg.0
0x174c  callvirt instance string Microsoft.ReportingServices.Library.QueuePollWorker::get_QueueTableName()
0x1751  ldarg.0
0x1752  callvirt instance string Microsoft.ReportingServices.Library.QueuePollWorker::get_QueueIDColumnName()
0x1757  ldloc.0
0x1758  callvirt instance string [mscorlib]System.Object::ToString()
0x175d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x1762  stloc.s  7
0x1764  ldarg.0
0x1765  ldloc.s  7
0x1767  call     instance void Microsoft.ReportingServices.Library.QueuePollWorker::IssueTextQuey(string query)
0x176c  ret
```
