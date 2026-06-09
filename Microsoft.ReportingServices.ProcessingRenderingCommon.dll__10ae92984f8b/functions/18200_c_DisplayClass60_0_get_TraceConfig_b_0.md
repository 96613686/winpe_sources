# <>c__DisplayClass60_0::<get_TraceConfig>b__0

- ea: `0x18200`
- end: `0x1825a`
- name: `<>c__DisplayClass60_0::<get_TraceConfig>b__0`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x4cb0`
- `0x4d40`
- `0x16a70`
- `0x17dd0`
- `0x17e30`
- `0x18200`

## string_xrefs

- `0x1820c`: `ReportServer\bin\ReportingServicesService.exe.config`

## pseudocode

```c

```

## disassembly

```asm
0x18200  ldarg.0
0x18201  ldarg.0
0x18202  ldfld    class RSWPTraceInternal <>c__DisplayClass60_0::<>4__this
0x18207  call     instance string RSWPTraceInternal::get_ReportingServicesBaseInstallPath()
0x1820c  ldstr    aReportserverBi_0// "ReportServer\\bin\\ReportingServicesSer"...
0x18211  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x18216  stfld    string <>c__DisplayClass60_0::configFileName
0x1821b  ldarg.0
0x1821c  ldfld    string <>c__DisplayClass60_0::configFileName
0x18221  call     bool [mscorlib]System.IO.File::Exists(string)
0x18226  brfalse.s loc_18246
0x18228  call     class [System.Xml]System.Xml.XmlDocument Microsoft.ReportingServices.Diagnostics.XmlUtil::CreateXmlDocumentWithNullResolver()
0x1822d  stloc.0
0x1822e  ldloc.0
0x1822f  ldarg.0
0x18230  ldfld    string <>c__DisplayClass60_0::configFileName
0x18235  call     void Microsoft.ReportingServices.Diagnostics.XmlUtil::LoadWithNullResolver(class [System.Xml]System.Xml.XmlDocument xmlDocument, string fileLocation)
0x1823a  ldarg.0
0x1823b  ldloc.0
0x1823c  newobj   instance void RSTraceConfig::.ctor(class [System.Xml]System.Xml.XmlDocument configDoc)
0x18241  stfld    class RSTraceConfig <>c__DisplayClass60_0::config
0x18246  ldarg.0
0x18247  ldfld    class RSTraceConfig <>c__DisplayClass60_0::config
0x1824c  brtrue.s loc_18259
0x1824e  ldarg.0
0x1824f  newobj   instance void RSTraceConfig::.ctor()
0x18254  stfld    class RSTraceConfig <>c__DisplayClass60_0::config
0x18259  ret
```
