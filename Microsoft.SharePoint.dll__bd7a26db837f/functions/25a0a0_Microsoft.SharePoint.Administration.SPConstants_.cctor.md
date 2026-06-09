# Microsoft.SharePoint.Administration.SPConstants::.cctor

- ea: `0x25a0a0`
- end: `0x25a5d6`
- name: `Microsoft.SharePoint.Administration.SPConstants::.cctor`
- size: `1334`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x2525d0`

## string_xrefs

- `0x25a15f`: `ReadSLA`
- `0x25a169`: `WriteSLA`
- `0x25a213`: `SPThreadContext.CompatibilityLevel`
- `0x25a21d`: `SPThreadContext.UserOverrideLanguages`
- `0x25a227`: `SPThreadContext.UserAcceptLanguages`
- `0x25a231`: `SPThreadContext.UserPreferredUILanguages`
- `0x25a23b`: `SharePoint_Shell_Access`
- `0x25a2dc`: `This service configuration is in use.  Please remove all participants before attempting to delete this.`
- `0x25a2e6`: `Blob was updated or removed during read.`
- `0x25a3b8`: `SPWriterV4`
- `0x25a3d6`: `AppFabricCachingService`
- `0x25a416`: `Microsoft Data Access Internet Publishing Provider Protocol Discovery`
- `0x25a43a`: `sharepointonline.com.akadns.net`
- `0x25a4d2`: `https://go.microsoft.com/fwlink/?LinkId=2198656`
- `0x25a5cb`: `https://go.microsoft.com/fwlink/?linkid=2286927`

## pseudocode

```c

```

## disassembly

