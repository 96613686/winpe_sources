# Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::Execute

- ea: `0x3d4b0`
- end: `0x3d99f`
- name: `Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::Execute`
- size: `1263`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x242a0`
- `0x3d300`
- `0x3d310`
- `0x3d320`
- `0x3d360`
- `0x3d380`
- `0x3d3a0`
- `0x3d3c0`
- `0x3d410`
- `0x3d4b0`
- `0x3d9a0`
- `0x3d9c0`
- `0x3de30`
- `0x3de90`
- `0x3dfa0`
- `0x43cb0`

## string_xrefs

- `0x3d5bb`: `tax_InstalledLCIDs`
- `0x3d614`: `tax_InstalledLCIDs`
- `0x3d870`: `Failed to save full hidden list update time for database {0} and proxy {1}, error was {2}.`

## pseudocode

```c

```

## disassembly

```asm
0x3d4b0  ldstr    aHiddenlistfull_0// "HiddenListFullSyncJobDefinition.Execute"
0x3d4b5  ldc.i4   0x756301
0x3d4ba  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x3d4bf  ldc.i4   0x756302
0x3d4c4  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x3d4c9  ldc.i4   0x756303
0x3d4ce  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x3d4d3  ldc.i4.0
0x3d4d4  ldnull
0x3d4d5  newobj   instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor::.ctor(string, unsigned int32, unsigned int32, unsigned int32, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPLogType, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x3d4da  stloc.0
0x3d4db  ldc.i4   0x6636776B
0x3d4e0  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3d4e5  ldc.i4.s 0x32
0x3d4e7  ldstr    aHiddenListFull// "Hidden List full sync timer job starts."
0x3d4ec  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x3d4f1  ldarg.1
0x3d4f2  ldstr    aContentdatabas// "contentDatabase"
0x3d4f7  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x3d4fc  ldarg.2
0x3d4fd  ldstr    aJobstate// "jobState"
0x3d502  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::ConfirmNotNull(object value, string parameterName)
0x3d507  ldarg.1
0x3d508  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase::get_WebApplication()
0x3d50d  call     void Microsoft.SharePoint.Taxonomy.TaxonomyField::CheckAndRegisterTimerJob(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication webApplication)
0x3d512  ldarg.0
0x3d513  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x3d518  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPObjectStatus [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Status()
0x3d51d  brfalse.s loc_3D53A
0x3d51f  ldloc.0
0x3d520  ldc.i4   0x756304
0x3d525  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x3d52a  ldstr    aHiddenListFull_0// "Hidden List full sync timer job stoppin"...
0x3d52f  ldnull
0x3d530  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32, string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x3d535  leave    loc_3D99E
0x3d53a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x3d53f  stloc.1
0x3d540  ldarg.0
0x3d541  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x3d546  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::termStoresImported
0x3d54b  ldarg.0
0x3d54c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x3d551  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::serviceAppsRestored
0x3d556  ldarg.0
0x3d557  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3d55c  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::currentUpdate
0x3d561  ldarg.0
0x3d562  ldc.i4.0
0x3d563  stfld    bool Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::newDatabase
0x3d568  ldarg.1
0x3d569  ldstr    aTaxHiddenlistf// "tax_HiddenListFullSyncWorkItems4"
0x3d56e  callvirt T0x2B00005E
0x3d573  stloc.2
0x3d574  ldloc.2
0x3d575  ldnull
0x3d576  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x3d57b  brtrue.s loc_3D5A8
0x3d57d  ldloc.2
0x3d57e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.PersistedHiddenListFullSyncWorkItems::get_ServiceAppsRestored()
0x3d583  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x3d588  brtrue   loc_3D7A1
0x3d58d  ldloc.2
0x3d58e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.PersistedHiddenListFullSyncWorkItems::get_TermStoresImported()
0x3d593  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x3d598  brtrue   loc_3D7A1
0x3d59d  ldloc.2
0x3d59e  callvirt instance bool Microsoft.SharePoint.Taxonomy.PersistedHiddenListFullSyncWorkItems::get_NewDatabase()
0x3d5a3  brtrue   loc_3D7A1
0x3d5a8  ldloc.2
0x3d5a9  ldnull
0x3d5aa  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x3d5af  brfalse.s loc_3D5B8
0x3d5b1  ldarg.0
0x3d5b2  ldc.i4.1
0x3d5b3  stfld    bool Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::newDatabase
0x3d5b8  ldnull
0x3d5b9  stloc.3
0x3d5ba  ldarg.1
0x3d5bb  ldstr    aTaxInstalledlc// "tax_InstalledLCIDs"
0x3d5c0  callvirt T0x2B00005F
0x3d5c5  stloc.s  4
0x3d5c7  ldloc.s  4
0x3d5c9  ldnull
0x3d5ca  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x3d5cf  brfalse.s loc_3D63C
0x3d5d1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x3d5d6  stloc.3
0x3d5d7  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPLanguage> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::get_InstalledLanguages()
0x3d5dc  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPLanguage>::GetEnumerator()
0x3d5e1  stloc.s  0xF
0x3d5e3  br.s     loc_3D5FB
0x3d5e5  ldloca.s 0xF
0x3d5e7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.SharePoint]Microsoft.SharePoint.SPLanguage>::get_Current()
0x3d5ec  stloc.s  5
0x3d5ee  ldloc.3
0x3d5ef  ldloc.s  5
0x3d5f1  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPLanguage::get_LCID()
0x3d5f6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x3d5fb  ldloca.s 0xF
0x3d5fd  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.SharePoint]Microsoft.SharePoint.SPLanguage>::MoveNext()
0x3d602  brtrue.s loc_3D5E5
0x3d604  leave.s  loc_3D614
0x3d606  ldloca.s 0xF
0x3d608  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.SharePoint]Microsoft.SharePoint.SPLanguage>
0x3d60e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3d613  endfinally
0x3d614  ldstr    aTaxInstalledlc// "tax_InstalledLCIDs"
0x3d619  ldarg.1
0x3d61a  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3d61f  newobj   instance void Microsoft.SharePoint.Taxonomy.PersistedInstalledLCIDs::.ctor(string name, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject parent, valuetype [mscorlib]System.Guid id)
0x3d624  stloc.s  4
0x3d626  ldloc.s  4
0x3d628  ldloc.3
0x3d629  callvirt instance void Microsoft.SharePoint.Taxonomy.PersistedInstalledLCIDs::set_Lcids(class [mscorlib]System.Collections.Generic.List`1<int32> value)
0x3d62e  ldloc.s  4
0x3d630  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::Update()
0x3d635  ldarg.0
0x3d636  ldc.i4.1
0x3d637  stfld    bool Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::newDatabase
0x3d63c  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPLanguage> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::get_InstalledLanguages()
0x3d641  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPLanguage>::GetEnumerator()
0x3d646  stloc.s  0x10
0x3d648  br.s     loc_3D675
0x3d64a  ldloca.s 0x10
0x3d64c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.SharePoint]Microsoft.SharePoint.SPLanguage>::get_Current()
0x3d651  stloc.s  6
0x3d653  ldloc.s  4
0x3d655  callvirt instance class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.SharePoint.Taxonomy.PersistedInstalledLCIDs::get_Lcids()
0x3d65a  ldloc.s  6
0x3d65c  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPLanguage::get_LCID()
0x3d661  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<int32>::Contains(var<u1>)
0x3d666  brtrue.s loc_3D675
0x3d668  ldloc.1
0x3d669  ldloc.s  6
0x3d66b  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPLanguage::get_LCID()
0x3d670  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x3d675  ldloca.s 0x10
0x3d677  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.SharePoint]Microsoft.SharePoint.SPLanguage>::MoveNext()
0x3d67c  brtrue.s loc_3D64A
0x3d67e  leave.s  loc_3D68E
0x3d680  ldloca.s 0x10
0x3d682  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.SharePoint]Microsoft.SharePoint.SPLanguage>
0x3d688  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3d68d  endfinally
0x3d68e  ldarg.1
0x3d68f  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPSiteCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase::get_Sites()
0x3d694  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPBaseCollection::get_Count()
0x3d699  ldc.i4.0
0x3d69a  ble      loc_3D7D1
0x3d69f  ldarg.1
0x3d6a0  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPSiteCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase::get_Sites()
0x3d6a5  ldc.i4.0
0x3d6a6  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPSiteCollection::get_Item(int32)
0x3d6ab  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::GetContext(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite)
0x3d6b0  stloc.s  7
0x3d6b2  ldloc.s  7
0x3d6b4  ldtoken  Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy
0x3d6b9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d6be  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy> [Microsoft.SharePoint]Microsoft.SharePoint.SPServiceContext::GetProxies(class [mscorlib]System.Type)
0x3d6c3  stloc.s  8
0x3d6c5  ldloc.s  8
0x3d6c7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy>::GetEnumerator()
0x3d6cc  stloc.s  0x11
0x3d6ce  br       loc_3D787
0x3d6d3  ldloc.s  0x11
0x3d6d5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceApplicationProxy>::get_Current()
0x3d6da  castclass Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy
0x3d6df  stloc.s  9
0x3d6e1  ldc.i4   0x6636776D
0x3d6e6  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x3d6eb  ldc.i4.s 0x64
0x3d6ed  ldstr    aCheckingForTer_1// "Checking for term store restoration in "...
0x3d6f2  ldc.i4.2
0x3d6f3  newarr   [mscorlib]System.Object
0x3d6f8  stloc.s  0x12
0x3d6fa  ldloc.s  0x12
0x3d6fc  ldc.i4.0
0x3d6fd  ldarg.0
0x3d6fe  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x3d703  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x3d708  box      [mscorlib]System.Guid
0x3d70d  stelem.ref
0x3d70e  ldloc.s  0x12
0x3d710  ldc.i4.1
0x3d711  ldloc.s  9
0x3d713  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x3d718  stelem.ref
0x3d719  ldloc.s  0x12
0x3d71b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x3d720  ldarg.0
0x3d721  ldloc.s  9
0x3d723  ldarg.1
0x3d724  ldloc.1
0x3d725  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<int32>::get_Count()
0x3d72a  ldc.i4.0
0x3d72b  cgt
0x3d72d  call     instance void Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::GetTermStoreChanges(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase contentDatabase, bool forceUpdateOfAllSites)
0x3d732  leave.s  loc_3D787
0x3d734  stloc.s  0xA
0x3d736  ldloc.0
0x3d737  ldc.i4   0x756305
0x3d73c  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x3d741  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3d746  ldstr    aFailedToGetFul// "Failed to get full hidden list changes "...
0x3d74b  ldc.i4.3
0x3d74c  newarr   [mscorlib]System.Object
0x3d751  stloc.s  0x13
0x3d753  ldloc.s  0x13
0x3d755  ldc.i4.0
0x3d756  ldarg.1
0x3d757  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x3d75c  stelem.ref
0x3d75d  ldloc.s  0x13
0x3d75f  ldc.i4.1
0x3d760  ldloc.s  9
0x3d762  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x3d767  box      [mscorlib]System.Guid
0x3d76c  stelem.ref
0x3d76d  ldloc.s  0x13
0x3d76f  ldc.i4.2
0x3d770  ldloc.s  0xA
0x3d772  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3d777  stelem.ref
0x3d778  ldloc.s  0x13
0x3d77a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3d77f  ldnull
0x3d780  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(unsigned int32, string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x3d785  leave.s  loc_3D787
0x3d787  ldloc.s  0x11
0x3d789  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3d78e  brtrue   loc_3D6D3
0x3d793  leave.s  loc_3D7D1
0x3d795  ldloc.s  0x11
0x3d797  brfalse.s loc_3D7A0
0x3d799  ldloc.s  0x11
0x3d79b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3d7a0  endfinally
0x3d7a1  ldarg.0
0x3d7a2  ldloc.2
0x3d7a3  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.PersistedHiddenListFullSyncWorkItems::get_ServiceAppsRestored()
0x3d7a8  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::serviceAppsRestored
0x3d7ad  ldarg.0
0x3d7ae  ldloc.2
0x3d7af  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.PersistedHiddenListFullSyncWorkItems::get_TermStoresImported()
0x3d7b4  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::termStoresImported
0x3d7b9  ldarg.0
0x3d7ba  ldloc.2
0x3d7bb  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.Taxonomy.PersistedHiddenListFullSyncWorkItems::get_CurrentUpdate()
0x3d7c0  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::currentUpdate
0x3d7c5  ldarg.0
0x3d7c6  ldloc.2
0x3d7c7  callvirt instance bool Microsoft.SharePoint.Taxonomy.PersistedHiddenListFullSyncWorkItems::get_NewDatabase()
0x3d7cc  stfld    bool Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::newDatabase
0x3d7d1  ldarg.0
0x3d7d2  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::serviceAppsRestored
0x3d7d7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x3d7dc  ldc.i4.0
0x3d7dd  bgt.s    loc_3D7F8
0x3d7df  ldarg.0
0x3d7e0  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::termStoresImported
0x3d7e5  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x3d7ea  ldc.i4.0
0x3d7eb  bgt.s    loc_3D7F8
0x3d7ed  ldarg.0
0x3d7ee  ldfld    bool Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::newDatabase
0x3d7f3  brfalse  loc_3D917
0x3d7f8  ldarg.0
0x3d7f9  ldarg.1
0x3d7fa  ldc.i4.0
0x3d7fb  call     instance void Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::SetWorkInProgress(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase contentDatabase, bool completed)
0x3d800  ldarg.0
0x3d801  ldarg.1
0x3d802  ldarg.2
0x3d803  call     instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAllSitesJobDefinition::Execute(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobState)
0x3d808  ldarg.2
0x3d809  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobState::get_ShouldStop()
0x3d80e  brtrue   loc_3D917
0x3d813  ldarg.0
0x3d814  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::termStoresImported
0x3d819  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Clear()
0x3d81e  ldarg.0
0x3d81f  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::serviceAppsRestored
0x3d824  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Clear()
0x3d829  ldarg.0
0x3d82a  ldc.i4.0
0x3d82b  stfld    bool Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::newDatabase
0x3d830  ldarg.0
0x3d831  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::currentUpdate
0x3d836  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x3d83b  stloc.s  0x14
0x3d83d  br.s     loc_3D8B1
0x3d83f  ldloca.s 0x14
0x3d841  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x3d846  stloc.s  0xB
0x3d848  ldloc.s  0xB
0x3d84a  call     valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::GetGuidFromEntry(string entry)
0x3d84f  ldarg.1
0x3d850  ldloc.s  0xB
0x3d852  call     valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.HiddenListFullSyncJobDefinition::GetTimeFromEntry(string entry)
  ... truncated ...
```
