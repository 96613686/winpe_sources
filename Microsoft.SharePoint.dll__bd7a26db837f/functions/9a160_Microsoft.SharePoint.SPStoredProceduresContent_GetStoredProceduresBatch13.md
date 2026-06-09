# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch13

- ea: `0x9a160`
- end: `0x9a8cf`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch13`
- size: `1903`
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

- `0x9a868`: `@DeleteTransactionId`
- `0x9a167`: `proc_App_UpdateDownloadProgress`
- `0x9a1cb`: `proc_App_WritePackageStream`
- `0x9a469`: `@DeferUpdateDiskUsed`
- `0x9a570`: `@DeferUpdateDiskUsed`
- `0x9a50a`: `@TemplateId`
- `0x9a51f`: `@AutoCleanupDate`
- `0x9a533`: `@ForceDelete`
- `0x9a58a`: `proc_CalculateAndUpdateSiteDiskUsed`
- `0x9a68f`: `proc_CascadeDeleteItems`
- `0x9a71b`: `@ParentServerTemplate`
- `0x9a758`: `@ParentAcl`
- `0x9a781`: `@ParentListDeletedUrls`
- `0x9a83b`: `@DeleteOp`
- `0x9a87e`: `@DeleteFlags`
- `0x9a8bb`: `@ParentAclVersion`

## pseudocode

```c

