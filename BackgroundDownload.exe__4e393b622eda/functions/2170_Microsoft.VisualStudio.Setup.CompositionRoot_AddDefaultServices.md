# Microsoft.VisualStudio.Setup.CompositionRoot::AddDefaultServices

- ea: `0x2170`
- end: `0x231b`
- name: `Microsoft.VisualStudio.Setup.CompositionRoot::AddDefaultServices`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x5090`

## callees

- `0x1cb0`
- `0x2170`
- `0x2b50`
- `0x2d70`

## pseudocode

```c

```

## disassembly

```asm
0x2170  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x2175  stloc.0
0x2176  ldarg.0
0x2177  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileSystem::Default
0x217c  ldc.i4.0
0x217d  ldc.i4.0
0x217e  callvirt T0x2B000018
0x2183  ldarg.0
0x2184  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ProcessService::Default
0x2189  ldc.i4.0
0x218a  ldc.i4.0
0x218b  callvirt T0x2B000019
0x2190  ldarg.0
0x2191  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IHashingService [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.HashingService::get_Default()
0x2196  ldc.i4.0
0x2197  ldc.i4.0
0x2198  callvirt T0x2B00001A
0x219d  ldarg.0
0x219e  ldsfld   class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IOpcService [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.OpcService::Default
0x21a3  ldc.i4.0
0x21a4  ldc.i4.0
0x21a5  callvirt T0x2B00001B
0x21aa  ldarg.0
0x21ab  ldnull
0x21ac  ldloc.0
0x21ad  callvirt instance string [System]System.Diagnostics.Process::get_ProcessName()
0x21b2  ldc.i4.5
0x21b3  ldc.i4   0xBB8
0x21b8  call     class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileLogger [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.FileLogger::OpenFileLogger(class [mscorlib]System.IServiceProvider, string, string, int32, int32)
0x21bd  stloc.1
0x21be  ldarg.0
0x21bf  ldloc.1
0x21c0  ldc.i4.0
0x21c1  ldc.i4.0
0x21c2  callvirt T0x2B00001C
0x21c7  ldarg.0
0x21c8  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.WindowsRegistry::Default
0x21cd  ldc.i4.0
0x21ce  ldc.i4.0
0x21cf  callvirt T0x2B00001D
0x21d4  ldarg.0
0x21d5  ldloc.1
0x21d6  newobj   instance void Microsoft.VisualStudio.Setup.WMIValidator::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger)
0x21db  ldc.i4.0
0x21dc  ldc.i4.0
0x21dd  callvirt T0x2B00001E
0x21e2  ldarg.0
0x21e3  ldarg.0
0x21e4  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.PolicyService::.ctor(class [mscorlib]System.IServiceProvider)
0x21e9  ldc.i4.0
0x21ea  ldc.i4.0
0x21eb  callvirt T0x2B00001F
0x21f0  ldarg.0
0x21f1  ldarg.0
0x21f2  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.AccountProfileService::.ctor(class [mscorlib]System.IServiceProvider)
0x21f7  dup
0x21f8  ldc.i4.1
0x21f9  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.AccountProfileService::set_InUserMode(bool)
0x21fe  ldc.i4.0
0x21ff  ldc.i4.0
0x2200  callvirt T0x2B000020
0x2205  ldarg.0
0x2206  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ICompressedPackageReader [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.CompressedPackageReader::Default
0x220b  ldc.i4.0
0x220c  ldc.i4.0
0x220d  callvirt T0x2B000021
0x2212  ldarg.0
0x2213  ldarg.0
0x2214  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.LockService::.ctor(class [mscorlib]System.IServiceProvider)
0x2219  ldc.i4.0
0x221a  ldc.i4.0
0x221b  callvirt T0x2B000022
0x2220  ldarg.0
0x2221  ldarg.0
0x2222  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Cache.Query::.ctor(class [mscorlib]System.IServiceProvider)
0x2227  ldc.i4.0
0x2228  ldc.i4.0
0x2229  callvirt T0x2B000023
0x222e  ldarg.0
0x222f  newobj   instance void [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.WindowHandlerFacade::.ctor()
0x2234  ldc.i4.0
0x2235  ldc.i4.0
0x2236  callvirt T0x2B000024
0x223b  ldarg.0
0x223c  ldarg.0
0x223d  newobj   instance void [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.WebRequestService::.ctor(class [mscorlib]System.IServiceProvider)
0x2242  newobj   instance void [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.FetchService::.ctor(class [Microsoft.VisualStudio.Setup.Download]Microsoft.VisualStudio.Setup.Download.IWebRequestService)
0x2247  ldc.i4.0
0x2248  ldc.i4.0
0x2249  callvirt T0x2B000025
0x224e  ldarg.0
0x224f  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Security.SignatureManager::.ctor(class [mscorlib]System.IServiceProvider)
0x2254  stloc.2
0x2255  ldloc.2
0x2256  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Security.SignatureManager::AddDefaultVerifiers()
0x225b  ldarg.0
0x225c  ldloc.2
0x225d  ldc.i4.0
0x225e  ldc.i4.0
0x225f  callvirt T0x2B000026
0x2264  ldarg.0
0x2265  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.StopSignal::BackgroundDownloadSyncEventName
0x226a  ldc.i4.1
0x226b  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.StopSignal::.ctor(string, bool)
0x2270  ldc.i4.0
0x2271  ldc.i4.0
0x2272  callvirt T0x2B000027
0x2277  ldarg.0
0x2278  ldarg.0
0x2279  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.VisualStudio.Setup.BackgroundDownloadConstants::IdleTimeout
0x227e  newobj   instance void Microsoft.VisualStudio.Setup.UserActivityMonitor::.ctor(class [mscorlib]System.IServiceProvider services, valuetype [mscorlib]System.TimeSpan idleTimeout)
0x2283  ldc.i4.0
0x2284  ldc.i4.0
0x2285  callvirt T0x2B000028
0x228a  ldarg.1
0x228b  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.CommandLine::get_ChildClientInstallerVersion()
0x2290  dup
0x2291  brtrue.s loc_229B
0x2293  pop
0x2294  ldarg.0
0x2295  ldnull
0x2296  call     class [mscorlib]System.Version [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Client::GetInstallerVersion(class [mscorlib]System.IServiceProvider, string)
0x229b  stloc.3
0x229c  ldarg.0
0x229d  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Telemetry::.ctor(class [mscorlib]System.IServiceProvider)
0x22a2  stloc.s  4
0x22a4  ldloc.s  4
0x22a6  callvirt instance class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Telemetry::get_TelemetrySession()
0x22ab  stloc.s  5
0x22ad  ldstr    aVsXsetup// "vs-xsetup"
0x22b2  ldloc.3
0x22b3  brtrue.s loc_22B8
0x22b5  ldnull
0x22b6  br.s     loc_22BE
0x22b8  ldloc.3
0x22b9  callvirt instance string [mscorlib]System.Object::ToString()
0x22be  ldloc.s  5
0x22c0  ldloc.s  4
0x22c2  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Experimentation.ExperimentationTelemetry::.ctor(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry)
0x22c7  ldarg.0
0x22c8  ldc.i4.0
0x22c9  call     T0x2B000011
0x22ce  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Experimentation.ExperimentationFactory::.ctor(string, string, class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession, class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Experimentation.IExperimentationTelemetry, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger)
0x22d3  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Experimentation.IExperimentationService [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Experimentation.ExperimentationFactory::CreateExperimentationService()
0x22d8  stloc.s  6
0x22da  ldloc.s  5
0x22dc  ldloc.s  6
0x22de  callvirt instance class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Experimentation.IExperimentationService [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Experimentation.IExperimentationService::GetExperimentationService()
0x22e3  ldsfld   string Microsoft.VisualStudio.Setup.ProgramConstants::BackgroundDownloadExeName
0x22e8  ldloc.3
0x22e9  brtrue.s loc_22EE
0x22eb  ldnull
0x22ec  br.s     loc_22F4
0x22ee  ldloc.3
0x22ef  callvirt instance string [mscorlib]System.Object::ToString()
0x22f4  call     class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.RemoteSettingsService [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.RemoteSettingsServiceFactory::Create(class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Telemetry.TelemetrySession, class [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.Experimentation.IExperimentationService, string, string)
0x22f9  stloc.s  7
0x22fb  ldloc.s  4
0x22fd  ldloc.s  7
0x22ff  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TelemetrySamplingDecorator::Create(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRemoteSettingsService)
0x2304  stloc.s  8
0x2306  ldarg.0
0x2307  ldloc.s  8
0x2309  ldc.i4.0
0x230a  ldc.i4.0
0x230b  callvirt T0x2B000029
0x2310  ldarg.0
0x2311  ldloc.s  7
0x2313  ldc.i4.0
0x2314  ldc.i4.0
0x2315  callvirt T0x2B00002A
0x231a  ret
```
