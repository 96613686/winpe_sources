# Microsoft.ReportingServices.Diagnostics.RSConfiguration::CalculateProperties

- ea: `0x65e0`
- end: `0x66fb`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::CalculateProperties`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4170`

## callees

- `0x3e40`
- `0x3ff0`
- `0x4130`
- `0x65e0`
- `0x6700`
- `0x6a00`

## pseudocode

```c

```

## disassembly

```asm
0x65e0  ldarg.0
0x65e1  ldarg.0
0x65e2  ldc.i4.1
0x65e3  ldarg.0
0x65e4  ldflda   string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_reportServerUrlHostnameCalculated
0x65e9  call     instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::GetReportServerUrl(bool local, [out] string& hostname)
0x65ee  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_reportServerUrlCalculated
0x65f3  ldarg.0
0x65f4  ldarg.0
0x65f5  ldc.i4.0
0x65f6  ldarg.0
0x65f7  ldflda   string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_reportServerExternalUrlHostnameCalculated
0x65fc  call     instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::GetReportServerUrl(bool local, [out] string& hostname)
0x6601  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_reportServerExternalUrlCalculated
0x6606  ldarg.0
0x6607  ldc.i4.2
0x6608  call     instance bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::IsApplicationUrlSubsetOfReportServer(valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication application)
0x660d  stloc.0
0x660e  ldarg.0
0x660f  ldloc.0
0x6610  brfalse.s loc_662C
0x6612  ldarg.0
0x6613  call     instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_Hostname()
0x6618  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x661d  brfalse.s loc_662C
0x661f  ldarg.0
0x6620  call     instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ReportServerExternalUrl()
0x6625  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x662a  br.s     loc_662D
0x662c  ldc.i4.0
0x662d  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_canTranslateReportManagerRequest
0x6632  ldarg.0
0x6633  ldarg.0
0x6634  call     instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_Hostname()
0x6639  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x663e  brfalse.s loc_664D
0x6640  ldarg.0
0x6641  call     instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_ReportServerExternalUrl()
0x6646  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x664b  br.s     loc_664E
0x664d  ldc.i4.0
0x664e  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_canTranslateReportServerRequest
0x6653  ldarg.0
0x6654  ldarg.0
0x6655  call     instance string Microsoft.ReportingServices.Diagnostics.RSConfiguration::get_UrlRoot()
0x665a  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_urlRootCalculated
0x665f  ldarg.0
0x6660  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_urlRootCalculated
0x6665  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x666a  brfalse.s loc_6678
0x666c  ldarg.0
0x666d  ldarg.0
0x666e  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_reportServerExternalUrlCalculated
0x6673  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_urlRootCalculated
0x6678  ldarg.0
0x6679  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_urlRootCalculated
0x667e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6683  brfalse.s loc_6691
0x6685  ldarg.0
0x6686  ldarg.0
0x6687  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_reportServerUrlCalculated
0x668c  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_urlRootCalculated
0x6691  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6696  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x669b  brfalse.s loc_66FA
0x669d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x66a2  ldc.i4.3
0x66a3  ldstr    aUsingReportSer// "Using report server internal url {0}."
0x66a8  ldc.i4.1
0x66a9  newarr   [mscorlib]System.Object
0x66ae  dup
0x66af  ldc.i4.0
0x66b0  ldarg.0
0x66b1  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_reportServerUrlCalculated
0x66b6  stelem.ref
0x66b7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x66bc  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x66c1  ldc.i4.3
0x66c2  ldstr    aUsingReportSer_0// "Using report server external url {0}."
0x66c7  ldc.i4.1
0x66c8  newarr   [mscorlib]System.Object
0x66cd  dup
0x66ce  ldc.i4.0
0x66cf  ldarg.0
0x66d0  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_reportServerExternalUrlCalculated
0x66d5  stelem.ref
0x66d6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x66db  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x66e0  ldc.i4.3
0x66e1  ldstr    aUsingUrlRoot0// "Using url root {0}."
0x66e6  ldc.i4.1
0x66e7  newarr   [mscorlib]System.Object
0x66ec  dup
0x66ed  ldc.i4.0
0x66ee  ldarg.0
0x66ef  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_urlRootCalculated
0x66f4  stelem.ref
0x66f5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x66fa  ret
```
