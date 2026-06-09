# <>c__DisplayClass16::<BITs_Commit>b__12

- ea: `0xbf0e20`
- end: `0xbf18ff`
- name: `<>c__DisplayClass16::<BITs_Commit>b__12`
- size: `2783`
- prototype: ``
- caller_count: `0`
- callee_count: `83`
- tags: `broker_com_uri`

## callees

- `0x193060`
- `0x1b7f20`
- `0x1c3c50`
- `0x1c3c70`
- `0x342e60`
- `0x50a880`
- `0x50a8a0`
- `0x50a8c0`
- `0x50a8e0`
- `0x50a900`
- `0x50a920`
- `0x50a940`
- `0x50a990`
- `0x50ace0`
- `0x50ad00`
- `0x50aef0`
- `0x50af10`
- `0x50af30`
- `0x50b1d0`
- `0x50b1f0`
- `0x50b210`
- `0x50b260`
- `0x50b280`
- `0x50b310`
- `0x50b330`
- `0x50b360`
- `0x50c8b0`
- `0x50c8c0`
- `0x50d330`
- `0x50d860`
- `0x50db00`
- `0x5117d0`
- `0x513a00`
- `0x521610`
- `0x521760`
- `0x5217a0`
- `0x521830`
- `0x5218a0`
- `0x5218c0`
- `0x5218e0`
- `0x5218f0`
- `0x521920`
- `0x521950`
- `0x5263f0`
- `0x6c9890`
- `0x79fac0`
- `0x93dab0`
- `0x93dae0`
- `0x957d90`
- `0xa9a3f0`

## string_xrefs

- `0xbf0fde`: `BitsUpload.Commit: `
- `0xbf1120`: `BitsUpload.Commit: `
- `0xbf1114`: `BitsUpload.BITs_Commit: Error Data hash mismatch, cannot commit.`
- `0xbf0fa9`: `BitsUpload.BITs_Commit: Error Bits size mismatch, cannot commit. clientChange.DataSize:[{0}]; size:[{1}]`
- `0xbf0f1b`: `BitsUpload.BITSs_Commit: Error encountered pre-existing file with same name. Existing FileETag[{0}], IsNewFile[true]`
- `0xbf1569`: `BitsUpload.BITSs_Commit: Error encountered pre-existing file with same name. Existing FileETag[{0}], IsNewFile[true]`
- `0xbf0f47`: `BitsUpload.BITSs_Commit: Warning encountered pre-existing BITs stub file during inline upload. Existing FileETag[{0}], IsNewFile[true]`
- `0xbf1596`: `BitsUpload.BITSs_Commit: Warning encountered pre-existing BITs stub file during inline upload. Existing FileETag[{0}], IsNewFile[true]`
- `0xbf125c`: `vti_timelastmodified_nooverwrite`
- `0xbf128d`: `BITs_Commit`
- `0xbf143f`: `BITs_Commit`
- `0xbf1645`: `BITs_Commit`
- `0xbf178d`: `BITs_Commit`
- `0xbf15c3`: `BitsUpload.BITSs_Commit: Error encountered. BITs inline upload Failure, IsNewFile[true]`
- `0xbf1613`: `BitsUpload.BITs_Commit: Error encountered non-BitsStubFile with same name/ID. Create/Bits_Commit Failure. FileId[{0}], FileETag[{1}]`
- `0xbf1838`: `BitsUpload.BITs_Commit: New ETag from BITS Info did not match for BitsSessionId=[{0}], FileUniqueID=[{1}], ETagFromBITS=[{2}], ETagFromSave=[{3}]`
- `0xbf18ac`: `BitsUpload.BITs_Commit: Could not get OutBITSStreamInfo for BitsSessionId=[{0}], FileUniqueID=[{1}], ETag=[{2}]`

## pseudocode

```c

```

## disassembly

