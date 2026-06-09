# Microsoft.SharePoint.SPStoredProceduresAppMng::GetStoredProceduresBatch4

- ea: `0x173f70`
- end: `0x174888`
- name: `Microsoft.SharePoint.SPStoredProceduresAppMng::GetStoredProceduresBatch4`
- size: `2328`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x176190`

## callees

- `0x17e710`

## string_xrefs

- `0x173f97`: `@CompositePartitionKey`
- `0x174010`: `@CompositePartitionKey`
- `0x17404c`: `@CompositePartitionKey`
- `0x17421e`: `@CompositePartitionKey`
- `0x174405`: `@CompositePartitionKey`
- `0x1744cc`: `@CompositePartitionKey`
- `0x17458b`: `@CompositePartitionKey`
- `0x174690`: `@CompositePartitionKey`
- `0x1747ae`: `@CompositePartitionKey`
- `0x17482f`: `@CompositePartitionKey`
- `0x174164`: `@TokenExpiryDate`
- `0x17434b`: `@TokenExpiryDate`
- `0x1741a3`: `@RawXMLEntitlementToken`
- `0x17438a`: `@RawXMLEntitlementToken`
- `0x173fdb`: `proc_AM_InternalDeleteLicense`
- `0x1741fe`: `proc_AM_InternalUpdateLicense`
- `0x17447d`: `@IsInternalDirectoryOnlyApp`

## pseudocode

```c

