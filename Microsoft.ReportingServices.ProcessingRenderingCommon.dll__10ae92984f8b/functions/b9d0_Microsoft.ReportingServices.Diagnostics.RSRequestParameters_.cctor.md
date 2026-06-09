# Microsoft.ReportingServices.Diagnostics.RSRequestParameters::.cctor

- ea: `0xb9d0`
- end: `0xbbc3`
- name: `Microsoft.ReportingServices.Diagnostics.RSRequestParameters::.cctor`
- size: `499`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0xb9d0`: `<DeviceInfo>\n                        <UseFullUrls>True</UseFullUrls>\n                        <PageHeight>3.125in</PageHeight>\n                        <PageWidth>5.3125in</PageWidth>\n                        <ActiveXControls>False</ActiveXControls>\n                        <OutputFormat>PNG</OutputFormat>                   \n                        <ReportItemPath>{0}</ReportItemPath>\n                    </DeviceInfo>`
- `0xba8f`: `OpenSession`
- `0xbabf`: `ExecuteCommands`
- `0xbb4f`: `ExecuteCommands`

## pseudocode

```c

```

## disassembly

```asm
0xb9d0  ldstr    aDeviceinfoUsef// "<DeviceInfo>\r\n                       "...
0xb9d5  stsfld   string Microsoft.ReportingServices.Diagnostics.RSRequestParameters::PBIDeviceInfoStringFormat
0xb9da  ldc.i4.8
0xb9db  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::.ctor(int32)
0xb9e0  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_crescentCommands
0xb9e5  ldc.i4.6
0xb9e6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod>::.ctor(int32)
0xb9eb  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewCommands
0xb9f0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xb9f5  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewServerVrmCommands
0xb9fa  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_crescentCommands
0xb9ff  ldstr    aRenderedit// "RenderEdit"
0xba04  ldc.i4.1
0xba05  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0xba0a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_crescentCommands
0xba0f  ldstr    aGetmodel// "GetModel"
0xba14  ldc.i4.1
0xba15  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0xba1a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_crescentCommands
0xba1f  ldstr    aExecutequeries// "ExecuteQueries"
0xba24  ldc.i4.1
0xba25  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0xba2a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_crescentCommands
0xba2f  ldstr    aLogclienttrace// "LogClientTraceEvents"
0xba34  ldc.i4.1
0xba35  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0xba3a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_crescentCommands
0xba3f  ldstr    aClosesession// "CloseSession"
0xba44  ldc.i4.1
0xba45  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0xba4a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_crescentCommands
0xba4f  ldstr    aCancelprogress// "CancelProgressiveSessionJobs"
0xba54  ldc.i4.1
0xba55  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0xba5a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_crescentCommands
0xba5f  ldstr    aGetexternalima// "GetExternalImages"
0xba64  ldc.i4.1
0xba65  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0xba6a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_crescentCommands
0xba6f  ldstr    aGetreportandmo// "GetReportAndModels"
0xba74  ldc.i4.1
0xba75  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0xba7a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewCommands
0xba7f  ldstr    aClosesession// "CloseSession"
0xba84  ldc.i4.1
0xba85  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod>::Add(var<u1>, !!T0)
0xba8a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewCommands
0xba8f  ldstr    aOpensession// "OpenSession"
0xba94  ldc.i4.1
0xba95  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod>::Add(var<u1>, !!T0)
0xba9a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewCommands
0xba9f  ldstr    aLogclientactiv// "LogClientActivities"
0xbaa4  ldc.i4.1
0xbaa5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod>::Add(var<u1>, !!T0)
0xbaaa  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewCommands
0xbaaf  ldstr    aLogclienttrace_0// "LogClientTraces"
0xbab4  ldc.i4.1
0xbab5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod>::Add(var<u1>, !!T0)
0xbaba  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewCommands
0xbabf  ldstr    aExecutecommand// "ExecuteCommands"
0xbac4  ldc.i4.1
0xbac5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod>::Add(var<u1>, !!T0)
0xbaca  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewCommands
0xbacf  ldstr    aLoaddocument// "LoadDocument"
0xbad4  ldc.i4.1
0xbad5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod>::Add(var<u1>, !!T0)
0xbada  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewCommands
0xbadf  ldstr    aLoadreport// "LoadReport"
0xbae4  ldc.i4.1
0xbae5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod>::Add(var<u1>, !!T0)
0xbaea  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewCommands
0xbaef  ldstr    aGetvisual// "GetVisual"
0xbaf4  ldc.i4.0
0xbaf5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod>::Add(var<u1>, !!T0)
0xbafa  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewCommands
0xbaff  ldstr    aSavereport// "SaveReport"
0xbb04  ldc.i4.1
0xbb05  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod>::Add(var<u1>, !!T0)
0xbb0a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewCommands
0xbb0f  ldstr    aExecutesemanti// "ExecuteSemanticQuery"
0xbb14  ldc.i4.1
0xbb15  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod>::Add(var<u1>, !!T0)
0xbb1a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewCommands
0xbb1f  ldstr    aGetentitydatam// "GetEntityDataModel"
0xbb24  ldc.i4.0
0xbb25  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod>::Add(var<u1>, !!T0)
0xbb2a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewCommands
0xbb2f  ldstr    aGetsemanticque// "GetSemanticQuery"
0xbb34  ldc.i4.1
0xbb35  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod>::Add(var<u1>, !!T0)
0xbb3a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewCommands
0xbb3f  ldstr    aGetdocument// "GetDocument"
0xbb44  ldc.i4.0
0xbb45  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype HttpMethod>::Add(var<u1>, !!T0)
0xbb4a  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewServerVrmCommands
0xbb4f  ldstr    aExecutecommand// "ExecuteCommands"
0xbb54  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbb59  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewServerVrmCommands
0xbb5e  ldstr    aLoaddocument// "LoadDocument"
0xbb63  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbb68  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewServerVrmCommands
0xbb6d  ldstr    aLoadreport// "LoadReport"
0xbb72  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbb77  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewServerVrmCommands
0xbb7c  ldstr    aGetvisual// "GetVisual"
0xbb81  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbb86  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewServerVrmCommands
0xbb8b  ldstr    aExecutesemanti// "ExecuteSemanticQuery"
0xbb90  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbb95  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewServerVrmCommands
0xbb9a  ldstr    aSavereport// "SaveReport"
0xbb9f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbba4  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewServerVrmCommands
0xbba9  ldstr    aGetsemanticque// "GetSemanticQuery"
0xbbae  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbbb3  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Diagnostics.RSRequestParameters::m_powerViewServerVrmCommands
0xbbb8  ldstr    aGetdocument// "GetDocument"
0xbbbd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xbbc2  ret
```
