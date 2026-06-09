# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch1

- ea: `0x94bb0`
- end: `0x95d3f`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch1`
- size: `4495`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0xd24c0`

## callees

- `0x17e6f0`
- `0x17e710`
- `0x2bc070`
- `0xabe9f0`

## string_xrefs

- `0x94da0`: `@DocIncomingCreatedDTM`
- `0x95208`: `@DocIncomingCreatedDTM`
- `0x94db4`: `@DocIncomingDTM`
- `0x9521c`: `@DocIncomingDTM`
- `0x94df0`: `@CreateParentDir`
- `0x95258`: `@CreateParentDir`
- `0x94eec`: `@Comment`
- `0x95354`: `@Comment`
- `0x94fec`: `@ComplianceTag`
- `0x95454`: `@ComplianceTag`
- `0x95005`: `@ComplianceFlags`
- `0x9546d`: `@ComplianceFlags`
- `0x95607`: `proc_AddEventToCache`
- `0x957e5`: `@ForceReprocessExtensions`
- `0x95933`: `@Overwrite`
- `0x9596f`: `@HasDeleteListItemsRight`
- `0x95983`: `@UpdateSiteQuota`
- `0x95997`: `@SetupPathVersion`
- `0x959ac`: `@SetupPath`
- `0x959c5`: `@SetupPathUser`
- `0x95a07`: `@fCheckQuotaAndWriteLock`
- `0x95a1b`: `@fCheckIfWebWelcomePage`
- `0x95a5e`: `proc_AddLink`
- `0x95ad2`: `@LinkNumber`
- `0x95b2d`: `@Security`
- `0x95bc5`: `proc_AddLinksToDoc256Leaf`
- `0x95c41`: `@LinkData`
- `0x95d01`: `@LinkData`
- `0x95c55`: `tvpLinkData256Leaf`
- `0x95c85`: `proc_AddLinksToDoc400`
- `0x95d15`: `tvpLinkData400`

## pseudocode

```c

```

## disassembly

