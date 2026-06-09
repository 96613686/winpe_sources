# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileWatcherManager::ConfigFileChanged

- ea: `0x90d0`
- end: `0x920d`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileWatcherManager::ConfigFileChanged`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x6f30`
- `0x72f0`
- `0x90d0`
- `0x9210`
- `0xa960`

## string_xrefs

- `0x91f1`: `Error occured with a config file change. New config file will not be used. Error: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x90d0  ldarg.2
0x90d1  callvirt instance valuetype [System]System.IO.WatcherChangeTypes [System]System.IO.FileSystemEventArgs::get_ChangeType()
0x90d6  ldc.i4.s 0xD
0x90d8  and
0x90d9  brfalse.s loc_90F3
0x90db  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x90e0  ldarg.2
0x90e1  callvirt instance string [System]System.IO.FileSystemEventArgs::get_Name()
0x90e6  ldarg.0
0x90e7  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_configFileName
0x90ec  callvirt instance int32 [mscorlib]System.StringComparer::Compare(string, string)
0x90f1  brfalse.s loc_90F8
0x90f3  leave    loc_920C
0x90f8  ldarg.0
0x90f9  ldfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.RSConfigurationFileWatcherManager::m_lastChangedTime
0x90fe  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x9103  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x9108  brfalse.s loc_912C
0x910a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x910f  ldarg.0
0x9110  ldfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.RSConfigurationFileWatcherManager::m_lastChangedTime
0x9115  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x911a  ldarg.0
0x911b  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Diagnostics.RSConfigurationFileWatcherManager::m_minTime
0x9120  call     bool [mscorlib]System.TimeSpan::op_LessThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x9125  brfalse.s loc_912C
0x9127  leave    loc_920C
0x912c  ldarg.0
0x912d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x9132  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.RSConfigurationFileWatcherManager::m_lastChangedTime
0x9137  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x913c  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x9141  brfalse.s loc_9153
0x9143  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x9148  ldc.i4.3
0x9149  ldstr    aHandlingFileCh// "Handling File Changes"
0x914e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x9153  ldarg.0
0x9154  ldfld    object Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_configChangeLockObject
0x9159  stloc.0
0x915a  ldc.i4.0
0x915b  stloc.1
0x915c  ldloc.0
0x915d  ldloca.s 1
0x915f  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x9164  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0x9169  ldc.i4.3
0x916a  beq.s    loc_9171
0x916c  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.NativeXEMethods::AlterXESessions()
0x9171  ldarg.0
0x9172  callvirt instance class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::LoadConfiguration()
0x9177  stloc.2
0x9178  ldarg.0
0x9179  ldloc.2
0x917a  ldarg.0
0x917b  ldfld    class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_properties
0x9180  call     instance bool Microsoft.ReportingServices.Diagnostics.RSConfigurationFileWatcherManager::PropertiesAreEqual(class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties1, class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties2)
0x9185  brtrue.s loc_91B4
0x9187  ldarg.0
0x9188  ldloc.2
0x9189  stfld    class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_properties
0x918e  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x9193  ldc.i4.s 0x6D
0x9195  ldc.i4.1
0x9196  newarr   [mscorlib]System.Object
0x919b  dup
0x919c  ldc.i4.0
0x919d  ldarg.0
0x919e  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_configFileName
0x91a3  stelem.ref
0x91a4  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteInformation(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Event, object[])
0x91a9  ldarg.0
0x91aa  ldloc.2
0x91ab  ldc.i4.1
0x91ac  ldarg.0
0x91ad  callvirt instance void Microsoft.ReportingServices.Diagnostics.RSConfigurationManager::ChangeConfiguration(class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties, bool resetProperties, class Microsoft.ReportingServices.Diagnostics.RSConfigurationManager source)
0x91b2  br.s     loc_91D0
0x91b4  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x91b9  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x91be  brfalse.s loc_91D0
0x91c0  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x91c5  ldc.i4.3
0x91c6  ldstr    aPropertiesAreU// "Properties are unchanged from previous "...
0x91cb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x91d0  leave.s  loc_91DC
0x91d2  ldloc.1
0x91d3  brfalse.s loc_91DB
0x91d5  ldloc.0
0x91d6  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x91db  endfinally
0x91dc  leave.s  loc_920C
0x91de  stloc.3
0x91df  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x91e4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x91e9  brfalse.s loc_920A
0x91eb  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_Tracer
0x91f0  ldc.i4.1
0x91f1  ldstr    aErrorOccuredWi// "Error occured with a config file change"...
0x91f6  ldc.i4.1
0x91f7  newarr   [mscorlib]System.Object
0x91fc  dup
0x91fd  ldc.i4.0
0x91fe  ldloc.3
0x91ff  callvirt instance string [mscorlib]System.Object::ToString()
0x9204  stelem.ref
0x9205  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x920a  leave.s  loc_920C
0x920c  ret
```
