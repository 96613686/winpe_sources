# Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::Execute

- ea: `0x57ea0`
- end: `0x58165`
- name: `Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::Execute`
- size: `709`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callees

- `0xc670`
- `0xc6c0`
- `0x242a0`
- `0x284e0`
- `0x28bb0`
- `0x28be0`
- `0x28cf0`
- `0x28dd0`
- `0x2ad40`
- `0x57ea0`
- `0x58170`
- `0x58190`
- `0x581c0`
- `0x5bd70`
- `0x5bde0`
- `0x5bdf0`
- `0x5be00`
- `0x5be10`
- `0x5be30`
- `0x5be40`
- `0x60230`

## string_xrefs

- `0x57f87`: `lastUpdateTimeUtc`
- `0x57fcf`: `Hybrid Content Type: Replicating on {0}, fullReplication: {1}, lastUpdateTimeUtc: {2}, lastRunTimeUtc: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x57ea0  ldarg.0
0x57ea1  ldfld    class [System]System.Uri Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::localSiteUrl
0x57ea6  ldarg.0
0x57ea7  ldfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::localTermStoreId
0x57eac  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.TermStoreFactory::GetLocalTermStoreById(class [System]System.Uri siteUrl, valuetype [mscorlib]System.Guid localTermStoreId)
0x57eb1  stloc.0
0x57eb2  ldloc.0
0x57eb3  ldstr    aLocaltermstore// "localTermStore"
0x57eb8  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x57ebd  ldloc.0
0x57ebe  call     class Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::GetReplicationParameters(class Microsoft.SharePoint.Taxonomy.TermStore localTermStore)
0x57ec3  stloc.1
0x57ec4  ldarg.0
0x57ec5  ldfld    class [System]System.Uri Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::localSiteUrl
0x57eca  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x57ecf  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::.ctor(string)
0x57ed4  stloc.2
0x57ed5  ldloc.2
0x57ed6  ldstr    aSite// "site"
0x57edb  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x57ee0  ldloc.2
0x57ee1  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0x57ee6  newobj   instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb rootWeb)
0x57eeb  stloc.3
0x57eec  ldc.i4.0
0x57eed  conv.i8
0x57eee  stloc.s  4
0x57ef0  ldnull
0x57ef1  stloc.s  5
0x57ef3  ldloc.1
0x57ef4  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::get_RemoteHubUrl()
0x57ef9  newobj   instance void [System]System.Uri::.ctor(string)
0x57efe  ldstr    aLayouts15Wsaup// "/_layouts/15/WsaUpload.ashx"
0x57f03  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, string)
0x57f08  stloc.s  6
0x57f0a  ldloc.s  6
0x57f0c  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.ManagedWsaClient::.ctor(class [System]System.Uri endPointUrl)
0x57f11  stloc.s  7
0x57f13  ldloc.s  7
0x57f15  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::set_Client(class Microsoft.SharePoint.Taxonomy.Internal.Hybrid.ManagedWsaClient value)
0x57f1a  leave.s  loc_57F46
0x57f1c  stloc.s  8
0x57f1e  ldc.i4   0x15D76C7
0x57f23  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x57f28  ldc.i4.s 0x14
0x57f2a  ldstr    aHybridContentT_13// "Hybrid Content Type: Failed to initiali"...
0x57f2f  ldc.i4.1
0x57f30  newarr   [mscorlib]System.Object
0x57f35  stloc.s  0xE
0x57f37  ldloc.s  0xE
0x57f39  ldc.i4.0
0x57f3a  ldloc.s  8
0x57f3c  stelem.ref
0x57f3d  ldloc.s  0xE
0x57f3f  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x57f44  leave.s  loc_57F46
0x57f46  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x57f4b  stloc.s  9
0x57f4d  ldloc.s  9
0x57f4f  ldloc.1
0x57f50  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::get_ContentTypeLastFullReplicationTimeUtc()
0x57f55  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x57f5a  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.Taxonomy.Hybrid.Constants::ContentTypeFullReplicationInterval
0x57f5f  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x57f64  stloc.s  0xA
0x57f66  ldstr    aSharepointhybr_4// "SharePointHybridContentType_Replication"...
0x57f6b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x57f70  stloc.s  0xC
0x57f72  ldloc.s  0xC
0x57f74  ldstr    aFullreplicatio// "fullReplication"
0x57f79  ldloc.s  0xA
0x57f7b  box      [mscorlib]System.Boolean
0x57f80  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x57f85  ldloc.s  0xC
0x57f87  ldstr    aLastupdatetime_0// "lastUpdateTimeUtc"
0x57f8c  ldloc.1
0x57f8d  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::get_ContentTypeLastUpdateTimeUtc()
0x57f92  box      [mscorlib]System.DateTime
0x57f97  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x57f9c  ldloc.s  0xC
0x57f9e  ldstr    aLastruntimeutc// "lastRunTimeUtc"
0x57fa3  ldloc.1
0x57fa4  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::get_ContentTypeLastRunTimeUtc()
0x57fa9  box      [mscorlib]System.DateTime
0x57fae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x57fb3  ldloc.s  0xC
0x57fb5  ldc.r8   NaN
0x57fbe  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] float64 durationMs)
0x57fc3  ldc.i4   0x15A2359
0x57fc8  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x57fcd  ldc.i4.s 0x32
0x57fcf  ldstr    aHybridContentT// "Hybrid Content Type: Replicating on {0}"...
0x57fd4  ldc.i4.4
0x57fd5  newarr   [mscorlib]System.Object
0x57fda  stloc.s  0xF
0x57fdc  ldloc.s  0xF
0x57fde  ldc.i4.0
0x57fdf  ldarg.0
0x57fe0  ldfld    class [System]System.Uri Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::localSiteUrl
0x57fe5  stelem.ref
0x57fe6  ldloc.s  0xF
0x57fe8  ldc.i4.1
0x57fe9  ldloc.s  0xA
0x57feb  box      [mscorlib]System.Boolean
0x57ff0  stelem.ref
0x57ff1  ldloc.s  0xF
0x57ff3  ldc.i4.2
0x57ff4  ldloc.1
0x57ff5  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::get_ContentTypeLastUpdateTimeUtc()
0x57ffa  box      [mscorlib]System.DateTime
0x57fff  stelem.ref
0x58000  ldloc.s  0xF
0x58002  ldc.i4.3
0x58003  ldloc.1
0x58004  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::get_ContentTypeLastRunTimeUtc()
0x58009  box      [mscorlib]System.DateTime
0x5800e  stelem.ref
0x5800f  ldloc.s  0xF
0x58011  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x58016  ldloc.s  4
0x58018  ldloc.3
0x58019  ldloc.0
0x5801a  ldloca.s 1
0x5801c  ldloc.s  0xA
0x5801e  ldarg.0
0x5801f  call     instance string Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::get_GraphApiEndpoint()
0x58024  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationStatus Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::Replicate(class Microsoft.SharePoint.Taxonomy.TermStore localTermStore, class Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters& replicationParameters, bool fullReplication, [opt] string graphApiEndPoint)
0x58029  or
0x5802a  stloc.s  4
0x5802c  leave.s  loc_5809D
0x5802e  stloc.s  0xB
0x58030  ldloc.s  0xB
0x58032  stloc.s  5
0x58034  ldloc.s  0xA
0x58036  brtrue.s loc_5803F
0x58038  ldstr    aSharepointhybr_19// "SharePointHybridContentType_Incremental"...
0x5803d  br.s     loc_58044
0x5803f  ldstr    aSharepointhybr_20// "SharePointHybridContentType_FullReplica"...
0x58044  ldloc.s  0xB
0x58046  ldnull
0x58047  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x5804c  ldloc.s  9
0x5804e  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x58053  stloc.s  0x10
0x58055  ldloca.s 0x10
0x58057  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x5805c  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::WriteException(string engagementName, class [mscorlib]System.Exception exception, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] float64 durationMs)
0x58061  ldloc.s  4
0x58063  ldloc.s  0xA
0x58065  brtrue.s loc_5806B
0x58067  ldc.i4.4
0x58068  conv.i8
0x58069  br.s     loc_5806D
0x5806b  ldc.i4.2
0x5806c  conv.i8
0x5806d  or
0x5806e  stloc.s  4
0x58070  ldc.i4   0x15A235A
0x58075  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5807a  ldc.i4.s 0x32
0x5807c  ldstr    aHybridContentT_14// "Hybrid Content Type: Replication failed"...
0x58081  ldc.i4.1
0x58082  newarr   [mscorlib]System.Object
0x58087  stloc.s  0x11
0x58089  ldloc.s  0x11
0x5808b  ldc.i4.0
0x5808c  ldloc.s  0xB
0x5808e  callvirt instance string [mscorlib]System.Object::ToString()
0x58093  stelem.ref
0x58094  ldloc.s  0x11
0x58096  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x5809b  leave.s  loc_5809D
0x5809d  ldloc.s  4
0x5809f  ldc.i4.0
0x580a0  conv.i8
0x580a1  bne.un.s loc_580B7
0x580a3  ldloc.1
0x580a4  ldloc.s  9
0x580a6  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::set_ContentTypeLastSuccessfulReplicationTimeUtc(valuetype [mscorlib]System.DateTime value)
0x580ab  ldloc.s  0xA
0x580ad  brfalse.s loc_580B7
0x580af  ldloc.1
0x580b0  ldloc.s  9
0x580b2  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::set_ContentTypeLastFullReplicationTimeUtc(valuetype [mscorlib]System.DateTime value)
0x580b7  ldloc.1
0x580b8  ldloc.s  9
0x580ba  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::set_ContentTypeLastRunTimeUtc(valuetype [mscorlib]System.DateTime value)
0x580bf  ldstr    aSharepointhybr_6// "SharePointHybridContentType_Replication"...
0x580c4  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x580c9  stloc.s  0xD
0x580cb  ldloc.s  0xD
0x580cd  ldstr    aResult// "result"
0x580d2  ldloc.s  4
0x580d4  box      Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationStatus
0x580d9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x580de  ldloc.s  0xD
0x580e0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x580e5  ldloc.s  9
0x580e7  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x580ec  stloc.s  0x12
0x580ee  ldloca.s 0x12
0x580f0  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x580f5  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] float64 durationMs)
0x580fa  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::Flush()
0x580ff  ldloc.1
0x58100  ldloc.0
0x58101  call     void Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::SetContentTypeReplicationParameters(class Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters replicationParameters, class Microsoft.SharePoint.Taxonomy.TermStore localTermStore)
0x58106  ldloc.s  5
0x58108  brfalse.s loc_58158
0x5810a  ldloc.s  0xA
0x5810c  brfalse.s loc_58133
0x5810e  ldstr    aContenttypeful// "ContentTypeFullReplicationFailure"
0x58113  ldc.i4.1
0x58114  newarr   [mscorlib]System.Object
0x58119  stloc.s  0x13
0x5811b  ldloc.s  0x13
0x5811d  ldc.i4.0
0x5811e  ldloc.s  5
0x58120  callvirt instance string [mscorlib]System.Exception::get_Message()
0x58125  stelem.ref
0x58126  ldloc.s  0x13
0x58128  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x5812d  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPException::.ctor(string)
0x58132  throw
0x58133  ldstr    aContenttypeinc// "ContentTypeIncrementalReplicationFailur"...
0x58138  ldc.i4.1
0x58139  newarr   [mscorlib]System.Object
0x5813e  stloc.s  0x14
0x58140  ldloc.s  0x14
0x58142  ldc.i4.0
0x58143  ldloc.s  5
0x58145  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5814a  stelem.ref
0x5814b  ldloc.s  0x14
0x5814d  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x58152  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPException::.ctor(string)
0x58157  throw
0x58158  leave.s  loc_58164
0x5815a  ldloc.2
0x5815b  brfalse.s loc_58163
0x5815d  ldloc.2
0x5815e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x58163  endfinally
0x58164  ret
```
