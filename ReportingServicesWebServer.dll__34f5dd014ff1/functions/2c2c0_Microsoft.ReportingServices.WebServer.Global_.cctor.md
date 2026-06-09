# Microsoft.ReportingServices.WebServer.Global::.cctor

- ea: `0x2c2c0`
- end: `0x2c3b0`
- name: `Microsoft.ReportingServices.WebServer.Global::.cctor`
- size: `240`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x7da0`
- `0x23600`
- `0x3c610`
- `0x3c640`

## string_xrefs

- `0x2c33b`: `/ReportService2005.asmx`
- `0x2c35b`: `Microsoft.ReportingServices.WebServer.ReportingServicesExecSharepoint.disco`
- `0x2c36c`: `/ReportService2006.asmx`
- `0x2c371`: `/ReportService2006wsdl.aspx`
- `0x2c376`: `/ReportService2006disco.aspx`
- `0x2c37b`: `Microsoft.ReportingServices.WebServer.ReportingServices2006Sharepoint.disco`
- `0x2c38c`: `/ReportService2010.asmx`
- `0x2c391`: `/ReportService2010wsdl.aspx`
- `0x2c396`: `/ReportService2010disco.aspx`
- `0x2c39b`: `Microsoft.ReportingServices.WebServer.ReportingServices2010Sharepoint.disco`

## pseudocode

```c

```

## disassembly

```asm
0x2c2c0  ldnull
0x2c2c1  stsfld   class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningRequestsScavenger Microsoft.ReportingServices.WebServer.Global::m_requestsScavenger
0x2c2c6  ldnull
0x2c2c7  stsfld   class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RunningJobDbTimer Microsoft.ReportingServices.WebServer.Global::m_requestsDbTimer
0x2c2cc  ldnull
0x2c2cd  stsfld   class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.MemoryStatsTimer Microsoft.ReportingServices.WebServer.Global::m_memStatsTimer
0x2c2d2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_WebServerTracer()
0x2c2d7  stsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.WebServer.Global::m_WebServerTracer
0x2c2dc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x2c2e1  stsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.WebServer.Global::m_SessionTracer
0x2c2e6  call     class Microsoft.Reporting.WebForms.HttpHandler Microsoft.Reporting.WebForms.ReportViewerFactory::get_HttpHandler()
0x2c2eb  callvirt instance string Microsoft.Reporting.WebForms.HttpHandler::get_HttpHandlerPath()
0x2c2f0  stsfld   string Microsoft.ReportingServices.WebServer.Global::ControlHandlerPath
0x2c2f5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x2c2fa  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.ReportingServices.WebServer.Global::m_wsdlTemplateCache
0x2c2ff  newobj   instance void [mscorlib]System.Object::.ctor()
0x2c304  stsfld   object Microsoft.ReportingServices.WebServer.Global::m_wsdlTemplateCacheLockObject
0x2c309  ldc.i4.0
0x2c30a  stsfld   bool Microsoft.ReportingServices.WebServer.Global::m_appStarted
0x2c30f  newobj   instance void [mscorlib]System.Object::.ctor()
0x2c314  stsfld   object Microsoft.ReportingServices.WebServer.Global::m_lockObject
0x2c319  ldnull
0x2c31a  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.IPathMatcher, class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.Header> Microsoft.ReportingServices.WebServer.Global::_headerRules
0x2c31f  newobj   instance void [mscorlib]System.Object::.ctor()
0x2c324  stsfld   object Microsoft.ReportingServices.WebServer.Global::m_requestParameterSyncObj
0x2c329  newobj   instance void [mscorlib]System.Object::.ctor()
0x2c32e  stsfld   object Microsoft.ReportingServices.WebServer.Global::m_requestFilesKeySyncObj
0x2c333  ldc.i4.4
0x2c334  newarr   WsdlSpecification
0x2c339  dup
0x2c33a  ldc.i4.0
0x2c33b  ldstr    aReportservice2// "/ReportService2005.asmx"
0x2c340  newobj   instance void WsdlSpecification::.ctor(string serviceObject)
0x2c345  stelem   WsdlSpecification
0x2c34a  dup
0x2c34b  ldc.i4.1
0x2c34c  ldstr    aReportexecutio// "/ReportExecution2005.asmx"
0x2c351  ldstr    aReportexecutio_1// "/ReportExecution2005wsdl.aspx"
0x2c356  ldstr    aReportexecutio_2// "/ReportExecution2005disco.aspx"
0x2c35b  ldstr    aMicrosoftRepor_126// "Microsoft.ReportingServices.WebServer.R"...
0x2c360  newobj   instance void WsdlSpecification::.ctor(string serviceObject, string serviceObjectWsdlAspx, string serviceObjectDiscoAspx, string discoSharepointResourceName)
0x2c365  stelem   WsdlSpecification
0x2c36a  dup
0x2c36b  ldc.i4.2
0x2c36c  ldstr    aReportservice2_0// "/ReportService2006.asmx"
0x2c371  ldstr    aReportservice2_1// "/ReportService2006wsdl.aspx"
0x2c376  ldstr    aReportservice2_2// "/ReportService2006disco.aspx"
0x2c37b  ldstr    aMicrosoftRepor_127// "Microsoft.ReportingServices.WebServer.R"...
0x2c380  newobj   instance void WsdlSpecification::.ctor(string serviceObject, string serviceObjectWsdlAspx, string serviceObjectDiscoAspx, string discoSharepointResourceName)
0x2c385  stelem   WsdlSpecification
0x2c38a  dup
0x2c38b  ldc.i4.3
0x2c38c  ldstr    aReportservice2_3// "/ReportService2010.asmx"
0x2c391  ldstr    aReportservice2_4// "/ReportService2010wsdl.aspx"
0x2c396  ldstr    aReportservice2_5// "/ReportService2010disco.aspx"
0x2c39b  ldstr    aMicrosoftRepor_128// "Microsoft.ReportingServices.WebServer.R"...
0x2c3a0  newobj   instance void WsdlSpecification::.ctor(string serviceObject, string serviceObjectWsdlAspx, string serviceObjectDiscoAspx, string discoSharepointResourceName)
0x2c3a5  stelem   WsdlSpecification
0x2c3aa  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype WsdlSpecification> Microsoft.ReportingServices.WebServer.Global::m_wsdlSpecifications
0x2c3af  ret
```
