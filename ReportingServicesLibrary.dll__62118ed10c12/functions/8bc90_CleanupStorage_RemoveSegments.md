# CleanupStorage::RemoveSegments

- ea: `0x8bc90`
- end: `0x8bcf0`
- name: `CleanupStorage::RemoveSegments`
- size: `96`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x5dcf0`

## callees

- `0x8bc60`
- `0x8bc90`

## string_xrefs

- `0x8bc91`: `RemoveSegment`
- `0x8bca9`: `@DeleteCountPermanent`
- `0x8bcc0`: `@DeleteCountTemp`

## pseudocode

```c

```

## disassembly

```asm
0x8bc90  ldarg.0
0x8bc91  ldstr    aRemovesegment// "RemoveSegment"
0x8bc96  ldnull
0x8bc97  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x8bc9c  stloc.0
0x8bc9d  ldloc.0
0x8bc9e  call     int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCleanupTimeoutSeconds()
0x8bca3  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32)
0x8bca8  ldloc.0
0x8bca9  ldstr    aDeletecountper// "@DeleteCountPermanent"
0x8bcae  ldc.i4.8
0x8bcaf  call     int32 CleanupStorage::get_SegmentCountPerBatch()
0x8bcb4  box      [mscorlib]System.Int32
0x8bcb9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x8bcbe  pop
0x8bcbf  ldloc.0
0x8bcc0  ldstr    aDeletecounttem// "@DeleteCountTemp"
0x8bcc5  ldc.i4.8
0x8bcc6  call     int32 CleanupStorage::get_SegmentCountPerBatch()
0x8bccb  box      [mscorlib]System.Int32
0x8bcd0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x8bcd5  pop
0x8bcd6  ldloc.0
0x8bcd7  callvirt instance object [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteScalar()
0x8bcdc  unbox.any [mscorlib]System.Int32
0x8bce1  stloc.1
0x8bce2  leave.s  loc_8BCEE
0x8bce4  ldloc.0
0x8bce5  brfalse.s loc_8BCED
0x8bce7  ldloc.0
0x8bce8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8bced  endfinally
0x8bcee  ldloc.1
0x8bcef  ret
```
