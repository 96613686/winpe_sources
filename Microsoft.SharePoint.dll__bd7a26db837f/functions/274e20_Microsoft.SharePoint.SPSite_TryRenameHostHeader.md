# Microsoft.SharePoint.SPSite::TryRenameHostHeader

- ea: `0x274e20`
- end: `0x2752e1`
- name: `Microsoft.SharePoint.SPSite::TryRenameHostHeader`
- size: `1217`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x274660`

## callees

- `0x1c8480`
- `0x1c87b0`
- `0x1f8e40`
- `0x249550`
- `0x249dc0`
- `0x24c440`
- `0x261a40`
- `0x26bde0`
- `0x26bf00`
- `0x26f650`
- `0x26f6a0`
- `0x274e20`
- `0x2758e0`
- `0x280870`
- `0x29d0f0`
- `0x31d7a0`
- `0x6c9890`
- `0x93dae0`
- `0x957470`

## string_xrefs

- `0x274e9d`: `SPSite.RenameHostHeader: {0} DBs have sites with host header {1}`
- `0x274f45`: `SPSite.RenameHostHeader: Cannot rename site host header because the following DB already contains sites with the target host header: {0}`
- `0x274f77`: `SPSite.RenameHostHeader: The following DB already contains sites with the target host header: {0}. Continuing trying to rename site host header as skipFailures flag is set.`
- `0x274fa5`: `SkipHostHeaderRenameForSingleSite`
- `0x274ffe`: `SPSite.RenameHostHeader: DB {0} have {1} sites with host header {2}`
- `0x27504a`: `SPSite.RenameHostHeader: Using normal site rename process since host header site has very few sites under it: {0}`
- `0x2750c7`: `SPSite.RenameHostHeader: finished renaming host header sites in {0} out of {1} DBs`
- `0x275127`: `SPSite.RenameHostHeader: Exception caught while renaming site host header, SKIPPING rolling back changes: {0}`
- `0x275178`: `SPSite.RenameHostHeader: Skipping roll back of site renamed in DB [Id: {0}, Name: {1}]`
- `0x2751b2`: `SPSite.RenameHostHeader: Skipping roll back of site renamed in DB [Id: {0}]. Execption retreiving db object: {2}`
- `0x275204`: `SPSite.RenameHostHeader: Exception caught while renaming site host header, rolling back change: {0}`
- `0x275267`: `SPSite.RenameHostHeader: Exception caught rolling back changes in DB {0} : {1}`
- `0x2752b7`: `SPSite.RenameHostHeader: suceessfully updated host header URL: Old URL: {0} Current URL: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x274e20  ldarg.0
0x274e21  call     instance string Microsoft.SharePoint.SPSite::get_Url()
0x274e26  newobj   instance void [System]System.Uri::.ctor(string)
0x274e2b  stloc.0
0x274e2c  ldarg.0
0x274e2d  ldarg.1
0x274e2e  ldloc.0
0x274e2f  ldc.i4.1
0x274e30  ldarg.0
0x274e31  call     instance bool Microsoft.SharePoint.SPSite::get_AllowRenameIgnoreLockState()
0x274e36  call     instance void Microsoft.SharePoint.SPSite::ValidateRename(class [System]System.Uri newUri, class [System]System.Uri currentUri, bool isNewNameHostHeader, bool allowRenameIgnoreLockState)
0x274e3b  call     class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_Local()
0x274e40  ldarg.0
0x274e41  call     instance class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.SPSite::get_WebApplication()
0x274e46  ldloc.0
0x274e47  callvirt instance string [System]System.Uri::get_Host()
0x274e4c  ldarg.0
0x274e4d  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSite::get_SafeSubScriptionId()
0x274e52  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x274e57  ldloca.s 0x11
0x274e59  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x274e5f  ldloc.s  0x11
0x274e61  ldloca.s 0x12
0x274e63  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.SPHostHeaderSiteUriScheme>
0x274e69  ldloc.s  0x12
0x274e6b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x274e70  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x274e75  ldc.i4.1
0x274e76  ldnull
0x274e77  ldloca.s 0x13
0x274e79  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x274e7f  ldloc.s  0x13
0x274e81  ldloca.s 0x14
0x274e83  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.SPHostHeaderSiteUriScheme>
0x274e89  ldloc.s  0x14
0x274e8b  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Administration.SPConfigurationDatabase::GetSiteInfoDatabases(class Microsoft.SharePoint.Administration.SPWebApplication wa, string strPathLike, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> siteSubscriptionId, valuetype [mscorlib]System.Nullable`1<bool> bHostHeader, valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.SPHostHeaderSiteUriScheme> uriScheme, valuetype [mscorlib]System.Guid dbIdStart, valuetype [mscorlib]System.Guid siteIdStart, bool bIncludeDeletedSites, string strExcludePathLike, valuetype [mscorlib]System.Nullable`1<bool> bHostHeaderExcludePath, valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.SPHostHeaderSiteUriScheme> uriSchemeExcludePath)
0x274e90  stloc.1
0x274e91  ldc.i4   0x1818355
0x274e96  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x274e9b  ldc.i4.s 0x32
0x274e9d  ldstr    aSpsiteRenameho// "SPSite.RenameHostHeader: {0} DBs have s"...
0x274ea2  ldc.i4.2
0x274ea3  newarr   [mscorlib]System.Object
0x274ea8  stloc.s  0x15
0x274eaa  ldloc.s  0x15
0x274eac  ldc.i4.0
0x274ead  ldloc.1
0x274eae  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x274eb3  box      [mscorlib]System.Int32
0x274eb8  stelem.ref
0x274eb9  ldloc.s  0x15
0x274ebb  ldc.i4.1
0x274ebc  ldloc.0
0x274ebd  callvirt instance string [System]System.Uri::get_Host()
0x274ec2  stelem.ref
0x274ec3  ldloc.s  0x15
0x274ec5  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x274eca  call     class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_Local()
0x274ecf  ldarg.0
0x274ed0  call     instance class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.SPSite::get_WebApplication()
0x274ed5  ldarg.1
0x274ed6  callvirt instance string [System]System.Uri::get_Host()
0x274edb  ldarg.0
0x274edc  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSite::get_SafeSubScriptionId()
0x274ee1  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x274ee6  ldloca.s 0x16
0x274ee8  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x274eee  ldloc.s  0x16
0x274ef0  ldloca.s 0x17
0x274ef2  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.SPHostHeaderSiteUriScheme>
0x274ef8  ldloc.s  0x17
0x274efa  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x274eff  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x274f04  ldc.i4.1
0x274f05  ldnull
0x274f06  ldloca.s 0x18
0x274f08  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x274f0e  ldloc.s  0x18
0x274f10  ldloca.s 0x19
0x274f12  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.SPHostHeaderSiteUriScheme>
0x274f18  ldloc.s  0x19
0x274f1a  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Administration.SPConfigurationDatabase::GetSiteInfoDatabases(class Microsoft.SharePoint.Administration.SPWebApplication wa, string strPathLike, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> siteSubscriptionId, valuetype [mscorlib]System.Nullable`1<bool> bHostHeader, valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.SPHostHeaderSiteUriScheme> uriScheme, valuetype [mscorlib]System.Guid dbIdStart, valuetype [mscorlib]System.Guid siteIdStart, bool bIncludeDeletedSites, string strExcludePathLike, valuetype [mscorlib]System.Nullable`1<bool> bHostHeaderExcludePath, valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.SharePoint.SPHostHeaderSiteUriScheme> uriSchemeExcludePath)
0x274f1f  stloc.2
0x274f20  ldloc.1
0x274f21  ldloc.2
0x274f22  call     T0x2B00015A
0x274f27  call     T0x2B00007B
0x274f2c  stloc.3
0x274f2d  ldloc.3
0x274f2e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x274f33  ldc.i4.0
0x274f34  ble.s    loc_274F9B
0x274f36  ldarg.3
0x274f37  brtrue.s loc_274F6B
0x274f39  ldc.i4   0x13CB295
0x274f3e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x274f43  ldc.i4.s 0xA
0x274f45  ldstr    aSpsiteRenameho_0// "SPSite.RenameHostHeader: Cannot rename "...
0x274f4a  ldc.i4.1
0x274f4b  newarr   [mscorlib]System.Object
0x274f50  stloc.s  0x1A
0x274f52  ldloc.s  0x1A
0x274f54  ldc.i4.0
0x274f55  ldloc.3
0x274f56  ldc.i4.0
0x274f57  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Item(!!T0)
0x274f5c  box      [mscorlib]System.Guid
0x274f61  stelem.ref
0x274f62  ldloc.s  0x1A
0x274f64  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x274f69  ldc.i4.0
0x274f6a  ret
0x274f6b  ldc.i4   0x229524E
0x274f70  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x274f75  ldc.i4.s 0xA
0x274f77  ldstr    aSpsiteRenameho_1// "SPSite.RenameHostHeader: The following "...
0x274f7c  ldc.i4.1
0x274f7d  newarr   [mscorlib]System.Object
0x274f82  stloc.s  0x1B
0x274f84  ldloc.s  0x1B
0x274f86  ldc.i4.0
0x274f87  ldloc.3
0x274f88  ldc.i4.0
0x274f89  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Item(!!T0)
0x274f8e  box      [mscorlib]System.Guid
0x274f93  stelem.ref
0x274f94  ldloc.s  0x1B
0x274f96  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x274f9b  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSite::SkipHostHeaderRenameForSingleSiteKillSwitch
0x274fa0  ldstr    a05092017// "05/09/2017"
0x274fa5  ldstr    aSkiphostheader// "SkipHostHeaderRenameForSingleSite"
0x274faa  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x274faf  brtrue   loc_27506A
0x274fb4  ldloc.1
0x274fb5  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x274fba  ldc.i4.1
0x274fbb  bne.un   loc_27506A
0x274fc0  call     class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x274fc5  callvirt instance class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.SPPersistedObject::get_ConfigurationDatabase()
0x274fca  callvirt instance class Microsoft.SharePoint.Administration.SPSiteLookupProvider Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_SiteLookupProvider()
0x274fcf  isinst   Microsoft.SharePoint.Administration.ISPSiteLookupProviderSiteSubscription
0x274fd4  stloc.s  4
0x274fd6  ldloc.s  4
0x274fd8  brfalse  loc_27506A
0x274fdd  ldloc.s  4
0x274fdf  ldarg.0
0x274fe0  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSite::get_SafeSubScriptionId()
0x274fe5  ldloc.0
0x274fe6  callvirt instance string [System]System.Uri::get_Host()
0x274feb  callvirt instance int64 Microsoft.SharePoint.Administration.ISPSiteLookupProviderSiteSubscription::GetSiteCountBySiteSubscriptionAndPathPrefix(valuetype [mscorlib]System.Guid subscriptionId, string pathPrefix)
0x274ff0  stloc.s  5
0x274ff2  ldc.i4   0x1818356
0x274ff7  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x274ffc  ldc.i4.s 0x32
0x274ffe  ldstr    aSpsiteRenameho_2// "SPSite.RenameHostHeader: DB {0} have {1"...
0x275003  ldc.i4.3
0x275004  newarr   [mscorlib]System.Object
0x275009  stloc.s  0x1C
0x27500b  ldloc.s  0x1C
0x27500d  ldc.i4.0
0x27500e  ldloc.1
0x27500f  ldc.i4.0
0x275010  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Item(!!T0)
0x275015  box      [mscorlib]System.Guid
0x27501a  stelem.ref
0x27501b  ldloc.s  0x1C
0x27501d  ldc.i4.1
0x27501e  ldloc.s  5
0x275020  box      [mscorlib]System.Int64
0x275025  stelem.ref
0x275026  ldloc.s  0x1C
0x275028  ldc.i4.2
0x275029  ldloc.0
0x27502a  callvirt instance string [System]System.Uri::get_Host()
0x27502f  stelem.ref
0x275030  ldloc.s  0x1C
0x275032  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x275037  ldloc.s  5
0x275039  ldc.i4.s 0x32
0x27503b  conv.i8
0x27503c  bgt.s    loc_27506A
0x27503e  ldc.i4   0x16430C2
0x275043  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x275048  ldc.i4.s 0xA
0x27504a  ldstr    aSpsiteRenameho_3// "SPSite.RenameHostHeader: Using normal s"...
0x27504f  ldc.i4.1
0x275050  newarr   [mscorlib]System.Object
0x275055  stloc.s  0x1D
0x275057  ldloc.s  0x1D
0x275059  ldc.i4.0
0x27505a  ldloc.0
0x27505b  callvirt instance string [System]System.Uri::get_Host()
0x275060  stelem.ref
0x275061  ldloc.s  0x1D
0x275063  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x275068  ldc.i4.0
0x275069  ret
0x27506a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x27506f  stloc.s  6
0x275071  ldc.i4.0
0x275072  stloc.s  7
0x275074  ldloc.1
0x275075  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x27507a  stloc.s  0x1E
0x27507c  br.s     loc_2750F5
0x27507e  ldloca.s 0x1E
0x275080  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x275085  stloc.s  8
0x275087  ldloc.s  6
0x275089  ldloc.s  8
0x27508b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x275090  ldarg.0
0x275091  call     instance class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.SPSite::get_WebApplication()
0x275096  callvirt instance class Microsoft.SharePoint.Administration.SPContentDatabaseCollection Microsoft.SharePoint.Administration.SPWebApplication::get_ContentDatabases()
0x27509b  ldloc.s  8
0x27509d  callvirt instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Administration.SPContentDatabaseCollection::get_Item(valuetype [mscorlib]System.Guid id)
0x2750a2  stloc.s  9
0x2750a4  ldloc.s  9
0x2750a6  ldloc.0
0x2750a7  ldarg.1
0x2750a8  ldarg.0
0x2750a9  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSite::get_SafeSubScriptionId()
0x2750ae  ldarg.2
0x2750af  ldarg.3
0x2750b0  callvirt instance void Microsoft.SharePoint.Administration.SPContentDatabase::RenameHostHeaderSites(class [System]System.Uri currentHostHeader, class [System]System.Uri newHostHeader, valuetype [mscorlib]System.Guid subscriptionID, bool skipSiteMapUpdate, bool skipFailures)
0x2750b5  ldloc.s  7
0x2750b7  ldc.i4.1
0x2750b8  add
0x2750b9  stloc.s  7
0x2750bb  ldc.i4   0x1818357
0x2750c0  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x2750c5  ldc.i4.s 0x32
0x2750c7  ldstr    aSpsiteRenameho_4// "SPSite.RenameHostHeader: finished renam"...
0x2750cc  ldc.i4.2
0x2750cd  newarr   [mscorlib]System.Object
0x2750d2  stloc.s  0x1F
0x2750d4  ldloc.s  0x1F
0x2750d6  ldc.i4.0
0x2750d7  ldloc.s  7
0x2750d9  box      [mscorlib]System.Int32
0x2750de  stelem.ref
0x2750df  ldloc.s  0x1F
0x2750e1  ldc.i4.1
0x2750e2  ldloc.1
0x2750e3  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x2750e8  box      [mscorlib]System.Int32
0x2750ed  stelem.ref
0x2750ee  ldloc.s  0x1F
0x2750f0  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2750f5  ldloca.s 0x1E
0x2750f7  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x2750fc  brtrue.s loc_27507E
0x2750fe  leave.s  loc_27510E
0x275100  ldloca.s 0x1E
0x275102  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x275108  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27510d  endfinally
0x27510e  leave    loc_2752AB
0x275113  stloc.s  0xA
0x275115  ldarg.3
0x275116  brfalse  loc_2751F8
0x27511b  ldc.i4   0x2295251
0x275120  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x275125  ldc.i4.s 0xA
0x275127  ldstr    aSpsiteRenameho_5// "SPSite.RenameHostHeader: Exception caug"...
0x27512c  ldc.i4.1
0x27512d  newarr   [mscorlib]System.Object
0x275132  stloc.s  0x20
0x275134  ldloc.s  0x20
0x275136  ldc.i4.0
0x275137  ldloc.s  0xA
0x275139  stelem.ref
0x27513a  ldloc.s  0x20
0x27513c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x275141  ldloc.s  6
0x275143  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x275148  stloc.s  0x21
0x27514a  br       loc_2751D9
0x27514f  ldloca.s 0x21
0x275151  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x275156  stloc.s  0xB
0x275158  ldarg.0
0x275159  call     instance class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.SPSite::get_WebApplication()
0x27515e  callvirt instance class Microsoft.SharePoint.Administration.SPContentDatabaseCollection Microsoft.SharePoint.Administration.SPWebApplication::get_ContentDatabases()
0x275163  ldloc.s  0xB
0x275165  callvirt instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Administration.SPContentDatabaseCollection::get_Item(valuetype [mscorlib]System.Guid id)
0x27516a  stloc.s  0xC
0x27516c  ldc.i4   0x2295252
0x275171  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x275176  ldc.i4.s 0xA
0x275178  ldstr    aSpsiteRenameho_6// "SPSite.RenameHostHeader: Skipping roll "...
0x27517d  ldc.i4.2
0x27517e  newarr   [mscorlib]System.Object
0x275183  stloc.s  0x22
0x275185  ldloc.s  0x22
0x275187  ldc.i4.0
0x275188  ldloc.s  0xB
0x27518a  box      [mscorlib]System.Guid
0x27518f  stelem.ref
0x275190  ldloc.s  0x22
  ... truncated ...
```