```asm
0x25a0a0  ldstr    aSharepointerro// "SharePointError"
0x25a0a5  stsfld   string Microsoft.SharePoint.Administration.SPConstants::SharePointErrorHeader
0x25a0aa  ldsfld   string Microsoft.SharePoint.Utilities.SPUtilityInternal::VKEY_FPSEV3ConfigDb
0x25a0af  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ConfigDbKeyName
0x25a0b4  ldsfld   string Microsoft.SharePoint.Utilities.SPUtilityInternal::VKEY_FPSEVer
0x25a0b9  stsfld   string Microsoft.SharePoint.Administration.SPConstants::SharePointConfigurationKeyName
0x25a0be  ldsfld   string Microsoft.SharePoint.Utilities.SPUtilityInternal::VKEY_FPSEFarmAdmin
0x25a0c3  stsfld   string Microsoft.SharePoint.Administration.SPConstants::FarmAdminKeyName
0x25a0c8  ldsfld   string Microsoft.SharePoint.Utilities.SPUtilityInternal::VKEY_FPSEVerSecureGlobal
0x25a0cd  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ApplicationCredentialKeyName
0x25a0d2  ldstr    aSharepoint// "SharePoint"
0x25a0d7  stsfld   string Microsoft.SharePoint.Administration.SPConstants::AllUnassignedWebSiteHostName
0x25a0dc  ldstr    aWssAdministrat// "WSS_Administration"
0x25a0e1  stsfld   string Microsoft.SharePoint.Administration.SPConstants::AdminObjectName
0x25a0e6  ldstr    aWssAdminconten// "WSS_AdminContent"
0x25a0eb  stsfld   string Microsoft.SharePoint.Administration.SPConstants::DefaultAdminContentDbName
0x25a0f0  ldstr    aFarmAdministra// "Farm Administrators"
0x25a0f5  stsfld   string Microsoft.SharePoint.Administration.SPConstants::FarmAdministratorsGroupId
0x25a0fa  ldstr    aDelegatedAdmin// "Delegated Administrators"
0x25a0ff  stsfld   string Microsoft.SharePoint.Administration.SPConstants::DelegatedAdministratorsGroupId
0x25a104  ldstr    aSharepointCent// "SharePoint Central Administration v4"
0x25a109  stsfld   string Microsoft.SharePoint.Administration.SPConstants::AdminSiteName
0x25a10e  ldstr    aSharepointCent_0// "SharePoint Central Administration v3"
0x25a113  stsfld   string Microsoft.SharePoint.Administration.SPConstants::AdminSiteNamePreviousVersion
0x25a118  ldstr    aSharepoint01// "SharePoint - {0}{1}"
0x25a11d  stsfld   string Microsoft.SharePoint.Administration.SPConstants::SharePointDefaultWebAppName
0x25a122  ldc.i4.s 0xA
0x25a124  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::MaxFileAccessAttempts
0x25a129  ldc.i4.s 0x1E
0x25a12b  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::DefaultMaxAuditLogTrimmingRetention
0x25a130  ldc.i4.s 0x5A
0x25a132  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::MaxAuditLogRetentionInDays
0x25a137  ldc.i4   0x3E8
0x25a13c  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::MaxFileAccessDelay
0x25a141  ldstr    aDsn2// "dsn2"
0x25a146  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ConfigDbDsn2ValueName
0x25a14b  ldstr    aDsn// "dsn"
0x25a150  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ConfigDbDsnValueName
0x25a155  ldstr    aId_2// "Id"
0x25a15a  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ConfigDbIdValueName
0x25a15f  ldstr    aReadsla// "ReadSLA"
0x25a164  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ConfigCacheReadSLAValueName
0x25a169  ldstr    aWritesla// "WriteSLA"
0x25a16e  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ConfigCacheWriteSLAValueName
0x25a173  ldstr    aServerid_0// "ServerId"
0x25a178  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ServerIdValueName
0x25a17d  ldstr    aAdminserverloc// "AdminServerLocation"
0x25a182  stsfld   string Microsoft.SharePoint.Administration.SPConstants::AdminServerLocationName
0x25a187  ldstr    aVersion_1// "Version"
0x25a18c  stsfld   string Microsoft.SharePoint.Administration.SPConstants::VersionName
0x25a191  ldstr    aAppcredentialk// "AppCredentialKey"
0x25a196  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ApplicationCredentialValueName
0x25a19b  ldstr    aCentraladminis// "CentralAdministrationURL"
0x25a1a0  stsfld   string Microsoft.SharePoint.Administration.SPConstants::CentralAdministrationURLValueName
0x25a1a5  ldstr    aAlwaysroutetos// "AlwaysRouteToSelf"
0x25a1aa  stsfld   string Microsoft.SharePoint.Administration.SPConstants::AlwaysRouteToSelf
0x25a1af  ldstr    aRoutetoselfifp// "RouteToSelfIfPossible"
0x25a1b4  stsfld   string Microsoft.SharePoint.Administration.SPConstants::RouteToSelfIfPossible
0x25a1b9  ldstr    aRoutetosamerol// "RouteToSameRoleIfPossible"
0x25a1be  stsfld   string Microsoft.SharePoint.Administration.SPConstants::RouteToSameRoleIfPossible
0x25a1c3  call     string Microsoft.SharePoint.Utilities.SqlSession::get_DefaultCollation()
0x25a1c8  stsfld   string Microsoft.SharePoint.Administration.SPConstants::DatabaseCollation
0x25a1cd  ldstr    aSqlLatin1Gener// "SQL_Latin1_General"
0x25a1d2  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ServerCollationPart1
0x25a1d7  ldstr    aCiAs// "CI_AS"
0x25a1dc  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ServerCollationPart2
0x25a1e1  ldstr    aMicrosoftShare_17// "Microsoft.SharePoint.AdminPort"
0x25a1e6  stsfld   string Microsoft.SharePoint.Administration.SPConstants::RequestFromAdminPort
0x25a1eb  ldstr    aWssAdminWpg// "WSS_ADMIN_WPG"
0x25a1f0  stsfld   string Microsoft.SharePoint.Administration.SPConstants::AdminWorkerProcessGroupName
0x25a1f5  ldstr    aWssRestrictedW// "WSS_RESTRICTED_WPG_V4"
0x25a1fa  stsfld   string Microsoft.SharePoint.Administration.SPConstants::FarmAdminGroupName
0x25a1ff  ldstr    aWssWpg// "WSS_WPG"
0x25a204  stsfld   string Microsoft.SharePoint.Administration.SPConstants::WorkerProcessGroupName
0x25a209  ldstr    aWssContentAppl// "WSS_Content_Application_Pools"
0x25a20e  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ContentApplicationSqlRole
0x25a213  ldstr    aSpthreadcontex_1// "SPThreadContext.CompatibilityLevel"
0x25a218  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ThreadContextCompatibilityLevel
0x25a21d  ldstr    aSpthreadcontex_2// "SPThreadContext.UserOverrideLanguages"
0x25a222  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ThreadContextUserOverrideLanguages
0x25a227  ldstr    aSpthreadcontex_3// "SPThreadContext.UserAcceptLanguages"
0x25a22c  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ThreadContextUserAcceptLanguages
0x25a231  ldstr    aSpthreadcontex_4// "SPThreadContext.UserPreferredUILanguage"...
0x25a236  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ThreadContextUserPreferredUILanguages
0x25a23b  ldstr    aSharepointShel// "SharePoint_Shell_Access"
0x25a240  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ShellAccessRole
0x25a245  ldc.i4   0x80
0x25a24a  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::SiteNameMaxLength
0x25a24f  ldsfld   int32 Microsoft.SharePoint.Administration.SPConstants::SiteNameMaxLength
0x25a254  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::MaximumSiteLength
0x25a259  ldc.i4   0xFF
0x25a25e  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::SitePathMaxLength
0x25a263  ldc.i4   0x80
0x25a268  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::PersistedObjectNameMaxLength
0x25a26d  ldc.i4   0x80
0x25a272  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::DisplayNameMaxLength
0x25a277  ldc.i4   0x80
0x25a27c  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::ServerAddressMaxLength
0x25a281  ldc.i4   0x80
0x25a286  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::ServiceInstanceMaxLength
0x25a28b  ldc.i4   0x180
0x25a290  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::ConnectionStringMaxLength
0x25a295  ldc.i4   0x80
0x25a29a  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::MailAddressMaxLength
0x25a29f  ldc.i4.s 0x40
0x25a2a1  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::VersionMaxLength
0x25a2a6  ldc.i4.s 0x20
0x25a2a8  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::MaxDependenciesPerObject
0x25a2ad  ldc.i4.m1
0x25a2ae  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::InvalidRowVersion
0x25a2b3  ldc.i4.6
0x25a2b4  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::ObjectTableColumns
0x25a2b9  ldc.i4.s 9
0x25a2bb  ldc.i4.0
0x25a2bc  ldc.i4.0
0x25a2bd  ldc.i4.0
0x25a2be  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x25a2c3  stsfld   class [mscorlib]System.Version Microsoft.SharePoint.Administration.SPConstants::YukonProductVersion
0x25a2c8  ldstr    aValueCannotBeG// "Value cannot be Guid.Empty."
0x25a2cd  stsfld   string Microsoft.SharePoint.Administration.SPConstants::EmptyGuidArgumentExceptionMessage
0x25a2d2  ldstr    aValueDoesNotHa// "Value does not have a valid object iden"...
0x25a2d7  stsfld   string Microsoft.SharePoint.Administration.SPConstants::InvalidObjectIdArgumentExceptionMessage
0x25a2dc  ldstr    aThisServiceCon// "This service configuration is in use.  "...
0x25a2e1  stsfld   string Microsoft.SharePoint.Administration.SPConstants::ServiceConfigurationInUseExceptionMessage
0x25a2e6  ldstr    aBlobWasUpdated// "Blob was updated or removed during read"...
0x25a2eb  stsfld   string Microsoft.SharePoint.Administration.SPConstants::BlobConcurrencyExceptionMessage
0x25a2f0  ldstr    asc_C00000// ""
0x25a2f5  stsfld   string Microsoft.SharePoint.Administration.SPConstants::DefaultLocalObjectName
0x25a2fa  ldstr    aObject// "object"
0x25a2ff  stsfld   string Microsoft.SharePoint.Administration.SPConstants::SerializedObjectElement
0x25a304  ldstr    aFld_0// "fld"
0x25a309  stsfld   string Microsoft.SharePoint.Administration.SPConstants::SerializedFieldElement
0x25a30e  ldstr    aSfld// "sFld"
0x25a313  stsfld   string Microsoft.SharePoint.Administration.SPConstants::SerializedSystemFieldElement
0x25a318  ldstr    aType_0// "type"
0x25a31d  stsfld   string Microsoft.SharePoint.Administration.SPConstants::SerializedFieldType
0x25a322  ldstr    aName// "name"
0x25a327  stsfld   string Microsoft.SharePoint.Administration.SPConstants::SerializedFieldName
0x25a32c  ldstr    aValue_2// "value"
0x25a331  stsfld   string Microsoft.SharePoint.Administration.SPConstants::SerializedFieldValue
0x25a336  ldstr    aNull_2// "null"
0x25a33b  stsfld   string Microsoft.SharePoint.Administration.SPConstants::NullTypeValue
0x25a340  ldstr    aFaulty// "Faulty"
0x25a345  stsfld   string Microsoft.SharePoint.Administration.SPConstants::SerializedFaultyTypeElement
0x25a34a  ldstr    aIisfilter// "IIsFilter"
0x25a34f  stsfld   string Microsoft.SharePoint.Administration.SPConstants::IisFilterSchemaClassName
0x25a354  ldstr    aIiswebserver// "IIsWebServer"
0x25a359  stsfld   string Microsoft.SharePoint.Administration.SPConstants::IisWebSiteSchemaClassName
0x25a35e  ldstr    aIiswebvirtuald// "IIsWebVirtualDir"
0x25a363  stsfld   string Microsoft.SharePoint.Administration.SPConstants::IisVirtualDirectorySchemaClassName
0x25a368  ldstr    aIisapplication// "IIsApplicationPool"
0x25a36d  stsfld   string Microsoft.SharePoint.Administration.SPConstants::IisApplicationPoolSchemaClassName
0x25a372  ldstr    aIiswebfile// "IIsWebFile"
0x25a377  stsfld   string Microsoft.SharePoint.Administration.SPConstants::IisWebFileSchemaClassName
0x25a37c  ldstr    aVtiBuildversio// "vti_buildversion:SR|{0}"
0x25a381  stsfld   string Microsoft.SharePoint.Administration.SPConstants::vtiBuildVersionFormat
0x25a386  ldstr    aVtiExtenderver// "vti_extenderversion:SR|{0}"
0x25a38b  stsfld   string Microsoft.SharePoint.Administration.SPConstants::vtiMetadictFormat
0x25a390  ldstr    aVtiEncodingSrU// "vti_encoding:SR|utf8-nl"
0x25a395  stsfld   string Microsoft.SharePoint.Administration.SPConstants::vtiEncoding
0x25a39a  ldstr    aSptimerv3// "SPTimerV3"
0x25a39f  stsfld   string Microsoft.SharePoint.Administration.SPConstants::TimerServiceNamePreviousVersion
0x25a3a4  ldstr    aSptimerv4// "SPTimerV4"
0x25a3a9  stsfld   string Microsoft.SharePoint.Administration.SPConstants::TimerServiceName
0x25a3ae  ldstr    aSpadminv4// "SPAdminV4"
0x25a3b3  stsfld   string Microsoft.SharePoint.Administration.SPConstants::AdminServiceName
0x25a3b8  ldstr    aSpwriterv4// "SPWriterV4"
0x25a3bd  stsfld   string Microsoft.SharePoint.Administration.SPConstants::VssWriterServiceName
0x25a3c2  ldstr    aSptracev4// "SPTraceV4"
0x25a3c7  stsfld   string Microsoft.SharePoint.Administration.SPConstants::TraceServiceName
0x25a3cc  ldstr    aSpusercodev4// "SPUserCodeV4"
0x25a3d1  stsfld   string Microsoft.SharePoint.Administration.SPConstants::UserCodeServiceName
0x25a3d6  ldstr    aAppfabriccachi// "AppFabricCachingService"
0x25a3db  stsfld   string Microsoft.SharePoint.Administration.SPConstants::CacheServiceName
0x25a3e0  ldstr    aProvisioningSp// "PROVISIONING_SPSITE"
0x25a3e5  stsfld   string Microsoft.SharePoint.Administration.SPConstants::CachedProvisioningSPSite
0x25a3ea  ldc.i4.0
0x25a3eb  ldc.i4.s 0xC
0x25a3ed  ldc.i4.0
0x25a3ee  ldc.i4.0
0x25a3ef  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32, int32)
0x25a3f4  stsfld   valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.Administration.SPConstants::DefaultAsynchronousJobTimeout
0x25a3f9  ldstr    aSearchprovider// "SearchProviderName"
0x25a3fe  stsfld   string Microsoft.SharePoint.Administration.SPConstants::SearchProviderNamePropertyName
0x25a403  ldstr    aRequestguid// "@RequestGuid"
0x25a408  stsfld   string Microsoft.SharePoint.Administration.SPConstants::RequestGuid
0x25a40d  ldc.i4.4
0x25a40e  newarr   [mscorlib]System.String
0x25a413  stloc.2
0x25a414  ldloc.2
0x25a415  ldc.i4.0
0x25a416  ldstr    aMicrosoftDataA_0// "Microsoft Data Access Internet Publishi"...
0x25a41b  stelem.ref
0x25a41c  ldloc.2
0x25a41d  ldc.i4.1
0x25a41e  ldstr    aMsfrontpage// "MSFrontPage"
0x25a423  stelem.ref
0x25a424  ldloc.2
0x25a425  ldc.i4.2
0x25a426  ldstr    aTestForWebForm// "Test for Web Form Existence"
0x25a42b  stelem.ref
0x25a42c  ldloc.2
0x25a42d  ldc.i4.3
0x25a42e  ldstr    aMicrosoftOffic_6// "Microsoft Office"
0x25a433  stelem.ref
0x25a434  ldloc.2
0x25a435  stsfld   string[] Microsoft.SharePoint.Administration.SPConstants::OfficeClientUserAgents
0x25a43a  ldstr    aSharepointonli// "sharepointonline.com.akadns.net"
0x25a43f  stsfld   string Microsoft.SharePoint.Administration.SPConstants::EdgeProbesURISuffix
0x25a444  ldc.i4.s 0xA
0x25a446  stsfld   int32 Microsoft.SharePoint.Administration.SPConstants::MaxFileNameUniquifierPrefixSuffixLength
0x25a44b  ldstr    a61774fff656369// "61774fff-6563-6964-7478-6d6c00000000"
0x25a450  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x25a455  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPConstants::StreamIdGuidForWordSSR
0x25a45a  ldstr    a74654fff7a6270// "74654fff-7a62-7069-0000-000000000000"
0x25a45f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x25a464  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPConstants::StreamIdGuidForPowerPointSSR
0x25a469  ldstr    a70664fff706467// "70664fff-7064-676e-0000-000000000000"
0x25a46e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x25a473  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPConstants::StreamIdGuidForVisioSSR
0x25a478  ldstr    a6e634fff6a746f// "6e634fff-6a74-6f73-6e00-000000000000"
0x25a47d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x25a482  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPConstants::StreamIdGuidForExcelSSR
0x25a487  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x25a48c  stloc.0
0x25a48d  ldloc.0
0x25a48e  ldstr    aVtiBinWebpartp// "/_vti_bin/WebPartPages.asmx"
0x25a493  ldc.i4.1
0x25a494  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x25a499  ldloc.0
0x25a49a  ldstr    aAdminBdcAddbdc// "/_admin/BDC/AddBDCApplication.aspx"
0x25a49f  ldc.i4.1
0x25a4a0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x25a4a5  ldloc.0
0x25a4a6  ldstr    aBusinessdatame// "/BusinessDataMetadataCatalog/BDCMetadat"...
0x25a4ab  ldc.i4.1
0x25a4ac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x25a4b1  ldloc.0
0x25a4b2  ldstr    aLayouts15QrAsp// "/_layouts/15/qr.aspx"
0x25a4b7  ldc.i4.1
0x25a4b8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x25a4bd  ldloc.0
0x25a4be  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.SharePoint.Administration.SPConstants::SystemPredefinedTargetedEndpoints
0x25a4c3  ldstr    a456d8cc0De154f// "456d8cc0-de15-4f2d-9296-39ed22bd2122"
0x25a4c8  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x25a4cd  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPConstants::killswitchStatsUpdateForContentDBs
0x25a4d2  ldstr    aHttpsGoMicroso// "https://go.microsoft.com/fwlink/?LinkId"...
0x25a4d7  stsfld   string Microsoft.SharePoint.Administration.SPConstants::EndOfSupportNotificationLink
0x25a4dc  ldc.i4   0x7EA
0x25a4e1  ldc.i4.7
0x25a4e2  ldc.i4.s 0xE
0x25a4e4  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0x25a4e9  ldstr    aPacificStandar// "Pacific Standard Time"
0x25a4ee  call     class [mscorlib]System.TimeZoneInfo [mscorlib]System.TimeZoneInfo::FindSystemTimeZoneById(string)
0x25a4f3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZoneInfo::ConvertTimeToUtc(valuetype [mscorlib]System.DateTime, class [mscorlib]System.TimeZoneInfo)
0x25a4f8  stsfld   valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Administration.SPConstants::EndOfSupportDate
0x25a4fd  ldc.i4   0x7E9
0x25a502  ldc.i4.6
0x25a503  ldc.i4.s 0x1E
0x25a505  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0x25a50a  ldstr    aPacificStandar// "Pacific Standard Time"
0x25a50f  call     class [mscorlib]System.TimeZoneInfo [mscorlib]System.TimeZoneInfo::FindSystemTimeZoneById(string)
0x25a514  call     valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZoneInfo::ConvertTimeToUtc(valuetype [mscorlib]System.DateTime, class [mscorlib]System.TimeZoneInfo)
0x25a519  stsfld   valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Administration.SPConstants::ScsEndOfSupportDate
0x25a51e  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x25a523  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x25a528  stloc.1
0x25a529  ldloc.1
0x25a52a  ldstr    aLayouts15Signo// "/_layouts/15/SignOut.aspx"
0x25a52f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x25a534  pop
0x25a535  ldloc.1
0x25a536  ldstr    aLayouts151033I// "/_layouts/15/1033/initstrings.js"
0x25a53b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x25a540  pop
0x25a541  ldloc.1
0x25a542  ldstr    aLayouts15InitJ// "/_layouts/15/init.js"
0x25a547  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x25a54c  pop
0x25a54d  ldloc.1
0x25a54e  ldstr    aLayouts15Themi// "/_layouts/15/theming.js"
0x25a553  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x25a558  pop
0x25a559  ldloc.1
0x25a55a  ldstr    aScriptresource_2// "/ScriptResource.axd"
0x25a55f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x25a564  pop
0x25a565  ldloc.1
0x25a566  ldstr    aLayouts15Blank// "/_layouts/15/blank.js"
0x25a56b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x25a570  pop
0x25a571  ldloc.1
0x25a572  ldstr    aScriptresource_2// "/ScriptResource.axd"
0x25a577  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x25a57c  pop
0x25a57d  ldloc.1
0x25a57e  ldstr    aWebresourceAxd// "/WebResource.axd"
0x25a583  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x25a588  pop
0x25a589  ldloc.1
  ... truncated ...
```
