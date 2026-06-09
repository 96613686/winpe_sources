# Microsoft.SharePoint.Diagnostics.SPWebFrontEndDiagnosticsPerformanceCounterProvider::.ctor_0

- ea: `0x640270`
- end: `0x640a12`
- name: `Microsoft.SharePoint.Diagnostics.SPWebFrontEndDiagnosticsPerformanceCounterProvider::.ctor_0`
- size: `1954`
- prototype: ``
- caller_count: `6`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x639390`
- `0x65f0d0`
- `0x65f170`
- `0x65f210`
- `0x65f2a0`
- `0x65f330`

## callees

- `0x1c8480`
- `0x1c8720`
- `0x1c8850`
- `0x1c89b0`
- `0x1c89e0`
- `0x29d020`
- `0x2a43f0`
- `0x472c20`
- `0x577060`
- `0x63f2a0`
- `0x640230`
- `0x640270`
- `0x6412d0`
- `0x6414a0`
- `0x6414b0`
- `0x6414d0`
- `0x7c41d0`
- `0x7c43c0`

## string_xrefs

- `0x640415`: `AddAccessServicesPerfCounter`
- `0x640471`: `Access Services: Secure Store Services`
- `0x640497`: `Application login delete processing time`
- `0x6404a3`: `Application login create processing time`
- `0x6404c7`: `Server login delete processing time`
- `0x6404d3`: `Server login create processing time`
- `0x6404e8`: `Access Services: Data Access Layer`
- `0x640502`: `Avg. DAC Installation Duration`
- `0x64051a`: `Avg. SQL Write Failures`
- `0x640526`: `SQL Write Attempts`
- `0x640532`: `SQL Connection Attempts`
- `0x64053e`: `Unique SQL Connection Attempts`
- `0x640556`: `SQL Connection Retry Attempts`
- `0x640583`: `Access Services: WFE Proxy`
- `0x6405ca`: `Access Services: Template Manager`
- `0x6405d8`: `Avg. SPApp Installation Duration`
- `0x6405f9`: `Access Services: Access Data Services`
- `0x64061f`: `Availability of Access Workload`
- `0x640637`: `Capacity of Access Workload`
- `0x6407c7`: `DiagnosticsDistributedCacheCounters`
- `0x64083a`: `AppFabric Caching:Cache`
- `0x640995`: `Config Total Read Operations`
- `0x6409a1`: `Config Total Read SLA Operations`
- `0x6409ad`: `Config Total Write Operations`
- `0x6409b9`: `Config Total Write SLA Operations`

## pseudocode

```c

