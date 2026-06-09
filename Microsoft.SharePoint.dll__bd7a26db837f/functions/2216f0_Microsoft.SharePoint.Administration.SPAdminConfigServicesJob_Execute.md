# Microsoft.SharePoint.Administration.SPAdminConfigServicesJob::Execute

- ea: `0x2216f0`
- end: `0x22209d`
- name: `Microsoft.SharePoint.Administration.SPAdminConfigServicesJob::Execute`
- size: `2477`
- prototype: ``
- caller_count: `0`
- callee_count: `39`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1b7de0`
- `0x1c8480`
- `0x1c8520`
- `0x1c8530`
- `0x1c8540`
- `0x1c8850`
- `0x1c89b0`
- `0x1c89e0`
- `0x1c8a20`
- `0x1c8ee0`
- `0x2216f0`
- `0x222a40`
- `0x2232c0`
- `0x249550`
- `0x24a190`
- `0x29d110`
- `0x29d1e0`
- `0x29ffd0`
- `0x2d8cb0`
- `0x2dc910`
- `0x2eb850`
- `0x2eba00`
- `0x2ee620`
- `0x2ee720`
- `0x2ef190`
- `0x2ef1c0`
- `0x340ff0`
- `0x341000`
- `0x341010`
- `0x341020`
- `0x36fe00`
- `0x36fee0`
- `0x373b20`
- `0x373b40`
- `0x577060`
- `0x93d420`
- `0x93dae0`
- `0x93e240`
- `0x957470`

## string_xrefs

- `0x221711`: `AdminConfigServicesJob_LocalSPServerNotFound`
- `0x221733`: `AdminConfigServicesJob_ServiceInstancesCollectionNull`
- `0x221755`: `Beginning service instance configuring according to MinRole`
- `0x2217a2`: `Configuring service instance: {0}`
- `0x22181f`: `Configuring service instance complete: {0}`
- `0x221853`: `Configuring service instance failed: {0}`
- `0x221884`: `AdminConfigServicesJob_InstanceProvisioningFailure`
- `0x22190a`: `Completed service instance configuring`
- `0x22192c`: `Preparing to provision service applications`
- `0x221963`: `AdminConfigServicesJob_FailedToCreateProvisioningContext`
- `0x221984`: `AdminConfigServicesJob_DefaultProvisioningContextIsNull`
- `0x2219a6`: `Beginning service application provisioning`
- `0x221a3a`: `Creating service application: {0}`
- `0x221a79`: `Creating service application completed: {0}`
- `0x221ac0`: `Creating service application proxy: {0}`
- `0x221b18`: `Creating service application proxy completed: {0}`
- `0x221b52`: `AdminConfigServicesJob_ServiceApplicationCreationFailure`
- `0x221bac`: `Creating service application FAILED: {0}`
- `0x221bf9`: `AdminConfigServicesJob_ServiceApplicationProvisioningFailure`
- `0x221d77`: `AdminConfigServicesJob_ServiceApplicationProvisioningFailure`
- `0x221c58`: `Provisioning service applications FAILED: {0}`
- `0x221cb5`: `Provisioning service application {0}`
- `0x221d46`: `Failed to provision service application {0}`
- `0x221e11`: `Provisioning service application proxy {0}`
- `0x221e6e`: `Successfully provisioned service application proxy {0}`
- `0x221e99`: `Adding service proxy to default service application proxy group {0}`
- `0x221ed4`: `Succesfully added service proxy to default service application proxy group {0}`
- `0x221f08`: `Failed to provision service application proxy {0}`
- `0x221f39`: `AdminConfigServicesJob_ServiceApplicationProxyProvisioningFailure`
- `0x221fb6`: `Completed service application provisioning`
- `0x22207b`: `FAILED service application provisioning. There was at least one error while creating and provisioning service instances, service applications, and service proxies.`
- `0x222086`: `AdminConfigServicesJob_ErrorsInJob`

## pseudocode

```c

