# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::Replicate

- ea: `0xc6c0`
- end: `0xc9c3`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::Replicate`
- size: `771`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x39e50`
- `0x57ea0`

## callees

- `0xc6c0`
- `0xd000`
- `0xd020`
- `0xd6e0`
- `0xdbd0`
- `0x10ca0`
- `0x12ff0`
- `0x242a0`
- `0x25480`
- `0x27450`
- `0x28be0`
- `0x387b0`
- `0x4cba0`
- `0x4cf50`
- `0x56c70`
- `0x56e70`
- `0x5bd70`
- `0x5bd90`
- `0x5bdb0`
- `0x5bdc0`
- `0x5be10`
- `0x5be20`
- `0x5fd90`
- `0x72240`
- `0x72260`

## string_xrefs

- `0xc817`: `packageinfo.xml`
- `0xc876`: `[XGeo Content Type] Start replicating Content Types, temporary folder: {0}, last replicate time: {1:u}, pacakge count: {2}`
- `0xc8b4`: `SharePointContentType_ReplicationUpdatedPackages`

## pseudocode

```c

```

## disassembly

```asm
0xc6c0  newobj   instance void <>c__DisplayClassa::.ctor()
0xc6c5  stloc.s  0xC
0xc6c7  ldc.i4.0
0xc6c8  conv.i8
0xc6c9  stloc.0
0xc6ca  ldarg.1
0xc6cb  ldstr    aLocaltermstore// "localTermStore"
0xc6d0  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0xc6d5  ldloc.s  0xC
0xc6d7  ldarg.2
0xc6d8  ldind.ref
0xc6d9  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::get_RemoteHubUrl()
0xc6de  newobj   instance void [System]System.Uri::.ctor(string)
0xc6e3  ldstr    aContenttyperep// "ContentTypeReplication"
0xc6e8  call     class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Hybrid.TermStoreFactory::GetRemoteTermStore(class [System]System.Uri url, [opt] string userAgentType)
0xc6ed  stfld    class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore <>c__DisplayClassa::remoteTermStore
0xc6f2  ldloc.s  0xC
0xc6f4  ldfld    class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore <>c__DisplayClassa::remoteTermStore
0xc6f9  ldstr    aRemotetermstor// "remoteTermStore"
0xc6fe  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0xc703  ldarg.1
0xc704  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.TermStore::get_Session()
0xc709  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomySessionContext Microsoft.SharePoint.Taxonomy.TaxonomySession::get_Context()
0xc70e  callvirt instance string Microsoft.SharePoint.Taxonomy.Internal.TaxonomySessionContext::get_UrlOrEmpty()
0xc713  newobj   instance void [System]System.Uri::.ctor(string)
0xc718  ldnull
0xc719  ldnull
0xc71a  ldarg.s  4
0xc71c  newobj   instance void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserPrincipalNameMapper::.ctor(class [System]System.Uri localSiteUrl, [opt] class Microsoft.SharePoint.Taxonomy.Internal.Hybrid.UserCredential userCred, [opt] string authEndpoint, [opt] string graphApiEndpoint)
0xc721  stloc.1
0xc722  newobj   instance void <>c__DisplayClassc::.ctor()
0xc727  stloc.s  0xA
0xc729  ldloc.s  0xA
0xc72b  ldloc.s  0xC
0xc72d  stfld    class <>c__DisplayClassa <>c__DisplayClassc::CS$<>8__localsb
0xc732  newobj   instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationResult::.ctor()
0xc737  stloc.2
0xc738  ldloc.s  0xA
0xc73a  ldarg.3
0xc73b  brtrue.s loc_C746
0xc73d  ldarg.2
0xc73e  ldind.ref
0xc73f  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::get_ContentTypeLastUpdateTimeUtc()
0xc744  br.s     loc_C754
0xc746  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xc74b  stloc.s  0xE
0xc74d  ldloca.s 0xE
0xc74f  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0xc754  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClassc::lastUpdateTimeUtc
0xc759  ldarg.2
0xc75a  ldind.ref
0xc75b  callvirt instance string[] Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::get_ReplicatedPackagesIdAndMd5()
0xc760  ldsfld   class [mscorlib]System.Func`2<string, string[]> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::CS$<>9__CachedAnonymousMethodDelegate6
0xc765  brtrue.s loc_C778
0xc767  ldnull
0xc768  ldftn    string[] Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::<Replicate>b__1(string package)
0xc76e  newobj   instance void class [mscorlib]System.Func`2<string, string[]>::.ctor(object, native int)
0xc773  stsfld   class [mscorlib]System.Func`2<string, string[]> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::CS$<>9__CachedAnonymousMethodDelegate6
0xc778  ldsfld   class [mscorlib]System.Func`2<string, string[]> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::CS$<>9__CachedAnonymousMethodDelegate6
0xc77d  call     T0x2B00000C
0xc782  ldsfld   class [mscorlib]System.Func`2<string[], string> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::CS$<>9__CachedAnonymousMethodDelegate7
0xc787  brtrue.s loc_C79A
0xc789  ldnull
0xc78a  ldftn    string Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::<Replicate>b__2(string[] package)
0xc790  newobj   instance void class [mscorlib]System.Func`2<string[], string>::.ctor(object, native int)
0xc795  stsfld   class [mscorlib]System.Func`2<string[], string> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::CS$<>9__CachedAnonymousMethodDelegate7
0xc79a  ldsfld   class [mscorlib]System.Func`2<string[], string> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::CS$<>9__CachedAnonymousMethodDelegate7
0xc79f  ldsfld   class [mscorlib]System.Func`2<string[], string> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::CS$<>9__CachedAnonymousMethodDelegate8
0xc7a4  brtrue.s loc_C7B7
0xc7a6  ldnull
0xc7a7  ldftn    string Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::<Replicate>b__3(string[] package)
0xc7ad  newobj   instance void class [mscorlib]System.Func`2<string[], string>::.ctor(object, native int)
0xc7b2  stsfld   class [mscorlib]System.Func`2<string[], string> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::CS$<>9__CachedAnonymousMethodDelegate8
0xc7b7  ldsfld   class [mscorlib]System.Func`2<string[], string> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::CS$<>9__CachedAnonymousMethodDelegate8
0xc7bc  call     T0x2B00000D
0xc7c1  stloc.3
0xc7c2  ldloc.s  0xA
0xc7c4  ldnull
0xc7c5  stfld    class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ClientResult`1<class [mscorlib]System.IO.Stream> <>c__DisplayClassc::packageInfostream
0xc7ca  ldloc.s  0xA
0xc7cc  ldftn    instance void <>c__DisplayClassc::<Replicate>b__4()
0xc7d2  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0xc7d7  ldc.i4.3
0xc7d8  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::RunCsomQueryWithRetries(class [mscorlib]System.Action codeToRunWithRetries, int32 maxAttempts)
0xc7dd  ldloc.s  0xA
0xc7df  ldfld    class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ClientResult`1<class [mscorlib]System.IO.Stream> <>c__DisplayClassc::packageInfostream
0xc7e4  ldstr    aPackageinfostr// "packageInfostream"
0xc7e9  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0xc7ee  ldloc.s  0xA
0xc7f0  ldfld    class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ClientResult`1<class [mscorlib]System.IO.Stream> <>c__DisplayClassc::packageInfostream
0xc7f5  callvirt instance var<u1> class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ClientResult`1<class [mscorlib]System.IO.Stream>::get_Value()
0xc7fa  ldstr    aPackageinfostr_0// "packageInfostream.Value"
0xc7ff  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0xc804  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PackageInfo>::.ctor()
0xc809  stloc.s  4
0xc80b  ldarg.0
0xc80c  call     instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::EnsureTemporaryFolder()
0xc811  ldarg.0
0xc812  call     instance string Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::get_TemporaryLocation()
0xc817  ldstr    aPackageinfoXml// "packageinfo.xml"
0xc81c  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xc821  stloc.s  5
0xc823  ldloc.s  5
0xc825  ldc.i4.2
0xc826  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode)
0xc82b  stloc.s  6
0xc82d  ldloc.s  0xA
0xc82f  ldfld    class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ClientResult`1<class [mscorlib]System.IO.Stream> <>c__DisplayClassc::packageInfostream
0xc834  callvirt instance var<u1> class [Microsoft.SharePoint.Client.Runtime]Microsoft.SharePoint.Client.ClientResult`1<class [mscorlib]System.IO.Stream>::get_Value()
0xc839  ldloc.s  6
0xc83b  callvirt instance void [mscorlib]System.IO.Stream::CopyTo(class [mscorlib]System.IO.Stream)
0xc840  leave.s  loc_C84E
0xc842  ldloc.s  6
0xc844  brfalse.s loc_C84D
0xc846  ldloc.s  6
0xc848  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc84d  endfinally
0xc84e  ldarg.0
0xc84f  ldfld    class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::session
0xc854  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomySession::get_DefaultSiteCollectionTermStore()
0xc859  callvirt instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy Microsoft.SharePoint.Taxonomy.TermStore::get_SharedServiceProxy()
0xc85e  ldloc.2
0xc85f  ldloc.s  5
0xc861  ldloc.s  4
0xc863  call     valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.Subscriber::ReadInfoFile(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy, class Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.SyndicationResult result, string infoFilePath, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PackageInfo> packageList)
0xc868  stloc.s  7
0xc86a  ldc.i4   0x149B600
0xc86f  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xc874  ldc.i4.s 0xF
0xc876  ldstr    aXgeoContentTyp// "[XGeo Content Type] Start replicating C"...
0xc87b  ldc.i4.3
0xc87c  newarr   [mscorlib]System.Object
0xc881  stloc.s  0xF
0xc883  ldloc.s  0xF
0xc885  ldc.i4.0
0xc886  ldarg.0
0xc887  call     instance string Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::get_TemporaryLocation()
0xc88c  stelem.ref
0xc88d  ldloc.s  0xF
0xc88f  ldc.i4.1
0xc890  ldloc.s  0xA
0xc892  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClassc::lastUpdateTimeUtc
0xc897  box      [mscorlib]System.DateTime
0xc89c  stelem.ref
0xc89d  ldloc.s  0xF
0xc89f  ldc.i4.2
0xc8a0  ldloc.s  4
0xc8a2  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PackageInfo>::get_Count()
0xc8a7  box      [mscorlib]System.Int32
0xc8ac  stelem.ref
0xc8ad  ldloc.s  0xF
0xc8af  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xc8b4  ldstr    aSharepointcont// "SharePointContentType_ReplicationUpdate"...
0xc8b9  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0xc8be  stloc.s  9
0xc8c0  ldloc.s  9
0xc8c2  ldstr    aCount// "count"
0xc8c7  ldloc.s  4
0xc8c9  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PackageInfo>::get_Count()
0xc8ce  box      [mscorlib]System.Int32
0xc8d3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xc8d8  ldloc.s  9
0xc8da  ldc.r8   NaN
0xc8e3  call     void Microsoft.SharePoint.Taxonomy.Internal.Hybrid.TaxonomyUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, [opt] float64 durationMs)
0xc8e8  ldloc.s  4
0xc8ea  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PackageInfo>::GetEnumerator()
0xc8ef  stloc.s  0x10
0xc8f1  br.s     loc_C918
0xc8f3  ldloca.s 0x10
0xc8f5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PackageInfo>::get_Current()
0xc8fa  stloc.s  8
0xc8fc  ldloc.0
0xc8fd  ldarg.0
0xc8fe  ldloc.s  0xC
0xc900  ldfld    class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore <>c__DisplayClassa::remoteTermStore
0xc905  ldarg.1
0xc906  ldloc.s  8
0xc908  ldloc.3
0xc909  ldarg.2
0xc90a  ldind.ref
0xc90b  callvirt instance bool Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::get_IsReplicateAllPackages()
0xc910  ldloc.1
0xc911  call     instance valuetype Microsoft.SharePoint.Taxonomy.Hybrid.ContentTypeReplicationStatus Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::ReplicateContentType(class [Microsoft.SharePoint.Client.Taxonomy]Microsoft.SharePoint.Client.Taxonomy.TermStore remoteTermStore, class Microsoft.SharePoint.Taxonomy.TermStore localTermStore, class Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PackageInfo packageInfo, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> packageMd5Map, bool replicateAllContentTypes, class Microsoft.SharePoint.Taxonomy.Internal.Hybrid.UserPrincipalNameMapper userPrincipalNameMapper)
0xc916  or
0xc917  stloc.0
0xc918  ldloca.s 0x10
0xc91a  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PackageInfo>::MoveNext()
0xc91f  brtrue.s loc_C8F3
0xc921  leave.s  loc_C931
0xc923  ldloca.s 0x10
0xc925  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.PackageInfo>
0xc92b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc930  endfinally
0xc931  ldc.i4   0x149B603
0xc936  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xc93b  ldc.i4.s 0xF
0xc93d  ldstr    aXgeoContentTyp_0// "[XGeo Content Type] Finished replicatin"...
0xc942  ldc.i4.1
0xc943  newarr   [mscorlib]System.Object
0xc948  stloc.s  0x11
0xc94a  ldloc.s  0x11
0xc94c  ldc.i4.0
0xc94d  ldloc.s  7
0xc94f  box      [mscorlib]System.DateTime
0xc954  stelem.ref
0xc955  ldloc.s  0x11
0xc957  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xc95c  ldarg.2
0xc95d  ldind.ref
0xc95e  ldloc.s  7
0xc960  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::set_ContentTypeLastUpdateTimeUtc(valuetype [mscorlib]System.DateTime value)
0xc965  ldarg.2
0xc966  ldind.ref
0xc967  ldloc.3
0xc968  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::CS$<>9__CachedAnonymousMethodDelegate9
0xc96d  brtrue.s loc_C980
0xc96f  ldnull
0xc970  ldftn    string Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::<Replicate>b__5(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> packageMd5)
0xc976  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string>::.ctor(object, native int)
0xc97b  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::CS$<>9__CachedAnonymousMethodDelegate9
0xc980  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::CS$<>9__CachedAnonymousMethodDelegate9
0xc985  call     T0x2B00000E
0xc98a  call     T0x2B00000F
0xc98f  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyReplicationParameters::set_ReplicatedPackagesIdAndMd5(string[] value)
0xc994  ldloc.0
0xc995  stloc.s  0xD
0xc997  leave.s  loc_C9C0
0xc999  stloc.s  0xB
0xc99b  ldc.i4   0x149B604
0xc9a0  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xc9a5  ldloc.s  0xB
0xc9a7  ldstr    aXgeoContentTyp_1// "[XGeo Content Type] Replication failed"
0xc9ac  ldc.i4.0
0xc9ad  newarr   [mscorlib]System.Object
0xc9b2  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, class [mscorlib]System.Exception, string, object[])
0xc9b7  rethrow
0xc9b9  ldarg.0
0xc9ba  call     instance void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubSharedContentTypeManager::CleanUpTemporaryFolder()
0xc9bf  endfinally
0xc9c0  ldloc.s  0xD
0xc9c2  ret
```
