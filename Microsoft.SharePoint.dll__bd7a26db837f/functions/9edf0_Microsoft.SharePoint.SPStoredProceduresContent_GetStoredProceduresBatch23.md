# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch23

- ea: `0x9edf0`
- end: `0x9f69b`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch23`
- size: `2219`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0xd24c0`

## callees

- `0x17e6f0`
- `0x17e710`
- `0x2bc070`
- `0xabe9f0`

## string_xrefs

- `0x9ef8d`: `@UpdateQuota`
- `0x9f0a8`: `@UpdateQuota`
- `0x9f3e3`: `@DeleteTransactionId`
- `0x9f5eb`: `@DeleteTransactionId`
- `0x9f32e`: `@DeleteOp`
- `0x9edf7`: `proc_DeleteFieldTemplateInScope`
- `0x9eea2`: `proc_DeleteFileFragmentsById`
- `0x9ef51`: `@DeleteUntil`
- `0x9f080`: `@DeleteUntil`
- `0x9ef65`: `@DeleteOnly`
- `0x9efbb`: `proc_DeleteFileFragmentsByTag`
- `0x9f0d6`: `proc_DeleteFromNVP`
- `0x9f14f`: `proc_DeleteFromNVPBatched`
- `0x9f1c7`: `proc_DeleteInProgressWorkItems`
- `0x9f26b`: `proc_DeleteItemVersion`
- `0x9f35d`: `proc_DeleteRecycleBinItem`
- `0x9f485`: `proc_DeleteRecycleBinItemTVP`
- `0x9f51f`: `@DeleteTransactionData`
- `0x9f533`: `tvpDeleteTransactionData`
- `0x9f548`: `@FailedDeleteTransactionId`
- `0x9f579`: `proc_DeleteRecycleBinItemV2`

## pseudocode

```c

```

## disassembly

