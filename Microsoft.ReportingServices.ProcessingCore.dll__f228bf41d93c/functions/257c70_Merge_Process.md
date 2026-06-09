# Merge::Process

- ea: `0x257c70`
- end: `0x258106`
- name: `Merge::Process`
- size: `1174`
- prototype: ``
- caller_count: `2`
- callee_count: `51`
- tags: `broker_com_uri`

## callers

- `0x1798d0`
- `0x247450`

## callees

- `0x17d060`
- `0x1803e0`
- `0x18f300`
- `0x18f330`
- `0x18f6c0`
- `0x195350`
- `0x195750`
- `0x1958a0`
- `0x1958c0`
- `0x195b20`
- `0x195c00`
- `0x195c10`
- `0x195c20`
- `0x195c50`
- `0x1a8330`
- `0x1a8350`
- `0x1c9050`
- `0x1d08a0`
- `0x1d08b0`
- `0x1d22c0`
- `0x23f350`
- `0x23fb90`
- `0x23fc30`
- `0x2404f0`
- `0x240530`
- `0x240540`
- `0x2406a0`
- `0x2406c0`
- `0x2406e0`
- `0x2408f0`
- `0x240910`
- `0x240990`
- `0x2409b0`
- `0x240bc0`
- `0x240c30`
- `0x241880`
- `0x246770`
- `0x257c70`
- `0x258230`
- `0x258510`
- `0x258720`
- `0x258850`
- `0x258900`
- `0x258910`
- `0x2589b0`
- `0x2589e0`
- `0x2589f0`
- `0x258b80`
- `0x258bc0`
- `0x26e1a0`

## string_xrefs

- `0x257f4e`: `The processing of all data sources has been completed.`

## pseudocode

```c

```

## disassembly

