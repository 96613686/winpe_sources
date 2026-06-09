# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch24

- ea: `0x9f6a0`
- end: `0xa2849`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch24`
- size: `12713`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0xd24c0`

## callees

- `0x17e6f0`
- `0x17e710`
- `0x2bc070`
- `0xabe9f0`

## string_xrefs

- `0x9fa1f`: `@UpdateQuota`
- `0xa2697`: `@DeleteTransactionId`
- `0xa2642`: `@DeleteOp`
- `0xa2729`: `@DeleteFlags`
- `0xa26fe`: `@ChildDeleteTransactionId`
- `0x9f6f0`: `@DeleteIsForMigration`
- `0x9f7a5`: `@DeleteIsForMigration`
- `0x9f6a7`: `proc_DeleteSite`
- `0x9f704`: `@ExtensionDeleteSprocs`
- `0x9f7b9`: `@ExtensionDeleteSprocs`
- `0x9f882`: `@ExtensionDeleteSprocs`
- `0x9f72d`: `@CheckComplianceFlags`
- `0x9f7e2`: `@CheckComplianceFlags`
- `0x9f75c`: `proc_DeleteSiteAsync`
- `0x9f81f`: `@DeferSiteDeleteEvent`
- `0x9f839`: `proc_DeleteSiteCoreAsync`
- `0x9f8da`: `proc_DeleteSiteSession`
- `0x9f92b`: `proc_DeleteSmartPagePersonalization`
- `0x9f9c1`: `proc_DeleteStreamsInBatches`
- `0x9f9f6`: `@docsToDelete`
- `0x9fa62`: `proc_DeleteSubscription`
- `0x9faef`: `proc_DeleteSubscriptionJunctionEntries`
- `0xa252a`: `proc_DeleteUrl`
- `0xa25c9`: `@ListDeletedUrls`
- `0xa25dd`: `@ListDeletedAliases`
- `0xa26d6`: `@IsCascadeDeleteOperation`
- `0xa27a3`: `@DeletedFileCount`
- `0xa27d1`: `proc_DeleteUserResource`

## pseudocode

```c

```

## disassembly

