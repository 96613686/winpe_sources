# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch2

- ea: `0x95d40`
- end: `0x96b94`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch2`
- size: `3668`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0xd24c0`

## callees

- `0x17e6f0`
- `0x17e710`
- `0x2bc070`
- `0xabe9f0`

## string_xrefs

- `0x95dbb`: `@LinkData`
- `0x95e73`: `@LinkData`
- `0x95dcf`: `tvpLinkData256Leaf`
- `0x95e87`: `tvpLinkData400`
- `0x95d47`: `proc_AddLinksToDocInternal256Leaf`
- `0x95dff`: `proc_AddLinksToDocInternal400`
- `0x95f7b`: `@CopySecurityFromMasterID`
- `0x95f8f`: `@ExtraItemSize`
- `0x960ce`: `@ServerTemplate`
- `0x9615f`: `@tp_ThreadIndex`
- `0x96241`: `@tp_Created`
- `0x96282`: `@tp_CopySource`
- `0x9629b`: `@tp_HasCopyDestinations`
- `0x963c4`: `@AclVersion`
- `0x966a9`: `@UpdateQuota`
- `0x96848`: `@Cache`
- `0x968c4`: `@bDeleteUsersOtherWebParts`
- `0x9691c`: `proc_AddOrphanAbsBlobsToDeletedAbsBlobs`
- `0x96950`: `tvpDeletedDocStreamsInfo`
- `0x96980`: `proc_AddOrUpdateCustomAction`
- `0x96a8c`: `proc_AddOrUpdateSolutionFile`
- `0x96b15`: `@SolutionFilePath`

## pseudocode

```c

```

## disassembly

