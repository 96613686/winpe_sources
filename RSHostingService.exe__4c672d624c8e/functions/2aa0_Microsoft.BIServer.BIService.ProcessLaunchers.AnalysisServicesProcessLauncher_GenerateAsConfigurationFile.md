# Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::GenerateAsConfigurationFile

- ea: `0x2aa0`
- end: `0x2ade`
- name: `Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::GenerateAsConfigurationFile`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2a50`

## callees

- `0x2680`
- `0x26c0`

## pseudocode

```c

```

## disassembly

```asm
0x2aa0  ldarg.1
0x2aa1  ldstr    aMsmdsrvIni// "msmdsrv.ini"
0x2aa6  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2aab  stloc.0
0x2aac  ldarg.1
0x2aad  ldarg.0
0x2aae  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_logRootPath
0x2ab3  ldarg.0
0x2ab4  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_analysisServicesFlightRecorderTraceDefinitionFile
0x2ab9  ldarg.0
0x2aba  ldfld    int32 Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_port
0x2abf  newobj   instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::.ctor(string workspacePath, string logPath, string flightRecorderTraceDefinitionFile, int32 asPort)
0x2ac4  ldarg.0
0x2ac5  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_analysisServicesDefaultConfigurationPath
0x2aca  call     class [System.Xml.Linq]System.Xml.Linq.XDocument [System.Xml.Linq]System.Xml.Linq.XDocument::Load(string)
0x2acf  stloc.1
0x2ad0  ldloc.1
0x2ad1  callvirt instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::Transform(class [System.Xml.Linq]System.Xml.Linq.XDocument xmlDocument)
0x2ad6  ldloc.1
0x2ad7  ldloc.0
0x2ad8  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XDocument::Save(string)
0x2add  ret
```
