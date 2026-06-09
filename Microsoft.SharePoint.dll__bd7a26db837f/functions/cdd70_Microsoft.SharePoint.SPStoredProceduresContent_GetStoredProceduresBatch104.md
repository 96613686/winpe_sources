# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch104

- ea: `0xcdd70`
- end: `0xced5c`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch104`
- size: `4076`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0xd24c0`

## callees

- `0x17e710`

## string_xrefs

- `0xcde13`: `@ExtraItemSize`
- `0xce817`: `@ServerTemplate`
- `0xce008`: `@tp_ThreadIndex`
- `0xce17f`: `@tp_Created`
- `0xce0b2`: `@tp_CopySource`
- `0xce0cb`: `@tp_HasCopyDestinations`
- `0xce2c8`: `@AclVersion`
- `0xce844`: `@ReadSecurity`
- `0xce858`: `@WriteSecurity`
- `0xcdd77`: `proc_UpdateListItem`
- `0xcdf3b`: `@SystemUpdate`
- `0xce0f3`: `@BumpLastDelete`
- `0xce107`: `@CreateItemVersion`
- `0xce2b4`: `@AccessControlFlags`
- `0xce30b`: `proc_UpdateListItemCount`
- `0xce355`: `@UpdateUserModified`
- `0xce36f`: `proc_UpdateListItemWorkflowInstanceData`
- `0xce53a`: `@WorkflowCompleted`
- `0xce5f6`: `proc_UpdateListItemWorkflowLock`
- `0xce6ac`: `proc_UpdateListNavNode`
- `0xce74d`: `@AddOrRemove`
- `0xce7a4`: `proc_UpdateListSettings`
- `0xce896`: `@TemplateDirName`
- `0xce8af`: `@TemplateLeafName`
- `0xcea13`: `@AddOrRemoveFromNavBar`
- `0xcea78`: `@RemoveSystemAlerts`
- `0xceb51`: `proc_UpdateListTemplateTypeForNavNodes`
- `0xceb9b`: `@UpdatedNavLinkCount`
- `0xcebca`: `proc_UpdateListViewFormWebPartSource`
- `0xcec44`: `proc_UpdateListViewToDataViewForSite`
- `0xcecd3`: `proc_UpdateListViewToDataViewForWeb`

## pseudocode

```c

```

## disassembly

