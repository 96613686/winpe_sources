# Microsoft.ReportingServices.Library.QueuePollWorker::WorkItemStart

- ea: `0x1830`
- end: `0x19ad`
- name: `Microsoft.ReportingServices.Library.QueuePollWorker::WorkItemStart`
- size: `381`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0xca0`
- `0xcb0`
- `0xe20`
- `0x10e0`
- `0x1130`
- `0x14f0`
- `0x1570`
- `0x1580`
- `0x1770`
- `0x1830`
- `0x1d50`
- `0x2020`

## string_xrefs

- `0x198b`: `Queue worker thread caught unhandled exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1830  call     void Microsoft.ReportingServices.Library.DBPoll::PollItemStart()
0x1835  ldc.i4.0
0x1836  stloc.0
0x1837  ldarg.1
0x1838  castclass Microsoft.ReportingServices.Library.QueueItem
0x183d  stloc.1
0x183e  ldarg.0
0x183f  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x1844  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x1849  brfalse.s loc_1878
0x184b  ldarg.0
0x184c  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x1851  ldstr    a0ProcessingIte// "{0} processing item {1}"
0x1856  ldc.i4.2
0x1857  newarr   [mscorlib]System.Object
0x185c  dup
0x185d  ldc.i4.0
0x185e  ldarg.0
0x185f  callvirt instance string Microsoft.ReportingServices.Library.PollWorker::get_PollingTraceName()
0x1864  stelem.ref
0x1865  dup
0x1866  ldc.i4.1
0x1867  ldloc.1
0x1868  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.QueueItem::get_ID()
0x186d  box      [mscorlib]System.Guid
0x1872  stelem.ref
0x1873  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x1878  ldarg.0
0x1879  call     instance bool Microsoft.ReportingServices.Library.PollWorker::get_ContinueWorking()
0x187e  brfalse.s loc_1888
0x1880  ldarg.0
0x1881  ldloc.1
0x1882  callvirt instance bool Microsoft.ReportingServices.Library.QueuePollWorker::QueueWorker(class Microsoft.ReportingServices.Library.QueueItem item)
0x1887  stloc.0
0x1888  leave.s  loc_18D3
0x188a  stloc.2
0x188b  ldc.i4.1
0x188c  stloc.0
0x188d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x1892  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x1897  brfalse.s loc_18B8
0x1899  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x189e  ldc.i4.1
0x189f  ldstr    aQueueItemProce// "Queue item processing had unhandled exc"...
0x18a4  ldc.i4.1
0x18a5  newarr   [mscorlib]System.Object
0x18aa  dup
0x18ab  ldc.i4.0
0x18ac  ldloc.2
0x18ad  callvirt instance string [mscorlib]System.Object::ToString()
0x18b2  stelem.ref
0x18b3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x18b8  ldloc.2
0x18b9  isinst   [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSException
0x18be  brfalse.s loc_18C5
0x18c0  leave    loc_19AC
0x18c5  ldloc.2
0x18c6  ldstr    aQueueItemProce_0// "Queue item processing had unhandled non"...
0x18cb  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0x18d0  pop
0x18d1  leave.s  loc_18D3
0x18d3  leave    loc_1974
0x18d8  ldarg.0
0x18d9  ldloc.1
0x18da  call     instance void Microsoft.ReportingServices.Library.QueuePollWorker::RemoveItem(class Microsoft.ReportingServices.Library.QueueItem item)
0x18df  ldloc.0
0x18e0  brfalse.s loc_1925
0x18e2  ldarg.0
0x18e3  ldloc.1
0x18e4  callvirt instance void Microsoft.ReportingServices.Library.QueuePollWorker::DeleteQueueItem(class Microsoft.ReportingServices.Library.QueueItem item)
0x18e9  ldarg.0
0x18ea  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x18ef  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x18f4  brfalse.s loc_1966
0x18f6  ldarg.0
0x18f7  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x18fc  ldstr    a0FinishedProce// "{0} finished processing item {1}"
0x1901  ldc.i4.2
0x1902  newarr   [mscorlib]System.Object
0x1907  dup
0x1908  ldc.i4.0
0x1909  ldarg.0
0x190a  callvirt instance string Microsoft.ReportingServices.Library.PollWorker::get_PollingTraceName()
0x190f  stelem.ref
0x1910  dup
0x1911  ldc.i4.1
0x1912  ldloc.1
0x1913  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.QueueItem::get_ID()
0x1918  box      [mscorlib]System.Guid
0x191d  stelem.ref
0x191e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x1923  br.s     loc_1966
0x1925  ldarg.0
0x1926  ldloc.1
0x1927  call     instance void Microsoft.ReportingServices.Library.QueuePollWorker::ResetSingleRow(class Microsoft.ReportingServices.Library.QueueItem item)
0x192c  ldarg.0
0x192d  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x1932  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x1937  brfalse.s loc_1966
0x1939  ldarg.0
0x193a  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x193f  ldstr    a0NoLongerProce// "{0} no longer processing item {1}, will"...
0x1944  ldc.i4.2
0x1945  newarr   [mscorlib]System.Object
0x194a  dup
0x194b  ldc.i4.0
0x194c  ldarg.0
0x194d  callvirt instance string Microsoft.ReportingServices.Library.PollWorker::get_PollingTraceName()
0x1952  stelem.ref
0x1953  dup
0x1954  ldc.i4.1
0x1955  ldloc.1
0x1956  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.QueueItem::get_ID()
0x195b  box      [mscorlib]System.Guid
0x1960  stelem.ref
0x1961  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x1966  ldarg.0
0x1967  call     instance bool Microsoft.ReportingServices.Library.QueuePollWorker::ThreadPressureRelaxed()
0x196c  brfalse.s loc_1973
0x196e  call     void Microsoft.ReportingServices.Library.DBPoll::SetWaitEvent()
0x1973  endfinally
0x1974  leave.s  loc_19AC
0x1976  stloc.3
0x1977  ldarg.0
0x1978  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x197d  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x1982  brfalse.s loc_19A4
0x1984  ldarg.0
0x1985  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.QueuePollWorker::m_tracer
0x198a  ldc.i4.1
0x198b  ldstr    aQueueWorkerThr// "Queue worker thread caught unhandled ex"...
0x1990  ldc.i4.1
0x1991  newarr   [mscorlib]System.Object
0x1996  dup
0x1997  ldc.i4.0
0x1998  ldloc.3
0x1999  callvirt instance string [mscorlib]System.Object::ToString()
0x199e  stelem.ref
0x199f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x19a4  leave.s  loc_19AC
0x19a6  call     void Microsoft.ReportingServices.Library.DBPoll::PollItemEnd()
0x19ab  endfinally
0x19ac  ret
```