```

## disassembly

```asm
0x2216f0  ldc.i4.0
0x2216f1  stloc.0
0x2216f2  ldsfld   string [mscorlib]System.String::Empty
0x2216f7  stloc.1
0x2216f8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPServiceApplication>::.ctor()
0x2216fd  stloc.2
0x2216fe  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPServiceApplicationProxy>::.ctor()
0x221703  stloc.3
0x221704  call     class Microsoft.SharePoint.Administration.SPServer Microsoft.SharePoint.Administration.SPServer::get_Local()
0x221709  ldnull
0x22170a  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x22170f  brfalse.s loc_221727
0x221711  ldstr    aAdminconfigser_2// "AdminConfigServicesJob_LocalSPServerNot"...
0x221716  ldc.i4.0
0x221717  newarr   [mscorlib]System.Object
0x22171c  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x221721  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x221726  throw
0x221727  call     class Microsoft.SharePoint.Administration.SPServer Microsoft.SharePoint.Administration.SPServer::get_Local()
0x22172c  callvirt instance class Microsoft.SharePoint.Administration.SPServiceInstanceCollection Microsoft.SharePoint.Administration.SPServer::get_ServiceInstances()
0x221731  brtrue.s loc_221749
0x221733  ldstr    aAdminconfigser_3// "AdminConfigServicesJob_ServiceInstances"...
0x221738  ldc.i4.0
0x221739  newarr   [mscorlib]System.Object
0x22173e  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x221743  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x221748  throw
0x221749  ldc.i4   0x7DF4CC
0x22174e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x221753  ldc.i4.s 0x14
0x221755  ldstr    aBeginningServi// "Beginning service instance configuring "...
0x22175a  ldnull
0x22175b  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x221760  call     class Microsoft.SharePoint.Administration.SPServer Microsoft.SharePoint.Administration.SPServer::get_Local()
0x221765  callvirt instance class Microsoft.SharePoint.Administration.SPServiceInstanceCollection Microsoft.SharePoint.Administration.SPServer::get_ServiceInstances()
0x22176a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPServiceInstance>::GetEnumerator()
0x22176f  stloc.s  0x1B
0x221771  br       loc_2218E4
0x221776  ldloc.s  0x1B
0x221778  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Administration.SPServiceInstance>::get_Current()
0x22177d  stloc.s  4
0x22177f  ldarg.0
0x221780  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.SharePoint.Administration.SPAdminConfigServicesJob::ServiceInstances
0x221785  ldloc.s  4
0x221787  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x22178c  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x221791  brfalse  loc_2218E4
0x221796  ldc.i4   0x7DF4CD
0x22179b  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x2217a0  ldc.i4.s 0x14
0x2217a2  ldstr    aConfiguringSer// "Configuring service instance: {0}"
0x2217a7  ldc.i4.1
0x2217a8  newarr   [mscorlib]System.Object
0x2217ad  stloc.s  0x1C
0x2217af  ldloc.s  0x1C
0x2217b1  ldc.i4.0
0x2217b2  ldloc.s  4
0x2217b4  callvirt instance string [mscorlib]System.Object::ToString()
0x2217b9  stelem.ref
0x2217ba  ldloc.s  0x1C
0x2217bc  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2217c1  call     bool Microsoft.SharePoint.Administration.SPServerRoleManager::IsMinRoleFeatureEnabled()
0x2217c6  brfalse.s loc_22180C
0x2217c8  call     class Microsoft.SharePoint.Administration.SPConfigurationDatabase Microsoft.SharePoint.Administration.SPConfigurationDatabase::get_Local()
0x2217cd  ldloc.s  4
0x2217cf  callvirt instance class Microsoft.SharePoint.Administration.SPService Microsoft.SharePoint.Administration.SPServiceInstance::get_Service()
0x2217d4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x2217d9  ldc.i4.0
0x2217da  ldc.i4.0
0x2217db  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject Microsoft.SharePoint.Administration.SPConfigurationDatabase::GetObject(valuetype [mscorlib]System.Guid id, bool checkInMemoryCache, bool checkFileSystemCache)
0x2217e0  castclass Microsoft.SharePoint.Administration.SPService
0x2217e5  stloc.s  5
0x2217e7  ldloc.s  5
0x2217e9  callvirt instance bool Microsoft.SharePoint.Administration.SPService::get_AutoProvision()
0x2217ee  brfalse.s loc_2217FE
0x2217f0  call     class Microsoft.SharePoint.Administration.SPServerRoleManager Microsoft.SharePoint.Administration.SPServerRoleManager::get_LocalOrThrow()
0x2217f5  ldloc.s  4
0x2217f7  callvirt instance void Microsoft.SharePoint.Administration.SPServerRoleManager::ProvisionServiceInstance(class Microsoft.SharePoint.Administration.SPServiceInstance serviceInstance)
0x2217fc  br.s     loc_221813
0x2217fe  call     class Microsoft.SharePoint.Administration.SPServerRoleManager Microsoft.SharePoint.Administration.SPServerRoleManager::get_LocalOrThrow()
0x221803  ldloc.s  4
0x221805  callvirt instance void Microsoft.SharePoint.Administration.SPServerRoleManager::UnprovisionServiceInstance(class Microsoft.SharePoint.Administration.SPServiceInstance serviceInstance)
0x22180a  br.s     loc_221813
0x22180c  ldloc.s  4
0x22180e  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Provision()
0x221813  ldc.i4   0x7DF4CE
0x221818  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x22181d  ldc.i4.s 0x14
0x22181f  ldstr    aConfiguringSer_0// "Configuring service instance complete: "...
0x221824  ldc.i4.1
0x221825  newarr   [mscorlib]System.Object
0x22182a  stloc.s  0x1D
0x22182c  ldloc.s  0x1D
0x22182e  ldc.i4.0
0x22182f  ldloc.s  4
0x221831  callvirt instance string [mscorlib]System.Object::ToString()
0x221836  stelem.ref
0x221837  ldloc.s  0x1D
0x221839  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x22183e  leave    loc_2218E4
0x221843  stloc.s  6
0x221845  ldc.i4.1
0x221846  stloc.0
0x221847  ldc.i4   0x7DF4CF
0x22184c  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x221851  ldloc.s  6
0x221853  ldstr    aConfiguringSer_1// "Configuring service instance failed: {0"...
0x221858  ldc.i4.1
0x221859  newarr   [mscorlib]System.Object
0x22185e  stloc.s  0x1E
0x221860  ldloc.s  0x1E
0x221862  ldc.i4.0
0x221863  ldloc.s  4
0x221865  callvirt instance string [mscorlib]System.Object::ToString()
0x22186a  stelem.ref
0x22186b  ldloc.s  0x1E
0x22186d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendExceptionTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, class [mscorlib]System.Exception ex, string output, object[] data)
0x221872  ldloc.1
0x221873  ldstr    aStrong// "<strong>"
0x221878  call     string [mscorlib]System.String::Concat(string, string)
0x22187d  stloc.1
0x22187e  ldloc.1
0x22187f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x221884  ldstr    aAdminconfigser_4// "AdminConfigServicesJob_InstanceProvisio"...
0x221889  ldc.i4.0
0x22188a  newarr   [mscorlib]System.Object
0x22188f  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x221894  ldc.i4.2
0x221895  newarr   [mscorlib]System.Object
0x22189a  stloc.s  0x1F
0x22189c  ldloc.s  0x1F
0x22189e  ldc.i4.0
0x22189f  ldloc.s  4
0x2218a1  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_DisplayName()
0x2218a6  dup
0x2218a7  brtrue.s loc_2218B1
0x2218a9  pop
0x2218aa  ldloc.s  4
0x2218ac  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_TypeName()
0x2218b1  stelem.ref
0x2218b2  ldloc.s  0x1F
0x2218b4  ldc.i4.1
0x2218b5  ldloc.s  6
0x2218b7  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2218bc  stelem.ref
0x2218bd  ldloc.s  0x1F
0x2218bf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2218c4  call     string [mscorlib]System.String::Concat(string, string)
0x2218c9  stloc.1
0x2218ca  ldloc.1
0x2218cb  ldstr    aStrong_0// "</strong>\n"
0x2218d0  ldloc.s  6
0x2218d2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2218d7  ldstr    aBrBr_0// "<br /><br />\n"
0x2218dc  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x2218e1  stloc.1
0x2218e2  leave.s  loc_2218E4
0x2218e4  ldloc.s  0x1B
0x2218e6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2218eb  brtrue   loc_221776
0x2218f0  leave.s  loc_2218FE
0x2218f2  ldloc.s  0x1B
0x2218f4  brfalse.s loc_2218FD
0x2218f6  ldloc.s  0x1B
0x2218f8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2218fd  endfinally
0x2218fe  ldc.i4   0x7DF4D0
0x221903  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x221908  ldc.i4.s 0x14
0x22190a  ldstr    aCompletedServi// "Completed service instance configuring"
0x22190f  ldnull
0x221910  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x221915  ldarg.0
0x221916  ldfld    bool Microsoft.SharePoint.Administration.SPAdminConfigServicesJob::bProvisionServiceApplications
0x22191b  brfalse  loc_221FAA
0x221920  ldc.i4   0x7DF4D1
0x221925  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x22192a  ldc.i4.s 0x14
0x22192c  ldstr    aPreparingToPro_0// "Preparing to provision service applicat"...
0x221931  ldnull
0x221932  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x221937  ldnull
0x221938  stloc.s  7
0x22193a  ldarg.0
0x22193b  ldfld    class Microsoft.SharePoint.Administration.SPManagedAccount Microsoft.SharePoint.Administration.SPAdminConfigServicesJob::ServiceAccount
0x221940  ldnull
0x221941  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x221946  brfalse.s loc_221979
0x221948  ldarg.0
0x221949  ldfld    class Microsoft.SharePoint.Administration.SPManagedAccount Microsoft.SharePoint.Administration.SPAdminConfigServicesJob::ServiceAccount
0x22194e  newobj   instance void Microsoft.SharePoint.Administration.SPProcessAccount::.ctor(class Microsoft.SharePoint.Administration.SPManagedAccount managedAccount)
0x221953  stloc.s  8
0x221955  ldloc.s  8
0x221957  ldarg.0
0x221958  call     class Microsoft.SharePoint.Administration.SPServiceProvisioningContext Microsoft.SharePoint.Administration.SPServiceProvisioningContext::EnsureContext(class Microsoft.SharePoint.Administration.SPProcessAccount applicationProcessAccount, class Microsoft.SharePoint.Administration.SPAdminConfigServicesJob adminConfigServicesJob)
0x22195d  stloc.s  7
0x22195f  ldloc.s  7
0x221961  brtrue.s loc_22199A
0x221963  ldstr    aAdminconfigser_5// "AdminConfigServicesJob_FailedToCreatePr"...
0x221968  ldc.i4.0
0x221969  newarr   [mscorlib]System.Object
0x22196e  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x221973  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x221978  throw
0x221979  call     class Microsoft.SharePoint.Administration.SPServiceProvisioningContext Microsoft.SharePoint.Administration.SPServiceProvisioningContext::EnsureDefault()
0x22197e  stloc.s  7
0x221980  ldloc.s  7
0x221982  brtrue.s loc_22199A
0x221984  ldstr    aAdminconfigser_6// "AdminConfigServicesJob_DefaultProvision"...
0x221989  ldc.i4.0
0x22198a  newarr   [mscorlib]System.Object
0x22198f  call     string Microsoft.SharePoint.SPResource::GetString(string name, object[] values)
0x221994  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x221999  throw
0x22199a  ldc.i4   0x7DF4D2
0x22199f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x2219a4  ldc.i4.s 0x14
0x2219a6  ldstr    aBeginningServi_0// "Beginning service application provision"...
0x2219ab  ldnull
0x2219ac  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2219b1  call     class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPFarm::get_LocalOrThrow()
0x2219b6  callvirt instance class Microsoft.SharePoint.Administration.SPServiceCollection Microsoft.SharePoint.Administration.SPFarm::get_Services()
0x2219bb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPService>::GetEnumerator()
0x2219c0  stloc.s  0x20
0x2219c2  br       loc_221C79
0x2219c7  ldloc.s  0x20
0x2219c9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Administration.SPService>::get_Current()
0x2219ce  stloc.s  9
0x2219d0  ldloc.s  9
0x2219d2  isinst   Microsoft.SharePoint.Administration.IServiceAdministration
0x2219d7  brfalse  loc_221BDE
0x2219dc  ldloc.s  9
0x2219de  castclass Microsoft.SharePoint.Administration.IServiceAdministration
0x2219e3  stloc.s  0xA
0x2219e5  ldloc.s  0xA
0x2219e7  callvirt instance class [mscorlib]System.Type[] Microsoft.SharePoint.Administration.IServiceAdministration::GetApplicationTypes()
0x2219ec  stloc.s  0xB
0x2219ee  ldloc.s  0xB
0x2219f0  stloc.s  0x21
0x2219f2  ldc.i4.0
0x2219f3  stloc.s  0x22
0x2219f5  br       loc_221BD3
0x2219fa  ldloc.s  0x21
0x2219fc  ldloc.s  0x22
0x2219fe  ldelem.ref
0x2219ff  stloc.s  0xC
0x221a01  ldarg.0
0x221a02  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.SharePoint.Administration.SPAdminConfigServicesJob::ServiceApplications
0x221a07  ldloc.s  0xC
0x221a09  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x221a0e  brfalse  loc_221BCD
0x221a13  ldsfld   string [mscorlib]System.String::Empty
0x221a18  stloc.s  0xD
0x221a1a  ldloc.s  0xA
0x221a1c  ldloc.s  0xC
0x221a1e  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedTypeDescription Microsoft.SharePoint.Administration.IServiceAdministration::GetApplicationTypeDescription(class [mscorlib]System.Type serviceApplicationType)
0x221a23  stloc.s  0xE
0x221a25  ldloc.s  0xE
0x221a27  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedTypeDescription::get_Name()
0x221a2c  stloc.s  0xD
0x221a2e  ldc.i4   0x7DF4D3
0x221a33  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x221a38  ldc.i4.s 0x14
0x221a3a  ldstr    aCreatingServic// "Creating service application: {0}"
0x221a3f  ldc.i4.1
0x221a40  newarr   [mscorlib]System.Object
0x221a45  stloc.s  0x23
0x221a47  ldloc.s  0x23
0x221a49  ldc.i4.0
0x221a4a  ldloc.s  0xE
0x221a4c  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedTypeDescription::get_Name()
0x221a51  stelem.ref
0x221a52  ldloc.s  0x23
0x221a54  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x221a59  ldloc.s  0xA
0x221a5b  ldloc.s  0xE
0x221a5d  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedTypeDescription::get_Name()
0x221a62  ldloc.s  0xC
0x221a64  ldloc.s  7
0x221a66  callvirt instance class Microsoft.SharePoint.Administration.SPServiceApplication Microsoft.SharePoint.Administration.IServiceAdministration::CreateApplication(string name, class [mscorlib]System.Type serviceApplicationType, class Microsoft.SharePoint.Administration.SPServiceProvisioningContext provisioningContext)
0x221a6b  stloc.s  0xF
0x221a6d  ldc.i4   0x7DF4D4
0x221a72  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x221a77  ldc.i4.s 0x14
0x221a79  ldstr    aCreatingServic_0// "Creating service application completed:"...
0x221a7e  ldc.i4.1
0x221a7f  newarr   [mscorlib]System.Object
0x221a84  stloc.s  0x24
0x221a86  ldloc.s  0x24
0x221a88  ldc.i4.0
0x221a89  ldloc.s  0xE
0x221a8b  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedTypeDescription::get_Name()
0x221a90  stelem.ref
0x221a91  ldloc.s  0x24
0x221a93  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x221a98  ldloc.s  0xF
0x221a9a  ldnull
0x221a9b  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x221aa0  brfalse  loc_221B37
0x221aa5  ldloc.s  0xF
  ... truncated ...
```
