# <>c__DisplayClass8_0::<.ctor>b__0

- ea: `0x880f0`
- end: `0x881b3`
- name: `<>c__DisplayClass8_0::<.ctor>b__0`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x880f0`

## string_xrefs

- `0x8811d`: `Path for directory is not a directory`
- `0x88158`: `Using folder {0} for temporary files.`
- `0x8818a`: `Error create temp folder: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x880f0  ldarg.0
0x880f1  ldfld    string[] <>c__DisplayClass8_0::folders
0x880f6  stloc.0
0x880f7  ldc.i4.0
0x880f8  stloc.1
0x880f9  br       loc_881A9
0x880fe  ldloc.0
0x880ff  ldloc.1
0x88100  ldelem.ref
0x88101  stloc.2
0x88102  ldloc.2
0x88103  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x88108  brtrue.s loc_88111
0x8810a  ldloc.2
0x8810b  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x88110  pop
0x88111  ldloc.2
0x88112  call     valuetype [mscorlib]System.IO.FileAttributes [mscorlib]System.IO.File::GetAttributes(string)
0x88117  ldc.i4.s 0x10
0x88119  and
0x8811a  brtrue.s loc_88128
0x8811c  ldnull
0x8811d  ldstr    aPathForDirecto// "Path for directory is not a directory"
0x88122  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ServerConfigurationErrorException::.ctor(class [mscorlib]System.Exception, string)
0x88127  throw
0x88128  ldarg.0
0x88129  ldfld    class Microsoft.ReportingServices.Library.PartitionManager <>c__DisplayClass8_0::<>4__this
0x8812e  ldloc.2
0x8812f  stfld    string Microsoft.ReportingServices.Library.PartitionManager::m_fileFolder
0x88134  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x88139  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x8813e  brfalse.s loc_88176
0x88140  ldarg.0
0x88141  ldfld    class Microsoft.ReportingServices.Library.PartitionManager <>c__DisplayClass8_0::<>4__this
0x88146  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace/WriteOnce Microsoft.ReportingServices.Library.PartitionManager::m_traceWriteOnce
0x8814b  ldloc.2
0x8814c  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace/WriteOnce::TraceWritten(string)
0x88151  brtrue.s loc_88176
0x88153  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x88158  ldstr    aUsingFolder0Fo// "Using folder {0} for temporary files."
0x8815d  ldc.i4.1
0x8815e  newarr   [mscorlib]System.Object
0x88163  dup
0x88164  ldc.i4.0
0x88165  ldarg.0
0x88166  ldfld    class Microsoft.ReportingServices.Library.PartitionManager <>c__DisplayClass8_0::<>4__this
0x8816b  ldfld    string Microsoft.ReportingServices.Library.PartitionManager::m_fileFolder
0x88170  stelem.ref
0x88171  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x88176  leave.s  loc_881B2
0x88178  stloc.3
0x88179  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x8817e  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x88183  brfalse.s loc_881A3
0x88185  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x8818a  ldstr    aErrorCreateTem// "Error create temp folder: {0}"
0x8818f  ldc.i4.1
0x88190  newarr   [mscorlib]System.Object
0x88195  dup
0x88196  ldc.i4.0
0x88197  ldloc.3
0x88198  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8819d  stelem.ref
0x8819e  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x881a3  leave.s  loc_881A5
0x881a5  ldloc.1
0x881a6  ldc.i4.1
0x881a7  add
0x881a8  stloc.1
0x881a9  ldloc.1
0x881aa  ldloc.0
0x881ab  ldlen
0x881ac  conv.i4
0x881ad  blt      loc_880FE
0x881b2  ret
```
