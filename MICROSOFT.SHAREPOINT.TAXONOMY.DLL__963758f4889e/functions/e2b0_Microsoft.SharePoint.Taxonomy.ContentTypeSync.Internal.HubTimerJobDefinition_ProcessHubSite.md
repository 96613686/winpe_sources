# Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::ProcessHubSite

- ea: `0xe2b0`
- end: `0xe46b`
- name: `Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::ProcessHubSite`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xde00`

## callees

- `0xe2b0`
- `0xe470`
- `0xe580`
- `0xe6b0`
- `0xeab0`
- `0x4baa0`

## string_xrefs

- `0xe368`: `MetadataHubPreviousToken`
- `0xe39d`: `Skip processing changes on the hub site {0} because of same token.`
- `0xe3ce`: `Skip processing changes on the hub site {0} because of CurrentChangeToken is null.`

## pseudocode

```c

```

## disassembly

```asm
0xe2b0  ldnull
0xe2b1  stloc.0
0xe2b2  ldarg.0
0xe2b3  callvirt instance string [mscorlib]System.Object::ToString()
0xe2b8  stloc.1
0xe2b9  ldc.i4   0x61306738
0xe2be  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xe2c3  ldc.i4.s 0x64
0xe2c5  ldstr    aProcessingHubS// "Processing hub site {0}"
0xe2ca  ldc.i4.1
0xe2cb  newarr   [mscorlib]System.Object
0xe2d0  stloc.s  7
0xe2d2  ldloc.s  7
0xe2d4  ldc.i4.0
0xe2d5  ldloc.1
0xe2d6  stelem.ref
0xe2d7  ldloc.s  7
0xe2d9  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xe2de  ldloc.1
0xe2df  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::.ctor(string)
0xe2e4  dup
0xe2e5  stloc.0
0xe2e6  stloc.s  8
0xe2e8  ldloc.0
0xe2e9  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFeatureCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_Features()
0xe2ee  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.FeatureIds::MetadataHub
0xe2f3  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFeature [Microsoft.SharePoint]Microsoft.SharePoint.SPFeatureCollection::get_Item(valuetype [mscorlib]System.Guid)
0xe2f8  brtrue.s loc_E324
0xe2fa  ldc.i4   0x38797138
0xe2ff  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xe304  ldc.i4.s 0xA
0xe306  ldstr    aTheSite0DoesNo// "The site {0} does not have hub feature "...
0xe30b  ldc.i4.1
0xe30c  newarr   [mscorlib]System.Object
0xe311  stloc.s  9
0xe313  ldloc.s  9
0xe315  ldc.i4.0
0xe316  ldloc.1
0xe317  stelem.ref
0xe318  ldloc.s  9
0xe31a  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xe31f  br       loc_E3EF
0xe324  ldloc.0
0xe325  newobj   instance void Microsoft.SharePoint.Taxonomy.TaxonomySession::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site)
0xe32a  stloc.2
0xe32b  ldloc.0
0xe32c  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb [Microsoft.SharePoint]Microsoft.SharePoint.SPSite::get_RootWeb()
0xe331  stloc.3
0xe332  ldloc.3
0xe333  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::GetPreviousChangeToken(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb rootWeb)
0xe338  stloc.s  4
0xe33a  ldloc.3
0xe33b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_CurrentChangeToken()
0xe340  stloc.s  5
0xe342  ldloc.s  4
0xe344  ldloc.s  5
0xe346  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken, class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken)
0xe34b  brfalse.s loc_E386
0xe34d  ldloc.s  5
0xe34f  ldnull
0xe350  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken, class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken)
0xe355  brfalse.s loc_E386
0xe357  ldloc.3
0xe358  ldloc.s  4
0xe35a  ldloc.s  5
0xe35c  call     int32 Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::ProcessChanges(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb rootWeb, class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken previousToken, class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken currentToken)
0xe361  pop
0xe362  ldloc.3
0xe363  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPropertyBag [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Properties()
0xe368  ldstr    aMetadatahubpre// "MetadataHubPreviousToken"
0xe36d  ldloc.s  5
0xe36f  callvirt instance string [mscorlib]System.Object::ToString()
0xe374  callvirt instance void [System]System.Collections.Specialized.StringDictionary::set_Item(string, string)
0xe379  ldloc.3
0xe37a  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPropertyBag [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Properties()
0xe37f  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPPropertyBag::Update()
0xe384  br.s     loc_E3E7
0xe386  ldloc.s  4
0xe388  ldloc.s  5
0xe38a  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken, class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken)
0xe38f  brfalse.s loc_E3B8
0xe391  ldc.i4   0x11341E
0xe396  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xe39b  ldc.i4.s 0x64
0xe39d  ldstr    aSkipProcessing// "Skip processing changes on the hub site"...
0xe3a2  ldc.i4.1
0xe3a3  newarr   [mscorlib]System.Object
0xe3a8  stloc.s  0xA
0xe3aa  ldloc.s  0xA
0xe3ac  ldc.i4.0
0xe3ad  ldloc.1
0xe3ae  stelem.ref
0xe3af  ldloc.s  0xA
0xe3b1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xe3b6  br.s     loc_E3E7
0xe3b8  ldloc.s  5
0xe3ba  ldnull
0xe3bb  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken, class [Microsoft.SharePoint]Microsoft.SharePoint.SPChangeToken)
0xe3c0  brfalse.s loc_E3E7
0xe3c2  ldc.i4   0x11341F
0xe3c7  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xe3cc  ldc.i4.s 0xA
0xe3ce  ldstr    aSkipProcessing_0// "Skip processing changes on the hub site"...
0xe3d3  ldc.i4.1
0xe3d4  newarr   [mscorlib]System.Object
0xe3d9  stloc.s  0xB
0xe3db  ldloc.s  0xB
0xe3dd  ldc.i4.0
0xe3de  ldloc.1
0xe3df  stelem.ref
0xe3e0  ldloc.s  0xB
0xe3e2  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xe3e7  ldloc.2
0xe3e8  ldloc.3
0xe3e9  ldarg.1
0xe3ea  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::SynchronizeLog(class Microsoft.SharePoint.Taxonomy.TaxonomySession session, class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb rootWeb, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy> proxyList)
0xe3ef  ldc.i4   0x140
0xe3f4  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0xe3f9  brfalse.s loc_E401
0xe3fb  ldloc.0
0xe3fc  call     void Microsoft.SharePoint.Taxonomy.ContentTypeSync.Internal.HubTimerJobDefinition::UpgradeHubIfOnly14ModeSite(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite hubSite)
0xe401  leave.s  loc_E40F
0xe403  ldloc.s  8
0xe405  brfalse.s loc_E40E
0xe407  ldloc.s  8
0xe409  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe40e  endfinally
0xe40f  leave.s  loc_E445
0xe411  stloc.s  6
0xe413  ldc.i4   0x38797165
0xe418  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xe41d  ldc.i4.s 0xA
0xe41f  ldstr    aFailedToProces// "Failed to process hub site {0}: {1}"
0xe424  ldc.i4.2
0xe425  newarr   [mscorlib]System.Object
0xe42a  stloc.s  0xC
0xe42c  ldloc.s  0xC
0xe42e  ldc.i4.0
0xe42f  ldloc.1
0xe430  stelem.ref
0xe431  ldloc.s  0xC
0xe433  ldc.i4.1
0xe434  ldloc.s  6
0xe436  callvirt instance string [mscorlib]System.Exception::get_Message()
0xe43b  stelem.ref
0xe43c  ldloc.s  0xC
0xe43e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xe443  leave.s  loc_E445
0xe445  ldc.i4   0x61306739
0xe44a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0xe44f  ldc.i4.s 0x64
0xe451  ldstr    aProcessedHubSi// "Processed hub site {0}"
0xe456  ldc.i4.1
0xe457  newarr   [mscorlib]System.Object
0xe45c  stloc.s  0xD
0xe45e  ldloc.s  0xD
0xe460  ldc.i4.0
0xe461  ldloc.1
0xe462  stelem.ref
0xe463  ldloc.s  0xD
0xe465  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0xe46a  ret
```
