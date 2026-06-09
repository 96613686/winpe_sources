# UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName(_FLT_INSTANCE const &,_FILE_OBJECT const &,_FLT_CALLBACK_DATA &,ulong,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &)

- ea: `0x140037b54`
- end: `0x14003a19c`
- name: `?GeneratePreCreateNormalizedName@UnionFsFilter@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@KPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@@Z`
- size: `9800`
- prototype: `__int64 __fastcall(UnionFs::UnionFsFilter *__hidden this, const struct _FLT_INSTANCE *, const struct _FILE_OBJECT *, struct _FLT_CALLBACK_DATA *, unsigned int, struct _FLT_NAME_CONTROL *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400365c8`

## callees

- `0x140005d5c`
- `0x140006340`
- `0x14000efa0`
- `0x14000f81c`
- `0x140010ba8`
- `0x140010ff0`
- `0x14001108c`
- `0x1400111b8`
- `0x14001126c`
- `0x140036268`
- `0x1400362c0`
- `0x140036568`
- `0x140037b54`
- `0x14003b60c`
- `0x14003cf90`
- `0x140043afc`
- `0x140044074`
- `0x1400446ac`
- `0x1400448c8`
- `0x140055f1c`
- `0x140056b94`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x1400611a4`
- `0x14006e394`
- `0x14006f198`
- `0x140075d30`
- `0x140076fa4`
- `0x1400779fc`
- `0x140079f68`
- `0x14007a114`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bbd0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x140037eba`
- `ntoskrnl!IoGetSilo` at `0x140038719`
- `ntoskrnl!IoGetSilo` at `0x140037eba`
- `ntoskrnl!IoGetSilo` at `0x140038719`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037d84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037fea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003808b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400380ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003822d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400382fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038337`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038396`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038492`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400384cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038500`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400385cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400385f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003861d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038656`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038687`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038a6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038a8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038c22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038c96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038d5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038eb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038fc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003910a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039144`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039373`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400393ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400394ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039527`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400395e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400395f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400396c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039827`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039861`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039a96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039c7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039df1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039f3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039fc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a0aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a130`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037d84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037fea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003808b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400380ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003822d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400382fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038337`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038396`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038492`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400384cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038500`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400385cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400385f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003861d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038656`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038687`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038a6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038a8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038c22`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038c96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038d5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038eb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038fc5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003910a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039144`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039373`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400393ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400394ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039527`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400395e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400395f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400396c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039827`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039861`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039a96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039c7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039df1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039f3e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039fc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a0aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a130`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140039d4a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140039d4a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140039d68`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140039d68`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140037ea7`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140038730`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140037ea7`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140038730`
- `ntoskrnl!PsGetHostSilo` at `0x1400388bc`
- `ntoskrnl!PsGetHostSilo` at `0x14003903c`
- `ntoskrnl!PsGetHostSilo` at `0x1400388bc`
- `ntoskrnl!PsGetHostSilo` at `0x14003903c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140039d34`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140039d34`
- `ntoskrnl!ObfDereferenceObject` at `0x1400389bd`
- `ntoskrnl!ObfDereferenceObject` at `0x140038a05`
- `ntoskrnl!ObfDereferenceObject` at `0x140038bbe`
- `ntoskrnl!ObfDereferenceObject` at `0x140038cfb`
- `ntoskrnl!ObfDereferenceObject` at `0x140038e77`
- `ntoskrnl!ObfDereferenceObject` at `0x140038f03`
- `ntoskrnl!ObfDereferenceObject` at `0x1400392e4`
- `ntoskrnl!ObfDereferenceObject` at `0x140039333`
- `ntoskrnl!ObfDereferenceObject` at `0x1400394ad`
- `ntoskrnl!ObfDereferenceObject` at `0x14003965d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400397ec`
- `ntoskrnl!ObfDereferenceObject` at `0x140039a56`
- `ntoskrnl!ObfDereferenceObject` at `0x140039c3d`
- `ntoskrnl!ObfDereferenceObject` at `0x140039db1`
- `ntoskrnl!ObfDereferenceObject` at `0x1400389bd`
- `ntoskrnl!ObfDereferenceObject` at `0x140038a05`
- `ntoskrnl!ObfDereferenceObject` at `0x140038bbe`
- `ntoskrnl!ObfDereferenceObject` at `0x140038cfb`
- `ntoskrnl!ObfDereferenceObject` at `0x140038e77`
- `ntoskrnl!ObfDereferenceObject` at `0x140038f03`
- `ntoskrnl!ObfDereferenceObject` at `0x1400392e4`
- `ntoskrnl!ObfDereferenceObject` at `0x140039333`
- `ntoskrnl!ObfDereferenceObject` at `0x1400394ad`
- `ntoskrnl!ObfDereferenceObject` at `0x14003965d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400397ec`
- `ntoskrnl!ObfDereferenceObject` at `0x140039a56`
- `ntoskrnl!ObfDereferenceObject` at `0x140039c3d`
- `ntoskrnl!ObfDereferenceObject` at `0x140039db1`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140039b99`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140039b99`
- `FLTMGR!FltQueryDirectoryFile` at `0x140038dff`
- `FLTMGR!FltQueryDirectoryFile` at `0x140039774`
- `FLTMGR!FltQueryDirectoryFile` at `0x140038dff`
- `FLTMGR!FltQueryDirectoryFile` at `0x140039774`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140038b36`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14003941e`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x140038b36`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x14003941e`
- `FLTMGR!FltGetVolumeName` at `0x14003884f`
- `FLTMGR!FltGetVolumeName` at `0x1400391ab`
- `FLTMGR!FltGetVolumeName` at `0x14003884f`
- `FLTMGR!FltGetVolumeName` at `0x1400391ab`
- `FLTMGR!FltCreateFileEx2` at `0x140038996`
- `FLTMGR!FltCreateFileEx2` at `0x1400392b4`
- `FLTMGR!FltCreateFileEx2` at `0x140038996`
- `FLTMGR!FltCreateFileEx2` at `0x1400392b4`
- `FLTMGR!FltGetVolumeFromInstance` at `0x14003879d`
- `FLTMGR!FltGetVolumeFromInstance` at `0x14003909d`
- `FLTMGR!FltGetVolumeFromInstance` at `0x14003879d`
- `FLTMGR!FltGetVolumeFromInstance` at `0x14003909d`
- `FLTMGR!FltClose` at `0x140038a1a`
- `FLTMGR!FltClose` at `0x140038bd3`
- `FLTMGR!FltClose` at `0x140038d10`
- `FLTMGR!FltClose` at `0x140038e8c`
- `FLTMGR!FltClose` at `0x140038f18`
- `FLTMGR!FltClose` at `0x140039348`
- `FLTMGR!FltClose` at `0x1400394c2`
- `FLTMGR!FltClose` at `0x140039672`
- `FLTMGR!FltClose` at `0x140039801`
- `FLTMGR!FltClose` at `0x140039a6b`
- `FLTMGR!FltClose` at `0x140039c52`
- `FLTMGR!FltClose` at `0x140039dc6`
- `FLTMGR!FltClose` at `0x140038a1a`
- `FLTMGR!FltClose` at `0x140038bd3`
- `FLTMGR!FltClose` at `0x140038d10`
- `FLTMGR!FltClose` at `0x140038e8c`
- `FLTMGR!FltClose` at `0x140038f18`
- `FLTMGR!FltClose` at `0x140039348`
- `FLTMGR!FltClose` at `0x1400394c2`
- `FLTMGR!FltClose` at `0x140039672`
- `FLTMGR!FltClose` at `0x140039801`
- `FLTMGR!FltClose` at `0x140039a6b`
- `FLTMGR!FltClose` at `0x140039c52`
- `FLTMGR!FltClose` at `0x140039dc6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037c96`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037dab`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003811d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400383c9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400386b6`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140038af0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140038b5d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140038ba5`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140038ce2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140038e5e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140038eea`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039447`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039494`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039644`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039723`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400397d3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039a3d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039c24`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039cfe`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039d98`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003a163`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037c96`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037dab`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003811d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400383c9`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400386b6`

## string_xrefs

