# Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::ExecuteClientQueryWithRetry

- ea: `0x59bf0`
- end: `0x59e6d`
- name: `Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::ExecuteClientQueryWithRetry`
- size: `637`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x591e0`
- `0x5a9f0`
- `0x5acb0`

## callees

- `0x28cf0`
- `0x584c0`
- `0x59240`
- `0x596c0`
- `0x59b90`
- `0x59bb0`
- `0x59bf0`

## string_xrefs

- `0x59d45`: `Taxonomy migration: commit request failed: {0}. Status code: {1}. Sleeping for {2} milliseconds before retrying. Retrying count: {3}`
- `0x59d91`: `Taxonomy migration: commit request failed: {0} as server returns error. Sleeping for {1} milliseconds before retrying. Retrying count: {2}. ServerCorrelationId: {3}, ServerErrorTypeName: {4}`
- `0x59e06`: `Taxonomy migration: encountered service time out exception, current batch size: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x59bf0  ldc.i4.0
0x59bf1  stloc.0
0x59bf2  ldc.i4   0xEA60
0x59bf7  stloc.1
0x59bf8  ldarg.0
0x59bf9  ldfld    int32 Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::batchSize
0x59bfe  stloc.2
0x59bff  ldnull
0x59c00  stloc.3
0x59c01  ldc.i4   0x121059C
0x59c06  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x59c0b  ldc.i4.s 0x64
0x59c0d  ldstr    aTaxonomyMigrat_6// "Taxonomy migration: executing the clien"...
0x59c12  ldc.i4.1
0x59c13  newarr   [mscorlib]System.Object
0x59c18  stloc.s  9
0x59c1a  ldloc.s  9
0x59c1c  ldc.i4.0
0x59c1d  ldarg.0
0x59c1e  ldfld    int32 Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::csomRequestCount
0x59c23  box      [mscorlib]System.Int32
0x59c28  stelem.ref
0x59c29  ldloc.s  9
0x59c2b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x59c30  ldloc.0
0x59c31  brtrue.s loc_59C40
0x59c33  ldarg.0
0x59c34  ldfld    class [Microsoft.SharePoint.Client]Microsoft.SharePoint.Client.ClientContext Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::clientContext
0x59c39  callvirt instance void [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ClientRuntimeContext::ExecuteQuery()
0x59c3e  br.s     loc_59C95
0x59c40  ldloc.3
0x59c41  brfalse.s loc_59C82
0x59c43  ldloc.3
0x59c44  call     bool Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::IsClientQueryException(class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException exception)
0x59c49  brfalse.s loc_59C82
0x59c4b  ldloc.2
0x59c4c  ldc.i4.2
0x59c4d  div
0x59c4e  stloc.2
0x59c4f  ldc.i4   0x121059D
0x59c54  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x59c59  ldc.i4.s 0x14
0x59c5b  ldstr    aTaxonomyMigrat_7// "Taxonomy migration: client message is t"...
0x59c60  ldc.i4.1
0x59c61  newarr   [mscorlib]System.Object
0x59c66  stloc.s  0xA
0x59c68  ldloc.s  0xA
0x59c6a  ldc.i4.0
0x59c6b  ldloc.2
0x59c6c  box      [mscorlib]System.Int32
0x59c71  stelem.ref
0x59c72  ldloc.s  0xA
0x59c74  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x59c79  ldarg.0
0x59c7a  ldloc.2
0x59c7b  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::ReCommitBatchRequest([opt] int32 reCommitBatchSize)
0x59c80  br.s     loc_59C95
0x59c82  ldarg.0
0x59c83  call     instance bool Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::IsCurrentBatchSuccess()
0x59c88  brtrue.s loc_59C95
0x59c8a  ldarg.0
0x59c8b  ldc.i4   0x7FFFFFFF
0x59c90  call     instance void Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::ReCommitBatchRequest([opt] int32 reCommitBatchSize)
0x59c95  ldarg.0
0x59c96  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x59c9b  brfalse.s loc_59CBE
0x59c9d  ldarg.0
0x59c9e  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::currentBatch
0x59ca3  callvirt instance void Microsoft.SharePoint.Taxonomy.Hybrid.TaxonomyCsomBatch::CleanUp()
0x59ca8  ldc.i4   0x121059E
0x59cad  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x59cb2  ldc.i4.s 0x64
0x59cb4  ldstr    aTaxonomyMigrat_8// "Taxonomy migration: cleaned up current "...
0x59cb9  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x59cbe  ldc.i4   0x121059F
0x59cc3  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x59cc8  ldc.i4.s 0x64
0x59cca  ldstr    aTaxonomyMigrat_9// "Taxonomy migration: Execute the client "...
0x59ccf  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x59cd4  leave    loc_59E6C
0x59cd9  stloc.s  4
0x59cdb  ldstr    aSharepointhybr_21// "SharePointHybridTaxonomy_MigrationExcep"...
0x59ce0  ldloc.s  4
0x59ce2  ldnull
0x59ce3  ldc.r8   NaN
0x59cec  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::WriteException(string engagementName, class [mscorlib]System.Exception exception, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] float64 durationMs)
0x59cf1  ldloc.0
0x59cf2  ldc.i4.1
0x59cf3  add.ovf
0x59cf4  stloc.0
0x59cf5  ldloc.s  4
0x59cf7  isinst   [System]System.Net.WebException
0x59cfc  stloc.s  5
0x59cfe  ldloc.s  4
0x59d00  isinst   [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException
0x59d05  stloc.s  6
0x59d07  ldloc.s  5
0x59d09  brfalse.s loc_59D7E
0x59d0b  ldnull
0x59d0c  stloc.3
0x59d0d  ldloc.s  5
0x59d0f  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x59d14  isinst   [System]System.Net.HttpWebResponse
0x59d19  stloc.s  7
0x59d1b  ldstr    aNull// "<null>"
0x59d20  stloc.s  8
0x59d22  ldloc.s  7
0x59d24  brfalse.s loc_59D39
0x59d26  ldloc.s  7
0x59d28  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x59d2d  box      [System]System.Net.HttpStatusCode
0x59d32  callvirt instance string [mscorlib]System.Object::ToString()
0x59d37  stloc.s  8
0x59d39  ldc.i4   0x12105A0
0x59d3e  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x59d43  ldc.i4.s 0x14
0x59d45  ldstr    aTaxonomyMigrat_10// "Taxonomy migration: commit request fail"...
0x59d4a  ldc.i4.4
0x59d4b  newarr   [mscorlib]System.Object
0x59d50  stloc.s  0xB
0x59d52  ldloc.s  0xB
0x59d54  ldc.i4.0
0x59d55  ldloc.s  5
0x59d57  stelem.ref
0x59d58  ldloc.s  0xB
0x59d5a  ldc.i4.1
0x59d5b  ldloc.s  8
0x59d5d  stelem.ref
0x59d5e  ldloc.s  0xB
0x59d60  ldc.i4.2
0x59d61  ldloc.1
0x59d62  box      [mscorlib]System.Int32
0x59d67  stelem.ref
0x59d68  ldloc.s  0xB
0x59d6a  ldc.i4.3
0x59d6b  ldloc.0
0x59d6c  box      [mscorlib]System.Int32
0x59d71  stelem.ref
0x59d72  ldloc.s  0xB
0x59d74  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x59d79  br       loc_59E57
0x59d7e  ldloc.s  6
0x59d80  brfalse  loc_59E2B
0x59d85  ldc.i4   0x12105A1
0x59d8a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x59d8f  ldc.i4.s 0x14
0x59d91  ldstr    aTaxonomyMigrat_11// "Taxonomy migration: commit request fail"...
0x59d96  ldc.i4.5
0x59d97  newarr   [mscorlib]System.Object
0x59d9c  stloc.s  0xC
0x59d9e  ldloc.s  0xC
0x59da0  ldc.i4.0
0x59da1  ldloc.s  4
0x59da3  stelem.ref
0x59da4  ldloc.s  0xC
0x59da6  ldc.i4.1
0x59da7  ldloc.1
0x59da8  box      [mscorlib]System.Int32
0x59dad  stelem.ref
0x59dae  ldloc.s  0xC
0x59db0  ldc.i4.2
0x59db1  ldloc.0
0x59db2  box      [mscorlib]System.Int32
0x59db7  stelem.ref
0x59db8  ldloc.s  0xC
0x59dba  ldc.i4.3
0x59dbb  ldloc.s  6
0x59dbd  callvirt instance string [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException::get_ServerErrorTraceCorrelationId()
0x59dc2  stelem.ref
0x59dc3  ldloc.s  0xC
0x59dc5  ldc.i4.4
0x59dc6  ldloc.s  6
0x59dc8  callvirt instance string [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException::get_ServerErrorTypeName()
0x59dcd  stelem.ref
0x59dce  ldloc.s  0xC
0x59dd0  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x59dd5  ldloc.s  6
0x59dd7  stloc.3
0x59dd8  ldloc.3
0x59dd9  call     bool Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::IsServiceTimeOutException(class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ServerException exception)
0x59dde  brfalse.s loc_59E57
0x59de0  ldarg.0
0x59de1  ldfld    int32 Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::batchSize
0x59de6  ldc.i4.2
0x59de7  div
0x59de8  ldc.i4.s 0x10
0x59dea  blt.s    loc_59DFA
0x59dec  ldarg.0
0x59ded  ldarg.0
0x59dee  ldfld    int32 Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::batchSize
0x59df3  ldc.i4.2
0x59df4  div
0x59df5  stfld    int32 Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::batchSize
0x59dfa  ldc.i4   0x12105A2
0x59dff  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x59e04  ldc.i4.s 0x14
0x59e06  ldstr    aTaxonomyMigrat_12// "Taxonomy migration: encountered service"...
0x59e0b  ldc.i4.1
0x59e0c  newarr   [mscorlib]System.Object
0x59e11  stloc.s  0xD
0x59e13  ldloc.s  0xD
0x59e15  ldc.i4.0
0x59e16  ldarg.0
0x59e17  ldfld    int32 Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::batchSize
0x59e1c  box      [mscorlib]System.Int32
0x59e21  stelem.ref
0x59e22  ldloc.s  0xD
0x59e24  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x59e29  br.s     loc_59E57
0x59e2b  ldc.i4   0x12105A3
0x59e30  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x59e35  ldloc.s  4
0x59e37  ldstr    aTaxonomyMigrat_13// "Taxonomy migration: unexpected exceptio"...
0x59e3c  ldc.i4.1
0x59e3d  newarr   [mscorlib]System.Object
0x59e42  stloc.s  0xE
0x59e44  ldloc.s  0xE
0x59e46  ldc.i4.0
0x59e47  ldloc.0
0x59e48  box      [mscorlib]System.Int32
0x59e4d  stelem.ref
0x59e4e  ldloc.s  0xE
0x59e50  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, class [mscorlib]System.Exception, string, object[])
0x59e55  rethrow
0x59e57  ldloc.0
0x59e58  ldc.i4.5
0x59e59  bne.un.s loc_59E5D
0x59e5b  rethrow
0x59e5d  ldloc.1
0x59e5e  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x59e63  ldloc.1
0x59e64  ldc.i4.2
0x59e65  mul.ovf
0x59e66  stloc.1
0x59e67  leave    loc_59C30
0x59e6c  ret
```
