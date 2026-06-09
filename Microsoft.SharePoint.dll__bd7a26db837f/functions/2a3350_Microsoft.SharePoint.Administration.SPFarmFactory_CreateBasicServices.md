# Microsoft.SharePoint.Administration.SPFarmFactory::CreateBasicServices

- ea: `0x2a3350`
- end: `0x2a3885`
- name: `Microsoft.SharePoint.Administration.SPFarmFactory::CreateBasicServices`
- size: `1333`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `service_task, broker_com_uri`

## callers

- `0x2a2fc0`

## callees

- `0x1c8a20`
- `0x1c8ee0`
- `0x1c91a0`
- `0x223200`
- `0x232440`
- `0x293270`
- `0x2a0800`
- `0x2a2e40`
- `0x2a2e60`
- `0x2a2e80`
- `0x2a2ee0`
- `0x2a2f00`
- `0x2a2f20`
- `0x2a3350`
- `0x2a3890`
- `0x2a3a60`
- `0x2a3b00`
- `0x2b5c10`
- `0x2c3e00`
- `0x315cd0`
- `0x316820`
- `0x32e0c0`
- `0x341540`
- `0x3608e0`
- `0x36fe20`
- `0x3722c0`
- `0x3740a0`
- `0x374500`
- `0x374f30`
- `0x39e520`
- `0x669210`
- `0x6a0100`
- `0x6a1130`
- `0x8b2000`
- `0x93dab0`
- `0x957530`

## string_xrefs

- `0x2a3377`: `Creating Core Services`
- `0x2a3383`: `Creating SPIncomingEmailService`
- `0x2a339b`: `Creating the SPIncomingEmailService.`
- `0x2a33cd`: `Creating SPWebService`
- `0x2a33e5`: `Creating the SPWebService.`
- `0x2a344d`: `Creating SPAdministrationService`
- `0x2a3465`: `Creating the SPAdministrationService.`
- `0x2a3495`: `Creating SPUserCodeService`
- `0x2a34ad`: `Ensuring SPUserCodeService object in farm.`
- `0x2a34ca`: `Ensured SPUserCodeService object in farm.`
- `0x2a34ee`: `Creating the SPWriterService.`
- `0x2a34f8`: `Creating SPDiagnosticsService`
- `0x2a3510`: `Creating the SPDiagnosticsService.`
- `0x2a353a`: `Creating SPUsageService`
- `0x2a3552`: `Creating the SPUsageService.`
- `0x2a3581`: `Registering SPServiceCallUsageProvider`
- `0x2a35a0`: `Registering SPDistributedCacheCallUsageProvider`
- `0x2a35bf`: `Creating SPSecurityTokenService service and application`
- `0x2a35d7`: `Creating the SPSecurityTokenService.`
- `0x2a3602`: `Successfully created the SPSecurityTokenService.`
- `0x2a3618`: `Provisioning the SPSecurityTokenService.`
- `0x2a3635`: `Successfully provisioned the SPSecurityTokenService.`
- `0x2a364b`: `Ensuring the default SPSecurityTokenServiceApplication is created`
- `0x2a3668`: `Successfully ensured that the default SPSecurityTokenServiceApplication is created`
- `0x2a367e`: `Provisioning the default SPSecurityTokenServiceApplication`
- `0x2a369b`: `Successfully provisioned the default SPSecurityTokenServiceApplication`
- `0x2a36b3`: `Creating SPTopologyWebService service, proxy and application`
- `0x2a36cb`: `Creating the SPTopologyWebService.`
- `0x2a36f6`: `Successfully created the SPTopologyWebService.`
- `0x2a370c`: `Provisioning the SPTopologyWebService.`
- `0x2a3729`: `Successfully provisioned the SPTopologyWebService.`
- `0x2a373f`: `Creating the SPTopologyWebServiceProxy.`
- `0x2a3769`: `Successfully created the SPTopologyWebServiceProxy.`
- `0x2a377f`: `Provisioning the SPTopologyWebServiceProxy.`
- `0x2a379c`: `Successfully provisioned the SPTopologyWebServiceProxy.`
- `0x2a37b2`: `Ensuring the default SPTopologyWebServiceApplication is created and provisioned`
- `0x2a37ce`: `Successfully ensured that the default SPTopologyWebServiceApplication is created and provisioned`
- `0x2a37e6`: `Creating SPTracingService`
- `0x2a37fe`: `Creating the SPTracingService.`
- `0x2a382c`: `Creating SPRequestManagementService`
- `0x2a3844`: `Creating the SPRequestManagementService.`

