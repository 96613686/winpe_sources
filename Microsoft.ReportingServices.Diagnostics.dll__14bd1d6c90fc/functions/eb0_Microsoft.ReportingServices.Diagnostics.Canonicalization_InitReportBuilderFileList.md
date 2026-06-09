# Microsoft.ReportingServices.Diagnostics.Canonicalization::InitReportBuilderFileList

- ea: `0xeb0`
- end: `0xf64`
- name: `Microsoft.ReportingServices.Diagnostics.Canonicalization::InitReportBuilderFileList`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xeb0`
- `0xf70`
- `0x10f0`

## string_xrefs

- `0xf03`: `InitReportBuilderFileList: RBManifestFiles.Length == RBSubdirs.Length`

## pseudocode

```c

```

## disassembly

```asm
0xeb0  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xeb5  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0xeba  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.ReportingServices.Diagnostics.Canonicalization::m_reportbuilderFiles
0xebf  ldsfld   string[] Microsoft.ReportingServices.Diagnostics.Canonicalization::RBApplicationFiles
0xec4  stloc.0
0xec5  ldc.i4.0
0xec6  stloc.1
0xec7  br.s     loc_EE8
0xec9  ldloc.0
0xeca  ldloc.1
0xecb  ldelem.ref
0xecc  stloc.2
0xecd  ldsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.ReportingServices.Diagnostics.Canonicalization::m_reportbuilderFiles
0xed2  ldloc.2
0xed3  ldsfld   string [mscorlib]System.String::Empty
0xed8  ldc.i4.0
0xed9  call     string Microsoft.ReportingServices.Diagnostics.Canonicalization::GetRBFilePath(string file, string subdir, bool deployExtension)
0xede  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xee3  pop
0xee4  ldloc.1
0xee5  ldc.i4.1
0xee6  add
0xee7  stloc.1
0xee8  ldloc.1
0xee9  ldloc.0
0xeea  ldlen
0xeeb  conv.i4
0xeec  blt.s    loc_EC9
0xeee  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_HttpRuntimeTracer()
0xef3  ldsfld   string[] Microsoft.ReportingServices.Diagnostics.Canonicalization::RBManifestFiles
0xef8  ldlen
0xef9  conv.i4
0xefa  ldsfld   string[] Microsoft.ReportingServices.Diagnostics.Canonicalization::RBSubdirs
0xeff  ldlen
0xf00  conv.i4
0xf01  ceq
0xf03  ldstr    aInitreportbuil// "InitReportBuilderFileList: RBManifestFi"...
0xf08  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0xf0d  ldc.i4.0
0xf0e  stloc.3
0xf0f  br.s     loc_F59
0xf11  ldsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.ReportingServices.Diagnostics.Canonicalization::m_reportbuilderFiles
0xf16  ldsfld   string[] Microsoft.ReportingServices.Diagnostics.Canonicalization::RBManifestFiles
0xf1b  ldloc.3
0xf1c  ldelem.ref
0xf1d  ldsfld   string[] Microsoft.ReportingServices.Diagnostics.Canonicalization::RBSubdirs
0xf22  ldloc.3
0xf23  ldelem.ref
0xf24  ldc.i4.0
0xf25  call     string Microsoft.ReportingServices.Diagnostics.Canonicalization::GetRBFilePath(string file, string subdir, bool deployExtension)
0xf2a  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0xf2f  pop
0xf30  ldarg.0
0xf31  ldsfld   string[] Microsoft.ReportingServices.Diagnostics.Canonicalization::RBSubdirs
0xf36  ldloc.3
0xf37  ldelem.ref
0xf38  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xf3d  ldsfld   string[] Microsoft.ReportingServices.Diagnostics.Canonicalization::RBManifestFiles
0xf42  ldloc.3
0xf43  ldelem.ref
0xf44  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xf49  ldsfld   string[] Microsoft.ReportingServices.Diagnostics.Canonicalization::RBSubdirs
0xf4e  ldloc.3
0xf4f  ldelem.ref
0xf50  call     void Microsoft.ReportingServices.Diagnostics.Canonicalization::AddFilesInManifest(string manifestFile, string subdir)
0xf55  ldloc.3
0xf56  ldc.i4.1
0xf57  add
0xf58  stloc.3
0xf59  ldloc.3
0xf5a  ldsfld   string[] Microsoft.ReportingServices.Diagnostics.Canonicalization::RBManifestFiles
0xf5f  ldlen
0xf60  conv.i4
0xf61  blt.s    loc_F11
0xf63  ret
```
