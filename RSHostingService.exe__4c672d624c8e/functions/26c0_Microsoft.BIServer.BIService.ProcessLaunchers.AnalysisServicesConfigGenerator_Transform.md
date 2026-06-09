# Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::Transform

- ea: `0x26c0`
- end: `0x27c8`
- name: `Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::Transform`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x2aa0`

## callees

- `0x27d0`

## string_xrefs

- `0x26f9`: `TempDir`
- `0x2753`: `DAX/ExtensionDir`
- `0x27b8`: `TMCompatibilitySKU`

## pseudocode

```c

```

## disassembly

```asm
0x26c0  ldarg.1
0x26c1  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XDocument::get_Root()
0x26c6  stloc.0
0x26c7  ldarg.0
0x26c8  ldloc.0
0x26c9  ldstr    aPrivateprocess// "PrivateProcess"
0x26ce  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x26d3  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x26d8  stloc.1
0x26d9  ldloca.s 1
0x26db  call     instance string [mscorlib]System.Int32::ToString()
0x26e0  call     instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::SetValueOfNode(class [System.Xml.Linq]System.Xml.Linq.XElement root, string path, string value)
0x26e5  ldarg.0
0x26e6  ldloc.0
0x26e7  ldstr    aDatadir// "DataDir"
0x26ec  ldarg.0
0x26ed  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::_safeWorkspacePath
0x26f2  call     instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::SetValueOfNode(class [System.Xml.Linq]System.Xml.Linq.XElement root, string path, string value)
0x26f7  ldarg.0
0x26f8  ldloc.0
0x26f9  ldstr    aTempdir// "TempDir"
0x26fe  ldarg.0
0x26ff  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::_safeWorkspacePath
0x2704  call     instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::SetValueOfNode(class [System.Xml.Linq]System.Xml.Linq.XElement root, string path, string value)
0x2709  ldarg.0
0x270a  ldloc.0
0x270b  ldstr    aLogdir// "LogDir"
0x2710  ldarg.0
0x2711  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::_safeLogPath
0x2716  call     instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::SetValueOfNode(class [System.Xml.Linq]System.Xml.Linq.XElement root, string path, string value)
0x271b  ldarg.0
0x271c  ldloc.0
0x271d  ldstr    aBackupdir// "BackupDir"
0x2722  ldarg.0
0x2723  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::_safeWorkspacePath
0x2728  call     instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::SetValueOfNode(class [System.Xml.Linq]System.Xml.Linq.XElement root, string path, string value)
0x272d  ldarg.0
0x272e  ldloc.0
0x272f  ldstr    aAllowedbrowsin// "AllowedBrowsingFolders"
0x2734  ldarg.0
0x2735  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::_safeWorkspacePath
0x273a  call     instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::SetValueOfNode(class [System.Xml.Linq]System.Xml.Linq.XElement root, string path, string value)
0x273f  ldarg.0
0x2740  ldloc.0
0x2741  ldstr    aLogExceptionCr// "Log/Exception/CrashReportsFolder"
0x2746  ldarg.0
0x2747  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::_safeLogPath
0x274c  call     instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::SetValueOfNode(class [System.Xml.Linq]System.Xml.Linq.XElement root, string path, string value)
0x2751  ldarg.0
0x2752  ldloc.0
0x2753  ldstr    aDaxExtensiondi// "DAX/ExtensionDir"
0x2758  ldarg.0
0x2759  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::_safeWorkspacePath
0x275e  call     instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::SetValueOfNode(class [System.Xml.Linq]System.Xml.Linq.XElement root, string path, string value)
0x2763  ldarg.0
0x2764  ldloc.0
0x2765  ldstr    aPort// "Port"
0x276a  ldarg.0
0x276b  ldfld    int32 Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::_asPort
0x2770  stloc.1
0x2771  ldloca.s 1
0x2773  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2778  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x277d  call     instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::SetValueOfNode(class [System.Xml.Linq]System.Xml.Linq.XElement root, string path, string value)
0x2782  ldarg.0
0x2783  ldloc.0
0x2784  ldstr    aLogFlightrecor// "Log/FlightRecorder/TraceDefinitionFile"
0x2789  ldarg.0
0x278a  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::_flightRecorderTraceDefinitionPath
0x278f  call     instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::SetValueOfNode(class [System.Xml.Linq]System.Xml.Linq.XElement root, string path, string value)
0x2794  ldarg.0
0x2795  ldloc.0
0x2796  ldstr    aDeploymentmode// "DeploymentMode"
0x279b  ldstr    a1// "1"
0x27a0  call     instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::SetValueOfNode(class [System.Xml.Linq]System.Xml.Linq.XElement root, string path, string value)
0x27a5  ldarg.0
0x27a6  ldloc.0
0x27a7  ldstr    aServerlocation// "ServerLocation"
0x27ac  ldstr    a4// "4"
0x27b1  call     instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::SetValueOfNode(class [System.Xml.Linq]System.Xml.Linq.XElement root, string path, string value)
0x27b6  ldarg.0
0x27b7  ldloc.0
0x27b8  ldstr    aTmcompatibilit// "TMCompatibilitySKU"
0x27bd  ldstr    a2// "2"
0x27c2  call     instance void Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesConfigGenerator::SetValueOfNode(class [System.Xml.Linq]System.Xml.Linq.XElement root, string path, string value)
0x27c7  ret
```
