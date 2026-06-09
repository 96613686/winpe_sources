# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch102

- ea: `0xcc190`
- end: `0xcd324`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch102`
- size: `4500`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0xd24c0`

## callees

- `0x17e6f0`
- `0x17e710`
- `0x2bc070`
- `0xabe9f0`

## string_xrefs

- `0xcc5c5`: `@DocIncomingCreatedDTM`
- `0xccaf5`: `@DocIncomingCreatedDTM`
- `0xcc5d9`: `@DocIncomingDTM`
- `0xccb09`: `@DocIncomingDTM`
- `0xcc6e2`: `@Comment`
- `0xccc12`: `@Comment`
- `0xcc197`: `proc_UpdateDocBuildDependencySet`
- `0xcc243`: `proc_UpdateDocCommentsTotalSize`
- `0xcc2a7`: `proc_UpdateDocEventReceiver`
- `0xcc41b`: `proc_UpdateDocStreamForCompression`
- `0xcc43b`: `@CompressedBlobs`
- `0xcc44f`: `tvpABSStreamDataCompressedUpdate`
- `0xcc47f`: `proc_UpdateDocument`
- `0xcc679`: `@UpdateFlags`
- `0xccba9`: `@UpdateFlags`
- `0xcc723`: `@WelcomePageUrl`
- `0xccc53`: `@WelcomePageUrl`
- `0xcc73c`: `@WelcomePageParameters`
- `0xccc6c`: `@WelcomePageParameters`
- `0xcc80d`: `@FileFragmentPartitionsToDelete`
- `0xccd3d`: `@FileFragmentPartitionsToDelete`
- `0xcc822`: `@PartitionsToDelete`
- `0xccd52`: `@PartitionsToDelete`
- `0xcc9af`: `proc_UpdateDocument2`
- `0xccedf`: `proc_UpdateDocUserActionsCountsInternal`
- `0xccf81`: `proc_UpdateEntityIdForList`
- `0xccffa`: `proc_UpdateEventReceiver`
- `0xcd273`: `proc_UpdateFeatureProperties`

## pseudocode

```c

```

## disassembly