```asm
0x94bb0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0x94bb5  stloc.0
0x94bb6  ldarg.0
0x94bb7  ldstr    aProcAdddocumen// "proc_AddDocument"
0x94bbc  ldloc.0
0x94bbd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0x94bc2  ldloc.0
0x94bc3  ldstr    aReturnValue// "@RETURN_VALUE"
0x94bc8  ldc.i4.8
0x94bc9  ldc.i4.0
0x94bca  ldc.i4.1
0x94bcb  ldc.i4.0
0x94bcc  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94bd1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94bd6  ldloc.0
0x94bd7  ldstr    aDocsiteid// "@DocSiteId"
0x94bdc  ldc.i4.s 0xE
0x94bde  ldc.i4.0
0x94bdf  ldc.i4.0
0x94be0  ldc.i4.0
0x94be1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94be6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94beb  ldloc.0
0x94bec  ldstr    aDocwebid// "@DocWebId"
0x94bf1  ldc.i4.s 0xE
0x94bf3  ldc.i4.0
0x94bf4  ldc.i4.0
0x94bf5  ldc.i4.0
0x94bf6  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94bfb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94c00  ldloc.0
0x94c01  ldstr    aUserid_1// "@UserId"
0x94c06  ldc.i4.8
0x94c07  ldc.i4.0
0x94c08  ldc.i4.0
0x94c09  ldc.i4.0
0x94c0a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94c0f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94c14  ldloc.0
0x94c15  ldstr    aAppprincipalid// "@AppPrincipalId"
0x94c1a  ldc.i4.8
0x94c1b  ldc.i4.0
0x94c1c  ldc.i4.0
0x94c1d  ldc.i4.0
0x94c1e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94c23  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94c28  ldloc.0
0x94c29  ldstr    aAuthorid// "@AuthorId"
0x94c2e  ldc.i4.8
0x94c2f  ldc.i4.0
0x94c30  ldc.i4.0
0x94c31  ldc.i4.0
0x94c32  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94c37  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94c3c  ldloc.0
0x94c3d  ldstr    aDocdirname// "@DocDirName"
0x94c42  ldc.i4.s 0xC
0x94c44  ldc.i4   0x190
0x94c49  ldc.i4.0
0x94c4a  ldc.i4.0
0x94c4b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94c50  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94c55  ldloc.0
0x94c56  ldstr    aDocleafname// "@DocLeafName"
0x94c5b  ldc.i4.s 0xC
0x94c5d  ldc.i4   0x190
0x94c62  ldc.i4.1
0x94c63  ldc.i4.0
0x94c64  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94c69  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94c6e  ldloc.0
0x94c6f  ldstr    aLevel_1// "@Level"
0x94c74  ldc.i4.s 0x14
0x94c76  ldc.i4.0
0x94c77  ldc.i4.0
0x94c78  ldc.i4.0
0x94c79  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94c7e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94c83  ldloc.0
0x94c84  ldstr    aUiversion_1// "@UIVersion"
0x94c89  ldc.i4.8
0x94c8a  ldc.i4.0
0x94c8b  ldc.i4.0
0x94c8c  ldc.i4.1
0x94c8d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94c92  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94c97  ldloc.0
0x94c98  ldstr    aNewdocid// "@NewDocId"
0x94c9d  ldc.i4.s 0xE
0x94c9f  ldc.i4.0
0x94ca0  ldc.i4.0
0x94ca1  ldc.i4.0
0x94ca2  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94ca7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94cac  ldloc.0
0x94cad  ldstr    aDoclibid// "@DoclibId"
0x94cb2  ldc.i4.s 0xE
0x94cb4  ldc.i4.0
0x94cb5  ldc.i4.0
0x94cb6  ldc.i4.0
0x94cb7  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94cbc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94cc1  ldloc.0
0x94cc2  ldstr    aNewdoclibrowid// "@NewDoclibRowId"
0x94cc7  ldc.i4.8
0x94cc8  ldc.i4.0
0x94cc9  ldc.i4.0
0x94cca  ldc.i4.0
0x94ccb  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94cd0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94cd5  ldloc.0
0x94cd6  ldstr    aSendingcontent// "@SendingContent"
0x94cdb  ldc.i4.2
0x94cdc  ldc.i4.0
0x94cdd  ldc.i4.0
0x94cde  ldc.i4.0
0x94cdf  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94ce4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94ce9  ldloc.0
0x94cea  ldstr    aDocmetainfo// "@DocMetaInfo"
0x94cef  ldc.i4.s 0x15
0x94cf1  ldc.i4.m1
0x94cf2  ldc.i4.0
0x94cf3  ldc.i4.0
0x94cf4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94cf9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94cfe  ldloc.0
0x94cff  ldstr    aDocsize// "@DocSize"
0x94d04  ldc.i4.8
0x94d05  ldc.i4.0
0x94d06  ldc.i4.0
0x94d07  ldc.i4.0
0x94d08  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94d0d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94d12  ldloc.0
0x94d13  ldstr    aDocmetainfosiz// "@DocMetaInfoSize"
0x94d18  ldc.i4.8
0x94d19  ldc.i4.0
0x94d1a  ldc.i4.0
0x94d1b  ldc.i4.0
0x94d1c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94d21  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94d26  ldloc.0
0x94d27  ldstr    aDocfileformatm// "@DocFileFormatMetaInfo"
0x94d2c  ldc.i4.s 0x15
0x94d2e  ldc.i4.m1
0x94d2f  ldc.i4.0
0x94d30  ldc.i4.0
0x94d31  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94d36  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94d3b  ldloc.0
0x94d3c  ldstr    aDocfileformatm_0// "@DocFileFormatMetaInfoSize"
0x94d41  ldc.i4.8
0x94d42  ldc.i4.0
0x94d43  ldc.i4.0
0x94d44  ldc.i4.0
0x94d45  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94d4a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94d4f  ldloc.0
0x94d50  ldstr    aEnableminorver// "@EnableMinorVersions"
0x94d55  ldc.i4.2
0x94d56  ldc.i4.0
0x94d57  ldc.i4.0
0x94d58  ldc.i4.0
0x94d59  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94d5e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94d63  ldloc.0
0x94d64  ldstr    aIsmoderated// "@IsModerated"
0x94d69  ldc.i4.2
0x94d6a  ldc.i4.0
0x94d6b  ldc.i4.0
0x94d6c  ldc.i4.0
0x94d6d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94d72  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94d77  ldloc.0
0x94d78  ldstr    aDocdirty// "@DocDirty"
0x94d7d  ldc.i4.2
0x94d7e  ldc.i4.0
0x94d7f  ldc.i4.0
0x94d80  ldc.i4.0
0x94d81  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94d86  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94d8b  ldloc.0
0x94d8c  ldstr    aDocflags// "@DocFlags"
0x94d91  ldc.i4.8
0x94d92  ldc.i4.0
0x94d93  ldc.i4.0
0x94d94  ldc.i4.0
0x94d95  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94d9a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94d9f  ldloc.0
0x94da0  ldstr    aDocincomingcre// "@DocIncomingCreatedDTM"
0x94da5  ldc.i4.4
0x94da6  ldc.i4.0
0x94da7  ldc.i4.0
0x94da8  ldc.i4.0
0x94da9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94dae  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94db3  ldloc.0
0x94db4  ldstr    aDocincomingdtm// "@DocIncomingDTM"
0x94db9  ldc.i4.4
0x94dba  ldc.i4.0
0x94dbb  ldc.i4.0
0x94dbc  ldc.i4.0
0x94dbd  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94dc2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94dc7  ldloc.0
0x94dc8  ldstr    aGetweblistforn// "@GetWebListForNormalization"
0x94dcd  ldc.i4.2
0x94dce  ldc.i4.0
0x94dcf  ldc.i4.0
0x94dd0  ldc.i4.0
0x94dd1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94dd6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94ddb  ldloc.0
0x94ddc  ldstr    aPutflags_0// "@PutFlags"
0x94de1  ldc.i4.0
0x94de2  ldc.i4.0
0x94de3  ldc.i4.0
0x94de4  ldc.i4.0
0x94de5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94dea  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94def  ldloc.0
0x94df0  ldstr    aCreateparentdi// "@CreateParentDir"
0x94df5  ldc.i4.2
0x94df6  ldc.i4.0
0x94df7  ldc.i4.0
0x94df8  ldc.i4.0
0x94df9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94dfe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94e03  ldloc.0
0x94e04  ldstr    aUrlissuggestio_0// "@UrlIsSuggestion"
0x94e09  ldc.i4.2
0x94e0a  ldc.i4.0
0x94e0b  ldc.i4.0
0x94e0c  ldc.i4.0
0x94e0d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94e12  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94e17  ldloc.0
0x94e18  ldstr    aThicketmainfil// "@ThicketMainFile"
0x94e1d  ldc.i4.2
0x94e1e  ldc.i4.0
0x94e1f  ldc.i4.0
0x94e20  ldc.i4.0
0x94e21  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94e26  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94e2b  ldloc.0
0x94e2c  ldstr    aCharset// "@CharSet"
0x94e31  ldc.i4.8
0x94e32  ldc.i4.0
0x94e33  ldc.i4.0
0x94e34  ldc.i4.0
0x94e35  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94e3a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94e3f  ldloc.0
0x94e40  ldstr    aProgid// "@ProgId"
0x94e45  ldc.i4.s 0xC
0x94e47  ldc.i4   0xFF
0x94e4c  ldc.i4.0
0x94e4d  ldc.i4.0
0x94e4e  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94e53  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94e58  ldloc.0
0x94e59  ldstr    aAttachmentop// "@AttachmentOp"
0x94e5e  ldc.i4.8
0x94e5f  ldc.i4.0
0x94e60  ldc.i4.0
0x94e61  ldc.i4.0
0x94e62  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94e67  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94e6c  ldloc.0
0x94e6d  ldstr    aVirusvendorid// "@VirusVendorID"
0x94e72  ldc.i4.8
0x94e73  ldc.i4.0
0x94e74  ldc.i4.0
0x94e75  ldc.i4.0
0x94e76  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94e7b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94e80  ldloc.0
0x94e81  ldstr    aVirusstatus// "@VirusStatus"
0x94e86  ldc.i4.s 0x14
0x94e88  ldc.i4.0
0x94e89  ldc.i4.0
0x94e8a  ldc.i4.0
0x94e8b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94e90  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94e95  ldloc.0
0x94e96  ldstr    aVirusinfo// "@VirusInfo"
0x94e9b  ldc.i4.s 0xC
0x94e9d  ldc.i4   0xFF
0x94ea2  ldc.i4.0
0x94ea3  ldc.i4.0
0x94ea4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0x94ea9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0x94eae  ldloc.0
0x94eaf  ldstr    aVirusinfoex// "@VirusInfoEx"
0x94eb4  ldc.i4.s 0x15
0x94eb6  ldc.i4.m1
0x94eb7  ldc.i4.0
0x94eb8  ldc.i4.0
  ... truncated ...
```
