# Microsoft.ReportingServices.Library.QueuePollWorker::get_Poll

- ea: `0x1a50`
- end: `0x1c25`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::get_Poll`
- size: `469`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1a50`
- `0x1c80`

## pseudocode

```c

```

## disassembly

```asm
0x1a50  ldarg.0
0x1a51  ldfld    bool Microsoft.ReportingServices.Library.QueuePollWorker::m_workLastPoll
0x1a56  brtrue.s loc_1AA9
0x1a58  ldarg.0
0x1a59  ldfld    bool Microsoft.ReportingServices.Library.QueuePollWorker::m_knownQueueItemInDatabase
0x1a5e  brtrue.s loc_1AA9
0x1a60  ldarg.0
0x1a61  ldfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.QueuePollWorker::m_lastEmptyPoll
0x1a66  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x1a6b  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1a70  brfalse.s loc_1A74
0x1a72  ldc.i4.1
0x1a73  ret
0x1a74  ldarg.0
0x1a75  ldfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.QueuePollWorker::m_lastEmptyPoll
0x1a7a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1a7f  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1a84  brfalse.s loc_1A88
0x1a86  ldc.i4.1
0x1a87  ret
0x1a88  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1a8d  ldarg.0
0x1a8e  ldfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.QueuePollWorker::m_lastEmptyPoll
0x1a93  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1a98  ldarg.0
0x1a99  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.QueuePollWorker::m_pollInterval
0x1a9e  call     bool [mscorlib]System.TimeSpan::op_GreaterThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x1aa3  brfalse.s loc_1AA7
0x1aa5  ldc.i4.1
0x1aa6  ret
0x1aa7  ldc.i4.0
0x1aa8  ret
0x1aa9  ldc.i4.1
0x1aaa  stloc.0
0x1aab  ldarg.0
0x1aac  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x1ab1  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x1ab6  brfalse  loc_1C1C
0x1abb  ldarg.0
0x1abc  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x1ac1  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x1ac6  ldarg.0
0x1ac7  ldfld    int32 Microsoft.ReportingServices.Library.QueuePollWorker::m_maxItems
0x1acc  blt      loc_1BDF
0x1ad1  ldc.i4.0
0x1ad2  stloc.0
0x1ad3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1ad8  ldarg.0
0x1ad9  ldfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.QueuePollWorker::m_lastPoll
0x1ade  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1ae3  ldarg.0
0x1ae4  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.QueuePollWorker::m_fullQueueStateInterval
0x1ae9  call     bool [mscorlib]System.TimeSpan::op_GreaterThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x1aee  brfalse  loc_1C1C
0x1af3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1af8  ldsfld   valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.QueuePollWorker::m_lastFullQueueWarning
0x1afd  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1b02  ldarg.0
0x1b03  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.QueuePollWorker::m_fullQueueTraceInterval
0x1b08  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x1b0d  brfalse  loc_1C1C
0x1b12  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1b17  stloc.1
0x1b18  ldc.i4.0
0x1b19  stloc.2
0x1b1a  ldarg.0
0x1b1b  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.QueuePollWorker::m_currentItems
0x1b20  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x1b25  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x1b2a  stloc.3
0x1b2b  br.s     loc_1B5C
0x1b2d  ldloc.3
0x1b2e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1b33  castclass Microsoft.ReportingServices.Library.QueueItem
0x1b38  stloc.s  4
0x1b3a  ldloc.1
0x1b3b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b40  ldstr    a01_0// "\r\n\t#{0}, {1}"
0x1b45  ldloc.2
0x1b46  dup
0x1b47  ldc.i4.1
0x1b48  add
0x1b49  stloc.2
0x1b4a  box      [mscorlib]System.Int32
0x1b4f  ldloc.s  4
0x1b51  callvirt instance string [mscorlib]System.Object::ToString()
0x1b56  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object, object)
0x1b5b  pop
0x1b5c  ldloc.3
0x1b5d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b62  brtrue.s loc_1B2D
0x1b64  leave.s  loc_1B7A
0x1b66  ldloc.3
0x1b67  isinst   [mscorlib]System.IDisposable
0x1b6c  stloc.s  5
0x1b6e  ldloc.s  5
0x1b70  brfalse.s loc_1B79
0x1b72  ldloc.s  5
0x1b74  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b79  endfinally
0x1b7a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DbPollingTracer()
0x1b7f  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x1b84  brfalse.s loc_1BAC
0x1b86  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_DbPollingTracer()
0x1b8b  ldc.i4.2
0x1b8c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b91  ldstr    aSchedulesEvent// "Schedules, events, and subscriptions pr"...
0x1b96  ldarg.0
0x1b97  ldfld    int32 Microsoft.ReportingServices.Library.QueuePollWorker::m_maxItems
0x1b9c  box      [mscorlib]System.Int32
0x1ba1  ldloc.1
0x1ba2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x1ba7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x1bac  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x1bb1  ldc.i4   0x8E
0x1bb6  ldc.i4.2
0x1bb7  newarr   [mscorlib]System.Object
0x1bbc  dup
0x1bbd  ldc.i4.0
0x1bbe  ldarg.0
0x1bbf  ldfld    int32 Microsoft.ReportingServices.Library.QueuePollWorker::m_maxItems
0x1bc4  box      [mscorlib]System.Int32
0x1bc9  stelem.ref
0x1bca  dup
0x1bcb  ldc.i4.1
0x1bcc  ldloc.1
0x1bcd  stelem.ref
0x1bce  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteWarning(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Event, object[])
0x1bd3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1bd8  stsfld   valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.QueuePollWorker::m_lastFullQueueWarning
0x1bdd  br.s     loc_1C1C
0x1bdf  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1be4  ldarg.0
0x1be5  ldfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.QueuePollWorker::m_lastPoll
0x1bea  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1bef  brfalse.s loc_1C12
0x1bf1  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x1bf6  ldarg.0
0x1bf7  ldfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.QueuePollWorker::m_lastPoll
0x1bfc  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1c01  ldarg.0
0x1c02  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.QueuePollWorker::m_successInterval
0x1c07  call     bool [mscorlib]System.TimeSpan::op_LessThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x1c0c  brfalse.s loc_1C12
0x1c0e  ldc.i4.0
0x1c0f  stloc.0
0x1c10  br.s     loc_1C1C
0x1c12  ldarg.0
0x1c13  call     instance bool Microsoft.ReportingServices.Library.QueuePollWorker::ProcessPressureReached()
0x1c18  ldc.i4.0
0x1c19  ceq
0x1c1b  stloc.0
0x1c1c  ldarg.0
0x1c1d  ldc.i4.0
0x1c1e  stfld    bool Microsoft.ReportingServices.Library.QueuePollWorker::m_knownQueueItemInDatabase
0x1c23  ldloc.0
0x1c24  ret
```