```

## disassembly

```asm
0x9a160  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9a165  stloc.0
0x9a166  ldarg.0
0x9a167  ldstr    aProcAppUpdated// "proc_App_UpdateDownloadProgress"
0x9a16c  ldloc.0
0x9a16d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9a172  ldloc.0
0x9a173  ldstr    aReturnValue// "@RETURN_VALUE"
0x9a178  ldc.i4.8
0x9a179  ldc.i4.0
0x9a17a  ldc.i4.1
0x9a17b  ldc.i4.0
0x9a17c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a181  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a186  ldloc.0
0x9a187  ldstr    aPackagefingerp// "@PackageFingerprint"
0x9a18c  ldc.i4.1
0x9a18d  ldc.i4.s 0x40
0x9a18f  ldc.i4.0
0x9a190  ldc.i4.0
0x9a191  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a196  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a19b  ldloc.0
0x9a19c  ldstr    aDownloadprogre// "@DownloadProgress"
0x9a1a1  ldc.i4.6
0x9a1a2  ldc.i4.0
0x9a1a3  ldc.i4.0
0x9a1a4  ldc.i4.0
0x9a1a5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a1aa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a1af  ldloc.0
0x9a1b0  ldstr    aSiteid_1// "@SiteId"
0x9a1b5  ldc.i4.s 0xE
0x9a1b7  ldc.i4.0
0x9a1b8  ldc.i4.0
0x9a1b9  ldc.i4.0
0x9a1ba  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a1bf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a1c4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9a1c9  stloc.0
0x9a1ca  ldarg.0
0x9a1cb  ldstr    aProcAppWritepa// "proc_App_WritePackageStream"
0x9a1d0  ldloc.0
0x9a1d1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9a1d6  ldloc.0
0x9a1d7  ldstr    aReturnValue// "@RETURN_VALUE"
0x9a1dc  ldc.i4.8
0x9a1dd  ldc.i4.0
0x9a1de  ldc.i4.1
0x9a1df  ldc.i4.0
0x9a1e0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a1e5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a1ea  ldloc.0
0x9a1eb  ldstr    aPackagefingerp// "@PackageFingerprint"
0x9a1f0  ldc.i4.1
0x9a1f1  ldc.i4.s 0x40
0x9a1f3  ldc.i4.0
0x9a1f4  ldc.i4.0
0x9a1f5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a1fa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a1ff  ldloc.0
0x9a200  ldstr    aStreamdata// "@StreamData"
0x9a205  ldstr    aContent// "Content"
0x9a20a  call     class Microsoft.SharePoint.Utilities.Sql.SqlSchema Microsoft.SharePoint.Utilities.Sql.Schema::GetSchema(string database)
0x9a20f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter> Microsoft.SharePoint.Utilities.Sql.SqlSchema::get_TVPs()
0x9a214  ldstr    aTvpstreamdata// "tvpStreamData"
0x9a219  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter>::get_Item(void)
0x9a21e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter tvpType)
0x9a223  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a228  ldloc.0
0x9a229  ldstr    aSiteid_1// "@SiteId"
0x9a22e  ldc.i4.s 0xE
0x9a230  ldc.i4.0
0x9a231  ldc.i4.0
0x9a232  ldc.i4.0
0x9a233  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a238  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a23d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9a242  stloc.0
0x9a243  ldarg.0
0x9a244  ldstr    aProcAppendfile// "proc_AppendFileFragmentDataById"
0x9a249  ldloc.0
0x9a24a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9a24f  ldloc.0
0x9a250  ldstr    aReturnValue// "@RETURN_VALUE"
0x9a255  ldc.i4.8
0x9a256  ldc.i4.0
0x9a257  ldc.i4.1
0x9a258  ldc.i4.0
0x9a259  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a25e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a263  ldloc.0
0x9a264  ldstr    aSiteid_1// "@SiteId"
0x9a269  ldc.i4.s 0xE
0x9a26b  ldc.i4.0
0x9a26c  ldc.i4.0
0x9a26d  ldc.i4.0
0x9a26e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a273  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a278  ldloc.0
0x9a279  ldstr    aDocid_1// "@DocId"
0x9a27e  ldc.i4.s 0xE
0x9a280  ldc.i4.0
0x9a281  ldc.i4.0
0x9a282  ldc.i4.0
0x9a283  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a288  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a28d  ldloc.0
0x9a28e  ldstr    aDocversion// "@DocVersion"
0x9a293  ldc.i4.8
0x9a294  ldc.i4.0
0x9a295  ldc.i4.0
0x9a296  ldc.i4.0
0x9a297  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a29c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a2a1  ldloc.0
0x9a2a2  ldstr    aUserid_1// "@UserId"
0x9a2a7  ldc.i4.8
0x9a2a8  ldc.i4.0
0x9a2a9  ldc.i4.0
0x9a2aa  ldc.i4.0
0x9a2ab  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a2b0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a2b5  ldloc.0
0x9a2b6  ldstr    aPartition_1// "@Partition"
0x9a2bb  ldc.i4.s 0x14
0x9a2bd  ldc.i4.0
0x9a2be  ldc.i4.0
0x9a2bf  ldc.i4.0
0x9a2c0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a2c5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a2ca  ldloc.0
0x9a2cb  ldstr    aId_1// "@Id"
0x9a2d0  ldc.i4.0
0x9a2d1  ldc.i4.0
0x9a2d2  ldc.i4.0
0x9a2d3  ldc.i4.0
0x9a2d4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a2d9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a2de  ldloc.0
0x9a2df  ldstr    aBlobdata// "@BlobData"
0x9a2e4  ldc.i4.s 0x15
0x9a2e6  ldc.i4.m1
0x9a2e7  ldc.i4.0
0x9a2e8  ldc.i4.0
0x9a2e9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a2ee  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a2f3  ldloc.0
0x9a2f4  ldstr    aBlobsize_0// "@BlobSize"
0x9a2f9  ldc.i4.8
0x9a2fa  ldc.i4.0
0x9a2fb  ldc.i4.0
0x9a2fc  ldc.i4.0
0x9a2fd  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a302  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a307  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9a30c  stloc.0
0x9a30d  ldarg.0
0x9a30e  ldstr    aProcApplyviewt// "proc_ApplyViewToListWebPart"
0x9a313  ldloc.0
0x9a314  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9a319  ldloc.0
0x9a31a  ldstr    aReturnValue// "@RETURN_VALUE"
0x9a31f  ldc.i4.8
0x9a320  ldc.i4.0
0x9a321  ldc.i4.1
0x9a322  ldc.i4.0
0x9a323  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a328  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a32d  ldloc.0
0x9a32e  ldstr    aSiteid_1// "@SiteId"
0x9a333  ldc.i4.s 0xE
0x9a335  ldc.i4.0
0x9a336  ldc.i4.0
0x9a337  ldc.i4.0
0x9a338  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a33d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a342  ldloc.0
0x9a343  ldstr    aDirname_0// "@DirName"
0x9a348  ldc.i4.s 0xC
0x9a34a  ldc.i4   0x190
0x9a34f  ldc.i4.0
0x9a350  ldc.i4.0
0x9a351  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a356  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a35b  ldloc.0
0x9a35c  ldstr    aLeafname// "@LeafName"
0x9a361  ldc.i4.s 0xC
0x9a363  ldc.i4   0x190
0x9a368  ldc.i4.0
0x9a369  ldc.i4.0
0x9a36a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a36f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a374  ldloc.0
0x9a375  ldstr    aLevel_1// "@Level"
0x9a37a  ldc.i4.s 0x14
0x9a37c  ldc.i4.0
0x9a37d  ldc.i4.1
0x9a37e  ldc.i4.0
0x9a37f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a384  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a389  ldloc.0
0x9a38a  ldstr    aWebpartid// "@WebPartId"
0x9a38f  ldc.i4.s 0xE
0x9a391  ldc.i4.0
0x9a392  ldc.i4.0
0x9a393  ldc.i4.0
0x9a394  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a399  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a39e  ldloc.0
0x9a39f  ldstr    aViewid// "@ViewId"
0x9a3a4  ldc.i4.s 0xE
0x9a3a6  ldc.i4.0
0x9a3a7  ldc.i4.0
0x9a3a8  ldc.i4.0
0x9a3a9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a3ae  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a3b3  ldloc.0
0x9a3b4  ldstr    aUserid_1// "@UserId"
0x9a3b9  ldc.i4.8
0x9a3ba  ldc.i4.0
0x9a3bb  ldc.i4.0
0x9a3bc  ldc.i4.0
0x9a3bd  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a3c2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a3c7  ldloc.0
0x9a3c8  ldstr    aVieweditperms// "@ViewEditPerms"
0x9a3cd  ldc.i4.8
0x9a3ce  ldc.i4.0
0x9a3cf  ldc.i4.0
0x9a3d0  ldc.i4.0
0x9a3d1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a3d6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a3db  ldloc.0
0x9a3dc  ldstr    aViewbody// "@ViewBody"
0x9a3e1  ldc.i4.s 0x15
0x9a3e3  ldc.i4.m1
0x9a3e4  ldc.i4.0
0x9a3e5  ldc.i4.0
0x9a3e6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a3eb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a3f0  ldloc.0
0x9a3f1  ldstr    aViewflags// "@ViewFlags"
0x9a3f6  ldc.i4.8
0x9a3f7  ldc.i4.0
0x9a3f8  ldc.i4.1
0x9a3f9  ldc.i4.0
0x9a3fa  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a3ff  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a404  ldloc.0
0x9a405  ldstr    aBaseviewid// "@BaseViewId"
0x9a40a  ldc.i4.8
0x9a40b  ldc.i4.0
0x9a40c  ldc.i4.1
0x9a40d  ldc.i4.0
0x9a40e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a413  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a418  ldloc.0
0x9a419  ldstr    aRequestguid// "@RequestGuid"
0x9a41e  ldc.i4.s 0xE
0x9a420  ldc.i4.0
0x9a421  ldc.i4.1
0x9a422  ldc.i4.1
0x9a423  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a428  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a42d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9a432  stloc.0
0x9a433  ldarg.0
0x9a434  ldstr    aProcAutocleanu// "proc_AutoCleanupWorkflows"
0x9a439  ldloc.0
0x9a43a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9a43f  ldloc.0
0x9a440  ldstr    aReturnValue// "@RETURN_VALUE"
0x9a445  ldc.i4.8
0x9a446  ldc.i4.0
0x9a447  ldc.i4.1
0x9a448  ldc.i4.0
0x9a449  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a44e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a453  ldloc.0
0x9a454  ldstr    aRequestguid// "@RequestGuid"
0x9a459  ldc.i4.s 0xE
0x9a45b  ldc.i4.0
0x9a45c  ldc.i4.1
0x9a45d  ldc.i4.1
0x9a45e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a463  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a468  ldloc.0
0x9a469  ldstr    aDeferupdatedis// "@DeferUpdateDiskUsed"
0x9a46e  ldc.i4.2
0x9a46f  ldc.i4.0
0x9a470  ldc.i4.0
0x9a471  ldc.i4.1
0x9a472  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9a477  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9a47c  ldloc.0
0x9a47d  ldstr    aDropall// "@DropAll"
0x9a482  ldc.i4.8
0x9a483  ldc.i4.0
0x9a484  ldc.i4.0
  ... truncated ...
```
