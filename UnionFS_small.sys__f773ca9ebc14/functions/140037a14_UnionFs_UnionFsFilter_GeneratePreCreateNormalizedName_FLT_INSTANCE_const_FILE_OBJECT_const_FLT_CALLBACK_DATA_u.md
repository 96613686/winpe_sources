# UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName(_FLT_INSTANCE const &,_FILE_OBJECT const &,_FLT_CALLBACK_DATA &,ulong,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &)

- ea: `0x140037a14`
- end: `0x14003a05c`
- name: `?GeneratePreCreateNormalizedName@UnionFsFilter@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@KPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@@Z`
- size: `9800`
- prototype: `__int64 __fastcall(UnionFs::UnionFsFilter *__hidden this, const struct _FLT_INSTANCE *, const struct _FILE_OBJECT *, struct _FLT_CALLBACK_DATA *, unsigned int, struct _FLT_NAME_CONTROL *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140036488`

## callees

- `0x140005d5c`
- `0x140006340`
- `0x14000efd0`
- `0x14000f7fc`
- `0x140010b88`
- `0x140010fd0`
- `0x14001106c`
- `0x140011198`
- `0x14001124c`
- `0x140036128`
- `0x140036180`
- `0x140036428`
- `0x140037a14`
- `0x14003b4ec`
- `0x14003ce70`
- `0x14004397c`
- `0x140043ef4`
- `0x14004452c`
- `0x140044748`
- `0x140055d9c`
- `0x140056a14`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140061024`
- `0x14006e1a4`
- `0x14006efa8`
- `0x140075b30`
- `0x140076da4`
- `0x140077710`
- `0x140079c48`
- `0x140079df4`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!IoGetSilo` at `0x140037d7a`
- `ntoskrnl!IoGetSilo` at `0x1400385d9`
- `ntoskrnl!IoGetSilo` at `0x140037d7a`
- `ntoskrnl!IoGetSilo` at `0x1400385d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037c44`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037eaa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037f4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037faa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400380ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400381be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400381f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038256`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038352`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003838b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400383c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003848d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400384b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400384dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038516`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038547`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003892a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003894e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038ae2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038b56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038c1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038d72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038e85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038fca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039004`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039233`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003926d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400393ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400393e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400394a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400394b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039581`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400396e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039721`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039956`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039b3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039cb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039dfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039e84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039f6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039ff0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037c44`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037eaa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037f4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037faa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400380ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400381be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400381f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038256`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038352`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003838b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400383c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003848d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400384b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400384dd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038516`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038547`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003892a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003894e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038ae2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038b56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038c1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038d72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038e85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038fca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039004`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039233`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003926d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400393ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400393e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400394a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400394b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039581`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400396e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039721`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039956`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039b3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039cb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039dfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039e84`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039f6a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039ff0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140039c0a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140039c0a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140039c28`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140039c28`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140037d67`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x1400385f0`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140037d67`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x1400385f0`
- `ntoskrnl!PsGetHostSilo` at `0x14003877c`
- `ntoskrnl!PsGetHostSilo` at `0x140038efc`
- `ntoskrnl!PsGetHostSilo` at `0x14003877c`
- `ntoskrnl!PsGetHostSilo` at `0x140038efc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140039bf4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140039bf4`
- `ntoskrnl!ObfDereferenceObject` at `0x14003887d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400388c5`
- `ntoskrnl!ObfDereferenceObject` at `0x140038a7e`
- `ntoskrnl!ObfDereferenceObject` at `0x140038bbb`
- `ntoskrnl!ObfDereferenceObject` at `0x140038d37`
- `ntoskrnl!ObfDereferenceObject` at `0x140038dc3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400391a4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400391f3`
- `ntoskrnl!ObfDereferenceObject` at `0x14003936d`
- `ntoskrnl!ObfDereferenceObject` at `0x14003951d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400396ac`
- `ntoskrnl!ObfDereferenceObject` at `0x140039916`
- `ntoskrnl!ObfDereferenceObject` at `0x140039afd`
- `ntoskrnl!ObfDereferenceObject` at `0x140039c71`
- `ntoskrnl!ObfDereferenceObject` at `0x14003887d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400388c5`
- `ntoskrnl!ObfDereferenceObject` at `0x140038a7e`
- `ntoskrnl!ObfDereferenceObject` at `0x140038bbb`
- `ntoskrnl!ObfDereferenceObject` at `0x140038d37`
- `ntoskrnl!ObfDereferenceObject` at `0x140038dc3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400391a4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400391f3`
- `ntoskrnl!ObfDereferenceObject` at `0x14003936d`
- `ntoskrnl!ObfDereferenceObject` at `0x14003951d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400396ac`
- `ntoskrnl!ObfDereferenceObject` at `0x140039916`
- `ntoskrnl!ObfDereferenceObject` at `0x140039afd`
- `ntoskrnl!ObfDereferenceObject` at `0x140039c71`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140039a59`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x140039a59`
- `FLTMGR!FltQueryDirectoryFile` at `0x140038cbf`
- `FLTMGR!FltQueryDirectoryFile` at `0x140039634`
- `FLTMGR!FltQueryDirectoryFile` at `0x140038cbf`
- `FLTMGR!FltQueryDirectoryFile` at `0x140039634`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400389f6`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400392de`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400389f6`
- `FLTMGR!FltGetFileNameInformationUnsafe` at `0x1400392de`
- `FLTMGR!FltGetVolumeName` at `0x14003870f`
- `FLTMGR!FltGetVolumeName` at `0x14003906b`
- `FLTMGR!FltGetVolumeName` at `0x14003870f`
- `FLTMGR!FltGetVolumeName` at `0x14003906b`
- `FLTMGR!FltCreateFileEx2` at `0x140038856`
- `FLTMGR!FltCreateFileEx2` at `0x140039174`
- `FLTMGR!FltCreateFileEx2` at `0x140038856`
- `FLTMGR!FltCreateFileEx2` at `0x140039174`
- `FLTMGR!FltGetVolumeFromInstance` at `0x14003865d`
- `FLTMGR!FltGetVolumeFromInstance` at `0x140038f5d`
- `FLTMGR!FltGetVolumeFromInstance` at `0x14003865d`
- `FLTMGR!FltGetVolumeFromInstance` at `0x140038f5d`
- `FLTMGR!FltClose` at `0x1400388da`
- `FLTMGR!FltClose` at `0x140038a93`
- `FLTMGR!FltClose` at `0x140038bd0`
- `FLTMGR!FltClose` at `0x140038d4c`
- `FLTMGR!FltClose` at `0x140038dd8`
- `FLTMGR!FltClose` at `0x140039208`
- `FLTMGR!FltClose` at `0x140039382`
- `FLTMGR!FltClose` at `0x140039532`
- `FLTMGR!FltClose` at `0x1400396c1`
- `FLTMGR!FltClose` at `0x14003992b`
- `FLTMGR!FltClose` at `0x140039b12`
- `FLTMGR!FltClose` at `0x140039c86`
- `FLTMGR!FltClose` at `0x1400388da`
- `FLTMGR!FltClose` at `0x140038a93`
- `FLTMGR!FltClose` at `0x140038bd0`
- `FLTMGR!FltClose` at `0x140038d4c`
- `FLTMGR!FltClose` at `0x140038dd8`
- `FLTMGR!FltClose` at `0x140039208`
- `FLTMGR!FltClose` at `0x140039382`
- `FLTMGR!FltClose` at `0x140039532`
- `FLTMGR!FltClose` at `0x1400396c1`
- `FLTMGR!FltClose` at `0x14003992b`
- `FLTMGR!FltClose` at `0x140039b12`
- `FLTMGR!FltClose` at `0x140039c86`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037b56`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037c6b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037fdd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140038289`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140038576`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400389b0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140038a1d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140038a65`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140038ba2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140038d1e`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140038daa`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039307`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039354`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039504`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400395e3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039693`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400398fd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039ae4`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039bbe`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140039c58`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003a023`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037b56`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037c6b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140037fdd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140038289`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140038576`

