# Microsoft.BIServer.HostingEnvironment.Logger::Create_1

- ea: `0x1140`
- end: `0x131b`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::Create_1`
- size: `475`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf10`
- `0xf80`

## callees

- `0xe80`
- `0x1140`
- `0x1320`
- `0x1340`
- `0x1370`
- `0x1550`
- `0x5350`
- `0x55a0`

## string_xrefs

- `0x1153`: `Attempt to reconfigure static logger. #{0} Do once per process.`
- `0x11df`: `${longdate}|${level:uppercase=true}|${threadid}|${message}${exception:format=ToString}`
- `0x12b0`: `File Logger created: {0} - level {1}, will roll at {2} Mb, process id {3}`
- `0x12f5`: `Metrics Logger created: {0} - level {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1140  newobj   instance void <>c__DisplayClass48_0::.ctor()
0x1145  stloc.0
0x1146  ldsflda  int32 Microsoft.BIServer.HostingEnvironment.Logger::_configCount
0x114b  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x1150  ldc.i4.1
0x1151  ble.s    loc_116D
0x1153  ldstr    aAttemptToRecon// "Attempt to reconfigure static logger. #"...
0x1158  ldsfld   int32 Microsoft.BIServer.HostingEnvironment.Logger::_configCount
0x115d  box      [mscorlib]System.Int32
0x1162  call     string [mscorlib]System.String::Format(string, object)
0x1167  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x116c  throw
0x116d  ldarg.1
0x116e  call     class [NLog]NLog.LogLevel Microsoft.BIServer.HostingEnvironment.Logger::Convert(valuetype Level level)
0x1173  stloc.1
0x1174  ldarg.2
0x1175  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x117a  brfalse.s loc_1188
0x117c  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x1181  callvirt instance string [mscorlib]System.AppDomain::get_BaseDirectory()
0x1186  starg.s  2
0x1188  ldarg.2
0x1189  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x118e  starg.s  2
0x1190  ldarg.2
0x1191  ldarg.0
0x1192  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1197  stloc.2
0x1198  call     class [NLog]NLog.Config.ConfigurationItemFactory [NLog]NLog.Config.ConfigurationItemFactory::get_Default()
0x119d  callvirt instance class [NLog]NLog.Config.INamedItemFactory`2<class [NLog]NLog.LayoutRenderers.LayoutRenderer, class [mscorlib]System.Type> [NLog]NLog.Config.ConfigurationItemFactory::get_LayoutRenderers()
0x11a2  ldstr    aDailydate// "DailyDate"
0x11a7  ldtoken  DailyDateLayoutRenderer
0x11ac  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11b1  callvirt instance void class [NLog]NLog.Config.INamedItemFactory`2<class [NLog]NLog.LayoutRenderers.LayoutRenderer, class [mscorlib]System.Type>::RegisterDefinition(string, var<u1>)
0x11b6  call     class [NLog]NLog.Config.ConfigurationItemFactory [NLog]NLog.Config.ConfigurationItemFactory::get_Default()
0x11bb  callvirt instance class [NLog]NLog.Config.INamedItemFactory`2<class [NLog]NLog.LayoutRenderers.LayoutRenderer, class [mscorlib]System.Type> [NLog]NLog.Config.ConfigurationItemFactory::get_LayoutRenderers()
0x11c0  ldstr    aArchivedate// "ArchiveDate"
0x11c5  ldtoken  ArchiveDateLayoutRenderer
0x11ca  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x11cf  callvirt instance void class [NLog]NLog.Config.INamedItemFactory`2<class [NLog]NLog.LayoutRenderers.LayoutRenderer, class [mscorlib]System.Type>::RegisterDefinition(string, var<u1>)
0x11d4  ldsfld   class [NLog]NLog.Logger Microsoft.BIServer.HostingEnvironment.Logger::Log
0x11d9  ldloc.2
0x11da  ldstr    aLog// ".log"
0x11df  ldstr    aLongdateLevelU// "${longdate}|${level:uppercase=true}|${t"...
0x11e4  call     class [NLog]NLog.Targets.FileTarget Microsoft.BIServer.HostingEnvironment.Logger::CreateFileTarget(class [NLog]NLog.Logger logger, string filePathBase, string suffix, string format)
0x11e9  stsfld   class [NLog]NLog.Targets.FileTarget Microsoft.BIServer.HostingEnvironment.Logger::_eventLogFileTarget
0x11ee  ldsfld   class [NLog]NLog.Targets.FileTarget Microsoft.BIServer.HostingEnvironment.Logger::_eventLogFileTarget
0x11f3  ldloc.2
0x11f4  ldstr    aLog_0// "_{#}.log"
0x11f9  call     string [mscorlib]System.String::Concat(string, string)
0x11fe  call     class [NLog]NLog.Layouts.Layout [NLog]NLog.Layouts.Layout::op_Implicit(string)
0x1203  callvirt instance void [NLog]NLog.Targets.FileTarget::set_ArchiveFileName(class [NLog]NLog.Layouts.Layout)
0x1208  ldsfld   class [NLog]NLog.Targets.FileTarget Microsoft.BIServer.HostingEnvironment.Logger::_eventLogFileTarget
0x120d  ldstr    aYyyyMmDdHhMmSs// "yyyy_MM_dd_HH_mm_ss"
0x1212  callvirt instance void [NLog]NLog.Targets.FileTarget::set_ArchiveDateFormat(string)
0x1217  ldsfld   class [NLog]NLog.Targets.FileTarget Microsoft.BIServer.HostingEnvironment.Logger::_eventLogFileTarget
0x121c  ldc.i4.3
0x121d  callvirt instance void [NLog]NLog.Targets.FileTarget::set_ArchiveNumbering(valuetype [NLog]NLog.Targets.ArchiveNumberingMode)
0x1222  ldsfld   class [NLog]NLog.Targets.FileTarget Microsoft.BIServer.HostingEnvironment.Logger::_eventLogFileTarget
0x1227  ldarg.3
0x1228  ldc.i4   0x100000
0x122d  mul
0x122e  conv.i8
0x122f  callvirt instance void [NLog]NLog.Targets.FileTarget::set_ArchiveAboveSize(int64)
0x1234  ldsfld   class [NLog]NLog.Logger Microsoft.BIServer.HostingEnvironment.Logger::Log
0x1239  ldsfld   class [NLog]NLog.Targets.FileTarget Microsoft.BIServer.HostingEnvironment.Logger::_eventLogFileTarget
0x123e  ldarg.s  5
0x1240  ldloc.1
0x1241  call     class [NLog]NLog.Targets.Wrappers.AsyncTargetWrapper Microsoft.BIServer.HostingEnvironment.Logger::SetAsyncLogging(class [NLog]NLog.Logger log, class [NLog]NLog.Targets.FileTarget fileTarget, int32 asyncQueueLimit, class [NLog]NLog.LogLevel level)
0x1246  stloc.3
0x1247  ldnull
0x1248  stloc.s  4
0x124a  ldloc.0
0x124b  ldsfld   class [NLog]NLog.Targets.FileTarget Microsoft.BIServer.HostingEnvironment.Logger::_eventLogFileTarget
0x1250  call     string Microsoft.BIServer.HostingEnvironment.Logger::FilePathFromTarget(class [NLog]NLog.Targets.FileTarget target)
0x1255  stfld    string <>c__DisplayClass48_0::logFileName
0x125a  ldnull
0x125b  stloc.s  5
0x125d  ldsfld   bool Microsoft.BIServer.HostingEnvironment.Logger::_metricsEnabled
0x1262  brfalse.s loc_1299
0x1264  ldsfld   class [NLog]NLog.Logger Microsoft.BIServer.HostingEnvironment.Logger::Metrics
0x1269  ldloc.2
0x126a  ldstr    aMtrx// ".mtrx"
0x126f  ldstr    aLongdateMessag// "${longdate}, ${message}"
0x1274  call     class [NLog]NLog.Targets.FileTarget Microsoft.BIServer.HostingEnvironment.Logger::CreateFileTarget(class [NLog]NLog.Logger logger, string filePathBase, string suffix, string format)
0x1279  stloc.s  6
0x127b  ldloc.s  6
0x127d  call     string Microsoft.BIServer.HostingEnvironment.Logger::FilePathFromTarget(class [NLog]NLog.Targets.FileTarget target)
0x1282  stloc.s  5
0x1284  ldsfld   class [NLog]NLog.Logger Microsoft.BIServer.HostingEnvironment.Logger::Metrics
0x1289  ldloc.s  6
0x128b  ldarg.s  5
0x128d  ldsfld   class [NLog]NLog.LogLevel [NLog]NLog.LogLevel::Info
0x1292  call     class [NLog]NLog.Targets.Wrappers.AsyncTargetWrapper Microsoft.BIServer.HostingEnvironment.Logger::SetAsyncLogging(class [NLog]NLog.Logger log, class [NLog]NLog.Targets.FileTarget fileTarget, int32 asyncQueueLimit, class [NLog]NLog.LogLevel level)
0x1297  stloc.s  4
0x1299  call     void [NLog]NLog.LogManager::ReconfigExistingLoggers()
0x129e  ldloc.0
0x129f  ldftn    instance void <>c__DisplayClass48_0::<Create>b__0()
0x12a5  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x12aa  call     class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::Run(class [mscorlib]System.Action)
0x12af  pop
0x12b0  ldstr    aFileLoggerCrea// "File Logger created: {0} - level {1}, w"...
0x12b5  ldc.i4.4
0x12b6  newarr   [mscorlib]System.Object
0x12bb  dup
0x12bc  ldc.i4.0
0x12bd  ldloc.0
0x12be  ldfld    string <>c__DisplayClass48_0::logFileName
0x12c3  stelem.ref
0x12c4  dup
0x12c5  ldc.i4.1
0x12c6  ldarg.1
0x12c7  box      Level
0x12cc  stelem.ref
0x12cd  dup
0x12ce  ldc.i4.2
0x12cf  ldarg.3
0x12d0  box      [mscorlib]System.Int32
0x12d5  stelem.ref
0x12d6  dup
0x12d7  ldc.i4.3
0x12d8  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x12dd  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x12e2  stloc.s  7
0x12e4  ldloca.s 7
0x12e6  call     instance string [mscorlib]System.Int32::ToString()
0x12eb  stelem.ref
0x12ec  call     void Microsoft.BIServer.HostingEnvironment.Logger::Info(string formatString, object[] formatParams)
0x12f1  ldloc.s  5
0x12f3  brfalse.s loc_1312
0x12f5  ldstr    aMetricsLoggerC// "Metrics Logger created: {0} - level {1}"
0x12fa  ldc.i4.2
0x12fb  newarr   [mscorlib]System.Object
0x1300  dup
0x1301  ldc.i4.0
0x1302  ldloc.s  5
0x1304  stelem.ref
0x1305  dup
0x1306  ldc.i4.1
0x1307  ldsfld   class [NLog]NLog.LogLevel [NLog]NLog.LogLevel::Info
0x130c  stelem.ref
0x130d  call     void Microsoft.BIServer.HostingEnvironment.Logger::Info(string formatString, object[] formatParams)
0x1312  ldloc.3
0x1313  ldloc.s  4
0x1315  newobj   instance void LogShutdown::.ctor(class [NLog]NLog.Targets.Wrappers.AsyncTargetWrapper asyncEventLog, [opt] class [NLog]NLog.Targets.Wrappers.AsyncTargetWrapper asyncMetricsLog)
0x131a  ret
```
