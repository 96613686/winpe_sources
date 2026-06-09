# Microsoft.SharePoint.Administration.SPLicenseRenewalJobDefinition::Execute

- ea: `0x2c7210`
- end: `0x2c822e`
- name: `Microsoft.SharePoint.Administration.SPLicenseRenewalJobDefinition::Execute`
- size: `4126`
- prototype: ``
- caller_count: `0`
- callee_count: `37`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1c8480`
- `0x1c8540`
- `0x1c8680`
- `0x1c8a20`
- `0x2229f0`
- `0x281150`
- `0x2c70b0`
- `0x2c70c0`
- `0x2c70d0`
- `0x2c7100`
- `0x2c7130`
- `0x2c7150`
- `0x2c71d0`
- `0x2c7210`
- `0x2c8270`
- `0x2c82f0`
- `0x2c8740`
- `0x2c87c0`
- `0x2c87e0`
- `0x31d7a0`
- `0x32cb60`
- `0x32cb80`
- `0x472c20`
- `0x6785e0`
- `0x6dba40`
- `0x6e4140`
- `0x791a30`
- `0x93dab0`
- `0x93dae0`
- `0x957990`
- `0xba2000`
- `0xba2020`
- `0xba2040`
- `0xba2140`
- `0xba2190`
- `0xba21c0`
- `0xba2360`

## string_xrefs

- `0x2c74cf`: `The timer job {0} with run ID {2} began operating on the app management service application or content database {1}`
- `0x2c75b0`: `An error has occured while trying to fetch licenses from the service database or content database bound to {0}: {1}. Skipping this service application or content database for automatic license renewal`
- `0x2c7634`: `The service database or content database bound to {0} have no licenses to renew`
- `0x2c7674`: `License renewal is completed for the service database or content database bound to {0}`
- `0x2c76ca`: `Batch number {0} is fetched from the service database or content database, including {1} licenses to be renewed`
- `0x2c7715`: `The complete list of (Product ID, Deployment ID, Purchaser ID) triples of licenses in this batch along with the associated XML token: `
- `0x2c7755`: `License Renewing: Product ID: {0} Deployment ID: {1} Purchaser ID: {2}; Token: {3}`
- `0x2c78ab`: `Office Marketplace renewal web service failed to respond successfully `
- `0x2c7a85`: `BulkImportLicense - Delete: Product ID: {0}, Deployment ID: {1}, Purchaser ID: {2}`
- `0x2c7d9a`: `The complete list of (Product ID, Deployment ID, Purchaser ID) triples of licenses that failed to be renewed: `
- `0x2c7e49`: `The complete list of (Product ID, Deployment ID, Purchaser ID) triples of licenses that are missing altogether from the licensing DB (deletion of the licenses from Manage App License UI in the middle of renewal process is a possible cause): `
- `0x2c7ef8`: `The complete list of (Product ID, Deployment ID, Purchaser ID) triples of licenses that will be retried to be renewed: `
- `0x2c80aa`: `The timer job {0} with run ID {1} is going to sleep, hence not proceeding onto the next app management service application.`
- `0x2c80ef`: `The timer job {0} with run ID {1} is proceeding onto the next app management service application`

## pseudocode

```c

