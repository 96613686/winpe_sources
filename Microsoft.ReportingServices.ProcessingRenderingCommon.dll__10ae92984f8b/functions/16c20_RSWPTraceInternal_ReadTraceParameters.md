# RSWPTraceInternal::ReadTraceParameters

- ea: `0x16c20`
- end: `0x16edd`
- name: `RSWPTraceInternal::ReadTraceParameters`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x16650`

## callees

- `0xd150`
- `0xd1a0`
- `0x16b80`
- `0x16c20`
- `0x16ee0`
- `0x180c0`
- `0x180e0`
- `0x18100`
- `0x18140`
- `0x18160`
- `0x18180`
- `0x181a0`
- `0x181c0`

## string_xrefs

- `0x16d54`: `FormatException parsing KeepFilesForDays in RSTrace section of config file.`
- `0x16d67`: `OverflowException parsing KeepFilesForDays in RSTrace section of config file.`
- `0x16ddd`: `Setting prefixes (Time:{0}, PID:{1}, ThreadId:{2}, AppDomain:{3})`
- `0x16e2c`: `overwrite`

## pseudocode

```c

```

## disassembly

```asm
0x16c20  ldarg.0
0x16c21  callvirt instance class RSTraceConfig RSWPTraceInternal::get_TraceConfig()
0x16c26  callvirt instance string RSTraceConfig::get_TraceListeners()
0x16c2b  stloc.0
0x16c2c  ldarg.0
0x16c2d  ldc.i4.0
0x16c2e  stfld    unsigned int32 RSWPTraceInternal::m_ListenersToInstall
0x16c33  ldc.i4.m1
0x16c34  ldloc.0
0x16c35  ldstr    aDebugwindow// "debugwindow"
0x16c3a  ldc.i4.4
0x16c3b  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x16c40  beq.s    loc_16C50
0x16c42  ldarg.0
0x16c43  ldarg.0
0x16c44  ldfld    unsigned int32 RSWPTraceInternal::m_ListenersToInstall
0x16c49  ldc.i4.1
0x16c4a  or
0x16c4b  stfld    unsigned int32 RSWPTraceInternal::m_ListenersToInstall
0x16c50  ldc.i4.m1
0x16c51  ldloc.0
0x16c52  ldstr    aFile_0// "file"
0x16c57  ldc.i4.4
0x16c58  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x16c5d  beq.s    loc_16C6D
0x16c5f  ldarg.0
0x16c60  ldarg.0
0x16c61  ldfld    unsigned int32 RSWPTraceInternal::m_ListenersToInstall
0x16c66  ldc.i4.2
0x16c67  or
0x16c68  stfld    unsigned int32 RSWPTraceInternal::m_ListenersToInstall
0x16c6d  ldc.i4.m1
0x16c6e  ldloc.0
0x16c6f  ldstr    aStdout// "stdout"
0x16c74  ldc.i4.4
0x16c75  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x16c7a  beq.s    loc_16C8A
0x16c7c  ldarg.0
0x16c7d  ldarg.0
0x16c7e  ldfld    unsigned int32 RSWPTraceInternal::m_ListenersToInstall
0x16c83  ldc.i4.4
0x16c84  or
0x16c85  stfld    unsigned int32 RSWPTraceInternal::m_ListenersToInstall
0x16c8a  ldarg.0
0x16c8b  ldarg.0
0x16c8c  callvirt instance class RSTraceConfig RSWPTraceInternal::get_TraceConfig()
0x16c91  callvirt instance string RSTraceConfig::get_FileName()
0x16c96  stfld    string RSWPTraceInternal::m_traceFileName
0x16c9b  ldarg.0
0x16c9c  callvirt instance class RSTraceConfig RSWPTraceInternal::get_TraceConfig()
0x16ca1  callvirt instance int32 RSTraceConfig::get_FileSizeLimitMB()
0x16ca6  ldc.i4.1
0x16ca7  bge.s    loc_16CB6
0x16ca9  ldarg.0
0x16caa  ldc.i4   0x100000
0x16caf  stfld    int32 RSWPTraceInternal::m_maxFileSizeBytes
0x16cb4  br.s     loc_16CD3
0x16cb6  ldarg.0
0x16cb7  ldarg.0
0x16cb8  callvirt instance class RSTraceConfig RSWPTraceInternal::get_TraceConfig()
0x16cbd  callvirt instance int32 RSTraceConfig::get_FileSizeLimitMB()
0x16cc2  ldc.i4   0x400
0x16cc7  mul.ovf
0x16cc8  ldc.i4   0x400
0x16ccd  mul.ovf
0x16cce  stfld    int32 RSWPTraceInternal::m_maxFileSizeBytes
0x16cd3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x16cd8  ldc.i4.4
0x16cd9  ldstr    aSettingMaxFile// "Setting max file size to {0} bytes"
0x16cde  ldc.i4.1
0x16cdf  newarr   [mscorlib]System.Object
0x16ce4  dup
0x16ce5  ldc.i4.0
0x16ce6  ldarg.0
0x16ce7  ldfld    int32 RSWPTraceInternal::m_maxFileSizeBytes
0x16cec  box      [mscorlib]System.Int32
0x16cf1  stelem.ref
0x16cf2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x16cf7  ldarg.0
0x16cf8  callvirt instance class RSTraceConfig RSWPTraceInternal::get_TraceConfig()
0x16cfd  callvirt instance string RSTraceConfig::get_KeepFilesForDays()
0x16d02  brfalse.s loc_16D27
0x16d04  ldarg.0
0x16d05  callvirt instance class RSTraceConfig RSWPTraceInternal::get_TraceConfig()
0x16d0a  callvirt instance string RSTraceConfig::get_KeepFilesForDays()
0x16d0f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16d14  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x16d19  stloc.1
0x16d1a  ldloc.1
0x16d1b  ldc.i4.1
0x16d1c  bge.s    loc_16D20
0x16d1e  ldc.i4.1
0x16d1f  stloc.1
0x16d20  ldarg.0
0x16d21  ldloc.1
0x16d22  stfld    int32 RSWPTraceInternal::m_keepFileForDays
0x16d27  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x16d2c  ldc.i4.4
0x16d2d  ldstr    aSettingPreserv// "Setting preserve files to {0} days"
0x16d32  ldc.i4.1
0x16d33  newarr   [mscorlib]System.Object
0x16d38  dup
0x16d39  ldc.i4.0
0x16d3a  ldarg.0
0x16d3b  ldfld    int32 RSWPTraceInternal::m_keepFileForDays
0x16d40  box      [mscorlib]System.Int32
0x16d45  stelem.ref
0x16d46  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x16d4b  leave.s  loc_16D73
0x16d4d  pop
0x16d4e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x16d53  ldc.i4.1
0x16d54  ldstr    aFormatexceptio// "FormatException parsing KeepFilesForDay"...
0x16d59  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x16d5e  leave.s  loc_16D73
0x16d60  pop
0x16d61  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x16d66  ldc.i4.1
0x16d67  ldstr    aOverflowexcept// "OverflowException parsing KeepFilesForD"...
0x16d6c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x16d71  leave.s  loc_16D73
0x16d73  ldarg.0
0x16d74  callvirt instance class RSTraceConfig RSWPTraceInternal::get_TraceConfig()
0x16d79  callvirt instance string RSTraceConfig::get_Prefix()
0x16d7e  stloc.0
0x16d7f  ldc.i4.m1
0x16d80  ldloc.0
0x16d81  ldstr    aTime// "time"
0x16d86  ldc.i4.4
0x16d87  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x16d8c  beq.s    loc_16D95
0x16d8e  ldarg.0
0x16d8f  ldc.i4.1
0x16d90  stfld    bool RSWPTraceInternal::m_IsTimePrefixed
0x16d95  ldc.i4.m1
0x16d96  ldloc.0
0x16d97  ldstr    aPid// "pid"
0x16d9c  ldc.i4.4
0x16d9d  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x16da2  beq.s    loc_16DAB
0x16da4  ldarg.0
0x16da5  ldc.i4.1
0x16da6  stfld    bool RSWPTraceInternal::m_IsPidPrefixed
0x16dab  ldc.i4.m1
0x16dac  ldloc.0
0x16dad  ldstr    aTid// "tid"
0x16db2  ldc.i4.4
0x16db3  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x16db8  beq.s    loc_16DC1
0x16dba  ldarg.0
0x16dbb  ldc.i4.1
0x16dbc  stfld    bool RSWPTraceInternal::m_IsTidPrefixed
0x16dc1  ldc.i4.m1
0x16dc2  ldloc.0
0x16dc3  ldstr    aAppdomain// "appdomain"
0x16dc8  ldc.i4.4
0x16dc9  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x16dce  beq.s    loc_16DD7
0x16dd0  ldarg.0
0x16dd1  ldc.i4.1
0x16dd2  stfld    bool RSWPTraceInternal::m_IsAppDomainPrefixed
0x16dd7  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x16ddc  ldc.i4.4
0x16ddd  ldstr    aSettingPrefixe// "Setting prefixes (Time:{0}, PID:{1}, Th"...
0x16de2  ldc.i4.4
0x16de3  newarr   [mscorlib]System.Object
0x16de8  dup
0x16de9  ldc.i4.0
0x16dea  ldarg.0
0x16deb  ldfld    bool RSWPTraceInternal::m_IsTimePrefixed
0x16df0  box      [mscorlib]System.Boolean
0x16df5  stelem.ref
0x16df6  dup
0x16df7  ldc.i4.1
0x16df8  ldarg.0
0x16df9  ldfld    bool RSWPTraceInternal::m_IsPidPrefixed
0x16dfe  box      [mscorlib]System.Boolean
0x16e03  stelem.ref
0x16e04  dup
0x16e05  ldc.i4.2
0x16e06  ldarg.0
0x16e07  ldfld    bool RSWPTraceInternal::m_IsTidPrefixed
0x16e0c  box      [mscorlib]System.Boolean
0x16e11  stelem.ref
0x16e12  dup
0x16e13  ldc.i4.3
0x16e14  ldstr    aAppdomain// "appdomain"
0x16e19  stelem.ref
0x16e1a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x16e1f  ldarg.0
0x16e20  callvirt instance class RSTraceConfig RSWPTraceInternal::get_TraceConfig()
0x16e25  callvirt instance string RSTraceConfig::get_TraceFileMode()
0x16e2a  stloc.0
0x16e2b  ldloc.0
0x16e2c  ldstr    aOverwrite// "overwrite"
0x16e31  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16e36  brtrue.s loc_16E47
0x16e38  ldloc.0
0x16e39  ldstr    aAppend// "append"
0x16e3e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16e43  brtrue.s loc_16E50
0x16e45  br.s     loc_16E59
0x16e47  ldarg.0
0x16e48  ldc.i4.1
0x16e49  stfld    valuetype TraceFileMode RSWPTraceInternal::m_TraceFileMode
0x16e4e  br.s     loc_16E60
0x16e50  ldarg.0
0x16e51  ldc.i4.2
0x16e52  stfld    valuetype TraceFileMode RSWPTraceInternal::m_TraceFileMode
0x16e57  br.s     loc_16E60
0x16e59  ldarg.0
0x16e5a  ldc.i4.0
0x16e5b  stfld    valuetype TraceFileMode RSWPTraceInternal::m_TraceFileMode
0x16e60  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x16e65  ldc.i4.4
0x16e66  ldstr    aSettingTraceFi// "Setting trace file mode to {0}"
0x16e6b  ldc.i4.1
0x16e6c  newarr   [mscorlib]System.Object
0x16e71  dup
0x16e72  ldc.i4.0
0x16e73  ldarg.0
0x16e74  ldfld    valuetype TraceFileMode RSWPTraceInternal::m_TraceFileMode
0x16e79  box      TraceFileMode
0x16e7e  stelem.ref
0x16e7f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x16e84  ldarg.0
0x16e85  ldarg.0
0x16e86  ldfld    valuetype [System]System.Diagnostics.TraceLevel RSWPTraceInternal::m_defaultTraceLevel
0x16e8b  box      [System]System.Diagnostics.TraceLevel
0x16e90  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x16e95  ldarg.0
0x16e96  callvirt instance class RSTraceConfig RSWPTraceInternal::get_TraceConfig()
0x16e9b  callvirt instance string RSTraceConfig::get_DefaultTraceSwitch()
0x16ea0  ldc.i4.1
0x16ea1  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x16ea6  unbox.any [System]System.Diagnostics.TraceLevel
0x16eab  stfld    valuetype [System]System.Diagnostics.TraceLevel RSWPTraceInternal::m_defaultTraceLevel
0x16eb0  leave.s  loc_16EB5
0x16eb2  pop
0x16eb3  leave.s  loc_16EB5
0x16eb5  ldarg.0
0x16eb6  ldarg.0
0x16eb7  callvirt instance class RSTraceConfig RSWPTraceInternal::get_TraceConfig()
0x16ebc  callvirt instance string RSTraceConfig::get_Components()
0x16ec1  call     instance void RSWPTraceInternal::FillComponentTable(string componentsString)
0x16ec6  ldarg.0
0x16ec7  ldftn    instance void RSWPTraceInternal::<ReadTraceParameters>b__64_0()
0x16ecd  newobj   instance void Microsoft.ReportingServices.Diagnostics.ContextBody::.ctor(object object, native int method)
0x16ed2  call     void Microsoft.ReportingServices.Diagnostics.RevertImpersonationContext::Run(class Microsoft.ReportingServices.Diagnostics.ContextBody callback)
0x16ed7  leave.s  loc_16EDC
0x16ed9  pop
0x16eda  rethrow
0x16edc  ret
```
