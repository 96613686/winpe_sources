# Microsoft.ReportingServices.Library.SegmentChunkDbInterface::GetFormattedOpenSegmentedChunkQueryText

- ea: `0x69320`
- end: `0x69365`
- name: `Microsoft.ReportingServices.Library.SegmentChunkDbInterface::GetFormattedOpenSegmentedChunkQueryText`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x69370`

## callees

- `0x69320`

## string_xrefs

- `0x69332`: `TempDB`
- `0x6934f`: `\nif (@IsPermanent = 1) begin		\n	select	@ChunkId = ChunkId,\n			@ChunkFlags = ChunkFlags,\n            @MimeType = MimeType\n	from dbo.SegmentedChunk chunk\n	where chunk.SnapshotDataId = @SnapshotId and chunk.ChunkName = @ChunkName and chunk.ChunkType = @ChunkType\n	\n	select	csm.SegmentId, 				\n			csm.LogicalByteCount as LogicalSegmentLength, \n			csm.ActualByteCount as ActualSegmentLength		\n	from ChunkSegmentMapping csm		\n	where csm.ChunkId = @ChunkId\n	order by csm.StartByte `

## pseudocode

```c

```

## disassembly

```asm
0x69320  ldsfld   string Microsoft.ReportingServices.Library.SegmentChunkDbInterface::m_formattedOpenSegmentedChunk
0x69325  brtrue.s loc_6935F
0x69327  ldarg.0
0x69328  call     instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_Connection()
0x6932d  callvirt instance string [System.Data]System.Data.Common.DbConnection::get_Database()
0x69332  ldstr    aTempdb// "TempDB"
0x69337  call     string [mscorlib]System.String::Concat(string, string)
0x6933c  stloc.0
0x6933d  ldarg.0
0x6933e  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x69343  ldloc.0
0x69344  callvirt instance string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::EscapeAndBracketDBName(string)
0x69349  stloc.1
0x6934a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6934f  ldstr    aIfIspermanent1// "\r\nif (@IsPermanent = 1) begin\t\t\r\n"...
0x69354  ldloc.1
0x69355  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x6935a  stsfld   string Microsoft.ReportingServices.Library.SegmentChunkDbInterface::m_formattedOpenSegmentedChunk
0x6935f  ldsfld   string Microsoft.ReportingServices.Library.SegmentChunkDbInterface::m_formattedOpenSegmentedChunk
0x69364  ret
```
