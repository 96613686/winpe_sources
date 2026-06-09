# Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::CreateProcess

- ea: `0x2970`
- end: `0x2a50`
- name: `Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::CreateProcess`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x2a50`

## callees

- `0x2190`
- `0x2970`

## pseudocode

```c

```

## disassembly

```asm
0x2970  newobj   instance void [System]System.Diagnostics.Process::.ctor()
0x2975  stloc.0
0x2976  ldloc.0
0x2977  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x297c  ldc.i4.1
0x297d  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_WindowStyle(valuetype [System]System.Diagnostics.ProcessWindowStyle)
0x2982  ldloc.0
0x2983  ldc.i4.1
0x2984  callvirt instance void [System]System.Diagnostics.Process::set_EnableRaisingEvents(bool)
0x2989  ldloc.0
0x298a  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x298f  ldarg.0
0x2990  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_analysisServicesExePath
0x2995  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_FileName(string)
0x299a  ldloc.0
0x299b  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x29a0  ldarg.0
0x29a1  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_analysisServicesBasePath
0x29a6  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_WorkingDirectory(string)
0x29ab  ldloc.0
0x29ac  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x29b1  ldc.i4.0
0x29b2  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_UseShellExecute(bool)
0x29b7  ldloc.0
0x29b8  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x29bd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29c2  ldstr    aCN0S1// "-c -n {0} -s \"{1}\""
0x29c7  ldstr    aPbirs// "PBIRS"
0x29cc  ldarg.0
0x29cd  ldfld    string Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_workspacesRootPath
0x29d2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x29d7  callvirt instance void [System]System.Diagnostics.ProcessStartInfo::set_Arguments(string)
0x29dc  ldarg.0
0x29dd  ldfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_processConfig
0x29e2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0x29e7  brfalse.s loc_2A4E
0x29e9  ldarg.0
0x29ea  ldfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_processConfig
0x29ef  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0x29f4  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Count()
0x29f9  ldc.i4.0
0x29fa  ble.s    loc_2A4E
0x29fc  ldarg.0
0x29fd  ldfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ProcessLaunchers.AnalysisServicesProcessLauncher::_processConfig
0x2a02  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.BIServer.BIService.ProcessConfig::get_Config()
0x2a07  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x2a0c  stloc.1
0x2a0d  br.s     loc_2A35
0x2a0f  ldloca.s 1
0x2a11  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x2a16  stloc.2
0x2a17  ldloc.0
0x2a18  callvirt instance class [System]System.Diagnostics.ProcessStartInfo [System]System.Diagnostics.Process::get_StartInfo()
0x2a1d  callvirt instance class [System]System.Collections.Specialized.StringDictionary [System]System.Diagnostics.ProcessStartInfo::get_EnvironmentVariables()
0x2a22  ldloca.s 2
0x2a24  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x2a29  ldloca.s 2
0x2a2b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x2a30  callvirt instance void [System]System.Collections.Specialized.StringDictionary::set_Item(string, string)
0x2a35  ldloca.s 1
0x2a37  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x2a3c  brtrue.s loc_2A0F
0x2a3e  leave.s  loc_2A4E
0x2a40  ldloca.s 1
0x2a42  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x2a48  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a4d  endfinally
0x2a4e  ldloc.0
0x2a4f  ret
```
