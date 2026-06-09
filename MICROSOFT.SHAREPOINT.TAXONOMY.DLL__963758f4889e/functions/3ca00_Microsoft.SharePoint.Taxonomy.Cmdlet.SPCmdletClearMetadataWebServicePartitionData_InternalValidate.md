# Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletClearMetadataWebServicePartitionData::InternalValidate

- ea: `0x3ca00`
- end: `0x3cb3c`
- name: `Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletClearMetadataWebServicePartitionData::InternalValidate`
- size: `316`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x2acd0`
- `0x3c960`
- `0x3c9a0`
- `0x3c9c0`
- `0x3c9e0`
- `0x3ca00`
- `0x660a0`

## string_xrefs

- `0x3ca20`: `ErrorNonexistingServiceApplication`
- `0x3ca54`: `ServiceContext`

## pseudocode

```c

```

## disassembly

```asm
0x3ca00  ldarg.0
0x3ca01  ldarg.0
0x3ca02  ldfld    class Microsoft.SharePoint.Taxonomy.Cmdlet.SPMetadataServiceProxyCmdletPipeBind Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletClearMetadataWebServicePartitionData::serviceProxyBind
0x3ca07  callvirt instance var<u1> class [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPCmdletPipeBind`1<class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy>::Read()
0x3ca0c  stfld    class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletClearMetadataWebServicePartitionData::metadataServiceProxy
0x3ca11  ldarg.0
0x3ca12  ldfld    class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletClearMetadataWebServicePartitionData::metadataServiceProxy
0x3ca17  ldnull
0x3ca18  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x3ca1d  brfalse.s loc_3CA3C
0x3ca1f  ldarg.0
0x3ca20  ldstr    aErrornonexisti// "ErrorNonexistingServiceApplication"
0x3ca25  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3ca2a  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3ca2f  ldc.i4.5
0x3ca30  ldarg.0
0x3ca31  call     instance void [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPCmdlet::WriteError(class [mscorlib]System.Exception, valuetype [System.Management.Automation]System.Management.Automation.ErrorCategory, object)
0x3ca36  ldarg.0
0x3ca37  call     instance void [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPCmdlet::SkipProcessCurrentRecord()
0x3ca3c  ldarg.0
0x3ca3d  call     instance string [System.Management.Automation]System.Management.Automation.PSCmdlet::get_ParameterSetName()
0x3ca42  dup
0x3ca43  stloc.3
0x3ca44  brfalse.s loc_3CA9F
0x3ca46  ldloc.3
0x3ca47  ldstr    aDefault// "Default"
0x3ca4c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3ca51  brtrue.s loc_3CA62
0x3ca53  ldloc.3
0x3ca54  ldstr    aServicecontext_0// "ServiceContext"
0x3ca59  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3ca5e  brtrue.s loc_3CA82
0x3ca60  br.s     loc_3CA9F
0x3ca62  ldarg.0
0x3ca63  call     instance class [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPSiteSubscriptionPipeBind Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletClearMetadataWebServicePartitionData::get_Identity()
0x3ca68  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPSiteSubscriptionPipeBind::Read()
0x3ca6d  stloc.0
0x3ca6e  ldarg.0
0x3ca6f  ldarg.0
0x3ca70  ldfld    class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletClearMetadataWebServicePartitionData::metadataServiceProxy
0x3ca75  ldloc.0
0x3ca76  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetRawPartitionId(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscription siteSubscription)
0x3ca7b  stfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletClearMetadataWebServicePartitionData::rawPartitionId
0x3ca80  br.s     loc_3CA9F
0x3ca82  ldarg.0
0x3ca83  call     instance class [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPServiceContextPipeBind Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletClearMetadataWebServicePartitionData::get_ServiceContext()
0x3ca88  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPServiceContextPipeBind::Read()
0x3ca8d  stloc.1
0x3ca8e  ldarg.0
0x3ca8f  ldloc.1
0x3ca90  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscriptionIdentifier [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::get_SiteSubscriptionId()
0x3ca95  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPSiteSubscriptionIdentifier::get_Id()
0x3ca9a  stfld    valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletClearMetadataWebServicePartitionData::rawPartitionId
0x3ca9f  ldarg.0
0x3caa0  call     instance class [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPContentDatabasePipeBind Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletClearMetadataWebServicePartitionData::get_FromContentDatabase()
0x3caa5  brfalse.s loc_3CB1A
0x3caa7  ldarg.0
0x3caa8  call     instance valuetype [System.Management.Automation]System.Management.Automation.SwitchParameter Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletClearMetadataWebServicePartitionData::get_FromServiceDatabase()
0x3caad  stloc.s  4
0x3caaf  ldloca.s 4
0x3cab1  call     instance bool [System.Management.Automation]System.Management.Automation.SwitchParameter::get_IsPresent()
0x3cab6  brfalse.s loc_3CAD5
0x3cab8  ldarg.0
0x3cab9  ldstr    aErrorcmdletspe// "ErrorCmdletSpecifiedBothDatabaseParams"
0x3cabe  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3cac3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3cac8  ldc.i4.5
0x3cac9  ldarg.0
0x3caca  call     instance void [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPCmdlet::WriteError(class [mscorlib]System.Exception, valuetype [System.Management.Automation]System.Management.Automation.ErrorCategory, object)
0x3cacf  ldarg.0
0x3cad0  call     instance void [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPCmdlet::SkipProcessCurrentRecord()
0x3cad5  ldarg.0
0x3cad6  call     instance class [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPContentDatabasePipeBind Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletClearMetadataWebServicePartitionData::get_FromContentDatabase()
0x3cadb  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPContentDatabasePipeBind::Read()
0x3cae0  stloc.2
0x3cae1  ldloc.2
0x3cae2  ldnull
0x3cae3  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x3cae8  brfalse.s loc_3CB08
0x3caea  ldarg.0
0x3caeb  ldstr    aErrorcmdletcan// "ErrorCmdletCannotFindContentDatabase"
0x3caf0  call     string Microsoft.SharePoint.Taxonomy.Internal.Resources::GetString(string resourceName)
0x3caf5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3cafa  ldc.i4.5
0x3cafb  ldarg.0
0x3cafc  call     instance void [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPCmdlet::WriteError(class [mscorlib]System.Exception, valuetype [System.Management.Automation]System.Management.Automation.ErrorCategory, object)
0x3cb01  ldarg.0
0x3cb02  call     instance void [Microsoft.SharePoint.PowerShell]Microsoft.SharePoint.PowerShell.SPCmdlet::SkipProcessCurrentRecord()
0x3cb07  ret
0x3cb08  ldarg.0
0x3cb09  ldloc.2
0x3cb0a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x3cb0f  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x3cb14  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletClearMetadataWebServicePartitionData::contentDatabaseId
0x3cb19  ret
0x3cb1a  ldarg.0
0x3cb1b  call     instance valuetype [System.Management.Automation]System.Management.Automation.SwitchParameter Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletClearMetadataWebServicePartitionData::get_FromServiceDatabase()
0x3cb20  stloc.s  5
0x3cb22  ldloca.s 5
0x3cb24  call     instance bool [System.Management.Automation]System.Management.Automation.SwitchParameter::get_IsPresent()
0x3cb29  brfalse.s loc_3CB3B
0x3cb2b  ldarg.0
0x3cb2c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3cb31  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x3cb36  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.Cmdlet.SPCmdletClearMetadataWebServicePartitionData::contentDatabaseId
0x3cb3b  ret
```