```asm
0x257c70  ldnull
0x257c71  stloc.0
0x257c72  ldc.i4.0
0x257c73  stloc.1
0x257c74  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x257c79  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x257c7e  brfalse.s loc_257CB2
0x257c80  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x257c85  ldc.i4.4
0x257c86  ldstr    aOnePassProcess// "One Pass Processing? {0}"
0x257c8b  ldc.i4.1
0x257c8c  newarr   [mscorlib]System.Object
0x257c91  dup
0x257c92  ldc.i4.0
0x257c93  ldarg.0
0x257c94  ldfld    class Microsoft.ReportingServices.ReportProcessing.Report Merge::m_report
0x257c99  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.Report::get_MergeOnePass()
0x257c9e  brtrue.s loc_257CA7
0x257ca0  ldstr    aNo_0// "No"
0x257ca5  br.s     loc_257CAC
0x257ca7  ldstr    aYes_0// "Yes"
0x257cac  stelem.ref
0x257cad  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x257cb2  ldarg.0
0x257cb3  ldfld    class Microsoft.ReportingServices.ReportProcessing.Report Merge::m_report
0x257cb8  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ImageStreamNames Microsoft.ReportingServices.ReportProcessing.Report::get_ImageStreamNames()
0x257cbd  stloc.2
0x257cbe  ldarg.0
0x257cbf  ldfld    bool Merge::m_fetchImageStreams
0x257cc4  brfalse  loc_257DCD
0x257cc9  ldloc.2
0x257cca  brfalse  loc_257DCD
0x257ccf  ldc.i4.0
0x257cd0  ldloc.2
0x257cd1  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x257cd6  bge      loc_257DCD
0x257cdb  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ImageStreamNames::.ctor()
0x257ce0  stloc.3
0x257ce1  ldloc.2
0x257ce2  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.Hashtable::GetEnumerator()
0x257ce7  stloc.s  4
0x257ce9  br       loc_257DA9
0x257cee  ldloc.s  4
0x257cf0  callvirt instance object [mscorlib]System.Collections.IDictionaryEnumerator::get_Key()
0x257cf5  castclass [mscorlib]System.String
0x257cfa  stloc.s  5
0x257cfc  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x257d01  ldloc.s  5
0x257d03  ldnull
0x257d04  cgt.un
0x257d06  ldstr    aTheUrlToThisIm// "The URL to this image should not be nul"...
0x257d0b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x257d10  ldnull
0x257d11  stloc.s  6
0x257d13  ldnull
0x257d14  stloc.s  7
0x257d16  ldloc.s  4
0x257d18  callvirt instance object [mscorlib]System.Collections.IDictionaryEnumerator::get_Value()
0x257d1d  castclass Microsoft.ReportingServices.ReportProcessing.ImageInfo
0x257d22  stloc.s  8
0x257d24  ldarg.0
0x257d25  ldfld    class ProcessingContext Merge::m_processingContext
0x257d2a  ldloc.s  5
0x257d2c  ldc.i4.7
0x257d2d  ldloc.s  8
0x257d2f  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ImageInfo::get_StreamName()
0x257d34  ldloca.s 7
0x257d36  ldloca.s 6
0x257d38  call     bool RuntimeRICollection::GetExternalImage(class ProcessingContext processingContext, string currentPath, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, [out] unsigned int8[]& imageData, [out] string& mimeType)
0x257d3d  pop
0x257d3e  ldloc.s  7
0x257d40  brfalse.s loc_257DA9
0x257d42  ldarg.0
0x257d43  ldfld    class ProcessingContext Merge::m_processingContext
0x257d48  callvirt instance class CreateReportChunk ProcessingContext::get_CreateReportChunkCallback()
0x257d4d  brfalse.s loc_257DA9
0x257d4f  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x257d54  stloc.s  0xA
0x257d56  ldloca.s 0xA
0x257d58  constrained. [mscorlib]System.Guid
0x257d5e  callvirt instance string [mscorlib]System.Object::ToString()
0x257d63  stloc.s  9
0x257d65  ldarg.0
0x257d66  ldfld    class ProcessingContext Merge::m_processingContext
0x257d6b  callvirt instance class CreateReportChunk ProcessingContext::get_CreateReportChunkCallback()
0x257d70  ldloc.s  9
0x257d72  ldc.i4.1
0x257d73  ldloc.s  6
0x257d75  callvirt instance class [mscorlib]System.IO.Stream CreateReportChunk::Invoke(string name, valuetype ReportChunkTypes type, string mimeType)
0x257d7a  stloc.s  0xB
0x257d7c  ldloc.s  0xB
0x257d7e  ldloc.s  7
0x257d80  ldc.i4.0
0x257d81  ldloc.s  7
0x257d83  ldlen
0x257d84  conv.i4
0x257d85  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x257d8a  leave.s  loc_257D98
0x257d8c  ldloc.s  0xB
0x257d8e  brfalse.s loc_257D97
0x257d90  ldloc.s  0xB
0x257d92  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x257d97  endfinally
0x257d98  ldloc.3
0x257d99  ldloc.s  5
0x257d9b  ldloc.s  9
0x257d9d  ldloc.s  6
0x257d9f  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ImageInfo::.ctor(string streamName, string mimeType)
0x257da4  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ImageStreamNames::set_Item(string url, class Microsoft.ReportingServices.ReportProcessing.ImageInfo value)
0x257da9  ldloc.s  4
0x257dab  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x257db0  brtrue   loc_257CEE
0x257db5  ldarg.0
0x257db6  ldfld    class Microsoft.ReportingServices.ReportProcessing.Report Merge::m_report
0x257dbb  ldloc.3
0x257dbc  callvirt instance void Microsoft.ReportingServices.ReportProcessing.Report::set_ImageStreamNames(class Microsoft.ReportingServices.ReportProcessing.ImageStreamNames value)
0x257dc1  ldarg.0
0x257dc2  ldfld    class ProcessingContext Merge::m_processingContext
0x257dc7  ldloc.3
0x257dc8  callvirt instance void ProcessingContext::set_ImageStreamNames(class Microsoft.ReportingServices.ReportProcessing.ImageStreamNames value)
0x257dcd  ldarg.0
0x257dce  ldarg.1
0x257dcf  ldc.i4.0
0x257dd0  call     instance void Merge::Init(class Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection parameters, bool prefetchDataOnly)
0x257dd5  ldarg.0
0x257dd6  call     instance void Merge::EvaluateAndSetReportLanguage()
0x257ddb  ldarg.0
0x257ddc  ldfld    class ProcessingContext Merge::m_processingContext
0x257de1  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModelImpl ProcessingContext::get_ReportObjectModel()
0x257de6  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.DataSourcesImpl Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModelImpl::get_DataSourcesImpl()
0x257deb  brtrue.s loc_257E0D
0x257ded  ldarg.0
0x257dee  ldfld    class ProcessingContext Merge::m_processingContext
0x257df3  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModelImpl ProcessingContext::get_ReportObjectModel()
0x257df8  ldarg.0
0x257df9  ldfld    class Microsoft.ReportingServices.ReportProcessing.Report Merge::m_report
0x257dfe  callvirt instance int32 Microsoft.ReportingServices.ReportProcessing.Report::get_DataSourceCount()
0x257e03  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.DataSourcesImpl::.ctor(int32 size)
0x257e08  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.ObjectModelImpl::set_DataSourcesImpl(class Microsoft.ReportingServices.ReportProcessing.ReportObjectModel.DataSourcesImpl value)
0x257e0d  ldarg.0
0x257e0e  ldfld    class Microsoft.ReportingServices.ReportProcessing.Report Merge::m_report
0x257e13  callvirt instance int32 Microsoft.ReportingServices.ReportProcessing.Report::get_DataSourceCount()
0x257e18  brfalse  loc_257FBC
0x257e1d  ldarg.0
0x257e1e  ldfld    class Microsoft.ReportingServices.ReportProcessing.Report Merge::m_report
0x257e23  callvirt instance class Microsoft.ReportingServices.ReportProcessing.DataSourceList Microsoft.ReportingServices.ReportProcessing.Report::get_DataSources()
0x257e28  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x257e2d  stloc.s  0xC
0x257e2f  ldc.i4.1
0x257e30  stloc.1
0x257e31  ldc.i4.0
0x257e32  stloc.s  0xF
0x257e34  br.s     loc_257E6B
0x257e36  ldarg.0
0x257e37  ldfld    class RuntimeDataSourceNodeList Merge::m_runtimeDataSourceNodes
0x257e3c  ldarg.0
0x257e3d  ldfld    class Microsoft.ReportingServices.ReportProcessing.Report Merge::m_report
0x257e42  ldarg.0
0x257e43  ldfld    class Microsoft.ReportingServices.ReportProcessing.Report Merge::m_report
0x257e48  callvirt instance class Microsoft.ReportingServices.ReportProcessing.DataSourceList Microsoft.ReportingServices.ReportProcessing.Report::get_DataSources()
0x257e4d  ldloc.s  0xF
0x257e4f  callvirt instance class Microsoft.ReportingServices.ReportProcessing.DataSource Microsoft.ReportingServices.ReportProcessing.DataSourceList::get_Item(int32 index)
0x257e54  ldarg.0
0x257e55  ldfld    class ProcessingContext Merge::m_processingContext
0x257e5a  newobj   instance void ReportRuntimeDataSourceNode::.ctor(class Microsoft.ReportingServices.ReportProcessing.Report report, class Microsoft.ReportingServices.ReportProcessing.DataSource dataSource, class ProcessingContext processingContext)
0x257e5f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x257e64  pop
0x257e65  ldloc.s  0xF
0x257e67  ldc.i4.1
0x257e68  add
0x257e69  stloc.s  0xF
0x257e6b  ldloc.s  0xF
0x257e6d  ldloc.s  0xC
0x257e6f  blt.s    loc_257E36
0x257e71  ldarg.0
0x257e72  ldftn    instance void Merge::AbortHandler(object sender, class [mscorlib]System.EventArgs e)
0x257e78  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x257e7d  stloc.0
0x257e7e  ldarg.0
0x257e7f  ldfld    class ProcessingContext Merge::m_processingContext
0x257e84  callvirt instance class AbortHelper ProcessingContext::get_AbortInfo()
0x257e89  ldloc.0
0x257e8a  callvirt instance void AbortHelper::add_ProcessingAbortEvent(class [mscorlib]System.EventHandler value)
0x257e8f  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x257e94  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x257e99  brfalse.s loc_257EAB
0x257e9b  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x257ea0  ldc.i4.4
0x257ea1  ldstr    aAbortHandlerRe// "Abort handler registered."
0x257ea6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x257eab  ldnull
0x257eac  stloc.s  0xE
0x257eae  ldloc.s  0xC
0x257eb0  ldc.i4.1
0x257eb1  ble.s    loc_257F06
0x257eb3  ldloc.s  0xC
0x257eb5  ldc.i4.1
0x257eb6  sub
0x257eb7  newobj   instance void ThreadSet::.ctor(int32 threadCount)
0x257ebc  stloc.s  0xE
0x257ebe  ldc.i4.1
0x257ebf  stloc.s  0x10
0x257ec1  br.s     loc_257F00
0x257ec3  ldarg.0
0x257ec4  ldfld    class RuntimeDataSourceNodeList Merge::m_runtimeDataSourceNodes
0x257ec9  ldloc.s  0x10
0x257ecb  callvirt instance class RuntimeDataSourceNode RuntimeDataSourceNodeList::get_Item(int32 index)
0x257ed0  stloc.s  0xD
0x257ed2  ldloc.s  0xD
0x257ed4  ldarg.2
0x257ed5  ldc.i4.0
0x257ed6  callvirt instance void RuntimeDataSourceNode::InitProcessingParams(bool mergeTran, bool prefetchDataOnly)
0x257edb  ldarg.0
0x257edc  ldfld    class ProcessingContext Merge::m_processingContext
0x257ee1  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IJobContext ProcessingContext::get_JobContext()
0x257ee6  ldloc.s  0xD
0x257ee8  ldftn    instance void RuntimeDataSourceNode::ProcessConcurrent(object threadSet)
0x257eee  newobj   instance void [mscorlib]System.Threading.WaitCallback::.ctor(object, native int)
0x257ef3  ldloc.s  0xE
0x257ef5  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IJobContext::TryQueueWorkItem(class [mscorlib]System.Threading.WaitCallback, object)
0x257efa  ldloc.s  0x10
0x257efc  ldc.i4.1
0x257efd  add
0x257efe  stloc.s  0x10
0x257f00  ldloc.s  0x10
0x257f02  ldloc.s  0xC
0x257f04  blt.s    loc_257EC3
0x257f06  ldarg.0
0x257f07  ldfld    class RuntimeDataSourceNodeList Merge::m_runtimeDataSourceNodes
0x257f0c  ldc.i4.0
0x257f0d  callvirt instance class RuntimeDataSourceNode RuntimeDataSourceNodeList::get_Item(int32 index)
0x257f12  stloc.s  0xD
0x257f14  ldloc.s  0xD
0x257f16  ldarg.2
0x257f17  ldc.i4.0
0x257f18  callvirt instance void RuntimeDataSourceNode::InitProcessingParams(bool mergeTran, bool prefetchDataOnly)
0x257f1d  ldloc.s  0xD
0x257f1f  ldnull
0x257f20  callvirt instance void RuntimeDataSourceNode::ProcessConcurrent(object threadSet)
0x257f25  ldarg.0
0x257f26  ldfld    class ProcessingContext Merge::m_processingContext
0x257f2b  callvirt instance void ProcessingContext::CheckAndThrowIfAborted()
0x257f30  ldloc.s  0xC
0x257f32  ldc.i4.1
0x257f33  ble.s    loc_257F3C
0x257f35  ldloc.s  0xE
0x257f37  callvirt instance void ThreadSet::WaitForCompletion()
0x257f3c  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x257f41  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x257f46  brfalse.s loc_257F58
0x257f48  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x257f4d  ldc.i4.4
0x257f4e  ldstr    aTheProcessingO// "The processing of all data sources has "...
0x257f53  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x257f58  ldarg.0
0x257f59  ldfld    class ProcessingContext Merge::m_processingContext
0x257f5e  callvirt instance void ProcessingContext::CheckAndThrowIfAborted()
0x257f63  ldc.i4.0
0x257f64  stloc.s  0x11
0x257f66  br.s     loc_257FB6
0x257f68  ldarg.0
0x257f69  ldfld    class RuntimeDataSourceNodeList Merge::m_runtimeDataSourceNodes
0x257f6e  ldloc.s  0x11
0x257f70  callvirt instance class RuntimeDataSourceNode RuntimeDataSourceNodeList::get_Item(int32 index)
0x257f75  stloc.s  0xD
0x257f77  ldloc.1
0x257f78  brfalse.s loc_257F82
0x257f7a  ldloc.s  0xD
0x257f7c  callvirt instance bool RuntimeDataSourceNode::get_NoRows()
0x257f81  stloc.1
0x257f82  ldarg.0
0x257f83  ldfld    class ProcessingContext Merge::m_processingContext
0x257f88  callvirt instance bool ProcessingContext::get_SaveSnapshotData()
0x257f8d  brfalse.s loc_257FB0
0x257f8f  ldarg.0
0x257f90  ldfld    class ProcessingContext Merge::m_processingContext
0x257f95  callvirt instance bool ProcessingContext::get_ErrorSavingSnapshotData()
0x257f9a  brfalse.s loc_257FB0
0x257f9c  ldarg.0
0x257f9d  ldfld    class ProcessingContext Merge::m_processingContext
0x257fa2  callvirt instance bool ProcessingContext::get_StopSaveSnapshotDataOnError()
0x257fa7  brfalse.s loc_257FB0
0x257fa9  ldloc.s  0xD
0x257fab  callvirt instance void RuntimeDataSourceNode::EraseDataChunk()
0x257fb0  ldloc.s  0x11
0x257fb2  ldc.i4.1
0x257fb3  add
0x257fb4  stloc.s  0x11
0x257fb6  ldloc.s  0x11
0x257fb8  ldloc.s  0xC
0x257fba  blt.s    loc_257F68
0x257fbc  ldarg.0
0x257fbd  ldfld    class Microsoft.ReportingServices.ReportProcessing.Report Merge::m_report
0x257fc2  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.Report::get_ParametersNotUsedInQuery()
0x257fc7  brfalse.s loc_257FF9
0x257fc9  ldarg.0
0x257fca  ldfld    class ProcessingContext Merge::m_processingContext
0x257fcf  callvirt instance bool ProcessingContext::get_ErrorSavingSnapshotData()
0x257fd4  brfalse.s loc_257FF9
0x257fd6  ldc.i4.0
  ... truncated ...
```
