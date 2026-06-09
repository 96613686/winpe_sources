# Microsoft.SharePoint.Administration.SPSiteMaster::IsValid

- ea: `0x2fdfc0`
- end: `0x2fea1e`
- name: `Microsoft.SharePoint.Administration.SPSiteMaster::IsValid`
- size: `2654`
- prototype: ``
- caller_count: `3`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0xbbb5a0`
- `0xbbbb80`
- `0xbbbcb0`

## callees

- `0x17f890`
- `0x1c8480`
- `0x25ce40`
- `0x269af0`
- `0x26bde0`
- `0x26f690`
- `0x2781e0`
- `0x29d0f0`
- `0x2fdc00`
- `0x2fdc20`
- `0x2fdc40`
- `0x2fdc60`
- `0x2fdc80`
- `0x2fdd60`
- `0x2fdd80`
- `0x2fdda0`
- `0x2fdfc0`
- `0x300430`
- `0x32be50`
- `0x32cb80`
- `0x577060`
- `0x590b30`
- `0x594c60`
- `0x5966e0`
- `0x6c9890`
- `0x7be4d0`
- `0x7be540`
- `0x7beb40`
- `0x8ecdb0`
- `0x93dae0`
- `0x957e90`

## string_xrefs

- `0x2fdfd8`: `SPSiteMaster.ForceNoValidationODBTemplate`
- `0x2fe062`: `SPSiteMaster.ForceNoValidationGroupTemplate`
- `0x2fe078`: `SPSiteMaster.ForceNoValidationPublishingTemplate`
- `0x2fe08e`: `SPSiteMaster.ForceNoValidationRedirectSiteTemplate`
- `0x2fe0ee`: `[SiteMaster.IsValid]: Template [{0}] is in SoftLock! SiteMaster Validation based on Farm Feature Hash, etc NOT NEEDED for Site Id: [{1}] in  Database: [{2}], Language: [{3}].`
- `0x2fe158`: `[SiteMaster.IsValid]: Template [{0}] is NOT in SoftLock!  SiteMaster Validation based on Farm Feature Hash, etc NEEDED for Site Id: [{1}] in  Database: [{2}], Language: [{3}].`
- `0x2fe1bb`: `[SiteMaster.IsValid]: SoftLock check NOT done for template [{0}]! honorSoftLock=[{1}].  Extensive checks will be done.  doAdditionalValidityChecks=[{2}] `
- `0x2fe27c`: `Skipping Site master needs upgrade check for SiteId [{0}] with Template: [{1}]`
- `0x2fe2ea`: `Site master validation. Id: [{0}], Url: [{1}] Template: [{2}], Database: [{3}], Language: [{4}], LastValidationTime: [{5}]`
- `0x2fe397`: `Site master has invalid subscription id [{1}]. Invalidating this site master. Id: [{0}], Expected Id: [{2}], Url: [{3}], Template: [{4}], Database: [{5}], Language: [{6}]`
- `0x2fe45a`: `Site master needs upgrade, SiteId: [{0}], Url: [{1}] Template: [{2}], Database: [{3}], Language: [{4}]`
- `0x2fe549`: `Master validation period expired. Check if the [{0}] timer job is running. SiteId: [{1}], Template: [{2}], Database: [{3}], Language: [{4}]`
- `0x2fe5e7`: `[ODB Modified Soft Lock]: SKIPPING Feature Hash Check for ODB! shouldSkipFarmFeatureHashCheckForODB; [{0}] Template: [{1}], Database: [{2}], Language: [{3}]`
- `0x2fe63c`: `[ODB Modified Soft Lock]: Proceeding with Feature Hash Check for ODB! shouldSkipFarmFeatureHashCheckForODB; [{0}] Template: [{1}], Database: [{2}], Language: [{3}]`
- `0x2fe6a9`: `Site master Hash does not match features Hash. SiteId: [{0}], stored: [{1}], computed: [{2}], Url: [{3}], Template: [{4}], Database: [{5}], Language: [{6}]`
- `0x2fe739`: `Site master Hash MATCH features Hash. SiteId: [{0}], stored: [{1}], computed: [{2}], Url: [{3}], Template: [{4}], Database: [{5}], Language: [{6}]`
- `0x2fe7e6`: `SiteMaster NOT FOUND from SPSiteCache.LookupById(). SiteMaster is NOT Valid!  Template is [{0}] for Site Id: [{1}] in  Database: [{2}], Language: [{3}].`
- `0x2fe84e`: `Site master IsValid threw an exception for SiteId: [{0}], Url: [{1}], Template: [{2}], Database: [{3}], Language: [{4}].  Exception Details: [{5}]`
- `0x2fe907`: `Site master IsValid is TRUE!: [{0}], Template: [{1}], Database: [{2}], Language: [{3}].  siteSubscriptionCheckPassed: [{4}]; upgradeCheckPassed:[{5}]; featuresHashCheckPassed:[{6}]; spSiteLookUpCheckPassed:[{7}];`
- `0x2fe99b`: `Site master IsValid is FALSE!: [{0}], Template: [{1}], Database: [{2}], Language: [{3}].  siteSubscriptionCheckPassed: [{4}]; upgradeCheckPassed:[{5}]; featuresHashCheckPassed:[{6}]; spSiteLookUpCheckPassed:[{7}];`

## pseudocode

```c