- `0x1400381d5`: `PUSH: Cache lookup`
- `0x1400389d1`: `API: Opening parent`
- `0x1400392fe`: `API: Opening parent`
- `0x140037be6`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140037c6f`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140037cce`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140037d4c`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140037f7e`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x14003804f`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x1400381e6`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x1400382c8`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x14003840e`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140038459`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140038597`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x1400387fc`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x1400389e2`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140038b82`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140038cbc`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140038e3b`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140038f6f`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x1400390d1`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x14003930f`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x14003946d`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x14003961e`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x1400397b0`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140039a09`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140039bc1`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140039bf4`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140039ed5`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x14003a041`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140037c5e`: `PUSH: Getting OPENED name`
- `0x140037cbd`: `API: Parsing opened name info`
- `0x1400383fd`: `PUSH: Copying UfsPathName`
- `0x140038e2a`: `API: Getting final component long name`
- `0x14003979f`: `API: Getting final component long name`
- `0x140039b34`: `PUSH: Copying UfsPathName to unique_unicode_string`
- `0x140039be3`: `PUSH: Rewriting path`
- `0x140039e6a`: `API: Appending final component`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName(
        UnionFs::UnionFsFilter *this,
        const struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        struct _FLT_CALLBACK_DATA *a4,
        unsigned int a5,
        struct _FLT_NAME_CONTROL *a6,
        struct _UNICODE_STRING *a7)
{
  NTSTATUS MappingTableForFileObject; // ebx
  UnionFs::UfsScratchMappingTable *v11; // r14
  struct _FLT_FILE_NAME_INFORMATION *v12; // rcx
  ULONG v13; // r13d
  int v14; // edi
  struct _UNICODE_STRING *v15; // rdx
  struct _UNICODE_STRING *v16; // rbx
  struct _FLT_FILE_NAME_INFORMATION *v17; // rcx
  utl::_RefCountBase *v18; // r14
  UnionFs::UfsLayerCtx *v19; // rbx
  volatile signed __int32 *v20; // rdi
  struct _UNICODE_STRING *v21; // rsi
  __int64 v22; // rcx
  __int64 Silo; // rax
  __int64 v24; // r9
  struct _FLT_INSTANCE *v25; // r13
  __int16 v26; // ax
  unsigned __int16 v27; // ax
  __int64 v28; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v29; // rdx
  struct _UNICODE_STRING *v30; // rdx
  NTSTATUS FileNameInformationUnsafe; // r12d
  struct _UNICODE_STRING *v32; // rdx
  struct _UNICODE_STRING *v33; // rbx
  struct _UNICODE_STRING *v34; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v35; // rcx
  _BOOL8 v36; // r9
  __int64 v37; // rcx
  struct _UNICODE_STRING *v38; // r12
  struct FsFltWil::Details::RundownRefCacheAware *v39; // rdx
  WCHAR *v40; // rbx
  struct _UNICODE_STRING v41; // xmm1
  int v42; // eax
  NTSTATUS VolumeFromInstance; // r13d
  struct _UNICODE_STRING *v44; // rdx
  struct _UNICODE_STRING *v45; // rbx
  struct _UNICODE_STRING *v46; // rdx
  struct _UNICODE_STRING *v47; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v48; // rcx
  struct _UNICODE_STRING *v49; // r13
  _QWORD *v50; // r14
  struct _UNICODE_STRING *v51; // rdx
  struct _UNICODE_STRING *v52; // rdx
  struct _UNICODE_STRING *v53; // rdx
  __int64 v54; // r9
  struct _UNICODE_STRING v55; // xmm1
  int v56; // eax
  struct _UNICODE_STRING *v57; // rdx
  struct _UNICODE_STRING *v58; // rbx
  utl::_RefCountBase *v59; // rcx
  struct _UNICODE_STRING *v60; // rdx
  struct _UNICODE_STRING *v61; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v62; // rcx
  UnionFs *v63; // rcx
  PVOID *v64; // rbx
  struct _UNICODE_STRING *v65; // r9
  struct _UNICODE_STRING *v66; // rdx
  NTSTATUS v67; // esi
  PVOID v68; // rcx
  struct _UNICODE_STRING *v69; // rdx
  PVOID v70; // rcx
  struct _UNICODE_STRING *v71; // rbx
  utl::_RefCountBase *v72; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v73; // rcx
  unsigned int v74; // r12d
  struct _FLT_FILE_NAME_INFORMATION *v75; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v76; // rcx
  PVOID v77; // rcx
  utl::_RefCountBase *v78; // rcx
  WCHAR **v79; // rax
  struct _FLT_FILE_NAME_INFORMATION *v80; // rcx
  PVOID v81; // rcx
  utl::_RefCountBase *v82; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v83; // rcx
  PVOID v84; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v85; // rcx
  PVOID v86; // rcx
  utl::_RefCountBase *v87; // r13
  volatile signed __int32 *v88; // rsi
  utl::_RefCountBase *v89; // rcx
  int v90; // eax
  utl::_RefCountBase *v91; // rcx
  struct _UNICODE_STRING *v92; // r9
  struct _UNICODE_STRING *v93; // rdx
  PFILE_OBJECT v94; // r13
  UnionFs *v95; // rcx
  PVOID v96; // rax
  PVOID v97; // rcx
  utl::_RefCountBase *v98; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v99; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v100; // rcx
  PVOID v101; // rcx
  utl::_RefCountBase *v102; // rcx
  WCHAR **v103; // rax
  WCHAR *v104; // r13
  struct _FLT_FILE_NAME_INFORMATION *v105; // rcx
  PVOID v106; // rcx
  utl::_RefCountBase *v107; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v108; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v109; // rcx
  PVOID v110; // rcx
  utl::_RefCountBase *v111; // rcx
  USHORT Length; // cx
  UnionFs::UfsLayerCtx *v113; // rcx
  NTSTATUS appended; // r14d
  __int64 v115; // r9
  struct _UNICODE_STRING *v116; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v117; // rcx
  PVOID v118; // rcx
  PFLT_NAME_CONTROL v119; // r12
  const char *v120; // rax
  __int64 v121; // r8
  struct _UNICODE_STRING *v122; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v123; // rcx
  PVOID v124; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v125; // rcx
  struct _UNICODE_STRING *v126; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v127; // rcx
  PVOID v128; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v129; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v130; // rdx
  struct _UNICODE_STRING *v131; // rdx
  struct _UNICODE_STRING *v132; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v133; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v134; // rdx
  struct _UNICODE_STRING *v135; // rdx
  struct _UNICODE_STRING *v136; // rdx
  const char *ObjectAttributes; // [rsp+28h] [rbp-D8h]
  const char *ObjectAttributesa; // [rsp+28h] [rbp-D8h]
  char *ObjectAttributesb; // [rsp+28h] [rbp-D8h]
  const char *ObjectAttributesc; // [rsp+28h] [rbp-D8h]
  const char *ObjectAttributesd; // [rsp+28h] [rbp-D8h]
  const char *ObjectAttributese; // [rsp+28h] [rbp-D8h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+80h] [rbp-80h] BYREF
  char v144; // [rsp+88h] [rbp-78h]
  char v145; // [rsp+89h] [rbp-77h]
  PVOID v146; // [rsp+90h] [rbp-70h] BYREF
  PFILE_OBJECT FileObject; // [rsp+98h] [rbp-68h] BYREF
  PFLT_FILE_NAME_INFORMATION v148; // [rsp+A0h] [rbp-60h] BYREF
  PVOID v149; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING *v150; // [rsp+B0h] [rbp-50h] BYREF
  UnionFs *v151; // [rsp+B8h] [rbp-48h]
  PVOID v152[2]; // [rsp+C0h] [rbp-40h] BYREF
  PVOID *p_FltObject; // [rsp+D0h] [rbp-30h] BYREF
  PFLT_VOLUME RetVolume; // [rsp+D8h] [rbp-28h] BYREF
  struct _FLT_INSTANCE *v155; // [rsp+E0h] [rbp-20h]
  PVOID v156; // [rsp+F0h] [rbp-10h] BYREF
  PVOID v157; // [rsp+F8h] [rbp-8h] BYREF
  PVOID Object; // [rsp+100h] [rbp+0h] BYREF
  PVOID v159; // [rsp+108h] [rbp+8h] BYREF
  ULONG BufferSizeNeeded; // [rsp+110h] [rbp+10h] BYREF
  void *FileHandle; // [rsp+118h] [rbp+18h] BYREF
  PVOID FltObject; // [rsp+120h] [rbp+20h] BYREF
  PFLT_FILE_NAME_INFORMATION v163; // [rsp+128h] [rbp+28h] BYREF
  __int64 v164; // [rsp+130h] [rbp+30h] BYREF
  utl::_RefCountBase *v165[2]; // [rsp+138h] [rbp+38h]
  PVOID P; // [rsp+148h] [rbp+48h]
  ULONG v167; // [rsp+150h] [rbp+50h] BYREF
  int v168; // [rsp+154h] [rbp+54h]
  PVOID v169[2]; // [rsp+158h] [rbp+58h] BYREF
  UNICODE_STRING Source; // [rsp+168h] [rbp+68h] BYREF
  struct _UNICODE_STRING v171; // [rsp+178h] [rbp+78h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+190h] [rbp+90h] BYREF
  struct _FLT_INSTANCE *v173; // [rsp+1A0h] [rbp+A0h]
  struct _UNICODE_STRING FileName; // [rsp+1A8h] [rbp+A8h] BYREF
  char v175[16]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v176; // [rsp+1D0h] [rbp+D0h]
  __int64 v177; // [rsp+1E0h] [rbp+E0h]
  __int64 v178; // [rsp+1E8h] [rbp+E8h]
  __int128 v179; // [rsp+1F0h] [rbp+F0h]
  PFLT_NAME_CONTROL NameCtrl; // [rsp+200h] [rbp+100h]
  struct _UNICODE_STRING v181; // [rsp+208h] [rbp+108h] BYREF
  UNICODE_STRING SourceString; // [rsp+220h] [rbp+120h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+230h] [rbp+130h] BYREF
  struct _IO_DRIVER_CREATE_CONTEXT v184; // [rsp+240h] [rbp+140h] BYREF
  __int64 v185; // [rsp+260h] [rbp+160h]
  struct _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+268h] [rbp+168h] BYREF
  __int64 HostSilo; // [rsp+288h] [rbp+188h]
  struct _OBJECT_ATTRIBUTES v188; // [rsp+290h] [rbp+190h] BYREF
  struct _IO_STATUS_BLOCK v189; // [rsp+2C0h] [rbp+1C0h] BYREF
  char v190[8]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _QWORD v191[14]; // [rsp+2D8h] [rbp+1D8h] BYREF
  utl::_RefCountBase *v192[2]; // [rsp+348h] [rbp+248h] BYREF
  _QWORD v193[17]; // [rsp+358h] [rbp+258h] BYREF
  struct _OBJECT_ATTRIBUTES v194; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned int v195; // [rsp+4A0h] [rbp+3A0h]

  v157 = a4;
  FileObject = a3;
  v173 = a2;
  NameCtrl = a6;
  FltObject = 0;
  MappingTableForFileObject = UnionFs::Utils::GetMappingTableForFileObject(a2, a3, &FltObject, a7, 0);
  if ( MappingTableForFileObject < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)MappingTableForFileObject,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x2B6000F031CLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
      "PUSH: Getting mapping table",
      ObjectAttributes);
    return (unsigned int)MappingTableForFileObject;
  }
  v11 = (UnionFs::UfsScratchMappingTable *)FltObject;
  if ( !FltObject )
    MicrosoftTelemetryAssertTriggeredMsgKM("Shouldn't have been called without a mapping table");
  FileNameInformation = 0;
  p_FltObject = (PVOID *)a4;
  v195 = a5 & 0xFF00FF00;
  RetVolume = 0;
  v155 = 0;
  MappingTableForFileObject = UnionFs::Utils::GetFileNameInformation(
                                &p_FltObject,
                                v195 | 0x3000002,
                                &FileNameInformation,
                                a7);
  if ( MappingTableForFileObject < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)MappingTableForFileObject,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x15E000F0334LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
      "PUSH: Getting OPENED name",
      ObjectAttributes);
LABEL_8:
    v12 = FileNameInformation;
    FileNameInformation = 0;
    goto LABEL_9;
  }
  MappingTableForFileObject = FltParseFileNameInformation(FileNameInformation);
  if ( MappingTableForFileObject < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)MappingTableForFileObject,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x670000F0339LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
      "API: Parsing opened name info",
      ObjectAttributes);
    goto LABEL_8;
  }
  v13 = a3->Flags >> 17;
  v164 = 1;
  LOBYTE(v13) = (v13 & 1) == 0;
  LODWORD(v151) = v13;
  *(_OWORD *)v165 = 0;
  P = 0;
  v14 = UnionFs::UfsScratchMappingTable::LookupScratchRoot(
          v11,
          v173,
          FileNameInformation,
          v13,
          (struct UnionFs::LookupScratchRootResults *)&v164,
          (struct UnionFs::StackEventTracer *)a7);
  if ( v14 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v14,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x15F000F0346LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
      "PUSH: Looking up name in mapping table",
      ObjectAttributesa);
    v16 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v16, v15);
      ExFreePoolWithTag(v16, 0);
    }
    if ( v165[1] )
      utl::_RefCountBase::_DecStrong(v165[1]);
    v17 = FileNameInformation;
    FileNameInformation = 0;
    if ( v17 )
      FltReleaseFileNameInformation(v17);
    return (unsigned int)v14;
  }
  v18 = v165[1];
  v19 = v165[0];
  v20 = (volatile signed __int32 *)v165[1];
  if ( v165[1] )
    _InterlockedIncrement((volatile signed __int32 *)v165[1] + 2);
  v21 = (struct _UNICODE_STRING *)P;
  v156 = P;
  P = 0;
  *(_OWORD *)v192 = 0;
  memset(v193, 0, sizeof(v193));
  if ( !v19 )
    goto LABEL_476;
  UnionFs::UfsLayerCtx::TryGetOwningUnion(
    v19,
    (struct UnionFs::UfsUnionCtxWithRundown *)v192,
    (struct UnionFs::StackEventTracer *)a7);
  if ( !v192[0] )
  {
    *(_DWORD *)&a7->Length = 0;
    *(&a7[34].MaximumLength + 1) = 0;
    if ( v20 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
    v20 = 0;
LABEL_476:
    p_FltObject = (PVOID *)v157;
    RetVolume = 0;
    v155 = 0;
    MappingTableForFileObject = UnionFs::UnionFsFilter::PassthroughNameQuery(v22, &p_FltObject, v195 | 1, NameCtrl, a7);
    if ( MappingTableForFileObject < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)MappingTableForFileObject,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x160000F0363LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
        "PUSH: Passthrough NORMALIZED query",
        ObjectAttributesa);
LABEL_478:
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v193, v39);
      if ( v193[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v193[16] + 24LL))(v193[16]);
      if ( v192[1] )
        utl::_RefCountBase::_DecStrong(v192[1]);
      if ( v21 )
      {
        if ( !LOBYTE(v21[1].Length) )
          *v21 = 0;
        FsFltWil::Details::FreeUnicodeString(v21, v135);
        ExFreePoolWithTag(v21, 0);
      }
      if ( v20 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
      if ( v18 )
        utl::_RefCountBase::_DecStrong(v18);
LABEL_490:
      v12 = FileNameInformation;
      FileNameInformation = 0;
LABEL_9:
      if ( v12 )
        FltReleaseFileNameInformation(v12);
      return (unsigned int)MappingTableForFileObject;
    }
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v193, v134);
    if ( v193[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v193[16] + 24LL))(v193[16]);
    if ( v192[1] )
      utl::_RefCountBase::_DecStrong(v192[1]);
    if ( v21 )
    {
      if ( !LOBYTE(v21[1].Length) )
        *v21 = 0;
      FsFltWil::Details::FreeUnicodeString(v21, v136);
      ExFreePoolWithTag(v21, 0);
    }
    if ( v20 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
    if ( v18 )
      utl::_RefCountBase::_DecStrong(v18);
    goto LABEL_503;
  }
  if ( HIDWORD(v164) == 1 )
  {
    v25 = v173;
LABEL_449:
    p_FltObject = (PVOID *)v157;
    RetVolume = (PFLT_VOLUME)FileObject;
    v155 = v25;
    MappingTableForFileObject = UnionFs::UnionFsFilter::PassthroughNameQuery(v22, &p_FltObject, v195 | 1, NameCtrl, a7);
    if ( MappingTableForFileObject >= 0 )
    {
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v193, v129);
      if ( v193[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v193[16] + 24LL))(v193[16]);
      if ( v192[1] )
        utl::_RefCountBase::_DecStrong(v192[1]);
      if ( v21 )
      {
        if ( !LOBYTE(v21[1].Length) )
          *v21 = 0;
        FsFltWil::Details::FreeUnicodeString(v21, v132);
        ExFreePoolWithTag(v21, 0);
      }
      if ( v20 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
      if ( v18 )
        utl::_RefCountBase::_DecStrong(v18);
      v133 = FileNameInformation;
      FileNameInformation = 0;
      goto LABEL_504;
    }
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)MappingTableForFileObject,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x166000F0397LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
      "PUSH: Passthrough NORMALIZED query to scratch",
      ObjectAttributesa);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v193, v130);
    if ( v193[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v193[16] + 24LL))(v193[16]);
    if ( v192[1] )
      utl::_RefCountBase::_DecStrong(v192[1]);
    if ( v21 )
    {
      if ( !LOBYTE(v21[1].Length) )
        *v21 = 0;
      FsFltWil::Details::FreeUnicodeString(v21, v131);
      ExFreePoolWithTag(v21, 0);
    }
    if ( v20 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
    if ( v18 )
      utl::_RefCountBase::_DecStrong(v18);
LABEL_462:
    v12 = FileNameInformation;
    FileNameInformation = 0;
    goto LABEL_9;
  }
  v191[0] = off_14007E748;
  v191[13] = v191;
  UnionFs::StackEventTracer::SetIgnoreStatusCallback(a7, v190);
  memset(&v194, 0, 0x48u);
  IoGetTransactionParameterBlock(FileObject);
  Silo = IoGetSilo(FileObject);
  v24 = (unsigned __int8)v13;
  v25 = v173;
  ObjectAttributesa = (const char *)a7;
  MappingTableForFileObject = UnionFs::Utils::StatItem(&FileNameInformation->Name, v173, Silo, v24, &v194);
  BufferSizeNeeded = MappingTableForFileObject;
  v26 = WORD1(a7[30].Buffer);
  if ( v26 )
  {
    v27 = v26 - 1;
    WORD1(a7[30].Buffer) = v27;
    v22 = 120 * (v27 + 1LL);
    v28 = *(_QWORD *)((char *)&a7->Length + v22);
    *(_QWORD *)((char *)&a7->Length + v22) = 0;
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 24LL))(v28);
  }
  if ( MappingTableForFileObject >= 0 )
    goto LABEL_449;
  if ( MappingTableForFileObject != -1073741766 && MappingTableForFileObject != -1073741772 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)MappingTableForFileObject,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x165000F0385LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
      "PUSH: Querying stat information",
      (const char *)a7);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v193, v29);
    if ( v193[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v193[16] + 24LL))(v193[16]);
    if ( v192[1] )
      utl::_RefCountBase::_DecStrong(v192[1]);
    if ( v21 )
    {
      if ( !LOBYTE(v21[1].Length) )
        *v21 = 0;
      FsFltWil::Details::FreeUnicodeString(v21, v30);
      ExFreePoolWithTag(v21, 0);
    }
    if ( v20 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
    if ( v18 )
      utl::_RefCountBase::_DecStrong(v18);
    v12 = FileNameInformation;
    FileNameInformation = 0;
    goto LABEL_9;
  }
  v152[0] = 0;
  FileNameInformationUnsafe = UnionFs::UfsPathName::AllocAndInit(FileNameInformation, v152, a7);
  if ( FileNameInformationUnsafe < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)FileNameInformationUnsafe,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x684000F03ABLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
      "PUSH: Allocating scratch name",
      (const char *)a7);
    v33 = (struct _UNICODE_STRING *)v152[0];
    if ( v152[0] )
    {
      if ( !*((_BYTE *)v152[0] + 16) )
        *(_OWORD *)v152[0] = 0;
      FsFltWil::Details::FreeUnicodeString(v33, v32);
      ExFreePoolWithTag(v33, 0);
    }
    FsFltWil::Details::ReleaseRundownProtectionCacheAware(
      (FsFltWil::Details *)v193,
      (struct FsFltWil::Details::RundownRefCacheAware *)v32);
    if ( v193[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v193[16] + 24LL))(v193[16]);
    if ( v192[1] )
      utl::_RefCountBase::_DecStrong(v192[1]);
    if ( v21 )
    {
      if ( !LOBYTE(v21[1].Length) )
        *v21 = 0;
      FsFltWil::Details::FreeUnicodeString(v21, v34);
      ExFreePoolWithTag(v21, 0);
    }
    if ( v20 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
    if ( v18 )
      utl::_RefCountBase::_DecStrong(v18);
LABEL_67:
    v35 = FileNameInformation;
    FileNameInformation = 0;
LABEL_68:
    if ( v35 )
      FltReleaseFileNameInformation(v35);
    return (unsigned int)FileNameInformationUnsafe;
  }
  *(_OWORD *)v175 = 0;
  v176 = 0;
  v177 = 0;
  v36 = (FileObject->Flags & 0x20000) == 0;
  v178 = 0;
  v179 = 0;
  *(_DWORD *)v175 = _mm_cvtsi128_si32((__m128i)0LL) | 3;
  if ( *((_DWORD *)v192[0] + 7) == 2 )
    v37 = *(_QWORD *)(*((_QWORD *)v192[0] + 4) + 16LL);
  else
    v37 = *((_QWORD *)UnionFs::g_FilterState + 10);
  v38 = (struct _UNICODE_STRING *)v152[0];
  ObjectAttributesb = v175;
  MappingTableForFileObject = UnionFs::UfsPathCache::LookupEntryPriv(v37, v25, v152[0], v36, 0);
  if ( MappingTableForFileObject < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)MappingTableForFileObject,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x14B000F03C0LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
      "PUSH: Cache lookup",
      v175);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v175);
    if ( v38 )
    {
      if ( !LOBYTE(v38[1].Length) )
        *v38 = 0;
      FsFltWil::Details::FreeUnicodeString(v38, (struct _UNICODE_STRING *)v39);
      ExFreePoolWithTag(v38, 0);
    }
    goto LABEL_478;
  }
  v40 = 0;
  v150 = 0;
  if ( (_DWORD)v178 == 2 )
  {
    v157 = 0;
    FileName = (struct _UNICODE_STRING)**((_OWORD **)&v179 + 1);
    v41 = *(struct _UNICODE_STRING *)v179;
    *(struct _UNICODE_STRING *)v169 = *v38;
    v171 = v41;
    v42 = UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(
            (UnionFs::Rtl *)v169,
            &v171,
            &FileName,
            &v157,
            (int)a7);
    VolumeFromInstance = v42;
    if ( v42 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v42,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x14D000F03D0LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
        "PUSH: Replacing substring",
        ObjectAttributesb);
      v45 = (struct _UNICODE_STRING *)v157;
LABEL_82:
      if ( v45 )
      {
        if ( !LOBYTE(v45[1].Length) )
          *v45 = 0;
        FsFltWil::Details::FreeUnicodeString(v45, v44);
        ExFreePoolWithTag(v45, 0);
      }
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v175);
      if ( v38 )
      {
        if ( !LOBYTE(v38[1].Length) )
          *v38 = 0;
        FsFltWil::Details::FreeUnicodeString(v38, v46);
        ExFreePoolWithTag(v38, 0);
      }
      FsFltWil::Details::ReleaseRundownProtectionCacheAware(
        (FsFltWil::Details *)v193,
        (struct FsFltWil::Details::RundownRefCacheAware *)v46);
      if ( v193[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v193[16] + 24LL))(v193[16]);
      if ( v192[1] )
        utl::_RefCountBase::_DecStrong(v192[1]);
      if ( v21 )
      {
        if ( !LOBYTE(v21[1].Length) )
          *v21 = 0;
        FsFltWil::Details::FreeUnicodeString(v21, v47);
        ExFreePoolWithTag(v21, 0);
      }
      if ( v20 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
      if ( v18 )
        utl::_RefCountBase::_DecStrong(v18);
LABEL_102:
      v48 = FileNameInformation;
      FileNameInformation = 0;
      if ( v48 )
        FltReleaseFileNameInformation(v48);
      return (unsigned int)VolumeFromInstance;
    }
    v49 = (struct _UNICODE_STRING *)v157;
    v150 = (struct _UNICODE_STRING *)v157;
  }
  else
  {
    VolumeFromInstance = UnionFs::UfsPathName::Copy(v38);
    if ( VolumeFromInstance < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)VolumeFromInstance,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x67E000F03D9LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
        "PUSH: Copying UfsPathName",
        v175);
      v45 = v150;
      goto LABEL_82;
    }
    v49 = v150;
  }
  utl::make_unique<UnionFs::FindAndStatResults,,0>(&v157);
  v50 = v157;
  if ( !v157 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x307000F03E1LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
      "ORIGIN: Allocating findAndStatResults",
      ObjectAttributesb);
    if ( v49 )
    {
      if ( !LOBYTE(v49[1].Length) )
        *v49 = 0;
      FsFltWil::Details::FreeUnicodeString(v49, v51);
      ExFreePoolWithTag(v49, 0);
    }
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v175);
    if ( v38 )
    {
      if ( !LOBYTE(v38[1].Length) )
        *v38 = 0;
      FsFltWil::Details::FreeUnicodeString(v38, v52);
      ExFreePoolWithTag(v38, 0);
    }
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v192);
    if ( v21 )
    {
      if ( !LOBYTE(v21[1].Length) )
        *v21 = 0;
      FsFltWil::Details::FreeUnicodeString(v21, v53);
      ExFreePoolWithTag(v21, 0);
    }
    if ( v20 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
LABEL_355:
    UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v164);
    v108 = FileNameInformation;
    FileNameInformation = 0;
    if ( v108 )
      FltReleaseFileNameInformation(v108);
    return 3221225626LL;
  }
  v54 = (unsigned __int8)v151;
  v149 = 0;
  *((_QWORD *)v157 + 12) = &v149;
  v55 = *v49;
  ObjectAttributesc = (const char *)a7;
  FileName = *v21;
  v171 = v55;
  v56 = UnionFs::UfsUnionCtx::FindAndStatItemInLayers(v192[0], &v171, &FileName, v54, v50);
  LODWORD(v151) = v56;
  if ( v56 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v56,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x167000F03EELL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
      "PUSH: Utils::FindAndStatItemInLayers",
      (const char *)a7);
LABEL_127:
    v58 = (struct _UNICODE_STRING *)v149;
    if ( v149 )
    {
      if ( !*((_BYTE *)v149 + 16) )
        *(_OWORD *)v149 = 0;
      FsFltWil::Details::FreeUnicodeString(v58, v57);
      ExFreePoolWithTag(v58, 0);
    }
    if ( v50 )
    {
      v59 = (utl::_RefCountBase *)v50[11];
      if ( v59 )
        utl::_RefCountBase::_DecStrong(v59);
      ExFreePoolWithTag(v50, 0);
    }
    if ( v49 )
    {
      if ( !LOBYTE(v49[1].Length) )
        *v49 = 0;
      FsFltWil::Details::FreeUnicodeString(v49, v57);
      ExFreePoolWithTag(v49, 0);
    }
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v175);
    if ( v38 )
    {
      if ( !LOBYTE(v38[1].Length) )
        *v38 = 0;
      FsFltWil::Details::FreeUnicodeString(v38, v60);
      ExFreePoolWithTag(v38, 0);
    }
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v192);
    if ( !LOBYTE(v21[1].Length) )
      *v21 = 0;
    FsFltWil::Details::FreeUnicodeString(v21, v61);
    ExFreePoolWithTag(v21, 0);
LABEL_146:
    if ( v20 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
    UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v164);
    v62 = FileNameInformation;
    FileNameInformation = 0;
    if ( v62 )
      FltReleaseFileNameInformation(v62);
    return (unsigned int)v151;
  }
  LOBYTE(v168) = 0;
  memset(&v184, 0, sizeof(v184));
  v144 = 0;
  v185 = 1;
  v184.Size = 40;
  v181 = 0;
  if ( BufferSizeNeeded == -1073741772 )
  {
    if ( v20 )
      _InterlockedIncrement(v20 + 2);
    v185 = IoGetSilo(FileObject);
    v184.TxnParameters = IoGetTransactionParameterBlock(FileObject);
    v181.Buffer = FileNameInformation->Name.Buffer;
    *(_DWORD *)&v181.Length = *(_DWORD *)&FileNameInformation->Name.Length;
    if ( *(_WORD *)v50 == 1 )
    {
      LOBYTE(v155) = 1;
      FltObject = 0;
      p_FltObject = &FltObject;
      RetVolume = 0;
      LODWORD(v151) = FltGetVolumeFromInstance(**(PFLT_INSTANCE **)(v50[10] + 8LL), &RetVolume);
      v63 = (UnionFs *)(unsigned int)v151;
      if ( (_BYTE)v155 )
      {
        v64 = p_FltObject;
        v169[0] = RetVolume;
        if ( *p_FltObject )
        {
          FltObjectDereference(*p_FltObject);
          v63 = (UnionFs *)(unsigned int)v151;
        }
        *v64 = v169[0];
      }
      if ( (int)v63 < 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          v63,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x168000F0413LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
          "API: Getting volume from instance",
          (const char *)a7);
        if ( FltObject )
          FltObjectDereference(FltObject);
        if ( v20 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
        goto LABEL_127;
      }
      BufferSizeNeeded = 0;
      FltGetVolumeName((PFLT_VOLUME)FltObject, 0, &BufferSizeNeeded);
      v66 = (struct _UNICODE_STRING *)BufferSizeNeeded;
      if ( BufferSizeNeeded > 0xFFFF )
      {
        MicrosoftTelemetryAssertTriggeredMsgKM("layerVolumeNameSize <= MAXUSHORT");
        v66 = (struct _UNICODE_STRING *)BufferSizeNeeded;
      }
      FileName = 0;
      v171 = *(struct _UNICODE_STRING *)v149;
      UnionFs::Utils::RemoveFinalComponent((UnionFs::Utils *)&v171, v66, (unsigned __int16)&FileName, v65);
      HostSilo = 1;
      memset(&DriverContext, 0, sizeof(DriverContext));
      DriverContext.Size = 40;
      HostSilo = PsGetHostSilo();
      *(_QWORD *)&v194.Length = 48;
      v194.ObjectName = &v171;
      *(_QWORD *)&v194.Attributes = 512;
      p_FltObject = &Object;
      v194.RootDirectory = 0;
      *(_OWORD *)&v194.SecurityDescriptor = 0;
      Object = 0;
      IoStatusBlock = 0;
      RetVolume = 0;
      LOBYTE(v155) = 1;
      FileObject = 0;
      v67 = FltCreateFileEx2(
              *(PFLT_FILTER *)UnionFs::g_FilterState,
              **(PFLT_INSTANCE **)(v50[10] + 8LL),
              (PHANDLE)&FileObject,
              (PFILE_OBJECT *)&RetVolume,
              0x80u,
              &v194,
              &IoStatusBlock,
              0,
              0,
              7u,
              1u,
              0x20u,
              0,
              0,
              0,
              &DriverContext);
      if ( (_BYTE)v155 )
      {
        v68 = *p_FltObject;
        *p_FltObject = RetVolume;
        if ( v68 )
          ObfDereferenceObject(v68);
      }
      if ( v67 < 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v67,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x16A000F0444LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
          "API: Opening parent",
          ObjectAttributesd);
        v70 = Object;
        Object = 0;
        if ( v70 )
          ObfDereferenceObject(v70);
        if ( FileObject )
          FltClose(FileObject);
        if ( FltObject )
          FltObjectDereference(FltObject);
        if ( v20 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
        v71 = (struct _UNICODE_STRING *)v149;
        if ( v149 )
        {
          if ( !*((_BYTE *)v149 + 16) )
            *(_OWORD *)v149 = 0;
          FsFltWil::Details::FreeUnicodeString(v71, v69);
          ExFreePoolWithTag(v71, 0);
        }
LABEL_182:
        if ( v50 )
        {
          v72 = (utl::_RefCountBase *)v50[11];
          if ( v72 )
            utl::_RefCountBase::_DecStrong(v72);
          ExFreePoolWithTag(v50, 0);
        }
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v150);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v175);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(v152);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v192);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v156);
        if ( v20 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
LABEL_188:
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v164);
        v73 = FileNameInformation;
        FileNameInformation = 0;
        if ( v73 )
          FltReleaseFileNameInformation(v73);
        return (unsigned int)v67;
      }
      v74 = v195;
      p_FltObject = (PVOID *)&v163;
      v163 = 0;
      RetVolume = 0;
      LOBYTE(v155) = 1;
      MappingTableForFileObject = FltGetFileNameInformationUnsafe(
                                    (PFILE_OBJECT)Object,
                                    **(PFLT_INSTANCE **)(v50[10] + 8LL),
                                    v195 | 1,
                                    (PFLT_FILE_NAME_INFORMATION *)&RetVolume);
      if ( (_BYTE)v155 )
      {
        v75 = (struct _FLT_FILE_NAME_INFORMATION *)*p_FltObject;
        *p_FltObject = RetVolume;
        if ( v75 )
          FltReleaseFileNameInformation(v75);
      }
      if ( MappingTableForFileObject < 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)MappingTableForFileObject,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x16B000F0453LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
          "API: Querying parent name",
          ObjectAttributesd);
        v76 = v163;
        v163 = 0;
        if ( v76 )
          FltReleaseFileNameInformation(v76);
        v77 = Object;
        Object = 0;
        if ( v77 )
          ObfDereferenceObject(v77);
        if ( FileObject )
          FltClose(FileObject);
        if ( FltObject )
          FltObjectDereference(FltObject);
        if ( v20 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v149);
        if ( v50 )
        {
          v78 = (utl::_RefCountBase *)v50[11];
          if ( v78 )
            utl::_RefCountBase::_DecStrong(v78);
          ExFreePoolWithTag(v50, 0);
        }
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v150);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v175);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(v152);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v192);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v156);
        if ( v20 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v164);
        goto LABEL_490;
      }
      v79 = (WCHAR **)utl::make_unique_pool<enum gsl::byte [0],256,1835943509,0>(v169);
      v40 = *v79;
      *v79 = 0;
      if ( v169[0] )
        ExFreePoolWithTag(v169[0], 0);
      if ( !v40 )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000009ALL,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x1CD000F045FLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
          "ORIGIN: Allocating fileNamesInfoBuffer",
          ObjectAttributesd);
        v80 = v163;
        v163 = 0;
        if ( v80 )
          FltReleaseFileNameInformation(v80);
        v81 = Object;
        Object = 0;
        if ( v81 )
          ObfDereferenceObject(v81);
        if ( FileObject )
          FltClose(FileObject);
        if ( FltObject )
          FltObjectDereference(FltObject);
        if ( v20 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v149);
        if ( v50 )
        {
          v82 = (utl::_RefCountBase *)v50[11];
          if ( v82 )
            utl::_RefCountBase::_DecStrong(v82);
          ExFreePoolWithTag(v50, 0);
        }
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v150);
        UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v175);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(v152);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v192);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v156);
        if ( v20 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
        goto LABEL_355;
      }
      v67 = FltQueryDirectoryFile(
              **(PFLT_INSTANCE **)(v50[10] + 8LL),
              (PFILE_OBJECT)Object,
              v40,
              0x400u,
              FileNamesInformation,
              1u,
              &FileName,
              1u,
              0);
      if ( v67 == -1073741809 )
      {
        MicrosoftTelemetryAssertTriggeredMsgKM("status != STATUS_NO_SUCH_FILE");
LABEL_235:
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v67,
          (int)a7,
          (struct UnionFs::StackEventTracer *)0x16C000F0470LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
          "API: Getting final component long name",
          ObjectAttributesc);
        v83 = v163;
        v163 = 0;
        if ( v83 )
          FltReleaseFileNameInformation(v83);
        v84 = Object;
        Object = 0;
        if ( v84 )
          ObfDereferenceObject(v84);
        if ( FileObject )
          FltClose(FileObject);
        if ( FltObject )
          FltObjectDereference(FltObject);
        ExFreePoolWithTag(v40, 0);
        if ( v20 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v149);
        goto LABEL_182;
      }
      if ( v67 < 0 )
        goto LABEL_235;
      v85 = v163;
      v144 = 1;
      v163 = 0;
      if ( v85 )
        FltReleaseFileNameInformation(v85);
      v86 = Object;
      Object = 0;
      if ( v86 )
        ObfDereferenceObject(v86);
      if ( FileObject )
        FltClose(FileObject);
      if ( FltObject )
        FltObjectDereference(FltObject);
    }
    else
    {
      v74 = v195;
    }
    v87 = v165[0];
    FileObject = (PFILE_OBJECT)v165[0];
    v88 = v20;
    v145 = 0;
  }
  else
  {
    if ( *(_WORD *)v50 == 2 )
    {
      v67 = -1073741766;
      UnionFs::ProcessTraceInfoOrigin(
        (UnionFs *)0xC000003ALL,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x251000F0483LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
        "ORIGIN: Item not found in scratch or layers",
        (const char *)&FileNameInformation->Name,
        a7);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v149);
      if ( v50 )
      {
        v89 = (utl::_RefCountBase *)v50[11];
        if ( v89 )
          utl::_RefCountBase::_DecStrong(v89);
        ExFreePoolWithTag(v50, 0);
      }
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v150);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v175);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(v152);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v192);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v156);
      if ( v20 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
      goto LABEL_188;
    }
    v88 = (volatile signed __int32 *)v50[11];
    v87 = (utl::_RefCountBase *)v50[10];
    FileObject = (PFILE_OBJECT)v87;
    if ( v88 )
      _InterlockedIncrement(v88 + 2);
    v74 = v195;
    v185 = PsGetHostSilo();
    v145 = 1;
    v90 = (unsigned __int8)v168;
    v181 = *(struct _UNICODE_STRING *)v149;
    if ( *(_WORD *)v50 == 1 )
      v90 = 1;
    v168 = v90;
  }
  LOBYTE(v155) = 1;
  p_FltObject = &v159;
  v159 = 0;
  RetVolume = 0;
  VolumeFromInstance = FltGetVolumeFromInstance(**((PFLT_INSTANCE **)v87 + 1), &RetVolume);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FLT_VOLUME *,void (*)(void *),&void FltObjectDereference(void *),wistd::integral_constant<unsigned __int64,0>,_FLT_VOLUME *,_FLT_VOLUME *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_FLT_VOLUME *,void (*)(void *),&void FltObjectDereference(void *),wistd::integral_constant<unsigned __int64,0>,_FLT_VOLUME *,_FLT_VOLUME *,0,std::nullptr_t>>>>(&p_FltObject);
  if ( VolumeFromInstance < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)VolumeFromInstance,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x185000F049ELL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
      "API: Getting volume from instance",
      ObjectAttributesc);
    if ( v159 )
      FltObjectDereference(v159);
    if ( v40 )
      ExFreePoolWithTag(v40, 0);
    if ( v88 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v88);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v149);
    if ( v50 )
    {
      v91 = (utl::_RefCountBase *)v50[11];
      if ( v91 )
        utl::_RefCountBase::_DecStrong(v91);
      ExFreePoolWithTag(v50, 0);
    }
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v150);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v175);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(v152);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v192);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v156);
    if ( v20 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
    UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v164);
    goto LABEL_102;
  }
  v167 = 0;
  FltGetVolumeName((PFLT_VOLUME)v159, 0, &v167);
  v93 = (struct _UNICODE_STRING *)v167;
  if ( v167 > 0xFFFF )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("volumeNameSize <= MAXUSHORT");
    v93 = (struct _UNICODE_STRING *)v167;
  }
  Source = 0;
  UnionFs::Utils::RemoveFinalComponent((UnionFs::Utils *)&v181, v93, (unsigned __int16)&Source, v92);
  v94 = FileObject;
  v188.ObjectName = &v181;
  v188.RootDirectory = 0;
  p_FltObject = &v146;
  v146 = 0;
  RetVolume = 0;
  LOBYTE(v155) = 1;
  FileHandle = 0;
  *(_QWORD *)&v188.Length = 48;
  *(_QWORD *)&v188.Attributes = 512;
  *(_OWORD *)&v188.SecurityDescriptor = 0;
  v189 = 0;
  LODWORD(v151) = FltCreateFileEx2(
                    *(PFLT_FILTER *)UnionFs::g_FilterState,
                    *(PFLT_INSTANCE *)FileObject->DeviceObject,
                    &FileHandle,
                    (PFILE_OBJECT *)&RetVolume,
                    0x80u,
                    &v188,
                    &v189,
                    0,
                    0,
                    7u,
                    1u,
                    0x20u,
                    0,
                    0,
                    0,
                    &v184);
  v95 = (UnionFs *)(unsigned int)v151;
  if ( (_BYTE)v155 )
  {
    v96 = *p_FltObject;
    *p_FltObject = RetVolume;
    if ( v96 )
    {
      ObfDereferenceObject(v96);
      v95 = (UnionFs *)(unsigned int)v151;
    }
  }
  if ( (int)v95 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      v95,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x187000F04C6LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
      "API: Opening parent",
      ObjectAttributese);
    v97 = v146;
    v146 = 0;
    if ( v97 )
      ObfDereferenceObject(v97);
    if ( FileHandle )
      FltClose(FileHandle);
    if ( v159 )
      FltObjectDereference(v159);
    if ( v40 )
      ExFreePoolWithTag(v40, 0);
    if ( v88 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v88);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v149);
    if ( v50 )
    {
      v98 = (utl::_RefCountBase *)v50[11];
      if ( v98 )
        utl::_RefCountBase::_DecStrong(v98);
      ExFreePoolWithTag(v50, 0);
    }
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v150);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v175);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(v152);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v192);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v156);
    goto LABEL_146;
  }
  p_FltObject = (PVOID *)&v148;
  v148 = 0;
  RetVolume = 0;
  LOBYTE(v155) = 1;
  FileNameInformationUnsafe = FltGetFileNameInformationUnsafe(
                                (PFILE_OBJECT)v146,
                                *(PFLT_INSTANCE *)v94->DeviceObject,
                                v74 | 1,
                                (PFLT_FILE_NAME_INFORMATION *)&RetVolume);
  if ( (_BYTE)v155 )
  {
    v99 = (struct _FLT_FILE_NAME_INFORMATION *)*p_FltObject;
    *p_FltObject = RetVolume;
    if ( v99 )
      FltReleaseFileNameInformation(v99);
  }
  if ( FileNameInformationUnsafe < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)FileNameInformationUnsafe,
      (int)a7,
      (struct UnionFs::StackEventTracer *)0x188000F04D3LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
      "API: Querying parent name",
      ObjectAttributese);
    v100 = v148;
    v148 = 0;
    if ( v100 )
      FltReleaseFileNameInformation(v100);
    v101 = v146;
    v146 = 0;
    if ( v101 )
      ObfDereferenceObject(v101);
    if ( FileHandle )
      FltClose(FileHandle);
    if ( v159 )
      FltObjectDereference(v159);
    if ( v40 )
      ExFreePoolWithTag(v40, 0);
    if ( v88 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v88);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v149);
    if ( v50 )
    {
      v102 = (utl::_RefCountBase *)v50[11];
      if ( v102 )
        utl::_RefCountBase::_DecStrong(v102);
      ExFreePoolWithTag(v50, 0);
    }
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v150);
    UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v175);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(v152);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v192);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v156);
    if ( v20 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
    UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v164);
    goto LABEL_67;
  }
  if ( (_BYTE)v168 )
  {
    if ( *(_WORD *)v50 != 1 )
      MicrosoftTelemetryAssertTriggeredMsgKM("findAndStatResults->FindResult == LAYER_FIND_RESULT::Found");
    if ( v94 != (PFILE_OBJECT)v50[10] )
      MicrosoftTelemetryAssertTriggeredMsgKM("scratchOrLayerCtx == findAndStatResults->FoundLayer");
    if ( v40 )
      MicrosoftTelemetryAssertTriggeredMsgKM("!fileNamesInfoBuffer");
    v103 = (WCHAR **)utl::make_unique_pool<enum gsl::byte [0],256,1835943509,0>(v169);
    v104 = *v103;
    *v103 = 0;
    if ( v40 )
      ExFreePoolWithTag(v40, 0);
    if ( v169[0] )
      ExFreePoolWithTag(v169[0], 0);
    if ( !v104 )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x1CE000F04E5LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
        "ORIGIN: Allocating fileNamesInfoBuffer",
        ObjectAttributese);
      v105 = v148;
      v148 = 0;
      if ( v105 )
        FltReleaseFileNameInformation(v105);
      v106 = v146;
      v146 = 0;
      if ( v106 )
        ObfDereferenceObject(v106);
      if ( FileHandle )
        FltClose(FileHandle);
      if ( v159 )
        FltObjectDereference(v159);
      if ( v88 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v88);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v149);
      if ( v50 )
      {
        v107 = (utl::_RefCountBase *)v50[11];
        if ( v107 )
          utl::_RefCountBase::_DecStrong(v107);
        ExFreePoolWithTag(v50, 0);
      }
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v150);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v175);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(v152);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v192);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v156);
      if ( v20 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
      goto LABEL_355;
    }
    MappingTableForFileObject = FltQueryDirectoryFile(
                                  *(PFLT_INSTANCE *)FileObject->DeviceObject,
                                  (PFILE_OBJECT)v146,
                                  v104,
                                  0x400u,
                                  FileNamesInformation,
                                  1u,
                                  &Source,
                                  1u,
                                  0);
    if ( MappingTableForFileObject == -1073741809 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("status != STATUS_NO_SUCH_FILE");
LABEL_361:
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)MappingTableForFileObject,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x189000F04F5LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
        "API: Getting final component long name",
        ObjectAttributese);
      v109 = v148;
      v148 = 0;
      if ( v109 )
        FltReleaseFileNameInformation(v109);
      v110 = v146;
      v146 = 0;
      if ( v110 )
        ObfDereferenceObject(v110);
      if ( FileHandle )
        FltClose(FileHandle);
      if ( v159 )
        FltObjectDereference(v159);
      ExFreePoolWithTag(v104, 0);
      if ( v88 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v88);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v149);
      if ( v50 )
      {
        v111 = (utl::_RefCountBase *)v50[11];
        if ( v111 )
          utl::_RefCountBase::_DecStrong(v111);
        ExFreePoolWithTag(v50, 0);
      }
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v150);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v175);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(v152);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v192);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v156);
      if ( v20 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
      UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v164);
      goto LABEL_462;
    }
    if ( MappingTableForFileObject < 0 )
      goto LABEL_361;
    v40 = v104;
    Source.Buffer = v104 + 6;
    Length = v104[4];
    Source.Length = Length;
    Source.MaximumLength = Length;
  }
  else if ( v144 )
  {
    Source.Buffer = v40 + 6;
    Length = v40[4];
    Source.Length = Length;
    Source.MaximumLength = Length;
  }
  else
  {
    Length = Source.Length;
  }
  SourceString = 0;
  UnicodeString = 0;
  if ( !v145 )
    goto LABEL_406;
  v113 = (UnionFs::UfsLayerCtx *)v50[10];
  v171 = 0;
  UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(v113, &v171, 0);
  FileName = 0;
  UnionFs::UfsLayerCtx::GetNormalizedLayerRootPath(v165[0], &FileName, 0);
  v169[0] = v173;
  LOWORD(v169[1]) = 0;
  *(_DWORD *)((char *)&v169[1] + 2) = 0;
  HIWORD(v169[1]) = 0;
  appended = UnionFs::Utils::RewritePath(v148, &v171, &FileName, &UnicodeString, (int)a7, (__int64)v169);
  if ( (_DWORD)v178 == 2 )
  {
    FileObject = 0;
    IoStatusBlock = *(struct _IO_STATUS_BLOCK *)v179;
    v171 = (struct _UNICODE_STRING)**((_OWORD **)&v179 + 1);
    FileNameInformationUnsafe = UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(
                                  (UnionFs::Rtl *)&UnicodeString,
                                  &v171,
                                  (PCUNICODE_STRING)&IoStatusBlock,
                                  &FileObject,
                                  (int)a7);
    if ( FileNameInformationUnsafe < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)FileNameInformationUnsafe,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x1B2000F052CLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
        "PUSH: Replacing substring",
        ObjectAttributese);
LABEL_386:
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&FileObject);
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v116);
      v117 = v148;
      v148 = 0;
      if ( v117 )
        FltReleaseFileNameInformation(v117);
      v118 = v146;
      v146 = 0;
      if ( v118 )
        ObfDereferenceObject(v118);
      if ( FileHandle )
        FltClose(FileHandle);
      if ( v159 )
        FltObjectDereference(v159);
      if ( v40 )
        ExFreePoolWithTag(v40, 0);
      if ( v88 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v88);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v149);
      utl::unique_ptr<UnionFs::FindAndStatResults,utl::default_delete<UnionFs::FindAndStatResults>>::~unique_ptr<UnionFs::FindAndStatResults,utl::default_delete<UnionFs::FindAndStatResults>>(&v157);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v150);
      UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v175);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(v152);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v192);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v156);
      if ( v20 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
      UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v164);
      v35 = FileNameInformation;
      FileNameInformation = 0;
      goto LABEL_68;
    }
    LOBYTE(v115) = 1;
    FileNameInformationUnsafe = UnionFs::UfsPathName::AsUnicodeString(FileObject, &UnicodeString, a7, v115);
    if ( FileNameInformationUnsafe < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)FileNameInformationUnsafe,
        (int)a7,
        (struct UnionFs::StackEventTracer *)0x1B3000F0531LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
        "PUSH: Copying UfsPathName to unique_unicode_string",
        ObjectAttributese);
      goto LABEL_386;
    }
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&FileObject);
  }
  if ( appended == -1073741275 )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("Hit STATUS_NOT_FOUND mapping name to scratch");
    Length = Source.Length;
LABEL_406:
    SourceString = v148->Name;
LABEL_407:
    v119 = NameCtrl;
    appended = FltCheckAndGrowNameControl(NameCtrl, Length + SourceString.Length + 2);
    if ( appended >= 0 )
    {
      RtlCopyUnicodeString(&v119->Name, &SourceString);
      appended = RtlAppendUnicodeToString(&v119->Name, L"\\");
      if ( appended >= 0 )
      {
        appended = RtlAppendUnicodeStringToString(&v119->Name, &Source);
        if ( appended >= 0 )
        {
          FsFltWil::Details::FreeUnicodeString(&UnicodeString, v126);
          v127 = v148;
          v148 = 0;
          if ( v127 )
            FltReleaseFileNameInformation(v127);
          v128 = v146;
          v146 = 0;
          if ( v128 )
            ObfDereferenceObject(v128);
          if ( FileHandle )
            FltClose(FileHandle);
          if ( v159 )
            FltObjectDereference(v159);
          if ( v40 )
            ExFreePoolWithTag(v40, 0);
          if ( v88 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v88);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v149);
          utl::unique_ptr<UnionFs::FindAndStatResults,utl::default_delete<UnionFs::FindAndStatResults>>::~unique_ptr<UnionFs::FindAndStatResults,utl::default_delete<UnionFs::FindAndStatResults>>(&v157);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v150);
          UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v175);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(v152);
          UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v192);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v156);
          if ( v20 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
          UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v164);
LABEL_503:
          v133 = FileNameInformation;
          FileNameInformation = 0;
LABEL_504:
          if ( v133 )
            FltReleaseFileNameInformation(v133);
          return 0;
        }
      }
      v120 = "API: Appending final component";
      v121 = 0x16F000F0561LL;
    }
    else
    {
      v120 = "API: Growing OutputNameControl";
      v121 = 0x16E000F0558LL;
    }
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)appended,
      (int)a7,
      (struct UnionFs::StackEventTracer *)v121,
      (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
      v120,
      ObjectAttributese);
    goto LABEL_412;
  }
  if ( appended >= 0 )
  {
    Length = Source.Length;
    SourceString = UnicodeString;
    goto LABEL_407;
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)appended,
    (int)a7,
    (struct UnionFs::StackEventTracer *)0x16D000F0543LL,
    (unsigned __int64)"UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName",
    "PUSH: Rewriting path",
    ObjectAttributese);
LABEL_412:
  FsFltWil::Details::FreeUnicodeString(&UnicodeString, v122);
  v123 = v148;
  v148 = 0;
  if ( v123 )
    FltReleaseFileNameInformation(v123);
  v124 = v146;
  v146 = 0;
  if ( v124 )
    ObfDereferenceObject(v124);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v159 )
    FltObjectDereference(v159);
  if ( v40 )
    ExFreePoolWithTag(v40, 0);
  if ( v88 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v88);
  utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v149);
  utl::unique_ptr<UnionFs::FindAndStatResults,utl::default_delete<UnionFs::FindAndStatResults>>::~unique_ptr<UnionFs::FindAndStatResults,utl::default_delete<UnionFs::FindAndStatResults>>(&v157);
  utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v150);
  UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)v175);
  utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(v152);
  UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v192);
  utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v156);
  if ( v20 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v20);
  UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v164);
  v125 = FileNameInformation;
  FileNameInformation = 0;
  if ( v125 )
    FltReleaseFileNameInformation(v125);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140037b54  mov     [rsp-8+arg_0], rbx
0x140037b59  push    rbp
0x140037b5a  push    rsi
0x140037b5b  push    rdi
0x140037b5c  push    r12
0x140037b5e  push    r13
0x140037b60  push    r14
0x140037b62  push    r15
0x140037b64  lea     rbp, [rsp-340h]
0x140037b6c  sub     rsp, 440h
0x140037b73  mov     rax, cs:__security_cookie
0x140037b7a  xor     rax, rsp
0x140037b7d  mov     [rbp+370h+var_40], rax
0x140037b84  mov     rax, [rbp+370h+arg_28]
0x140037b8b  mov     rdi, r8
0x140037b8e  mov     r15, [rbp+370h+arg_30]
0x140037b95  mov     r10, rdx
0x140037b98  mov     rsi, r9
0x140037b9b  mov     [rbp+370h+var_378], r9
0x140037b9f  mov     [rbp+370h+FileObject], r8
0x140037ba3  xor     r12d, r12d
0x140037ba6  mov     [rbp+370h+var_2D0], rdx
0x140037bad  lea     r8, [rbp+370h+FltObject]
0x140037bb1  mov     r9, r15
0x140037bb4  mov     [rbp+370h+NameCtrl], rax
0x140037bbb  mov     rdx, rdi
0x140037bbe  mov     [rbp+370h+FltObject], r12
0x140037bc2  mov     rcx, r10
0x140037bc5  mov     qword ptr [rsp+470h+DesiredAccess], r12
0x140037bca  call    ?GetMappingTableForFileObject@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAPEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@PEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@@Z; UnionFs::Utils::GetMappingTableForFileObject(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsScratchMappingTable * *,UnionFs::StackEventTracer &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> *)
0x140037bcf  mov     ebx, eax
0x140037bd1  test    eax, eax
0x140037bd3  jns     short loc_140037C03
0x140037bd5  lea     rax, aPushGettingMap; "PUSH: Getting mapping table"
0x140037bdc  mov     r8, 2B6000F031Ch; struct UnionFs::StackEventTracer *
0x140037be6  lea     r9, aUnionfsUnionfs_40; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x140037bed  mov     qword ptr [rsp+470h+DesiredAccess], rax; char *
0x140037bf2  mov     rdx, r15; int
0x140037bf5  mov     ecx, ebx; this
0x140037bf7  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140037bfc  mov     eax, ebx
0x140037bfe  jmp     loc_14003A171
0x140037c03  mov     r14, [rbp+370h+FltObject]
0x140037c07  test    r14, r14
0x140037c0a  jnz     short loc_140037C18
0x140037c0c  lea     rcx, aShouldnTHaveBe; "Shouldn't have been called without a ma"...
0x140037c13  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140037c18  mov     [rbp+370h+FileNameInformation], r12
0x140037c1c  lea     r8, [rbp+370h+FileNameInformation]
0x140037c20  mov     r12d, [rbp+370h+arg_20]
0x140037c27  lea     rcx, [rbp+370h+var_3A0]
0x140037c2b  and     r12d, 0FF00FF00h
0x140037c32  mov     [rbp+370h+var_3A0], rsi
0x140037c36  mov     edx, r12d
0x140037c39  mov     [rbp+370h+arg_20], r12d
0x140037c40  xor     esi, esi
0x140037c42  or      edx, 3000002h
0x140037c48  mov     r9, r15
0x140037c4b  mov     [rbp+370h+RetVolume], rsi
0x140037c4f  mov     [rbp+370h+var_390], rsi
0x140037c53  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x140037c58  mov     ebx, eax
0x140037c5a  test    eax, eax
0x140037c5c  jns     short loc_140037CA7
0x140037c5e  lea     rax, aPushGettingOpe_1; "PUSH: Getting OPENED name"
0x140037c65  mov     r8, 15E000F0334h; struct UnionFs::StackEventTracer *
0x140037c6f  lea     r9, aUnionfsUnionfs_40; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x140037c76  mov     qword ptr [rsp+470h+DesiredAccess], rax; char *
0x140037c7b  mov     rdx, r15; int
0x140037c7e  mov     ecx, ebx; this
0x140037c80  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140037c85  mov     rcx, [rbp+370h+FileNameInformation]; FileNameInformation
0x140037c89  mov     [rbp+370h+FileNameInformation], rsi
0x140037c8d  test    rcx, rcx
0x140037c90  jz      loc_140037BFC
0x140037c96  call    cs:__imp_FltReleaseFileNameInformation
0x140037c9d  nop     dword ptr [rax+rax+00h]
0x140037ca2  jmp     loc_140037BFC
0x140037ca7  mov     rcx, [rbp+370h+FileNameInformation]; FileNameInformation
0x140037cab  call    cs:__imp_FltParseFileNameInformation
0x140037cb2  nop     dword ptr [rax+rax+00h]
0x140037cb7  mov     ebx, eax
0x140037cb9  test    eax, eax
0x140037cbb  jns     short loc_140037CE6
0x140037cbd  lea     rax, aApiParsingOpen; "API: Parsing opened name info"
0x140037cc4  mov     r8, 670000F0339h; struct UnionFs::StackEventTracer *
0x140037cce  lea     r9, aUnionfsUnionfs_40; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x140037cd5  mov     qword ptr [rsp+470h+DesiredAccess], rax; char *
0x140037cda  mov     rdx, r15; int
0x140037cdd  mov     ecx, ebx; this
0x140037cdf  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140037ce4  jmp     short loc_140037C85
0x140037ce6  mov     r13d, [rdi+50h]
0x140037cea  mov     eax, 1
0x140037cef  mov     r8, [rbp+370h+FileNameInformation]; struct _FLT_FILE_NAME_INFORMATION *
0x140037cf3  xorps   xmm0, xmm0
0x140037cf6  mov     rdx, [rbp+370h+var_2D0]; struct _FLT_INSTANCE *
0x140037cfd  mov     rcx, r14; this
0x140037d00  shr     r13d, 11h
0x140037d04  not     r13b
0x140037d07  mov     [rbp+370h+var_340], rax
0x140037d0b  and     r13b, al
0x140037d0e  mov     [rsp+470h+ObjectAttributes], r15; char *
0x140037d13  lea     rax, [rbp+370h+var_340]
0x140037d17  mov     dword ptr [rbp+370h+var_3B8], r13d
0x140037d1b  mov     r9b, r13b; bool
0x140037d1e  mov     qword ptr [rsp+470h+DesiredAccess], rax; struct UnionFs::LookupScratchRootResults *
0x140037d23  movdqu  xmmword ptr [rbp+370h+var_338], xmm0
0x140037d28  mov     [rbp+370h+P], rsi
0x140037d2c  call    ?LookupScratchRoot@UfsScratchMappingTable@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@_NAEAULookupScratchRootResults@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsScratchMappingTable::LookupScratchRoot(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,bool,UnionFs::LookupScratchRootResults &,UnionFs::StackEventTracer &)
0x140037d31  mov     edi, eax
0x140037d33  test    eax, eax
0x140037d35  jns     loc_140037DBE
0x140037d3b  lea     rax, aPushLookingUpN_0; "PUSH: Looking up name in mapping table"
0x140037d42  mov     r8, 15F000F0346h; struct UnionFs::StackEventTracer *
0x140037d4c  lea     r9, aUnionfsUnionfs_40; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x140037d53  mov     qword ptr [rsp+470h+DesiredAccess], rax; char *
0x140037d58  mov     rdx, r15; int
0x140037d5b  mov     ecx, edi; this
0x140037d5d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140037d62  mov     rbx, [rbp+370h+P]
0x140037d66  test    rbx, rbx
0x140037d69  jz      short loc_140037D90
0x140037d6b  cmp     [rbx+10h], sil
0x140037d6f  jnz     short loc_140037D77
0x140037d71  xorps   xmm0, xmm0
0x140037d74  movups  xmmword ptr [rbx], xmm0
0x140037d77  mov     rcx, rbx; UnicodeString
0x140037d7a  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140037d7f  xor     edx, edx; Tag
0x140037d81  mov     rcx, rbx; P
0x140037d84  call    cs:__imp_ExFreePoolWithTag
0x140037d8b  nop     dword ptr [rax+rax+00h]
0x140037d90  mov     rcx, [rbp+370h+var_338+8]; this
0x140037d94  test    rcx, rcx
0x140037d97  jz      short loc_140037D9E
0x140037d99  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140037d9e  mov     rcx, [rbp+370h+FileNameInformation]; FileNameInformation
0x140037da2  mov     [rbp+370h+FileNameInformation], rsi
0x140037da6  test    rcx, rcx
0x140037da9  jz      short loc_140037DB7
0x140037dab  call    cs:__imp_FltReleaseFileNameInformation
0x140037db2  nop     dword ptr [rax+rax+00h]
0x140037db7  mov     eax, edi
0x140037db9  jmp     loc_14003A171
0x140037dbe  mov     r14, [rbp+370h+var_338+8]
0x140037dc2  mov     rbx, [rbp+370h+var_338]
0x140037dc6  mov     rdi, r14
0x140037dc9  test    r14, r14
0x140037dcc  jz      short loc_140037DD3
0x140037dce  lock inc dword ptr [r14+8]
0x140037dd3  mov     rsi, [rbp+370h+P]
0x140037dd7  lea     rcx, [rbp+370h+var_118]; void *
0x140037dde  xor     eax, eax
0x140037de0  mov     [rbp+370h+var_380], rsi
0x140037de4  xorps   xmm0, xmm0
0x140037de7  mov     [rbp+370h+P], rax
0x140037deb  xor     edx, edx; Val
0x140037ded  mov     [rbp+370h+var_118], rax
0x140037df4  mov     r8d, 88h; Size
0x140037dfa  mov     [rbp+370h+var_110], al
0x140037e00  movdqu  xmmword ptr [rbp+370h+var_128], xmm0
0x140037e08  mov     [rbp+370h+var_98], rax
0x140037e0f  call    memset
0x140037e14  test    rbx, rbx
0x140037e17  jz      loc_140039FF7
0x140037e1d  mov     r8, r15; struct UnionFs::StackEventTracer *
0x140037e20  lea     rdx, [rbp+370h+var_128]; struct UnionFs::UfsUnionCtxWithRundown *
0x140037e27  mov     rcx, rbx; this
0x140037e2a  call    ?TryGetOwningUnion@UfsLayerCtx@UnionFs@@QEBAJAEAUUfsUnionCtxWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsLayerCtx::TryGetOwningUnion(UnionFs::UfsUnionCtxWithRundown &,UnionFs::StackEventTracer &)
0x140037e2f  cmp     [rbp+370h+var_128], 0
0x140037e37  jnz     short loc_140037E5C
0x140037e39  xor     r13d, r13d
0x140037e3c  mov     [r15], r13d
0x140037e3f  mov     [r15+224h], r13w
0x140037e47  test    rdi, rdi
0x140037e4a  jz      short loc_140037E54
0x140037e4c  mov     rcx, rdi; this
0x140037e4f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140037e54  mov     rdi, r13
0x140037e57  jmp     loc_140039FFA
0x140037e5c  cmp     dword ptr [rbp+370h+var_340+4], 1
0x140037e60  jz      loc_140039E80
0x140037e66  lea     rax, off_14007E748
0x140037e6d  mov     rcx, r15
0x140037e70  mov     [rbp+370h+var_198], rax
0x140037e77  lea     rdx, [rbp+370h+var_1A0]
0x140037e7e  lea     rax, [rbp+370h+var_198]
0x140037e85  mov     [rbp+370h+var_130], rax
0x140037e8c  call    ?SetIgnoreStatusCallback@StackEventTracer@UnionFs@@QEAAXV?$function@$$A6A_NJ@Z@wistd@@@Z; UnionFs::StackEventTracer::SetIgnoreStatusCallback(wistd::function<bool (long)>)
0x140037e91  xor     edx, edx; Val
0x140037e93  lea     rcx, [rbp+370h+var_90]; void *
0x140037e9a  lea     r8d, [rdx+48h]; Size
0x140037e9e  call    memset
0x140037ea3  mov     rcx, [rbp+370h+FileObject]; FileObject
0x140037ea7  call    cs:__imp_IoGetTransactionParameterBlock
0x140037eae  nop     dword ptr [rax+rax+00h]
0x140037eb3  mov     rcx, [rbp+370h+FileObject]
0x140037eb7  mov     rbx, rax
0x140037eba  call    cs:__imp_IoGetSilo
0x140037ec1  nop     dword ptr [rax+rax+00h]
0x140037ec6  mov     rcx, [rbp+370h+FileNameInformation]
0x140037eca  lea     rdx, [rbp+370h+var_90]
0x140037ed1  mov     [rsp+470h+AllocationSize], 0
0x140037eda  add     rcx, 8
0x140037ede  movzx   r9d, r13b
0x140037ee2  mov     r8, rax
0x140037ee5  mov     r13, [rbp+370h+var_2D0]
0x140037eec  mov     [rsp+470h+IoStatusBlock], rbx
0x140037ef1  mov     [rsp+470h+ObjectAttributes], r15; char *
0x140037ef6  mov     qword ptr [rsp+470h+DesiredAccess], rdx
0x140037efb  mov     rdx, r13
0x140037efe  call    ?StatItem@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAVStackEventTracer@2@QEAU_TXN_PARAMETER_BLOCK@@PEAU_FLT_CALLBACK_DATA@@@Z; UnionFs::Utils::StatItem(_UNICODE_STRING const &,_FLT_INSTANCE const &,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,UnionFs::StackEventTracer &,_TXN_PARAMETER_BLOCK * const,_FLT_CALLBACK_DATA *)
0x140037f03  mov     ebx, eax
0x140037f05  mov     [rbp+370h+BufferSizeNeeded], eax
0x140037f08  movzx   eax, word ptr [r15+1EAh]
0x140037f10  xor     r8d, r8d
0x140037f13  test    ax, ax
0x140037f16  jz      short loc_140037F4D
0x140037f18  lea     edx, [r8+1]
0x140037f1c  sub     ax, dx
0x140037f1f  movzx   ecx, ax
0x140037f22  mov     [r15+1EAh], cx
0x140037f2a  add     rcx, rdx
0x140037f2d  imul    rcx, 78h ; 'x'
0x140037f31  mov     rdx, [rcx+r15]
0x140037f35  mov     [rcx+r15], r8
0x140037f39  test    rdx, rdx
0x140037f3c  jz      short loc_140037F4D
0x140037f3e  mov     rax, [rdx]
0x140037f41  mov     rcx, rdx
0x140037f44  mov     rax, [rax+18h]
0x140037f48  call    _guard_dispatch_icall
0x140037f4d  test    ebx, ebx
0x140037f4f  jns     loc_140039E87
0x140037f55  cmp     ebx, 0C000003Ah
0x140037f5b  jz      loc_14003801D
0x140037f61  cmp     ebx, 0C0000034h
0x140037f67  jz      loc_14003801D
0x140037f6d  lea     rax, aPushQueryingSt; "PUSH: Querying stat information"
0x140037f74  mov     r8, 165000F0385h; struct UnionFs::StackEventTracer *
0x140037f7e  lea     r9, aUnionfsUnionfs_40; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x140037f85  mov     qword ptr [rsp+470h+DesiredAccess], rax; char *
0x140037f8a  mov     rdx, r15; int
0x140037f8d  mov     ecx, ebx; this
0x140037f8f  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140037f94  lea     rcx, [rbp+370h+var_118]; this
0x140037f9b  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140037fa0  mov     rcx, [rbp+370h+var_98]
0x140037fa7  xor     r15d, r15d
0x140037faa  test    rcx, rcx
0x140037fad  jz      short loc_140037FBB
0x140037faf  mov     rax, [rcx]
0x140037fb2  mov     rax, [rax+18h]
0x140037fb6  call    _guard_dispatch_icall
0x140037fbb  mov     rcx, [rbp+370h+var_128+8]; this
0x140037fc2  test    rcx, rcx
0x140037fc5  jz      short loc_140037FCC
0x140037fc7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140037fcc  test    rsi, rsi
0x140037fcf  jz      short loc_140037FF6
0x140037fd1  cmp     [rsi+10h], r15b
0x140037fd5  jnz     short loc_140037FDD
0x140037fd7  xorps   xmm0, xmm0
0x140037fda  movups  xmmword ptr [rsi], xmm0
0x140037fdd  mov     rcx, rsi; UnicodeString
0x140037fe0  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140037fe5  xor     edx, edx; Tag
0x140037fe7  mov     rcx, rsi; P
0x140037fea  call    cs:__imp_ExFreePoolWithTag
0x140037ff1  nop     dword ptr [rax+rax+00h]
0x140037ff6  test    rdi, rdi
0x140037ff9  jz      short loc_140038003
0x140037ffb  mov     rcx, rdi; this
0x140037ffe  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140038003  test    r14, r14
0x140038006  jz      short loc_140038010
0x140038008  mov     rcx, r14; this
0x14003800b  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140038010  mov     rcx, [rbp+370h+FileNameInformation]
0x140038014  mov     [rbp+370h+FileNameInformation], r15
0x140038018  jmp     loc_140037C8D
0x14003801d  mov     rcx, [rbp+370h+FileNameInformation]
0x140038021  lea     rdx, [rbp+370h+var_3B0]
0x140038025  xor     ebx, ebx
0x140038027  mov     r8, r15
0x14003802a  mov     [rbp+370h+var_3B0], rbx
0x14003802e  call    ?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_FLT_FILE_NAME_INFORMATION@@AEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInit(_FLT_FILE_NAME_INFORMATION const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140038033  mov     r12d, eax
0x140038036  test    eax, eax
0x140038038  jns     loc_140038131
0x14003803e  lea     rax, aPushAllocating_15; "PUSH: Allocating scratch name"
0x140038045  mov     r8, 684000F03ABh; struct UnionFs::StackEventTracer *
0x14003804f  lea     r9, aUnionfsUnionfs_40; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x140038056  mov     qword ptr [rsp+470h+DesiredAccess], rax; char *
0x14003805b  mov     rdx, r15; int
0x14003805e  mov     ecx, r12d; this
0x140038061  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140038066  mov     rbx, [rbp+370h+var_3B0]
0x14003806a  xor     r15d, r15d
  ... truncated ...
```
