# Microsoft.SharePoint.Administration.SPSiteCollection::AddInternal

- ea: `0x2f4a50`
- end: `0x2f610a`
- name: `Microsoft.SharePoint.Administration.SPSiteCollection::AddInternal`
- size: `5818`
- prototype: ``
- caller_count: `1`
- callee_count: `218`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x2f4990`

## callees

- `0x3ae60`
- `0x3ca00`
- `0x188de0`
- `0x19d580`
- `0x19d590`
- `0x1b7de0`
- `0x1bfc60`
- `0x1c1800`
- `0x1c1810`
- `0x1c1820`
- `0x1c1830`
- `0x1c1840`
- `0x1c1850`
- `0x1c1860`
- `0x1c1870`
- `0x1c1880`
- `0x1c18a0`
- `0x1c18c0`
- `0x1c3ec0`
- `0x1c8480`
- `0x1c8530`
- `0x1c8540`
- `0x1c87b0`
- `0x1c8850`
- `0x1c89b0`
- `0x1c89e0`
- `0x1c8a20`
- `0x223bd0`
- `0x223e40`
- `0x224180`
- `0x224290`
- `0x232050`
- `0x241ec0`
- `0x241ef0`
- `0x247f00`
- `0x24be20`
- `0x24c810`
- `0x25a9e0`
- `0x25c660`
- `0x25c6b0`
- `0x25cb80`
- `0x262f30`
- `0x2697b0`
- `0x269b30`
- `0x26b840`
- `0x26b850`
- `0x26b8b0`
- `0x26ba80`
- `0x26bd00`
- `0x26dc40`

## string_xrefs

- `0x2f4c21`: `InvalidCompatibilityLevel`
- `0x2f4a5b`: `Creating SPSite: Title:[{0}];CreateFromSiteMaster:{1};EffectiveCreateFromSiteMaster:{2};CreatingSiteMaster:{3};Template:{4};BatchTableCopy:{6};Description:{5}`
- `0x2f4b01`: `Exception while attempting to create Monitored Scope message: `
- `0x2f4b9a`: `POP_UseSPVersionCompatLevel`
- `0x2f4bb2`: `AddInternal: Skipping GetDefaultCompatibilityLevel, using SPVersion.MaxCompatibilityLevel [{0}].  Incoming value is [{1}]`
- `0x2f4da0`: `Creating site: Url [{0}] HostHeader [{1}] CreateFromMaster [{2}] EffectiveCreateFromSiteMaster [{3}] Database [{4}]`
- `0x2f5824`: `Exception attempting to ApplyWebTemplate to SPSite {0}:\n{1}\nAttempting to delete the site collection.`
- `0x2f597d`: `SPSiteCollection::AddInternal - CurrentUserName: {0}; CurrentUserKey: {1}; ClientIP: {2}; UserAgent: {3}; GroupId: {4}; AADUserId: {5}; `
- `0x2f5a47`: `Exception attempting to Create Site SPSite {0}:\n{1}\nAttempting to delete the site collection.`
- `0x2f5a7b`: `SNAP_GradualDeleteOnFailure`
- `0x2f5b08`: `SNAP_GradualDeleteOnFailure`
- `0x2f5aab`: `Exception attempting to delete SPSite {0} after ApplyWebTemplate failure:\n{1}\n`
- `0x2f5d03`: `Site created in {0} msecs using {1} queries. Url [{2}] FromMaster [{3}] Template [{4}] Language [{5}] CompatibilityLevel [{6}] BatchTableCopy [{7}] QueryDuration [{8}] SqlConnectionDuration [{9}] SlowestQueryDatabase [{10}] ServiceCallCount [{11}] Service CallDuration [{12}] LockWaitDuration [{13}] CPU Cycles [{14}] CPU Duration [{15}] databaseCheck [{16}] siteMasterCheck [{17}] configDBCreateSite [{18}] spRequestCreateSite [{19}] ensureSiteMaster [{20}] updateSiteSettings [{21}] updateRootWebPr`
- `0x2f6036`: `Exception attempting to log resource usage for site creation: {0}\n`
- `0x2f60a8`: `QuotaTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x2f4a50  ldstr    aCreatingSpsite// "Creating SPSite"
0x2f4a55  stloc.0
0x2f4a56  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2f4a5b  ldstr    aCreatingSpsite_0// "Creating SPSite: Title:[{0}];CreateFrom"...
0x2f4a60  ldc.i4.7
0x2f4a61  newarr   [mscorlib]System.Object
0x2f4a66  stloc.s  0x4D
0x2f4a68  ldloc.s  0x4D
0x2f4a6a  ldc.i4.0
0x2f4a6b  ldarg.1
0x2f4a6c  callvirt instance string Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_Title()
0x2f4a71  stelem.ref
0x2f4a72  ldloc.s  0x4D
0x2f4a74  ldc.i4.1
0x2f4a75  ldarg.1
0x2f4a76  callvirt instance bool Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_CreateFromSiteMaster()
0x2f4a7b  box      [mscorlib]System.Boolean
0x2f4a80  stelem.ref
0x2f4a81  ldloc.s  0x4D
0x2f4a83  ldc.i4.2
0x2f4a84  ldarg.1
0x2f4a85  callvirt instance bool Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_EffectiveCreateFromSiteMaster()
0x2f4a8a  box      [mscorlib]System.Boolean
0x2f4a8f  stelem.ref
0x2f4a90  ldloc.s  0x4D
0x2f4a92  ldc.i4.3
0x2f4a93  ldarg.1
0x2f4a94  callvirt instance bool Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_CreatingSiteMaster()
0x2f4a99  box      [mscorlib]System.Boolean
0x2f4a9e  stelem.ref
0x2f4a9f  ldloc.s  0x4D
0x2f4aa1  ldc.i4.4
0x2f4aa2  ldarg.1
0x2f4aa3  callvirt instance string Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_WebTemplate()
0x2f4aa8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2f4aad  brtrue.s loc_2F4AB7
0x2f4aaf  ldarg.1
0x2f4ab0  callvirt instance string Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_WebTemplate()
0x2f4ab5  br.s     loc_2F4ABC
0x2f4ab7  ldstr    aNull_3// "NULL"
0x2f4abc  stelem.ref
0x2f4abd  ldloc.s  0x4D
0x2f4abf  ldc.i4.5
0x2f4ac0  ldarg.1
0x2f4ac1  callvirt instance string Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_Description()
0x2f4ac6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2f4acb  brtrue.s loc_2F4AD5
0x2f4acd  ldarg.1
0x2f4ace  callvirt instance string Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_Description()
0x2f4ad3  br.s     loc_2F4ADA
0x2f4ad5  ldstr    aNull_3// "NULL"
0x2f4ada  stelem.ref
0x2f4adb  ldloc.s  0x4D
0x2f4add  ldc.i4.6
0x2f4ade  ldarg.1
0x2f4adf  callvirt instance bool Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_BatchTableCopy()
0x2f4ae4  box      [mscorlib]System.Boolean
0x2f4ae9  stelem.ref
0x2f4aea  ldloc.s  0x4D
0x2f4aec  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2f4af1  stloc.0
0x2f4af2  leave.s  loc_2F4B18
0x2f4af4  stloc.1
0x2f4af5  ldc.i4   0x8C709F
0x2f4afa  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2f4aff  ldc.i4.s 0xA
0x2f4b01  ldstr    aExceptionWhile_19// "Exception while attempting to create Mo"...
0x2f4b06  ldloc.1
0x2f4b07  callvirt instance string [mscorlib]System.Object::ToString()
0x2f4b0c  call     string [mscorlib]System.String::Concat(string, string)
0x2f4b11  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2f4b16  leave.s  loc_2F4B18
0x2f4b18  ldloc.0
0x2f4b19  ldc.i4.s 0x32
0x2f4b1b  ldc.i4.6
0x2f4b1c  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x2f4b21  stloc.s  0x4E
0x2f4b23  ldloc.s  0x4E
0x2f4b25  ldc.i4.0
0x2f4b26  ldc.i4.0
0x2f4b27  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor(int32 maxAllowedQueries)
0x2f4b2c  stelem.ref
0x2f4b2d  ldloc.s  0x4E
0x2f4b2f  ldc.i4.1
0x2f4b30  ldc.i4.s 0x64
0x2f4b32  newobj   instance void Microsoft.SharePoint.Utilities.SPRequestUsageCounter::.ctor(int32 maxValue)
0x2f4b37  stelem.ref
0x2f4b38  ldloc.s  0x4E
0x2f4b3a  ldc.i4.2
0x2f4b3b  ldc.i4   0x7FFFFFFF
0x2f4b40  newobj   instance void Microsoft.SharePoint.Utilities.SPServiceCallCounter::.ctor(int32 maxValue)
0x2f4b45  stelem.ref
0x2f4b46  ldloc.s  0x4E
0x2f4b48  ldc.i4.3
0x2f4b49  newobj   instance void Microsoft.SharePoint.Utilities.SPLockWaitCounter::.ctor()
0x2f4b4e  stelem.ref
0x2f4b4f  ldloc.s  0x4E
0x2f4b51  ldc.i4.4
0x2f4b52  newobj   instance void Microsoft.SharePoint.Utilities.SPCPUCycleCounter::.ctor()
0x2f4b57  stelem.ref
0x2f4b58  ldloc.s  0x4E
0x2f4b5a  ldc.i4.5
0x2f4b5b  newobj   instance void Microsoft.SharePoint.Utilities.SPSiteCreationMonitor::.ctor()
0x2f4b60  stelem.ref
0x2f4b61  ldloc.s  0x4E
0x2f4b63  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceLevel, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x2f4b68  stloc.2
0x2f4b69  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2f4b6e  stloc.3
0x2f4b6f  ldloc.3
0x2f4b70  stloc.s  4
0x2f4b72  ldloc.3
0x2f4b73  stloc.s  5
0x2f4b75  ldloc.3
0x2f4b76  stloc.s  6
0x2f4b78  ldloc.3
0x2f4b79  stloc.s  7
0x2f4b7b  ldloc.3
0x2f4b7c  stloc.s  8
0x2f4b7e  ldloc.3
0x2f4b7f  stloc.s  9
0x2f4b81  ldloc.3
0x2f4b82  stloc.s  0xA
0x2f4b84  ldloc.3
0x2f4b85  stloc.s  0xB
0x2f4b87  ldloc.3
0x2f4b88  stloc.s  0xC
0x2f4b8a  ldarg.0
0x2f4b8b  call     instance void Microsoft.SharePoint.Administration.SPSiteCollection::VerifyAttachState()
0x2f4b90  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPSiteCollection::s_UseSPVersionCompatLevel
0x2f4b95  ldstr    a20180413// "2018/04/13"
0x2f4b9a  ldstr    aPopUsespversio// "POP_UseSPVersionCompatLevel"
0x2f4b9f  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x2f4ba4  brtrue.s loc_2F4BED
0x2f4ba6  ldc.i4   0x2343598
0x2f4bab  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2f4bb0  ldc.i4.s 0x14
0x2f4bb2  ldstr    aAddinternalSki// "AddInternal: Skipping GetDefaultCompati"...
0x2f4bb7  ldc.i4.2
0x2f4bb8  newarr   [mscorlib]System.Object
0x2f4bbd  stloc.s  0x4D
0x2f4bbf  ldloc.s  0x4D
0x2f4bc1  ldc.i4.0
0x2f4bc2  ldc.i4.s 0xF
0x2f4bc4  box      [mscorlib]System.Int32
0x2f4bc9  stelem.ref
0x2f4bca  ldloc.s  0x4D
0x2f4bcc  ldc.i4.1
0x2f4bcd  ldarg.1
0x2f4bce  callvirt instance int32 Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_CompatibilityLevel()
0x2f4bd3  box      [mscorlib]System.Int32
0x2f4bd8  stelem.ref
0x2f4bd9  ldloc.s  0x4D
0x2f4bdb  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2f4be0  ldarg.1
0x2f4be1  ldc.i4.s 0xF
0x2f4be3  callvirt instance void Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::set_CompatibilityLevel(int32 value)
0x2f4be8  br       loc_2F4C81
0x2f4bed  ldarg.1
0x2f4bee  callvirt instance int32 Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_CompatibilityLevel()
0x2f4bf3  brtrue.s loc_2F4C0C
0x2f4bf5  ldarg.1
0x2f4bf6  ldarg.0
0x2f4bf7  call     instance class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.Administration.SPSiteCollection::get_WebApplication()
0x2f4bfc  ldarg.1
0x2f4bfd  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_SiteSubscription()
0x2f4c02  call     int32 Microsoft.SharePoint.Utilities.SPUtility::GetDefaultCompatibilityLevel(class Microsoft.SharePoint.Administration.SPWebApplication webApp, class Microsoft.SharePoint.SPSiteSubscription siteSubscription)
0x2f4c07  callvirt instance void Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::set_CompatibilityLevel(int32 value)
0x2f4c0c  ldarg.1
0x2f4c0d  callvirt instance bool Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_OverrideCompatibilityRestriction()
0x2f4c12  brfalse.s loc_2F4C6A
0x2f4c14  ldarg.1
0x2f4c15  callvirt instance int32 Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_CompatibilityLevel()
0x2f4c1a  call     bool Microsoft.SharePoint.Utilities.SPUtility::IsValidCompatibilityLevel(int32 compatibilityLevel)
0x2f4c1f  brtrue.s loc_2F4C4A
0x2f4c21  ldstr    aInvalidcompati// "InvalidCompatibilityLevel"
0x2f4c26  ldc.i4.1
0x2f4c27  newarr   [mscorlib]System.Object
0x2f4c2c  stloc.s  0x4D
0x2f4c2e  ldloc.s  0x4D
0x2f4c30  ldc.i4.0
0x2f4c31  ldarg.1
0x2f4c32  callvirt instance int32 Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_CompatibilityLevel()
0x2f4c37  box      [mscorlib]System.Int32
0x2f4c3c  stelem.ref
0x2f4c3d  ldloc.s  0x4D
0x2f4c3f  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x2f4c44  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x2f4c49  throw
0x2f4c4a  ldarg.1
0x2f4c4b  callvirt instance bool Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_CreatingSiteMaster()
0x2f4c50  brtrue.s loc_2F4C81
0x2f4c52  ldarg.0
0x2f4c53  call     instance class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.Administration.SPSiteCollection::get_WebApplication()
0x2f4c58  callvirt instance class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPPersistedObject::get_Farm()
0x2f4c5d  callvirt instance bool Microsoft.SharePoint.Administration.SPFarm::CurrentUserIsAdministrator()
0x2f4c62  brtrue.s loc_2F4C81
0x2f4c64  newobj   instance void [mscorlib]System.UnauthorizedAccessException::.ctor()
0x2f4c69  throw
0x2f4c6a  ldarg.0
0x2f4c6b  call     instance class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.Administration.SPSiteCollection::get_WebApplication()
0x2f4c70  ldarg.1
0x2f4c71  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_SiteSubscription()
0x2f4c76  ldarg.1
0x2f4c77  callvirt instance int32 Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_CompatibilityLevel()
0x2f4c7c  call     void Microsoft.SharePoint.Administration.SPSiteCollection::ValidateSiteCompatibilityLevel(class Microsoft.SharePoint.Administration.SPWebApplication application, class Microsoft.SharePoint.SPSiteSubscription siteSubscription, int32 compatibilityLevel)
0x2f4c81  ldarg.1
0x2f4c82  callvirt instance string Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_SiteUrl()
0x2f4c87  stloc.s  0xE
0x2f4c89  ldnull
0x2f4c8a  stloc.s  0x10
0x2f4c8c  ldnull
0x2f4c8d  stloc.s  0x11
0x2f4c8f  ldarg.0
0x2f4c90  call     instance class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.Administration.SPSiteCollection::get_WebApplication()
0x2f4c95  ldarg.0
0x2f4c96  ldfld    valuetype Microsoft.SharePoint.Administration.SPUrlZone Microsoft.SharePoint.Administration.SPSiteCollection::m_Zone
0x2f4c9b  ldloca.s 0xE
0x2f4c9d  ldarg.1
0x2f4c9e  callvirt instance bool Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_UseHostHeaderAsSiteName()
0x2f4ca3  ldloca.s 0xD
0x2f4ca5  ldloca.s 0xF
0x2f4ca7  call     void Microsoft.SharePoint.Administration.SPSiteCollection::ValidateSiteUrlEx(class Microsoft.SharePoint.Administration.SPWebApplication application, valuetype Microsoft.SharePoint.Administration.SPUrlZone zone, string& siteUrl, bool useHostHeaderAsSiteName, [out] class [System]System.Uri& fullUri, [out] string& strFullUrl)
0x2f4cac  ldloc.s  0xD
0x2f4cae  call     class [System]System.Uri Microsoft.SharePoint.Administration.SPAlternateUrl::Canonicalize(class [System]System.Uri uri)
0x2f4cb3  stloc.s  0x12
0x2f4cb5  ldarg.1
0x2f4cb6  callvirt instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_ContentDatabase()
0x2f4cbb  stloc.s  0x13
0x2f4cbd  ldnull
0x2f4cbe  ldloc.s  0x13
0x2f4cc0  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x2f4cc5  brfalse.s loc_2F4D2C
0x2f4cc7  ldarg.1
0x2f4cc8  callvirt instance string Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_DatabaseServer()
0x2f4ccd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2f4cd2  brtrue.s loc_2F4D16
0x2f4cd4  ldarg.0
0x2f4cd5  call     instance class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.Administration.SPSiteCollection::get_WebApplication()
0x2f4cda  callvirt instance class Microsoft.SharePoint.Administration.SPContentDatabaseCollection Microsoft.SharePoint.Administration.SPWebApplication::get_ContentDatabases()
0x2f4cdf  ldarg.1
0x2f4ce0  callvirt instance string Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_DatabaseServer()
0x2f4ce5  ldarg.1
0x2f4ce6  callvirt instance string Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_DatabaseName()
0x2f4ceb  ldarg.1
0x2f4cec  callvirt instance string Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_UserName()
0x2f4cf1  ldarg.1
0x2f4cf2  callvirt instance string Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_Password()
0x2f4cf7  ldc.i4   0x7D0
0x2f4cfc  ldc.i4   0x1388
0x2f4d01  ldc.i4.0
0x2f4d02  callvirt instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Administration.SPContentDatabaseCollection::Add(string strDatabaseServer, string strDatabaseName, string strDatabaseUsername, string strDatabasePassword, int32 warningSiteCount, int32 maximumSiteCount, int32 status)
0x2f4d07  stloc.s  0x13
0x2f4d09  ldarg.0
0x2f4d0a  call     instance class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.Administration.SPSiteCollection::get_WebApplication()
0x2f4d0f  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x2f4d14  br.s     loc_2F4D2C
0x2f4d16  ldarg.0
0x2f4d17  ldarg.1
0x2f4d18  callvirt instance class Microsoft.SharePoint.SPSiteSubscription Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_SiteSubscription()
0x2f4d1d  ldarg.1
0x2f4d1e  callvirt instance bool Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_UseHostHeaderAsSiteName()
0x2f4d23  ldloc.s  0xD
0x2f4d25  call     instance class Microsoft.SharePoint.Administration.SPContentDatabase Microsoft.SharePoint.Administration.SPSiteCollection::GetContentDatabaseForSiteCreation(class Microsoft.SharePoint.SPSiteSubscription siteSubscription, bool useHostHeaderAsSiteName, class [System]System.Uri siteUri)
0x2f4d2a  stloc.s  0x13
0x2f4d2c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2f4d31  stloc.s  4
0x2f4d33  ldc.i4.0
0x2f4d34  stloc.s  0x14
0x2f4d36  ldarg.0
0x2f4d37  call     instance class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.Administration.SPSiteCollection::get_WebApplication()
0x2f4d3c  isinst   Microsoft.SharePoint.Administration.SPAdministrationWebApplication
0x2f4d41  brtrue.s loc_2F4D62
0x2f4d43  ldarg.0
0x2f4d44  call     instance class Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.Administration.SPSiteCollection::get_WebApplication()
0x2f4d49  callvirt instance class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPPersistedObject::get_Farm()
0x2f4d4e  callvirt instance class Microsoft.SharePoint.Administration.SPServiceCollection Microsoft.SharePoint.Administration.SPFarm::get_Services()
0x2f4d53  callvirt T0x2B000030
0x2f4d58  callvirt instance bool Microsoft.SharePoint.Administration.SPWebService::get_CreateActiveDirectoryAccounts()
0x2f4d5d  brfalse.s loc_2F4D62
0x2f4d5f  ldc.i4.1
0x2f4d60  stloc.s  0x14
0x2f4d62  ldarg.1
0x2f4d63  ldloc.s  0x13
0x2f4d65  callvirt instance class Microsoft.SharePoint.Administration.SPSiteMasterManager Microsoft.SharePoint.Administration.SPContentDatabase::get_SiteMasterManager()
0x2f4d6a  ldarg.1
0x2f4d6b  callvirt instance bool Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_CreateFromSiteMaster()
0x2f4d70  ldarg.1
0x2f4d71  callvirt instance string Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_WebTemplate()
0x2f4d76  ldloc.s  0x14
0x2f4d78  ldarg.1
0x2f4d79  callvirt instance bool Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_CreatingSiteMaster()
0x2f4d7e  ldarg.1
0x2f4d7f  callvirt instance int32 Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::get_CompatibilityLevel()
0x2f4d84  callvirt instance bool Microsoft.SharePoint.Administration.SPSiteMasterManager::GetEffectiveCreateFromSiteMasterFlag(bool createFromMaster, string webTemplate, bool adAccountCreateMode, bool bCreatingSiteMaster, int32 CompatibilityLevel)
0x2f4d89  callvirt instance void Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::set_EffectiveCreateFromSiteMaster(bool value)
0x2f4d8e  ldarg.1
0x2f4d8f  ldloc.s  0x13
0x2f4d91  callvirt instance bool Microsoft.SharePoint.Administration.SPDatabase::get_IsSqlAzure()
0x2f4d96  callvirt instance void Microsoft.SharePoint.Administration.SPSiteCollectionAddParameters::set_SiteDatabaseOnSqlAzure(bool value)
  ... truncated ...
```
