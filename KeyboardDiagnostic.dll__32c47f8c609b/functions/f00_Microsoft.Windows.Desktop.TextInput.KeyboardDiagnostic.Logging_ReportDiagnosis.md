# Microsoft.Windows.Desktop.TextInput.KeyboardDiagnostic.Logging::ReportDiagnosis

- ea: `0xf00`
- end: `0xfaf`
- name: `Microsoft.Windows.Desktop.TextInput.KeyboardDiagnostic.Logging::ReportDiagnosis`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x9f0`
- `0xf00`

## pseudocode

```c

```

## disassembly

```asm
0xf00  ldstr    aMicrosoftWindo// "Microsoft.Windows.Desktop.TextInput.Key"...
0xf05  newobj   instance void Microsoft.Diagnostics.Telemetry.TelemetryEventSource::.ctor(string eventSourceName)
0xf0a  stloc.0
0xf0b  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xf10  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentUICulture()
0xf15  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0xf1a  stloc.1
0xf1b  call     string [Windows]Windows.Globalization.Language::get_CurrentInputMethodLanguageTag()
0xf20  stloc.2
0xf21  ldsfld   string [mscorlib]System.String::Empty
0xf26  stloc.3
0xf27  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::CurrentUser
0xf2c  ldstr    aKeyboardLayout// "Keyboard Layout\\Preload"
0xf31  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0xf36  stloc.s  4
0xf38  ldloc.s  4
0xf3a  callvirt instance string[] [mscorlib]Microsoft.Win32.RegistryKey::GetValueNames()
0xf3f  stloc.s  5
0xf41  ldc.i4.0
0xf42  stloc.s  6
0xf44  br.s     loc_F74
0xf46  ldloc.s  5
0xf48  ldloc.s  6
0xf4a  ldelem.ref
0xf4b  stloc.s  7
0xf4d  ldloc.3
0xf4e  ldstr    a01// "{0}={1};"
0xf53  ldloc.s  7
0xf55  ldloc.s  4
0xf57  ldloc.s  7
0xf59  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0xf5e  castclass [mscorlib]System.String
0xf63  call     string [mscorlib]System.String::Format(string, object, object)
0xf68  call     string [mscorlib]System.String::Concat(string, string)
0xf6d  stloc.3
0xf6e  ldloc.s  6
0xf70  ldc.i4.1
0xf71  add
0xf72  stloc.s  6
0xf74  ldloc.s  6
0xf76  ldloc.s  5
0xf78  ldlen
0xf79  conv.i4
0xf7a  blt.s    loc_F46
0xf7c  leave.s  loc_F8A
0xf7e  ldloc.s  4
0xf80  brfalse.s loc_F89
0xf82  ldloc.s  4
0xf84  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf89  endfinally
0xf8a  ldloc.0
0xf8b  ldstr    aStarted// "Started"
0xf90  ldsfld   valuetype [mscorlib]System.Diagnostics.Tracing.EventSourceOptions Microsoft.Windows.Desktop.TextInput.KeyboardDiagnostic.Logging::telemetryInfoOption
0xf95  ldloc.1
0xf96  ldloc.2
0xf97  ldloc.3
0xf98  newobj   instance void class <>f__AnonymousType0`3<string, string, string>::.ctor(var<u1>, !!T0, var<u1>)
0xf9d  callvirt T0x2B000009
0xfa2  leave.s  loc_FAE
0xfa4  ldloc.0
0xfa5  brfalse.s loc_FAD
0xfa7  ldloc.0
0xfa8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfad  endfinally
0xfae  ret
```
