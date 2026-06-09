# Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::ProcessBatch

- ea: `0x20510`
- end: `0x206be`
- name: `Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::ProcessBatch`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x204a0`

## callees

- `0x98e0`
- `0xe000`
- `0xe010`
- `0x12df0`
- `0x20390`
- `0x20510`
- `0x206e0`
- `0x20b40`
- `0x20bc0`
- `0x20c00`
- `0x21bc0`
- `0x26780`

## string_xrefs

- `0x20648`: `Commit transaction for this changeset`

## pseudocode

```c

```

## disassembly

```asm
0x20510  ldarg.0
0x20511  ldarg.0
0x20512  ldfld    class [mscorlib]System.IO.Stream Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::m_inputStream
0x20517  ldarg.0
0x20518  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::m_headers
0x2051d  ldarg.0
0x2051e  ldfld    string Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::m_httpMethod
0x20523  ldnull
0x20524  call     instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageReader Microsoft.SharePoint.Client.Rest.RestRequestProcessorBase::CreateODataMessageReader(class [mscorlib]System.IO.Stream inputStream, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> headers, string httpMethod, [opt] object target)
0x20529  stloc.0
0x2052a  ldloc.0
0x2052b  callvirt instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchReader [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageReader::CreateODataBatchReader()
0x20530  stloc.1
0x20531  ldarg.0
0x20532  ldfld    class Microsoft.SharePoint.Client.Rest.RestResponseMessage Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::m_responseMessage
0x20537  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter::.ctor(class [Microsoft.Data.OData]Microsoft.Data.OData.IODataResponseMessage)
0x2053c  stloc.2
0x2053d  ldloc.2
0x2053e  callvirt instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchWriter [Microsoft.Data.OData]Microsoft.Data.OData.ODataMessageWriter::CreateODataBatchWriter()
0x20543  stloc.3
0x20544  ldloc.3
0x20545  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchWriter::WriteStartBatch()
0x2054a  ldc.i4.0
0x2054b  stloc.s  4
0x2054d  ldc.i4.0
0x2054e  stloc.s  5
0x20550  br       loc_2067A
0x20555  ldloc.1
0x20556  callvirt instance valuetype [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchReaderState [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchReader::get_State()
0x2055b  stloc.s  0xA
0x2055d  ldloc.s  0xA
0x2055f  switch   loc_2067A, loc_20581, loc_205FB, loc_2063C, loc_2067A, loc_2065E
0x2057c  br       loc_2067A
0x20581  ldarg.0
0x20582  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x20587  ldc.i4   0x59E217
0x2058c  ldc.i4.2
0x2058d  ldstr    aProcessing0Ope// "Processing {0} operation"
0x20592  ldc.i4.1
0x20593  newarr   [mscorlib]System.Object
0x20598  stloc.s  0xB
0x2059a  ldloc.s  0xB
0x2059c  ldc.i4.0
0x2059d  ldloc.s  4
0x2059f  box      [mscorlib]System.Int32
0x205a4  stelem.ref
0x205a5  ldloc.s  0xB
0x205a7  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x205ac  ldloc.1
0x205ad  callvirt instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchOperationRequestMessage [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchReader::CreateOperationRequestMessage()
0x205b2  stloc.s  6
0x205b4  ldloc.3
0x205b5  callvirt instance class [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchOperationResponseMessage [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchWriter::CreateOperationResponseMessage()
0x205ba  stloc.s  7
0x205bc  ldarg.0
0x205bd  ldloc.s  6
0x205bf  ldloc.s  7
0x205c1  ldloc.s  4
0x205c3  call     instance void Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::ProcessOneOperation(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchOperationRequestMessage requestMessage, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchOperationResponseMessage responseMessage, int32 batchItemIndex)
0x205c8  ldloc.s  4
0x205ca  ldc.i4.1
0x205cb  add
0x205cc  stloc.s  4
0x205ce  ldarg.0
0x205cf  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x205d4  ldc.i4   0x59E218
0x205d9  ldc.i4.2
0x205da  ldstr    aProcessed0Oper// "Processed {0} operation"
0x205df  ldc.i4.1
0x205e0  newarr   [mscorlib]System.Object
0x205e5  stloc.s  0xC
0x205e7  ldloc.s  0xC
0x205e9  ldc.i4.0
0x205ea  ldloc.s  4
0x205ec  box      [mscorlib]System.Int32
0x205f1  stelem.ref
0x205f2  ldloc.s  0xC
0x205f4  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x205f9  br.s     loc_2067A
0x205fb  ldarg.0
0x205fc  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x20601  ldc.i4   0x617420
0x20606  ldc.i4.2
0x20607  ldstr    aStartTransacti// "Start transaction for changeset"
0x2060c  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x20611  ldloc.s  5
0x20613  brfalse.s loc_20631
0x20615  ldarg.0
0x20616  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x2061b  ldc.i4   0x617421
0x20620  ldc.i4.1
0x20621  ldstr    aThePreviousCha// "The previous changeset is not closed"
0x20626  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x2062b  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x20630  throw
0x20631  ldarg.0
0x20632  call     instance void Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::StartChangeSet()
0x20637  ldc.i4.1
0x20638  stloc.s  5
0x2063a  br.s     loc_2067A
0x2063c  ldarg.0
0x2063d  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x20642  ldc.i4   0x617422
0x20647  ldc.i4.2
0x20648  ldstr    aCommitTransact// "Commit transaction for this changeset"
0x2064d  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x20652  ldarg.0
0x20653  ldc.i4.0
0x20654  call     instance void Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::EndChangeSet(bool failedChangeSet)
0x20659  ldc.i4.0
0x2065a  stloc.s  5
0x2065c  br.s     loc_2067A
0x2065e  ldarg.0
0x2065f  call     instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.RequestProcessor::get_ServiceHost()
0x20664  ldc.i4   0x59E219
0x20669  ldc.i4.1
0x2066a  ldstr    aErrorWhenProce_0// "Error when processing batch"
0x2066f  callvirt instance void Microsoft.SharePoint.Client.ClientServiceHost::SendTraceTag(unsigned int32 tagId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message)
0x20674  newobj   instance void Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x20679  throw
0x2067a  ldloc.1
0x2067b  callvirt instance bool [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchReader::Read()
0x20680  brtrue   loc_20555
0x20685  leave.s  loc_20693
0x20687  ldloc.s  5
0x20689  brfalse.s loc_20692
0x2068b  ldarg.0
0x2068c  ldc.i4.1
0x2068d  call     instance void Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::EndChangeSet(bool failedChangeSet)
0x20692  endfinally
0x20693  ldloc.3
0x20694  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchWriter::WriteEndBatch()
0x20699  ldloc.3
0x2069a  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataBatchWriter::Flush()
0x2069f  ldarg.0
0x206a0  ldfld    class Microsoft.SharePoint.Client.Rest.RestResponseMessage Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::m_responseMessage
0x206a5  callvirt instance string Microsoft.SharePoint.Client.Rest.RestResponseMessage::GetContentType()
0x206aa  stloc.s  8
0x206ac  ldloc.s  8
0x206ae  ldarg.0
0x206af  call     instance class Microsoft.SharePoint.Utilities.ChunkStreamBuilder Microsoft.SharePoint.Client.Rest.RestBatchRequestProcessor::DetachStreamBuilder()
0x206b4  newobj   instance void Microsoft.SharePoint.Client.RestRequestResult::.ctor(string contentType, class Microsoft.SharePoint.Utilities.ChunkStreamBuilder streamBuilder)
0x206b9  stloc.s  9
0x206bb  ldloc.s  9
0x206bd  ret
```