```

## disassembly

```asm
0x2c7210  call     void Microsoft.SharePoint.Marketplace.SPMarketplaceSettings::CheckMarketplaceConnection()
0x2c7215  leave.s  loc_2C724A
0x2c7217  pop
0x2c7218  ldc.i4   0x25940B
0x2c721d  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppMarketplace()
0x2c7222  ldc.i4.s 0x32
0x2c7224  ldstr    aPublicSharepoi// "Public SharePoint Store is currently tu"...
0x2c7229  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2c722e  ldarg.0
0x2c722f  call     instance class Microsoft.SharePoint.Administration.SPLicenseRenewalTimerJobPersistedInformation Microsoft.SharePoint.Administration.SPLicenseRenewalJobDefinition::get_JobPersistedInformation()
0x2c7234  ldc.i4.0
0x2c7235  callvirt instance void Microsoft.SharePoint.Administration.SPLicenseRenewalTimerJobPersistedInformation::set_NumberOfSubsequentJobFailures(int32 value)
0x2c723a  ldarg.0
0x2c723b  call     instance class Microsoft.SharePoint.Administration.SPLicenseRenewalTimerJobPersistedInformation Microsoft.SharePoint.Administration.SPLicenseRenewalJobDefinition::get_JobPersistedInformation()
0x2c7240  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x2c7245  leave    loc_2C822D
0x2c724a  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x2c724f  stloc.0
0x2c7250  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2c7255  ldstr    aLicenseRenewal// "<License Renewal Timer Job Run ID {0}> "
0x2c725a  ldc.i4.1
0x2c725b  newarr   [mscorlib]System.Object
0x2c7260  stloc.s  0x31
0x2c7262  ldloc.s  0x31
0x2c7264  ldc.i4.0
0x2c7265  ldloc.0
0x2c7266  box      [mscorlib]System.Guid
0x2c726b  stelem.ref
0x2c726c  ldloc.s  0x31
0x2c726e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2c7273  stloc.1
0x2c7274  ldc.i4   0x1593D2
0x2c7279  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppMarketplace()
0x2c727e  ldc.i4.s 0x32
0x2c7280  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2c7285  ldloc.1
0x2c7286  ldstr    aTheTimerJob0Wi// "The timer job {0} with run ID {1} has s"...
0x2c728b  call     string [mscorlib]System.String::Concat(string, string)
0x2c7290  ldc.i4.2
0x2c7291  newarr   [mscorlib]System.Object
0x2c7296  stloc.s  0x32
0x2c7298  ldloc.s  0x32
0x2c729a  ldc.i4.0
0x2c729b  ldstr    aJobSpappLicens// "job-spapp-licenserenewal"
0x2c72a0  stelem.ref
0x2c72a1  ldloc.s  0x32
0x2c72a3  ldc.i4.1
0x2c72a4  ldloc.0
0x2c72a5  box      [mscorlib]System.Guid
0x2c72aa  stelem.ref
0x2c72ab  ldloc.s  0x32
0x2c72ad  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2c72b2  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2c72b7  ldnull
0x2c72b8  stloc.s  0xA
0x2c72ba  ldc.i4.0
0x2c72bb  stloc.s  0x13
0x2c72bd  ldc.i4.0
0x2c72be  stloc.s  0x14
0x2c72c0  ldc.i4.0
0x2c72c1  stloc.s  0x15
0x2c72c3  ldc.i4.0
0x2c72c4  stloc.s  0x16
0x2c72c6  ldc.i4.0
0x2c72c7  stloc.s  0x17
0x2c72c9  ldc.i4.0
0x2c72ca  stloc.s  0x18
0x2c72cc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.LicenseStore>::.ctor()
0x2c72d1  stloc.s  0x19
0x2c72d3  ldarg.0
0x2c72d4  call     instance class Microsoft.SharePoint.Administration.SPPersistedObject Microsoft.SharePoint.Administration.SPPersistedObject::get_Parent()
0x2c72d9  castclass Microsoft.SharePoint.AppManagement.AppManagementService
0x2c72de  callvirt instance class Microsoft.SharePoint.Administration.SPServiceApplicationCollection Microsoft.SharePoint.Administration.SPService::get_Applications()
0x2c72e3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPServiceApplication>::GetEnumerator()
0x2c72e8  stloc.s  0x33
0x2c72ea  br.s     loc_2C730C
0x2c72ec  ldloc.s  0x33
0x2c72ee  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Administration.SPServiceApplication>::get_Current()
0x2c72f3  castclass Microsoft.SharePoint.AppManagement.AppManagementServiceApplication
0x2c72f8  stloc.s  0x1A
0x2c72fa  ldloc.s  0x1A
0x2c72fc  newobj   instance void Microsoft.SharePoint.Administration.LicenseStore::.ctor(class Microsoft.SharePoint.AppManagement.AppManagementServiceApplication appManagementServiceApplication)
0x2c7301  stloc.s  0x1B
0x2c7303  ldloc.s  0x19
0x2c7305  ldloc.s  0x1B
0x2c7307  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.LicenseStore>::Add(var<u1>)
0x2c730c  ldloc.s  0x33
0x2c730e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2c7313  brtrue.s loc_2C72EC
0x2c7315  leave.s  loc_2C7323
0x2c7317  ldloc.s  0x33
0x2c7319  brfalse.s loc_2C7322
0x2c731b  ldloc.s  0x33
0x2c731d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c7322  endfinally
0x2c7323  call     bool Microsoft.SharePoint.SPGlobal::get_IsSPO()
0x2c7328  brfalse  loc_2C74A6
0x2c732d  ldc.i4   0x2825
0x2c7332  call     bool Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId)
0x2c7337  brfalse  loc_2C74A6
0x2c733c  ldc.i4   0x6171C1
0x2c7341  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppMarketplace()
0x2c7346  ldc.i4.s 0x32
0x2c7348  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2c734d  ldloc.1
0x2c734e  ldstr    aTheTimerJob0Wi_0// "The timer job {0} with run ID {1} is ab"...
0x2c7353  call     string [mscorlib]System.String::Concat(string, string)
0x2c7358  ldc.i4.2
0x2c7359  newarr   [mscorlib]System.Object
0x2c735e  stloc.s  0x34
0x2c7360  ldloc.s  0x34
0x2c7362  ldc.i4.0
0x2c7363  ldstr    aJobSpappLicens// "job-spapp-licenserenewal"
0x2c7368  stelem.ref
0x2c7369  ldloc.s  0x34
0x2c736b  ldc.i4.1
0x2c736c  ldloc.0
0x2c736d  box      [mscorlib]System.Guid
0x2c7372  stelem.ref
0x2c7373  ldloc.s  0x34
0x2c7375  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2c737a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2c737f  call     class Microsoft.SharePoint.Administration.SPWebService Microsoft.SharePoint.Administration.SPWebService::get_ContentService()
0x2c7384  callvirt instance class Microsoft.SharePoint.Administration.SPWebApplicationCollection Microsoft.SharePoint.Administration.SPWebService::get_WebApplications()
0x2c7389  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPWebApplication>::GetEnumerator()
0x2c738e  stloc.s  0x35
0x2c7390  br       loc_2C748C
0x2c7395  ldloc.s  0x35
0x2c7397  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Administration.SPWebApplication>::get_Current()
0x2c739c  stloc.s  0x1C
0x2c739e  ldc.i4   0x6171C2
0x2c73a3  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppMarketplace()
0x2c73a8  ldc.i4.s 0x32
0x2c73aa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2c73af  ldloc.1
0x2c73b0  ldstr    aTheTimerJob0Wi_1// "The timer job {0} with run ID {1} will "...
0x2c73b5  call     string [mscorlib]System.String::Concat(string, string)
0x2c73ba  ldc.i4.3
0x2c73bb  newarr   [mscorlib]System.Object
0x2c73c0  stloc.s  0x36
0x2c73c2  ldloc.s  0x36
0x2c73c4  ldc.i4.0
0x2c73c5  ldstr    aJobSpappLicens// "job-spapp-licenserenewal"
0x2c73ca  stelem.ref
0x2c73cb  ldloc.s  0x36
0x2c73cd  ldc.i4.1
0x2c73ce  ldloc.0
0x2c73cf  box      [mscorlib]System.Guid
0x2c73d4  stelem.ref
0x2c73d5  ldloc.s  0x36
0x2c73d7  ldc.i4.2
0x2c73d8  ldloc.s  0x1C
0x2c73da  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x2c73df  box      [mscorlib]System.Guid
0x2c73e4  stelem.ref
0x2c73e5  ldloc.s  0x36
0x2c73e7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2c73ec  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2c73f1  ldloc.s  0x1C
0x2c73f3  callvirt instance class Microsoft.SharePoint.Administration.SPContentDatabaseCollection Microsoft.SharePoint.Administration.SPWebApplication::get_ContentDatabases()
0x2c73f8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Administration.SPContentDatabase> Microsoft.SharePoint.Administration.SPContentDatabaseCollection::GetEnumerator()
0x2c73fd  stloc.s  0x37
0x2c73ff  br.s     loc_2C7475
0x2c7401  ldloc.s  0x37
0x2c7403  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Administration.SPContentDatabase>::get_Current()
0x2c7408  stloc.s  0x1D
0x2c740a  ldc.i4   0x6171C3
0x2c740f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppMarketplace()
0x2c7414  ldc.i4.s 0x32
0x2c7416  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2c741b  ldloc.1
0x2c741c  ldstr    aTheTimerJob0Wi_2// "The timer job {0} with run ID {1} will "...
0x2c7421  call     string [mscorlib]System.String::Concat(string, string)
0x2c7426  ldc.i4.4
0x2c7427  newarr   [mscorlib]System.Object
0x2c742c  stloc.s  0x38
0x2c742e  ldloc.s  0x38
0x2c7430  ldc.i4.0
0x2c7431  ldstr    aJobSpappLicens// "job-spapp-licenserenewal"
0x2c7436  stelem.ref
0x2c7437  ldloc.s  0x38
0x2c7439  ldc.i4.1
0x2c743a  ldloc.0
0x2c743b  box      [mscorlib]System.Guid
0x2c7440  stelem.ref
0x2c7441  ldloc.s  0x38
0x2c7443  ldc.i4.2
0x2c7444  ldloc.s  0x1D
0x2c7446  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x2c744b  stelem.ref
0x2c744c  ldloc.s  0x38
0x2c744e  ldc.i4.3
0x2c744f  ldloc.s  0x1C
0x2c7451  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x2c7456  stelem.ref
0x2c7457  ldloc.s  0x38
0x2c7459  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2c745e  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2c7463  ldloc.s  0x1D
0x2c7465  newobj   instance void Microsoft.SharePoint.Administration.LicenseStore::.ctor(class Microsoft.SharePoint.Administration.SPContentDatabase contentDatabase)
0x2c746a  stloc.s  0x1E
0x2c746c  ldloc.s  0x19
0x2c746e  ldloc.s  0x1E
0x2c7470  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.LicenseStore>::Add(var<u1>)
0x2c7475  ldloc.s  0x37
0x2c7477  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2c747c  brtrue.s loc_2C7401
0x2c747e  leave.s  loc_2C748C
0x2c7480  ldloc.s  0x37
0x2c7482  brfalse.s loc_2C748B
0x2c7484  ldloc.s  0x37
0x2c7486  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c748b  endfinally
0x2c748c  ldloc.s  0x35
0x2c748e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2c7493  brtrue   loc_2C7395
0x2c7498  leave.s  loc_2C74A6
0x2c749a  ldloc.s  0x35
0x2c749c  brfalse.s loc_2C74A5
0x2c749e  ldloc.s  0x35
0x2c74a0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c74a5  endfinally
0x2c74a6  ldloc.s  0x19
0x2c74a8  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.LicenseStore>::GetEnumerator()
0x2c74ad  stloc.s  0x39
0x2c74af  br       loc_2C8120
0x2c74b4  ldloca.s 0x39
0x2c74b6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Administration.LicenseStore>::get_Current()
0x2c74bb  stloc.s  0x1F
0x2c74bd  ldc.i4   0x1593D3
0x2c74c2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AppMarketplace()
0x2c74c7  ldc.i4.s 0x32
0x2c74c9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2c74ce  ldloc.1
0x2c74cf  ldstr    aTheTimerJob0Wi_3// "The timer job {0} with run ID {2} began"...
0x2c74d4  call     string [mscorlib]System.String::Concat(string, string)
0x2c74d9  ldc.i4.3
0x2c74da  newarr   [mscorlib]System.Object
0x2c74df  stloc.s  0x3A
0x2c74e1  ldloc.s  0x3A
0x2c74e3  ldc.i4.0
0x2c74e4  ldstr    aJobSpappLicens// "job-spapp-licenserenewal"
0x2c74e9  stelem.ref
0x2c74ea  ldloc.s  0x3A
0x2c74ec  ldc.i4.1
0x2c74ed  ldloc.s  0x1F
0x2c74ef  callvirt instance string Microsoft.SharePoint.Administration.LicenseStore::get_DisplayName()
0x2c74f4  stelem.ref
0x2c74f5  ldloc.s  0x3A
0x2c74f7  ldc.i4.2
0x2c74f8  ldloc.0
0x2c74f9  box      [mscorlib]System.Guid
0x2c74fe  stelem.ref
0x2c74ff  ldloc.s  0x3A
0x2c7501  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2c7506  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x2c750b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2c7510  stloc.2
0x2c7511  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2c7516  stloc.3
0x2c7517  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2c751c  stloc.s  4
0x2c751e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::.ctor()
0x2c7523  stloc.s  9
0x2c7525  ldc.i4.0
0x2c7526  stloc.s  0x21
0x2c7528  ldc.i4.0
0x2c7529  stloc.s  0x22
0x2c752b  br       loc_2C808D
0x2c7530  ldloc.s  0x1F
0x2c7532  ldloc.s  4
0x2c7534  stloc.s  0x3B
0x2c7536  ldloc.3
0x2c7537  stloc.s  0x3C
0x2c7539  ldloc.2
0x2c753a  ldloc.s  0x3C
0x2c753c  ldloc.s  0x3B
0x2c753e  ldarg.0
0x2c753f  call     instance class Microsoft.SharePoint.Administration.SPLicenseRenewalTimerJobPersistedInformation Microsoft.SharePoint.Administration.SPLicenseRenewalJobDefinition::get_JobPersistedInformation()
0x2c7544  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Administration.SPLicenseRenewalTimerJobPersistedInformation::get_MappingsTickets()
0x2c7549  ldloc.s  0x1F
0x2c754b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.LicenseStore::get_Id()
0x2c7550  ldloca.s 8
0x2c7552  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::TryGetValue(var<u1>, !!T0)
0x2c7557  brtrue.s loc_2C7560
0x2c7559  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2c755e  br.s     loc_2C7562
0x2c7560  ldloc.s  8
0x2c7562  ldloca.s 0x20
0x2c7564  callvirt instance class Microsoft.SharePoint.SPAppLicenseCollection Microsoft.SharePoint.Administration.LicenseStore::AcquireEntitlementsForRenewal(valuetype [mscorlib]System.Guid startingTenantId, valuetype [mscorlib]System.Guid startingProductId, valuetype [mscorlib]System.Guid startingLicenseId, valuetype [mscorlib]System.Guid retrialMappingsTicket, [out] valuetype [mscorlib]System.Guid& mappingsTicket)
0x2c7569  stloc.s  0xA
0x2c756b  ldarg.0
0x2c756c  call     instance class Microsoft.SharePoint.Administration.SPLicenseRenewalTimerJobPersistedInformation Microsoft.SharePoint.Administration.SPLicenseRenewalJobDefinition::get_JobPersistedInformation()
0x2c7571  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Administration.SPLicenseRenewalTimerJobPersistedInformation::get_MappingsTickets()
0x2c7576  ldloc.s  0x1F
0x2c7578  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.LicenseStore::get_Id()
0x2c757d  ldloc.s  0x20
0x2c757f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::set_Item(var<u1>, !!T0)
0x2c7584  leave.s  loc_2C75EE
0x2c7586  stloc.s  0x23
  ... truncated ...
```