## string_xrefs

- `0x140038095`: `PUSH: Cache lookup`
- `0x140038891`: `API: Opening parent`
- `0x1400391be`: `API: Opening parent`
- `0x140037aa6`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140037b2f`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140037b8e`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140037c0c`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140037e3e`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140037f0f`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x1400380a6`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140038188`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x1400382ce`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140038319`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140038457`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x1400386bc`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x1400388a2`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140038a42`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140038b7c`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140038cfb`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140038e2f`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140038f91`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x1400391cf`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x14003932d`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x1400394de`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140039670`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x1400398c9`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140039a81`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140039ab4`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140039d95`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140039f01`: `UnionFs::UnionFsFilter::GeneratePreCreateNormalizedName`
- `0x140037b1e`: `PUSH: Getting OPENED name`
- `0x140037b7d`: `API: Parsing opened name info`
- `0x1400382bd`: `PUSH: Copying UfsPathName`
- `0x140038cea`: `API: Getting final component long name`
- `0x14003965f`: `API: Getting final component long name`
- `0x1400399f4`: `PUSH: Copying UfsPathName to unique_unicode_string`
- `0x140039aa3`: `PUSH: Rewriting path`
- `0x140039d2a`: `API: Appending final component`

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
      (struct UnionFs::StackEventTracer *)0x2B6000F031BLL,
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
      (struct UnionFs::StackEventTracer *)0x15E000F0333LL,
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
      (struct UnionFs::StackEventTracer *)0x670000F0338LL,
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
      (struct UnionFs::StackEventTracer *)0x15F000F0345LL,
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
        (struct UnionFs::StackEventTracer *)0x160000F0362LL,
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
      (struct UnionFs::StackEventTracer *)0x166000F0396LL,
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
  v191[0] = off_14007E740;
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
      (struct UnionFs::StackEventTracer *)0x165000F0384LL,
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
      (struct UnionFs::StackEventTracer *)0x684000F03AALL,
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
      (struct UnionFs::StackEventTracer *)0x14B000F03BFLL,
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
        (struct UnionFs::StackEventTracer *)0x14D000F03CFLL,
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
        (struct UnionFs::StackEventTracer *)0x67E000F03D8LL,
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
      (struct UnionFs::StackEventTracer *)0x307000F03E0LL,
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
      (struct UnionFs::StackEventTracer *)0x167000F03EDLL,
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
          (struct UnionFs::StackEventTracer *)0x168000F0412LL,
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
          (struct UnionFs::StackEventTracer *)0x16A000F0443LL,
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
          (struct UnionFs::StackEventTracer *)0x16B000F0452LL,
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
          (struct UnionFs::StackEventTracer *)0x1CD000F045ELL,
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
          (struct UnionFs::StackEventTracer *)0x16C000F046FLL,
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
        (struct UnionFs::StackEventTracer *)0x251000F0482LL,
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
      (struct UnionFs::StackEventTracer *)0x185000F049DLL,
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
      (struct UnionFs::StackEventTracer *)0x187000F04C5LL,
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
      (struct UnionFs::StackEventTracer *)0x188000F04D2LL,
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
        (struct UnionFs::StackEventTracer *)0x1CE000F04E4LL,
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
        (struct UnionFs::StackEventTracer *)0x189000F04F4LL,
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
        (struct UnionFs::StackEventTracer *)0x1B2000F052BLL,
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
        (struct UnionFs::StackEventTracer *)0x1B3000F0530LL,
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
      v121 = 0x16F000F0560LL;
    }
    else
    {
      v120 = "API: Growing OutputNameControl";
      v121 = 0x16E000F0557LL;
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
    (struct UnionFs::StackEventTracer *)0x16D000F0542LL,
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
0x140037a14  mov     [rsp-8+arg_0], rbx
0x140037a19  push    rbp
0x140037a1a  push    rsi
0x140037a1b  push    rdi
0x140037a1c  push    r12
0x140037a1e  push    r13
0x140037a20  push    r14
0x140037a22  push    r15
0x140037a24  lea     rbp, [rsp-340h]
0x140037a2c  sub     rsp, 440h
0x140037a33  mov     rax, cs:__security_cookie
0x140037a3a  xor     rax, rsp
0x140037a3d  mov     [rbp+370h+var_40], rax
0x140037a44  mov     rax, [rbp+370h+arg_28]
0x140037a4b  mov     rdi, r8
0x140037a4e  mov     r15, [rbp+370h+arg_30]
0x140037a55  mov     r10, rdx
0x140037a58  mov     rsi, r9
0x140037a5b  mov     [rbp+370h+var_378], r9
0x140037a5f  mov     [rbp+370h+FileObject], r8
0x140037a63  xor     r12d, r12d
0x140037a66  mov     [rbp+370h+var_2D0], rdx
0x140037a6d  lea     r8, [rbp+370h+FltObject]
0x140037a71  mov     r9, r15
0x140037a74  mov     [rbp+370h+NameCtrl], rax
0x140037a7b  mov     rdx, rdi
0x140037a7e  mov     [rbp+370h+FltObject], r12
0x140037a82  mov     rcx, r10
0x140037a85  mov     qword ptr [rsp+470h+DesiredAccess], r12
0x140037a8a  call    ?GetMappingTableForFileObject@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAPEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@PEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@@Z; UnionFs::Utils::GetMappingTableForFileObject(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsScratchMappingTable * *,UnionFs::StackEventTracer &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> *)
0x140037a8f  mov     ebx, eax
0x140037a91  test    eax, eax
0x140037a93  jns     short loc_140037AC3
0x140037a95  lea     rax, aPushGettingMap; "PUSH: Getting mapping table"
0x140037a9c  mov     r8, 2B6000F031Bh; struct UnionFs::StackEventTracer *
0x140037aa6  lea     r9, aUnionfsUnionfs_39; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x140037aad  mov     qword ptr [rsp+470h+DesiredAccess], rax; char *
0x140037ab2  mov     rdx, r15; int
0x140037ab5  mov     ecx, ebx; this
0x140037ab7  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140037abc  mov     eax, ebx
0x140037abe  jmp     loc_14003A031
0x140037ac3  mov     r14, [rbp+370h+FltObject]
0x140037ac7  test    r14, r14
0x140037aca  jnz     short loc_140037AD8
0x140037acc  lea     rcx, aShouldnTHaveBe; "Shouldn't have been called without a ma"...
0x140037ad3  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140037ad8  mov     [rbp+370h+FileNameInformation], r12
0x140037adc  lea     r8, [rbp+370h+FileNameInformation]
0x140037ae0  mov     r12d, [rbp+370h+arg_20]
0x140037ae7  lea     rcx, [rbp+370h+var_3A0]
0x140037aeb  and     r12d, 0FF00FF00h
0x140037af2  mov     [rbp+370h+var_3A0], rsi
0x140037af6  mov     edx, r12d
0x140037af9  mov     [rbp+370h+arg_20], r12d
0x140037b00  xor     esi, esi
0x140037b02  or      edx, 3000002h
0x140037b08  mov     r9, r15
0x140037b0b  mov     [rbp+370h+RetVolume], rsi
0x140037b0f  mov     [rbp+370h+var_390], rsi
0x140037b13  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x140037b18  mov     ebx, eax
0x140037b1a  test    eax, eax
0x140037b1c  jns     short loc_140037B67
0x140037b1e  lea     rax, aPushGettingOpe_1; "PUSH: Getting OPENED name"
0x140037b25  mov     r8, 15E000F0333h; struct UnionFs::StackEventTracer *
0x140037b2f  lea     r9, aUnionfsUnionfs_39; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x140037b36  mov     qword ptr [rsp+470h+DesiredAccess], rax; char *
0x140037b3b  mov     rdx, r15; int
0x140037b3e  mov     ecx, ebx; this
0x140037b40  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140037b45  mov     rcx, [rbp+370h+FileNameInformation]; FileNameInformation
0x140037b49  mov     [rbp+370h+FileNameInformation], rsi
0x140037b4d  test    rcx, rcx
0x140037b50  jz      loc_140037ABC
0x140037b56  call    cs:__imp_FltReleaseFileNameInformation
0x140037b5d  nop     dword ptr [rax+rax+00h]
0x140037b62  jmp     loc_140037ABC
0x140037b67  mov     rcx, [rbp+370h+FileNameInformation]; FileNameInformation
0x140037b6b  call    cs:__imp_FltParseFileNameInformation
0x140037b72  nop     dword ptr [rax+rax+00h]
0x140037b77  mov     ebx, eax
0x140037b79  test    eax, eax
0x140037b7b  jns     short loc_140037BA6
0x140037b7d  lea     rax, aApiParsingOpen; "API: Parsing opened name info"
0x140037b84  mov     r8, 670000F0338h; struct UnionFs::StackEventTracer *
0x140037b8e  lea     r9, aUnionfsUnionfs_39; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x140037b95  mov     qword ptr [rsp+470h+DesiredAccess], rax; char *
0x140037b9a  mov     rdx, r15; int
0x140037b9d  mov     ecx, ebx; this
0x140037b9f  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140037ba4  jmp     short loc_140037B45
0x140037ba6  mov     r13d, [rdi+50h]
0x140037baa  mov     eax, 1
0x140037baf  mov     r8, [rbp+370h+FileNameInformation]; struct _FLT_FILE_NAME_INFORMATION *
0x140037bb3  xorps   xmm0, xmm0
0x140037bb6  mov     rdx, [rbp+370h+var_2D0]; struct _FLT_INSTANCE *
0x140037bbd  mov     rcx, r14; this
0x140037bc0  shr     r13d, 11h
0x140037bc4  not     r13b
0x140037bc7  mov     [rbp+370h+var_340], rax
0x140037bcb  and     r13b, al
0x140037bce  mov     [rsp+470h+ObjectAttributes], r15; char *
0x140037bd3  lea     rax, [rbp+370h+var_340]
0x140037bd7  mov     dword ptr [rbp+370h+var_3B8], r13d
0x140037bdb  mov     r9b, r13b; bool
0x140037bde  mov     qword ptr [rsp+470h+DesiredAccess], rax; struct UnionFs::LookupScratchRootResults *
0x140037be3  movdqu  xmmword ptr [rbp+370h+var_338], xmm0
0x140037be8  mov     [rbp+370h+P], rsi
0x140037bec  call    ?LookupScratchRoot@UfsScratchMappingTable@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@_NAEAULookupScratchRootResults@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsScratchMappingTable::LookupScratchRoot(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,bool,UnionFs::LookupScratchRootResults &,UnionFs::StackEventTracer &)
0x140037bf1  mov     edi, eax
0x140037bf3  test    eax, eax
0x140037bf5  jns     loc_140037C7E
0x140037bfb  lea     rax, aPushLookingUpN_0; "PUSH: Looking up name in mapping table"
0x140037c02  mov     r8, 15F000F0345h; struct UnionFs::StackEventTracer *
0x140037c0c  lea     r9, aUnionfsUnionfs_39; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x140037c13  mov     qword ptr [rsp+470h+DesiredAccess], rax; char *
0x140037c18  mov     rdx, r15; int
0x140037c1b  mov     ecx, edi; this
0x140037c1d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140037c22  mov     rbx, [rbp+370h+P]
0x140037c26  test    rbx, rbx
0x140037c29  jz      short loc_140037C50
0x140037c2b  cmp     [rbx+10h], sil
0x140037c2f  jnz     short loc_140037C37
0x140037c31  xorps   xmm0, xmm0
0x140037c34  movups  xmmword ptr [rbx], xmm0
0x140037c37  mov     rcx, rbx; UnicodeString
0x140037c3a  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140037c3f  xor     edx, edx; Tag
0x140037c41  mov     rcx, rbx; P
0x140037c44  call    cs:__imp_ExFreePoolWithTag
0x140037c4b  nop     dword ptr [rax+rax+00h]
0x140037c50  mov     rcx, [rbp+370h+var_338+8]; this
0x140037c54  test    rcx, rcx
0x140037c57  jz      short loc_140037C5E
0x140037c59  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140037c5e  mov     rcx, [rbp+370h+FileNameInformation]; FileNameInformation
0x140037c62  mov     [rbp+370h+FileNameInformation], rsi
0x140037c66  test    rcx, rcx
0x140037c69  jz      short loc_140037C77
0x140037c6b  call    cs:__imp_FltReleaseFileNameInformation
0x140037c72  nop     dword ptr [rax+rax+00h]
0x140037c77  mov     eax, edi
0x140037c79  jmp     loc_14003A031
0x140037c7e  mov     r14, [rbp+370h+var_338+8]
0x140037c82  mov     rbx, [rbp+370h+var_338]
0x140037c86  mov     rdi, r14
0x140037c89  test    r14, r14
0x140037c8c  jz      short loc_140037C93
0x140037c8e  lock inc dword ptr [r14+8]
0x140037c93  mov     rsi, [rbp+370h+P]
0x140037c97  lea     rcx, [rbp+370h+var_118]; void *
0x140037c9e  xor     eax, eax
0x140037ca0  mov     [rbp+370h+var_380], rsi
0x140037ca4  xorps   xmm0, xmm0
0x140037ca7  mov     [rbp+370h+P], rax
0x140037cab  xor     edx, edx; Val
0x140037cad  mov     [rbp+370h+var_118], rax
0x140037cb4  mov     r8d, 88h; Size
0x140037cba  mov     [rbp+370h+var_110], al
0x140037cc0  movdqu  xmmword ptr [rbp+370h+var_128], xmm0
0x140037cc8  mov     [rbp+370h+var_98], rax
0x140037ccf  call    memset
0x140037cd4  test    rbx, rbx
0x140037cd7  jz      loc_140039EB7
0x140037cdd  mov     r8, r15; struct UnionFs::StackEventTracer *
0x140037ce0  lea     rdx, [rbp+370h+var_128]; struct UnionFs::UfsUnionCtxWithRundown *
0x140037ce7  mov     rcx, rbx; this
0x140037cea  call    ?TryGetOwningUnion@UfsLayerCtx@UnionFs@@QEBAJAEAUUfsUnionCtxWithRundown@2@AEAVStackEventTracer@2@@Z; UnionFs::UfsLayerCtx::TryGetOwningUnion(UnionFs::UfsUnionCtxWithRundown &,UnionFs::StackEventTracer &)
0x140037cef  cmp     [rbp+370h+var_128], 0
0x140037cf7  jnz     short loc_140037D1C
0x140037cf9  xor     r13d, r13d
0x140037cfc  mov     [r15], r13d
0x140037cff  mov     [r15+224h], r13w
0x140037d07  test    rdi, rdi
0x140037d0a  jz      short loc_140037D14
0x140037d0c  mov     rcx, rdi; this
0x140037d0f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140037d14  mov     rdi, r13
0x140037d17  jmp     loc_140039EBA
0x140037d1c  cmp     dword ptr [rbp+370h+var_340+4], 1
0x140037d20  jz      loc_140039D40
0x140037d26  lea     rax, off_14007E740
0x140037d2d  mov     rcx, r15
0x140037d30  mov     [rbp+370h+var_198], rax
0x140037d37  lea     rdx, [rbp+370h+var_1A0]
0x140037d3e  lea     rax, [rbp+370h+var_198]
0x140037d45  mov     [rbp+370h+var_130], rax
0x140037d4c  call    ?SetIgnoreStatusCallback@StackEventTracer@UnionFs@@QEAAXV?$function@$$A6A_NJ@Z@wistd@@@Z; UnionFs::StackEventTracer::SetIgnoreStatusCallback(wistd::function<bool (long)>)
0x140037d51  xor     edx, edx; Val
0x140037d53  lea     rcx, [rbp+370h+var_90]; void *
0x140037d5a  lea     r8d, [rdx+48h]; Size
0x140037d5e  call    memset
0x140037d63  mov     rcx, [rbp+370h+FileObject]; FileObject
0x140037d67  call    cs:__imp_IoGetTransactionParameterBlock
0x140037d6e  nop     dword ptr [rax+rax+00h]
0x140037d73  mov     rcx, [rbp+370h+FileObject]
0x140037d77  mov     rbx, rax
0x140037d7a  call    cs:__imp_IoGetSilo
0x140037d81  nop     dword ptr [rax+rax+00h]
0x140037d86  mov     rcx, [rbp+370h+FileNameInformation]
0x140037d8a  lea     rdx, [rbp+370h+var_90]
0x140037d91  mov     [rsp+470h+AllocationSize], 0
0x140037d9a  add     rcx, 8
0x140037d9e  movzx   r9d, r13b
0x140037da2  mov     r8, rax
0x140037da5  mov     r13, [rbp+370h+var_2D0]
0x140037dac  mov     [rsp+470h+IoStatusBlock], rbx
0x140037db1  mov     [rsp+470h+ObjectAttributes], r15; char *
0x140037db6  mov     qword ptr [rsp+470h+DesiredAccess], rdx
0x140037dbb  mov     rdx, r13
0x140037dbe  call    ?StatItem@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAVStackEventTracer@2@QEAU_TXN_PARAMETER_BLOCK@@PEAU_FLT_CALLBACK_DATA@@@Z; UnionFs::Utils::StatItem(_UNICODE_STRING const &,_FLT_INSTANCE const &,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,UnionFs::StackEventTracer &,_TXN_PARAMETER_BLOCK * const,_FLT_CALLBACK_DATA *)
0x140037dc3  mov     ebx, eax
0x140037dc5  mov     [rbp+370h+BufferSizeNeeded], eax
0x140037dc8  movzx   eax, word ptr [r15+1EAh]
0x140037dd0  xor     r8d, r8d
0x140037dd3  test    ax, ax
0x140037dd6  jz      short loc_140037E0D
0x140037dd8  lea     edx, [r8+1]
0x140037ddc  sub     ax, dx
0x140037ddf  movzx   ecx, ax
0x140037de2  mov     [r15+1EAh], cx
0x140037dea  add     rcx, rdx
0x140037ded  imul    rcx, 78h ; 'x'
0x140037df1  mov     rdx, [rcx+r15]
0x140037df5  mov     [rcx+r15], r8
0x140037df9  test    rdx, rdx
0x140037dfc  jz      short loc_140037E0D
0x140037dfe  mov     rax, [rdx]
0x140037e01  mov     rcx, rdx
0x140037e04  mov     rax, [rax+18h]
0x140037e08  call    _guard_dispatch_icall
0x140037e0d  test    ebx, ebx
0x140037e0f  jns     loc_140039D47
0x140037e15  cmp     ebx, 0C000003Ah
0x140037e1b  jz      loc_140037EDD
0x140037e21  cmp     ebx, 0C0000034h
0x140037e27  jz      loc_140037EDD
0x140037e2d  lea     rax, aPushQueryingSt; "PUSH: Querying stat information"
0x140037e34  mov     r8, 165000F0384h; struct UnionFs::StackEventTracer *
0x140037e3e  lea     r9, aUnionfsUnionfs_39; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x140037e45  mov     qword ptr [rsp+470h+DesiredAccess], rax; char *
0x140037e4a  mov     rdx, r15; int
0x140037e4d  mov     ecx, ebx; this
0x140037e4f  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140037e54  lea     rcx, [rbp+370h+var_118]; this
0x140037e5b  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140037e60  mov     rcx, [rbp+370h+var_98]
0x140037e67  xor     r15d, r15d
0x140037e6a  test    rcx, rcx
0x140037e6d  jz      short loc_140037E7B
0x140037e6f  mov     rax, [rcx]
0x140037e72  mov     rax, [rax+18h]
0x140037e76  call    _guard_dispatch_icall
0x140037e7b  mov     rcx, [rbp+370h+var_128+8]; this
0x140037e82  test    rcx, rcx
0x140037e85  jz      short loc_140037E8C
0x140037e87  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140037e8c  test    rsi, rsi
0x140037e8f  jz      short loc_140037EB6
0x140037e91  cmp     [rsi+10h], r15b
0x140037e95  jnz     short loc_140037E9D
0x140037e97  xorps   xmm0, xmm0
0x140037e9a  movups  xmmword ptr [rsi], xmm0
0x140037e9d  mov     rcx, rsi; UnicodeString
0x140037ea0  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140037ea5  xor     edx, edx; Tag
0x140037ea7  mov     rcx, rsi; P
0x140037eaa  call    cs:__imp_ExFreePoolWithTag
0x140037eb1  nop     dword ptr [rax+rax+00h]
0x140037eb6  test    rdi, rdi
0x140037eb9  jz      short loc_140037EC3
0x140037ebb  mov     rcx, rdi; this
0x140037ebe  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140037ec3  test    r14, r14
0x140037ec6  jz      short loc_140037ED0
0x140037ec8  mov     rcx, r14; this
0x140037ecb  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140037ed0  mov     rcx, [rbp+370h+FileNameInformation]
0x140037ed4  mov     [rbp+370h+FileNameInformation], r15
0x140037ed8  jmp     loc_140037B4D
0x140037edd  mov     rcx, [rbp+370h+FileNameInformation]
0x140037ee1  lea     rdx, [rbp+370h+var_3B0]
0x140037ee5  xor     ebx, ebx
0x140037ee7  mov     r8, r15
0x140037eea  mov     [rbp+370h+var_3B0], rbx
0x140037eee  call    ?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_FLT_FILE_NAME_INFORMATION@@AEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInit(_FLT_FILE_NAME_INFORMATION const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140037ef3  mov     r12d, eax
0x140037ef6  test    eax, eax
0x140037ef8  jns     loc_140037FF1
0x140037efe  lea     rax, aPushAllocating_15; "PUSH: Allocating scratch name"
0x140037f05  mov     r8, 684000F03AAh; struct UnionFs::StackEventTracer *
0x140037f0f  lea     r9, aUnionfsUnionfs_39; "UnionFs::UnionFsFilter::GeneratePreCrea"...
0x140037f16  mov     qword ptr [rsp+470h+DesiredAccess], rax; char *
0x140037f1b  mov     rdx, r15; int
0x140037f1e  mov     ecx, r12d; this
0x140037f21  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140037f26  mov     rbx, [rbp+370h+var_3B0]
0x140037f2a  xor     r15d, r15d
  ... truncated ...
```
