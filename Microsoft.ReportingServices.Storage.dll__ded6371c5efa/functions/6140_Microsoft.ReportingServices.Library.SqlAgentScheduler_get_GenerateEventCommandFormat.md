# Microsoft.ReportingServices.Library.SqlAgentScheduler::get_GenerateEventCommandFormat

- ea: `0x6140`
- end: `0x6194`
- name: `Microsoft.ReportingServices.Library.SqlAgentScheduler::get_GenerateEventCommandFormat`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x63e0`

## callees

- `0x3650`
- `0x6140`
- `0x6a70`
- `0x6a80`

## pseudocode

```c

```

## disassembly

```asm
0x6140  ldarg.0
0x6141  stloc.0
0x6142  ldc.i4.0
0x6143  stloc.1
0x6144  ldloc.0
0x6145  ldloca.s 1
0x6147  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x614c  ldarg.0
0x614d  ldfld    string Microsoft.ReportingServices.Library.SqlAgentScheduler::m_eventCommandFormat
0x6152  brtrue.s loc_617F
0x6154  ldarg.0
0x6155  ldstr    aExec// "exec "
0x615a  ldarg.0
0x615b  callvirt instance class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x6160  ldarg.0
0x6161  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection Microsoft.ReportingServices.Library.Storage::get_Connection()
0x6166  callvirt instance string [System.Data]System.Data.Common.DbConnection::get_Database()
0x616b  callvirt instance string Microsoft.ReportingServices.Library.ConnectionManager::EscapeAndBracketDBName(string dbName)
0x6170  ldstr    aDboAddeventEve// ".dbo.AddEvent @EventType='{0}', @EventD"...
0x6175  call     string [mscorlib]System.String::Concat(string, string, string)
0x617a  stfld    string Microsoft.ReportingServices.Library.SqlAgentScheduler::m_eventCommandFormat
0x617f  ldarg.0
0x6180  ldfld    string Microsoft.ReportingServices.Library.SqlAgentScheduler::m_eventCommandFormat
0x6185  stloc.2
0x6186  leave.s  loc_6192
0x6188  ldloc.1
0x6189  brfalse.s loc_6191
0x618b  ldloc.0
0x618c  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x6191  endfinally
0x6192  ldloc.2
0x6193  ret
```
