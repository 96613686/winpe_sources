# Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentManifestReader::FindComponents

- ea: `0x433f50`
- end: `0x434470`
- name: `Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentManifestReader::FindComponents`
- size: `1312`
- prototype: ``
- caller_count: `2`
- callee_count: `35`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x433ab0`
- `0x433b80`

## callees

- `0x232050`
- `0x26b840`
- `0x26f690`
- `0x3192a0`
- `0x42ced0`
- `0x42ea90`
- `0x42f370`
- `0x431f30`
- `0x4322d0`
- `0x432700`
- `0x433f50`
- `0x434560`
- `0x435890`
- `0x4358c0`
- `0x435910`
- `0x435aa0`
- `0x4361f0`
- `0x436200`
- `0x436320`
- `0x436410`
- `0x436420`
- `0x436bc0`
- `0x436cc0`
- `0x436d00`
- `0x5c24f0`
- `0x6c9890`
- `0x7be4d0`
- `0x7be510`
- `0x7be540`
- `0x7be580`
- `0x7beb40`
- `0x8ecdb0`
- `0x93dab0`
- `0x93dae0`
- `0x957470`

## string_xrefs

- `0x433f95`: `Get component by version`
- `0x433fd1`: `Get component by version`
- `0x433ff9`: `Get component by version`
- `0x43410d`: `Log not found component id info`
- `0x4341e1`: `Log not found component id info`
- `0x43428b`: `Log not found component id info`
- `0x433f66`: `First party client side component retrieval`
- `0x434034`: `[SPClientSideComponentManifestReader.FindComponents] Following components were not found in first party provider : {0}`
- `0x43407d`: `Client web part component retrieval`
- `0x4340b4`: `Third party cached client side component retrieval`
- `0x434125`: `Not found components: {0}`
- `0x434259`: `Not found components: {0}`
- `0x43416b`: `Third party site collection client side component retrieval`
- `0x4341ab`: `Third party tenant client side component retrieval`
- `0x4341fc`: `FirstPartyManifests found: {0}, ClientWebPartManifests found: {1}, ClientWebPartManifests found: {2}, ThirdPartyTenantManifests found: {3}, ThirdPartySiteCollectionManifests found: {4}`
- `0x4342a6`: `Third Party Cache Reliability`
- `0x4342e8`: `Cache miss`
- `0x43430b`: `ComponentFoundManifests`
- `0x434319`: `TotalManifests`
- `0x43432b`: `FirstPartyManifests`
- `0x43433d`: `ClientWebPartManifests`
- `0x43434f`: `CachedThirdPartyManifests`
- `0x434362`: `ThirdPartyTenantManifests`
- `0x434375`: `ThirdPartySiteCollectionManifests`
- `0x434388`: `DevCookieDebugManifests`
- `0x4343b5`: `[SPClientSideComponentManifestReader.FindComponents] Following components were not found in first and third party providers : {0}`
- `0x434408`: `componentIds:`
- `0x43443a`: `Found more manifests than required`

## pseudocode

```c

