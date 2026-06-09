# Microsoft.SharePoint.Taxonomy.Hybrid.Cmdlet.SPCmdletStopSPContentTypeReplication::InternalProcessRecord

- ea: `0x39e50`
- end: `0x3a141`
- name: `Microsoft.SharePoint.Taxonomy.Hybrid.Cmdlet.SPCmdletStopSPContentTypeReplication::InternalProcessRecord`
- size: `753`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callees

- `0xc670`
- `0xc6c0`
- `0x242a0`
- `0x28be0`
- `0x28cf0`
- `0x28dd0`
- `0x2acd0`
- `0x2ad40`
- `0x39e50`
- `0x57bc0`
- `0x58170`
- `0x581c0`
- `0x581e0`
- `0x581f0`
- `0x5be10`
- `0x5be30`
- `0x60230`
- `0x73930`

## string_xrefs

- `0x39f53`: `lastUpdateTimeUtc`
- `0x39f9d`: `Hybrid Content Type: Replicating on {0}, fullReplication: {1}, lastUpdateTimeUtc: {2}, lastRunTimeUtc: {3}`
- `0x3a0e0`: `ContentTypeStopReplicationBeginDelete`

## pseudocode

```c

```

## disassembly

```asm
0x39e50  ldnull
0x39e51  stloc.s  0xD
0x39e53  newobj   instance void <>c__DisplayClass4::.ctor()
0x39e58  stloc.s  0xE
0x39e5a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x39e5f  stloc.0
0x39e60  ldloc.0
0x39e61  ldstr    aFarm// "farm"
0x39e66  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x39e6b  ldloc.s  0xE
0x39e6d  ldloc.0
0x39e6e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPTimerService [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_TimerService()
0x39e73  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinitionCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPService::get_JobDefinitions()
0x39e78  ldsfld   string Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::TimerJobName
0x39e7d  callvirt T0x2B000001
0x39e82  stfld    class Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition <>c__DisplayClass4::job
0x39e87  ldloc.s  0xE
0x39e89  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition <>c__DisplayClass4::job
0x39e8e  ldstr    aJob// "job"
0x39e93  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x39e98  ldloc.s  0xE
0x39e9a  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition <>c__DisplayClass4::job
0x39e9f  callvirt instance class [System]System.Uri Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::get_LocalSiteUrl()
0x39ea4  stloc.1
0x39ea5  ldloc.s  0xE
0x39ea7  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition <>c__DisplayClass4::job
0x39eac  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::get_LocalTermStoreId()
0x39eb1  stloc.2
0x39eb2  ldc.i4.1
0x39eb3  stloc.3
0x39eb4  ldloc.s  0xE
0x39eb6  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition <>c__DisplayClass4::job
0x39ebb  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_IsDisabled()
0x39ec0  brtrue.s loc_39EE3
0x39ec2  ldloc.s  0xE
0x39ec4  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition <>c__DisplayClass4::job
0x39ec9  ldloc.s  0xD
0x39ecb  brtrue.s loc_39EDC
0x39ecd  ldloc.s  0xE
0x39ecf  ldftn    instance void <>c__DisplayClass4::<InternalProcessRecord>b__2()
0x39ed5  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject/CodeToRunWithRetries::.ctor(object, native int)
0x39eda  stloc.s  0xD
0x39edc  ldloc.s  0xD
0x39ede  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::RunWithConcurrencyRetries(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject/CodeToRunWithRetries)
0x39ee3  ldloc.1
0x39ee4  ldloc.2
0x39ee5  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.TermStoreFactory::GetLocalTermStoreById(class [System]System.Uri siteUrl, valuetype [mscorlib]System.Guid localTermStoreId)
0x39eea  stloc.s  4
0x39eec  ldloc.s  4
0x39eee  ldstr    aLocaltermstore// "localTermStore"
0x39ef3  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x39ef8  ldloc.s  4
0x39efa  call     class Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::GetReplicationParameters(class Microsoft.SharePoint.Taxonomy.TermStore localTermStore)
0x39eff  stloc.s  5
0x39f01  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x39f06  stloc.s  6
0x39f08  ldloc.1
0x39f09  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x39f0e  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::.ctor(string)
0x39f13  stloc.s  7
0x39f15  ldloc.s  7
0x39f17  ldstr    aSite// "site"
0x39f1c  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x39f21  ldloc.s  7
0x39f23  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0x39f28  newobj   instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb rootWeb)
0x39f2d  stloc.s  8
0x39f2f  ldc.i4.0
0x39f30  conv.i8
0x39f31  stloc.s  9
0x39f33  ldstr    aSharepointhybr_4// "SharePointHybridContentType_Replication"...
0x39f38  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x39f3d  stloc.s  0xB
0x39f3f  ldloc.s  0xB
0x39f41  ldstr    aFullreplicatio// "fullReplication"
0x39f46  ldloc.3
0x39f47  box      [mscorlib]System.Boolean
0x39f4c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x39f51  ldloc.s  0xB
0x39f53  ldstr    aLastupdatetime_0// "lastUpdateTimeUtc"
0x39f58  ldloc.s  5
0x39f5a  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::get_ContentTypeLastUpdateTimeUtc()
0x39f5f  box      [mscorlib]System.DateTime
0x39f64  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x39f69  ldloc.s  0xB
0x39f6b  ldstr    aLastruntimeutc// "lastRunTimeUtc"
0x39f70  ldloc.s  5
0x39f72  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::get_ContentTypeLastRunTimeUtc()
0x39f77  box      [mscorlib]System.DateTime
0x39f7c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x39f81  ldloc.s  0xB
0x39f83  ldc.r8   NaN
0x39f8c  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] float64 durationMs)
0x39f91  ldc.i4   0x15CF65A
0x39f96  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x39f9b  ldc.i4.s 0x32
0x39f9d  ldstr    aHybridContentT// "Hybrid Content Type: Replicating on {0}"...
0x39fa2  ldc.i4.4
0x39fa3  newarr   [mscorlib]System.Object
0x39fa8  stloc.s  0xF
0x39faa  ldloc.s  0xF
0x39fac  ldc.i4.0
0x39fad  ldloc.1
0x39fae  stelem.ref
0x39faf  ldloc.s  0xF
0x39fb1  ldc.i4.1
0x39fb2  ldloc.3
0x39fb3  box      [mscorlib]System.Boolean
0x39fb8  stelem.ref
0x39fb9  ldloc.s  0xF
0x39fbb  ldc.i4.2
0x39fbc  ldloc.s  5
0x39fbe  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::get_ContentTypeLastUpdateTimeUtc()
0x39fc3  box      [mscorlib]System.DateTime
0x39fc8  stelem.ref
0x39fc9  ldloc.s  0xF
0x39fcb  ldc.i4.3
0x39fcc  ldloc.s  5
0x39fce  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::get_ContentTypeLastRunTimeUtc()
0x39fd3  box      [mscorlib]System.DateTime
0x39fd8  stelem.ref
0x39fd9  ldloc.s  0xF
0x39fdb  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x39fe0  ldstr    aContenttypesto// "ContentTypeStopReplicationBegin"
0x39fe5  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x39fea  call     void [mscorlib]System.Console::WriteLine(string)
0x39fef  ldloc.s  9
0x39ff1  ldloc.s  8
0x39ff3  ldloc.s  4
0x39ff5  ldloca.s 5
0x39ff7  ldloc.3
0x39ff8  ldloc.s  0xE
0x39ffa  ldfld    class Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition <>c__DisplayClass4::job
0x39fff  callvirt instance string Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::get_GraphApiEndpoint()
0x3a004  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationStatus Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::Replicate(class Microsoft.SharePoint.Taxonomy.TermStore localTermStore, class Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters& replicationParameters, bool fullReplication, [opt] string graphApiEndPoint)
0x3a009  or
0x3a00a  stloc.s  9
0x3a00c  ldloc.s  9
0x3a00e  ldc.i4.1
0x3a00f  conv.i8
0x3a010  and
0x3a011  ldc.i4.1
0x3a012  conv.i8
0x3a013  bne.un.s loc_3A024
0x3a015  ldstr    aContenttypesto_0// "ContentTypeStopReplicationIdMappingFail"...
0x3a01a  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3a01f  call     void [mscorlib]System.Console::WriteLine(string)
0x3a024  leave.s  loc_3A097
0x3a026  stloc.s  0xA
0x3a028  ldloc.s  9
0x3a02a  ldc.i4.2
0x3a02b  conv.i8
0x3a02c  or
0x3a02d  stloc.s  9
0x3a02f  ldstr    aSharepointhybr_5// "SharePointHybridContentType_StopReplica"...
0x3a034  ldloc.s  0xA
0x3a036  ldnull
0x3a037  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3a03c  ldloc.s  6
0x3a03e  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3a043  stloc.s  0x10
0x3a045  ldloca.s 0x10
0x3a047  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x3a04c  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::WriteException(string engagementName, class [mscorlib]System.Exception exception, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] float64 durationMs)
0x3a051  ldc.i4   0x15CF65B
0x3a056  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3a05b  ldloc.s  0xA
0x3a05d  ldstr    aHybridContentT_0// "Hybrid Content Type: Full replication f"...
0x3a062  ldc.i4.0
0x3a063  newarr   [mscorlib]System.Object
0x3a068  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, class [mscorlib]System.Exception, string, object[])
0x3a06d  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::Flush()
0x3a072  ldstr    aContenttypeful// "ContentTypeFullReplicationFailure"
0x3a077  ldc.i4.1
0x3a078  newarr   [mscorlib]System.Object
0x3a07d  stloc.s  0x11
0x3a07f  ldloc.s  0x11
0x3a081  ldc.i4.0
0x3a082  ldloc.s  0xA
0x3a084  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3a089  stelem.ref
0x3a08a  ldloc.s  0x11
0x3a08c  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x3a091  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPException::.ctor(string)
0x3a096  throw
0x3a097  ldstr    aSharepointhybr_6// "SharePointHybridContentType_Replication"...
0x3a09c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x3a0a1  stloc.s  0xC
0x3a0a3  ldloc.s  0xC
0x3a0a5  ldstr    aResult// "result"
0x3a0aa  ldloc.s  9
0x3a0ac  box      Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationStatus
0x3a0b1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x3a0b6  ldloc.s  0xC
0x3a0b8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3a0bd  ldloc.s  6
0x3a0bf  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3a0c4  stloc.s  0x12
0x3a0c6  ldloca.s 0x12
0x3a0c8  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x3a0cd  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] float64 durationMs)
0x3a0d2  leave.s  loc_3A0E0
0x3a0d4  ldloc.s  7
0x3a0d6  brfalse.s loc_3A0DF
0x3a0d8  ldloc.s  7
0x3a0da  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3a0df  endfinally
0x3a0e0  ldstr    aContenttypesto_1// "ContentTypeStopReplicationBeginDelete"
0x3a0e5  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3a0ea  call     void [mscorlib]System.Console::WriteLine(string)
0x3a0ef  ldloc.s  4
0x3a0f1  call     void Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::DeleteExistingJobDefinitions(class Microsoft.SharePoint.Taxonomy.TermStore localTermStore)
0x3a0f6  ldstr    aContenttypesto_2// "ContentTypeStopReplicationFinish"
0x3a0fb  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3a100  call     void [mscorlib]System.Console::WriteLine(string)
0x3a105  ldc.i4   0x15CF65D
0x3a10a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3a10f  ldc.i4.s 0x14
0x3a111  ldstr    aContentTypeRep// "Content type replicaiton: the content t"...
0x3a116  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x3a11b  ldstr    aSharepointhybr_7// "SharePointHybridContentType_TimerJobSto"...
0x3a120  ldnull
0x3a121  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x3a126  ldloc.s  6
0x3a128  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3a12d  stloc.s  0x13
0x3a12f  ldloca.s 0x13
0x3a131  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x3a136  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] float64 durationMs)
0x3a13b  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::Flush()
0x3a140  ret
```
