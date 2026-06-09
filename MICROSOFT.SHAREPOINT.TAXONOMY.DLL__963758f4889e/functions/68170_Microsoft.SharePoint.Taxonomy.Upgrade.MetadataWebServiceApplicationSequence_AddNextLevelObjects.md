# Microsoft.SharePoint.Taxonomy.Upgrade.MetadataWebServiceApplicationSequence::AddNextLevelObjects

- ea: `0x68170`
- end: `0x68228`
- name: `Microsoft.SharePoint.Taxonomy.Upgrade.MetadataWebServiceApplicationSequence::AddNextLevelObjects`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x64b50`
- `0x68140`
- `0x68170`

## string_xrefs

- `0x68180`: `CheckTaxonomyDBBeforeAdding`
- `0x681b8`: `MetadataWebServiceApplicationSequence: Adding Metadata Application Database to the hierarchy tree. Metadata service application name : {0}`
- `0x68200`: `MetadataWebServiceApplicationSequence: Unable to add MetadataWebServiceApplication.Database to the hierarchy, either MetadataWebServiceApplication or MetadataWebServiceApplication.Database is null`

## pseudocode

```c

```

## disassembly

```asm
0x68170  ldarg.0
0x68171  call     instance void [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPSequence::AddNextLevelObjects()
0x68176  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Upgrade.MetadataWebServiceApplicationSequence::dbCheckKillSwitch
0x6817b  ldstr    a4192018// "4/19/2018"
0x68180  ldstr    aChecktaxonomyd// "CheckTaxonomyDBBeforeAdding"
0x68185  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x6818a  brtrue.s loc_6820B
0x6818c  ldarg.0
0x6818d  call     instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication Microsoft.SharePoint.Taxonomy.Upgrade.MetadataWebServiceApplicationSequence::get_metadataApplication()
0x68192  ldnull
0x68193  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x68198  brfalse.s loc_681F5
0x6819a  ldarg.0
0x6819b  call     instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication Microsoft.SharePoint.Taxonomy.Upgrade.MetadataWebServiceApplicationSequence::get_metadataApplication()
0x681a0  callvirt instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_Database()
0x681a5  ldnull
0x681a6  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x681ab  brfalse.s loc_681F5
0x681ad  ldarg.0
0x681ae  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPLog [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPDelegate::get_Log()
0x681b3  ldc.i4   0x234409D
0x681b8  ldstr    aMetadatawebser_70// "MetadataWebServiceApplicationSequence: "...
0x681bd  ldc.i4.1
0x681be  newarr   [mscorlib]System.Object
0x681c3  stloc.0
0x681c4  ldloc.0
0x681c5  ldc.i4.0
0x681c6  ldarg.0
0x681c7  call     instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication Microsoft.SharePoint.Taxonomy.Upgrade.MetadataWebServiceApplicationSequence::get_metadataApplication()
0x681cc  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x681d1  stelem.ref
0x681d2  ldloc.0
0x681d3  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32, string, object[])
0x681d8  ldarg.0
0x681d9  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPHierarchyManager [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPSequence::get_HierarchyManager()
0x681de  ldarg.0
0x681df  call     instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication Microsoft.SharePoint.Taxonomy.Upgrade.MetadataWebServiceApplicationSequence::get_metadataApplication()
0x681e4  ldarg.0
0x681e5  call     instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication Microsoft.SharePoint.Taxonomy.Upgrade.MetadataWebServiceApplicationSequence::get_metadataApplication()
0x681ea  callvirt instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_Database()
0x681ef  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPHierarchyManager::AddNextLevelObject(object, object)
0x681f4  ret
0x681f5  ldarg.0
0x681f6  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPLog [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPDelegate::get_Log()
0x681fb  ldc.i4   0x234409E
0x68200  ldstr    aMetadatawebser_71// "MetadataWebServiceApplicationSequence: "...
0x68205  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPLog::WarningTag(unsigned int32, string)
0x6820a  ret
0x6820b  ldarg.0
0x6820c  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPHierarchyManager [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPSequence::get_HierarchyManager()
0x68211  ldarg.0
0x68212  call     instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication Microsoft.SharePoint.Taxonomy.Upgrade.MetadataWebServiceApplicationSequence::get_metadataApplication()
0x68217  ldarg.0
0x68218  call     instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication Microsoft.SharePoint.Taxonomy.Upgrade.MetadataWebServiceApplicationSequence::get_metadataApplication()
0x6821d  callvirt instance class Microsoft.SharePoint.Taxonomy.MetadataWebServiceDatabase Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplication::get_Database()
0x68222  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Upgrade.SPHierarchyManager::AddNextLevelObject(object, object)
0x68227  ret
```
