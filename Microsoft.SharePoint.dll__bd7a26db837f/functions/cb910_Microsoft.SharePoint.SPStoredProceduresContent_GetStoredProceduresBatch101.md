# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch101

- ea: `0xcb910`
- end: `0xcc187`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch101`
- size: `2167`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd24c0`

## callees

- `0x17e710`

## string_xrefs

- `0xcbc50`: `proc_UpdateDatabaseDefaultOptions`
- `0xcb917`: `proc_UpdateAllSitesDateRowAdded`
- `0xcb967`: `proc_UpdateAppPrincipalFlags`
- `0xcb9f8`: `proc_UpdateCachedNav`
- `0xcba57`: `@CachedNavData`
- `0xcba6c`: `@CachedInheritedNavData`
- `0xcba81`: `@CachedNavScopeData`
- `0xcba96`: `@NavParentCachedNavData`
- `0xcbaab`: `@NavParentCachedScopeData`
- `0xcbac0`: `@CachedNavDirty`
- `0xcbad4`: `@CachedDataVersion`
- `0xcbae8`: `@NavParentCachedDataVersion`
- `0xcbb17`: `proc_UpdateComplianceTagMarkForUpdate`
- `0xcbb52`: `proc_UpdateContentTypeInScope`
- `0xcbc76`: `proc_UpdateDataViewWhileSaving`
- `0xcbd71`: `proc_UpdateDirtyDocument`
- `0xcbf37`: `proc_UpdateDirtyDocument2`
- `0xcc13e`: `proc_UpdateDiskUsed`
- `0xcc173`: `@bUpdateTimeStampForce`

## pseudocode

```c

```

## disassembly

