# Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::.ctor

- ea: `0x2860`
- end: `0x2968`
- name: `Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::.ctor`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2c90`

## callees

- `0x1a90`
- `0x20f0`
- `0x2190`
- `0x2860`

## string_xrefs

- `0x2917`: `Logger.path`
- `0x292a`: `Logger.path`
- `0x28bd`: `FlightRecorderTraceDef.xml`
- `0x28d2`: `Workspaces.path`
- `0x28e5`: `Workspaces.path`

## pseudocode

```c

```

## disassembly

```asm
0x2860  ldarg.0
0x2861  call     instance void [mscorlib]System.Object::.ctor()
0x2866  ldarg.1
0x2867  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0x286c  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Args::.ctor(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x2871  newobj   instance void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::.ctor(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Args)
0x2876  stloc.0
0x2877  ldarg.0
0x2878  ldarg.1
0x2879  stfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_processConfig
0x287e  ldarg.0
0x287f  ldarg.1
0x2880  callvirt instance string Microsoft.BIServer.BIService.ProcessConfig::get_Path()
0x2885  call     string Microsoft.BIServer.BIService.Paths::RelativeToBaseDirectory(string relativeDirectory)
0x288a  stfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_analysisServicesExePath
0x288f  ldarg.0
0x2890  ldarg.0
0x2891  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_analysisServicesExePath
0x2896  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x289b  stfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_analysisServicesBasePath
0x28a0  ldarg.0
0x28a1  ldarg.0
0x28a2  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_analysisServicesBasePath
0x28a7  ldstr    aMsmdsrvIni// "msmdsrv.ini"
0x28ac  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x28b1  stfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_analysisServicesDefaultConfigurationPath
0x28b6  ldarg.0
0x28b7  ldarg.0
0x28b8  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_analysisServicesBasePath
0x28bd  ldstr    aFlightrecorder// "FlightRecorderTraceDef.xml"
0x28c2  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x28c7  stfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_analysisServicesFlightRecorderTraceDefinitionFile
0x28cc  ldarg.1
0x28cd  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0x28d2  ldstr    aWorkspacesPath// "Workspaces.path"
0x28d7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x28dc  brfalse.s loc_28FB
0x28de  ldarg.0
0x28df  ldarg.1
0x28e0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0x28e5  ldstr    aWorkspacesPath// "Workspaces.path"
0x28ea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x28ef  call     string Microsoft.BIServer.BIService.Paths::RelativeToBaseDirectory(string relativeDirectory)
0x28f4  stfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_workspacesRootPath
0x28f9  br.s     loc_2911
0x28fb  ldarg.0
0x28fc  ldarg.0
0x28fd  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_analysisServicesBasePath
0x2902  ldstr    aWorkspaces// "workspaces"
0x2907  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x290c  stfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_workspacesRootPath
0x2911  ldarg.1
0x2912  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0x2917  ldstr    aLoggerPath// "Logger.path"
0x291c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x2921  brfalse.s loc_2940
0x2923  ldarg.0
0x2924  ldarg.1
0x2925  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0x292a  ldstr    aLoggerPath// "Logger.path"
0x292f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x2934  call     string Microsoft.BIServer.BIService.Paths::RelativeToBaseDirectory(string relativeDirectory)
0x2939  stfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_logRootPath
0x293e  br.s     loc_294C
0x2940  ldarg.0
0x2941  ldarg.0
0x2942  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_workspacesRootPath
0x2947  stfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_logRootPath
0x294c  ldarg.0
0x294d  ldloc.0
0x294e  ldc.i4.0
0x294f  stloc.1
0x2950  ldloca.s 1
0x2952  constrained. [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.HostingInfo.ConfigSettings
0x2958  callvirt instance string [mscorlib]System.Object::ToString()
0x295d  callvirt instance int32 [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrException(string)
0x2962  stfld    int32 Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_port
0x2967  ret
```
