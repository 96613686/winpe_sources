# Microsoft.SharePoint.SPStoredProceduresAppMng::GetStoredProceduresBatch5

- ea: `0x174890`
- end: `0x174de6`
- name: `Microsoft.SharePoint.SPStoredProceduresAppMng::GetStoredProceduresBatch5`
- size: `1366`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x176190`

## callees

- `0x17e6f0`
- `0x17e710`
- `0x2bc070`
- `0xabe9f0`

## string_xrefs

- `0x174978`: `@AllPermsRemoved`
- `0x1748b7`: `@CompositePartitionKey`
- `0x17494a`: `@CompositePartitionKey`
- `0x1749c7`: `@CompositePartitionKey`
- `0x174a30`: `@CompositePartitionKey`
- `0x174ab2`: `@CompositePartitionKey`
- `0x174b59`: `@CompositePartitionKey`
- `0x174bd7`: `@CompositePartitionKey`
- `0x174ca8`: `@CompositePartitionKey`
- `0x174d26`: `@CompositePartitionKey`
- `0x174d93`: `@CompositePartitionKey`
- `0x17492a`: `proc_AM_RemoveAppPrincipalAppInstancePerms`
- `0x1749a7`: `proc_AM_RemoveAppPrincipalPerms`
- `0x174a10`: `proc_AM_RemoveAppPrincipalPermsWithUserIdentity`
- `0x174a92`: `proc_AM_RemoveApprovedAppById`
- `0x174afb`: `proc_AM_RemoveLicenseDirectors`
- `0x174bb7`: `proc_AM_RemoveRegisteredOAuthAppId`
- `0x174c4a`: `proc_AM_RemoveUserLicenseAssignments`

## pseudocode

```c