```asm
0xbf0e20  ldarg.0
0xbf0e21  ldfld    bool <>c__DisplayClass16::createFile
0xbf0e26  brfalse  loc_BF15D4
0xbf0e2b  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.FileSync.BitsUpload::InlineUploadThroughSetStreamApiKillSwitch
0xbf0e30  ldstr    a11212017// "11/21/2017"
0xbf0e35  ldstr    aFilestoreInlin// "FileStore_InlineUploadThroughSetStreamA"...
0xbf0e3a  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0xbf0e3f  brtrue   loc_BF11BB
0xbf0e44  ldnull
0xbf0e45  stloc.0
0xbf0e46  call     class SuppressActivityLoggingScope SuppressActivityLoggingScope::CreateGlobalSuppression()
0xbf0e4b  stloc.s  0x17
0xbf0e4d  ldarg.0
0xbf0e4e  ldfld    class BitsProcessingContext <>c__DisplayClass16::bitsContext
0xbf0e53  ldarg.0
0xbf0e54  ldfld    class Microsoft.SharePoint.FileSync.SyncRequestContext <>c__DisplayClass16::syncRequestContext
0xbf0e59  ldarg.0
0xbf0e5a  ldfld    class Microsoft.SharePoint.SPList <>c__DisplayClass16::list
0xbf0e5f  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0xbf0e64  ldarg.0
0xbf0e65  ldfld    class Microsoft.SharePoint.FileSync.SyncChange <>c__DisplayClass16::clientChange
0xbf0e6a  callvirt instance string Microsoft.SharePoint.FileSync.SyncRecordBase::get_ParentResourceID()
0xbf0e6f  ldarg.0
0xbf0e70  ldfld    class Microsoft.SharePoint.FileSync.SyncChange <>c__DisplayClass16::clientChange
0xbf0e75  callvirt instance class Microsoft.SharePoint.SPResourcePath Microsoft.SharePoint.FileSync.SyncRecordBase::get_RelationshipName()
0xbf0e7a  ldloca.s 0
0xbf0e7c  call     class Microsoft.SharePoint.SPFile Microsoft.SharePoint.FileSync.BitsUpload::CreateSpFileAndCheckLength(class Microsoft.SharePoint.FileSync.SyncRequestContext syncRequestContext, class Microsoft.SharePoint.SPWeb web, string parentResourceId, class Microsoft.SharePoint.SPResourcePath relationshipName, [out] string& newETag)
0xbf0e81  callvirt instance void BitsProcessingContext::set_File(class Microsoft.SharePoint.SPFile value)
0xbf0e86  leave.s  loc_BF0E94
0xbf0e88  ldloc.s  0x17
0xbf0e8a  brfalse.s loc_BF0E93
0xbf0e8c  ldloc.s  0x17
0xbf0e8e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbf0e93  endfinally
0xbf0e94  leave    loc_BF0F67
0xbf0e99  pop
0xbf0e9a  ldarg.0
0xbf0e9b  ldfld    class RequestContext <>c__DisplayClass16::requestContext
0xbf0ea0  callvirt instance class Microsoft.SharePoint.SPList RequestContext::get_List()
0xbf0ea5  callvirt instance class Microsoft.SharePoint.SPWeb Microsoft.SharePoint.SPList::get_ParentWeb()
0xbf0eaa  ldarg.0
0xbf0eab  ldfld    class Microsoft.SharePoint.FileSync.SyncChange <>c__DisplayClass16::clientChange
0xbf0eb0  callvirt instance string Microsoft.SharePoint.FileSync.SyncRecordBase::get_ParentResourceID()
0xbf0eb5  ldarg.0
0xbf0eb6  ldfld    class Microsoft.SharePoint.FileSync.SyncChange <>c__DisplayClass16::clientChange
0xbf0ebb  callvirt instance class Microsoft.SharePoint.SPResourcePath Microsoft.SharePoint.FileSync.SyncRecordBase::get_RelationshipName()
0xbf0ec0  call     class Microsoft.SharePoint.SPFile Microsoft.SharePoint.FileSync.SPFileSyncObjectHelper::GetSPFile(class Microsoft.SharePoint.SPWeb web, string parentFolderId, class Microsoft.SharePoint.SPResourcePath filename)
0xbf0ec5  stloc.1
0xbf0ec6  ldc.i4.0
0xbf0ec7  stloc.2
0xbf0ec8  ldloc.1
0xbf0ec9  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.SPFile::get_Properties()
0xbf0ece  ldstr    aVtiBitsstubfil// "vti_bitsstubfile"
0xbf0ed3  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0xbf0ed8  brfalse.s loc_BF0F0C
0xbf0eda  ldloc.1
0xbf0edb  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.SharePoint.SPFile::get_Properties()
0xbf0ee0  ldstr    aVtiBitsstubfil// "vti_bitsstubfile"
0xbf0ee5  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0xbf0eea  isinst   [mscorlib]System.String
0xbf0eef  stloc.3
0xbf0ef0  ldloc.3
0xbf0ef1  ldsfld   string [mscorlib]System.Boolean::TrueString
0xbf0ef6  ldc.i4.5
0xbf0ef7  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xbf0efc  brfalse.s loc_BF0F0C
0xbf0efe  ldc.i4.1
0xbf0eff  stloc.2
0xbf0f00  ldarg.0
0xbf0f01  ldfld    class BitsProcessingContext <>c__DisplayClass16::bitsContext
0xbf0f06  ldloc.1
0xbf0f07  callvirt instance void BitsProcessingContext::set_File(class Microsoft.SharePoint.SPFile value)
0xbf0f0c  ldloc.2
0xbf0f0d  brtrue.s loc_BF0F3B
0xbf0f0f  ldc.i4   0x125B717
0xbf0f14  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xbf0f19  ldc.i4.s 0x32
0xbf0f1b  ldstr    aBitsuploadBits_2// "BitsUpload.BITSs_Commit: Error encounte"...
0xbf0f20  ldc.i4.1
0xbf0f21  newarr   [mscorlib]System.Object
0xbf0f26  stloc.s  0x18
0xbf0f28  ldloc.s  0x18
0xbf0f2a  ldc.i4.0
0xbf0f2b  ldloc.1
0xbf0f2c  callvirt instance string Microsoft.SharePoint.SPFile::get_ETag()
0xbf0f31  stelem.ref
0xbf0f32  ldloc.s  0x18
0xbf0f34  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xbf0f39  rethrow
0xbf0f3b  ldc.i4   0x125B718
0xbf0f40  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xbf0f45  ldc.i4.s 0x14
0xbf0f47  ldstr    aBitsuploadBits_3// "BitsUpload.BITSs_Commit: Warning encoun"...
0xbf0f4c  ldc.i4.1
0xbf0f4d  newarr   [mscorlib]System.Object
0xbf0f52  stloc.s  0x19
0xbf0f54  ldloc.s  0x19
0xbf0f56  ldc.i4.0
0xbf0f57  ldloc.1
0xbf0f58  callvirt instance string Microsoft.SharePoint.SPFile::get_ETag()
0xbf0f5d  stelem.ref
0xbf0f5e  ldloc.s  0x19
0xbf0f60  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xbf0f65  leave.s  loc_BF0F67
0xbf0f67  ldarg.0
0xbf0f68  ldarg.0
0xbf0f69  ldfld    class BitsProcessingContext <>c__DisplayClass16::bitsContext
0xbf0f6e  callvirt instance class Microsoft.SharePoint.SPFile BitsProcessingContext::get_File()
0xbf0f73  stfld    class Microsoft.SharePoint.SPFile <>c__DisplayClass16::file
0xbf0f78  ldarg.0
0xbf0f79  ldfld    class Microsoft.SharePoint.FileSync.SyncChange <>c__DisplayClass16::clientChange
0xbf0f7e  callvirt instance class [mscorlib]System.IO.MemoryStream Microsoft.SharePoint.FileSync.SyncChange::get_DocumentContent()
0xbf0f83  stloc.s  4
0xbf0f85  ldloc.s  4
0xbf0f87  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0xbf0f8c  stloc.s  5
0xbf0f8e  ldarg.0
0xbf0f8f  ldfld    class Microsoft.SharePoint.FileSync.SyncChange <>c__DisplayClass16::clientChange
0xbf0f94  callvirt instance int64 Microsoft.SharePoint.FileSync.SyncChange::get_DataSize()
0xbf0f99  ldloc.s  5
0xbf0f9b  beq.s    loc_BF0FFA
0xbf0f9d  ldc.i4   0x700747
0xbf0fa2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xbf0fa7  ldc.i4.s 0x14
0xbf0fa9  ldstr    aBitsuploadBits_1// "BitsUpload.BITs_Commit: Error Bits size"...
0xbf0fae  ldc.i4.2
0xbf0faf  newarr   [mscorlib]System.Object
0xbf0fb4  stloc.s  0x1A
0xbf0fb6  ldloc.s  0x1A
0xbf0fb8  ldc.i4.0
0xbf0fb9  ldarg.0
0xbf0fba  ldfld    class Microsoft.SharePoint.FileSync.SyncChange <>c__DisplayClass16::clientChange
0xbf0fbf  callvirt instance int64 Microsoft.SharePoint.FileSync.SyncChange::get_DataSize()
0xbf0fc4  box      [mscorlib]System.Int64
0xbf0fc9  stelem.ref
0xbf0fca  ldloc.s  0x1A
0xbf0fcc  ldc.i4.1
0xbf0fcd  ldloc.s  5
0xbf0fcf  box      [mscorlib]System.Int64
0xbf0fd4  stelem.ref
0xbf0fd5  ldloc.s  0x1A
0xbf0fd7  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0xbf0fdc  ldc.i4.s 0x14
0xbf0fde  ldstr    aBitsuploadComm// "BitsUpload.Commit: "
0xbf0fe3  ldc.i4.s 0x14
0xbf0fe5  box      Microsoft.SharePoint.FileSync.WriteStatus
0xbf0fea  callvirt instance string [mscorlib]System.Object::ToString()
0xbf0fef  call     string [mscorlib]System.String::Concat(string, string)
0xbf0ff4  newobj   instance void Microsoft.SharePoint.FileSync.SyncBitsCommitErrorException::.ctor(valuetype Microsoft.SharePoint.FileSync.WriteStatus writeStatus, string message)
0xbf0ff9  throw
0xbf0ffa  newobj   instance void Microsoft.SharePoint.SPFileSaveBinaryParameters::.ctor()
0xbf0fff  stloc.s  6
0xbf1001  ldloc.s  6
0xbf1003  ldc.i4.1
0xbf1004  callvirt instance void Microsoft.SharePoint.SPFileSaveBinaryParameters::set_CheckRequiredFields(bool value)
0xbf1009  ldloc.s  6
0xbf100b  ldc.i4.1
0xbf100c  callvirt instance void Microsoft.SharePoint.SPFileSaveBinaryParameters::set_CreateVersion(bool value)
0xbf1011  ldloc.s  6
0xbf1013  ldarg.0
0xbf1014  ldfld    string <>c__DisplayClass16::inETag
0xbf1019  callvirt instance void Microsoft.SharePoint.SPFileSaveBinaryParameters::set_ETagMatch(string value)
0xbf101e  ldarg.0
0xbf101f  ldfld    class Microsoft.SharePoint.FileSync.SyncChange <>c__DisplayClass16::clientChange
0xbf1024  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.FileSync.SyncChange::get_DateModifiedOnClient()
0xbf1029  stloc.s  7
0xbf102b  ldloc.s  7
0xbf102d  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xbf1032  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xbf1037  brfalse.s loc_BF104A
0xbf1039  ldloc.s  6
0xbf103b  ldloc.s  7
0xbf103d  callvirt instance void Microsoft.SharePoint.SPFileSaveBinaryParameters::set_TimeLastModified(valuetype [mscorlib]System.DateTime value)
0xbf1042  ldloc.s  6
0xbf1044  ldc.i4.1
0xbf1045  callvirt instance void Microsoft.SharePoint.SPFileSaveBinaryParameters::set_UseTimeLastModified(bool value)
0xbf104a  ldloc.s  6
0xbf104c  ldarg.0
0xbf104d  ldfld    class Microsoft.SharePoint.FileSync.SyncChange <>c__DisplayClass16::clientChange
0xbf1052  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.FileSync.SyncChange::get_DateCreatedOnClient()
0xbf1057  callvirt instance void Microsoft.SharePoint.SPFileSaveBinaryParameters::set_TimeCreated(valuetype [mscorlib]System.DateTime value)
0xbf105c  ldloc.s  6
0xbf105e  ldc.i4.1
0xbf105f  callvirt instance void Microsoft.SharePoint.SPFileSaveBinaryParameters::set_UseTimeCreated(bool value)
0xbf1064  ldloc.s  6
0xbf1066  ldc.i4.1
0xbf1067  callvirt instance void Microsoft.SharePoint.SPFileSaveBinaryParameters::set_PersistBITSStreamInfo(bool value)
0xbf106c  ldloc.s  6
0xbf106e  ldarg.0
0xbf106f  ldfld    class BitsProcessingContext <>c__DisplayClass16::bitsContext
0xbf1074  callvirt instance valuetype [mscorlib]System.Guid BitsProcessingContext::get_SessionId()
0xbf1079  callvirt instance void Microsoft.SharePoint.SPFileSaveBinaryParameters::set_BITSSessionId(valuetype [mscorlib]System.Guid value)
0xbf107e  ldloc.s  6
0xbf1080  ldarg.0
0xbf1081  ldfld    class Microsoft.SharePoint.FileSync.SyncChange <>c__DisplayClass16::clientChange
0xbf1086  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.FileSync.SyncRecordBase::get_OriginatorId()
0xbf108b  callvirt instance void Microsoft.SharePoint.SPFileSaveBinaryParameters::set_OriginatorId(valuetype [mscorlib]System.Guid value)
0xbf1090  ldarg.0
0xbf1091  ldfld    class BitsProcessingContext <>c__DisplayClass16::bitsContext
0xbf1096  callvirt instance class Microsoft.SharePoint.SPFile BitsProcessingContext::get_File()
0xbf109b  callvirt instance string Microsoft.SharePoint.SPFile::get_FullUrl()
0xbf10a0  call     class SuppressActivityLoggingScope SuppressActivityLoggingScope::CreateTargetedSuppression(string objectId)
0xbf10a5  stloc.s  0x1B
0xbf10a7  ldarg.0
0xbf10a8  ldfld    class BitsProcessingContext <>c__DisplayClass16::bitsContext
0xbf10ad  callvirt instance class Microsoft.SharePoint.SPFile BitsProcessingContext::get_File()
0xbf10b2  ldarg.0
0xbf10b3  ldfld    class Microsoft.SharePoint.FileSync.SyncRequestContext <>c__DisplayClass16::syncRequestContext
0xbf10b8  brfalse.s loc_BF10C7
0xbf10ba  ldarg.0
0xbf10bb  ldfld    class Microsoft.SharePoint.FileSync.SyncRequestContext <>c__DisplayClass16::syncRequestContext
0xbf10c0  callvirt instance bool Microsoft.SharePoint.FileSync.SyncRequestContext::get_EmitIrm()
0xbf10c5  br.s     loc_BF10C8
0xbf10c7  ldc.i4.0
0xbf10c8  callvirt instance void Microsoft.SharePoint.SPFile::set_SkipIrmChecks(bool value)
0xbf10cd  ldarg.0
0xbf10ce  ldfld    class BitsProcessingContext <>c__DisplayClass16::bitsContext
0xbf10d3  callvirt instance class Microsoft.SharePoint.SPFile BitsProcessingContext::get_File()
0xbf10d8  ldarg.0
0xbf10d9  ldfld    class Microsoft.SharePoint.FileSync.SyncChange <>c__DisplayClass16::clientChange
0xbf10de  callvirt instance class [mscorlib]System.IO.MemoryStream Microsoft.SharePoint.FileSync.SyncChange::get_DocumentContent()
0xbf10e3  ldloc.s  6
0xbf10e5  ldc.i4.0
0xbf10e6  ldc.i4.0
0xbf10e7  ldarg.0
0xbf10e8  ldfld    class Microsoft.SharePoint.FileSync.SyncChange <>c__DisplayClass16::clientChange
0xbf10ed  callvirt instance unsigned int8[] Microsoft.SharePoint.FileSync.SyncChange::get_ExpectedFinalDataHash()
0xbf10f2  call     void Microsoft.SharePoint.Utilities.SPBITSSession::SetStream(class Microsoft.SharePoint.SPFile file, class [mscorlib]System.IO.Stream content, class Microsoft.SharePoint.SPFileSaveBinaryParameters saveBinaryParams, [opt] bool retryTransientFailures, [opt] bool isDiffGram, [opt] unsigned int8[] finalDataHash)
0xbf10f7  leave.s  loc_BF1105
0xbf10f9  ldloc.s  0x1B
0xbf10fb  brfalse.s loc_BF1104
0xbf10fd  ldloc.s  0x1B
0xbf10ff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbf1104  endfinally
0xbf1105  leave.s  loc_BF113C
0xbf1107  pop
0xbf1108  ldc.i4   0x20018C2
0xbf110d  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SkySync()
0xbf1112  ldc.i4.s 0x14
0xbf1114  ldstr    aBitsuploadBits_0// "BitsUpload.BITs_Commit: Error Data hash"...
0xbf1119  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0xbf111e  ldc.i4.s 0x25
0xbf1120  ldstr    aBitsuploadComm// "BitsUpload.Commit: "
0xbf1125  ldc.i4.s 0x25
0xbf1127  box      Microsoft.SharePoint.FileSync.WriteStatus
0xbf112c  callvirt instance string [mscorlib]System.Object::ToString()
0xbf1131  call     string [mscorlib]System.String::Concat(string, string)
0xbf1136  newobj   instance void Microsoft.SharePoint.FileSync.SyncBitsCommitErrorException::.ctor(valuetype Microsoft.SharePoint.FileSync.WriteStatus writeStatus, string message)
0xbf113b  throw
0xbf113c  ldarg.0
0xbf113d  ldfld    bool <>c__DisplayClass16::shouldAddNGSCChunkSizesKillSwitch
0xbf1142  brfalse.s loc_BF1190
0xbf1144  ldarg.0
0xbf1145  ldfld    class Microsoft.SharePoint.SPFile <>c__DisplayClass16::file
0xbf114a  ldc.i4.s 0x57
0xbf114c  ldarg.0
0xbf114d  ldfld    class Microsoft.SharePoint.FileSync.SyncRequestContext <>c__DisplayClass16::syncRequestContext
0xbf1152  brtrue.s loc_BF115B
0xbf1154  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xbf1159  br.s     loc_BF1166
0xbf115b  ldarg.0
0xbf115c  ldfld    class Microsoft.SharePoint.FileSync.SyncRequestContext <>c__DisplayClass16::syncRequestContext
0xbf1161  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.FileSync.SyncRequestContext::get_ClientMachineGuid()
0xbf1166  ldarg.0
0xbf1167  ldfld    class Microsoft.SharePoint.FileSync.SyncRequestContext <>c__DisplayClass16::syncRequestContext
0xbf116c  brtrue.s loc_BF1175
0xbf116e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xbf1173  br.s     loc_BF1180
0xbf1175  ldarg.0
0xbf1176  ldfld    class Microsoft.SharePoint.FileSync.SyncRequestContext <>c__DisplayClass16::syncRequestContext
0xbf117b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.FileSync.SyncRequestContext::get_DomainMachineGuid()
0xbf1180  ldarg.0
0xbf1181  ldfld    class Microsoft.SharePoint.FileSync.SyncChange <>c__DisplayClass16::clientChange
0xbf1186  callvirt instance int64 Microsoft.SharePoint.FileSync.SyncChange::get_BytesCommitted()
0xbf118b  call     void Microsoft.SharePoint.SPFile::WriteSyncAuditLog(class Microsoft.SharePoint.SPFile spFile, valuetype Microsoft.Office.Audit.Schema.SLAPI.SharePoint.SharePointAuditOperation fileActivity, valuetype [mscorlib]System.Guid machineId, valuetype [mscorlib]System.Guid domainGuid, [opt] int64 bytesCommitted)
0xbf1190  ldarg.0
0xbf1191  ldloc.s  6
0xbf1193  callvirt instance string Microsoft.SharePoint.SPFileSaveBinaryParameters::get_OutETagNew()
0xbf1198  stfld    string <>c__DisplayClass16::ETagFromSave
0xbf119d  ldarg.0
0xbf119e  ldloc.s  6
0xbf11a0  callvirt instance class Microsoft.SharePoint.SPFileBITSStreamInfo Microsoft.SharePoint.SPFileSaveBinaryParameters::get_OutBITSStreamInfo()
0xbf11a5  stfld    class Microsoft.SharePoint.SPFileBITSStreamInfo <>c__DisplayClass16::bitsStreamInfo
0xbf11aa  leave    loc_BF17DA
0xbf11af  ldloc.s  4
0xbf11b1  brfalse.s loc_BF11BA
0xbf11b3  ldloc.s  4
0xbf11b5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbf11ba  endfinally
0xbf11bb  ldnull
0xbf11bc  stloc.s  0xF
0xbf11be  ldnull
0xbf11bf  stloc.s  0x10
0xbf11c1  newobj   instance void <>c__DisplayClass1a::.ctor()
0xbf11c6  stloc.s  0x11
0xbf11c8  ldloc.s  0x11
0xbf11ca  ldarg.0
0xbf11cb  stfld    class <>c__DisplayClass16 <>c__DisplayClass1a::CS$<>8__locals17
0xbf11d0  ldloc.s  0x11
0xbf11d2  ldarg.0
  ... truncated ...
```
