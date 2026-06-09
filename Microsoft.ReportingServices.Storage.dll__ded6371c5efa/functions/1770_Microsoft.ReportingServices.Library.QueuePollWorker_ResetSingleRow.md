# Microsoft.ReportingServices.Library.QueuePollWorker::ResetSingleRow

- ea: `0x1770`
- end: `0x17b7`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::ResetSingleRow`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1830`

## callees

- `0x1530`
- `0x1540`
- `0x17c0`
- `0x2020`

## string_xrefs

- `0x1775`: `\n                                                    Update \n                                                        [{0}] \n                                                    set \n                                                        [ProcessStart] = NULL,\n                                                        [ProcessHeartbeat] = NULL\n                                                    where \n                                                        [{1}] in ({2})`

## pseudocode

```c

```

## disassembly

```asm
0x1770  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1775  ldstr    aUpdate_0// "\r\n                                   "...
0x177a  ldarg.0
0x177b  callvirt instance string Microsoft.ReportingServices.Library.QueuePollWorker::get_QueueTableName()
0x1780  ldarg.0
0x1781  callvirt instance string Microsoft.ReportingServices.Library.QueuePollWorker::get_QueueIDColumnName()
0x1786  ldstr    asc_AD44// "'"
0x178b  ldarg.1
0x178c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.QueueItem::get_ID()
0x1791  stloc.1
0x1792  ldloca.s 1
0x1794  constrained. [mscorlib]System.Guid
0x179a  callvirt instance string [mscorlib]System.Object::ToString()
0x179f  ldstr    asc_AD44// "'"
0x17a4  call     string [mscorlib]System.String::Concat(string, string, string)
0x17a9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0x17ae  stloc.0
0x17af  ldarg.0
0x17b0  ldloc.0
0x17b1  call     instance void Microsoft.ReportingServices.Library.QueuePollWorker::IssueTextQuey(string query)
0x17b6  ret
```