```asm
0x9edf0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9edf5  stloc.0
0x9edf6  ldarg.0
0x9edf7  ldstr    aProcDeletefiel// "proc_DeleteFieldTemplateInScope"
0x9edfc  ldloc.0
0x9edfd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9ee02  ldloc.0
0x9ee03  ldstr    aReturnValue// "@RETURN_VALUE"
0x9ee08  ldc.i4.8
0x9ee09  ldc.i4.0
0x9ee0a  ldc.i4.1
0x9ee0b  ldc.i4.0
0x9ee0c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ee11  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ee16  ldloc.0
0x9ee17  ldstr    aSiteid_1// "@SiteId"
0x9ee1c  ldc.i4.s 0xE
0x9ee1e  ldc.i4.0
0x9ee1f  ldc.i4.0
0x9ee20  ldc.i4.0
0x9ee21  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ee26  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ee2b  ldloc.0
0x9ee2c  ldstr    aScope_1// "@Scope"
0x9ee31  ldc.i4.s 0xC
0x9ee33  ldc.i4   0x100
0x9ee38  ldc.i4.0
0x9ee39  ldc.i4.0
0x9ee3a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ee3f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ee44  ldloc.0
0x9ee45  ldstr    aFieldid// "@FieldId"
0x9ee4a  ldc.i4.s 0xE
0x9ee4c  ldc.i4.0
0x9ee4d  ldc.i4.0
0x9ee4e  ldc.i4.0
0x9ee4f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ee54  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ee59  ldloc.0
0x9ee5a  ldstr    aFieldname// "@FieldName"
0x9ee5f  ldc.i4.s 0xC
0x9ee61  ldc.i4   0x100
0x9ee66  ldc.i4.0
0x9ee67  ldc.i4.0
0x9ee68  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ee6d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ee72  ldloc.0
0x9ee73  ldstr    aBasetypes// "@BaseTypes"
0x9ee78  ldc.i4.8
0x9ee79  ldc.i4.0
0x9ee7a  ldc.i4.0
0x9ee7b  ldc.i4.0
0x9ee7c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ee81  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ee86  ldloc.0
0x9ee87  ldstr    aRequestguid// "@RequestGuid"
0x9ee8c  ldc.i4.s 0xE
0x9ee8e  ldc.i4.0
0x9ee8f  ldc.i4.1
0x9ee90  ldc.i4.1
0x9ee91  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ee96  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ee9b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9eea0  stloc.0
0x9eea1  ldarg.0
0x9eea2  ldstr    aProcDeletefile// "proc_DeleteFileFragmentsById"
0x9eea7  ldloc.0
0x9eea8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9eead  ldloc.0
0x9eeae  ldstr    aReturnValue// "@RETURN_VALUE"
0x9eeb3  ldc.i4.8
0x9eeb4  ldc.i4.0
0x9eeb5  ldc.i4.1
0x9eeb6  ldc.i4.0
0x9eeb7  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9eebc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9eec1  ldloc.0
0x9eec2  ldstr    aSiteid_1// "@SiteId"
0x9eec7  ldc.i4.s 0xE
0x9eec9  ldc.i4.0
0x9eeca  ldc.i4.0
0x9eecb  ldc.i4.0
0x9eecc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9eed1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9eed6  ldloc.0
0x9eed7  ldstr    aDocid_1// "@DocId"
0x9eedc  ldc.i4.s 0xE
0x9eede  ldc.i4.0
0x9eedf  ldc.i4.0
0x9eee0  ldc.i4.0
0x9eee1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9eee6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9eeeb  ldloc.0
0x9eeec  ldstr    aDocversion// "@DocVersion"
0x9eef1  ldc.i4.8
0x9eef2  ldc.i4.0
0x9eef3  ldc.i4.0
0x9eef4  ldc.i4.0
0x9eef5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9eefa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9eeff  ldloc.0
0x9ef00  ldstr    aContentversion// "@ContentVersion"
0x9ef05  ldc.i4.8
0x9ef06  ldc.i4.0
0x9ef07  ldc.i4.0
0x9ef08  ldc.i4.0
0x9ef09  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ef0e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ef13  ldloc.0
0x9ef14  ldstr    aUserid_1// "@UserId"
0x9ef19  ldc.i4.8
0x9ef1a  ldc.i4.0
0x9ef1b  ldc.i4.0
0x9ef1c  ldc.i4.0
0x9ef1d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ef22  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ef27  ldloc.0
0x9ef28  ldstr    aPartition_1// "@Partition"
0x9ef2d  ldc.i4.s 0x14
0x9ef2f  ldc.i4.0
0x9ef30  ldc.i4.0
0x9ef31  ldc.i4.0
0x9ef32  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ef37  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ef3c  ldloc.0
0x9ef3d  ldstr    aId_1// "@Id"
0x9ef42  ldc.i4.0
0x9ef43  ldc.i4.0
0x9ef44  ldc.i4.0
0x9ef45  ldc.i4.0
0x9ef46  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ef4b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ef50  ldloc.0
0x9ef51  ldstr    aDeleteuntil// "@DeleteUntil"
0x9ef56  ldc.i4.2
0x9ef57  ldc.i4.0
0x9ef58  ldc.i4.0
0x9ef59  ldc.i4.0
0x9ef5a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ef5f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ef64  ldloc.0
0x9ef65  ldstr    aDeleteonly// "@DeleteOnly"
0x9ef6a  ldc.i4.2
0x9ef6b  ldc.i4.0
0x9ef6c  ldc.i4.0
0x9ef6d  ldc.i4.0
0x9ef6e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ef73  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ef78  ldloc.0
0x9ef79  ldstr    aCheckperms// "@CheckPerms"
0x9ef7e  ldc.i4.2
0x9ef7f  ldc.i4.0
0x9ef80  ldc.i4.0
0x9ef81  ldc.i4.0
0x9ef82  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ef87  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9ef8c  ldloc.0
0x9ef8d  ldstr    aUpdatequota// "@UpdateQuota"
0x9ef92  ldc.i4.2
0x9ef93  ldc.i4.0
0x9ef94  ldc.i4.0
0x9ef95  ldc.i4.0
0x9ef96  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9ef9b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9efa0  ldloc.0
0x9efa1  ldstr    aQuotachange// "@QuotaChange"
0x9efa6  ldc.i4.0
0x9efa7  ldc.i4.0
0x9efa8  ldc.i4.1
0x9efa9  ldc.i4.0
0x9efaa  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9efaf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9efb4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9efb9  stloc.0
0x9efba  ldarg.0
0x9efbb  ldstr    aProcDeletefile_0// "proc_DeleteFileFragmentsByTag"
0x9efc0  ldloc.0
0x9efc1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9efc6  ldloc.0
0x9efc7  ldstr    aReturnValue// "@RETURN_VALUE"
0x9efcc  ldc.i4.8
0x9efcd  ldc.i4.0
0x9efce  ldc.i4.1
0x9efcf  ldc.i4.0
0x9efd0  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9efd5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9efda  ldloc.0
0x9efdb  ldstr    aSiteid_1// "@SiteId"
0x9efe0  ldc.i4.s 0xE
0x9efe2  ldc.i4.0
0x9efe3  ldc.i4.0
0x9efe4  ldc.i4.0
0x9efe5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9efea  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9efef  ldloc.0
0x9eff0  ldstr    aDocid_1// "@DocId"
0x9eff5  ldc.i4.s 0xE
0x9eff7  ldc.i4.0
0x9eff8  ldc.i4.0
0x9eff9  ldc.i4.0
0x9effa  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9efff  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f004  ldloc.0
0x9f005  ldstr    aDocversion// "@DocVersion"
0x9f00a  ldc.i4.8
0x9f00b  ldc.i4.0
0x9f00c  ldc.i4.0
0x9f00d  ldc.i4.0
0x9f00e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f013  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f018  ldloc.0
0x9f019  ldstr    aContentversion// "@ContentVersion"
0x9f01e  ldc.i4.8
0x9f01f  ldc.i4.0
0x9f020  ldc.i4.0
0x9f021  ldc.i4.0
0x9f022  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f027  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f02c  ldloc.0
0x9f02d  ldstr    aUserid_1// "@UserId"
0x9f032  ldc.i4.8
0x9f033  ldc.i4.0
0x9f034  ldc.i4.0
0x9f035  ldc.i4.0
0x9f036  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f03b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f040  ldloc.0
0x9f041  ldstr    aPartition_1// "@Partition"
0x9f046  ldc.i4.s 0x14
0x9f048  ldc.i4.0
0x9f049  ldc.i4.0
0x9f04a  ldc.i4.0
0x9f04b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f050  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f055  ldloc.0
0x9f056  ldstr    aTag_0// "@Tag"
0x9f05b  ldc.i4.s 0x15
0x9f05d  ldc.i4.s 0x28
0x9f05f  ldc.i4.0
0x9f060  ldc.i4.0
0x9f061  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f066  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f06b  ldloc.0
0x9f06c  ldstr    aId_1// "@Id"
0x9f071  ldc.i4.0
0x9f072  ldc.i4.0
0x9f073  ldc.i4.0
0x9f074  ldc.i4.0
0x9f075  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f07a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f07f  ldloc.0
0x9f080  ldstr    aDeleteuntil// "@DeleteUntil"
0x9f085  ldc.i4.2
0x9f086  ldc.i4.0
0x9f087  ldc.i4.0
0x9f088  ldc.i4.0
0x9f089  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f08e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f093  ldloc.0
0x9f094  ldstr    aCheckperms// "@CheckPerms"
0x9f099  ldc.i4.2
0x9f09a  ldc.i4.0
0x9f09b  ldc.i4.0
0x9f09c  ldc.i4.0
0x9f09d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f0a2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f0a7  ldloc.0
0x9f0a8  ldstr    aUpdatequota// "@UpdateQuota"
0x9f0ad  ldc.i4.2
0x9f0ae  ldc.i4.0
0x9f0af  ldc.i4.0
0x9f0b0  ldc.i4.0
0x9f0b1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f0b6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f0bb  ldloc.0
0x9f0bc  ldstr    aQuotachange// "@QuotaChange"
0x9f0c1  ldc.i4.0
0x9f0c2  ldc.i4.0
0x9f0c3  ldc.i4.1
0x9f0c4  ldc.i4.0
0x9f0c5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f0ca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f0cf  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x9f0d4  stloc.0
0x9f0d5  ldarg.0
0x9f0d6  ldstr    aProcDeletefrom// "proc_DeleteFromNVP"
0x9f0db  ldloc.0
0x9f0dc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x9f0e1  ldloc.0
0x9f0e2  ldstr    aReturnValue// "@RETURN_VALUE"
0x9f0e7  ldc.i4.8
0x9f0e8  ldc.i4.0
0x9f0e9  ldc.i4.1
0x9f0ea  ldc.i4.0
0x9f0eb  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x9f0f0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x9f0f5  ldloc.0
0x9f0f6  ldstr    aSiteid_1// "@SiteId"
0x9f0fb  ldc.i4.s 0xE
0x9f0fd  ldc.i4.0
  ... truncated ...
```
