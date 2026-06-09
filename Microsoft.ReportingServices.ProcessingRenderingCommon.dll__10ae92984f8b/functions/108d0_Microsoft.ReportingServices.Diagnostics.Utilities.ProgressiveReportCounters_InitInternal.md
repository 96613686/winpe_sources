# Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::InitInternal

- ea: `0x108d0`
- end: `0x10ba1`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::InitInternal`
- size: `721`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x10890`

## callees

- `0x6130`
- `0xeb90`
- `0xeba0`
- `0xebb0`
- `0x10150`
- `0x108d0`

## string_xrefs

- `0x10b7f`: `Threads Active`
- `0x108de`: `ProgressiveReportCounters class being used and diaganostic dll was not initialized correctly.`

## pseudocode

```c

```

## disassembly

```asm
0x108d0  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x108d5  callvirt instance valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_CurrentApplication()
0x108da  ldc.i4.s 0xB
0x108dc  bne.un.s loc_108E9
0x108de  ldstr    aProgressiverep_0// "ProgressiveReportCounters class being u"...
0x108e3  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x108e8  throw
0x108e9  ldarg.0
0x108ea  ldarg.1
0x108eb  ldstr    aReportserverPo// "ReportServer.Power View"
0x108f0  ldstr    aReportRequests// "Report Requests Active"
0x108f5  ldarg.2
0x108f6  callvirt instance class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.ICounterProvider::GetCounterNumberOfItems(string categoryName, string counterName, bool resetCounter)
0x108fb  stfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_reportRequestsActive
0x10900  ldarg.0
0x10901  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable> Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_countersList
0x10906  ldarg.0
0x10907  ldfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_reportRequestsActive
0x1090c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x10911  ldarg.0
0x10912  ldarg.1
0x10913  ldstr    aReportserverPo// "ReportServer.Power View"
0x10918  ldstr    aReportRequests_0// "Report Requests Total"
0x1091d  ldstr    aReportRequests_1// "Report Requests/sec"
0x10922  ldarg.2
0x10923  callvirt instance class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.ICounterProvider::GetCounterRatePerSecond(string categoryName, string counterNameTotal, string counterNamePerSecond, bool resetCounter)
0x10928  stfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_reportRequestsTotal
0x1092d  ldarg.0
0x1092e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable> Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_countersList
0x10933  ldarg.0
0x10934  ldfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_reportRequestsTotal
0x10939  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x1093e  ldarg.0
0x1093f  ldarg.1
0x10940  ldstr    aReportserverPo// "ReportServer.Power View"
0x10945  ldstr    aReportRequests_2// "Report Requests Average Duration (ms)"
0x1094a  ldstr    aReportRequests_3// "Report Requests Average Duration base"
0x1094f  ldarg.2
0x10950  callvirt instance class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.ICounterProvider::GetCounterAverageCount(string categoryName, string counterNameAverage, string counterNameBase, bool resetCounter)
0x10955  stfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_reportRequestsAverageDuration
0x1095a  ldarg.0
0x1095b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable> Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_countersList
0x10960  ldarg.0
0x10961  ldfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_reportRequestsAverageDuration
0x10966  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x1096b  ldarg.0
0x1096c  ldarg.1
0x1096d  ldstr    aReportserverPo// "ReportServer.Power View"
0x10972  ldstr    aModelRequestsA// "Model Requests Active"
0x10977  ldarg.2
0x10978  callvirt instance class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.ICounterProvider::GetCounterNumberOfItems(string categoryName, string counterName, bool resetCounter)
0x1097d  stfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_modelRequestsActive
0x10982  ldarg.0
0x10983  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable> Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_countersList
0x10988  ldarg.0
0x10989  ldfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_modelRequestsActive
0x1098e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x10993  ldarg.0
0x10994  ldarg.1
0x10995  ldstr    aReportserverPo// "ReportServer.Power View"
0x1099a  ldstr    aModelRequestsT// "Model Requests Total"
0x1099f  ldstr    aModelRequestsS// "Model Requests/sec"
0x109a4  ldarg.2
0x109a5  callvirt instance class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.ICounterProvider::GetCounterRatePerSecond(string categoryName, string counterNameTotal, string counterNamePerSecond, bool resetCounter)
0x109aa  stfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_modelRequestsTotal
0x109af  ldarg.0
0x109b0  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable> Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_countersList
0x109b5  ldarg.0
0x109b6  ldfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_modelRequestsTotal
0x109bb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x109c0  ldarg.0
0x109c1  ldarg.1
0x109c2  ldstr    aReportserverPo// "ReportServer.Power View"
0x109c7  ldstr    aModelRequestsA_0// "Model Requests Average Duration (ms)"
0x109cc  ldstr    aModelRequestsA_1// "Model Requests Average Duration base"
0x109d1  ldarg.2
0x109d2  callvirt instance class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.ICounterProvider::GetCounterAverageCount(string categoryName, string counterNameAverage, string counterNameBase, bool resetCounter)
0x109d7  stfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_modelRequestsAverageDuration
0x109dc  ldarg.0
0x109dd  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable> Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_countersList
0x109e2  ldarg.0
0x109e3  ldfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_modelRequestsAverageDuration
0x109e8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x109ed  ldarg.0
0x109ee  ldarg.1
0x109ef  ldstr    aReportserverPo// "ReportServer.Power View"
0x109f4  ldstr    aQueryRequestsA// "Query Requests Active"
0x109f9  ldarg.2
0x109fa  callvirt instance class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.ICounterProvider::GetCounterNumberOfItems(string categoryName, string counterName, bool resetCounter)
0x109ff  stfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_queryRequestsActive
0x10a04  ldarg.0
0x10a05  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable> Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_countersList
0x10a0a  ldarg.0
0x10a0b  ldfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_queryRequestsActive
0x10a10  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x10a15  ldarg.0
0x10a16  ldarg.1
0x10a17  ldstr    aReportserverPo// "ReportServer.Power View"
0x10a1c  ldstr    aQueryRequestsT// "Query Requests Total"
0x10a21  ldstr    aQueryRequestsS// "Query Requests/sec"
0x10a26  ldarg.2
0x10a27  callvirt instance class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.ICounterProvider::GetCounterRatePerSecond(string categoryName, string counterNameTotal, string counterNamePerSecond, bool resetCounter)
0x10a2c  stfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_queryRequestsTotal
0x10a31  ldarg.0
0x10a32  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable> Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_countersList
0x10a37  ldarg.0
0x10a38  ldfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_queryRequestsTotal
0x10a3d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x10a42  ldarg.0
0x10a43  ldarg.1
0x10a44  ldstr    aReportserverPo// "ReportServer.Power View"
0x10a49  ldstr    aQueryRequestsA_0// "Query Requests Average Duration (ms)"
0x10a4e  ldstr    aQueryRequestsA_1// "Query Requests Average Duration base"
0x10a53  ldarg.2
0x10a54  callvirt instance class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.ICounterProvider::GetCounterAverageCount(string categoryName, string counterNameAverage, string counterNameBase, bool resetCounter)
0x10a59  stfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_queryRequestsAverageDuration
0x10a5e  ldarg.0
0x10a5f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable> Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_countersList
0x10a64  ldarg.0
0x10a65  ldfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_queryRequestsAverageDuration
0x10a6a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x10a6f  ldarg.0
0x10a70  ldarg.1
0x10a71  ldstr    aReportserverPo// "ReportServer.Power View"
0x10a76  ldstr    aFailuresTotal// "Failures Total"
0x10a7b  ldstr    aFailuresSec// "Failures/sec"
0x10a80  ldarg.2
0x10a81  callvirt instance class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.ICounterProvider::GetCounterRatePerSecond(string categoryName, string counterNameTotal, string counterNamePerSecond, bool resetCounter)
0x10a86  stfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_failuresTotal
0x10a8b  ldarg.0
0x10a8c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable> Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_countersList
0x10a91  ldarg.0
0x10a92  ldfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_failuresTotal
0x10a97  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x10a9c  ldarg.0
0x10a9d  ldarg.1
0x10a9e  ldstr    aReportserverPo// "ReportServer.Power View"
0x10aa3  ldstr    aSessionsActive// "Sessions Active"
0x10aa8  ldarg.2
0x10aa9  callvirt instance class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.ICounterProvider::GetCounterNumberOfItems(string categoryName, string counterName, bool resetCounter)
0x10aae  stfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_sessionsActive
0x10ab3  ldarg.0
0x10ab4  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable> Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_countersList
0x10ab9  ldarg.0
0x10aba  ldfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_sessionsActive
0x10abf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x10ac4  ldarg.0
0x10ac5  ldarg.1
0x10ac6  ldstr    aReportserverPo// "ReportServer.Power View"
0x10acb  ldstr    aRequestsInNewS// "Requests in New Sessions Total"
0x10ad0  ldstr    aRequestsInNewS_0// "Requests in New Sessions/sec"
0x10ad5  ldarg.2
0x10ad6  callvirt instance class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.ICounterProvider::GetCounterRatePerSecond(string categoryName, string counterNameTotal, string counterNamePerSecond, bool resetCounter)
0x10adb  stfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_newSessionTotal
0x10ae0  ldarg.0
0x10ae1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable> Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_countersList
0x10ae6  ldarg.0
0x10ae7  ldfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_newSessionTotal
0x10aec  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x10af1  ldarg.0
0x10af2  ldarg.1
0x10af3  ldstr    aReportserverPo// "ReportServer.Power View"
0x10af8  ldstr    aRequestsInExis// "Requests in Existing Sessions Total"
0x10afd  ldstr    aRequestsInExis_0// "Requests in Existing Sessions/sec"
0x10b02  ldarg.2
0x10b03  callvirt instance class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.ICounterProvider::GetCounterRatePerSecond(string categoryName, string counterNameTotal, string counterNamePerSecond, bool resetCounter)
0x10b08  stfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_existingSessionTotal
0x10b0d  ldarg.0
0x10b0e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable> Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_countersList
0x10b13  ldarg.0
0x10b14  ldfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_existingSessionTotal
0x10b19  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x10b1e  ldarg.0
0x10b1f  ldarg.1
0x10b20  ldstr    aReportserverPo// "ReportServer.Power View"
0x10b25  ldstr    aRequestsTotal// "Requests Total"
0x10b2a  ldstr    aRequestsSec// "Requests/sec"
0x10b2f  ldarg.2
0x10b30  callvirt instance class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.ICounterProvider::GetCounterRatePerSecond(string categoryName, string counterNameTotal, string counterNamePerSecond, bool resetCounter)
0x10b35  stfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_allRequestsTotal
0x10b3a  ldarg.0
0x10b3b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable> Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_countersList
0x10b40  ldarg.0
0x10b41  ldfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_allRequestsTotal
0x10b46  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x10b4b  ldarg.0
0x10b4c  ldarg.1
0x10b4d  ldstr    aReportserverPo// "ReportServer.Power View"
0x10b52  ldstr    aDataSourceConn// "Data Source Connection Failures Total"
0x10b57  ldstr    aDataSourceConn_0// "Data Source Connection Failures/sec"
0x10b5c  ldarg.2
0x10b5d  callvirt instance class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.ICounterProvider::GetCounterRatePerSecond(string categoryName, string counterNameTotal, string counterNamePerSecond, bool resetCounter)
0x10b62  stfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_dataSourceConnectionFailuresTotal
0x10b67  ldarg.0
0x10b68  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable> Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_countersList
0x10b6d  ldarg.0
0x10b6e  ldfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_dataSourceConnectionFailuresTotal
0x10b73  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x10b78  ldarg.0
0x10b79  ldarg.1
0x10b7a  ldstr    aReportserverPo// "ReportServer.Power View"
0x10b7f  ldstr    aThreadsActive// "Threads Active"
0x10b84  ldarg.2
0x10b85  callvirt instance class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.ICounterProvider::GetCounterNumberOfItems(string categoryName, string counterName, bool resetCounter)
0x10b8a  stfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_threadsActive
0x10b8f  ldarg.0
0x10b90  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable> Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_countersList
0x10b95  ldarg.0
0x10b96  ldfld    class Microsoft.ReportingServices.Diagnostics.ICounter Microsoft.ReportingServices.Diagnostics.Utilities.ProgressiveReportCounters::m_threadsActive
0x10b9b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.IDisposable>::Add(var<u1>)
0x10ba0  ret
```
