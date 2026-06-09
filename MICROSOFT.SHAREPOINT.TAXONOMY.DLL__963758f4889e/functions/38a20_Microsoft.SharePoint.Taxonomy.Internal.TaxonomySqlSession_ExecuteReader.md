# Microsoft.SharePoint.Taxonomy.Internal.TaxonomySqlSession::ExecuteReader

- ea: `0x38a20`
- end: `0x38b10`
- name: `Microsoft.SharePoint.Taxonomy.Internal.TaxonomySqlSession::ExecuteReader`
- size: `240`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x179b0`
- `0x19be0`
- `0x19cf0`
- `0x19e40`
- `0x38d50`

## callees

- `0x378f0`
- `0x379a0`
- `0x38a20`
- `0x38b10`
- `0x579c0`

## string_xrefs

- `0x38a20`: `Taxonomy SqlSession.ExecuteReader`
- `0x38a4b`: `Taxonomy ExecuteReader: `

## pseudocode

```c

```

## disassembly

```asm
0x38a20  ldstr    aTaxonomySqlses_0// "Taxonomy SqlSession.ExecuteReader"
0x38a25  ldc.i4   0x747598
0x38a2a  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x38a2f  ldc.i4   0x747599
0x38a34  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x38a39  ldc.i4   0x74759A
0x38a3e  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x38a43  ldc.i4.0
0x38a44  ldnull
0x38a45  newobj   instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor::.ctor(string, unsigned int32, unsigned int32, unsigned int32, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPLogType, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x38a4a  stloc.0
0x38a4b  ldstr    aTaxonomyExecut_0// "Taxonomy ExecuteReader: "
0x38a50  ldarg.1
0x38a51  callvirt instance string [System.Data]System.Data.Common.DbCommand::get_CommandText()
0x38a56  call     string [mscorlib]System.String::Concat(string, string)
0x38a5b  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0x38a60  stloc.1
0x38a61  ldarg.0
0x38a62  ldarg.1
0x38a63  call     instance class [System.Data]System.Data.SqlClient.SqlDataReader [Microsoft.Office.Server]Microsoft.Office.Server.Data.SqlSession::ExecuteReader(class [System.Data]System.Data.SqlClient.SqlCommand)
0x38a68  stloc.2
0x38a69  ldloc.0
0x38a6a  ldnull
0x38a6b  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::Success(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x38a70  ldloc.2
0x38a71  stloc.s  4
0x38a73  leave    loc_38B0D
0x38a78  ldloc.1
0x38a79  brfalse.s loc_38A81
0x38a7b  ldloc.1
0x38a7c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38a81  endfinally
0x38a82  stloc.3
0x38a83  ldc.i4   0x62396E65
0x38a88  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x38a8d  ldc.i4.s 0x32
0x38a8f  ldstr    aSqlExceptionEr// "Sql exception: ErrorNumber: {0} - Messa"...
0x38a94  ldc.i4.3
0x38a95  newarr   [mscorlib]System.Object
0x38a9a  stloc.s  5
0x38a9c  ldloc.s  5
0x38a9e  ldc.i4.0
0x38a9f  ldloc.3
0x38aa0  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x38aa5  box      [mscorlib]System.Int32
0x38aaa  stelem.ref
0x38aab  ldloc.s  5
0x38aad  ldc.i4.1
0x38aae  ldloc.3
0x38aaf  callvirt instance string [mscorlib]System.Exception::get_Message()
0x38ab4  stelem.ref
0x38ab5  ldloc.s  5
0x38ab7  ldc.i4.2
0x38ab8  ldloc.3
0x38ab9  callvirt instance string [mscorlib]System.Object::ToString()
0x38abe  stelem.ref
0x38abf  ldloc.s  5
0x38ac1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x38ac6  ldloc.3
0x38ac7  call     bool Microsoft.SharePoint.Taxonomy.Internal.SqlErrorConverter::IsUnexpectedError(class [System.Data]System.Data.SqlClient.SqlException exception)
0x38acc  brfalse.s loc_38AEA
0x38ace  ldc.i4   0x4975CD
0x38ad3  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x38ad8  ldc.i4.s 0xA
0x38ada  ldstr    aUnexpectedSqlE// "Unexpected SQL Error: "
0x38adf  ldloc.3
0x38ae0  call     string [mscorlib]System.String::Concat(object, object)
0x38ae5  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x38aea  ldloc.3
0x38aeb  ldloc.0
0x38aec  call     void Microsoft.SharePoint.Taxonomy.Internal.TaxonomySqlSession::MonitorSqlException(class [System.Data]System.Data.SqlClient.SqlException se, class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor monitor)
0x38af1  ldloc.3
0x38af2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x38af7  call     string Microsoft.SharePoint.Taxonomy.Internal.SqlErrorConverter::MapErrorMessage(string sqlErrorMessage)
0x38afc  ldloc.3
0x38afd  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x38b02  throw
0x38b03  ldloc.0
0x38b04  brfalse.s loc_38B0C
0x38b06  ldloc.0
0x38b07  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x38b0c  endfinally
0x38b0d  ldloc.s  4
0x38b0f  ret
```
