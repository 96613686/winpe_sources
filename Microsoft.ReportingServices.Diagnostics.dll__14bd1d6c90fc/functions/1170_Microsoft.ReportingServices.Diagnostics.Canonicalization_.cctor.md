# Microsoft.ReportingServices.Diagnostics.Canonicalization::.cctor

- ea: `0x1170`
- end: `0x11e2`
- name: `Microsoft.ReportingServices.Diagnostics.Canonicalization::.cctor`
- size: `114`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x118b`: `MSReportBuilder.exe.manifest`
- `0x11ae`: `/*/{0}:dependency/{0}:dependentAssembly[@dependencyType='install' and @codebase]`

## pseudocode

```c

```

## disassembly

```asm
0x1170  ldc.i4.1
0x1171  newarr   [mscorlib]System.String
0x1176  dup
0x1177  ldc.i4.0
0x1178  ldstr    aReportbuilder3// "ReportBuilder_3_0_0_0.application"
0x117d  stelem.ref
0x117e  stsfld   string[] Microsoft.ReportingServices.Diagnostics.Canonicalization::RBApplicationFiles
0x1183  ldc.i4.1
0x1184  newarr   [mscorlib]System.String
0x1189  dup
0x118a  ldc.i4.0
0x118b  ldstr    aMsreportbuilde// "MSReportBuilder.exe.manifest"
0x1190  stelem.ref
0x1191  stsfld   string[] Microsoft.ReportingServices.Diagnostics.Canonicalization::RBManifestFiles
0x1196  ldc.i4.1
0x1197  newarr   [mscorlib]System.String
0x119c  dup
0x119d  ldc.i4.0
0x119e  ldstr    aRptbuilder3// "RptBuilder_3"
0x11a3  stelem.ref
0x11a4  stsfld   string[] Microsoft.ReportingServices.Diagnostics.Canonicalization::RBSubdirs
0x11a9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11ae  ldstr    a0Dependency0De// "/*/{0}:dependency/{0}:dependentAssembly"...
0x11b3  ldstr    aDefault// "default"
0x11b8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x11bd  stsfld   string Microsoft.ReportingServices.Diagnostics.Canonicalization::XPathAssembly
0x11c2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11c7  ldstr    a0FileName// "/*/{0}:file[@name]"
0x11cc  ldstr    aDefault// "default"
0x11d1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x11d6  stsfld   string Microsoft.ReportingServices.Diagnostics.Canonicalization::XPathFile
0x11db  ldnull
0x11dc  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.ReportingServices.Diagnostics.Canonicalization::m_reportbuilderFiles
0x11e1  ret
```