```asm
0xcdd70  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xcdd75  stloc.0
0xcdd76  ldarg.0
0xcdd77  ldstr    aProcUpdatelist_3// "proc_UpdateListItem"
0xcdd7c  ldloc.0
0xcdd7d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xcdd82  ldloc.0
0xcdd83  ldstr    aReturnValue// "@RETURN_VALUE"
0xcdd88  ldc.i4.8
0xcdd89  ldc.i4.0
0xcdd8a  ldc.i4.1
0xcdd8b  ldc.i4.0
0xcdd8c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdd91  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdd96  ldloc.0
0xcdd97  ldstr    aSiteid_1// "@SiteId"
0xcdd9c  ldc.i4.s 0xE
0xcdd9e  ldc.i4.0
0xcdd9f  ldc.i4.0
0xcdda0  ldc.i4.0
0xcdda1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdda6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcddab  ldloc.0
0xcddac  ldstr    aWebid_0// "@WebId"
0xcddb1  ldc.i4.s 0xE
0xcddb3  ldc.i4.0
0xcddb4  ldc.i4.0
0xcddb5  ldc.i4.0
0xcddb6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcddbb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcddc0  ldloc.0
0xcddc1  ldstr    aListid_0// "@ListId"
0xcddc6  ldc.i4.s 0xE
0xcddc8  ldc.i4.0
0xcddc9  ldc.i4.0
0xcddca  ldc.i4.0
0xcddcb  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcddd0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcddd5  ldloc.0
0xcddd6  ldstr    aItemid// "@ItemId"
0xcdddb  ldc.i4.8
0xcdddc  ldc.i4.0
0xcdddd  ldc.i4.0
0xcddde  ldc.i4.0
0xcdddf  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdde4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdde9  ldloc.0
0xcddea  ldstr    aRowordinal// "@RowOrdinal"
0xcddef  ldc.i4.s 0x14
0xcddf1  ldc.i4.0
0xcddf2  ldc.i4.0
0xcddf3  ldc.i4.0
0xcddf4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcddf9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcddfe  ldloc.0
0xcddff  ldstr    aSize_0// "@Size"
0xcde04  ldc.i4.8
0xcde05  ldc.i4.0
0xcde06  ldc.i4.0
0xcde07  ldc.i4.0
0xcde08  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcde0d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcde12  ldloc.0
0xcde13  ldstr    aExtraitemsize// "@ExtraItemSize"
0xcde18  ldc.i4.8
0xcde19  ldc.i4.0
0xcde1a  ldc.i4.0
0xcde1b  ldc.i4.1
0xcde1c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcde21  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcde26  ldloc.0
0xcde27  ldstr    aItemname// "@ItemName"
0xcde2c  ldc.i4.s 0xC
0xcde2e  ldc.i4   0xFF
0xcde33  ldc.i4.0
0xcde34  ldc.i4.1
0xcde35  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcde3a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcde3f  ldloc.0
0xcde40  ldstr    aUsenvarchar1it// "@UseNvarchar1ItemName"
0xcde45  ldc.i4.2
0xcde46  ldc.i4.0
0xcde47  ldc.i4.0
0xcde48  ldc.i4.1
0xcde49  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcde4e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcde53  ldloc.0
0xcde54  ldstr    aItemdirname// "@ItemDirName"
0xcde59  ldc.i4.s 0xC
0xcde5b  ldc.i4   0x190
0xcde60  ldc.i4.1
0xcde61  ldc.i4.1
0xcde62  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcde67  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcde6c  ldloc.0
0xcde6d  ldstr    aItemleafname// "@ItemLeafName"
0xcde72  ldc.i4.s 0xC
0xcde74  ldc.i4   0x190
0xcde79  ldc.i4.1
0xcde7a  ldc.i4.1
0xcde7b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcde80  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcde85  ldloc.0
0xcde86  ldstr    aUserid_1// "@UserId"
0xcde8b  ldc.i4.8
0xcde8c  ldc.i4.0
0xcde8d  ldc.i4.0
0xcde8e  ldc.i4.0
0xcde8f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcde94  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcde99  ldloc.0
0xcde9a  ldstr    aLevel_1// "@Level"
0xcde9f  ldc.i4.s 0x14
0xcdea1  ldc.i4.0
0xcdea2  ldc.i4.1
0xcdea3  ldc.i4.1
0xcdea4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdea9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdeae  ldloc.0
0xcdeaf  ldstr    aTimenow// "@TimeNow"
0xcdeb4  ldc.i4.4
0xcdeb5  ldc.i4.0
0xcdeb6  ldc.i4.0
0xcdeb7  ldc.i4.0
0xcdeb8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdebd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdec2  ldloc.0
0xcdec3  ldstr    aNeedsauthorres// "@NeedsAuthorRestriction"
0xcdec8  ldc.i4.2
0xcdec9  ldc.i4.0
0xcdeca  ldc.i4.0
0xcdecb  ldc.i4.1
0xcdecc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcded1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcded6  ldloc.0
0xcded7  ldstr    aNeedsdraftowne// "@NeedsDraftOwnerRestriction"
0xcdedc  ldc.i4.2
0xcdedd  ldc.i4.0
0xcdede  ldc.i4.0
0xcdedf  ldc.i4.1
0xcdee0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdee5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdeea  ldloc.0
0xcdeeb  ldstr    aPreserveversio// "@PreserveVersion"
0xcdef0  ldc.i4.2
0xcdef1  ldc.i4.0
0xcdef2  ldc.i4.0
0xcdef3  ldc.i4.1
0xcdef4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdef9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdefe  ldloc.0
0xcdeff  ldstr    aIsmeetingslist// "@IsMeetingsList"
0xcdf04  ldc.i4.2
0xcdf05  ldc.i4.0
0xcdf06  ldc.i4.0
0xcdf07  ldc.i4.1
0xcdf08  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdf0d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdf12  ldloc.0
0xcdf13  ldstr    aIsissuelist// "@IsIssueList"
0xcdf18  ldc.i4.2
0xcdf19  ldc.i4.0
0xcdf1a  ldc.i4.0
0xcdf1b  ldc.i4.1
0xcdf1c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdf21  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdf26  ldloc.0
0xcdf27  ldstr    aIsnotuserdispl// "@IsNotUserDisplayed"
0xcdf2c  ldc.i4.2
0xcdf2d  ldc.i4.0
0xcdf2e  ldc.i4.0
0xcdf2f  ldc.i4.1
0xcdf30  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdf35  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdf3a  ldloc.0
0xcdf3b  ldstr    aSystemupdate// "@SystemUpdate"
0xcdf40  ldc.i4.2
0xcdf41  ldc.i4.0
0xcdf42  ldc.i4.0
0xcdf43  ldc.i4.1
0xcdf44  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdf49  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdf4e  ldloc.0
0xcdf4f  ldstr    aChangelevel// "@ChangeLevel"
0xcdf54  ldc.i4.2
0xcdf55  ldc.i4.0
0xcdf56  ldc.i4.0
0xcdf57  ldc.i4.1
0xcdf58  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdf5d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdf62  ldloc.0
0xcdf63  ldstr    aCheckinitem// "@CheckinItem"
0xcdf68  ldc.i4.2
0xcdf69  ldc.i4.0
0xcdf6a  ldc.i4.0
0xcdf6b  ldc.i4.1
0xcdf6c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdf71  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdf76  ldloc.0
0xcdf77  ldstr    aNeedclone// "@NeedClone"
0xcdf7c  ldc.i4.2
0xcdf7d  ldc.i4.0
0xcdf7e  ldc.i4.0
0xcdf7f  ldc.i4.1
0xcdf80  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdf85  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdf8a  ldloc.0
0xcdf8b  ldstr    aMajorversionsl// "@MajorVersionsLimit"
0xcdf90  ldc.i4.8
0xcdf91  ldc.i4.0
0xcdf92  ldc.i4.0
0xcdf93  ldc.i4.1
0xcdf94  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdf99  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdf9e  ldloc.0
0xcdf9f  ldstr    aMajorminorvers// "@MajorMinorVersionsLimit"
0xcdfa4  ldc.i4.8
0xcdfa5  ldc.i4.0
0xcdfa6  ldc.i4.0
0xcdfa7  ldc.i4.1
0xcdfa8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdfad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdfb2  ldloc.0
0xcdfb3  ldstr    aIsdoclib// "@IsDocLib"
0xcdfb8  ldc.i4.2
0xcdfb9  ldc.i4.0
0xcdfba  ldc.i4.0
0xcdfbb  ldc.i4.1
0xcdfbc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdfc1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdfc6  ldloc.0
0xcdfc7  ldstr    aCheckschemaver// "@CheckSchemaVersion"
0xcdfcc  ldc.i4.8
0xcdfcd  ldc.i4.0
0xcdfce  ldc.i4.0
0xcdfcf  ldc.i4.1
0xcdfd0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdfd5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdfda  ldloc.0
0xcdfdb  ldstr    aSorttyperevers// "@SortTypeReversed"
0xcdfe0  ldc.i4.2
0xcdfe1  ldc.i4.0
0xcdfe2  ldc.i4.0
0xcdfe3  ldc.i4.1
0xcdfe4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcdfe9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcdfee  ldloc.0
0xcdfef  ldstr    aTpOrdering// "@tp_Ordering"
0xcdff4  ldc.i4.s 0x16
0xcdff6  ldc.i4   0x200
0xcdffb  ldc.i4.0
0xcdffc  ldc.i4.1
0xcdffd  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xce002  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xce007  ldloc.0
0xce008  ldstr    aTpThreadindex// "@tp_ThreadIndex"
0xce00d  ldc.i4.s 0x15
0xce00f  ldc.i4   0x200
0xce014  ldc.i4.0
0xce015  ldc.i4.1
0xce016  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xce01b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xce020  ldloc.0
0xce021  ldstr    aTpHasattachmen// "@tp_HasAttachment"
0xce026  ldc.i4.2
0xce027  ldc.i4.0
0xce028  ldc.i4.0
0xce029  ldc.i4.1
0xce02a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xce02f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xce034  ldloc.0
0xce035  ldstr    aTpModerationst// "@tp_ModerationStatus"
0xce03a  ldc.i4.8
0xce03b  ldc.i4.0
0xce03c  ldc.i4.0
0xce03d  ldc.i4.1
0xce03e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xce043  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xce048  ldloc.0
0xce049  ldstr    aTpIscurrent// "@tp_IsCurrent"
0xce04e  ldc.i4.2
0xce04f  ldc.i4.0
0xce050  ldc.i4.0
0xce051  ldc.i4.1
0xce052  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xce057  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xce05c  ldloc.0
0xce05d  ldstr    aTpItemorder// "@tp_ItemOrder"
0xce062  ldc.i4.6
0xce063  ldc.i4.0
0xce064  ldc.i4.0
0xce065  ldc.i4.1
0xce066  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xce06b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xce070  ldloc.0
0xce071  ldstr    aTpVersion// "@tp_Version"
0xce076  ldc.i4.8
0xce077  ldc.i4.0
0xce078  ldc.i4.0
0xce079  ldc.i4.1
  ... truncated ...
```