```asm
0xcc190  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xcc195  stloc.0
0xcc196  ldarg.0
0xcc197  ldstr    aProcUpdatedocb// "proc_UpdateDocBuildDependencySet"
0xcc19c  ldloc.0
0xcc19d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xcc1a2  ldloc.0
0xcc1a3  ldstr    aReturnValue// "@RETURN_VALUE"
0xcc1a8  ldc.i4.8
0xcc1a9  ldc.i4.0
0xcc1aa  ldc.i4.1
0xcc1ab  ldc.i4.0
0xcc1ac  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc1b1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc1b6  ldloc.0
0xcc1b7  ldstr    aDocsiteid// "@DocSiteId"
0xcc1bc  ldc.i4.s 0xE
0xcc1be  ldc.i4.0
0xcc1bf  ldc.i4.0
0xcc1c0  ldc.i4.0
0xcc1c1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc1c6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc1cb  ldloc.0
0xcc1cc  ldstr    aDocdirname// "@DocDirName"
0xcc1d1  ldc.i4.s 0xC
0xcc1d3  ldc.i4   0x190
0xcc1d8  ldc.i4.0
0xcc1d9  ldc.i4.0
0xcc1da  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc1df  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc1e4  ldloc.0
0xcc1e5  ldstr    aDocleafname// "@DocLeafName"
0xcc1ea  ldc.i4.s 0xC
0xcc1ec  ldc.i4   0x190
0xcc1f1  ldc.i4.0
0xcc1f2  ldc.i4.0
0xcc1f3  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc1f8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc1fd  ldloc.0
0xcc1fe  ldstr    aLevel_1// "@Level"
0xcc203  ldc.i4.s 0x14
0xcc205  ldc.i4.0
0xcc206  ldc.i4.0
0xcc207  ldc.i4.0
0xcc208  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc20d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc212  ldloc.0
0xcc213  ldstr    aBuilddependenc// "@BuildDependencySet"
0xcc218  ldc.i4.s 0x15
0xcc21a  ldc.i4.m1
0xcc21b  ldc.i4.0
0xcc21c  ldc.i4.0
0xcc21d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc222  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc227  ldloc.0
0xcc228  ldstr    aRequestguid// "@RequestGuid"
0xcc22d  ldc.i4.s 0xE
0xcc22f  ldc.i4.0
0xcc230  ldc.i4.1
0xcc231  ldc.i4.1
0xcc232  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc237  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc23c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xcc241  stloc.0
0xcc242  ldarg.0
0xcc243  ldstr    aProcUpdatedocc// "proc_UpdateDocCommentsTotalSize"
0xcc248  ldloc.0
0xcc249  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xcc24e  ldloc.0
0xcc24f  ldstr    aReturnValue// "@RETURN_VALUE"
0xcc254  ldc.i4.8
0xcc255  ldc.i4.0
0xcc256  ldc.i4.1
0xcc257  ldc.i4.0
0xcc258  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc25d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc262  ldloc.0
0xcc263  ldstr    aSiteid_1// "@SiteId"
0xcc268  ldc.i4.s 0xE
0xcc26a  ldc.i4.0
0xcc26b  ldc.i4.0
0xcc26c  ldc.i4.0
0xcc26d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc272  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc277  ldloc.0
0xcc278  ldstr    aDocid_1// "@DocId"
0xcc27d  ldc.i4.s 0xE
0xcc27f  ldc.i4.0
0xcc280  ldc.i4.0
0xcc281  ldc.i4.0
0xcc282  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc287  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc28c  ldloc.0
0xcc28d  ldstr    aDelta// "@Delta"
0xcc292  ldc.i4.0
0xcc293  ldc.i4.0
0xcc294  ldc.i4.0
0xcc295  ldc.i4.0
0xcc296  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc29b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc2a0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xcc2a5  stloc.0
0xcc2a6  ldarg.0
0xcc2a7  ldstr    aProcUpdatedoce// "proc_UpdateDocEventReceiver"
0xcc2ac  ldloc.0
0xcc2ad  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xcc2b2  ldloc.0
0xcc2b3  ldstr    aReturnValue// "@RETURN_VALUE"
0xcc2b8  ldc.i4.8
0xcc2b9  ldc.i4.0
0xcc2ba  ldc.i4.1
0xcc2bb  ldc.i4.0
0xcc2bc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc2c1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc2c6  ldloc.0
0xcc2c7  ldstr    aDocurl// "@DocUrl"
0xcc2cc  ldc.i4.s 0xC
0xcc2ce  ldc.i4   0x190
0xcc2d3  ldc.i4.0
0xcc2d4  ldc.i4.0
0xcc2d5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc2da  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc2df  ldloc.0
0xcc2e0  ldstr    aId_1// "@Id"
0xcc2e5  ldc.i4.s 0xE
0xcc2e7  ldc.i4.0
0xcc2e8  ldc.i4.0
0xcc2e9  ldc.i4.0
0xcc2ea  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc2ef  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc2f4  ldloc.0
0xcc2f5  ldstr    aName_1// "@Name"
0xcc2fa  ldc.i4.s 0xC
0xcc2fc  ldc.i4   0x100
0xcc301  ldc.i4.0
0xcc302  ldc.i4.0
0xcc303  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc308  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc30d  ldloc.0
0xcc30e  ldstr    aSiteid_1// "@SiteId"
0xcc313  ldc.i4.s 0xE
0xcc315  ldc.i4.0
0xcc316  ldc.i4.0
0xcc317  ldc.i4.0
0xcc318  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc31d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc322  ldloc.0
0xcc323  ldstr    aWebid_0// "@WebId"
0xcc328  ldc.i4.s 0xE
0xcc32a  ldc.i4.0
0xcc32b  ldc.i4.0
0xcc32c  ldc.i4.0
0xcc32d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc332  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc337  ldloc.0
0xcc338  ldstr    aItemid// "@ItemId"
0xcc33d  ldc.i4.8
0xcc33e  ldc.i4.0
0xcc33f  ldc.i4.0
0xcc340  ldc.i4.0
0xcc341  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc346  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc34b  ldloc.0
0xcc34c  ldstr    aSynchronizatio// "@Synchronization"
0xcc351  ldc.i4.8
0xcc352  ldc.i4.0
0xcc353  ldc.i4.0
0xcc354  ldc.i4.0
0xcc355  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc35a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc35f  ldloc.0
0xcc360  ldstr    aType_2// "@Type"
0xcc365  ldc.i4.8
0xcc366  ldc.i4.0
0xcc367  ldc.i4.0
0xcc368  ldc.i4.0
0xcc369  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc36e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc373  ldloc.0
0xcc374  ldstr    aSequencenumber_0// "@SequenceNumber"
0xcc379  ldc.i4.8
0xcc37a  ldc.i4.0
0xcc37b  ldc.i4.0
0xcc37c  ldc.i4.0
0xcc37d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc382  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc387  ldloc.0
0xcc388  ldstr    aAssembly// "@Assembly"
0xcc38d  ldc.i4.s 0xC
0xcc38f  ldc.i4   0x100
0xcc394  ldc.i4.0
0xcc395  ldc.i4.0
0xcc396  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc39b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc3a0  ldloc.0
0xcc3a1  ldstr    aClass// "@Class"
0xcc3a6  ldc.i4.s 0xC
0xcc3a8  ldc.i4   0x100
0xcc3ad  ldc.i4.0
0xcc3ae  ldc.i4.0
0xcc3af  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc3b4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc3b9  ldloc.0
0xcc3ba  ldstr    aData_1// "@Data"
0xcc3bf  ldc.i4.s 0xC
0xcc3c1  ldc.i4   0x100
0xcc3c6  ldc.i4.0
0xcc3c7  ldc.i4.0
0xcc3c8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc3cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc3d2  ldloc.0
0xcc3d3  ldstr    aFilter// "@Filter"
0xcc3d8  ldc.i4.s 0xC
0xcc3da  ldc.i4   0x100
0xcc3df  ldc.i4.0
0xcc3e0  ldc.i4.0
0xcc3e1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc3e6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc3eb  ldloc.0
0xcc3ec  ldstr    aCredential// "@Credential"
0xcc3f1  ldc.i4.8
0xcc3f2  ldc.i4.0
0xcc3f3  ldc.i4.0
0xcc3f4  ldc.i4.0
0xcc3f5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc3fa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc3ff  ldloc.0
0xcc400  ldstr    aRequestguid// "@RequestGuid"
0xcc405  ldc.i4.s 0xE
0xcc407  ldc.i4.0
0xcc408  ldc.i4.1
0xcc409  ldc.i4.1
0xcc40a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc40f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc414  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xcc419  stloc.0
0xcc41a  ldarg.0
0xcc41b  ldstr    aProcUpdatedocs// "proc_UpdateDocStreamForCompression"
0xcc420  ldloc.0
0xcc421  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xcc426  ldloc.0
0xcc427  ldstr    aReturnValue// "@RETURN_VALUE"
0xcc42c  ldc.i4.8
0xcc42d  ldc.i4.0
0xcc42e  ldc.i4.1
0xcc42f  ldc.i4.0
0xcc430  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc435  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc43a  ldloc.0
0xcc43b  ldstr    aCompressedblob// "@CompressedBlobs"
0xcc440  ldstr    aContent// "Content"
0xcc445  call     class Microsoft.SharePoint.Utilities.Sql.SqlSchema Microsoft.SharePoint.Utilities.Sql.Schema::GetSchema(string database)
0xcc44a  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter> Microsoft.SharePoint.Utilities.Sql.SqlSchema::get_TVPs()
0xcc44f  ldstr    aTvpabsstreamda_2// "tvpABSStreamDataCompressedUpdate"
0xcc454  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter>::get_Item(void)
0xcc459  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, class Microsoft.SharePoint.Utilities.Sql.TableValuedParameter tvpType)
0xcc45e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc463  ldloc.0
0xcc464  ldstr    aRequestguid// "@RequestGuid"
0xcc469  ldc.i4.s 0xE
0xcc46b  ldc.i4.0
0xcc46c  ldc.i4.1
0xcc46d  ldc.i4.1
0xcc46e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc473  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc478  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xcc47d  stloc.0
0xcc47e  ldarg.0
0xcc47f  ldstr    aProcUpdatedocu// "proc_UpdateDocument"
0xcc484  ldloc.0
0xcc485  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xcc48a  ldloc.0
0xcc48b  ldstr    aReturnValue// "@RETURN_VALUE"
0xcc490  ldc.i4.8
0xcc491  ldc.i4.0
0xcc492  ldc.i4.1
0xcc493  ldc.i4.0
0xcc494  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc499  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc49e  ldloc.0
0xcc49f  ldstr    aDocsiteid// "@DocSiteId"
0xcc4a4  ldc.i4.s 0xE
0xcc4a6  ldc.i4.0
0xcc4a7  ldc.i4.0
0xcc4a8  ldc.i4.0
0xcc4a9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc4ae  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc4b3  ldloc.0
0xcc4b4  ldstr    aDocwebid// "@DocWebId"
0xcc4b9  ldc.i4.s 0xE
0xcc4bb  ldc.i4.0
0xcc4bc  ldc.i4.0
0xcc4bd  ldc.i4.0
0xcc4be  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcc4c3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcc4c8  ldloc.0
0xcc4c9  ldstr    aDocdirname// "@DocDirName"
0xcc4ce  ldc.i4.s 0xC
0xcc4d0  ldc.i4   0x190
0xcc4d5  ldc.i4.0
  ... truncated ...
```