```asm
0x9f6a0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9f6a5  stloc.0
0x9f6a6  ldarg.0
0x9f6a7  ldstr    aProcDeletesite// "proc_DeleteSite"
0x9f6ac  ldloc.0
0x9f6ad  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9f6b2  ldloc.0
0x9f6b3  ldstr    aReturnValue// "@RETURN_VALUE"
0x9f6b8  ldc.i4.8
0x9f6b9  ldc.i4.0
0x9f6ba  ldc.i4.1
0x9f6bb  ldc.i4.0
0x9f6bc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f6c1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f6c6  ldloc.0
0x9f6c7  ldstr    aSiteid_1// "@SiteId"
0x9f6cc  ldc.i4.s 0xE
0x9f6ce  ldc.i4.0
0x9f6cf  ldc.i4.0
0x9f6d0  ldc.i4.0
0x9f6d1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f6d6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f6db  ldloc.0
0x9f6dc  ldstr    aThresholdrowco// "@ThresholdRowCount"
0x9f6e1  ldc.i4.8
0x9f6e2  ldc.i4.0
0x9f6e3  ldc.i4.0
0x9f6e4  ldc.i4.0
0x9f6e5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f6ea  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f6ef  ldloc.0
0x9f6f0  ldstr    aDeleteisformig// "@DeleteIsForMigration"
0x9f6f5  ldc.i4.2
0x9f6f6  ldc.i4.0
0x9f6f7  ldc.i4.0
0x9f6f8  ldc.i4.0
0x9f6f9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f6fe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f703  ldloc.0
0x9f704  ldstr    aExtensiondelet// "@ExtensionDeleteSprocs"
0x9f709  ldstr    aContent// "Content"
0x9f70e  call     class Microsoft.SharePoint.Utilities.Sql.SqlSchema Microsoft.SharePoint.Utilities.Sql.Schema::GetSchema(string database)
0x9f713  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter> Microsoft.SharePoint.Utilities.Sql.SqlSchema::get_TVPs()
0x9f718  ldstr    aTvparrayofstri// "tvpArrayOfStrings"
0x9f71d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter>::get_Item(void)
0x9f722  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter tvpType)
0x9f727  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f72c  ldloc.0
0x9f72d  ldstr    aCheckcomplianc// "@CheckComplianceFlags"
0x9f732  ldc.i4.2
0x9f733  ldc.i4.0
0x9f734  ldc.i4.0
0x9f735  ldc.i4.1
0x9f736  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f73b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f740  ldloc.0
0x9f741  ldstr    aRequestguid// "@RequestGuid"
0x9f746  ldc.i4.s 0xE
0x9f748  ldc.i4.0
0x9f749  ldc.i4.1
0x9f74a  ldc.i4.1
0x9f74b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f750  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f755  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9f75a  stloc.0
0x9f75b  ldarg.0
0x9f75c  ldstr    aProcDeletesite_0// "proc_DeleteSiteAsync"
0x9f761  ldloc.0
0x9f762  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9f767  ldloc.0
0x9f768  ldstr    aReturnValue// "@RETURN_VALUE"
0x9f76d  ldc.i4.8
0x9f76e  ldc.i4.0
0x9f76f  ldc.i4.1
0x9f770  ldc.i4.0
0x9f771  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f776  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f77b  ldloc.0
0x9f77c  ldstr    aSiteid_1// "@SiteId"
0x9f781  ldc.i4.s 0xE
0x9f783  ldc.i4.0
0x9f784  ldc.i4.0
0x9f785  ldc.i4.0
0x9f786  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f78b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f790  ldloc.0
0x9f791  ldstr    aRestorable// "@Restorable"
0x9f796  ldc.i4.2
0x9f797  ldc.i4.0
0x9f798  ldc.i4.0
0x9f799  ldc.i4.0
0x9f79a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f79f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f7a4  ldloc.0
0x9f7a5  ldstr    aDeleteisformig// "@DeleteIsForMigration"
0x9f7aa  ldc.i4.2
0x9f7ab  ldc.i4.0
0x9f7ac  ldc.i4.0
0x9f7ad  ldc.i4.0
0x9f7ae  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f7b3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f7b8  ldloc.0
0x9f7b9  ldstr    aExtensiondelet// "@ExtensionDeleteSprocs"
0x9f7be  ldstr    aContent// "Content"
0x9f7c3  call     class Microsoft.SharePoint.Utilities.Sql.SqlSchema Microsoft.SharePoint.Utilities.Sql.Schema::GetSchema(string database)
0x9f7c8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter> Microsoft.SharePoint.Utilities.Sql.SqlSchema::get_TVPs()
0x9f7cd  ldstr    aTvparrayofstri// "tvpArrayOfStrings"
0x9f7d2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter>::get_Item(void)
0x9f7d7  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter tvpType)
0x9f7dc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f7e1  ldloc.0
0x9f7e2  ldstr    aCheckcomplianc// "@CheckComplianceFlags"
0x9f7e7  ldc.i4.2
0x9f7e8  ldc.i4.0
0x9f7e9  ldc.i4.0
0x9f7ea  ldc.i4.1
0x9f7eb  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f7f0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f7f5  ldloc.0
0x9f7f6  ldstr    aRequestguid// "@RequestGuid"
0x9f7fb  ldc.i4.s 0xE
0x9f7fd  ldc.i4.0
0x9f7fe  ldc.i4.1
0x9f7ff  ldc.i4.1
0x9f800  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f805  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f80a  ldloc.0
0x9f80b  ldstr    aDateoffset// "@DateOffset"
0x9f810  ldc.i4.8
0x9f811  ldc.i4.0
0x9f812  ldc.i4.0
0x9f813  ldc.i4.1
0x9f814  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f819  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f81e  ldloc.0
0x9f81f  ldstr    aDefersitedelet// "@DeferSiteDeleteEvent"
0x9f824  ldc.i4.2
0x9f825  ldc.i4.0
0x9f826  ldc.i4.0
0x9f827  ldc.i4.1
0x9f828  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f82d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f832  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9f837  stloc.0
0x9f838  ldarg.0
0x9f839  ldstr    aProcDeletesite_1// "proc_DeleteSiteCoreAsync"
0x9f83e  ldloc.0
0x9f83f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9f844  ldloc.0
0x9f845  ldstr    aReturnValue// "@RETURN_VALUE"
0x9f84a  ldc.i4.8
0x9f84b  ldc.i4.0
0x9f84c  ldc.i4.1
0x9f84d  ldc.i4.0
0x9f84e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f853  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f858  ldloc.0
0x9f859  ldstr    aSiteid_1// "@SiteId"
0x9f85e  ldc.i4.s 0xE
0x9f860  ldc.i4.0
0x9f861  ldc.i4.0
0x9f862  ldc.i4.0
0x9f863  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f868  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f86d  ldloc.0
0x9f86e  ldstr    aDeletionid// "@DeletionId"
0x9f873  ldc.i4.0
0x9f874  ldc.i4.0
0x9f875  ldc.i4.0
0x9f876  ldc.i4.0
0x9f877  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f87c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f881  ldloc.0
0x9f882  ldstr    aExtensiondelet// "@ExtensionDeleteSprocs"
0x9f887  ldstr    aContent// "Content"
0x9f88c  call     class Microsoft.SharePoint.Utilities.Sql.SqlSchema Microsoft.SharePoint.Utilities.Sql.Schema::GetSchema(string database)
0x9f891  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter> Microsoft.SharePoint.Utilities.Sql.SqlSchema::get_TVPs()
0x9f896  ldstr    aTvparrayofstri// "tvpArrayOfStrings"
0x9f89b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter>::get_Item(void)
0x9f8a0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter tvpType)
0x9f8a5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f8aa  ldloc.0
0x9f8ab  ldstr    aRequestguid// "@RequestGuid"
0x9f8b0  ldc.i4.s 0xE
0x9f8b2  ldc.i4.0
0x9f8b3  ldc.i4.1
0x9f8b4  ldc.i4.1
0x9f8b5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f8ba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f8bf  ldloc.0
0x9f8c0  ldstr    aTimeoutseconds// "@TimeoutSeconds"
0x9f8c5  ldc.i4.8
0x9f8c6  ldc.i4.0
0x9f8c7  ldc.i4.0
0x9f8c8  ldc.i4.1
0x9f8c9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f8ce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f8d3  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9f8d8  stloc.0
0x9f8d9  ldarg.0
0x9f8da  ldstr    aProcDeletesite_2// "proc_DeleteSiteSession"
0x9f8df  ldloc.0
0x9f8e0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9f8e5  ldloc.0
0x9f8e6  ldstr    aReturnValue// "@RETURN_VALUE"
0x9f8eb  ldc.i4.8
0x9f8ec  ldc.i4.0
0x9f8ed  ldc.i4.1
0x9f8ee  ldc.i4.0
0x9f8ef  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f8f4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f8f9  ldloc.0
0x9f8fa  ldstr    aSiteid_1// "@SiteId"
0x9f8ff  ldc.i4.s 0xE
0x9f901  ldc.i4.0
0x9f902  ldc.i4.0
0x9f903  ldc.i4.0
0x9f904  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f909  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f90e  ldloc.0
0x9f90f  ldstr    aSessionid_0// "@SessionId"
0x9f914  ldc.i4.s 0xC
0x9f916  ldc.i4.s 0x64
0x9f918  ldc.i4.0
0x9f919  ldc.i4.0
0x9f91a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f91f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f924  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9f929  stloc.0
0x9f92a  ldarg.0
0x9f92b  ldstr    aProcDeletesmar// "proc_DeleteSmartPagePersonalization"
0x9f930  ldloc.0
0x9f931  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9f936  ldloc.0
0x9f937  ldstr    aReturnValue// "@RETURN_VALUE"
0x9f93c  ldc.i4.8
0x9f93d  ldc.i4.0
0x9f93e  ldc.i4.1
0x9f93f  ldc.i4.0
0x9f940  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f945  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f94a  ldloc.0
0x9f94b  ldstr    aSiteid_1// "@SiteId"
0x9f950  ldc.i4.s 0xE
0x9f952  ldc.i4.0
0x9f953  ldc.i4.0
0x9f954  ldc.i4.0
0x9f955  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f95a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f95f  ldloc.0
0x9f960  ldstr    aDirname_0// "@DirName"
0x9f965  ldc.i4.s 0xC
0x9f967  ldc.i4   0x190
0x9f96c  ldc.i4.0
0x9f96d  ldc.i4.0
0x9f96e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f973  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f978  ldloc.0
0x9f979  ldstr    aLeafname// "@LeafName"
0x9f97e  ldc.i4.s 0xC
0x9f980  ldc.i4   0x190
0x9f985  ldc.i4.0
0x9f986  ldc.i4.0
0x9f987  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f98c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f991  ldloc.0
0x9f992  ldstr    aUserid_1// "@UserId"
0x9f997  ldc.i4.8
0x9f998  ldc.i4.0
0x9f999  ldc.i4.0
0x9f99a  ldc.i4.0
0x9f99b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f9a0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f9a5  ldloc.0
0x9f9a6  ldstr    aRequestguid// "@RequestGuid"
0x9f9ab  ldc.i4.s 0xE
0x9f9ad  ldc.i4.0
0x9f9ae  ldc.i4.1
0x9f9af  ldc.i4.1
0x9f9b0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f9b5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f9ba  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9f9bf  stloc.0
0x9f9c0  ldarg.0
0x9f9c1  ldstr    aProcDeletestre// "proc_DeleteStreamsInBatches"
0x9f9c6  ldloc.0
0x9f9c7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9f9cc  ldloc.0
0x9f9cd  ldstr    aReturnValue// "@RETURN_VALUE"
0x9f9d2  ldc.i4.8
0x9f9d3  ldc.i4.0
0x9f9d4  ldc.i4.1
0x9f9d5  ldc.i4.0
0x9f9d6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f9db  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f9e0  ldloc.0
0x9f9e1  ldstr    aSiteid_1// "@SiteId"
0x9f9e6  ldc.i4.s 0xE
0x9f9e8  ldc.i4.0
0x9f9e9  ldc.i4.0
  ... truncated ...
```