## pseudocode

```c

```

## disassembly

```asm
0x2a3350  ldarg.1
0x2a3351  call     void Microsoft.SharePoint.Administration.SPServiceApplicationProxyGroup::EnsureDefault(class Microsoft.SharePoint.Administration.SPFarm farm)
0x2a3356  ldstr    aProvisioningFi// "Provisioning file url redirect manager"
0x2a335b  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x2a3360  stloc.s  0xB
0x2a3362  ldarg.1
0x2a3363  call     class Microsoft.SharePoint.Administration.SPFileUrlRedirectManager Microsoft.SharePoint.Administration.SPFileUrlRedirectManager::Create(class Microsoft.SharePoint.Administration.SPFarm farm)
0x2a3368  pop
0x2a3369  leave.s  loc_2A3377
0x2a336b  ldloc.s  0xB
0x2a336d  brfalse.s loc_2A3376
0x2a336f  ldloc.s  0xB
0x2a3371  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a3376  endfinally
0x2a3377  ldstr    aCreatingCoreSe// "Creating Core Services"
0x2a337c  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x2a3381  stloc.s  0xC
0x2a3383  ldstr    aCreatingSpinco// "Creating SPIncomingEmailService"
0x2a3388  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x2a338d  stloc.s  0xD
0x2a338f  ldc.i4   0x4433C0
0x2a3394  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a3399  ldc.i4.s 0x14
0x2a339b  ldstr    aCreatingTheSpi// "Creating the SPIncomingEmailService."
0x2a33a0  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a33a5  ldsfld   string [mscorlib]System.String::Empty
0x2a33aa  ldarg.1
0x2a33ab  newobj   instance void Microsoft.SharePoint.Administration.SPIncomingEmailService::.ctor(string name, class Microsoft.SharePoint.Administration.SPFarm farm)
0x2a33b0  stloc.0
0x2a33b1  ldloc.0
0x2a33b2  ldc.i4.1
0x2a33b3  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update(bool ensure)
0x2a33b8  leave.s  loc_2A33C6
0x2a33ba  ldloc.s  0xD
0x2a33bc  brfalse.s loc_2A33C5
0x2a33be  ldloc.s  0xD
0x2a33c0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a33c5  endfinally
0x2a33c6  ldarg.0
0x2a33c7  ldarg.1
0x2a33c8  call     instance void Microsoft.SharePoint.Administration.SPFarmFactory::CreateTimerService(class Microsoft.SharePoint.Administration.SPFarm farm)
0x2a33cd  ldstr    aCreatingSpwebs// "Creating SPWebService"
0x2a33d2  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x2a33d7  stloc.s  0xE
0x2a33d9  ldc.i4   0x4433C1
0x2a33de  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a33e3  ldc.i4.s 0x14
0x2a33e5  ldstr    aCreatingTheSpw// "Creating the SPWebService."
0x2a33ea  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a33ef  ldsfld   string [mscorlib]System.String::Empty
0x2a33f4  ldarg.1
0x2a33f5  newobj   instance void Microsoft.SharePoint.Administration.SPWebService::.ctor(string name, class Microsoft.SharePoint.Administration.SPFarm farm)
0x2a33fa  stloc.1
0x2a33fb  ldloc.1
0x2a33fc  ldarg.0
0x2a33fd  call     instance class [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder Microsoft.SharePoint.Administration.SPFarmFactory::get_SiteMapDatabase()
0x2a3402  stfld    class [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder Microsoft.SharePoint.Administration.SPWebService::m_SiteMapDatabaseConnectionString
0x2a3407  ldloc.1
0x2a3408  ldarg.0
0x2a3409  call     instance class [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder Microsoft.SharePoint.Administration.SPFarmFactory::get_TimerServiceDatabase()
0x2a340e  stfld    class [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder Microsoft.SharePoint.Administration.SPWebService::m_TimerServiceDatabaseConnectionString
0x2a3413  ldloc.1
0x2a3414  ldc.i4.1
0x2a3415  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update(bool ensure)
0x2a341a  leave.s  loc_2A3428
0x2a341c  ldloc.s  0xE
0x2a341e  brfalse.s loc_2A3427
0x2a3420  ldloc.s  0xE
0x2a3422  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a3427  endfinally
0x2a3428  ldarg.1
0x2a3429  call     void Microsoft.SharePoint.Administration.SPFarmFactory::EnsureOutOfBoxFeaturesInstalled(class Microsoft.SharePoint.Administration.SPFarm farm)
0x2a342e  ldarg.0
0x2a342f  ldarg.1
0x2a3430  ldarg.0
0x2a3431  call     instance class [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder Microsoft.SharePoint.Administration.SPFarmFactory::get_AdministrationContentDatabase()
0x2a3436  ldarg.0
0x2a3437  call     instance valuetype Microsoft.SharePoint.Administration.IdentityType Microsoft.SharePoint.Administration.SPFarmFactory::get_AdministrationWebApplicationIdentityType()
0x2a343c  ldarg.0
0x2a343d  call     instance string Microsoft.SharePoint.Administration.SPFarmFactory::get_FarmUser()
0x2a3442  ldarg.0
0x2a3443  call     instance class [mscorlib]System.Security.SecureString Microsoft.SharePoint.Administration.SPFarmFactory::get_FarmPassword()
0x2a3448  call     instance void Microsoft.SharePoint.Administration.SPFarmFactory::CreateAdministrationWebService(class Microsoft.SharePoint.Administration.SPFarm farm, class [System.Data]System.Data.SqlClient.SqlConnectionStringBuilder administrationContentDatabase, valuetype Microsoft.SharePoint.Administration.IdentityType identityType, string farmUser, class [mscorlib]System.Security.SecureString farmPassword)
0x2a344d  ldstr    aCreatingSpadmi// "Creating SPAdministrationService"
0x2a3452  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x2a3457  stloc.s  0xF
0x2a3459  ldc.i4   0x4433C3
0x2a345e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a3463  ldc.i4.s 0x14
0x2a3465  ldstr    aCreatingTheSpa// "Creating the SPAdministrationService."
0x2a346a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a346f  ldsfld   string Microsoft.SharePoint.Administration.SPConstants::AdminServiceName
0x2a3474  ldarg.1
0x2a3475  newobj   instance void Microsoft.SharePoint.Administration.SPAdministrationService::.ctor(string name, class Microsoft.SharePoint.Administration.SPFarm farm)
0x2a347a  stloc.2
0x2a347b  ldloc.2
0x2a347c  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x2a3481  leave.s  loc_2A348F
0x2a3483  ldloc.s  0xF
0x2a3485  brfalse.s loc_2A348E
0x2a3487  ldloc.s  0xF
0x2a3489  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a348e  endfinally
0x2a348f  call     class Microsoft.SharePoint.Workflow.SPWorkflowTimerService Microsoft.SharePoint.Workflow.SPWorkflowTimerService::Ensure()
0x2a3494  pop
0x2a3495  ldstr    aCreatingSpuser// "Creating SPUserCodeService"
0x2a349a  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x2a349f  stloc.s  0x10
0x2a34a1  ldc.i4   0x4433C4
0x2a34a6  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a34ab  ldc.i4.s 0x14
0x2a34ad  ldstr    aEnsuringSpuser// "Ensuring SPUserCodeService object in fa"...
0x2a34b2  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a34b7  ldarg.1
0x2a34b8  ldc.i4.0
0x2a34b9  call     void Microsoft.SharePoint.Administration.SPUserCodeService::EnsureService(class Microsoft.SharePoint.Administration.SPFarm farm, bool upgrading)
0x2a34be  ldc.i4   0x4433C5
0x2a34c3  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a34c8  ldc.i4.s 0x14
0x2a34ca  ldstr    aEnsuredSpuserc// "Ensured SPUserCodeService object in far"...
0x2a34cf  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a34d4  leave.s  loc_2A34E2
0x2a34d6  ldloc.s  0x10
0x2a34d8  brfalse.s loc_2A34E1
0x2a34da  ldloc.s  0x10
0x2a34dc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a34e1  endfinally
0x2a34e2  ldc.i4   0x4433C6
0x2a34e7  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a34ec  ldc.i4.s 0x14
0x2a34ee  ldstr    aCreatingTheSpw_0// "Creating the SPWriterService."
0x2a34f3  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a34f8  ldstr    aCreatingSpdiag// "Creating SPDiagnosticsService"
0x2a34fd  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x2a3502  stloc.s  0x11
0x2a3504  ldc.i4   0x4433C7
0x2a3509  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a350e  ldc.i4.s 0x14
0x2a3510  ldstr    aCreatingTheSpd// "Creating the SPDiagnosticsService."
0x2a3515  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a351a  ldsfld   string [mscorlib]System.String::Empty
0x2a351f  ldarg.1
0x2a3520  newobj   instance void Microsoft.SharePoint.Administration.SPDiagnosticsService::.ctor(string name, class Microsoft.SharePoint.Administration.SPFarm parent)
0x2a3525  stloc.3
0x2a3526  ldloc.3
0x2a3527  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x2a352c  leave.s  loc_2A353A
0x2a352e  ldloc.s  0x11
0x2a3530  brfalse.s loc_2A3539
0x2a3532  ldloc.s  0x11
0x2a3534  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a3539  endfinally
0x2a353a  ldstr    aCreatingSpusag// "Creating SPUsageService"
0x2a353f  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x2a3544  stloc.s  0x12
0x2a3546  ldc.i4   0x4433C8
0x2a354b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a3550  ldc.i4.s 0x14
0x2a3552  ldstr    aCreatingTheSpu// "Creating the SPUsageService."
0x2a3557  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a355c  ldarg.1
0x2a355d  newobj   instance void Microsoft.SharePoint.Administration.SPUsageService::.ctor(class Microsoft.SharePoint.Administration.SPFarm farm)
0x2a3562  stloc.s  4
0x2a3564  ldloc.s  4
0x2a3566  ldc.i4.1
0x2a3567  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update(bool ensure)
0x2a356c  ldloc.s  4
0x2a356e  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Provision()
0x2a3573  leave.s  loc_2A3581
0x2a3575  ldloc.s  0x12
0x2a3577  brfalse.s loc_2A3580
0x2a3579  ldloc.s  0x12
0x2a357b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a3580  endfinally
0x2a3581  ldstr    aRegisteringSps// "Registering SPServiceCallUsageProvider"
0x2a3586  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x2a358b  stloc.s  0x13
0x2a358d  call     void Microsoft.SharePoint.Administration.SPServiceCallUsageProvider::RegisterUsageProvider()
0x2a3592  leave.s  loc_2A35A0
0x2a3594  ldloc.s  0x13
0x2a3596  brfalse.s loc_2A359F
0x2a3598  ldloc.s  0x13
0x2a359a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a359f  endfinally
0x2a35a0  ldstr    aRegisteringSpd// "Registering SPDistributedCacheCallUsage"...
0x2a35a5  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x2a35aa  stloc.s  0x14
0x2a35ac  call     void Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheCallUsageProvider::RegisterUsageProvider()
0x2a35b1  leave.s  loc_2A35BF
0x2a35b3  ldloc.s  0x14
0x2a35b5  brfalse.s loc_2A35BE
0x2a35b7  ldloc.s  0x14
0x2a35b9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a35be  endfinally
0x2a35bf  ldstr    aCreatingSpsecu// "Creating SPSecurityTokenService service"...
0x2a35c4  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x2a35c9  stloc.s  0x15
0x2a35cb  ldc.i4   0x4433C9
0x2a35d0  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a35d5  ldc.i4.s 0x14
0x2a35d7  ldstr    aCreatingTheSps// "Creating the SPSecurityTokenService."
0x2a35dc  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a35e1  ldsfld   string Microsoft.SharePoint.Administration.SPConstants::DefaultLocalObjectName
0x2a35e6  ldarg.1
0x2a35e7  newobj   instance void Microsoft.SharePoint.Administration.Claims.SPSecurityTokenService::.ctor(string name, class Microsoft.SharePoint.Administration.SPFarm farm)
0x2a35ec  stloc.s  5
0x2a35ee  ldloc.s  5
0x2a35f0  ldc.i4.1
0x2a35f1  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update(bool ensure)
0x2a35f6  ldc.i4   0x4433CA
0x2a35fb  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a3600  ldc.i4.s 0x14
0x2a3602  ldstr    aSuccessfullyCr_1// "Successfully created the SPSecurityToke"...
0x2a3607  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a360c  ldc.i4   0x4433CB
0x2a3611  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a3616  ldc.i4.s 0x14
0x2a3618  ldstr    aProvisioningTh_3// "Provisioning the SPSecurityTokenService"...
0x2a361d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a3622  ldloc.s  5
0x2a3624  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Provision()
0x2a3629  ldc.i4   0x4433CC
0x2a362e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a3633  ldc.i4.s 0x14
0x2a3635  ldstr    aSuccessfullyPr_1// "Successfully provisioned the SPSecurity"...
0x2a363a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a363f  ldc.i4   0x4433CD
0x2a3644  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a3649  ldc.i4.s 0x14
0x2a364b  ldstr    aEnsuringTheDef// "Ensuring the default SPSecurityTokenSer"...
0x2a3650  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a3655  call     class Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceApplication Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceApplication::EnsureDefaultApplication()
0x2a365a  stloc.s  6
0x2a365c  ldc.i4   0x4433CE
0x2a3661  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a3666  ldc.i4.s 0x14
0x2a3668  ldstr    aSuccessfullyEn// "Successfully ensured that the default S"...
0x2a366d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a3672  ldc.i4   0x4433CF
0x2a3677  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a367c  ldc.i4.s 0x14
0x2a367e  ldstr    aProvisioningTh_4// "Provisioning the default SPSecurityToke"...
0x2a3683  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a3688  ldloc.s  6
0x2a368a  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Provision()
0x2a368f  ldc.i4   0x4433D0
0x2a3694  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a3699  ldc.i4.s 0x14
0x2a369b  ldstr    aSuccessfullyPr_2// "Successfully provisioned the default SP"...
0x2a36a0  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a36a5  leave.s  loc_2A36B3
0x2a36a7  ldloc.s  0x15
0x2a36a9  brfalse.s loc_2A36B2
0x2a36ab  ldloc.s  0x15
0x2a36ad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a36b2  endfinally
0x2a36b3  ldstr    aCreatingSptopo// "Creating SPTopologyWebService service, "...
0x2a36b8  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name)
0x2a36bd  stloc.s  0x16
0x2a36bf  ldc.i4   0x4433D1
0x2a36c4  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a36c9  ldc.i4.s 0x14
0x2a36cb  ldstr    aCreatingTheSpt// "Creating the SPTopologyWebService."
0x2a36d0  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a36d5  ldsfld   string Microsoft.SharePoint.Administration.SPConstants::DefaultLocalObjectName
0x2a36da  ldarg.1
0x2a36db  newobj   instance void Microsoft.SharePoint.SPTopologyWebService::.ctor(string name, class Microsoft.SharePoint.Administration.SPFarm farm)
0x2a36e0  stloc.s  7
0x2a36e2  ldloc.s  7
0x2a36e4  ldc.i4.1
0x2a36e5  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update(bool ensure)
0x2a36ea  ldc.i4   0x4433D2
0x2a36ef  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a36f4  ldc.i4.s 0x14
0x2a36f6  ldstr    aSuccessfullyCr_2// "Successfully created the SPTopologyWebS"...
0x2a36fb  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a3700  ldc.i4   0x4433D3
0x2a3705  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a370a  ldc.i4.s 0x14
0x2a370c  ldstr    aProvisioningTh_5// "Provisioning the SPTopologyWebService."
0x2a3711  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a3716  ldloc.s  7
0x2a3718  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Provision()
0x2a371d  ldc.i4   0x4433D4
0x2a3722  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a3727  ldc.i4.s 0x14
0x2a3729  ldstr    aSuccessfullyPr_3// "Successfully provisioned the SPTopology"...
0x2a372e  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a3733  ldc.i4   0x4433D5
0x2a3738  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x2a373d  ldc.i4.s 0x14
0x2a373f  ldstr    aCreatingTheSpt_0// "Creating the SPTopologyWebServiceProxy."
0x2a3744  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2a3749  ldsfld   string Microsoft.SharePoint.Administration.SPConstants::DefaultLocalObjectName
0x2a374e  ldarg.1
0x2a374f  newobj   instance void Microsoft.SharePoint.SPTopologyWebServiceProxy::.ctor(string name, class Microsoft.SharePoint.Administration.SPFarm farm)
0x2a3754  stloc.s  8
0x2a3756  ldloc.s  8
0x2a3758  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x2a375d  ldc.i4   0x4433D6
  ... truncated ...
```
