# Microsoft.ReportingServices.ReportProcessing.ReportProcessing::DeserializeReport_2

- ea: `0x179db0`
- end: `0x179e03`
- name: `Microsoft.ReportingServices.ReportProcessing.ReportProcessing::DeserializeReport_2`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x179d90`
- `0x179da0`

## callees

- `0x179db0`
- `0x195010`
- `0x195750`
- `0x1d0530`
- `0x1d0580`
- `0x1dba90`
- `0x1dbcf0`
- `0x1dbdf0`
- `0x23f3a0`

## string_xrefs

- `0x179db3`: `CompiledDefinition`

## pseudocode

```c

```

## disassembly

```asm
0x179db0  ldnull
0x179db1  stloc.0
0x179db2  ldarg.0
0x179db3  ldstr    aCompileddefini// "CompiledDefinition"
0x179db8  ldc.i4.0
0x179db9  ldloca.s 1
0x179dbb  callvirt instance class [mscorlib]System.IO.Stream GetReportChunk::Invoke(string name, valuetype ReportChunkTypes type, [out] string& mimeType)
0x179dc0  stloc.0
0x179dc1  ldloc.0
0x179dc2  newobj   instance void Microsoft.ReportingServices.ReportProcessing.Persistence.IntermediateFormatReader::.ctor(class [mscorlib]System.IO.Stream stream)
0x179dc7  stloc.2
0x179dc8  ldloc.2
0x179dc9  ldarg.1
0x179dca  callvirt instance class Microsoft.ReportingServices.ReportProcessing.Report Microsoft.ReportingServices.ReportProcessing.Persistence.IntermediateFormatReader::ReadReport(class Microsoft.ReportingServices.ReportProcessing.ReportItem parent)
0x179dcf  stloc.3
0x179dd0  ldarg.2
0x179dd1  ldloc.2
0x179dd2  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.ReportProcessing.Persistence.IntermediateFormatReader::get_DefinitionObjects()
0x179dd7  stind.ref
0x179dd8  ldloc.3
0x179dd9  callvirt instance class Microsoft.ReportingServices.ReportProcessing.IntermediateFormatVersion Microsoft.ReportingServices.ReportProcessing.Report::get_IntermediateFormatVersion()
0x179dde  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.IntermediateFormatVersion::get_IsOldVersion()
0x179de3  brfalse.s loc_179DF1
0x179de5  ldloc.3
0x179de6  call     void Microsoft.ReportingServices.ReportProcessing.Upgrade.Upgrader::UpgradeToCurrent(class Microsoft.ReportingServices.ReportProcessing.Report report)
0x179deb  ldloc.3
0x179dec  call     void Microsoft.ReportingServices.ReportProcessing.Upgrade.Upgrader::UpgradeDatasetIDs(class Microsoft.ReportingServices.ReportProcessing.Report report)
0x179df1  ldloc.3
0x179df2  stloc.s  4
0x179df4  leave.s  loc_179E00
0x179df6  ldloc.0
0x179df7  brfalse.s loc_179DFF
0x179df9  ldloc.0
0x179dfa  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x179dff  endfinally
0x179e00  ldloc.s  4
0x179e02  ret
```