```

## disassembly

```asm
0x433f50  ldarg.0
0x433f51  callvirt instance int32 Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection::get_Count()
0x433f56  stloc.0
0x433f57  ldc.i4.0
0x433f58  stloc.1
0x433f59  ldc.i4.0
0x433f5a  stloc.2
0x433f5b  ldc.i4.0
0x433f5c  stloc.3
0x433f5d  ldc.i4.0
0x433f5e  stloc.s  4
0x433f60  ldc.i4.0
0x433f61  stloc.s  5
0x433f63  ldc.i4.0
0x433f64  stloc.s  6
0x433f66  ldstr    aFirstPartyClie// "First party client side component retri"...
0x433f6b  ldc.i4.s 0x32
0x433f6d  ldc.i4.0
0x433f6e  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x433f73  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceLevel, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x433f78  stloc.s  7
0x433f7a  ldarg.3
0x433f7b  newobj   instance void Microsoft.SharePoint.ClientSideComponent.SPClientSideDevCookieDebugComponentProvider::.ctor(class Microsoft.SharePoint.ClientSideComponent.IClientSideDevCookie devCookie)
0x433f80  stloc.s  8
0x433f82  ldloc.s  8
0x433f84  callvirt instance bool Microsoft.SharePoint.ClientSideComponent.SPClientSideDevCookieDebugComponentProvider::get_ShouldLoadManifest()
0x433f89  brfalse.s loc_433FEF
0x433f8b  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentManifestReader::GetComponentByVersionKillSwitch
0x433f90  ldstr    a20171013// "2017/10/13"
0x433f95  ldstr    aGetComponentBy// "Get component by version"
0x433f9a  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x433f9f  brtrue.s loc_433FAC
0x433fa1  ldloc.s  8
0x433fa3  ldarg.0
0x433fa4  callvirt instance int32 Microsoft.SharePoint.ClientSideComponent.SPClientSideDevCookieDebugComponentProvider::GetNotFoundQueryResults(class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection requests)
0x433fa9  stloc.1
0x433faa  br.s     loc_433FB5
0x433fac  ldloc.s  8
0x433fae  ldarg.0
0x433faf  callvirt instance int32 Microsoft.SharePoint.ClientSideComponent.SPClientSideDevCookieDebugComponentProvider::GetNotFoundComponents(class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection requests)
0x433fb4  stloc.1
0x433fb5  ldloc.s  8
0x433fb7  callvirt instance bool Microsoft.SharePoint.ClientSideComponent.SPClientSideDevCookieDebugComponentProvider::get_ShouldLoadManifest()
0x433fbc  brfalse.s loc_433FC7
0x433fbe  ldloc.s  8
0x433fc0  callvirt instance bool Microsoft.SharePoint.ClientSideComponent.SPClientSideDevCookieDebugComponentProvider::get_IsLoadingSpecifiedComponents()
0x433fc5  brfalse.s loc_434015
0x433fc7  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentManifestReader::GetComponentByVersionKillSwitch
0x433fcc  ldstr    a20171013// "2017/10/13"
0x433fd1  ldstr    aGetComponentBy// "Get component by version"
0x433fd6  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x433fdb  brtrue.s loc_433FE6
0x433fdd  ldarg.0
0x433fde  call     int32 Microsoft.SharePoint.ClientSideComponent.SPClientSideFirstPartyComponentProvider::GetNotFoundQueryResults(class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection requests)
0x433fe3  stloc.2
0x433fe4  br.s     loc_434015
0x433fe6  ldarg.0
0x433fe7  call     int32 Microsoft.SharePoint.ClientSideComponent.SPClientSideFirstPartyComponentProvider::GetNotFoundComponents(class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection requests)
0x433fec  stloc.2
0x433fed  br.s     loc_434015
0x433fef  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentManifestReader::GetComponentByVersionKillSwitch
0x433ff4  ldstr    a20171013// "2017/10/13"
0x433ff9  ldstr    aGetComponentBy// "Get component by version"
0x433ffe  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x434003  brtrue.s loc_43400E
0x434005  ldarg.0
0x434006  call     int32 Microsoft.SharePoint.ClientSideComponent.SPClientSideFirstPartyComponentProvider::GetNotFoundQueryResults(class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection requests)
0x43400b  stloc.2
0x43400c  br.s     loc_434015
0x43400e  ldarg.0
0x43400f  call     int32 Microsoft.SharePoint.ClientSideComponent.SPClientSideFirstPartyComponentProvider::GetNotFoundComponents(class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection requests)
0x434014  stloc.2
0x434015  leave.s  loc_434023
0x434017  ldloc.s  7
0x434019  brfalse.s loc_434022
0x43401b  ldloc.s  7
0x43401d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x434022  endfinally
0x434023  ldc.i4   0x1218819
0x434028  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x43402d  ldc.i4.s 0x64
0x43402f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x434034  ldstr    aSpclientsideco_11// "[SPClientSideComponentManifestReader.Fi"...
0x434039  ldc.i4.1
0x43403a  newarr   [mscorlib]System.Object
0x43403f  stloc.s  0x17
0x434041  ldloc.s  0x17
0x434043  ldc.i4.0
0x434044  ldstr    asc_C6AA4A// ","
0x434049  ldarg.0
0x43404a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection::get_NotFoundComponents()
0x43404f  call     T0x2B0000EA
0x434054  stelem.ref
0x434055  ldloc.s  0x17
0x434057  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x43405c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x434061  ldarg.0
0x434062  callvirt instance bool Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection::get_HasNotFoundComponents()
0x434067  stloc.s  9
0x434069  ldloc.s  9
0x43406b  brfalse.s loc_4340B0
0x43406d  ldarg.0
0x43406e  call     bool Microsoft.SharePoint.ClientSideComponent.SPClientWebPartComponentProvider::HasClientWebParts(class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection queryResults)
0x434073  brfalse.s loc_4340B0
0x434075  ldarg.1
0x434076  newobj   instance void Microsoft.SharePoint.ClientSideComponent.SPClientWebPartComponentProvider::.ctor(class Microsoft.SharePoint.SPWeb web)
0x43407b  stloc.s  0xA
0x43407d  ldstr    aClientWebPartC// "Client web part component retrieval"
0x434082  ldc.i4.s 0x32
0x434084  ldc.i4.0
0x434085  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x43408a  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceLevel, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x43408f  stloc.s  0xB
0x434091  ldloc.s  0xA
0x434093  ldarg.0
0x434094  callvirt instance int32 Microsoft.SharePoint.ClientSideComponent.SPClientWebPartComponentProvider::GetNotFoundComponents(class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection requests)
0x434099  stloc.3
0x43409a  leave.s  loc_4340A8
0x43409c  ldloc.s  0xB
0x43409e  brfalse.s loc_4340A7
0x4340a0  ldloc.s  0xB
0x4340a2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4340a7  endfinally
0x4340a8  ldarg.0
0x4340a9  callvirt instance bool Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection::get_HasNotFoundComponents()
0x4340ae  stloc.s  9
0x4340b0  ldloc.s  9
0x4340b2  brfalse.s loc_4340FC
0x4340b4  ldstr    aThirdPartyCach// "Third party cached client side componen"...
0x4340b9  ldc.i4.s 0x32
0x4340bb  ldc.i4.0
0x4340bc  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x4340c1  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceLevel, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x4340c6  stloc.s  0xC
0x4340c8  ldarg.0
0x4340c9  ldarg.1
0x4340ca  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x4340cf  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.SPSite::get_SiteSubscription()
0x4340d4  ldarg.1
0x4340d5  callvirt instance class Microsoft.SharePoint.SPSite Microsoft.SharePoint.SPWeb::get_Site()
0x4340da  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSite::get_ID()
0x4340df  call     int32 Microsoft.SharePoint.ClientSideComponent.SPClientSideCachedThirdPartyComponentProvider::GetNotFoundComponents(class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection requests, class Microsoft.SharePoint.SPSiteSubscription subscription, valuetype [mscorlib]System.Guid siteId)
0x4340e4  stloc.s  6
0x4340e6  leave.s  loc_4340F4
0x4340e8  ldloc.s  0xC
0x4340ea  brfalse.s loc_4340F3
0x4340ec  ldloc.s  0xC
0x4340ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4340f3  endfinally
0x4340f4  ldarg.0
0x4340f5  callvirt instance bool Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection::get_HasNotFoundComponents()
0x4340fa  stloc.s  9
0x4340fc  ldloc.s  9
0x4340fe  brfalse  loc_43419F
0x434103  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentManifestReader::LogInfoAboutNotFoundComponents
0x434108  ldstr    a2212018// "2/21/2018"
0x43410d  ldstr    aLogNotFoundCom// "Log not found component id info"
0x434112  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x434117  brtrue.s loc_43414D
0x434119  ldc.i4   0x229C71D
0x43411e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x434123  ldc.i4.s 0x32
0x434125  ldstr    aNotFoundCompon// "Not found components: {0}"
0x43412a  ldc.i4.1
0x43412b  newarr   [mscorlib]System.Object
0x434130  stloc.s  0x18
0x434132  ldloc.s  0x18
0x434134  ldc.i4.0
0x434135  ldstr    asc_C6AA4A// ","
0x43413a  ldarg.0
0x43413b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection::get_NotFoundComponents()
0x434140  call     T0x2B0000EA
0x434145  stelem.ref
0x434146  ldloc.s  0x18
0x434148  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x43414d  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Marketplace.CorporateCuratedGallery.SPCorporateCatalogAccessorBase::SiteCollectionCatalogKillSwitch
0x434152  ldstr    a10312016// "10/31/2016"
0x434157  ldstr    aEnableSiteColl// "Enable site collection app catalog"
0x43415c  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x434161  brtrue.s loc_43419F
0x434163  ldarg.1
0x434164  newobj   instance void Microsoft.SharePoint.ClientSideComponent.SPSiteCollectionAppCatalogProvider::.ctor(class Microsoft.SharePoint.SPWeb web)
0x434169  stloc.s  0xD
0x43416b  ldstr    aThirdPartySite// "Third party site collection client side"...
0x434170  ldc.i4.s 0x32
0x434172  ldc.i4.0
0x434173  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x434178  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceLevel, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x43417d  stloc.s  0xE
0x43417f  ldloc.s  0xD
0x434181  ldarg.0
0x434182  callvirt instance int32 Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::GetNotFoundComponents(class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection requests)
0x434187  stloc.s  4
0x434189  leave.s  loc_434197
0x43418b  ldloc.s  0xE
0x43418d  brfalse.s loc_434196
0x43418f  ldloc.s  0xE
0x434191  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x434196  endfinally
0x434197  ldarg.0
0x434198  callvirt instance bool Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection::get_HasNotFoundComponents()
0x43419d  stloc.s  9
0x43419f  ldloc.s  9
0x4341a1  brfalse.s loc_4341D7
0x4341a3  ldarg.1
0x4341a4  newobj   instance void Microsoft.SharePoint.ClientSideComponent.SPTenantAppCatalogProvider::.ctor(class Microsoft.SharePoint.SPWeb web)
0x4341a9  stloc.s  0xF
0x4341ab  ldstr    aThirdPartyTena// "Third party tenant client side componen"...
0x4341b0  ldc.i4.s 0x32
0x4341b2  ldc.i4.0
0x4341b3  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x4341b8  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceLevel, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x4341bd  stloc.s  0x10
0x4341bf  ldloc.s  0xF
0x4341c1  ldarg.0
0x4341c2  callvirt instance int32 Microsoft.SharePoint.ClientSideComponent.SPClientSideThirdPartyComponentProvider::GetNotFoundComponents(class Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection requests)
0x4341c7  stloc.s  5
0x4341c9  leave.s  loc_4341D7
0x4341cb  ldloc.s  0x10
0x4341cd  brfalse.s loc_4341D6
0x4341cf  ldloc.s  0x10
0x4341d1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4341d6  endfinally
0x4341d7  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentManifestReader::LogInfoAboutNotFoundComponents
0x4341dc  ldstr    a2212018// "2/21/2018"
0x4341e1  ldstr    aLogNotFoundCom// "Log not found component id info"
0x4341e6  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x4341eb  brtrue   loc_43430B
0x4341f0  ldc.i4   0x229C71E
0x4341f5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x4341fa  ldc.i4.s 0x32
0x4341fc  ldstr    aFirstpartymani// "FirstPartyManifests found: {0}, ClientW"...
0x434201  ldc.i4.5
0x434202  newarr   [mscorlib]System.Object
0x434207  stloc.s  0x19
0x434209  ldloc.s  0x19
0x43420b  ldc.i4.0
0x43420c  ldloc.2
0x43420d  box      [mscorlib]System.Int32
0x434212  stelem.ref
0x434213  ldloc.s  0x19
0x434215  ldc.i4.1
0x434216  ldloc.3
0x434217  box      [mscorlib]System.Int32
0x43421c  stelem.ref
0x43421d  ldloc.s  0x19
0x43421f  ldc.i4.2
0x434220  ldloc.s  6
0x434222  box      [mscorlib]System.Int32
0x434227  stelem.ref
0x434228  ldloc.s  0x19
0x43422a  ldc.i4.3
0x43422b  ldloc.s  5
0x43422d  box      [mscorlib]System.Int32
0x434232  stelem.ref
0x434233  ldloc.s  0x19
0x434235  ldc.i4.4
0x434236  ldloc.s  4
0x434238  box      [mscorlib]System.Int32
0x43423d  stelem.ref
0x43423e  ldloc.s  0x19
0x434240  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x434245  ldarg.0
0x434246  callvirt instance bool Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection::get_HasNotFoundComponents()
0x43424b  brfalse.s loc_434281
0x43424d  ldc.i4   0x229C71F
0x434252  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x434257  ldc.i4.s 0xA
0x434259  ldstr    aNotFoundCompon// "Not found components: {0}"
0x43425e  ldc.i4.1
0x43425f  newarr   [mscorlib]System.Object
0x434264  stloc.s  0x1A
0x434266  ldloc.s  0x1A
0x434268  ldc.i4.0
0x434269  ldstr    asc_C6AA4A// ","
0x43426e  ldarg.0
0x43426f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentQueryResultCollection::get_NotFoundComponents()
0x434274  call     T0x2B0000EA
0x434279  stelem.ref
0x43427a  ldloc.s  0x1A
0x43427c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x434281  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ClientSideComponent.SPClientSideComponentManifestReader::ThirdPartyCacheReliabilityMonitorKillSwitch
0x434286  ldstr    a3232018// "3/23/2018"
0x43428b  ldstr    aLogNotFoundCom// "Log not found component id info"
0x434290  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x434295  brtrue.s loc_43430B
0x434297  ldloc.s  6
0x434299  ldc.i4.0
0x43429a  bgt.s    loc_4342A6
0x43429c  ldloc.s  4
0x43429e  ldc.i4.0
0x43429f  bgt.s    loc_4342A6
0x4342a1  ldloc.s  5
0x4342a3  ldc.i4.0
0x4342a4  ble.s    loc_43430B
0x4342a6  ldstr    aThirdPartyCach_0// "Third Party Cache Reliability"
0x4342ab  ldc.i4   0x23025DA
0x4342b0  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x4342b5  ldc.i4   0x23025DB
0x4342ba  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
  ... truncated ...
```
