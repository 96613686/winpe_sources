# <>c__DisplayClass18_0::<LoadDocument>b__0

- ea: `0x10340`
- end: `0x103da`
- name: `<>c__DisplayClass18_0::<LoadDocument>b__0`
- size: `154`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x10340`

## string_xrefs

- `0x103c3`: `Could not find config file at '`

## pseudocode

```c

```

## disassembly

```asm
0x10340  ldc.i4.3
0x10341  stloc.0
0x10342  ldc.i4.0
0x10343  stloc.1
0x10344  ldarg.0
0x10345  ldfld    class Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager <>c__DisplayClass18_0::<>4__this
0x1034a  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_configLocation
0x1034f  ldarg.0
0x10350  ldfld    class Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager <>c__DisplayClass18_0::<>4__this
0x10355  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_configFileName
0x1035a  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1035f  stloc.2
0x10360  ldc.i4.0
0x10361  stloc.3
0x10362  br.s     loc_1038B
0x10364  nop
0x10365  ldc.i4.s 0x64
0x10367  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x1036c  ldloc.2
0x1036d  call     bool [mscorlib]System.IO.File::Exists(string)
0x10372  brfalse.s loc_10382
0x10374  ldarg.0
0x10375  ldfld    class [System.Xml]System.Xml.XmlDocument <>c__DisplayClass18_0::xmlConfiguration
0x1037a  ldloc.2
0x1037b  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.XmlUtil::SafeOpenXmlDocumentFile(class [System.Xml]System.Xml.XmlDocument, string)
0x10380  ldc.i4.1
0x10381  stloc.1
0x10382  leave.s  loc_1038F
0x10384  pop
0x10385  leave.s  loc_10387
0x10387  ldloc.3
0x10388  ldc.i4.1
0x10389  add
0x1038a  stloc.3
0x1038b  ldloc.3
0x1038c  ldloc.0
0x1038d  blt.s    loc_10364
0x1038f  ldloc.1
0x10390  brtrue.s loc_103D9
0x10392  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x10397  ldc.i4   0x82
0x1039c  ldc.i4.2
0x1039d  newarr   [mscorlib]System.Object
0x103a2  dup
0x103a3  ldc.i4.0
0x103a4  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x103a9  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_SourceName()
0x103ae  stelem.ref
0x103af  dup
0x103b0  ldc.i4.1
0x103b1  ldarg.0
0x103b2  ldfld    class Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager <>c__DisplayClass18_0::<>4__this
0x103b7  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_configFileName
0x103bc  stelem.ref
0x103bd  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteError(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Event, object[])
0x103c2  ldnull
0x103c3  ldstr    aCouldNotFindCo// "Could not find config file at '"
0x103c8  ldloc.2
0x103c9  ldstr    asc_177C6// "'"
0x103ce  call     string [mscorlib]System.String::Concat(string, string, string)
0x103d3  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(class [mscorlib]System.Exception, string)
0x103d8  throw
0x103d9  ret
```