```

## disassembly

```asm
0x173f70  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x173f75  stloc.0
0x173f76  ldarg.0
0x173f77  ldstr    aProcAmIncremen// "proc_AM_IncrementSiteSubscriptionAppIns"...
0x173f7c  ldloc.0
0x173f7d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x173f82  ldloc.0
0x173f83  ldstr    aReturnValue// "@RETURN_VALUE"
0x173f88  ldc.i4.8
0x173f89  ldc.i4.0
0x173f8a  ldc.i4.1
0x173f8b  ldc.i4.0
0x173f8c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x173f91  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x173f96  ldloc.0
0x173f97  ldstr    aCompositeparti// "@CompositePartitionKey"
0x173f9c  ldc.i4.1
0x173f9d  ldc.i4.s 0x11
0x173f9f  ldc.i4.0
0x173fa0  ldc.i4.0
0x173fa1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x173fa6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x173fab  ldloc.0
0x173fac  ldstr    aErrorcode_0// "@ErrorCode"
0x173fb1  ldc.i4.8
0x173fb2  ldc.i4.0
0x173fb3  ldc.i4.1
0x173fb4  ldc.i4.0
0x173fb5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x173fba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x173fbf  ldloc.0
0x173fc0  ldstr    aRequestguid// "@RequestGuid"
0x173fc5  ldc.i4.s 0xE
0x173fc7  ldc.i4.0
0x173fc8  ldc.i4.1
0x173fc9  ldc.i4.1
0x173fca  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x173fcf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x173fd4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x173fd9  stloc.0
0x173fda  ldarg.0
0x173fdb  ldstr    aProcAmInternal// "proc_AM_InternalDeleteLicense"
0x173fe0  ldloc.0
0x173fe1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x173fe6  ldloc.0
0x173fe7  ldstr    aReturnValue// "@RETURN_VALUE"
0x173fec  ldc.i4.8
0x173fed  ldc.i4.0
0x173fee  ldc.i4.1
0x173fef  ldc.i4.0
0x173ff0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x173ff5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x173ffa  ldloc.0
0x173ffb  ldstr    aLicenseid// "@LicenseId"
0x174000  ldc.i4.s 0xE
0x174002  ldc.i4.0
0x174003  ldc.i4.0
0x174004  ldc.i4.0
0x174005  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x17400a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x17400f  ldloc.0
0x174010  ldstr    aCompositeparti// "@CompositePartitionKey"
0x174015  ldc.i4.s 0x15
0x174017  ldc.i4.s 0x21
0x174019  ldc.i4.0
0x17401a  ldc.i4.0
0x17401b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174020  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174025  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x17402a  stloc.0
0x17402b  ldarg.0
0x17402c  ldstr    aProcAmInternal_0// "proc_AM_InternalInsertLicense"
0x174031  ldloc.0
0x174032  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x174037  ldloc.0
0x174038  ldstr    aReturnValue// "@RETURN_VALUE"
0x17403d  ldc.i4.8
0x17403e  ldc.i4.0
0x17403f  ldc.i4.1
0x174040  ldc.i4.0
0x174041  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174046  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x17404b  ldloc.0
0x17404c  ldstr    aCompositeparti// "@CompositePartitionKey"
0x174051  ldc.i4.s 0x15
0x174053  ldc.i4.s 0x21
0x174055  ldc.i4.0
0x174056  ldc.i4.0
0x174057  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x17405c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174061  ldloc.0
0x174062  ldstr    aLicenseid// "@LicenseId"
0x174067  ldc.i4.s 0xE
0x174069  ldc.i4.0
0x17406a  ldc.i4.0
0x17406b  ldc.i4.0
0x17406c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174071  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174076  ldloc.0
0x174077  ldstr    aUseridentity// "@UserIdentity"
0x17407c  ldc.i4.s 0xC
0x17407e  ldc.i4   0xFF
0x174083  ldc.i4.0
0x174084  ldc.i4.0
0x174085  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x17408a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x17408f  ldloc.0
0x174090  ldstr    aUserkey_0// "@UserKey"
0x174095  ldc.i4.s 0xC
0x174097  ldc.i4   0xFF
0x17409c  ldc.i4.0
0x17409d  ldc.i4.0
0x17409e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x1740a3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1740a8  ldloc.0
0x1740a9  ldstr    aPurchaserident// "@PurchaserIdentity"
0x1740ae  ldc.i4.s 0xC
0x1740b0  ldc.i4.s 0x10
0x1740b2  ldc.i4.0
0x1740b3  ldc.i4.0
0x1740b4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x1740b9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1740be  ldloc.0
0x1740bf  ldstr    aLicensetype_0// "@LicenseType"
0x1740c4  ldc.i4.s 0x14
0x1740c6  ldc.i4.0
0x1740c7  ldc.i4.0
0x1740c8  ldc.i4.0
0x1740c9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x1740ce  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1740d3  ldloc.0
0x1740d4  ldstr    aOmexlicensetyp// "@OmexLicenseType"
0x1740d9  ldc.i4.s 0x14
0x1740db  ldc.i4.0
0x1740dc  ldc.i4.0
0x1740dd  ldc.i4.0
0x1740de  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x1740e3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1740e8  ldloc.0
0x1740e9  ldstr    aMaxusercount// "@MaxUserCount"
0x1740ee  ldc.i4.8
0x1740ef  ldc.i4.0
0x1740f0  ldc.i4.0
0x1740f1  ldc.i4.0
0x1740f2  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x1740f7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1740fc  ldloc.0
0x1740fd  ldstr    aCurrentusercou// "@CurrentUserCount"
0x174102  ldc.i4.8
0x174103  ldc.i4.0
0x174104  ldc.i4.1
0x174105  ldc.i4.0
0x174106  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x17410b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174110  ldloc.0
0x174111  ldstr    aExpirationdate// "@ExpirationDate"
0x174116  ldc.i4.4
0x174117  ldc.i4.0
0x174118  ldc.i4.0
0x174119  ldc.i4.0
0x17411a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x17411f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174124  ldloc.0
0x174125  ldstr    aAssetid// "@AssetId"
0x17412a  ldc.i4.s 0xC
0x17412c  ldc.i4.s 0xE
0x17412e  ldc.i4.0
0x17412f  ldc.i4.0
0x174130  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174135  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x17413a  ldloc.0
0x17413b  ldstr    aDeploymentid// "@DeploymentId"
0x174140  ldc.i4.s 0xE
0x174142  ldc.i4.0
0x174143  ldc.i4.0
0x174144  ldc.i4.0
0x174145  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x17414a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x17414f  ldloc.0
0x174150  ldstr    aLicenseacquisi// "@LicenseAcquisitionDate"
0x174155  ldc.i4.4
0x174156  ldc.i4.0
0x174157  ldc.i4.0
0x174158  ldc.i4.0
0x174159  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x17415e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174163  ldloc.0
0x174164  ldstr    aTokenexpirydat// "@TokenExpiryDate"
0x174169  ldc.i4.4
0x17416a  ldc.i4.0
0x17416b  ldc.i4.0
0x17416c  ldc.i4.0
0x17416d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174172  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174177  ldloc.0
0x174178  ldstr    aContentmarket// "@ContentMarket"
0x17417d  ldc.i4.s 0xC
0x17417f  ldc.i4.s 0xA
0x174181  ldc.i4.0
0x174182  ldc.i4.0
0x174183  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174188  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x17418d  ldloc.0
0x17418e  ldstr    aBillingmarket// "@BillingMarket"
0x174193  ldc.i4.s 0xC
0x174195  ldc.i4.2
0x174196  ldc.i4.0
0x174197  ldc.i4.0
0x174198  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x17419d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1741a2  ldloc.0
0x1741a3  ldstr    aRawxmlentitlem// "@RawXMLEntitlementToken"
0x1741a8  ldc.i4.s 0xC
0x1741aa  ldc.i4   0x200
0x1741af  ldc.i4.0
0x1741b0  ldc.i4.0
0x1741b1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x1741b6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1741bb  ldloc.0
0x1741bc  ldstr    aRetryrenewalaf// "@RetryRenewalAfter"
0x1741c1  ldc.i4.4
0x1741c2  ldc.i4.0
0x1741c3  ldc.i4.0
0x1741c4  ldc.i4.0
0x1741c5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x1741ca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1741cf  ldloc.0
0x1741d0  ldstr    aIspending// "@IsPending"
0x1741d5  ldc.i4.2
0x1741d6  ldc.i4.0
0x1741d7  ldc.i4.0
0x1741d8  ldc.i4.0
0x1741d9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x1741de  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1741e3  ldloc.0
0x1741e4  ldstr    aIstestlicense// "@IsTestLicense"
0x1741e9  ldc.i4.2
0x1741ea  ldc.i4.0
0x1741eb  ldc.i4.0
0x1741ec  ldc.i4.0
0x1741ed  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x1741f2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1741f7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x1741fc  stloc.0
0x1741fd  ldarg.0
0x1741fe  ldstr    aProcAmInternal_1// "proc_AM_InternalUpdateLicense"
0x174203  ldloc.0
0x174204  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x174209  ldloc.0
0x17420a  ldstr    aReturnValue// "@RETURN_VALUE"
0x17420f  ldc.i4.8
0x174210  ldc.i4.0
0x174211  ldc.i4.1
0x174212  ldc.i4.0
0x174213  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174218  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x17421d  ldloc.0
0x17421e  ldstr    aCompositeparti// "@CompositePartitionKey"
0x174223  ldc.i4.s 0x15
0x174225  ldc.i4.s 0x21
0x174227  ldc.i4.0
0x174228  ldc.i4.0
0x174229  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x17422e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174233  ldloc.0
0x174234  ldstr    aLicenseid// "@LicenseId"
0x174239  ldc.i4.s 0xE
0x17423b  ldc.i4.0
0x17423c  ldc.i4.0
0x17423d  ldc.i4.0
0x17423e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174243  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174248  ldloc.0
0x174249  ldstr    aUseridentity// "@UserIdentity"
0x17424e  ldc.i4.s 0xC
0x174250  ldc.i4   0xFF
0x174255  ldc.i4.0
0x174256  ldc.i4.0
0x174257  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x17425c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174261  ldloc.0
0x174262  ldstr    aUserkey_0// "@UserKey"
0x174267  ldc.i4.s 0xC
0x174269  ldc.i4   0xFF
0x17426e  ldc.i4.0
0x17426f  ldc.i4.0
0x174270  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174275  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x17427a  ldloc.0
0x17427b  ldstr    aMaxusercount// "@MaxUserCount"
0x174280  ldc.i4.8
0x174281  ldc.i4.0
0x174282  ldc.i4.0
0x174283  ldc.i4.0
0x174284  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174289  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x17428e  ldloc.0
0x17428f  ldstr    aCurrentusercou// "@CurrentUserCount"
0x174294  ldc.i4.8
0x174295  ldc.i4.0
  ... truncated ...
```