```asm
0x95d40  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x95d45  stloc.0
0x95d46  ldarg.0
0x95d47  ldstr    aProcAddlinksto_1// "proc_AddLinksToDocInternal256Leaf"
0x95d4c  ldloc.0
0x95d4d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x95d52  ldloc.0
0x95d53  ldstr    aReturnValue// "@RETURN_VALUE"
0x95d58  ldc.i4.8
0x95d59  ldc.i4.0
0x95d5a  ldc.i4.1
0x95d5b  ldc.i4.0
0x95d5c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95d61  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95d66  ldloc.0
0x95d67  ldstr    aSiteid_1// "@SiteId"
0x95d6c  ldc.i4.s 0xE
0x95d6e  ldc.i4.0
0x95d6f  ldc.i4.0
0x95d70  ldc.i4.0
0x95d71  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95d76  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95d7b  ldloc.0
0x95d7c  ldstr    aDocparentid// "@DocParentId"
0x95d81  ldc.i4.s 0xE
0x95d83  ldc.i4.0
0x95d84  ldc.i4.0
0x95d85  ldc.i4.0
0x95d86  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95d8b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95d90  ldloc.0
0x95d91  ldstr    aDocid_1// "@DocId"
0x95d96  ldc.i4.s 0xE
0x95d98  ldc.i4.0
0x95d99  ldc.i4.0
0x95d9a  ldc.i4.0
0x95d9b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95da0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95da5  ldloc.0
0x95da6  ldstr    aLevel_1// "@Level"
0x95dab  ldc.i4.s 0x14
0x95dad  ldc.i4.0
0x95dae  ldc.i4.0
0x95daf  ldc.i4.0
0x95db0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95db5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95dba  ldloc.0
0x95dbb  ldstr    aLinkdata// "@LinkData"
0x95dc0  ldstr    aContent// "Content"
0x95dc5  call     class Microsoft.SharePoint.Utilities.Sql.SqlSchema Microsoft.SharePoint.Utilities.Sql.Schema::GetSchema(string database)
0x95dca  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter> Microsoft.SharePoint.Utilities.Sql.SqlSchema::get_TVPs()
0x95dcf  ldstr    aTvplinkdata256// "tvpLinkData256Leaf"
0x95dd4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter>::get_Item(void)
0x95dd9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter tvpType)
0x95dde  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95de3  ldloc.0
0x95de4  ldstr    aRequestguid// "@RequestGuid"
0x95de9  ldc.i4.s 0xE
0x95deb  ldc.i4.0
0x95dec  ldc.i4.1
0x95ded  ldc.i4.1
0x95dee  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95df3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95df8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x95dfd  stloc.0
0x95dfe  ldarg.0
0x95dff  ldstr    aProcAddlinksto_2// "proc_AddLinksToDocInternal400"
0x95e04  ldloc.0
0x95e05  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x95e0a  ldloc.0
0x95e0b  ldstr    aReturnValue// "@RETURN_VALUE"
0x95e10  ldc.i4.8
0x95e11  ldc.i4.0
0x95e12  ldc.i4.1
0x95e13  ldc.i4.0
0x95e14  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95e19  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95e1e  ldloc.0
0x95e1f  ldstr    aSiteid_1// "@SiteId"
0x95e24  ldc.i4.s 0xE
0x95e26  ldc.i4.0
0x95e27  ldc.i4.0
0x95e28  ldc.i4.0
0x95e29  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95e2e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95e33  ldloc.0
0x95e34  ldstr    aDocparentid// "@DocParentId"
0x95e39  ldc.i4.s 0xE
0x95e3b  ldc.i4.0
0x95e3c  ldc.i4.0
0x95e3d  ldc.i4.0
0x95e3e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95e43  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95e48  ldloc.0
0x95e49  ldstr    aDocid_1// "@DocId"
0x95e4e  ldc.i4.s 0xE
0x95e50  ldc.i4.0
0x95e51  ldc.i4.0
0x95e52  ldc.i4.0
0x95e53  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95e58  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95e5d  ldloc.0
0x95e5e  ldstr    aLevel_1// "@Level"
0x95e63  ldc.i4.s 0x14
0x95e65  ldc.i4.0
0x95e66  ldc.i4.0
0x95e67  ldc.i4.0
0x95e68  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95e6d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95e72  ldloc.0
0x95e73  ldstr    aLinkdata// "@LinkData"
0x95e78  ldstr    aContent// "Content"
0x95e7d  call     class Microsoft.SharePoint.Utilities.Sql.SqlSchema Microsoft.SharePoint.Utilities.Sql.Schema::GetSchema(string database)
0x95e82  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter> Microsoft.SharePoint.Utilities.Sql.SqlSchema::get_TVPs()
0x95e87  ldstr    aTvplinkdata400// "tvpLinkData400"
0x95e8c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter>::get_Item(void)
0x95e91  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter tvpType)
0x95e96  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95e9b  ldloc.0
0x95e9c  ldstr    aRequestguid// "@RequestGuid"
0x95ea1  ldc.i4.s 0xE
0x95ea3  ldc.i4.0
0x95ea4  ldc.i4.1
0x95ea5  ldc.i4.1
0x95ea6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95eab  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95eb0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x95eb5  stloc.0
0x95eb6  ldarg.0
0x95eb7  ldstr    aProcAddlistite// "proc_AddListItem"
0x95ebc  ldloc.0
0x95ebd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x95ec2  ldloc.0
0x95ec3  ldstr    aReturnValue// "@RETURN_VALUE"
0x95ec8  ldc.i4.8
0x95ec9  ldc.i4.0
0x95eca  ldc.i4.1
0x95ecb  ldc.i4.0
0x95ecc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95ed1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95ed6  ldloc.0
0x95ed7  ldstr    aSiteid_1// "@SiteId"
0x95edc  ldc.i4.s 0xE
0x95ede  ldc.i4.0
0x95edf  ldc.i4.0
0x95ee0  ldc.i4.0
0x95ee1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95ee6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95eeb  ldloc.0
0x95eec  ldstr    aWebid_0// "@WebId"
0x95ef1  ldc.i4.s 0xE
0x95ef3  ldc.i4.0
0x95ef4  ldc.i4.0
0x95ef5  ldc.i4.0
0x95ef6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95efb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95f00  ldloc.0
0x95f01  ldstr    aListid_0// "@ListId"
0x95f06  ldc.i4.s 0xE
0x95f08  ldc.i4.0
0x95f09  ldc.i4.0
0x95f0a  ldc.i4.0
0x95f0b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95f10  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95f15  ldloc.0
0x95f16  ldstr    aRowordinal// "@RowOrdinal"
0x95f1b  ldc.i4.s 0x14
0x95f1d  ldc.i4.0
0x95f1e  ldc.i4.0
0x95f1f  ldc.i4.0
0x95f20  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95f25  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95f2a  ldloc.0
0x95f2b  ldstr    aItemid// "@ItemId"
0x95f30  ldc.i4.8
0x95f31  ldc.i4.0
0x95f32  ldc.i4.1
0x95f33  ldc.i4.0
0x95f34  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95f39  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95f3e  ldloc.0
0x95f3f  ldstr    aUserid_1// "@UserId"
0x95f44  ldc.i4.8
0x95f45  ldc.i4.0
0x95f46  ldc.i4.0
0x95f47  ldc.i4.0
0x95f48  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95f4d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95f52  ldloc.0
0x95f53  ldstr    aSize_0// "@Size"
0x95f58  ldc.i4.8
0x95f59  ldc.i4.0
0x95f5a  ldc.i4.0
0x95f5b  ldc.i4.0
0x95f5c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95f61  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95f66  ldloc.0
0x95f67  ldstr    aTimenow// "@TimeNow"
0x95f6c  ldc.i4.4
0x95f6d  ldc.i4.0
0x95f6e  ldc.i4.0
0x95f6f  ldc.i4.0
0x95f70  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95f75  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95f7a  ldloc.0
0x95f7b  ldstr    aCopysecurityfr// "@CopySecurityFromMasterID"
0x95f80  ldc.i4.8
0x95f81  ldc.i4.0
0x95f82  ldc.i4.0
0x95f83  ldc.i4.1
0x95f84  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95f89  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95f8e  ldloc.0
0x95f8f  ldstr    aExtraitemsize// "@ExtraItemSize"
0x95f94  ldc.i4.8
0x95f95  ldc.i4.0
0x95f96  ldc.i4.0
0x95f97  ldc.i4.1
0x95f98  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95f9d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95fa2  ldloc.0
0x95fa3  ldstr    aCheckdiskquota// "@CheckDiskQuota"
0x95fa8  ldc.i4.2
0x95fa9  ldc.i4.0
0x95faa  ldc.i4.0
0x95fab  ldc.i4.1
0x95fac  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95fb1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95fb6  ldloc.0
0x95fb7  ldstr    aItemdoctype// "@ItemDocType"
0x95fbc  ldc.i4.s 0x14
0x95fbe  ldc.i4.0
0x95fbf  ldc.i4.0
0x95fc0  ldc.i4.1
0x95fc1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95fc6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95fcb  ldloc.0
0x95fcc  ldstr    aSorttyperevers// "@SortTypeReversed"
0x95fd1  ldc.i4.2
0x95fd2  ldc.i4.0
0x95fd3  ldc.i4.0
0x95fd4  ldc.i4.1
0x95fd5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95fda  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95fdf  ldloc.0
0x95fe0  ldstr    aBaserowitemid// "@BaseRowItemId"
0x95fe5  ldc.i4.8
0x95fe6  ldc.i4.0
0x95fe7  ldc.i4.0
0x95fe8  ldc.i4.1
0x95fe9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x95fee  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x95ff3  ldloc.0
0x95ff4  ldstr    aDocidadded// "@DocIdAdded"
0x95ff9  ldc.i4.s 0xE
0x95ffb  ldc.i4.0
0x95ffc  ldc.i4.0
0x95ffd  ldc.i4.1
0x95ffe  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x96003  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x96008  ldloc.0
0x96009  ldstr    aRetainid// "@RetainId"
0x9600e  ldc.i4.s 0xE
0x96010  ldc.i4.0
0x96011  ldc.i4.0
0x96012  ldc.i4.1
0x96013  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x96018  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9601d  ldloc.0
0x9601e  ldstr    aRetainobjectid// "@RetainObjectIdentity"
0x96023  ldc.i4.2
0x96024  ldc.i4.0
0x96025  ldc.i4.0
0x96026  ldc.i4.1
0x96027  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9602c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x96031  ldloc.0
0x96032  ldstr    aLevel_1// "@Level"
0x96037  ldc.i4.s 0x14
0x96039  ldc.i4.0
0x9603a  ldc.i4.0
0x9603b  ldc.i4.1
0x9603c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x96041  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x96046  ldloc.0
0x96047  ldstr    aUiversion_1// "@UIVersion"
0x9604c  ldc.i4.8
0x9604d  ldc.i4.0
0x9604e  ldc.i4.0
0x9604f  ldc.i4.1
0x96050  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x96055  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9605a  ldloc.0
0x9605b  ldstr    aItemcountdelta// "@ItemCountDelta"
0x96060  ldc.i4.8
0x96061  ldc.i4.0
0x96062  ldc.i4.0
0x96063  ldc.i4.1
0x96064  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x96069  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
  ... truncated ...
```
