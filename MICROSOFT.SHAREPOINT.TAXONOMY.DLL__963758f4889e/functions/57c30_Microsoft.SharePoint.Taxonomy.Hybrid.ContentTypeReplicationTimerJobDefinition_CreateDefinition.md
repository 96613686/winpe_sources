# Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::CreateDefinition

- ea: `0x57c30`
- end: `0x57e92`
- name: `Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::CreateDefinition`
- size: `610`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callees

- `0x242a0`
- `0x242d0`
- `0x3be20`
- `0x3cfc0`
- `0x3cff0`
- `0x3d010`
- `0x3d030`
- `0x3d0a0`
- `0x55710`
- `0x56c70`
- `0x57ad0`
- `0x57bc0`
- `0x57c30`
- `0x581e0`
- `0x59ea0`
- `0x5a2f0`
- `0x5fd90`
- `0x60170`

## string_xrefs

- `0x57c47`: `localTermStoreName`
- `0x57ce3`: `remoteService`

## pseudocode

```c

```

## disassembly

```asm
0x57c30  ldarg.0
0x57c31  ldstr    aRemotesiteurl// "remoteSiteUrl"
0x57c36  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x57c3b  ldarg.1
0x57c3c  ldstr    aLocasiteurl// "locaSiteUrl"
0x57c41  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x57c46  ldarg.2
0x57c47  ldstr    aLocaltermstore_0// "localTermStoreName"
0x57c4c  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x57c51  ldarg.0
0x57c52  ldstr    aSitesContentty_0// "sites/contentTypeHub"
0x57c57  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, string)
0x57c5c  stloc.0
0x57c5d  ldloc.0
0x57c5e  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x57c63  ldc.i4.5
0x57c64  rem
0x57c65  call     int32 [mscorlib]System.Math::Abs(int32)
0x57c6a  ldc.i4.1
0x57c6b  add.ovf
0x57c6c  stloc.1
0x57c6d  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::.ctor()
0x57c72  stloc.2
0x57c73  ldloc.2
0x57c74  ldloc.1
0x57c75  ldc.i4.1
0x57c76  sub.ovf
0x57c77  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::set_BeginHour(int32)
0x57c7c  ldloc.2
0x57c7d  ldc.i4.0
0x57c7e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::set_BeginMinute(int32)
0x57c83  ldloc.2
0x57c84  ldc.i4.0
0x57c85  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::set_BeginSecond(int32)
0x57c8a  ldloc.2
0x57c8b  ldloc.1
0x57c8c  ldc.i4.1
0x57c8d  add.ovf
0x57c8e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::set_EndHour(int32)
0x57c93  ldloc.2
0x57c94  ldc.i4.s 0x3B
0x57c96  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::set_EndMinute(int32)
0x57c9b  ldloc.2
0x57c9c  ldc.i4.s 0x3B
0x57c9e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPDailySchedule::set_EndSecond(int32)
0x57ca3  ldarg.1
0x57ca4  ldarg.2
0x57ca5  call     class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.TermStoreFactory::GetLocalTermStore(class [System]System.Uri siteUrl, string termStoreName)
0x57caa  stloc.3
0x57cab  ldloc.3
0x57cac  ldstr    aLocaltermstore// "localTermStore"
0x57cb1  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x57cb6  ldloc.3
0x57cb7  call     void Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::DeleteExistingJobDefinitions(class Microsoft.SharePoint.Taxonomy.TermStore localTermStore)
0x57cbc  ldc.i4.0
0x57cbd  stloc.s  4
0x57cbf  ldnull
0x57cc0  stloc.s  5
0x57cc2  ldarg.0
0x57cc3  ldnull
0x57cc4  call     class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.TermStoreFactory::GetRemoteTermStore(class [System]System.Uri url, [opt] string userAgentType)
0x57cc9  stloc.s  6
0x57ccb  ldloc.s  6
0x57ccd  ldstr    aRemotetermstor// "remoteTermStore"
0x57cd2  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x57cd7  ldloc.s  6
0x57cd9  ldc.i4.1
0x57cda  newobj   instance void Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::.ctor(class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore termStore, [opt] bool fetchSpecialGroupIds)
0x57cdf  stloc.s  7
0x57ce1  ldloc.s  7
0x57ce3  ldstr    aRemoteservice// "remoteService"
0x57ce8  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x57ced  ldarg.3
0x57cee  brfalse.s loc_57CF5
0x57cf0  ldarg.3
0x57cf1  ldlen
0x57cf2  conv.i4
0x57cf3  brtrue.s loc_57D02
0x57cf5  ldc.i4.1
0x57cf6  stloc.s  4
0x57cf8  ldc.i4.0
0x57cf9  newarr   [mscorlib]System.String
0x57cfe  stloc.s  5
0x57d00  br.s     loc_57D62
0x57d02  ldc.i4.0
0x57d03  stloc.s  8
0x57d05  br.s     loc_57D28
0x57d07  ldarg.3
0x57d08  ldloc.s  8
0x57d0a  ldelem.ref
0x57d0b  ldstr    aReplicatedcont// "replicatedContentTypeNames"
0x57d10  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNullOrEmpty(string value, string parameterName)
0x57d15  ldarg.3
0x57d16  ldloc.s  8
0x57d18  ldarg.3
0x57d19  ldloc.s  8
0x57d1b  ldelem.ref
0x57d1c  callvirt instance string [mscorlib]System.String::Trim()
0x57d21  stelem.ref
0x57d22  ldloc.s  8
0x57d24  ldc.i4.1
0x57d25  add.ovf
0x57d26  stloc.s  8
0x57d28  ldloc.s  8
0x57d2a  ldarg.3
0x57d2b  ldlen
0x57d2c  conv.i4
0x57d2d  blt.s    loc_57D07
0x57d2f  ldarg.3
0x57d30  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x57d35  stloc.s  9
0x57d37  ldarg.3
0x57d38  ldlen
0x57d39  conv.i4
0x57d3a  newarr   [mscorlib]System.String
0x57d3f  stloc.s  5
0x57d41  ldc.i4.0
0x57d42  stloc.s  4
0x57d44  ldloc.s  7
0x57d46  ldloc.s  9
0x57d48  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.SharePoint.Taxonomy.Hybrid.RemoteService::GetTargetContentTypeIds(class [System.Core]System.Collections.Generic.HashSet`1<string> targetContentTypeNames)
0x57d4d  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>::get_Values()
0x57d52  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x57d57  stloc.s  0xA
0x57d59  ldloc.s  0xA
0x57d5b  ldloc.s  5
0x57d5d  callvirt instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::CopyTo(var<u1>[])
0x57d62  ldloc.0
0x57d63  ldarg.1
0x57d64  ldloc.3
0x57d65  ldarg.3
0x57d66  ldloc.s  5
0x57d68  ldloc.s  4
0x57d6a  newobj   instance void Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::.ctor(class [System]System.Uri remoteHubSiteUrl, class [System]System.Uri localSiteUrl, class Microsoft.SharePoint.Taxonomy.TermStore localTermStore, string[] replicatedContentTypeNames, string[] replicatedContentTypeIds, bool isReplicateAllContentTypes)
0x57d6f  stloc.s  0xE
0x57d71  ldloc.s  0xE
0x57d73  ldloc.2
0x57d74  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::set_Schedule(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSchedule)
0x57d79  ldloc.s  0xE
0x57d7b  stloc.s  0xB
0x57d7d  ldloc.s  0xB
0x57d7f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x57d84  ldc.i4   0x14D96CC
0x57d89  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x57d8e  ldc.i4.s 0x32
0x57d90  ldstr    aFinishedSchedu// "Finished scheduling Content Type Replic"...
0x57d95  ldc.i4.1
0x57d96  newarr   [mscorlib]System.Object
0x57d9b  stloc.s  0xF
0x57d9d  ldloc.s  0xF
0x57d9f  ldc.i4.0
0x57da0  ldloc.0
0x57da1  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x57da6  stelem.ref
0x57da7  ldloc.s  0xF
0x57da9  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x57dae  ldloc.3
0x57daf  callvirt instance class [System]System.Uri Microsoft.SharePoint.Taxonomy.TermStore::get_ContentTypePublishingHub()
0x57db4  ldnull
0x57db5  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x57dba  brtrue.s loc_57DCC
0x57dbc  ldloc.3
0x57dbd  callvirt instance class [System]System.Uri Microsoft.SharePoint.Taxonomy.TermStore::get_ContentTypePublishingHub()
0x57dc2  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::Exists(class [System]System.Uri)
0x57dc7  brtrue   loc_57E8F
0x57dcc  newobj   instance void Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletSetSiteSubscriptionMetadataConfig::.ctor()
0x57dd1  stloc.s  0xC
0x57dd3  ldloc.s  0xB
0x57dd5  callvirt instance class [System]System.Uri Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::get_LocalSiteUrl()
0x57dda  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x57ddf  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::.ctor(string)
0x57de4  stloc.s  0xD
0x57de6  ldloc.s  0xC
0x57de8  ldloc.s  0xD
0x57dea  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x57def  newobj   instance void [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPSiteSubscriptionPipeBind::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription)
0x57df4  callvirt instance void Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletSetSiteSubscriptionMetadataConfig::set_Identity(class [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPSiteSubscriptionPipeBind value)
0x57df9  leave.s  loc_57E07
0x57dfb  ldloc.s  0xD
0x57dfd  brfalse.s loc_57E06
0x57dff  ldloc.s  0xD
0x57e01  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x57e06  endfinally
0x57e07  ldloc.s  0xC
0x57e09  ldloc.3
0x57e0a  callvirt instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy Microsoft.SharePoint.Taxonomy.TermStore::get_SharedServiceProxy()
0x57e0f  newobj   instance void Microsoft.SharePoint.Taxonomy.Cmdlet.SPMetadataServiceProxyCmdletPipeBind::.ctor(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy pipedObject)
0x57e14  callvirt instance void Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletSetSiteSubscriptionMetadataConfig::set_ServiceProxy(class Microsoft.SharePoint.Taxonomy.Cmdlet.SPMetadataServiceProxyCmdletPipeBind value)
0x57e19  ldloc.s  0xC
0x57e1b  ldloc.s  0xB
0x57e1d  callvirt instance class [System]System.Uri Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationTimerJobDefinition::get_LocalSiteUrl()
0x57e22  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x57e27  callvirt instance void Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletSetSiteSubscriptionMetadataConfig::set_HubUri(string value)
0x57e2c  ldloc.s  0xC
0x57e2e  callvirt instance bool Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletSetSiteSubscriptionMetadataConfig::ProvisionSiteSubscriptionMetadataConfig()
0x57e33  brtrue.s loc_57E65
0x57e35  ldc.i4   0x15CF65E
0x57e3a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x57e3f  ldc.i4.s 0x32
0x57e41  ldstr    aHybridContentT_11// "Hybrid Content Type: Failed to provisio"...
0x57e46  ldc.i4.2
0x57e47  newarr   [mscorlib]System.Object
0x57e4c  stloc.s  0x10
0x57e4e  ldloc.s  0x10
0x57e50  ldc.i4.0
0x57e51  ldarg.1
0x57e52  stelem.ref
0x57e53  ldloc.s  0x10
0x57e55  ldc.i4.1
0x57e56  ldarg.2
0x57e57  stelem.ref
0x57e58  ldloc.s  0x10
0x57e5a  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x57e5f  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x57e64  throw
0x57e65  ldc.i4   0x15CF65F
0x57e6a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x57e6f  ldc.i4.s 0x32
0x57e71  ldstr    aHybridContentT_12// "Hybrid Content Type: Succeeded to provi"...
0x57e76  ldc.i4.2
0x57e77  newarr   [mscorlib]System.Object
0x57e7c  stloc.s  0x11
0x57e7e  ldloc.s  0x11
0x57e80  ldc.i4.0
0x57e81  ldarg.1
0x57e82  stelem.ref
0x57e83  ldloc.s  0x11
0x57e85  ldc.i4.1
0x57e86  ldarg.2
0x57e87  stelem.ref
0x57e88  ldloc.s  0x11
0x57e8a  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x57e8f  ldloc.s  0xB
0x57e91  ret
```