```

## disassembly

```asm
0x640270  ldarg.0
0x640271  ldstr    aSpwebfrontendd_0// "SPWebFrontEndDiagnosticsPerfMonProvider"...
0x640276  ldc.i4.0
0x640277  newarr   [mscorlib]System.Object
0x64027c  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x640281  call     string Microsoft.SharePoint.Diagnostics.SPWebFrontEndDiagnosticsPerformanceCounterProvider::get_ObjectName()
0x640286  ldstr    aEvery1Minutes// "every 1 minutes"
0x64028b  ldarg.1
0x64028c  ldc.i4.0
0x64028d  call     instance void Microsoft.SharePoint.Diagnostics.SPDiagnosticsPerformanceCounterProvider::.ctor(string title, string name, string schedule, class Microsoft.SharePoint.Administration.SPService service, valuetype Microsoft.SharePoint.Administration.SPJobLockType lockType)
0x640292  ldarg.0
0x640293  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition>::.ctor()
0x640298  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition> Microsoft.SharePoint.Diagnostics.SPDiagnosticsPerformanceCounterProvider::m_Categories
0x64029d  ldarg.1
0x64029e  callvirt instance class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPPersistedObject::get_Farm()
0x6402a3  stloc.0
0x6402a4  ldloc.0
0x6402a5  ldnull
0x6402a6  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x6402ab  brtrue.s loc_6402FF
0x6402ad  ldloc.0
0x6402ae  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Administration.SPPersistedObject::get_Properties()
0x6402b3  ldstr    aDonotstoreperf// "DoNotStorePerfCountersInUsageDB"
0x6402b8  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x6402bd  brfalse.s loc_6402FF
0x6402bf  ldloc.0
0x6402c0  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Administration.SPPersistedObject::get_Properties()
0x6402c5  ldstr    aDonotstoreperf// "DoNotStorePerfCountersInUsageDB"
0x6402ca  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x6402cf  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6402d4  ldtoken  [mscorlib]System.Boolean
0x6402d9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6402de  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6402e3  brtrue.s loc_6402FF
0x6402e5  ldloc.0
0x6402e6  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.Administration.SPPersistedObject::get_Properties()
0x6402eb  ldstr    aDonotstoreperf// "DoNotStorePerfCountersInUsageDB"
0x6402f0  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x6402f5  unbox.any [mscorlib]System.Boolean
0x6402fa  brtrue   loc_6403EF
0x6402ff  ldarg.0
0x640300  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition> Microsoft.SharePoint.Diagnostics.SPDiagnosticsPerformanceCounterProvider::m_Categories
0x640305  ldc.i4.3
0x640306  newarr   Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition
0x64030b  stloc.s  0x1D
0x64030d  ldloc.s  0x1D
0x64030f  ldc.i4.0
0x640310  ldsfld   string Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition::s_WebServiceCategory
0x640315  ldsfld   string[] Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition::s_WebServiceDefaultCounterNames
0x64031a  ldc.i4.1
0x64031b  newobj   instance void Microsoft.SharePoint.Diagnostics.SPGeneralPerformanceCategoryDefinition::.ctor(string categoryName, class [mscorlib]System.Collections.Generic.IList`1<string> counterNames, bool monitorAllInstances)
0x640320  stelem.ref
0x640321  ldloc.s  0x1D
0x640323  ldc.i4.1
0x640324  ldstr    aProcess_0// "Process"
0x640329  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x64032e  stloc.2
0x64032f  ldloc.2
0x640330  ldstr    aPrivateBytes// "Private Bytes"
0x640335  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x64033a  ldloc.2
0x64033b  ldstr    aIdProcess// "ID Process"
0x640340  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640345  ldloc.2
0x640346  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x64034b  stloc.3
0x64034c  ldloc.3
0x64034d  ldstr    aOwstimer// "OWSTIMER"
0x640352  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640357  ldloc.3
0x640358  ldstr    aW3wp// "W3WP"
0x64035d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640362  ldloc.3
0x640363  newobj   instance void Microsoft.SharePoint.Diagnostics.SPGeneralPerformanceCategoryDefinition::.ctor(string categoryName, class [mscorlib]System.Collections.Generic.IList`1<string> counterNames, class [mscorlib]System.Collections.Generic.IList`1<string> instanceNames)
0x640368  stelem.ref
0x640369  ldloc.s  0x1D
0x64036b  ldc.i4.2
0x64036c  ldstr    aProcessor_2// "Processor"
0x640371  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x640376  stloc.s  4
0x640378  ldloc.s  4
0x64037a  ldstr    aProcessorTime// "% Processor Time"
0x64037f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640384  ldloc.s  4
0x640386  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x64038b  stloc.s  5
0x64038d  ldloc.s  5
0x64038f  ldstr    aTotal// "_Total"
0x640394  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640399  ldloc.s  5
0x64039b  newobj   instance void Microsoft.SharePoint.Diagnostics.SPGeneralPerformanceCategoryDefinition::.ctor(string categoryName, class [mscorlib]System.Collections.Generic.IList`1<string> counterNames, class [mscorlib]System.Collections.Generic.IList`1<string> instanceNames)
0x6403a0  stelem.ref
0x6403a1  ldloc.s  0x1D
0x6403a3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x6403a8  call     class Microsoft.SharePoint.Utilities.SPServerPerformanceInspector Microsoft.SharePoint.Utilities.SPServerPerformanceInspector::get_Local()
0x6403ad  ldarg.0
0x6403ae  callvirt instance void Microsoft.SharePoint.Utilities.SPServerPerformanceInspector::EnsureThrottleCountersToDiagnosticProvider(class Microsoft.SharePoint.Diagnostics.SPDiagnosticsPerformanceCounterProvider provider)
0x6403b3  ldarg.0
0x6403b4  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition> Microsoft.SharePoint.Diagnostics.SPDiagnosticsPerformanceCounterProvider::m_Categories
0x6403b9  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition>::GetEnumerator()
0x6403be  stloc.s  0x1E
0x6403c0  br.s     loc_6403D6
0x6403c2  ldloca.s 0x1E
0x6403c4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition>::get_Current()
0x6403c9  stloc.1
0x6403ca  ldloc.1
0x6403cb  ldarg.0
0x6403cc  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x6403d1  callvirt instance void Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition::set_ProviderName(string value)
0x6403d6  ldloca.s 0x1E
0x6403d8  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition>::MoveNext()
0x6403dd  brtrue.s loc_6403C2
0x6403df  leave.s  loc_6403EF
0x6403e1  ldloca.s 0x1E
0x6403e3  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition>
0x6403e9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6403ee  endfinally
0x6403ef  ldloc.0
0x6403f0  ldnull
0x6403f1  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x6403f6  brfalse  loc_640A11
0x6403fb  ldloc.0
0x6403fc  callvirt instance class Microsoft.SharePoint.Administration.SPFarmInitializationSettings Microsoft.SharePoint.Administration.SPFarm::get_InitializationSettings()
0x640401  callvirt instance bool Microsoft.SharePoint.Administration.SPFarmInitializationSettings::get_IsEnabled()
0x640406  brfalse  loc_640A11
0x64040b  ldloc.0
0x64040c  callvirt instance class Microsoft.SharePoint.Administration.SPFarmInitializationSettings Microsoft.SharePoint.Administration.SPFarm::get_InitializationSettings()
0x640411  stloc.s  6
0x640413  ldloc.s  6
0x640415  ldstr    aAddaccessservi// "AddAccessServicesPerfCounter"
0x64041a  callvirt T0x2B00012E
0x64041f  stloc.s  7
0x640421  ldloc.s  7
0x640423  brfalse  loc_64069A
0x640428  ldarg.0
0x640429  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition> Microsoft.SharePoint.Diagnostics.SPDiagnosticsPerformanceCounterProvider::m_Categories
0x64042e  ldc.i4.6
0x64042f  newarr   Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition
0x640434  stloc.s  0x1F
0x640436  ldloc.s  0x1F
0x640438  ldc.i4.0
0x640439  ldstr    aProcessor_2// "Processor"
0x64043e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x640443  stloc.s  9
0x640445  ldloc.s  9
0x640447  ldstr    aProcessorTime// "% Processor Time"
0x64044c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640451  ldloc.s  9
0x640453  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x640458  stloc.s  0xA
0x64045a  ldloc.s  0xA
0x64045c  ldstr    aTotal// "_Total"
0x640461  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640466  ldloc.s  0xA
0x640468  newobj   instance void Microsoft.SharePoint.Diagnostics.SPGeneralPerformanceCategoryDefinition::.ctor(string categoryName, class [mscorlib]System.Collections.Generic.IList`1<string> counterNames, class [mscorlib]System.Collections.Generic.IList`1<string> instanceNames)
0x64046d  stelem.ref
0x64046e  ldloc.s  0x1F
0x640470  ldc.i4.1
0x640471  ldstr    aAccessServices// "Access Services: Secure Store Services"
0x640476  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x64047b  stloc.s  0xB
0x64047d  ldloc.s  0xB
0x64047f  ldstr    aApplicationLog// "Application login set processing time"
0x640484  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640489  ldloc.s  0xB
0x64048b  ldstr    aApplicationLog_0// "Application login retrieve processing t"...
0x640490  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640495  ldloc.s  0xB
0x640497  ldstr    aApplicationLog_1// "Application login delete processing tim"...
0x64049c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6404a1  ldloc.s  0xB
0x6404a3  ldstr    aApplicationLog_2// "Application login create processing tim"...
0x6404a8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6404ad  ldloc.s  0xB
0x6404af  ldstr    aServerLoginSet// "Server login set processing time"
0x6404b4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6404b9  ldloc.s  0xB
0x6404bb  ldstr    aServerLoginRet// "Server login retrieve processing time"
0x6404c0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6404c5  ldloc.s  0xB
0x6404c7  ldstr    aServerLoginDel// "Server login delete processing time"
0x6404cc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6404d1  ldloc.s  0xB
0x6404d3  ldstr    aServerLoginCre// "Server login create processing time"
0x6404d8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6404dd  ldloc.s  0xB
0x6404df  newobj   instance void Microsoft.SharePoint.Diagnostics.SPGeneralPerformanceCategoryDefinition::.ctor(string categoryName, class [mscorlib]System.Collections.Generic.IList`1<string> counterNames)
0x6404e4  stelem.ref
0x6404e5  ldloc.s  0x1F
0x6404e7  ldc.i4.2
0x6404e8  ldstr    aAccessServices_0// "Access Services: Data Access Layer"
0x6404ed  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6404f2  stloc.s  0xC
0x6404f4  ldloc.s  0xC
0x6404f6  ldstr    aAvgDacExtracti// "Avg. DAC Extraction Duration"
0x6404fb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640500  ldloc.s  0xC
0x640502  ldstr    aAvgDacInstalla// "Avg. DAC Installation Duration"
0x640507  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x64050c  ldloc.s  0xC
0x64050e  ldstr    aAvgGetObjectSc// "Avg. Get Object Schema Duration"
0x640513  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640518  ldloc.s  0xC
0x64051a  ldstr    aAvgSqlWriteFai// "Avg. SQL Write Failures"
0x64051f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640524  ldloc.s  0xC
0x640526  ldstr    aSqlWriteAttemp// "SQL Write Attempts"
0x64052b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640530  ldloc.s  0xC
0x640532  ldstr    aSqlConnectionA// "SQL Connection Attempts"
0x640537  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x64053c  ldloc.s  0xC
0x64053e  ldstr    aUniqueSqlConne// "Unique SQL Connection Attempts"
0x640543  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640548  ldloc.s  0xC
0x64054a  ldstr    aUniqueSuccessf// "Unique Successful SQL Connections"
0x64054f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640554  ldloc.s  0xC
0x640556  ldstr    aSqlConnectionR// "SQL Connection Retry Attempts"
0x64055b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640560  ldloc.s  0xC
0x640562  ldstr    aSuccessfulSqlC// "Successful SQL Connection Retries"
0x640567  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x64056c  ldloc.s  0xC
0x64056e  ldstr    aAvgSqlConnecti// "Avg. SQL Connection Retry Failures"
0x640573  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640578  ldloc.s  0xC
0x64057a  newobj   instance void Microsoft.SharePoint.Diagnostics.SPGeneralPerformanceCategoryDefinition::.ctor(string categoryName, class [mscorlib]System.Collections.Generic.IList`1<string> counterNames)
0x64057f  stelem.ref
0x640580  ldloc.s  0x1F
0x640582  ldc.i4.3
0x640583  ldstr    aAccessServices_1// "Access Services: WFE Proxy"
0x640588  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x64058d  stloc.s  0xD
0x64058f  ldloc.s  0xD
0x640591  ldstr    aTotalAvailable// "Total Available ADS Servers"
0x640596  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x64059b  ldloc.s  0xD
0x64059d  ldstr    aTotalHealthyAv// "Total Healthy Available ADS Servers"
0x6405a2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6405a7  ldloc.s  0xD
0x6405a9  ldstr    aRequestsPerSec// "Requests per second"
0x6405ae  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6405b3  ldloc.s  0xD
0x6405b5  ldstr    aActiveRequests// "Active Requests"
0x6405ba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6405bf  ldloc.s  0xD
0x6405c1  newobj   instance void Microsoft.SharePoint.Diagnostics.SPGeneralPerformanceCategoryDefinition::.ctor(string categoryName, class [mscorlib]System.Collections.Generic.IList`1<string> counterNames)
0x6405c6  stelem.ref
0x6405c7  ldloc.s  0x1F
0x6405c9  ldc.i4.4
0x6405ca  ldstr    aAccessServices_2// "Access Services: Template Manager"
0x6405cf  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6405d4  stloc.s  0xE
0x6405d6  ldloc.s  0xE
0x6405d8  ldstr    aAvgSpappInstal// "Avg. SPApp Installation Duration"
0x6405dd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6405e2  ldloc.s  0xE
0x6405e4  ldstr    aAvgSpappExtrac// "Avg. SPApp Extraction Duration"
0x6405e9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6405ee  ldloc.s  0xE
0x6405f0  newobj   instance void Microsoft.SharePoint.Diagnostics.SPGeneralPerformanceCategoryDefinition::.ctor(string categoryName, class [mscorlib]System.Collections.Generic.IList`1<string> counterNames)
0x6405f5  stelem.ref
0x6405f6  ldloc.s  0x1F
0x6405f8  ldc.i4.5
0x6405f9  ldstr    aAccessServices_3// "Access Services: Access Data Services"
0x6405fe  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x640603  stloc.s  0xF
0x640605  ldloc.s  0xF
0x640607  ldstr    aAverageDataSto// "Average Data Store Request Processing T"...
0x64060c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640611  ldloc.s  0xF
0x640613  ldstr    aDataStoreReque// "Data Store Requests/sec"
0x640618  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x64061d  ldloc.s  0xF
0x64061f  ldstr    aAvailabilityOf// "Availability of Access Workload"
0x640624  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640629  ldloc.s  0xF
0x64062b  ldstr    aAvailabilityOf_0// "Availability of Application Workload"
0x640630  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640635  ldloc.s  0xF
0x640637  ldstr    aCapacityOfAcce// "Capacity of Access Workload"
0x64063c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x640641  ldloc.s  0xF
0x640643  ldstr    aCapacityOfAppl// "Capacity of Application Workload"
0x640648  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x64064d  ldloc.s  0xF
0x64064f  newobj   instance void Microsoft.SharePoint.Diagnostics.SPGeneralPerformanceCategoryDefinition::.ctor(string categoryName, class [mscorlib]System.Collections.Generic.IList`1<string> counterNames)
0x640654  stelem.ref
0x640655  ldloc.s  0x1F
0x640657  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x64065c  ldarg.0
0x64065d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition> Microsoft.SharePoint.Diagnostics.SPDiagnosticsPerformanceCounterProvider::m_Categories
0x640662  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition>::GetEnumerator()
0x640667  stloc.s  0x20
0x640669  br.s     loc_640681
0x64066b  ldloca.s 0x20
0x64066d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Diagnostics.SPPerformanceCategoryDefinition>::get_Current()
0x640672  stloc.s  8
0x640674  ldloc.s  8
  ... truncated ...
```