```asm
0xcb910  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xcb915  stloc.0
0xcb916  ldarg.0
0xcb917  ldstr    aProcUpdatealls// "proc_UpdateAllSitesDateRowAdded"
0xcb91c  ldloc.0
0xcb91d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xcb922  ldloc.0
0xcb923  ldstr    aReturnValue// "@RETURN_VALUE"
0xcb928  ldc.i4.8
0xcb929  ldc.i4.0
0xcb92a  ldc.i4.1
0xcb92b  ldc.i4.0
0xcb92c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcb931  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcb936  ldloc.0
0xcb937  ldstr    aSiteid_1// "@SiteId"
0xcb93c  ldc.i4.s 0xE
0xcb93e  ldc.i4.0
0xcb93f  ldc.i4.0
0xcb940  ldc.i4.0
0xcb941  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcb946  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcb94b  ldloc.0
0xcb94c  ldstr    aRequestguid// "@RequestGuid"
0xcb951  ldc.i4.s 0xE
0xcb953  ldc.i4.0
0xcb954  ldc.i4.1
0xcb955  ldc.i4.1
0xcb956  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcb95b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcb960  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xcb965  stloc.0
0xcb966  ldarg.0
0xcb967  ldstr    aProcUpdateappp// "proc_UpdateAppPrincipalFlags"
0xcb96c  ldloc.0
0xcb96d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xcb972  ldloc.0
0xcb973  ldstr    aReturnValue// "@RETURN_VALUE"
0xcb978  ldc.i4.8
0xcb979  ldc.i4.0
0xcb97a  ldc.i4.1
0xcb97b  ldc.i4.0
0xcb97c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcb981  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcb986  ldloc.0
0xcb987  ldstr    aSiteid_1// "@SiteId"
0xcb98c  ldc.i4.s 0xE
0xcb98e  ldc.i4.0
0xcb98f  ldc.i4.0
0xcb990  ldc.i4.0
0xcb991  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcb996  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcb99b  ldloc.0
0xcb99c  ldstr    aAppinstanceid// "@AppInstanceId"
0xcb9a1  ldc.i4.s 0xE
0xcb9a3  ldc.i4.0
0xcb9a4  ldc.i4.0
0xcb9a5  ldc.i4.0
0xcb9a6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcb9ab  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcb9b0  ldloc.0
0xcb9b1  ldstr    aFlag// "@Flag"
0xcb9b6  ldc.i4.8
0xcb9b7  ldc.i4.0
0xcb9b8  ldc.i4.0
0xcb9b9  ldc.i4.0
0xcb9ba  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcb9bf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcb9c4  ldloc.0
0xcb9c5  ldstr    aSetorclearflag// "@SetOrClearFlags"
0xcb9ca  ldc.i4.2
0xcb9cb  ldc.i4.0
0xcb9cc  ldc.i4.0
0xcb9cd  ldc.i4.0
0xcb9ce  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcb9d3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcb9d8  ldloc.0
0xcb9d9  ldstr    aAppprincipalna// "@AppPrincipalName"
0xcb9de  ldc.i4.s 0xC
0xcb9e0  ldc.i4   0x100
0xcb9e5  ldc.i4.1
0xcb9e6  ldc.i4.0
0xcb9e7  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcb9ec  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcb9f1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xcb9f6  stloc.0
0xcb9f7  ldarg.0
0xcb9f8  ldstr    aProcUpdatecach_0// "proc_UpdateCachedNav"
0xcb9fd  ldloc.0
0xcb9fe  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xcba03  ldloc.0
0xcba04  ldstr    aReturnValue// "@RETURN_VALUE"
0xcba09  ldc.i4.8
0xcba0a  ldc.i4.0
0xcba0b  ldc.i4.1
0xcba0c  ldc.i4.0
0xcba0d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcba12  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcba17  ldloc.0
0xcba18  ldstr    aSiteid_1// "@SiteId"
0xcba1d  ldc.i4.s 0xE
0xcba1f  ldc.i4.0
0xcba20  ldc.i4.0
0xcba21  ldc.i4.0
0xcba22  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcba27  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcba2c  ldloc.0
0xcba2d  ldstr    aWebid_0// "@WebId"
0xcba32  ldc.i4.s 0xE
0xcba34  ldc.i4.0
0xcba35  ldc.i4.0
0xcba36  ldc.i4.0
0xcba37  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcba3c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcba41  ldloc.0
0xcba42  ldstr    aNavparentwebid// "@NavParentWebId"
0xcba47  ldc.i4.s 0xE
0xcba49  ldc.i4.0
0xcba4a  ldc.i4.0
0xcba4b  ldc.i4.0
0xcba4c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcba51  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcba56  ldloc.0
0xcba57  ldstr    aCachednavdata// "@CachedNavData"
0xcba5c  ldc.i4.s 0x15
0xcba5e  ldc.i4.m1
0xcba5f  ldc.i4.0
0xcba60  ldc.i4.0
0xcba61  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcba66  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcba6b  ldloc.0
0xcba6c  ldstr    aCachedinherite// "@CachedInheritedNavData"
0xcba71  ldc.i4.s 0x15
0xcba73  ldc.i4.m1
0xcba74  ldc.i4.0
0xcba75  ldc.i4.0
0xcba76  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcba7b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcba80  ldloc.0
0xcba81  ldstr    aCachednavscope// "@CachedNavScopeData"
0xcba86  ldc.i4.s 0xC
0xcba88  ldc.i4.m1
0xcba89  ldc.i4.0
0xcba8a  ldc.i4.0
0xcba8b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcba90  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcba95  ldloc.0
0xcba96  ldstr    aNavparentcache// "@NavParentCachedNavData"
0xcba9b  ldc.i4.s 0x15
0xcba9d  ldc.i4.m1
0xcba9e  ldc.i4.0
0xcba9f  ldc.i4.0
0xcbaa0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbaa5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbaaa  ldloc.0
0xcbaab  ldstr    aNavparentcache_0// "@NavParentCachedScopeData"
0xcbab0  ldc.i4.s 0xC
0xcbab2  ldc.i4.m1
0xcbab3  ldc.i4.0
0xcbab4  ldc.i4.0
0xcbab5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbaba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbabf  ldloc.0
0xcbac0  ldstr    aCachednavdirty// "@CachedNavDirty"
0xcbac5  ldc.i4.8
0xcbac6  ldc.i4.0
0xcbac7  ldc.i4.0
0xcbac8  ldc.i4.0
0xcbac9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbace  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbad3  ldloc.0
0xcbad4  ldstr    aCacheddatavers// "@CachedDataVersion"
0xcbad9  ldc.i4.8
0xcbada  ldc.i4.0
0xcbadb  ldc.i4.0
0xcbadc  ldc.i4.0
0xcbadd  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbae2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbae7  ldloc.0
0xcbae8  ldstr    aNavparentcache_1// "@NavParentCachedDataVersion"
0xcbaed  ldc.i4.8
0xcbaee  ldc.i4.0
0xcbaef  ldc.i4.0
0xcbaf0  ldc.i4.0
0xcbaf1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbaf6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbafb  ldloc.0
0xcbafc  ldstr    aRequestguid// "@RequestGuid"
0xcbb01  ldc.i4.s 0xE
0xcbb03  ldc.i4.0
0xcbb04  ldc.i4.1
0xcbb05  ldc.i4.1
0xcbb06  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbb0b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbb10  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xcbb15  stloc.0
0xcbb16  ldarg.0
0xcbb17  ldstr    aProcUpdatecomp// "proc_UpdateComplianceTagMarkForUpdate"
0xcbb1c  ldloc.0
0xcbb1d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xcbb22  ldloc.0
0xcbb23  ldstr    aReturnValue// "@RETURN_VALUE"
0xcbb28  ldc.i4.8
0xcbb29  ldc.i4.0
0xcbb2a  ldc.i4.1
0xcbb2b  ldc.i4.0
0xcbb2c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbb31  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbb36  ldloc.0
0xcbb37  ldstr    aRequestguid// "@RequestGuid"
0xcbb3c  ldc.i4.s 0xE
0xcbb3e  ldc.i4.0
0xcbb3f  ldc.i4.1
0xcbb40  ldc.i4.1
0xcbb41  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbb46  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbb4b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xcbb50  stloc.0
0xcbb51  ldarg.0
0xcbb52  ldstr    aProcUpdatecont// "proc_UpdateContentTypeInScope"
0xcbb57  ldloc.0
0xcbb58  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xcbb5d  ldloc.0
0xcbb5e  ldstr    aReturnValue// "@RETURN_VALUE"
0xcbb63  ldc.i4.8
0xcbb64  ldc.i4.0
0xcbb65  ldc.i4.1
0xcbb66  ldc.i4.0
0xcbb67  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbb6c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbb71  ldloc.0
0xcbb72  ldstr    aSiteid_1// "@SiteId"
0xcbb77  ldc.i4.s 0xE
0xcbb79  ldc.i4.0
0xcbb7a  ldc.i4.0
0xcbb7b  ldc.i4.0
0xcbb7c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbb81  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbb86  ldloc.0
0xcbb87  ldstr    aClass// "@Class"
0xcbb8c  ldc.i4.s 0x14
0xcbb8e  ldc.i4.0
0xcbb8f  ldc.i4.0
0xcbb90  ldc.i4.0
0xcbb91  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbb96  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbb9b  ldloc.0
0xcbb9c  ldstr    aScope_1// "@Scope"
0xcbba1  ldc.i4.s 0xC
0xcbba3  ldc.i4   0x100
0xcbba8  ldc.i4.0
0xcbba9  ldc.i4.0
0xcbbaa  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbbaf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbbb4  ldloc.0
0xcbbb5  ldstr    aContenttypeid// "@ContentTypeId"
0xcbbba  ldc.i4.s 0x15
0xcbbbc  ldc.i4   0x200
0xcbbc1  ldc.i4.0
0xcbbc2  ldc.i4.0
0xcbbc3  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbbc8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbbcd  ldloc.0
0xcbbce  ldstr    aDefinition_0// "@Definition"
0xcbbd3  ldc.i4.s 0xC
0xcbbd5  ldc.i4.m1
0xcbbd6  ldc.i4.0
0xcbbd7  ldc.i4.0
0xcbbd8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbbdd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbbe2  ldloc.0
0xcbbe3  ldstr    aVersion_3// "@Version"
0xcbbe8  ldc.i4.8
0xcbbe9  ldc.i4.0
0xcbbea  ldc.i4.0
0xcbbeb  ldc.i4.0
0xcbbec  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbbf1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbbf6  ldloc.0
0xcbbf7  ldstr    aFeatureid_0// "@FeatureId"
0xcbbfc  ldc.i4.s 0xE
0xcbbfe  ldc.i4.0
0xcbbff  ldc.i4.0
0xcbc00  ldc.i4.1
0xcbc01  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbc06  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbc0b  ldloc.0
0xcbc0c  ldstr    aSolutionid_0// "@SolutionId"
0xcbc11  ldc.i4.s 0xE
0xcbc13  ldc.i4.0
0xcbc14  ldc.i4.0
0xcbc15  ldc.i4.1
0xcbc16  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcbc1b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcbc20  ldloc.0
0xcbc21  ldstr    aSetnextchildby// "@SetNextChildByteToZero"
0xcbc26  ldc.i4.2
0xcbc27  ldc.i4.0
0xcbc28  ldc.i4.0
0xcbc29  ldc.i4.1
  ... truncated ...
```