```

## disassembly

```asm
0x2fdfc0  ldc.i4.1
0x2fdfc1  stloc.0
0x2fdfc2  ldc.i4.1
0x2fdfc3  stloc.1
0x2fdfc4  ldc.i4.1
0x2fdfc5  stloc.2
0x2fdfc6  ldc.i4.1
0x2fdfc7  stloc.3
0x2fdfc8  ldc.i4.1
0x2fdfc9  stloc.s  4
0x2fdfcb  ldc.i4.1
0x2fdfcc  stloc.s  5
0x2fdfce  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteMaster::DoNotOverwriteSiteMasterIsValidChecksKillSwitchGuid
0x2fdfd3  ldstr    a1172017_0// "1/17/2017"
0x2fdfd8  ldstr    aSpsitemasterFo// "SPSiteMaster.ForceNoValidationODBTempla"...
0x2fdfdd  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x2fdfe2  ldc.i4.0
0x2fdfe3  ceq
0x2fdfe5  stloc.s  6
0x2fdfe7  ldstr    aSpsitemasterIs// "SPSiteMaster.IsValid"
0x2fdfec  ldc.i4   0x622460
0x2fdff1  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x2fdff6  ldc.i4   0x622461
0x2fdffb  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x2fe000  ldc.i4   0x622462
0x2fe005  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x2fe00a  ldc.i4.0
0x2fe00b  ldnull
0x2fe00c  newobj   instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitor::.ctor(string scenarioName, unsigned int32 startTag, unsigned int32 successTag, unsigned int32 unexpectedFailureTag, [opt] valuetype Microsoft.SharePoint.Administration.SPLogType logType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x2fe011  stloc.s  7
0x2fe013  ldsfld   string [mscorlib]System.String::Empty
0x2fe018  stloc.s  8
0x2fe01a  ldarg.0
0x2fe01b  call     instance string Microsoft.SharePoint.Administration.SPSiteMaster::get_TemplateName()
0x2fe020  callvirt instance string [mscorlib]System.String::ToUpper()
0x2fe025  stloc.s  9
0x2fe027  ldarg.1
0x2fe028  brfalse  loc_2FE1AF
0x2fe02d  ldc.i4   0x14D56E2
0x2fe032  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2fe037  ldc.i4.s 0x32
0x2fe039  ldstr    aSitemasterIsva// "[SiteMaster.IsValid]: SoftLock check wi"...
0x2fe03e  ldc.i4.1
0x2fe03f  newarr   [mscorlib]System.Object
0x2fe044  stloc.s  0x17
0x2fe046  ldloc.s  0x17
0x2fe048  ldc.i4.0
0x2fe049  ldarga.s 1
0x2fe04b  call     instance string [mscorlib]System.Boolean::ToString()
0x2fe050  stelem.ref
0x2fe051  ldloc.s  0x17
0x2fe053  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2fe058  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteMaster::ForceNoValidationGroupTemplateKillSwitchGuid
0x2fe05d  ldstr    a12082016// "12/08/2016"
0x2fe062  ldstr    aSpsitemasterFo_0// "SPSiteMaster.ForceNoValidationGroupTemp"...
0x2fe067  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x2fe06c  stloc.s  0xA
0x2fe06e  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteMaster::ForceNoValidationPublishingTemplateKillSwitchGuid
0x2fe073  ldstr    a12082016// "12/08/2016"
0x2fe078  ldstr    aSpsitemasterFo_1// "SPSiteMaster.ForceNoValidationPublishin"...
0x2fe07d  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x2fe082  stloc.s  0xB
0x2fe084  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteMaster::ForceNoValidationRedirectSiteTemplateKillSwitchGuid
0x2fe089  ldstr    a1222018// "1/22/2018"
0x2fe08e  ldstr    aSpsitemasterFo_2// "SPSiteMaster.ForceNoValidationRedirectS"...
0x2fe093  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x2fe098  stloc.s  0xC
0x2fe09a  ldloc.s  0xA
0x2fe09c  brtrue.s loc_2FE0AC
0x2fe09e  ldloc.s  9
0x2fe0a0  ldstr    aGroup_2// "GROUP"
0x2fe0a5  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2fe0aa  brtrue.s loc_2FE0E2
0x2fe0ac  ldloc.s  0xB
0x2fe0ae  brtrue.s loc_2FE0BE
0x2fe0b0  ldloc.s  9
0x2fe0b2  ldstr    aSitepagepublis// "SITEPAGEPUBLISHING"
0x2fe0b7  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2fe0bc  brtrue.s loc_2FE0E2
0x2fe0be  ldloc.s  0xB
0x2fe0c0  brtrue.s loc_2FE0D0
0x2fe0c2  ldloc.s  9
0x2fe0c4  ldstr    aSts3// "STS#3"
0x2fe0c9  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2fe0ce  brtrue.s loc_2FE0E2
0x2fe0d0  ldloc.s  0xC
0x2fe0d2  brtrue.s loc_2FE14C
0x2fe0d4  ldloc.s  9
0x2fe0d6  ldstr    aRedirectsite// "REDIRECTSITE#"
0x2fe0db  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2fe0e0  brfalse.s loc_2FE14C
0x2fe0e2  ldc.i4   0x11CA8CA
0x2fe0e7  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2fe0ec  ldc.i4.s 0x32
0x2fe0ee  ldstr    aSitemasterIsva_0// "[SiteMaster.IsValid]: Template [{0}] is"...
0x2fe0f3  ldc.i4.4
0x2fe0f4  newarr   [mscorlib]System.Object
0x2fe0f9  stloc.s  0x18
0x2fe0fb  ldloc.s  0x18
0x2fe0fd  ldc.i4.0
0x2fe0fe  ldarg.0
0x2fe0ff  call     instance string Microsoft.SharePoint.Administration.SPSiteMaster::get_TemplateName()
0x2fe104  stelem.ref
0x2fe105  ldloc.s  0x18
0x2fe107  ldc.i4.1
0x2fe108  ldarg.0
0x2fe109  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteMaster::get_SiteId()
0x2fe10e  stloc.s  0x19
0x2fe110  ldloca.s 0x19
0x2fe112  constrained. [mscorlib]System.Guid
0x2fe118  callvirt instance string [mscorlib]System.Object::ToString()
0x2fe11d  stelem.ref
0x2fe11e  ldloc.s  0x18
0x2fe120  ldc.i4.2
0x2fe121  ldarg.0
0x2fe122  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Administration.SPSiteMaster::get_ContentDatabase()
0x2fe127  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x2fe12c  stelem.ref
0x2fe12d  ldloc.s  0x18
0x2fe12f  ldc.i4.3
0x2fe130  ldarg.0
0x2fe131  call     instance unsigned int32 Microsoft.SharePoint.Administration.SPSiteMaster::get_Language()
0x2fe136  box      [mscorlib]System.UInt32
0x2fe13b  stelem.ref
0x2fe13c  ldloc.s  0x18
0x2fe13e  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2fe143  ldc.i4.1
0x2fe144  stloc.0
0x2fe145  ldc.i4.0
0x2fe146  stloc.1
0x2fe147  br       loc_2FE1ED
0x2fe14c  ldc.i4   0x11CA8CB
0x2fe151  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2fe156  ldc.i4.s 0x64
0x2fe158  ldstr    aSitemasterIsva_1// "[SiteMaster.IsValid]: Template [{0}] is"...
0x2fe15d  ldc.i4.4
0x2fe15e  newarr   [mscorlib]System.Object
0x2fe163  stloc.s  0x1A
0x2fe165  ldloc.s  0x1A
0x2fe167  ldc.i4.0
0x2fe168  ldarg.0
0x2fe169  call     instance string Microsoft.SharePoint.Administration.SPSiteMaster::get_TemplateName()
0x2fe16e  stelem.ref
0x2fe16f  ldloc.s  0x1A
0x2fe171  ldc.i4.1
0x2fe172  ldarg.0
0x2fe173  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteMaster::get_SiteId()
0x2fe178  stloc.s  0x1B
0x2fe17a  ldloca.s 0x1B
0x2fe17c  constrained. [mscorlib]System.Guid
0x2fe182  callvirt instance string [mscorlib]System.Object::ToString()
0x2fe187  stelem.ref
0x2fe188  ldloc.s  0x1A
0x2fe18a  ldc.i4.2
0x2fe18b  ldarg.0
0x2fe18c  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Administration.SPSiteMaster::get_ContentDatabase()
0x2fe191  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x2fe196  stelem.ref
0x2fe197  ldloc.s  0x1A
0x2fe199  ldc.i4.3
0x2fe19a  ldarg.0
0x2fe19b  call     instance unsigned int32 Microsoft.SharePoint.Administration.SPSiteMaster::get_Language()
0x2fe1a0  box      [mscorlib]System.UInt32
0x2fe1a5  stelem.ref
0x2fe1a6  ldloc.s  0x1A
0x2fe1a8  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2fe1ad  br.s     loc_2FE1ED
0x2fe1af  ldc.i4   0x14D56E3
0x2fe1b4  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2fe1b9  ldc.i4.s 0x32
0x2fe1bb  ldstr    aSitemasterIsva_2// "[SiteMaster.IsValid]: SoftLock check NO"...
0x2fe1c0  ldc.i4.3
0x2fe1c1  newarr   [mscorlib]System.Object
0x2fe1c6  stloc.s  0x1C
0x2fe1c8  ldloc.s  0x1C
0x2fe1ca  ldc.i4.0
0x2fe1cb  ldarg.0
0x2fe1cc  call     instance string Microsoft.SharePoint.Administration.SPSiteMaster::get_TemplateName()
0x2fe1d1  stelem.ref
0x2fe1d2  ldloc.s  0x1C
0x2fe1d4  ldc.i4.1
0x2fe1d5  ldarg.1
0x2fe1d6  box      [mscorlib]System.Boolean
0x2fe1db  stelem.ref
0x2fe1dc  ldloc.s  0x1C
0x2fe1de  ldc.i4.2
0x2fe1df  ldloc.1
0x2fe1e0  box      [mscorlib]System.Boolean
0x2fe1e5  stelem.ref
0x2fe1e6  ldloc.s  0x1C
0x2fe1e8  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2fe1ed  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteMaster::SkipSiteMasterUpgradeCheckKillSwitch
0x2fe1f2  ldstr    a4242017// "4/24/2017"
0x2fe1f7  ldstr    aSpsitemasterSk// "SPSiteMaster.SkipSiteMasterUpgradeCheck"...
0x2fe1fc  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x2fe201  ldc.i4.0
0x2fe202  ceq
0x2fe204  stloc.s  0xD
0x2fe206  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteMaster::SkipSiteMasterUpgradeCheckOnRedirectSiteKillSwitch
0x2fe20b  ldstr    a1222018// "1/22/2018"
0x2fe210  ldstr    aSpsitemasterSk_0// "SPSiteMaster.SkipSiteMasterUpgradeCheck"...
0x2fe215  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x2fe21a  ldc.i4.0
0x2fe21b  ceq
0x2fe21d  stloc.s  0xE
0x2fe21f  ldloc.s  0xD
0x2fe221  brfalse  loc_2FE2B8
0x2fe226  ldloc.s  9
0x2fe228  ldstr    aSpspers// "SPSPERS"
0x2fe22d  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2fe232  brtrue.s loc_2FE270
0x2fe234  ldloc.s  9
0x2fe236  ldstr    aGroup_2// "GROUP"
0x2fe23b  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2fe240  brtrue.s loc_2FE270
0x2fe242  ldloc.s  9
0x2fe244  ldstr    aSitepagepublis// "SITEPAGEPUBLISHING"
0x2fe249  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2fe24e  brtrue.s loc_2FE270
0x2fe250  ldloc.s  9
0x2fe252  ldstr    aSts3// "STS#3"
0x2fe257  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2fe25c  brtrue.s loc_2FE270
0x2fe25e  ldloc.s  0xE
0x2fe260  brfalse.s loc_2FE2B5
0x2fe262  ldloc.s  9
0x2fe264  ldstr    aRedirectsite// "REDIRECTSITE#"
0x2fe269  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2fe26e  brfalse.s loc_2FE2B5
0x2fe270  ldc.i4   0x1597615
0x2fe275  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2fe27a  ldc.i4.s 0x32
0x2fe27c  ldstr    aSkippingSiteMa// "Skipping Site master needs upgrade chec"...
0x2fe281  ldc.i4.2
0x2fe282  newarr   [mscorlib]System.Object
0x2fe287  stloc.s  0x1D
0x2fe289  ldloc.s  0x1D
0x2fe28b  ldc.i4.0
0x2fe28c  ldarg.0
0x2fe28d  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteMaster::get_SiteId()
0x2fe292  stloc.s  0x1E
0x2fe294  ldloca.s 0x1E
0x2fe296  constrained. [mscorlib]System.Guid
0x2fe29c  callvirt instance string [mscorlib]System.Object::ToString()
0x2fe2a1  stelem.ref
0x2fe2a2  ldloc.s  0x1D
0x2fe2a4  ldc.i4.1
0x2fe2a5  ldarg.0
0x2fe2a6  call     instance string Microsoft.SharePoint.Administration.SPSiteMaster::get_TemplateName()
0x2fe2ab  stelem.ref
0x2fe2ac  ldloc.s  0x1D
0x2fe2ae  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2fe2b3  br.s     loc_2FE2B8
0x2fe2b5  ldc.i4.0
0x2fe2b6  stloc.s  0xD
0x2fe2b8  ldarg.0
0x2fe2b9  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteMaster::get_SiteId()
0x2fe2be  newobj   instance void Microsoft.SharePoint.SPSite::.ctor(valuetype [mscorlib]System.Guid id)
0x2fe2c3  stloc.s  0xF
0x2fe2c5  ldloc.s  0xF
0x2fe2c7  callvirt instance string Microsoft.SharePoint.SPSite::get_Url()
0x2fe2cc  brtrue.s loc_2FE2D5
0x2fe2ce  ldsfld   string [mscorlib]System.String::Empty
0x2fe2d3  br.s     loc_2FE2DC
0x2fe2d5  ldloc.s  0xF
0x2fe2d7  callvirt instance string Microsoft.SharePoint.SPSite::get_Url()
0x2fe2dc  stloc.s  8
0x2fe2de  ldc.i4   0x39B358
0x2fe2e3  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SiteMaster()
0x2fe2e8  ldc.i4.s 0x64
0x2fe2ea  ldstr    aSiteMasterVali// "Site master validation. Id: [{0}], Url:"...
0x2fe2ef  ldc.i4.6
0x2fe2f0  newarr   [mscorlib]System.Object
0x2fe2f5  stloc.s  0x1F
0x2fe2f7  ldloc.s  0x1F
0x2fe2f9  ldc.i4.0
0x2fe2fa  ldarg.0
0x2fe2fb  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteMaster::get_SiteId()
0x2fe300  stloc.s  0x20
0x2fe302  ldloca.s 0x20
0x2fe304  constrained. [mscorlib]System.Guid
0x2fe30a  callvirt instance string [mscorlib]System.Object::ToString()
0x2fe30f  stelem.ref
0x2fe310  ldloc.s  0x1F
0x2fe312  ldc.i4.1
0x2fe313  ldloc.s  0xF
0x2fe315  callvirt instance string Microsoft.SharePoint.SPSite::get_Url()
0x2fe31a  stelem.ref
0x2fe31b  ldloc.s  0x1F
0x2fe31d  ldc.i4.2
0x2fe31e  ldarg.0
0x2fe31f  call     instance string Microsoft.SharePoint.Administration.SPSiteMaster::get_TemplateName()
0x2fe324  stelem.ref
0x2fe325  ldloc.s  0x1F
0x2fe327  ldc.i4.3
0x2fe328  ldarg.0
0x2fe329  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Administration.SPSiteMaster::get_ContentDatabase()
0x2fe32e  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x2fe333  stelem.ref
0x2fe334  ldloc.s  0x1F
  ... truncated ...
```
