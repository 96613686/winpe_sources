# Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetReportServerBinDirectory

- ea: `0x6f30`
- end: `0x6f6f`
- name: `Microsoft.ReportingServices.Diagnostics.ExtensionClassFactory::GetReportServerBinDirectory`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x6ee0`

## callees

- `0x6f30`

## string_xrefs

- `0x6f35`: `ReportServerPath`

## pseudocode

```c

```

## disassembly

```asm
0x6f30  call     class [System]System.Collections.Specialized.NameValueCollection [System.Configuration]System.Configuration.ConfigurationManager::get_AppSettings()
0x6f35  ldstr    aReportserverpa// "ReportServerPath"
0x6f3a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6f3f  stloc.0
0x6f40  ldloc.0
0x6f41  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6f46  brtrue.s loc_6F56
0x6f48  ldloc.0
0x6f49  ldstr    aBin_0// "bin"
0x6f4e  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x6f53  stloc.0
0x6f54  br.s     loc_6F6D
0x6f56  call     string [mscorlib]System.IO.Directory::GetCurrentDirectory()
0x6f5b  stloc.0
0x6f5c  ldloc.0
0x6f5d  ldstr    aPortal// "Portal"
0x6f62  ldstr    aReportserverBi// "ReportServer\\Bin"
0x6f67  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x6f6c  stloc.0
0x6f6d  ldloc.0
0x6f6e  ret
```