```

## disassembly

```asm
0x174890  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x174895  stloc.0
0x174896  ldarg.0
0x174897  ldstr    aProcAmRegister// "proc_AM_RegisterOAuthAppIdWithProduct"
0x17489c  ldloc.0
0x17489d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x1748a2  ldloc.0
0x1748a3  ldstr    aReturnValue// "@RETURN_VALUE"
0x1748a8  ldc.i4.8
0x1748a9  ldc.i4.0
0x1748aa  ldc.i4.1
0x1748ab  ldc.i4.0
0x1748ac  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x1748b1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1748b6  ldloc.0
0x1748b7  ldstr    aCompositeparti// "@CompositePartitionKey"
0x1748bc  ldc.i4.s 0x15
0x1748be  ldc.i4.s 0x21
0x1748c0  ldc.i4.0
0x1748c1  ldc.i4.0
0x1748c2  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x1748c7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1748cc  ldloc.0
0x1748cd  ldstr    aAppid// "@AppId"
0x1748d2  ldc.i4.s 0xC
0x1748d4  ldc.i4   0x100
0x1748d9  ldc.i4.0
0x1748da  ldc.i4.0
0x1748db  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x1748e0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1748e5  ldloc.0
0x1748e6  ldstr    aAppinstanceid// "@AppInstanceId"
0x1748eb  ldc.i4.s 0xE
0x1748ed  ldc.i4.0
0x1748ee  ldc.i4.0
0x1748ef  ldc.i4.0
0x1748f0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x1748f5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1748fa  ldloc.0
0x1748fb  ldstr    aErrorcode_0// "@ErrorCode"
0x174900  ldc.i4.8
0x174901  ldc.i4.0
0x174902  ldc.i4.1
0x174903  ldc.i4.0
0x174904  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174909  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x17490e  ldloc.0
0x17490f  ldstr    aRequestguid// "@RequestGuid"
0x174914  ldc.i4.s 0xE
0x174916  ldc.i4.0
0x174917  ldc.i4.1
0x174918  ldc.i4.1
0x174919  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x17491e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174923  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x174928  stloc.0
0x174929  ldarg.0
0x17492a  ldstr    aProcAmRemoveap// "proc_AM_RemoveAppPrincipalAppInstancePe"...
0x17492f  ldloc.0
0x174930  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x174935  ldloc.0
0x174936  ldstr    aReturnValue// "@RETURN_VALUE"
0x17493b  ldc.i4.8
0x17493c  ldc.i4.0
0x17493d  ldc.i4.1
0x17493e  ldc.i4.0
0x17493f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174944  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174949  ldloc.0
0x17494a  ldstr    aCompositeparti// "@CompositePartitionKey"
0x17494f  ldc.i4.s 0x15
0x174951  ldc.i4   0x211
0x174956  ldc.i4.0
0x174957  ldc.i4.0
0x174958  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x17495d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174962  ldloc.0
0x174963  ldstr    aAppinstanceid// "@AppInstanceId"
0x174968  ldc.i4.s 0xE
0x17496a  ldc.i4.0
0x17496b  ldc.i4.0
0x17496c  ldc.i4.0
0x17496d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174972  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174977  ldloc.0
0x174978  ldstr    aAllpermsremove// "@AllPermsRemoved"
0x17497d  ldc.i4.2
0x17497e  ldc.i4.0
0x17497f  ldc.i4.1
0x174980  ldc.i4.0
0x174981  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174986  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x17498b  ldloc.0
0x17498c  ldstr    aRequestguid// "@RequestGuid"
0x174991  ldc.i4.s 0xE
0x174993  ldc.i4.0
0x174994  ldc.i4.1
0x174995  ldc.i4.1
0x174996  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x17499b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1749a0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x1749a5  stloc.0
0x1749a6  ldarg.0
0x1749a7  ldstr    aProcAmRemoveap_0// "proc_AM_RemoveAppPrincipalPerms"
0x1749ac  ldloc.0
0x1749ad  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x1749b2  ldloc.0
0x1749b3  ldstr    aReturnValue// "@RETURN_VALUE"
0x1749b8  ldc.i4.8
0x1749b9  ldc.i4.0
0x1749ba  ldc.i4.1
0x1749bb  ldc.i4.0
0x1749bc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x1749c1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1749c6  ldloc.0
0x1749c7  ldstr    aCompositeparti// "@CompositePartitionKey"
0x1749cc  ldc.i4.s 0x15
0x1749ce  ldc.i4   0x211
0x1749d3  ldc.i4.0
0x1749d4  ldc.i4.0
0x1749d5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x1749da  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1749df  ldloc.0
0x1749e0  ldstr    aProvidertypeid// "@ProviderTypeId"
0x1749e5  ldc.i4.s 0xE
0x1749e7  ldc.i4.0
0x1749e8  ldc.i4.0
0x1749e9  ldc.i4.0
0x1749ea  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x1749ef  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x1749f4  ldloc.0
0x1749f5  ldstr    aRequestguid// "@RequestGuid"
0x1749fa  ldc.i4.s 0xE
0x1749fc  ldc.i4.0
0x1749fd  ldc.i4.1
0x1749fe  ldc.i4.1
0x1749ff  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174a04  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174a09  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x174a0e  stloc.0
0x174a0f  ldarg.0
0x174a10  ldstr    aProcAmRemoveap_1// "proc_AM_RemoveAppPrincipalPermsWithUser"...
0x174a15  ldloc.0
0x174a16  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x174a1b  ldloc.0
0x174a1c  ldstr    aReturnValue// "@RETURN_VALUE"
0x174a21  ldc.i4.8
0x174a22  ldc.i4.0
0x174a23  ldc.i4.1
0x174a24  ldc.i4.0
0x174a25  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174a2a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174a2f  ldloc.0
0x174a30  ldstr    aCompositeparti// "@CompositePartitionKey"
0x174a35  ldc.i4.s 0x15
0x174a37  ldc.i4   0x211
0x174a3c  ldc.i4.0
0x174a3d  ldc.i4.0
0x174a3e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174a43  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174a48  ldloc.0
0x174a49  ldstr    aProvidertypeid// "@ProviderTypeId"
0x174a4e  ldc.i4.s 0xE
0x174a50  ldc.i4.0
0x174a51  ldc.i4.0
0x174a52  ldc.i4.0
0x174a53  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174a58  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174a5d  ldloc.0
0x174a5e  ldstr    aUseridentity// "@UserIdentity"
0x174a63  ldc.i4.s 0xC
0x174a65  ldc.i4   0xFF
0x174a6a  ldc.i4.0
0x174a6b  ldc.i4.0
0x174a6c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174a71  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174a76  ldloc.0
0x174a77  ldstr    aRequestguid// "@RequestGuid"
0x174a7c  ldc.i4.s 0xE
0x174a7e  ldc.i4.0
0x174a7f  ldc.i4.1
0x174a80  ldc.i4.1
0x174a81  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174a86  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174a8b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x174a90  stloc.0
0x174a91  ldarg.0
0x174a92  ldstr    aProcAmRemoveap_2// "proc_AM_RemoveApprovedAppById"
0x174a97  ldloc.0
0x174a98  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x174a9d  ldloc.0
0x174a9e  ldstr    aReturnValue// "@RETURN_VALUE"
0x174aa3  ldc.i4.8
0x174aa4  ldc.i4.0
0x174aa5  ldc.i4.1
0x174aa6  ldc.i4.0
0x174aa7  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174aac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174ab1  ldloc.0
0x174ab2  ldstr    aCompositeparti// "@CompositePartitionKey"
0x174ab7  ldc.i4.s 0x15
0x174ab9  ldc.i4   0x211
0x174abe  ldc.i4.0
0x174abf  ldc.i4.0
0x174ac0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174ac5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174aca  ldloc.0
0x174acb  ldstr    aId_1// "@Id"
0x174ad0  ldc.i4.s 0xE
0x174ad2  ldc.i4.0
0x174ad3  ldc.i4.0
0x174ad4  ldc.i4.0
0x174ad5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174ada  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174adf  ldloc.0
0x174ae0  ldstr    aRequestguid// "@RequestGuid"
0x174ae5  ldc.i4.s 0xE
0x174ae7  ldc.i4.0
0x174ae8  ldc.i4.1
0x174ae9  ldc.i4.1
0x174aea  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174aef  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174af4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x174af9  stloc.0
0x174afa  ldarg.0
0x174afb  ldstr    aProcAmRemoveli// "proc_AM_RemoveLicenseDirectors"
0x174b00  ldloc.0
0x174b01  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x174b06  ldloc.0
0x174b07  ldstr    aReturnValue// "@RETURN_VALUE"
0x174b0c  ldc.i4.8
0x174b0d  ldc.i4.0
0x174b0e  ldc.i4.1
0x174b0f  ldc.i4.0
0x174b10  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174b15  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174b1a  ldloc.0
0x174b1b  ldstr    aUsers// "@Users"
0x174b20  ldstr    aAppmng// "AppMng"
0x174b25  call     class Microsoft.SharePoint.Utilities.Sql.SqlSchema Microsoft.SharePoint.Utilities.Sql.Schema::GetSchema(string database)
0x174b2a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter> Microsoft.SharePoint.Utilities.Sql.SqlSchema::get_TVPs()
0x174b2f  ldstr    aTvpuserlist// "tvpUserList"
0x174b34  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter>::get_Item(void)
0x174b39  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter tvpType)
0x174b3e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174b43  ldloc.0
0x174b44  ldstr    aLicenseid// "@LicenseId"
0x174b49  ldc.i4.s 0xE
0x174b4b  ldc.i4.0
0x174b4c  ldc.i4.0
0x174b4d  ldc.i4.0
0x174b4e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174b53  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174b58  ldloc.0
0x174b59  ldstr    aCompositeparti// "@CompositePartitionKey"
0x174b5e  ldc.i4.s 0x15
0x174b60  ldc.i4.s 0x21
0x174b62  ldc.i4.0
0x174b63  ldc.i4.0
0x174b64  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174b69  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174b6e  ldloc.0
0x174b6f  ldstr    aUserkey_0// "@UserKey"
0x174b74  ldc.i4.s 0xC
0x174b76  ldc.i4   0xFF
0x174b7b  ldc.i4.0
0x174b7c  ldc.i4.0
0x174b7d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174b82  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174b87  ldloc.0
0x174b88  ldstr    aErrorcode_0// "@ErrorCode"
0x174b8d  ldc.i4.8
0x174b8e  ldc.i4.0
0x174b8f  ldc.i4.1
0x174b90  ldc.i4.0
0x174b91  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174b96  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174b9b  ldloc.0
0x174b9c  ldstr    aRequestguid// "@RequestGuid"
0x174ba1  ldc.i4.s 0xE
0x174ba3  ldc.i4.0
0x174ba4  ldc.i4.1
0x174ba5  ldc.i4.1
0x174ba6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174bab  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174bb0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x174bb5  stloc.0
0x174bb6  ldarg.0
0x174bb7  ldstr    aProcAmRemovere// "proc_AM_RemoveRegisteredOAuthAppId"
0x174bbc  ldloc.0
0x174bbd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x174bc2  ldloc.0
0x174bc3  ldstr    aReturnValue// "@RETURN_VALUE"
0x174bc8  ldc.i4.8
0x174bc9  ldc.i4.0
0x174bca  ldc.i4.1
0x174bcb  ldc.i4.0
0x174bcc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x174bd1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x174bd6  ldloc.0
  ... truncated ...
```
