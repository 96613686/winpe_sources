# Microsoft.BIServer.HostingEnvironment.Logger::.cctor

- ea: `0xcc0`
- end: `0xda1`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::.cctor`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0xca0`
- `0xcc0`
- `0xdb0`

## string_xrefs

- `0xd4f`: `${threadid}|${message}${exception:format=ToString}`
- `0xd90`: `Configured Console Logger with level = {0}`

## pseudocode

```c

```

## disassembly

```asm
0xcc0  newobj   instance void [mscorlib]System.Object::.ctor()
0xcc5  stsfld   object Microsoft.BIServer.HostingEnvironment.Logger::LogHeaderLock
0xcca  ldc.i4.0
0xccb  stsfld   int32 Microsoft.BIServer.HostingEnvironment.Logger::_configCount
0xcd0  ldstr    aEventlog// "eventLog"
0xcd5  call     class [NLog]NLog.Logger [NLog]NLog.LogManager::GetLogger(string)
0xcda  stsfld   class [NLog]NLog.Logger Microsoft.BIServer.HostingEnvironment.Logger::Log
0xcdf  ldstr    aMetrics// "metrics"
0xce4  call     class [NLog]NLog.Logger [NLog]NLog.LogManager::GetLogger(string)
0xce9  stsfld   class [NLog]NLog.Logger Microsoft.BIServer.HostingEnvironment.Logger::Metrics
0xcee  ldstr    aLoggerMetrics// "Logger.Metrics"
0xcf3  ldsfld   string [mscorlib]System.Boolean::FalseString
0xcf8  call     string Microsoft.BIServer.HostingEnvironment.Logger::ConfigValueOrDefault(string key, string defaultValue)
0xcfd  ldsfld   string [mscorlib]System.Boolean::TrueString
0xd02  ldc.i4.3
0xd03  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xd08  stsfld   bool Microsoft.BIServer.HostingEnvironment.Logger::_metricsEnabled
0xd0d  ldstr    aLoggerMetricsM// "Logger.Metrics.MinLogMs"
0xd12  ldstr    a10// "10"
0xd17  call     string Microsoft.BIServer.HostingEnvironment.Logger::ConfigValueOrDefault(string key, string defaultValue)
0xd1c  ldsflda  int32 Microsoft.BIServer.HostingEnvironment.Logger::MetricsMinLogMs
0xd21  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0xd26  pop
0xd27  newobj   instance void [NLog]NLog.Config.LoggingConfiguration::.ctor()
0xd2c  call     void [NLog]NLog.LogManager::set_Configuration(class [NLog]NLog.Config.LoggingConfiguration)
0xd31  call     bool Microsoft.BIServer.HostingEnvironment.Logger::ConsoleAvailable()
0xd36  brfalse.s loc_D9B
0xd38  newobj   instance void [NLog]NLog.Targets.ColoredConsoleTarget::.ctor()
0xd3d  stloc.0
0xd3e  call     class [NLog]NLog.Config.LoggingConfiguration [NLog]NLog.LogManager::get_Configuration()
0xd43  ldstr    aConsole// "console"
0xd48  ldloc.0
0xd49  callvirt instance void [NLog]NLog.Config.LoggingConfiguration::AddTarget(string, class [NLog]NLog.Targets.Target)
0xd4e  ldloc.0
0xd4f  ldstr    aThreadidMessag// "${threadid}|${message}${exception:forma"...
0xd54  call     class [NLog]NLog.Layouts.Layout [NLog]NLog.Layouts.Layout::op_Implicit(string)
0xd59  callvirt instance void [NLog]NLog.Targets.TargetWithLayout::set_Layout(class [NLog]NLog.Layouts.Layout)
0xd5e  ldstr    aLoggerConsolel// "Logger.consoleLevel"
0xd63  ldstr    aInfo// "Info"
0xd68  call     string Microsoft.BIServer.HostingEnvironment.Logger::ConfigValueOrDefault(string key, string defaultValue)
0xd6d  call     class [NLog]NLog.LogLevel [NLog]NLog.LogLevel::FromString(string)
0xd72  stloc.1
0xd73  ldstr    aEventlog// "eventLog"
0xd78  ldloc.1
0xd79  ldloc.0
0xd7a  newobj   instance void [NLog]NLog.Config.LoggingRule::.ctor(string, class [NLog]NLog.LogLevel, class [NLog]NLog.Targets.Target)
0xd7f  stloc.2
0xd80  call     class [NLog]NLog.Config.LoggingConfiguration [NLog]NLog.LogManager::get_Configuration()
0xd85  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [NLog]NLog.Config.LoggingRule> [NLog]NLog.Config.LoggingConfiguration::get_LoggingRules()
0xd8a  ldloc.2
0xd8b  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [NLog]NLog.Config.LoggingRule>::Add(var<u1>)
0xd90  ldstr    aConfiguredCons// "Configured Console Logger with level = "...
0xd95  ldloc.1
0xd96  call     void [mscorlib]System.Console::WriteLine(string, object)
0xd9b  call     void [NLog]NLog.LogManager::ReconfigExistingLoggers()
0xda0  ret
```
