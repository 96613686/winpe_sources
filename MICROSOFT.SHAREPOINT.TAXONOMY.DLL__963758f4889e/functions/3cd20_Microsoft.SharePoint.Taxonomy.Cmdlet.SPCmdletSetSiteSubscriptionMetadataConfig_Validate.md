# Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletSetSiteSubscriptionMetadataConfig::Validate

- ea: `0x3cd20`
- end: `0x3cdf7`
- name: `Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletSetSiteSubscriptionMetadataConfig::Validate`
- size: `215`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3cd10`
- `0x3cfc0`

## callees

- `0x25a60`
- `0x2ad40`
- `0x3cd20`
- `0x3cf10`
- `0x3d000`
- `0x3d020`

## string_xrefs

- `0x3cd53`: `SPCmdletSetSiteSubscriptionMetadataConfig: SPMetadataServiceProxy is null.`
- `0x3cd88`: `SPCmdletSetSiteSubscriptionMetadataConfig: [{0}] is not a valid Hub Url.`
- `0x3cde9`: `SPCmdletSetSiteSubscriptionMetadataConfig: ShouldProcessHubUrlChange is false.`

## pseudocode

```c

```

## disassembly

```asm
0x3cd20  ldarg.0
0x3cd21  call     instance class Microsoft.SharePoint.Taxonomy.Cmdlet.SPMetadataServiceProxyCmdletPipeBind Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletSetSiteSubscriptionMetadataConfig::get_ServiceProxy()
0x3cd26  brfalse.s loc_3CD39
0x3cd28  ldarg.0
0x3cd29  ldarg.0
0x3cd2a  call     instance class Microsoft.SharePoint.Taxonomy.Cmdlet.SPMetadataServiceProxyCmdletPipeBind Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletSetSiteSubscriptionMetadataConfig::get_ServiceProxy()
0x3cd2f  callvirt instance var<u1> class [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPCmdletPipeBind`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>::Read()
0x3cd34  call     instance void class [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPSetCmdletBase`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>::set_DataObject(var<u1>)
0x3cd39  ldnull
0x3cd3a  ldarg.0
0x3cd3b  call     instance var<u1> class [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPSetCmdletBase`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>::get_DataObject()
0x3cd40  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x3cd45  brfalse.s loc_3CD5F
0x3cd47  ldc.i4   0x7DE555
0x3cd4c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3cd51  ldc.i4.s 0x32
0x3cd53  ldstr    aSpcmdletsetsit// "SPCmdletSetSiteSubscriptionMetadataConf"...
0x3cd58  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x3cd5d  ldc.i4.0
0x3cd5e  ret
0x3cd5f  ldarg.0
0x3cd60  call     instance string Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletSetSiteSubscriptionMetadataConfig::get_HubUri()
0x3cd65  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3cd6a  brtrue   loc_3CDF5
0x3cd6f  ldarg.0
0x3cd70  call     instance string Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletSetSiteSubscriptionMetadataConfig::get_HubUri()
0x3cd75  call     bool Microsoft.SharePoint.Taxonomy.Internal.CommonValidator::IsValidHubUrl(string urlString)
0x3cd7a  brtrue.s loc_3CDD5
0x3cd7c  ldc.i4   0x7DE556
0x3cd81  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3cd86  ldc.i4.s 0x14
0x3cd88  ldstr    aSpcmdletsetsit_0// "SPCmdletSetSiteSubscriptionMetadataConf"...
0x3cd8d  ldc.i4.1
0x3cd8e  newarr   [mscorlib]System.Object
0x3cd93  stloc.0
0x3cd94  ldloc.0
0x3cd95  ldc.i4.0
0x3cd96  ldarg.0
0x3cd97  call     instance string Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletSetSiteSubscriptionMetadataConfig::get_HubUri()
0x3cd9c  stelem.ref
0x3cd9d  ldloc.0
0x3cd9e  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x3cda3  ldarg.0
0x3cda4  call     instance class [System.Management.Automation]System.Management.Automation.Host.PSHost [System.Management.Automation]System.Management.Automation.PSCmdlet::get_Host()
0x3cda9  brfalse.s loc_3CDD3
0x3cdab  ldarg.0
0x3cdac  ldstr    aErrorinvalidhu// "ErrorInvalidHubUrl"
0x3cdb1  ldc.i4.1
0x3cdb2  newarr   [mscorlib]System.Object
0x3cdb7  stloc.1
0x3cdb8  ldloc.1
0x3cdb9  ldc.i4.0
0x3cdba  ldarg.0
0x3cdbb  call     instance string Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletSetSiteSubscriptionMetadataConfig::get_HubUri()
0x3cdc0  stelem.ref
0x3cdc1  ldloc.1
0x3cdc2  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetFormattedString(string resourceName, object[] args)
0x3cdc7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3cdcc  ldc.i4.5
0x3cdcd  ldarg.0
0x3cdce  call     instance void [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPCmdlet::WriteError(class [mscorlib]System.Exception, valuetype [System.Management.Automation]System.Management.Automation.ErrorCategory, object)
0x3cdd3  ldc.i4.0
0x3cdd4  ret
0x3cdd5  ldarg.0
0x3cdd6  call     instance bool Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletSetSiteSubscriptionMetadataConfig::ShouldProcessHubUrlChange()
0x3cddb  brtrue.s loc_3CDF5
0x3cddd  ldc.i4   0x7DE557
0x3cde2  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3cde7  ldc.i4.s 0x32
0x3cde9  ldstr    aSpcmdletsetsit_1// "SPCmdletSetSiteSubscriptionMetadataConf"...
0x3cdee  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x3cdf3  ldc.i4.0
0x3cdf4  ret
0x3cdf5  ldc.i4.1
0x3cdf6  ret
```
