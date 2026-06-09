# <>c__DisplayClass5::<WriteOld>b__4

- ea: `0x72760`
- end: `0x72a4a`
- name: `<>c__DisplayClass5::<WriteOld>b__4`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x72760`

## callees

- `0x178f0`
- `0x19bd0`
- `0x1afa0`
- `0x26e80`
- `0x27140`
- `0x33c30`
- `0x33d30`
- `0x34dc0`
- `0x34e30`
- `0x34e90`
- `0x34ea0`
- `0x34ec0`
- `0x378f0`
- `0x379a0`
- `0x38c20`
- `0x38c50`
- `0x38ce0`
- `0x579c0`
- `0x72760`

## string_xrefs

- `0x7283c`: `Sending command to SQL: {0}. Number of Parameters: {1} `
- `0x728e2`: `Sending command to SQL: {0}. Number of Parameters: {1} `

## pseudocode

```c

```

## disassembly

```asm
0x72760  ldarg.0
0x72761  ldc.i4.0
0x72762  stfld    bool <>c__DisplayClass5::retry
0x72767  ldarg.0
0x72768  dup
0x72769  ldfld    int32 <>c__DisplayClass5::retryCount
0x7276e  ldc.i4.1
0x7276f  add.ovf
0x72770  stfld    int32 <>c__DisplayClass5::retryCount
0x72775  ldarg.0
0x72776  ldfld    string <>c__DisplayClass5::xmlData
0x7277b  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x72780  stloc.0
0x72781  ldloc.0
0x72782  newobj   instance void [System.Xml]System.Xml.XmlTextReader::.ctor(class [mscorlib]System.IO.TextReader)
0x72787  stloc.s  4
0x72789  ldloc.s  4
0x7278b  ldc.i4.0
0x7278c  callvirt instance void [System.Xml]System.Xml.XmlTextReader::set_DtdProcessing(valuetype [System.Xml]System.Xml.DtdProcessing)
0x72791  ldloc.s  4
0x72793  stloc.1
0x72794  ldloc.1
0x72795  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::.ctor(class [System.Xml]System.Xml.XmlTextReader xmlReader)
0x7279a  stloc.2
0x7279b  ldarg.0
0x7279c  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyTransactionalSqlSession <>c__DisplayClass5::session
0x727a1  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyTransactionalSqlSession::BeginTransaction()
0x727a6  ldarg.0
0x727a7  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyTransactionalSqlSession <>c__DisplayClass5::session
0x727ac  ldarg.0
0x727ad  ldfld    class [System.Data]System.Data.SqlClient.SqlCommand <>c__DisplayClass5::cmd
0x727b2  call     void Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite::ExecuteNonQuery(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyTransactionalSqlSession sqlSession, class [System.Data]System.Data.SqlClient.SqlCommand command)
0x727b7  ldarg.0
0x727b8  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite <>c__DisplayClass5::<>4__this
0x727bd  ldarg.0
0x727be  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass5::resolvedPartitionId
0x727c3  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::.ctor(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase databaseAdapter, valuetype [mscorlib]System.Guid resolvedPartitionId)
0x727c8  stloc.3
0x727c9  ldarg.0
0x727ca  ldfld    class [System.Data]System.Data.SqlClient.SqlCommand <>c__DisplayClass5::cmd
0x727cf  ldarg.0
0x727d0  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite <>c__DisplayClass5::<>4__this
0x727d5  call     instance int32 Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadOnly::get_CommandTimeOut()
0x727da  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandTimeout(int32)
0x727df  br       loc_7288F
0x727e4  ldloc.3
0x727e5  ldloc.2
0x727e6  ldarg.0
0x727e7  ldfld    bool <>c__DisplayClass5::isRestrictedWrite
0x727ec  ldarg.0
0x727ed  ldfld    class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext <>c__DisplayClass5::databaseMapperContext
0x727f2  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::Process(class Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader dataReader, bool isRestrictedWrite, class Microsoft.SharePoint.Taxonomy.ITaxonomyDatabaseMapperContext databaseMapperContext)
0x727f7  brfalse  loc_7288F
0x727fc  ldloc.3
0x727fd  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_IsBatchFull()
0x72802  brfalse  loc_7288F
0x72807  ldarg.0
0x72808  ldc.i4.1
0x72809  stfld    bool <>c__DisplayClass5::batched
0x7280e  ldarg.0
0x7280f  ldfld    class [System.Data]System.Data.SqlClient.SqlCommand <>c__DisplayClass5::cmd
0x72814  ldloc.3
0x72815  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_CurrentBatch()
0x7281a  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x7281f  ldloc.3
0x72820  ldarg.0
0x72821  ldfld    class [System.Data]System.Data.SqlClient.SqlCommand <>c__DisplayClass5::cmd
0x72826  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x7282b  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::GetCurrentParameters(class [System.Data]System.Data.SqlClient.SqlParameterCollection sqlParameters)
0x72830  ldc.i4   0x31343972
0x72835  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x7283a  ldc.i4.s 0x32
0x7283c  ldstr    aSendingCommand// "Sending command to SQL: {0}. Number of "...
0x72841  ldc.i4.2
0x72842  newarr   [mscorlib]System.Object
0x72847  stloc.s  6
0x72849  ldloc.s  6
0x7284b  ldc.i4.0
0x7284c  ldarg.0
0x7284d  ldfld    class [System.Data]System.Data.SqlClient.SqlCommand <>c__DisplayClass5::cmd
0x72852  callvirt instance string [System.Data]System.Data.Common.DbCommand::get_CommandText()
0x72857  stelem.ref
0x72858  ldloc.s  6
0x7285a  ldc.i4.1
0x7285b  ldarg.0
0x7285c  ldfld    class [System.Data]System.Data.SqlClient.SqlCommand <>c__DisplayClass5::cmd
0x72861  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x72866  callvirt instance int32 [System.Data]System.Data.Common.DbParameterCollection::get_Count()
0x7286b  box      [mscorlib]System.Int32
0x72870  stelem.ref
0x72871  ldloc.s  6
0x72873  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x72878  ldarg.0
0x72879  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyTransactionalSqlSession <>c__DisplayClass5::session
0x7287e  ldarg.0
0x7287f  ldfld    class [System.Data]System.Data.SqlClient.SqlCommand <>c__DisplayClass5::cmd
0x72884  call     void Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite::ExecuteNonQuery(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyTransactionalSqlSession sqlSession, class [System.Data]System.Data.SqlClient.SqlCommand command)
0x72889  ldloc.3
0x7288a  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::ClearBatch()
0x7288f  ldloc.2
0x72890  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.XmlDataReader::Read()
0x72895  brtrue   loc_727E4
0x7289a  ldarg.0
0x7289b  ldfld    class [System.Data]System.Data.SqlClient.SqlCommand <>c__DisplayClass5::cmd
0x728a0  ldloc.3
0x728a1  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::get_CurrentBatch()
0x728a6  ldstr    aExec// "EXEC "
0x728ab  ldarg.0
0x728ac  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite <>c__DisplayClass5::<>4__this
0x728b1  ldstr    aProcEcmLogchan// "proc_ECM_LogChange"
0x728b6  call     instance string Microsoft.SharePoint.Taxonomy.Internal.TaxonomyDatabaseAdapterBase::GetScopedProcedureName(string procedureName)
0x728bb  call     string [mscorlib]System.String::Concat(string, string, string)
0x728c0  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x728c5  ldloc.3
0x728c6  ldarg.0
0x728c7  ldfld    class [System.Data]System.Data.SqlClient.SqlCommand <>c__DisplayClass5::cmd
0x728cc  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x728d1  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::GetCurrentParameters(class [System.Data]System.Data.SqlClient.SqlParameterCollection sqlParameters)
0x728d6  ldc.i4   0x31343973
0x728db  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x728e0  ldc.i4.s 0x32
0x728e2  ldstr    aSendingCommand// "Sending command to SQL: {0}. Number of "...
0x728e7  ldc.i4.2
0x728e8  newarr   [mscorlib]System.Object
0x728ed  stloc.s  7
0x728ef  ldloc.s  7
0x728f1  ldc.i4.0
0x728f2  ldarg.0
0x728f3  ldfld    class [System.Data]System.Data.SqlClient.SqlCommand <>c__DisplayClass5::cmd
0x728f8  callvirt instance string [System.Data]System.Data.Common.DbCommand::get_CommandText()
0x728fd  stelem.ref
0x728fe  ldloc.s  7
0x72900  ldc.i4.1
0x72901  ldarg.0
0x72902  ldfld    class [System.Data]System.Data.SqlClient.SqlCommand <>c__DisplayClass5::cmd
0x72907  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameterCollection [System.Data]System.Data.SqlClient.SqlCommand::get_Parameters()
0x7290c  callvirt instance int32 [System.Data]System.Data.Common.DbParameterCollection::get_Count()
0x72911  box      [mscorlib]System.Int32
0x72916  stelem.ref
0x72917  ldloc.s  7
0x72919  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x7291e  ldarg.0
0x7291f  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyTransactionalSqlSession <>c__DisplayClass5::session
0x72924  ldarg.0
0x72925  ldfld    class [System.Data]System.Data.SqlClient.SqlCommand <>c__DisplayClass5::cmd
0x7292a  call     void Microsoft.SharePoint.Taxonomy.Internal.SqlDataAccessReadWrite::ExecuteNonQuery(class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyTransactionalSqlSession sqlSession, class [System.Data]System.Data.SqlClient.SqlCommand command)
0x7292f  ldarg.0
0x72930  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyTransactionalSqlSession <>c__DisplayClass5::session
0x72935  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyTransactionalSqlSession::CommitTransaction()
0x7293a  ldloc.3
0x7293b  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SqlCommandFactory::FlushEngagementLogQueue()
0x72940  leave.s  loc_7294C
0x72942  ldloc.2
0x72943  brfalse.s loc_7294B
0x72945  ldloc.2
0x72946  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7294b  endfinally
0x7294c  leave.s  loc_72958
0x7294e  ldloc.1
0x7294f  brfalse.s loc_72957
0x72951  ldloc.1
0x72952  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x72957  endfinally
0x72958  leave.s  loc_72964
0x7295a  ldloc.0
0x7295b  brfalse.s loc_72963
0x7295d  ldloc.0
0x7295e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x72963  endfinally
0x72964  leave    loc_72A15
0x72969  stloc.s  5
0x7296b  ldc.i4   0x786F7A63
0x72970  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x72975  ldc.i4.s 0x32
0x72977  ldstr    aSqlExceptionRa// "Sql exception raw message: "
0x7297c  ldloc.s  5
0x7297e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x72983  ldstr    asc_7D394// " "
0x72988  ldloc.s  5
0x7298a  callvirt instance string [mscorlib]System.Object::ToString()
0x7298f  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x72994  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x72999  ldarg.0
0x7299a  ldfld    bool <>c__DisplayClass5::batched
0x7299f  brtrue.s loc_729D9
0x729a1  ldloc.s  5
0x729a3  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlException::get_Number()
0x729a8  ldc.i4   0x4B5
0x729ad  bne.un.s loc_729D9
0x729af  ldarg.0
0x729b0  ldfld    int32 <>c__DisplayClass5::retryCount
0x729b5  ldc.i4.3
0x729b6  bge.s    loc_729D9
0x729b8  ldarg.0
0x729b9  dup
0x729ba  ldfld    int32 <>c__DisplayClass5::retryCount
0x729bf  ldc.i4.1
0x729c0  add.ovf
0x729c1  stfld    int32 <>c__DisplayClass5::retryCount
0x729c6  ldarg.0
0x729c7  ldc.i4.1
0x729c8  stfld    bool <>c__DisplayClass5::retry
0x729cd  ldc.i4   0x1F4
0x729d2  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x729d7  br.s     loc_72A13
0x729d9  ldloc.s  5
0x729db  call     bool Microsoft.SharePoint.Taxonomy.Internal.SqlErrorConverter::IsUnexpectedError(class [System.Data]System.Data.SqlClient.SqlException exception)
0x729e0  brfalse.s loc_729FF
0x729e2  ldc.i4   0x4975CB
0x729e7  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x729ec  ldc.i4.s 0xA
0x729ee  ldstr    aUnexpectedSqlE// "Unexpected SQL Error: "
0x729f3  ldloc.s  5
0x729f5  call     string [mscorlib]System.String::Concat(object, object)
0x729fa  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x729ff  ldloc.s  5
0x72a01  callvirt instance string [mscorlib]System.Exception::get_Message()
0x72a06  call     string Microsoft.SharePoint.Taxonomy.Internal.SqlErrorConverter::MapErrorMessage(string sqlErrorMessage)
0x72a0b  ldloc.s  5
0x72a0d  newobj   instance void Microsoft.SharePoint.Taxonomy.TermStoreOperationException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x72a12  throw
0x72a13  leave.s  loc_72A15
0x72a15  leave.s  loc_72A3E
0x72a17  ldarg.0
0x72a18  ldfld    class [System.Data]System.Data.SqlClient.SqlCommand <>c__DisplayClass5::cmd
0x72a1d  brfalse.s loc_72A2A
0x72a1f  ldarg.0
0x72a20  ldfld    class [System.Data]System.Data.SqlClient.SqlCommand <>c__DisplayClass5::cmd
0x72a25  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x72a2a  ldarg.0
0x72a2b  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyTransactionalSqlSession <>c__DisplayClass5::session
0x72a30  brfalse.s loc_72A3D
0x72a32  ldarg.0
0x72a33  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyTransactionalSqlSession <>c__DisplayClass5::session
0x72a38  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyTransactionalSqlSession::Dispose()
0x72a3d  endfinally
0x72a3e  ldarg.0
0x72a3f  ldfld    bool <>c__DisplayClass5::retry
0x72a44  brtrue   __c__DisplayClass5___WriteOld_b__4
0x72a49  ret
```
