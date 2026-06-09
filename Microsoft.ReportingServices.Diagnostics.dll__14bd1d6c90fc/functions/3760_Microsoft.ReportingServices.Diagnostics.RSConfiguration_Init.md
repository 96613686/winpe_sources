# Microsoft.ReportingServices.Diagnostics.RSConfiguration::Init

- ea: `0x3760`
- end: `0x3ad0`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::Init`
- size: `880`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x36e0`
- `0x4170`

## pseudocode

```c

```

## disassembly

```asm
0x3760  ldarg.0
0x3761  ldc.i4.0
0x3762  conv.i8
0x3763  stfld    int64 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_sequence
0x3768  ldarg.0
0x3769  ldnull
0x376a  stfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExtensionsConfiguration Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_extensions
0x376f  ldarg.0
0x3770  ldnull
0x3771  stfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_pairs
0x3776  ldarg.0
0x3777  ldnull
0x3778  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_dsn
0x377d  ldarg.0
0x377e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.EventExtension>::.ctor()
0x3783  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.EventExtension> Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_events
0x3788  ldarg.0
0x3789  ldc.i4.0
0x378a  stfld    valuetype CatalogConnectionType Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_connectionType
0x378f  ldarg.0
0x3790  ldc.i4.1
0x3791  stfld    valuetype CatalogConnectionAuth Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_connectionAuth
0x3796  ldarg.0
0x3797  ldnull
0x3798  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_encryptedCatalogUser
0x379d  ldarg.0
0x379e  ldnull
0x379f  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_encryptedCatalogDomain
0x37a4  ldarg.0
0x37a5  ldnull
0x37a6  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_encryptedCatalogCred
0x37ab  ldarg.0
0x37ac  ldnull
0x37ad  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_defaultViewerStyle
0x37b2  ldarg.0
0x37b3  ldc.i4.1
0x37b4  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_displayErrorLink
0x37b9  ldarg.0
0x37ba  ldc.i4.1
0x37bb  stfld    valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SnapshotTemporaryStorage Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_WebServiceUseFileShareStorage
0x37c0  ldarg.0
0x37c1  ldc.i4.0
0x37c2  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isSchedulingService
0x37c7  ldarg.0
0x37c8  ldc.i4.0
0x37c9  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isNotificationService
0x37ce  ldarg.0
0x37cf  ldc.i4.0
0x37d0  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isEventService
0x37d5  ldarg.0
0x37d6  ldc.i4.s 0xA
0x37d8  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_pollingInterval
0x37dd  ldarg.0
0x37de  ldc.i4.0
0x37df  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_maxCatalogConnectionPoolSizePerProcess
0x37e4  ldarg.0
0x37e5  ldc.r4   0.80000001
0x37ea  stfld    float32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_memoryLimit
0x37ef  ldarg.0
0x37f0  ldc.r4   0.89999998
0x37f5  stfld    float32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_maxMemoryLimit
0x37fa  ldarg.0
0x37fb  ldc.i4.0
0x37fc  ldc.i4   0x2D0
0x3801  ldc.i4.0
0x3802  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x3807  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_recycleTime
0x380c  ldarg.0
0x380d  ldc.i4.0
0x380e  ldc.i4.s 0x1E
0x3810  ldc.i4.0
0x3811  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x3816  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_maxAppDomainUnloadTime
0x381b  ldarg.0
0x381c  ldc.i4.0
0x381d  ldc.i4.s 0x5A
0x381f  ldc.i4.0
0x3820  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x3825  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_maxTimedAppDomainUnload
0x382a  ldarg.0
0x382b  ldc.i4.0
0x382c  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_maxQueueThreads
0x3831  ldarg.0
0x3832  ldstr    asc_126C2// ""
0x3837  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_urlRoot
0x383c  ldarg.0
0x383d  ldnull
0x383e  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_encryptedSurrogateUserName
0x3843  ldarg.0
0x3844  ldnull
0x3845  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_encryptedSurrogateDomain
0x384a  ldarg.0
0x384b  ldnull
0x384c  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_encryptedSurrogatePassword
0x3851  ldarg.0
0x3852  ldnull
0x3853  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_policyLevel
0x3858  ldarg.0
0x3859  ldnull
0x385a  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_fileShareStoragePath
0x385f  ldarg.0
0x3860  ldc.i4.0
0x3861  stfld    valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.SnapshotTemporaryStorage Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_windowsServiceUserFileShareStorage
0x3866  ldarg.0
0x3867  ldnull
0x3868  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_webServiceAccount
0x386d  ldarg.0
0x386e  ldc.i4.1
0x386f  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isWebServiceEnabled
0x3874  ldarg.0
0x3875  ldc.i4.0
0x3876  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isReportBuilderAnonymousAccessEnabled
0x387b  ldarg.0
0x387c  ldc.i4.0
0x387d  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isRdceEnabled
0x3882  ldarg.0
0x3883  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3888  stfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_serviceApplicationId
0x388d  ldarg.0
0x388e  ldc.i4.0
0x388f  conv.i8
0x3890  stfld    int64 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_workingSetMin
0x3895  ldarg.0
0x3896  ldc.i4.0
0x3897  conv.i8
0x3898  stfld    int64 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_workingSetMax
0x389d  ldarg.0
0x389e  ldnull
0x389f  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_serverDirectory
0x38a4  ldarg.0
0x38a5  ldnull
0x38a6  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_serverUrl
0x38ab  ldarg.0
0x38ac  ldnull
0x38ad  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_serverExternalUrl
0x38b2  ldarg.0
0x38b3  ldnull
0x38b4  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_loginUrl
0x38b9  ldarg.0
0x38ba  ldc.i4.0
0x38bb  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_useSSL
0x38c0  ldarg.0
0x38c1  ldc.i4.1
0x38c2  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_enableReportDesignClientButton
0x38c7  ldarg.0
0x38c8  ldnull
0x38c9  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_pageCountMode
0x38ce  ldarg.0
0x38cf  ldc.i4.s 0x3C
0x38d1  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_postbackTimeout
0x38d6  ldarg.0
0x38d7  ldnull
0x38d8  stfld    class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_passthroughCookies
0x38dd  ldarg.0
0x38de  ldnull
0x38df  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication, valuetype Microsoft.ReportingServices.Diagnostics.UrlConfiguration> Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_urlConfiguration
0x38e4  ldarg.0
0x38e5  ldc.i4.0
0x38e6  stfld    valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.AuthenticationTypes Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_authenticationTypes
0x38eb  ldarg.0
0x38ec  ldc.i4.3
0x38ed  stfld    valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.LogonMethod Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_logonMethod
0x38f2  ldarg.0
0x38f3  ldnull
0x38f4  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_authRealm
0x38f9  ldarg.0
0x38fa  ldnull
0x38fb  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_authDomain
0x3900  ldarg.0
0x3901  ldc.i4.1
0x3902  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_authPersistence
0x3907  ldarg.0
0x3908  ldc.i4.s 0x32
0x390a  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_maxUnauthenticatedRequests
0x390f  ldarg.0
0x3910  ldc.i4.s 0xA
0x3912  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_unauthenticatedRequestWindow
0x3917  ldarg.0
0x3918  ldc.i4.s 0x3C
0x391a  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_unauthenticatedRequestLockoutTime
0x391f  ldarg.0
0x3920  ldc.i4   0x258
0x3925  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_authTokenCacheMaxSize
0x392a  ldarg.0
0x392b  ldc.i4   0x258
0x3930  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_authTokenCacheMaintenanceInterval
0x3935  ldarg.0
0x3936  ldc.i4.0
0x3937  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_authTokenCacheLogonTimeout
0x393c  ldarg.0
0x393d  ldc.i4   0x21C
0x3942  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_authTokenCacheEntryTimeout
0x3947  ldarg.0
0x3948  ldc.i4.1
0x3949  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_requiredHttpsLevel
0x394e  ldarg.0
0x394f  ldc.i4.0
0x3950  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_disableSecureFormsAuthenticationCookie
0x3955  ldarg.0
0x3956  ldc.i4.s 0x14
0x3958  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_maxActiveReqForOneUser
0x395d  ldarg.0
0x395e  ldc.i4.1
0x395f  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_maxScheduleWait
0x3964  ldarg.0
0x3965  ldc.i4.s 0x1E
0x3967  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_DBQueryTimeout
0x396c  ldarg.0
0x396d  ldc.i4   0x96
0x3972  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_processTimeout
0x3977  ldarg.0
0x3978  ldc.i4.s 0x1E
0x397a  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_processTimeoutGcExtension
0x397f  ldarg.0
0x3980  ldc.i4   0x1A4
0x3985  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_DBCleanupTimeout
0x398a  ldarg.0
0x398b  ldc.i4   0x3E8
0x3990  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_DBCleanupBatchFactor
0x3995  ldarg.0
0x3996  ldc.i4.s 0x78
0x3998  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_connectionTimeout
0x399d  ldarg.0
0x399e  ldnull
0x399f  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_installationID
0x39a4  ldarg.0
0x39a5  ldnull
0x39a6  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_instanceID
0x39ab  ldarg.0
0x39ac  ldnull
0x39ad  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_rpcEndpoint
0x39b2  ldarg.0
0x39b3  ldnull
0x39b4  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_windowsServiceName
0x39b9  ldarg.0
0x39ba  ldc.i4.0
0x39bb  stfld    valuetype RecycleOptions Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_RecycleProcessOnSevereErrors
0x39c0  ldarg.0
0x39c1  ldc.i4.s 0x1E
0x39c3  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_RunningRequestsScavengerCycleParam
0x39c8  ldarg.0
0x39c9  ldc.i4.s 0x1E
0x39cb  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_RunningRequestsDBCycleParam
0x39d0  ldarg.0
0x39d1  ldc.i4.s 0x1E
0x39d3  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_RunningRequestsAgeParam
0x39d8  ldarg.0
0x39d9  ldc.i4.s 0xA
0x39db  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_CleanupCycleMinutesParam
0x39e0  ldarg.0
0x39e1  ldc.i4.s 0x78
0x39e3  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_dailyCleanupMinuteOfDayParam
0x39e8  ldarg.0
0x39e9  ldc.i4.s 0x14
0x39eb  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_AlertingCleanupCycleMinutesParam
0x39f0  ldarg.0
0x39f1  ldc.i4   0x168
0x39f6  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_AlertingDataCleanupMinutesParam
0x39fb  ldarg.0
0x39fc  ldc.i4   0x2760
0x3a01  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_AlertingExecutionLogCleanupMinutesParam
0x3a06  ldarg.0
0x3a07  ldc.i4   0xB4
0x3a0c  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_AlertingMaxDataRetentionDaysParam
0x3a11  ldarg.0
0x3a12  ldc.i4.0
0x3a13  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_enableRemoteErrors
0x3a18  ldarg.0
0x3a19  ldc.i4.0
0x3a1a  stfld    valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExecutionLogLevel Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_execLogLevel
0x3a1f  ldarg.0
0x3a20  ldc.i4   0x258
0x3a25  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_rdlxSessionTimeout
0x3a2a  ldarg.0
0x3a2b  ldc.i4   0x384
0x3a30  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_rdlxExecutionTimeout
0x3a35  ldarg.0
0x3a36  ldc.r8   1.0
0x3a3f  stfld    float64 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_globalConnectionPoolEvictionTimeout
0x3a44  ldarg.0
0x3a45  ldc.r8   0.083
0x3a4e  stfld    float64 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_asOnPremConnectionPoolEvictionTimeout
0x3a53  ldarg.0
0x3a54  ldc.i4   0x428
0x3a59  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_watsonFlags
0x3a5e  ldarg.0
0x3a5f  ldsfld   class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.RSConfiguration::_DefaultWatsonDumpOnExceptions
0x3a64  stfld    class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_watsonDumpOnExceptions
0x3a69  ldarg.0
0x3a6a  ldsfld   class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.RSConfiguration::_DefaultWatsonDumpExcludeIfContainsExceptions
0x3a6f  stfld    class [System]System.Collections.Specialized.StringCollection Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_watsonDumpExcludeIfContainsExceptions
0x3a74  ldarg.0
0x3a75  ldc.i4.s 0x10
0x3a77  stfld    int32 Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_requestCacheSlots
0x3a7c  ldarg.0
0x3a7d  ldnull
0x3a7e  stfld    class Microsoft.ReportingServices.Diagnostics.RDLSandboxingConfiguration Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_rdlSandboxing
0x3a83  ldarg.0
0x3a84  ldnull
0x3a85  stfld    class Microsoft.ReportingServices.Diagnostics.MapTileServerConfiguration Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_mapTileServerConfiguration
  ... truncated ...
```
