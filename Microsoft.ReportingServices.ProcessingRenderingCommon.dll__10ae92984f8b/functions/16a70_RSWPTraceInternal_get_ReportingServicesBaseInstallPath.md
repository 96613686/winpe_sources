# RSWPTraceInternal::get_ReportingServicesBaseInstallPath

- ea: `0x16a70`
- end: `0x16b7c`
- name: `RSWPTraceInternal::get_ReportingServicesBaseInstallPath`
- size: `268`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x16bd0`
- `0x18200`

## callees

- `0x6130`
- `0x10150`
- `0x16a70`

## string_xrefs

- `0x16aaf`: `ReportServerPath`
- `0x16ac5`: `ReportServerPath`

## pseudocode

```c

```

## disassembly

```asm
0x16a70  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x16a75  callvirt instance string [mscorlib]System.Reflection.Assembly::get_CodeBase()
0x16a7a  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x16a7f  stloc.0
0x16a80  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x16a85  callvirt instance valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_CurrentApplication()
0x16a8a  ldc.i4.3
0x16a8b  beq.s    loc_16AAA
0x16a8d  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x16a92  callvirt instance valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_CurrentApplication()
0x16a97  ldc.i4.4
0x16a98  beq.s    loc_16AAA
0x16a9a  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x16a9f  callvirt instance valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_CurrentApplication()
0x16aa4  ldc.i4.5
0x16aa5  bne.un   loc_16B2B
0x16aaa  call     class [System]System.Collections.Specialized.NameValueCollection [System.Configuration]System.Configuration.ConfigurationManager::get_AppSettings()
0x16aaf  ldstr    aReportserverpa// "ReportServerPath"
0x16ab4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16ab9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16abe  brtrue.s loc_16AF1
0x16ac0  call     class [System]System.Collections.Specialized.NameValueCollection [System.Configuration]System.Configuration.ConfigurationManager::get_AppSettings()
0x16ac5  ldstr    aReportserverpa// "ReportServerPath"
0x16aca  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x16acf  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x16ad4  stloc.1
0x16ad5  ldloc.1
0x16ad6  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x16adb  brfalse  loc_16B7A
0x16ae0  ldloc.1
0x16ae1  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x16ae6  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x16aeb  stloc.0
0x16aec  br       loc_16B7A
0x16af1  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x16af6  callvirt instance string [mscorlib]System.Reflection.Assembly::get_CodeBase()
0x16afb  newobj   instance void [System]System.Uri::.ctor(string)
0x16b00  callvirt instance string [System]System.Uri::get_LocalPath()
0x16b05  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x16b0a  stloc.2
0x16b0b  ldloc.2
0x16b0c  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.FileInfo::get_Directory()
0x16b11  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x16b16  brfalse.s loc_16B7A
0x16b18  ldloc.2
0x16b19  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.FileInfo::get_Directory()
0x16b1e  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x16b23  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x16b28  stloc.0
0x16b29  br.s     loc_16B7A
0x16b2b  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x16b30  callvirt instance string [mscorlib]System.Reflection.Assembly::get_CodeBase()
0x16b35  newobj   instance void [System]System.Uri::.ctor(string)
0x16b3a  callvirt instance string [System]System.Uri::get_LocalPath()
0x16b3f  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x16b44  stloc.3
0x16b45  ldloc.3
0x16b46  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.FileInfo::get_Directory()
0x16b4b  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x16b50  brfalse.s loc_16B7A
0x16b52  ldloc.3
0x16b53  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.FileInfo::get_Directory()
0x16b58  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x16b5d  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x16b62  brfalse.s loc_16B7A
0x16b64  ldloc.3
0x16b65  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.FileInfo::get_Directory()
0x16b6a  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x16b6f  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x16b74  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x16b79  stloc.0
0x16b7a  ldloc.0
0x16b7b  ret
```
