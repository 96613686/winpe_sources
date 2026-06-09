# Microsoft.ReportingServices.DataExtensions.DataSetDefinition::.ctor_0

- ea: `0x16e4a0`
- end: `0x16e517`
- name: `Microsoft.ReportingServices.DataExtensions.DataSetDefinition::.ctor_0`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x144df0`
- `0x145860`
- `0x14b760`
- `0x16e4a0`
- `0x184250`

## string_xrefs

- `0x16e4c5`: `CompiledDefinition`

## pseudocode

```c

```

## disassembly

```asm
0x16e4a0  ldarg.0
0x16e4a1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x16e4a6  stfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.DataExtensions.DataSetDefinition::m_sharedDataSourceReferenceId
0x16e4ab  ldarg.0
0x16e4ac  call     instance void [mscorlib]System.Object::.ctor()
0x16e4b1  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x16e4b6  ldarg.1
0x16e4b7  ldnull
0x16e4b8  cgt.un
0x16e4ba  ldstr    aSharedDatasetD// "Shared dataset definition chunk factory"...
0x16e4bf  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x16e4c4  ldarg.1
0x16e4c5  ldstr    aCompileddefini// "CompiledDefinition"
0x16e4ca  ldc.i4.s 9
0x16e4cc  ldc.i4.0
0x16e4cd  ldloca.s 0
0x16e4cf  callvirt instance class [mscorlib]System.IO.Stream Microsoft.ReportingServices.ReportProcessing.IChunkFactory::GetChunk(string chunkName, valuetype ReportChunkTypes type, valuetype Microsoft.ReportingServices.ReportProcessing.ChunkMode mode, [out] string& mimeType)
0x16e4d4  stloc.1
0x16e4d5  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x16e4da  ldloc.1
0x16e4db  ldnull
0x16e4dc  cgt.un
0x16e4de  ldstr    aSharedDatasetD_0// "Shared dataset definition stream does n"...
0x16e4e3  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x16e4e8  ldloca.s 2
0x16e4ea  ldloc.1
0x16e4eb  ldnull
0x16e4ec  ldnull
0x16e4ed  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.ProcessingRIFObjectCreator::.ctor(class Microsoft.ReportingServices.ReportIntermediateFormat.IDOwner parentIDOwner, class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem parentReportItem)
0x16e4f2  ldnull
0x16e4f3  call     instance void Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::.ctor(class [mscorlib]System.IO.Stream str, class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IRIFObjectCreator rifObjectCreator, class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.GlobalIDOwnerCollection globalIDOwnersFromOtherStream)
0x16e4f8  ldarg.0
0x16e4f9  ldloca.s 2
0x16e4fb  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IPersistable Microsoft.ReportingServices.ReportIntermediateFormat.Persistence.IntermediateFormatReader::ReadRIFObject()
0x16e500  castclass Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore
0x16e505  stfld    class Microsoft.ReportingServices.ReportIntermediateFormat.DataSetCore Microsoft.ReportingServices.DataExtensions.DataSetDefinition::m_dataSetCore
0x16e50a  leave.s  loc_16E516
0x16e50c  ldloc.1
0x16e50d  brfalse.s loc_16E515
0x16e50f  ldloc.1
0x16e510  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x16e515  endfinally
0x16e516  ret
```
