# Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::GetTermstoreChanges

- ea: `0x47430`
- end: `0x479e9`
- name: `Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::GetTermstoreChanges`
- size: `1465`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x47a50`

## callees

- `0x38f30`
- `0x38f40`
- `0x46c60`
- `0x46d10`
- `0x46ec0`
- `0x46f20`
- `0x47430`
- `0x47a20`
- `0x66880`

## string_xrefs

- `0x474fd`: `QueryChangesInTaxonomyExtension`
- `0x475ea`: `UpdateHiddenListJob: Error getting taxonomy changes in content database {0}. Database will be skipped.`
- `0x47628`: `CleanupChangesInTaxonomyExtension`
- `0x4767a`: `UpdateHiddenListJob: Error cleaning up taxonomy changes in content database {0}. Database will be skipped.`

## pseudocode

```c

```

## disassembly

```asm
0x47430  ldarg.3
0x47431  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>>>::.ctor()
0x47436  stind.ref
0x47437  ldarg.0
0x47438  ldarg.2
0x47439  call     instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::GetLastServiceDatabaseUpdate(valuetype [mscorlib]System.Guid allPartitionTermStoreId)
0x4743e  stloc.0
0x4743f  ldarg.s  4
0x47441  ldloc.0
0x47442  stobj    [mscorlib]System.DateTime
0x47447  ldloc.0
0x47448  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x4744d  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x47452  brfalse.s loc_4746C
0x47454  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x47459  stloc.s  0x1B
0x4745b  ldloca.s 0x1B
0x4745d  ldc.r8   -1.0
0x47466  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x4746b  stloc.0
0x4746c  ldarg.1
0x4746d  ldloc.0
0x4746e  ldarg.0
0x4746f  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x47474  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x47479  ldloca.s 1
0x4747b  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.DictionaryEntry> Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::GetChanges(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy, valuetype [mscorlib]System.DateTime sinceTime, valuetype [mscorlib]System.Guid webAppId, [out] valuetype [mscorlib]System.DateTime& lastStoreChangeTime)
0x47480  stloc.2
0x47481  ldc.i4   0x2A32
0x47486  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x4748b  stloc.3
0x4748c  ldloc.3
0x4748d  brfalse.s loc_47499
0x4748f  ldarg.s  5
0x47491  ldloc.1
0x47492  stobj    [mscorlib]System.DateTime
0x47497  br.s     loc_474A5
0x47499  ldarg.s  5
0x4749b  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x474a0  stobj    [mscorlib]System.DateTime
0x474a5  ldarg.1
0x474a6  callvirt instance bool Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy::GetIsServiceDataMapEnabled()
0x474ab  brfalse  loc_476D2
0x474b0  ldc.i4.s 0x40
0x474b2  ldc.i4.0
0x474b3  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPServiceDataMap::GetAllServiceDataDsn(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.ServiceExtensionType, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.ServiceExtensionOption)
0x474b8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase>::GetEnumerator()
0x474bd  stloc.s  0x1C
0x474bf  br       loc_476B8
0x474c4  ldloc.s  0x1C
0x474c6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase>::get_Current()
0x474cb  stloc.s  4
0x474cd  ldc.i4   0x6DE289
0x474d2  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x474d7  ldc.i4.s 0x64
0x474d9  ldstr    aContentDatabas// "Content database {0} is a taxonomy mapp"...
0x474de  ldc.i4.1
0x474df  newarr   [mscorlib]System.Object
0x474e4  stloc.s  0x1D
0x474e6  ldloc.s  0x1D
0x474e8  ldc.i4.0
0x474e9  ldloc.s  4
0x474eb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x474f0  box      [mscorlib]System.Guid
0x474f5  stelem.ref
0x474f6  ldloc.s  0x1D
0x474f8  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x474fd  ldstr    aQuerychangesin// "QueryChangesInTaxonomyExtension"
0x47502  ldc.i4   0x6DE28A
0x47507  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x4750c  ldc.i4   0x6DE28B
0x47511  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x47516  ldc.i4   0x6DE28C
0x4751b  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x47520  ldc.i4.0
0x47521  ldnull
0x47522  newobj   instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor::.ctor(string, unsigned int32, unsigned int32, unsigned int32, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPLogType, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x47527  stloc.s  5
0x47529  ldarg.1
0x4752a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x4752f  ldloc.s  4
0x47531  call     valuetype [mscorlib]System.DateTime Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::GetLastContentDatabaseUpdate(valuetype [mscorlib]System.Guid proxyId, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase contentDatabase)
0x47536  stloc.s  6
0x47538  ldloc.s  6
0x4753a  stloc.s  7
0x4753c  ldloc.s  6
0x4753e  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x47543  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x47548  brfalse.s loc_47563
0x4754a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4754f  stloc.s  0x1E
0x47551  ldloca.s 0x1E
0x47553  ldc.r8   -1.0
0x4755c  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x47561  stloc.s  6
0x47563  ldloc.s  4
0x47565  ldarg.1
0x47566  ldloc.s  6
0x47568  ldarg.0
0x47569  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPJobDefinition::get_WebApplication()
0x4756e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x47573  ldloca.s 8
0x47575  call     class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.DictionaryEntry> Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::GetChangesForDatabase(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase database, class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy, valuetype [mscorlib]System.DateTime sinceTime, valuetype [mscorlib]System.Guid webAppId, [out] valuetype [mscorlib]System.DateTime& lastStoreChangeTime)
0x4757a  stloc.s  9
0x4757c  ldloc.3
0x4757d  brfalse.s loc_4758C
0x4757f  ldloc.s  8
0x47581  ldloc.s  7
0x47583  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x47588  stloc.s  0xA
0x4758a  br.s     loc_47598
0x4758c  ldloc.s  9
0x4758e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.DictionaryEntry>::get_Count()
0x47593  ldc.i4.0
0x47594  cgt
0x47596  stloc.s  0xA
0x47598  ldloc.s  0xA
0x4759a  brfalse.s loc_475B7
0x4759c  ldarg.0
0x4759d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase, valuetype [mscorlib]System.DateTime>> Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::contentDatabaseLastUpdateTimes
0x475a2  ldloc.s  4
0x475a4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x475a9  ldloc.s  4
0x475ab  ldloc.s  8
0x475ad  newobj   instance void class [mscorlib]System.Tuple`2<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase, valuetype [mscorlib]System.DateTime>::.ctor(var<u1>, !!T0)
0x475b2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase, valuetype [mscorlib]System.DateTime>>::Add(var<u1>, !!T0)
0x475b7  ldloc.2
0x475b8  ldloc.s  9
0x475ba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.DictionaryEntry>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x475bf  ldloc.s  5
0x475c1  ldnull
0x475c2  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::Success(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x475c7  leave.s  loc_4761A
0x475c9  stloc.s  0xB
0x475cb  ldarg.0
0x475cc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase, valuetype [mscorlib]System.DateTime>> Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::contentDatabaseLastUpdateTimes
0x475d1  ldloc.s  4
0x475d3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x475d8  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Tuple`2<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPContentDatabase, valuetype [mscorlib]System.DateTime>>::Remove(var<u1>)
0x475dd  pop
0x475de  ldc.i4   0x6DE28D
0x475e3  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x475e8  ldloc.s  0xB
0x475ea  ldstr    aUpdatehiddenli_4// "UpdateHiddenListJob: Error getting taxo"...
0x475ef  ldc.i4.1
0x475f0  newarr   [mscorlib]System.Object
0x475f5  stloc.s  0x1F
0x475f7  ldloc.s  0x1F
0x475f9  ldc.i4.0
0x475fa  ldloc.s  4
0x475fc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x47601  box      [mscorlib]System.Guid
0x47606  stelem.ref
0x47607  ldloc.s  0x1F
0x47609  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, class [mscorlib]System.Exception, string, object[])
0x4760e  ldloc.s  5
0x47610  ldloc.s  0xB
0x47612  ldnull
0x47613  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(class [mscorlib]System.Exception, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x47618  leave.s  loc_4761A
0x4761a  leave.s  loc_47628
0x4761c  ldloc.s  5
0x4761e  brfalse.s loc_47627
0x47620  ldloc.s  5
0x47622  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x47627  endfinally
0x47628  ldstr    aCleanupchanges// "CleanupChangesInTaxonomyExtension"
0x4762d  ldc.i4   0x6DE28E
0x47632  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x47637  ldc.i4   0x6DE28F
0x4763c  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x47641  ldc.i4   0x6DE290
0x47646  call     unsigned int32 [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x4764b  ldc.i4.0
0x4764c  ldnull
0x4764d  newobj   instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitor::.ctor(string, unsigned int32, unsigned int32, unsigned int32, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPLogType, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x47652  stloc.s  0xC
0x47654  ldarg.0
0x47655  ldarg.1
0x47656  ldloc.s  4
0x47658  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x4765d  call     instance void Microsoft.SharePoint.Taxonomy.UpdateHiddenListJobDefinition::CleanUpECMChangeLogInContentDatabase(class Microsoft.SharePoint.Taxonomy.MetadataWebServiceApplicationProxy proxy, valuetype [mscorlib]System.Guid contentDatabaseId)
0x47662  ldloc.s  0xC
0x47664  ldnull
0x47665  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::Success(class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x4766a  leave.s  loc_476AA
0x4766c  stloc.s  0xD
0x4766e  ldc.i4   0x6DE291
0x47673  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x47678  ldloc.s  0xD
0x4767a  ldstr    aUpdatehiddenli_5// "UpdateHiddenListJob: Error cleaning up "...
0x4767f  ldc.i4.1
0x47680  newarr   [mscorlib]System.Object
0x47685  stloc.s  0x20
0x47687  ldloc.s  0x20
0x47689  ldc.i4.0
0x4768a  ldloc.s  4
0x4768c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x47691  box      [mscorlib]System.Guid
0x47696  stelem.ref
0x47697  ldloc.s  0x20
0x47699  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, class [mscorlib]System.Exception, string, object[])
0x4769e  ldloc.s  0xC
0x476a0  ldloc.s  0xD
0x476a2  ldnull
0x476a3  callvirt instance void [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(class [mscorlib]System.Exception, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>)
0x476a8  leave.s  loc_476AA
0x476aa  leave.s  loc_476B8
0x476ac  ldloc.s  0xC
0x476ae  brfalse.s loc_476B7
0x476b0  ldloc.s  0xC
0x476b2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x476b7  endfinally
0x476b8  ldloc.s  0x1C
0x476ba  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x476bf  brtrue   loc_474C4
0x476c4  leave.s  loc_476D2
0x476c6  ldloc.s  0x1C
0x476c8  brfalse.s loc_476D1
0x476ca  ldloc.s  0x1C
0x476cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x476d1  endfinally
0x476d2  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x476d7  stloc.s  0xE
0x476d9  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x476de  stloc.s  0xF
0x476e0  ldnull
0x476e1  stloc.s  0x10
0x476e3  ldnull
0x476e4  stloc.s  0x11
0x476e6  ldnull
0x476e7  stloc.s  0x12
0x476e9  ldloc.2
0x476ea  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.DictionaryEntry>::GetEnumerator()
0x476ef  stloc.s  0x21
0x476f1  br       loc_479B2
0x476f6  ldloca.s 0x21
0x476f8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Collections.DictionaryEntry>::get_Current()
0x476fd  stloc.s  0x13
0x476ff  ldloca.s 0x13
0x47701  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0x47706  isinst   Microsoft.SharePoint.Taxonomy.ChangedTerm
0x4770b  stloc.s  0x14
0x4770d  ldloca.s 0x13
0x4770f  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0x47714  isinst   Microsoft.SharePoint.Taxonomy.ChangedItem
0x47719  stloc.s  0x15
0x4771b  ldloc.s  0x14
0x4771d  brfalse  loc_479B2
0x47722  ldc.i4   0x67326F69
0x47727  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4772c  ldc.i4.s 0x64
0x4772e  ldstr    aFoundChangeTer// "Found change term of {0} value {1}"
0x47733  ldc.i4.2
0x47734  newarr   [mscorlib]System.Object
0x47739  stloc.s  0x22
0x4773b  ldloc.s  0x22
0x4773d  ldc.i4.0
0x4773e  ldloc.2
0x4773f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.DictionaryEntry>::get_Count()
0x47744  box      [mscorlib]System.Int32
0x47749  stelem.ref
0x4774a  ldloc.s  0x22
0x4774c  ldc.i4.1
0x4774d  ldloc.s  0x14
0x4774f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ChangedItem::get_Id()
0x47754  stloc.s  0x23
0x47756  ldloca.s 0x23
0x47758  constrained. [mscorlib]System.Guid
0x4775e  callvirt instance string [mscorlib]System.Object::ToString()
0x47763  stelem.ref
0x47764  ldloc.s  0x22
0x47766  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x4776b  ldloca.s 0x13
0x4776d  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x47772  callvirt instance string [mscorlib]System.Object::ToString()
0x47777  ldc.i4.1
0x47778  newarr   [mscorlib]System.Char
0x4777d  stloc.s  0x24
0x4777f  ldloc.s  0x24
0x47781  ldc.i4.0
0x47782  ldc.i4.s 0x7C
0x47784  stelem.i2
0x47785  ldloc.s  0x24
0x47787  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x4778c  stloc.s  0x16
0x4778e  ldloca.s 0x17
0x47790  ldloc.s  0x16
0x47792  ldc.i4.0
0x47793  ldelem.ref
0x47794  call     instance void [mscorlib]System.Guid::.ctor(string)
0x47799  ldloc.s  0x17
0x4779b  ldloc.s  0xE
0x4779d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x477a2  brfalse.s loc_477FF
0x477a4  ldarg.3
0x477a5  ldind.ref
0x477a6  ldloc.s  0x17
0x477a8  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, bool>>>>::ContainsKey(var<u1>)
0x477ad  brfalse.s loc_477BC
  ... truncated ...
```
