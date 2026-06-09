# UnionFs::UnionFsFilter::PreCreate(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)

- ea: `0x140011e20`
- end: `0x1400136b1`
- name: `?PreCreate@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z`
- size: `6289`
- prototype: `enum _FLT_PREOP_CALLBACK_STATUS __fastcall(struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void **)`
- caller_count: `1`
- callee_count: `43`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400749f0`

## callees

- `0x140002044`
- `0x140005574`
- `0x1400056b4`
- `0x140006168`
- `0x140006340`
- `0x140006d38`
- `0x14000f81c`
- `0x140010c28`
- `0x1400110c8`
- `0x14001126c`
- `0x1400119c4`
- `0x140011e20`
- `0x1400136b8`
- `0x140013b60`
- `0x14001568c`
- `0x1400173f0`
- `0x1400183cc`
- `0x1400194b8`
- `0x14001a18c`
- `0x140023e3c`
- `0x140024134`
- `0x140027218`
- `0x140027764`
- `0x1400279dc`
- `0x1400362c0`
- `0x140055f1c`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140061918`
- `0x1400644f0`
- `0x14006e394`
- `0x14006f198`
- `0x14006faa8`
- `0x1400790f0`
- `0x140079d44`
- `0x140079f68`
- `0x14007a0c0`
- `0x14007a114`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bbd0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140012681`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001281c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012949`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012a63`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012c69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012cda`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012e9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400130f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400131c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400132d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013443`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013516`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013611`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012681`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001281c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012949`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012a63`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012c69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012cda`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012e9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400130f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400131c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400132d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013443`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013516`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013611`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14001287a`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14001321d`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140013329`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14001349b`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14001356e`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140013669`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14001287a`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14001321d`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140013329`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14001349b`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14001356e`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140013669`
- `ntoskrnl!IoReplaceFileObjectName` at `0x1400124c2`
- `ntoskrnl!IoReplaceFileObjectName` at `0x140012dff`
- `ntoskrnl!IoReplaceFileObjectName` at `0x1400124c2`
- `ntoskrnl!IoReplaceFileObjectName` at `0x140012dff`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140012d72`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140012e66`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400130c0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001318e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001329a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140012d72`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140012e66`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400130c0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001318e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001329a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140012bc7`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140012bc7`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x14001223d`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x14001223d`
- `FLTMGR!FltGetVolumeFromInstance` at `0x140012301`
- `FLTMGR!FltGetVolumeFromInstance` at `0x140012301`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400125ab`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140012855`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400131fa`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140013306`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140013478`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001354b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140013646`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400125ab`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140012855`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400131fa`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140013306`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140013478`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001354b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140013646`
- `FLTMGR!FltReleaseContext` at `0x140012023`
- `FLTMGR!FltReleaseContext` at `0x140012106`
- `FLTMGR!FltReleaseContext` at `0x1400121f9`
- `FLTMGR!FltReleaseContext` at `0x1400123fe`
- `FLTMGR!FltReleaseContext` at `0x140012491`
- `FLTMGR!FltReleaseContext` at `0x140012529`
- `FLTMGR!FltReleaseContext` at `0x140012a06`
- `FLTMGR!FltReleaseContext` at `0x140012dd5`
- `FLTMGR!FltReleaseContext` at `0x1400133e6`
- `FLTMGR!FltReleaseContext` at `0x1400134b9`
- `FLTMGR!FltReleaseContext` at `0x1400135b4`
- `FLTMGR!FltReleaseContext` at `0x140012023`
- `FLTMGR!FltReleaseContext` at `0x140012106`
- `FLTMGR!FltReleaseContext` at `0x1400121f9`
- `FLTMGR!FltReleaseContext` at `0x1400123fe`
- `FLTMGR!FltReleaseContext` at `0x140012491`
- `FLTMGR!FltReleaseContext` at `0x140012529`
- `FLTMGR!FltReleaseContext` at `0x140012a06`
- `FLTMGR!FltReleaseContext` at `0x140012dd5`
- `FLTMGR!FltReleaseContext` at `0x1400133e6`
- `FLTMGR!FltReleaseContext` at `0x1400134b9`
- `FLTMGR!FltReleaseContext` at `0x1400135b4`
- `FLTMGR!FltObjectDereference` at `0x140012261`
- `FLTMGR!FltObjectDereference` at `0x140012333`
- `FLTMGR!FltObjectDereference` at `0x1400123d4`
- `FLTMGR!FltObjectDereference` at `0x1400123ea`
- `FLTMGR!FltObjectDereference` at `0x140012434`
- `FLTMGR!FltObjectDereference` at `0x14001244a`
- `FLTMGR!FltObjectDereference` at `0x140012261`
- `FLTMGR!FltObjectDereference` at `0x140012333`
- `FLTMGR!FltObjectDereference` at `0x1400123d4`
- `FLTMGR!FltObjectDereference` at `0x1400123ea`
- `FLTMGR!FltObjectDereference` at `0x140012434`
- `FLTMGR!FltObjectDereference` at `0x14001244a`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140012513`
- `FLTMGR!FltSetCallbackDataDirty` at `0x140012513`

## string_xrefs

- `0x140011ee7`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140011f77`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140011ff0`: `UnionFs::UnionFsFilter::PreCreate`
- `0x1400120a2`: `UnionFs::UnionFsFilter::PreCreate`
- `0x14001228d`: `UnionFs::UnionFsFilter::PreCreate`
- `0x14001235d`: `UnionFs::UnionFsFilter::PreCreate`
- `0x1400123a3`: `UnionFs::UnionFsFilter::PreCreate`
- `0x1400124e5`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140012577`: `UnionFs::UnionFsFilter::PreCreate`
- `0x14001263e`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140012727`: `UnionFs::UnionFsFilter::PreCreate`
- `0x1400128d2`: `UnionFs::UnionFsFilter::PreCreate`
- `0x1400129da`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140012adc`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140012c19`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140012d34`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140012e27`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140012ed2`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140013162`: `UnionFs::UnionFsFilter::PreCreate`
- `0x1400133bb`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140011f64`: `ORIGIN: Open by file ID and delete on close flag both set`
- `0x140012092`: `onecore\base\fs\unionfs\sys\create.cpp`
- `0x1400124d4`: `API: IoReplaceFileObjectName`
- `0x140012e16`: `API: IoReplaceFileObjectName`
- `0x140012566`: `PUSH: Getting pre-create name`
- `0x1400128c1`: `PUSH: Getting relative path`
- `0x14001334f`: `lookupResult == MAPPING_LOOKUP_RESULT::MoreComponentsLeft`
- `0x1400133a5`: `PUSH: Query open processing`
- `0x140013598`: `IRP_MJ_NETWORK_QUERY_OPEN should have succeeded`
- `0x140012c04`: `ORIGIN: Allocating create context`
- `0x140012d1f`: `ORIGIN: Unexpected create operation type`
- `0x140012f1c`: `ORIGIN: Unexpected create disposition`
- `0x140013074`: `PUSH: Pre-create processing`
- `0x140013151`: `PUSH: Munging TagData for STATUS_REPARSE`
- `0x140013253`: `(callbackStatus == FLT_PREOP_SUCCESS_NO_CALLBACK) || (callbackStatus == FLT_PREOP_COMPLETE) || (callbackStatus == FLT_PREOP_PENDING)`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PreCreate(
        struct _FLT_CALLBACK_DATA *a1,
        const struct _FLT_RELATED_OBJECTS *a2,
        void **a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  PFILE_OBJECT FileObject; // rdx
  PFLT_INSTANCE Instance; // rcx
  NTSTATUS MappingTableForFileObject; // ebx
  struct UnionFs::UfsSiloCtx *v10; // rcx
  int v11; // r12d
  PFLT_IO_PARAMETER_BLOCK v12; // rax
  ULONG Options; // edx
  PFILE_OBJECT v14; // rax
  struct _FILE_OBJECT *RelatedFileObject; // rdi
  struct _FLT_INSTANCE *v16; // rcx
  NTSTATUS v17; // ebx
  int v18; // r9d
  PFLT_CONTEXT v19; // rcx
  PFILE_OBJECT v20; // rdx
  int Length; // r8d
  _BYTE *Buffer; // rcx
  PFLT_CONTEXT v23; // rbx
  __int128 *v24; // rax
  _QWORD *v25; // rdx
  utl::_RefCountBase *v26; // r14
  __int128 v27; // xmm0
  struct _FLT_FILTER *v28; // rcx
  int VolumeFromFileObject; // edi
  _QWORD *v30; // r14
  __int64 v31; // r15
  unsigned __int64 *v32; // rdx
  __int64 *v33; // rax
  volatile signed __int32 *v34; // rdi
  __int64 v35; // r15
  int VolumeFromInstance; // r15d
  _QWORD *v37; // rdi
  __int64 v38; // r14
  PFLT_CONTEXT v39; // rcx
  void *v40; // rcx
  struct UnionFs::UfsSiloCtx *v41; // rcx
  NTSTATUS NameFromFileID; // eax
  int v43; // edi
  NTSTATUS v44; // ebx
  struct _FLT_FILE_NAME_INFORMATION *v45; // rcx
  PFLT_FILE_NAME_INFORMATION v46; // r8
  struct _FLT_FILE_NAME_INFORMATION *v47; // rcx
  PFILE_OBJECT v48; // rax
  const struct _FLT_INSTANCE *v49; // rdx
  ULONG v50; // r9d
  struct _UNICODE_STRING *v51; // rdx
  NTSTATUS v52; // ebx
  struct _UNICODE_STRING *v53; // rdx
  __int64 v54; // rbx
  utl::_RefCountBase *v55; // rdi
  UnionFs::UfsLayerCtx *v56; // r14
  __int64 v57; // rbx
  int OwningUnion; // eax
  struct FsFltWil::Details::RundownRefCacheAware *v59; // rdx
  GUID *v60; // rax
  GUID v61; // xmm0
  __int128 v62; // xmm0
  UCHAR MajorFunction; // cl
  unsigned int v64; // ebx
  NTSTATUS RemainingPath; // r12d
  struct _UNICODE_STRING *v66; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v67; // rdx
  struct _UNICODE_STRING *v68; // rdx
  PFLT_IO_PARAMETER_BLOCK v69; // rax
  NTSTATUS v70; // r15d
  struct _UNICODE_STRING *v71; // rdx
  void *v72; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v73; // rdx
  struct _UNICODE_STRING *v74; // rdx
  PFLT_IO_PARAMETER_BLOCK v75; // rax
  UCHAR v76; // cl
  utl::_RefCountBase *v77; // r14
  utl::_RefCountBase *v78; // rcx
  __int64 v79; // rdx
  PVOID v80; // rax
  __int64 v81; // r15
  struct _UNICODE_STRING *v82; // rdx
  unsigned int *v83; // r8
  struct _UNICODE_STRING *v84; // rdx
  struct _UNICODE_STRING *v85; // rdx
  bool v86; // zf
  _QWORD *v87; // rax
  struct _UNICODE_STRING *v88; // rdx
  __int64 v89; // rcx
  struct _FILE_OBJECT *v90; // r8
  _WORD *FsContext; // rax
  char v92; // r14
  int v93; // r12d
  struct _UNICODE_STRING *v94; // rdx
  struct _UNICODE_STRING *v95; // rdx
  struct UnionFs::UfsSiloCtx *v96; // r12
  NTSTATUS v97; // r13d
  int v98; // eax
  struct _UNICODE_STRING *v99; // rdx
  UnionFs::UnionFsFilter *v100; // rcx
  struct UnionFs::StackEventTracer *v101; // r9
  const char *v102; // rax
  __int64 v103; // r8
  struct _UNICODE_STRING *v104; // rdx
  struct _UNICODE_STRING *v105; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v106; // rcx
  struct _UNICODE_STRING *v107; // rdx
  struct _UNICODE_STRING *v108; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v109; // rcx
  enum _FLT_PREOP_CALLBACK_STATUS v110; // r14d
  struct _UNICODE_STRING *v111; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v112; // rcx
  void *v113; // r15
  int Open; // eax
  struct _UNICODE_STRING *v115; // rdx
  struct _UNICODE_STRING *v116; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v117; // rdx
  struct _UNICODE_STRING *v118; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v119; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v120; // rdx
  struct _UNICODE_STRING *v121; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v122; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v123; // rdx
  struct _UNICODE_STRING *v124; // rdx
  struct UnionFs::StackEventTracer *v125; // [rsp+28h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v126; // [rsp+28h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v127; // [rsp+28h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v128; // [rsp+28h] [rbp-D8h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct UnionFs::UfsSiloCtx *v130; // [rsp+58h] [rbp-A8h] BYREF
  enum _FLT_PREOP_CALLBACK_STATUS v131; // [rsp+60h] [rbp-A0h] BYREF
  utl::_RefCountBase *v132[2]; // [rsp+68h] [rbp-98h] BYREF
  PFLT_CONTEXT Context; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v134[96]; // [rsp+80h] [rbp-80h] BYREF
  char v135; // [rsp+E0h] [rbp-20h]
  char *v136; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v137[2]; // [rsp+F8h] [rbp-8h] BYREF
  utl::_RefCountBase *v138[2]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v139[17]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v140[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v141; // [rsp+1D0h] [rbp+D0h]
  _BYTE v142[120]; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v143; // [rsp+250h] [rbp+150h]
  __int128 v144; // [rsp+258h] [rbp+158h]
  __int16 v145; // [rsp+268h] [rbp+168h]
  char v146; // [rsp+26Ah] [rbp+16Ah]
  __int64 v147; // [rsp+270h] [rbp+170h]
  char v148; // [rsp+278h] [rbp+178h]
  char v149[4]; // [rsp+280h] [rbp+180h] BYREF
  int v150; // [rsp+530h] [rbp+430h]
  __int128 v151; // [rsp+534h] [rbp+434h]
  GUID v152; // [rsp+544h] [rbp+444h]
  char v153; // [rsp+554h] [rbp+454h]
  __int128 v154; // [rsp+558h] [rbp+458h]
  char v155; // [rsp+568h] [rbp+468h]

  v136 = (char *)a3;
  *a3 = 0;
  Iopb = a1->Iopb;
  if ( !Iopb->MajorFunction && ((Iopb->TargetFileObject->Flags & 0x400000) != 0 || (Iopb->OperationFlags & 2) != 0) )
    return 1;
  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v149, 0xCF0002002CuLL, a1);
  FileObject = a2->FileObject;
  Instance = a2->Instance;
  v130 = 0;
  *(_QWORD *)&v134[8] = 0;
  MappingTableForFileObject = UnionFs::Utils::GetMappingTableForFileObject(Instance, FileObject, &v134[8], v149, &v130);
  if ( MappingTableForFileObject < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)MappingTableForFileObject,
      (int)v149,
      (struct UnionFs::StackEventTracer *)0x2AE0002003FLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
      "PUSH: Getting FILE_OBJECT silo",
      (const char *)v125);
    a1->IoStatus.Status = MappingTableForFileObject;
    a1->IoStatus.Information = 0;
    goto LABEL_7;
  }
  v11 = 1;
  if ( !*(_QWORD *)&v134[8] )
    goto LABEL_145;
  v12 = a1->Iopb;
  *(_OWORD *)v132 = 0;
  Options = v12->Parameters.Create.Options;
  v134[0] = (Options & 0x2000) != 0;
  if ( !v12->MajorFunction && (Options & 0x2000) != 0 )
  {
    if ( (Options & 0x1000) != 0 )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000000DLL,
        (int)v149,
        (struct UnionFs::StackEventTracer *)0x5E10002005CLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
        "ORIGIN: Open by file ID and delete on close flag both set",
        (const char *)v125);
      a1->IoStatus.Status = -1073741811;
      a1->IoStatus.Information = 0;
      goto LABEL_7;
    }
    v14 = a2->FileObject;
    RelatedFileObject = v14->RelatedFileObject;
    if ( RelatedFileObject )
      v14->RelatedFileObject = 0;
    v16 = a2->Instance;
    Context = 0;
    v17 = UnionFs::UfsInstanceCtx::FltGet(v16);
    if ( v17 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v17,
        (int)v149,
        (struct UnionFs::StackEventTracer *)0x38A00020071LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
        "PUSH: Getting instance context",
        (const char *)v125);
      v19 = Context;
      a1->IoStatus.Status = v17;
      a1->IoStatus.Information = 0;
      if ( v19 )
        FltReleaseContext(v19);
      goto LABEL_7;
    }
    v20 = a2->FileObject;
    Length = v20->FileName.Length;
    if ( (((_WORD)Length - 8) & 0xFFFD) != 0 )
    {
      if ( (((_WORD)Length - 16) & 0xFFFD) != 0 )
      {
        if ( (unsigned int)dword_14009E178 > 4
          && (qword_14009E188 & 0x200) != 0
          && (qword_14009E190 & 0x200) == qword_14009E190 )
        {
          *(_WORD *)v134 = v20->FileName.Length;
          v136 = "onecore\\base\\fs\\unionfs\\sys\\create.cpp";
          *(_DWORD *)&v134[8] = 176;
          *(_QWORD *)&v134[80] = "Not supported file ID size.";
          *(_QWORD *)&v134[64] = "UnionFs::UnionFsFilter::PreCreate";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(
            qword_14009E190,
            (unsigned int)&dword_14009619C,
            Length,
            v18,
            (__int64)&v134[80],
            (__int64)&v134[64],
            (__int64)&v136,
            (__int64)&v134[8],
            (__int64)v134);
        }
LABEL_25:
        if ( Context )
          FltReleaseContext(Context);
LABEL_145:
        if ( v130 )
          PsDereferenceSiloContext(v130);
        v64 = v11;
        goto LABEL_306;
      }
      Buffer = v20->FileName.Buffer;
      if ( (_WORD)Length != 16 )
        Buffer += 2;
      if ( *Buffer == 0xFF
        && Buffer[1] == 0xFF
        && Buffer[2] == 0xFF
        && Buffer[3] == 0xFF
        && Buffer[4] == 0xFF
        && Buffer[5] == 0xFF
        && Buffer[6] == 0xFF
        && Buffer[7] == 0xFF
        && Buffer[8] == 0xFF
        && Buffer[9] == 0xFF
        && Buffer[10] == 0xFF
        && Buffer[11] == 0xFF
        && Buffer[12] == 0xFF
        && Buffer[13] == 0xFF
        && Buffer[14] == 0xFF
        && Buffer[15] == 0xFF )
      {
        goto LABEL_25;
      }
      v23 = Context;
      *(_OWORD *)&v134[80] = *(_OWORD *)Buffer;
      v24 = (__int128 *)UnionFs::UfsFileID::UfsFileID(&v134[16], &v134[80], Context, v132);
    }
    else
    {
      v25 = v20->FileName.Buffer;
      if ( (_WORD)Length != 8 )
        v25 = (_QWORD *)((char *)v25 + 2);
      if ( *v25 == -1 )
        goto LABEL_25;
      v23 = Context;
      v24 = (__int128 *)UnionFs::UfsFileID::UfsFileID((UnionFs::UfsFileID *)&v134[16]);
    }
    v26 = v132[0];
    v27 = *v24;
    v137[1] = v24[1];
    v137[0] = v27;
    if ( !v132[0] )
    {
      if ( v23 )
        FltReleaseContext(v23);
      goto LABEL_143;
    }
    if ( RelatedFileObject )
    {
      *(_QWORD *)&v134[80] = &Context;
      Context = 0;
      *(_QWORD *)&v134[88] = 0;
      v28 = *(struct _FLT_FILTER **)UnionFs::g_FilterState;
      v135 = 1;
      VolumeFromFileObject = FltGetVolumeFromFileObject(v28, RelatedFileObject, (PFLT_VOLUME *)&v134[88]);
      if ( v135 )
      {
        v30 = *(_QWORD **)&v134[80];
        v31 = *(_QWORD *)&v134[88];
        if ( **(_QWORD **)&v134[80] )
          FltObjectDereference(**(PVOID **)&v134[80]);
        *v30 = v31;
        v26 = v132[0];
      }
      if ( VolumeFromFileObject < 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)VolumeFromFileObject,
          (int)v149,
          (struct UnionFs::StackEventTracer *)0x5FB000200C8LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
          "API: FltGetVolumeFromFileObject",
          (const char *)v125);
        a1->IoStatus.Status = VolumeFromFileObject;
        a1->IoStatus.Information = 0;
        goto LABEL_76;
      }
      *(_QWORD *)&v134[64] = 0;
      *(_QWORD *)&v134[16] = &v134[64];
      *(_QWORD *)&v134[24] = 0;
      v134[32] = 1;
      FsFltWil::AcquirePushLockShared(&v134[80], (char *)v26 + 72);
      v33 = (__int64 *)*((_QWORD *)v26 + 6);
      v34 = (volatile signed __int32 *)v33[1];
      v35 = *v33;
      if ( v34 )
        _InterlockedIncrement(v34 + 2);
      if ( *(_QWORD *)&v134[80] )
        FsFltWil::Details::ReleasePushLockShared(*(FsFltWil::Details **)&v134[80], v32);
      VolumeFromInstance = FltGetVolumeFromInstance(**(PFLT_INSTANCE **)(v35 + 8), (PFLT_VOLUME *)&v134[24]);
      if ( v34 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v34);
      if ( v134[32] )
      {
        v37 = *(_QWORD **)&v134[16];
        v38 = *(_QWORD *)&v134[24];
        if ( **(_QWORD **)&v134[16] )
          FltObjectDereference(**(PVOID **)&v134[16]);
        *v37 = v38;
        v26 = v132[0];
      }
      if ( VolumeFromInstance < 0 )
      {
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)VolumeFromInstance,
          (int)v149,
          (struct UnionFs::StackEventTracer *)0x38C000200D4LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
          "API: FltGetVolumeFromInstance",
          (const char *)v125);
        a1->IoStatus.Status = VolumeFromInstance;
        goto LABEL_74;
      }
      v39 = Context;
      if ( Context != *(PFLT_CONTEXT *)&v134[64] )
      {
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC000000DLL,
          (int)v149,
          (struct UnionFs::StackEventTracer *)0x5FC000200DCLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
          "ORIGIN: FltGetVolumeFromInstance",
          (const char *)v125);
        a1->IoStatus.Status = -1073741811;
LABEL_74:
        v40 = *(void **)&v134[64];
        a1->IoStatus.Information = 0;
        if ( v40 )
          FltObjectDereference(v40);
LABEL_76:
        if ( Context )
          FltObjectDereference(Context);
        if ( v23 )
          FltReleaseContext(v23);
        if ( v132[1] )
          utl::_RefCountBase::_DecStrong(v132[1]);
        v41 = v130;
        if ( !v130 )
          goto LABEL_247;
        goto LABEL_246;
      }
      if ( *(_QWORD *)&v134[64] )
      {
        FltObjectDereference(*(PVOID *)&v134[64]);
        v39 = Context;
      }
      if ( v39 )
        FltObjectDereference(v39);
    }
    *(_OWORD *)&v134[80] = 0;
    NameFromFileID = UnionFs::UfsUnionCtx::GetNameFromFileID(
                       v26,
                       (const struct UnionFs::UfsFileID *)v137,
                       (struct _UNICODE_STRING *)&v134[80],
                       (struct UnionFs::StackEventTracer *)v149);
    if ( NameFromFileID < 0 )
    {
      a1->IoStatus.Status = NameFromFileID;
      goto LABEL_90;
    }
    v43 = IoReplaceFileObjectName(a2->FileObject, *(PWSTR *)&v134[88], *(USHORT *)&v134[80]);
    if ( v43 < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)v43,
        (int)v149,
        (struct UnionFs::StackEventTracer *)0x5DE000200F4LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
        "API: IoReplaceFileObjectName",
        (const char *)v125);
      a1->IoStatus.Status = v43;
LABEL_90:
      a1->IoStatus.Information = 0;
      if ( v23 )
        FltReleaseContext(v23);
LABEL_92:
      if ( v132[1] )
        utl::_RefCountBase::_DecStrong(v132[1]);
LABEL_7:
      v10 = v130;
      if ( !v130 )
      {
LABEL_327:
        UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v149);
        return 4;
      }
LABEL_326:
      PsDereferenceSiloContext(v10);
      goto LABEL_327;
    }
    a1->Iopb->Parameters.Create.Options &= ~0x2000u;
    FltSetCallbackDataDirty(a1);
    if ( v23 )
      FltReleaseContext(v23);
  }
  FileNameInformation = 0;
  *(_QWORD *)&v134[16] = a1;
  *(_OWORD *)&v134[24] = 0u;
  v44 = UnionFs::Utils::GetFileNameInformation(&v134[16], 16777474, &FileNameInformation, v149);
  if ( v44 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v44,
      (int)v149,
      (struct UnionFs::StackEventTracer *)0xD000020111LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
      "PUSH: Getting pre-create name",
      (const char *)v125);
    a1->IoStatus.Status = v44;
    a1->IoStatus.Information = 0;
LABEL_100:
    v45 = FileNameInformation;
    FileNameInformation = 0;
    goto LABEL_101;
  }
  v46 = FileNameInformation;
  if ( FileNameInformation->Name.Length == FileNameInformation->Volume.Length )
  {
    FileNameInformation = 0;
    if ( !v46 )
      goto LABEL_143;
    v47 = v46;
LABEL_142:
    FltReleaseFileNameInformation(v47);
LABEL_143:
    if ( v132[1] )
      utl::_RefCountBase::_DecStrong(v132[1]);
    goto LABEL_145;
  }
  v48 = a2->FileObject;
  v49 = a2->Instance;
  *(_QWORD *)&v134[16] = 1;
  v50 = v48->Flags >> 17;
  memset(&v134[24], 0, 24);
  v52 = UnionFs::UfsScratchMappingTable::LookupScratchRoot(
          *(UnionFs::UfsScratchMappingTable **)&v134[8],
          v49,
          FileNameInformation,
          (v50 & 1) == 0,
          (struct UnionFs::LookupScratchRootResults *)&v134[16],
          (struct UnionFs::StackEventTracer *)v149);
  if ( v52 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v52,
      (int)v149,
      (struct UnionFs::StackEventTracer *)0xD100020127LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
      "PUSH: Looking up name",
      (const char *)v126);
    a1->IoStatus.Status = v52;
    v54 = *(_QWORD *)&v134[40];
    a1->IoStatus.Information = 0;
    if ( v54 )
    {
      if ( !*(_BYTE *)(v54 + 16) )
        *(_OWORD *)v54 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v54, v53);
      ExFreePoolWithTag((PVOID)v54, 0);
    }
    if ( *(_QWORD *)&v134[32] )
      utl::_RefCountBase::_DecStrong(*(utl::_RefCountBase **)&v134[32]);
    goto LABEL_100;
  }
  v55 = *(utl::_RefCountBase **)&v134[32];
  v56 = *(UnionFs::UfsLayerCtx **)&v134[24];
  if ( *(_QWORD *)&v134[32] )
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&v134[32] + 8LL));
  v57 = *(_QWORD *)&v134[40];
  *(_QWORD *)&v134[40] = 0;
  if ( !v56 )
    goto LABEL_134;
  *(_OWORD *)v138 = 0;
  memset(v139, 0, sizeof(v139));
  OwningUnion = UnionFs::UfsLayerCtx::TryGetOwningUnion(
                  v56,
                  (struct UnionFs::UfsUnionCtxWithRundown *)v138,
                  (struct UnionFs::StackEventTracer *)v149);
  if ( OwningUnion < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)OwningUnion,
      (int)v149,
      (struct UnionFs::StackEventTracer *)0x4210002013BLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
      "PUSH: Union no longer available",
      (const char *)v126);
LABEL_130:
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v139, v59);
    if ( v139[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v139[16] + 24LL))(v139[16]);
    if ( v138[1] )
      utl::_RefCountBase::_DecStrong(v138[1]);
LABEL_134:
    if ( v57 )
    {
      if ( !*(_BYTE *)(v57 + 16) )
        *(_OWORD *)v57 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v57, v51);
      ExFreePoolWithTag((PVOID)v57, 0);
    }
    if ( v55 )
    {
      utl::_RefCountBase::_DecStrong(v55);
      utl::_RefCountBase::_DecStrong(v55);
    }
    v47 = FileNameInformation;
    FileNameInformation = 0;
    goto LABEL_141;
  }
  if ( v138[0] && !v153 )
  {
    v150 = *((_DWORD *)v138[0] + 7);
    v151 = *(_OWORD *)((char *)v138[0] + 8);
    if ( *((_DWORD *)v138[0] + 7) == 2 && (v60 = (GUID *)*((_QWORD *)v138[0] + 4)) != 0 )
      v61 = v60[2];
    else
      v61 = GUID_NULL;
    v152 = v61;
    v153 = 1;
  }
  if ( !v155 )
  {
    v62 = *((_OWORD *)v56 + 3);
    v155 = 1;
    v154 = v62;
  }
  MajorFunction = a1->Iopb->MajorFunction;
  if ( (MajorFunction == 0xF2 || MajorFunction == 0xF9) && *(_DWORD *)&v134[20] == 1 )
    goto LABEL_130;
  *(_OWORD *)&v134[48] = 0;
  *(_OWORD *)&v134[80] = *(_OWORD *)v57;
  RemainingPath = UnionFs::Utils::GetRemainingPath(FileNameInformation, &v134[80], &v134[48], v149);
  if ( RemainingPath < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)RemainingPath,
      (int)v149,
      (struct UnionFs::StackEventTracer *)0x1C40002015CLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
      "PUSH: Getting relative path",
      (const char *)v126);
    a1->IoStatus.Status = RemainingPath;
    a1->IoStatus.Information = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v134[48], v66);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v139, v67);
    if ( v139[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v139[16] + 24LL))(v139[16]);
    if ( v138[1] )
      utl::_RefCountBase::_DecStrong(v138[1]);
    if ( !*(_BYTE *)(v57 + 16) )
      *(_OWORD *)v57 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v57, v68);
    ExFreePoolWithTag((PVOID)v57, 0);
    if ( v55 )
    {
      utl::_RefCountBase::_DecStrong(v55);
      utl::_RefCountBase::_DecStrong(v55);
    }
LABEL_157:
    v45 = FileNameInformation;
    FileNameInformation = 0;
    goto LABEL_101;
  }
  v69 = a1->Iopb;
  v11 = 0;
  *(_QWORD *)&v134[8] = 0;
  v70 = UnionFs::UfsStreamHandleCtx::FltAllocAndInit(
          v56,
          a2->FileObject,
          v57,
          &v134[48],
          (v69->Parameters.Create.Options >> 10) & 4);
  if ( v70 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v70,
      (int)v149,
      (struct UnionFs::StackEventTracer *)0x1900002016CLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
      "PUSH: Creating handle context",
      &v134[8]);
    a1->IoStatus.Status = v70;
LABEL_160:
    v72 = *(void **)&v134[8];
    a1->IoStatus.Information = 0;
    if ( v72 )
      FltReleaseContext(v72);
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v134[48], v71);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v139, v73);
    if ( v139[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v139[16] + 24LL))(v139[16]);
    if ( v138[1] )
      utl::_RefCountBase::_DecStrong(v138[1]);
    if ( !*(_BYTE *)(v57 + 16) )
      *(_OWORD *)v57 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v57, v74);
    ExFreePoolWithTag((PVOID)v57, 0);
    if ( v55 )
    {
      utl::_RefCountBase::_DecStrong(v55);
      utl::_RefCountBase::_DecStrong(v55);
    }
LABEL_170:
    v45 = FileNameInformation;
    FileNameInformation = 0;
LABEL_101:
    if ( v45 )
      FltReleaseFileNameInformation(v45);
    goto LABEL_92;
  }
  v75 = a1->Iopb;
  v76 = v75->MajorFunction;
  if ( v76 == 0xF2 || v76 == 0xF9 )
  {
    if ( *(_DWORD *)&v134[20] != 2 )
      MicrosoftTelemetryAssertTriggeredMsgKM("lookupResult == MAPPING_LOOKUP_RESULT::MoreComponentsLeft");
    v96 = v130;
    v113 = *(void **)&v134[8];
    Open = UnionFs::UnionFsFilter::QueryOpen(
             (UnionFs::UnionFsFilter *)UnionFs::g_FilterState,
             a1,
             a2,
             FileNameInformation,
             *(struct UnionFs::UfsStreamHandleCtx **)&v134[8],
             v138[0],
             (struct UnionFs::StackEventTracer *)v149,
             v130);
    if ( Open < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)Open,
        (int)v149,
        (struct UnionFs::StackEventTracer *)0x5F400020182LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
        "PUSH: Query open processing",
        (const char *)v128);
      if ( a1->Iopb->MajorFunction == 0xF9 )
      {
        if ( v113 )
          FltReleaseContext(v113);
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v134[48], v116);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v139, v117);
        if ( v139[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v139[16] + 24LL))(v139[16]);
        if ( v138[1] )
          utl::_RefCountBase::_DecStrong(v138[1]);
        if ( !*(_BYTE *)(v57 + 16) )
          *(_OWORD *)v57 = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v57, v118);
        ExFreePoolWithTag((PVOID)v57, 0);
        if ( v55 )
        {
          utl::_RefCountBase::_DecStrong(v55);
          utl::_RefCountBase::_DecStrong(v55);
        }
        v119 = FileNameInformation;
        FileNameInformation = 0;
        if ( v119 )
          FltReleaseFileNameInformation(v119);
        if ( v132[1] )
          utl::_RefCountBase::_DecStrong(v132[1]);
        if ( v96 )
          PsDereferenceSiloContext(v96);
        v64 = 6;
      }
      else
      {
        if ( v113 )
          FltReleaseContext(v113);
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v134[48], v116);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v139, v120);
        if ( v139[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v139[16] + 24LL))(v139[16]);
        if ( v138[1] )
          utl::_RefCountBase::_DecStrong(v138[1]);
        if ( !*(_BYTE *)(v57 + 16) )
          *(_OWORD *)v57 = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v57, v121);
        ExFreePoolWithTag((PVOID)v57, 0);
        if ( v55 )
        {
          utl::_RefCountBase::_DecStrong(v55);
          utl::_RefCountBase::_DecStrong(v55);
        }
        v122 = FileNameInformation;
        FileNameInformation = 0;
        if ( v122 )
          FltReleaseFileNameInformation(v122);
        if ( v132[1] )
          utl::_RefCountBase::_DecStrong(v132[1]);
        if ( v96 )
          PsDereferenceSiloContext(v96);
        v64 = 3;
      }
      goto LABEL_306;
    }
    if ( a1->IoStatus.Status )
      MicrosoftTelemetryAssertTriggeredMsgKM("IRP_MJ_NETWORK_QUERY_OPEN should have succeeded");
    a1->IoStatus.Status = 0;
    a1->IoStatus.Information = 0;
    if ( v113 )
      FltReleaseContext(v113);
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v134[48], v115);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v139, v123);
    if ( v139[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v139[16] + 24LL))(v139[16]);
    if ( v138[1] )
      utl::_RefCountBase::_DecStrong(v138[1]);
    if ( !*(_BYTE *)(v57 + 16) )
      *(_OWORD *)v57 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v57, v124);
    ExFreePoolWithTag((PVOID)v57, 0);
    if ( v55 )
    {
      utl::_RefCountBase::_DecStrong(v55);
      utl::_RefCountBase::_DecStrong(v55);
    }
    v106 = FileNameInformation;
    FileNameInformation = 0;
LABEL_320:
    if ( v106 )
      FltReleaseFileNameInformation(v106);
    if ( v132[1] )
      utl::_RefCountBase::_DecStrong(v132[1]);
    if ( !v96 )
      goto LABEL_327;
    v10 = v96;
    goto LABEL_326;
  }
  if ( (v75->Parameters.Create.Options & 0x1000) != 0 && !UnionFs::UfsUnionCtx::ReserveSpaceForTombstone(v138[0]) )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)v149,
      (struct UnionFs::StackEventTracer *)0x32A0002019BLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
      "ORIGIN: Reserving tombstone space",
      &v134[8]);
    a1->IoStatus.Status = -1073741670;
    goto LABEL_160;
  }
  v77 = v138[1];
  v78 = v138[0];
  if ( v138[1] )
  {
    v79 = (__int64)v138[1] + 8;
    _InterlockedIncrement((volatile signed __int32 *)v138[1] + 2);
  }
  else
  {
    v79 = 8;
  }
  v140[0] = FileNameInformation;
  FileNameInformation = 0;
  v140[1] = v78;
  v140[2] = v77;
  if ( v77 )
    _InterlockedIncrement((volatile signed __int32 *)v79);
  v140[3] = v139[0];
  v141 = v139[1];
  wistd::function<void (bool)>::function<void (bool)>(v142, &v139[2]);
  memset(v139, 0, sizeof(v139));
  v143 = *(_QWORD *)&v134[8];
  v145 = 0;
  v146 = 0;
  v147 = 0;
  v148 = 0;
  v144 = 0;
  if ( v77 )
    utl::_RefCountBase::_DecStrong(v77);
  v80 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 224));
  if ( v80 )
    v81 = UnionFs::CreateContext::CreateContext(v80, v140);
  else
    v81 = 0;
  UnionFs::CreateContext::~CreateContext((UnionFs::CreateContext *)v140);
  if ( !v81 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)v149,
      (struct UnionFs::StackEventTracer *)0xFE000201A9LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
      "ORIGIN: Allocating create context",
      &v134[8]);
    a1->IoStatus.Status = -1073741670;
    a1->IoStatus.Information = 0;
LABEL_188:
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v134[48], v84);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v138);
    if ( !*(_BYTE *)(v57 + 16) )
      *(_OWORD *)v57 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v57, v85);
    ExFreePoolWithTag((PVOID)v57, 0);
    if ( v55 )
      utl::_RefCountBase::_DecStrong(v55);
    UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v134[16]);
    goto LABEL_170;
  }
  v86 = *(_DWORD *)&v134[20] == 1;
  *(_BYTE *)(v81 + 185) = v134[0];
  if ( v86 )
  {
    v87 = v136;
    *(_BYTE *)(v81 + 200) = 1;
    *v87 = v81;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v134[48], v82);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v138);
    if ( !*(_BYTE *)(v57 + 16) )
      *(_OWORD *)v57 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v57, v88);
    ExFreePoolWithTag((PVOID)v57, 0);
    if ( v55 )
      utl::_RefCountBase::_DecStrong(v55);
    UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v134[16]);
    v47 = FileNameInformation;
    FileNameInformation = 0;
LABEL_141:
    if ( !v47 )
      goto LABEL_143;
    goto LABEL_142;
  }
  *(_DWORD *)v134 = 0;
  if ( !UnionFs::Utils::GetCreateDisposition((UnionFs::Utils *)a1, (const struct _FLT_CALLBACK_DATA *)v134, v83) )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC00000E5LL,
      (int)v149,
      (struct UnionFs::StackEventTracer *)0xD2000201CALL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
      "ORIGIN: Unexpected create operation type",
      &v134[8]);
    a1->IoStatus.Status = -1073741595;
    a1->IoStatus.Information = 0;
    UnionFs::CreateContext::~CreateContext((UnionFs::CreateContext *)v81);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 224), (PVOID)v81);
    goto LABEL_188;
  }
  v90 = a2->FileObject->RelatedFileObject;
  if ( v90 )
  {
    FsContext = v90->FsContext;
    if ( FsContext )
    {
      v89 = 17217;
      if ( *FsContext == 17217 )
      {
        UnionFs::UfsStreamHandleCtx::FltGet(&v134[80], a2->Instance, v90);
        v89 = *(_QWORD *)&v134[80];
        if ( *(_QWORD *)&v134[80] )
        {
          v92 = **(_BYTE **)&v134[80] & 1;
          FltReleaseContext(*(PFLT_CONTEXT *)&v134[80]);
          if ( v92 )
          {
            v93 = IoReplaceFileObjectName(
                    a2->FileObject,
                    *(PWSTR *)(*(_QWORD *)v81 + 112LL),
                    *(_WORD *)(*(_QWORD *)v81 + 88LL) + *(_WORD *)(*(_QWORD *)v81 + 104LL));
            if ( v93 < 0 )
            {
              UnionFs::ProcessTraceStatusFromApi(
                (UnionFs *)(unsigned int)v93,
                (int)v149,
                (struct UnionFs::StackEventTracer *)0x78000201DDLL,
                (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
                "API: IoReplaceFileObjectName",
                &v134[8]);
              a1->IoStatus.Status = v93;
              a1->IoStatus.Information = 0;
              UnionFs::CreateContext::~CreateContext((UnionFs::CreateContext *)v81);
              ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 224), (PVOID)v81);
              FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v134[48], v94);
              UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v138);
              if ( !*(_BYTE *)(v57 + 16) )
                *(_OWORD *)v57 = 0;
              FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v57, v95);
              ExFreePoolWithTag((PVOID)v57, 0);
              if ( v55 )
                utl::_RefCountBase::_DecStrong(v55);
              UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v134[16]);
              goto LABEL_157;
            }
            a2->FileObject->RelatedFileObject = 0;
          }
        }
      }
    }
  }
  v131 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
  v96 = v130;
  if ( *(_DWORD *)v134 )
  {
    switch ( *(_DWORD *)v134 )
    {
      case 1:
        v98 = UnionFs::UnionFsFilter::PreCreateFileOpen(
                (UnionFs::UnionFsFilter *)UnionFs::g_FilterState,
                a1,
                a2,
                &v131,
                (struct UnionFs::CreateContext *)v81,
                (struct UnionFs::StackEventTracer *)v149,
                v130);
        break;
      case 2:
        v98 = UnionFs::UnionFsFilter::PreCreateFileCreate(
                (UnionFs::UnionFsFilter *)v89,
                a1,
                a2,
                &v131,
                (struct UnionFs::CreateContext *)v81,
                (struct UnionFs::StackEventTracer *)v149,
                v130);
        break;
      case 3:
        v98 = UnionFs::UnionFsFilter::PreCreateFileOpenIf(
                (UnionFs::UnionFsFilter *)UnionFs::g_FilterState,
                a1,
                a2,
                &v131,
                (struct UnionFs::CreateContext *)v81,
                (struct UnionFs::StackEventTracer *)v149,
                v130);
        break;
      case 4:
        v98 = UnionFs::UnionFsFilter::PreCreateFileOverwrite(
                (UnionFs::UnionFsFilter *)UnionFs::g_FilterState,
                a1,
                a2,
                &v131,
                (struct UnionFs::CreateContext *)v81,
                (struct UnionFs::StackEventTracer *)v149,
                v130);
        break;
      case 5:
        v98 = UnionFs::UnionFsFilter::PreCreateFileOverwriteIf(
                (UnionFs::UnionFsFilter *)UnionFs::g_FilterState,
                a1,
                a2,
                &v131,
                (struct UnionFs::CreateContext *)v81,
                (struct UnionFs::StackEventTracer *)v149,
                v130);
        break;
      default:
        MicrosoftTelemetryAssertTriggeredMsgKM("false");
        v97 = -1073741595;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC00000E5LL,
          (int)v149,
          (struct UnionFs::StackEventTracer *)0xE600020223LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
          "ORIGIN: Unexpected create disposition",
          &v134[8]);
LABEL_227:
        v102 = "PUSH: Pre-create processing";
        v103 = 0xD40002022ALL;
LABEL_228:
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v97,
          (int)v149,
          (struct UnionFs::StackEventTracer *)v103,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
          v102,
          (const char *)v127);
        a1->IoStatus.Status = v97;
        a1->IoStatus.Information = 0;
        UnionFs::CreateContext::~CreateContext((UnionFs::CreateContext *)v81);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 224), (PVOID)v81);
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v134[48], v104);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v138);
        if ( !*(_BYTE *)(v57 + 16) )
          *(_OWORD *)v57 = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v57, v105);
        ExFreePoolWithTag((PVOID)v57, 0);
        if ( v55 )
          utl::_RefCountBase::_DecStrong(v55);
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v134[16]);
        v106 = FileNameInformation;
        FileNameInformation = 0;
        goto LABEL_320;
    }
  }
  else
  {
    v98 = UnionFs::UnionFsFilter::PreCreateFileSupersede(
            (UnionFs::UnionFsFilter *)UnionFs::g_FilterState,
            a1,
            a2,
            &v131,
            (struct UnionFs::CreateContext *)v81,
            (struct UnionFs::StackEventTracer *)v149,
            v130);
  }
  v97 = v98;
  if ( v98 < 0 )
    goto LABEL_227;
  if ( v98 == 260 )
  {
    v97 = UnionFs::Utils::VirtualizeReparseTagData(
            (UnionFs::Utils *)&a1->TagData,
            *(struct _FLT_TAG_DATA_BUFFER ***)(v81 + 8),
            (const struct UnionFs::UfsUnionCtx *)v149,
            v101);
    if ( v97 >= 0 )
    {
      a1->IoStatus.Status = 260;
      UnionFs::CreateContext::~CreateContext((UnionFs::CreateContext *)v81);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 224), (PVOID)v81);
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v134[48], v107);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v138);
      if ( !*(_BYTE *)(v57 + 16) )
        *(_OWORD *)v57 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v57, v108);
      ExFreePoolWithTag((PVOID)v57, 0);
      if ( v55 )
        utl::_RefCountBase::_DecStrong(v55);
      UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v134[16]);
      v109 = FileNameInformation;
      FileNameInformation = 0;
      if ( v109 )
        FltReleaseFileNameInformation(v109);
      if ( v132[1] )
        utl::_RefCountBase::_DecStrong(v132[1]);
      if ( !v96 )
        goto LABEL_247;
      v41 = v96;
LABEL_246:
      PsDereferenceSiloContext(v41);
LABEL_247:
      v64 = 4;
LABEL_306:
      UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v149);
      return v64;
    }
    v102 = "PUSH: Munging TagData for STATUS_REPARSE";
    v103 = 0x6C60002023CLL;
    goto LABEL_228;
  }
  v110 = v131;
  if ( v131 == FLT_PREOP_SUCCESS_WITH_CALLBACK )
    goto LABEL_255;
  if ( a1->IoStatus.Status != 260 )
  {
    if ( ((v131 - 1) & 0xFFFFFFFC) != 0 || v131 == FLT_PREOP_DISALLOW_FASTIO )
      MicrosoftTelemetryAssertTriggeredMsgKM(
        "(callbackStatus == FLT_PREOP_SUCCESS_NO_CALLBACK) || (callbackStatus == FLT_PREOP_COMPLETE) || (callbackStatus ="
        "= FLT_PREOP_PENDING)");
    UnionFs::UnionFsFilter::AcknowledgeRedirectionEcp(
      v100,
      a1,
      *(const struct UnionFs::UfsStreamHandleCtx **)(v81 + 160));
    v110 = v131;
  }
  if ( v110 )
  {
    UnionFs::CreateContext::~CreateContext((UnionFs::CreateContext *)v81);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 224), (PVOID)v81);
  }
  else
  {
LABEL_255:
    *(_QWORD *)v136 = v81;
  }
  FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)&v134[48], v99);
  UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v138);
  if ( !*(_BYTE *)(v57 + 16) )
    *(_OWORD *)v57 = 0;
  FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v57, v111);
  ExFreePoolWithTag((PVOID)v57, 0);
  if ( v55 )
    utl::_RefCountBase::_DecStrong(v55);
  UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v134[16]);
  v112 = FileNameInformation;
  FileNameInformation = 0;
  if ( v112 )
    FltReleaseFileNameInformation(v112);
  if ( v132[1] )
    utl::_RefCountBase::_DecStrong(v132[1]);
  if ( v96 )
    PsDereferenceSiloContext(v96);
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v149);
  return (unsigned int)v110;
}

```

## disassembly

```asm
0x140011e20  mov     [rsp-8+arg_18], rbx
0x140011e25  push    rbp
0x140011e26  push    rsi
0x140011e27  push    rdi
0x140011e28  push    r12
0x140011e2a  push    r13
0x140011e2c  push    r14
0x140011e2e  push    r15
0x140011e30  lea     rbp, [rsp-480h]
0x140011e38  sub     rsp, 580h
0x140011e3f  mov     rax, cs:__security_cookie
0x140011e46  xor     rax, rsp
0x140011e49  mov     [rbp+4B0h+var_40], rax
0x140011e50  xor     edi, edi
0x140011e52  mov     [rbp+4B0h+var_4C0], r8
0x140011e56  mov     [r8], rdi
0x140011e59  mov     r13, rdx
0x140011e5c  mov     rdx, [rcx+10h]
0x140011e60  mov     rsi, rcx
0x140011e63  cmp     [rdx+4], dil
0x140011e67  jnz     short loc_140011E86
0x140011e69  mov     rax, [rdx+8]
0x140011e6d  test    dword ptr [rax+50h], 400000h
0x140011e74  jnz     short loc_140011E7C
0x140011e76  test    byte ptr [rdx+6], 2
0x140011e7a  jz      short loc_140011E86
0x140011e7c  mov     eax, 1
0x140011e81  jmp     loc_140013686
0x140011e86  mov     r8, rsi; struct _FLT_CALLBACK_DATA *
0x140011e89  lea     rcx, [rbp+4B0h+var_330]; this
0x140011e90  mov     rdx, 0CF0002002Ch; unsigned __int64
0x140011e9a  call    ??0StackEventTracer@UnionFs@@QEAA@_KPEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64,_FLT_CALLBACK_DATA const *)
0x140011e9f  mov     rdx, [r13+20h]
0x140011ea3  lea     rax, [rsp+5B0h+var_558]
0x140011ea8  mov     rcx, [r13+18h]
0x140011eac  lea     r9, [rbp+4B0h+var_330]
0x140011eb3  lea     r8, [rbp+4B0h+var_530+8]
0x140011eb7  mov     [rsp+5B0h+var_590], rax
0x140011ebc  mov     [rsp+5B0h+var_558], rdi
0x140011ec1  mov     qword ptr [rbp+4B0h+var_530+8], rdi
0x140011ec5  call    ?GetMappingTableForFileObject@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAPEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@PEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@@Z; UnionFs::Utils::GetMappingTableForFileObject(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsScratchMappingTable * *,UnionFs::StackEventTracer &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> *)
0x140011eca  mov     ebx, eax
0x140011ecc  mov     r15d, 4
0x140011ed2  test    eax, eax
0x140011ed4  jns     short loc_140011F1B
0x140011ed6  lea     rax, aPushGettingFil; "PUSH: Getting FILE_OBJECT silo"
0x140011edd  mov     r8, 2AE0002003Fh; struct UnionFs::StackEventTracer *
0x140011ee7  lea     r9, aUnionfsUnionfs_31; "UnionFs::UnionFsFilter::PreCreate"
0x140011eee  mov     [rsp+5B0h+var_590], rax; char *
0x140011ef3  lea     rdx, [rbp+4B0h+var_330]; int
0x140011efa  mov     ecx, ebx; this
0x140011efc  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140011f01  mov     [rsi+18h], ebx
0x140011f04  mov     [rsi+20h], rdi
0x140011f08  mov     rcx, [rsp+5B0h+var_558]
0x140011f0d  test    rcx, rcx
0x140011f10  jz      loc_140013675
0x140011f16  jmp     loc_140013669
0x140011f1b  mov     r12d, 1
0x140011f21  cmp     qword ptr [rbp+4B0h+var_530+8], rdi
0x140011f25  jz      loc_140012870
0x140011f2b  mov     rax, [rsi+10h]
0x140011f2f  lea     r14d, [r12+7]
0x140011f34  xorps   xmm0, xmm0
0x140011f37  movdqu  xmmword ptr [rsp+5B0h+var_548], xmm0
0x140011f3d  mov     edx, [rax+20h]
0x140011f40  mov     ecx, edx
0x140011f42  and     ecx, 2000h
0x140011f48  setnz   [rbp+4B0h+var_530]
0x140011f4c  cmp     [rax+4], dil
0x140011f50  jnz     loc_140012535
0x140011f56  test    ecx, ecx
0x140011f58  jz      loc_140012535
0x140011f5e  bt      edx, 0Ch
0x140011f62  jnb     short loc_140011FA4
0x140011f64  lea     rax, aOriginOpenByFi; "ORIGIN: Open by file ID and delete on c"...
0x140011f6b  mov     edi, 0C000000Dh
0x140011f70  mov     ecx, edi; this
0x140011f72  mov     [rsp+5B0h+var_590], rax; char *
0x140011f77  lea     r9, aUnionfsUnionfs_31; "UnionFs::UnionFsFilter::PreCreate"
0x140011f7e  mov     r8, 5E10002005Ch; struct UnionFs::StackEventTracer *
0x140011f88  lea     rdx, [rbp+4B0h+var_330]; int
0x140011f8f  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140011f94  mov     [rsi+18h], edi
0x140011f97  mov     qword ptr [rsi+20h], 0
0x140011f9f  jmp     loc_140011F08
0x140011fa4  mov     rax, [r13+20h]
0x140011fa8  mov     rdi, [rax+40h]
0x140011fac  test    rdi, rdi
0x140011faf  jz      short loc_140011FB9
0x140011fb1  mov     qword ptr [rax+40h], 0
0x140011fb9  mov     rcx, [r13+18h]; Instance
0x140011fbd  lea     r9, [rbp+4B0h+var_330]
0x140011fc4  lea     r8, [rsp+5B0h+Context]
0x140011fc9  mov     [rsp+5B0h+Context], 0
0x140011fd2  xor     edx, edx
0x140011fd4  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FLT_INSTANCE const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140011fd9  mov     ebx, eax
0x140011fdb  test    eax, eax
0x140011fdd  jns     short loc_140012034
0x140011fdf  lea     rax, aPushGettingIns_0; "PUSH: Getting instance context"
0x140011fe6  mov     r8, 38A00020071h; struct UnionFs::StackEventTracer *
0x140011ff0  lea     r9, aUnionfsUnionfs_31; "UnionFs::UnionFsFilter::PreCreate"
0x140011ff7  mov     [rsp+5B0h+var_590], rax; char *
0x140011ffc  lea     rdx, [rbp+4B0h+var_330]; int
0x140012003  mov     ecx, ebx; this
0x140012005  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001200a  mov     rcx, [rsp+5B0h+Context]; Context
0x14001200f  mov     [rsi+18h], ebx
0x140012012  mov     qword ptr [rsi+20h], 0
0x14001201a  test    rcx, rcx
0x14001201d  jz      loc_140011F08
0x140012023  call    cs:__imp_FltReleaseContext
0x14001202a  nop     dword ptr [rax+rax+00h]
0x14001202f  jmp     loc_140011F08
0x140012034  mov     rdx, [r13+20h]
0x140012038  mov     ecx, 0FFFDh
0x14001203d  movzx   r8d, word ptr [rdx+58h]
0x140012042  movzx   eax, r8w
0x140012046  sub     ax, r14w
0x14001204a  test    cx, ax
0x14001204d  jz      loc_1400121A1
0x140012053  lea     eax, [r8-10h]
0x140012057  test    cx, ax
0x14001205a  jz      loc_140012117
0x140012060  mov     eax, cs:dword_14009E178
0x140012066  cmp     eax, r15d
0x140012069  jbe     loc_1400120F8
0x14001206f  mov     rcx, cs:qword_14009E190
0x140012076  mov     edx, 200h
0x14001207b  mov     rax, cs:qword_14009E188
0x140012082  test    rdx, rax
0x140012085  jz      short loc_1400120F8
0x140012087  mov     rax, rcx
0x14001208a  and     rax, rdx
0x14001208d  cmp     rax, rcx
0x140012090  jnz     short loc_1400120F8
0x140012092  lea     rax, aOnecoreBaseFsU_14; "onecore\\base\\fs\\unionfs\\sys\\create"...
0x140012099  mov     word ptr [rbp+4B0h+var_530], r8w
0x14001209e  mov     [rbp+4B0h+var_4C0], rax
0x1400120a2  lea     r14, aUnionfsUnionfs_31; "UnionFs::UnionFsFilter::PreCreate"
0x1400120a9  lea     rax, aNotSupportedFi; "Not supported file ID size."
0x1400120b0  mov     dword ptr [rbp+4B0h+var_530+8], 0B0h
0x1400120b7  mov     qword ptr [rbp+4B0h+var_530+50h], rax
0x1400120bb  lea     rdx, dword_14009619C
0x1400120c2  lea     rax, [rbp+4B0h+var_530]
0x1400120c6  mov     qword ptr [rbp+4B0h+var_530+40h], r14
0x1400120ca  mov     [rsp+5B0h+var_570], rax
0x1400120cf  lea     rax, [rbp+4B0h+var_530+8]
0x1400120d3  mov     [rsp+5B0h+var_578], rax
0x1400120d8  lea     rax, [rbp+4B0h+var_4C0]
0x1400120dc  mov     [rsp+5B0h+var_580], rax
0x1400120e1  lea     rax, [rbp+4B0h+var_530+40h]
0x1400120e5  mov     [rsp+5B0h+var_588], rax
0x1400120ea  lea     rax, [rbp+4B0h+var_530+50h]
0x1400120ee  mov     [rsp+5B0h+var_590], rax
0x1400120f3  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &)
0x1400120f8  mov     rcx, [rsp+5B0h+Context]; Context
0x1400120fd  test    rcx, rcx
0x140012100  jz      loc_140012870
0x140012106  call    cs:__imp_FltReleaseContext
0x14001210d  nop     dword ptr [rax+rax+00h]
0x140012112  jmp     loc_140012870
0x140012117  mov     rcx, [rdx+60h]
0x14001211b  cmp     r8w, 10h
0x140012120  lea     rax, [rcx+2]
0x140012124  cmovnz  rcx, rax
0x140012128  mov     al, 0FFh
0x14001212a  cmp     [rcx], al
0x14001212c  jnz     short loc_14001217D
0x14001212e  cmp     [rcx+1], al
0x140012131  jnz     short loc_14001217D
0x140012133  cmp     [rcx+2], al
0x140012136  jnz     short loc_14001217D
0x140012138  cmp     [rcx+3], al
0x14001213b  jnz     short loc_14001217D
0x14001213d  cmp     [rcx+4], al
0x140012140  jnz     short loc_14001217D
0x140012142  cmp     [rcx+5], al
0x140012145  jnz     short loc_14001217D
0x140012147  cmp     [rcx+6], al
0x14001214a  jnz     short loc_14001217D
0x14001214c  cmp     [rcx+7], al
0x14001214f  jnz     short loc_14001217D
0x140012151  cmp     [rcx+8], al
0x140012154  jnz     short loc_14001217D
0x140012156  cmp     [rcx+9], al
0x140012159  jnz     short loc_14001217D
0x14001215b  cmp     [rcx+0Ah], al
0x14001215e  jnz     short loc_14001217D
0x140012160  cmp     [rcx+0Bh], al
0x140012163  jnz     short loc_14001217D
0x140012165  cmp     [rcx+0Ch], al
0x140012168  jnz     short loc_14001217D
0x14001216a  cmp     [rcx+0Dh], al
0x14001216d  jnz     short loc_14001217D
0x14001216f  cmp     [rcx+0Eh], al
0x140012172  jnz     short loc_14001217D
0x140012174  cmp     [rcx+0Fh], al
0x140012177  jz      loc_1400120F8
0x14001217d  movups  xmm0, xmmword ptr [rcx]
0x140012180  mov     rbx, [rsp+5B0h+Context]
0x140012185  lea     r9, [rsp+5B0h+var_548]
0x14001218a  mov     r8, rbx
0x14001218d  lea     rdx, [rbp+4B0h+var_530+50h]
0x140012191  lea     rcx, [rbp+4B0h+var_530+10h]
0x140012195  movdqu  xmmword ptr [rbp+4B0h+var_530+50h], xmm0
0x14001219a  call    ??0UfsFileID@UnionFs@@QEAA@U_FILE_ID_128@@AEBVUfsInstanceCtx@1@AEAV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@@Z; UnionFs::UfsFileID::UfsFileID(_FILE_ID_128,UnionFs::UfsInstanceCtx const &,utl::shared_ptr<UnionFs::UfsUnionCtx> &)
0x14001219f  jmp     short loc_1400121D4
0x1400121a1  mov     rdx, [rdx+60h]
0x1400121a5  cmp     r8w, r14w
0x1400121a9  lea     rax, [rdx+2]
0x1400121ad  cmovnz  rdx, rax
0x1400121b1  mov     rdx, [rdx]
0x1400121b4  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1400121b8  jz      loc_1400120F8
0x1400121be  mov     rbx, [rsp+5B0h+Context]
0x1400121c3  lea     r9, [rsp+5B0h+var_548]
0x1400121c8  mov     r8, rbx
0x1400121cb  lea     rcx, [rbp+4B0h+var_530+10h]; this
0x1400121cf  call    ??0UfsFileID@UnionFs@@QEAA@T_LARGE_INTEGER@@AEBVUfsInstanceCtx@1@AEAV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@@Z; UnionFs::UfsFileID::UfsFileID(_LARGE_INTEGER,UnionFs::UfsInstanceCtx const &,utl::shared_ptr<UnionFs::UfsUnionCtx> &)
0x1400121d4  movups  xmm1, xmmword ptr [rax+10h]
0x1400121d8  mov     r14, [rsp+5B0h+var_548]
0x1400121dd  movups  xmm0, xmmword ptr [rax]
0x1400121e0  movups  [rbp+4B0h+var_4A8], xmm1
0x1400121e4  movups  [rbp+4B0h+var_4B8], xmm0
0x1400121e8  test    r14, r14
0x1400121eb  jnz     short loc_14001220A
0x1400121ed  test    rbx, rbx
0x1400121f0  jz      loc_140012861
0x1400121f6  mov     rcx, rbx; Context
0x1400121f9  call    cs:__imp_FltReleaseContext
0x140012200  nop     dword ptr [rax+rax+00h]
0x140012205  jmp     loc_140012861
0x14001220a  test    rdi, rdi
0x14001220d  jz      loc_14001245C
0x140012213  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001221a  lea     rax, [rsp+5B0h+Context]
0x14001221f  xor     r15d, r15d
0x140012222  mov     qword ptr [rbp+4B0h+var_530+50h], rax
0x140012226  lea     r8, [rbp+4B0h+var_530+58h]; RetVolume
0x14001222a  mov     [rsp+5B0h+Context], r15
0x14001222f  mov     rdx, rdi; FileObject
0x140012232  mov     qword ptr [rbp+4B0h+var_530+58h], r15
0x140012236  mov     rcx, [rcx]; Filter
0x140012239  mov     [rbp+4B0h+var_4D0], r12b
0x14001223d  call    cs:__imp_FltGetVolumeFromFileObject
0x140012244  nop     dword ptr [rax+rax+00h]
0x140012249  mov     edi, eax
0x14001224b  cmp     [rbp+4B0h+var_4D0], r15b
0x14001224f  jz      short loc_140012278
0x140012251  mov     r14, qword ptr [rbp+4B0h+var_530+50h]
0x140012255  mov     r15, qword ptr [rbp+4B0h+var_530+58h]
0x140012259  mov     rcx, [r14]; FltObject
0x14001225c  test    rcx, rcx
0x14001225f  jz      short loc_14001226D
0x140012261  call    cs:__imp_FltObjectDereference
0x140012268  nop     dword ptr [rax+rax+00h]
0x14001226d  mov     [r14], r15
0x140012270  xor     r15d, r15d
0x140012273  mov     r14, [rsp+5B0h+var_548]
0x140012278  test    edi, edi
0x14001227a  jns     short loc_1400122B3
0x14001227c  lea     rax, aApiFltgetvolum; "API: FltGetVolumeFromFileObject"
0x140012283  mov     r8, 5FB000200C8h; struct UnionFs::StackEventTracer *
0x14001228d  lea     r9, aUnionfsUnionfs_31; "UnionFs::UnionFsFilter::PreCreate"
0x140012294  mov     [rsp+5B0h+var_590], rax; char *
0x140012299  lea     rdx, [rbp+4B0h+var_330]; int
0x1400122a0  mov     ecx, edi; this
0x1400122a2  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400122a7  mov     [rsi+18h], edi
0x1400122aa  mov     [rsi+20h], r15
0x1400122ae  jmp     loc_1400123E0
0x1400122b3  lea     rax, [rbp+4B0h+var_530+40h]
0x1400122b7  mov     qword ptr [rbp+4B0h+var_530+40h], r15
0x1400122bb  lea     rdx, [r14+48h]
0x1400122bf  mov     qword ptr [rbp+4B0h+var_530+10h], rax
0x1400122c3  lea     rcx, [rbp+4B0h+var_530+50h]
0x1400122c7  mov     qword ptr [rbp+4B0h+var_530+18h], r15
0x1400122cb  mov     [rbp+4B0h+var_530+20h], r12b
0x1400122cf  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x1400122d4  mov     rax, [r14+30h]
0x1400122d8  mov     rdi, [rax+8]
0x1400122dc  mov     r15, [rax]
0x1400122df  test    rdi, rdi
0x1400122e2  jz      short loc_1400122E8
0x1400122e4  lock inc dword ptr [rdi+8]
0x1400122e8  mov     rcx, qword ptr [rbp+4B0h+var_530+50h]; this
0x1400122ec  test    rcx, rcx
0x1400122ef  jz      short loc_1400122F6
0x1400122f1  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x1400122f6  mov     rcx, [r15+8]
0x1400122fa  lea     rdx, [rbp+4B0h+var_530+18h]; RetVolume
0x1400122fe  mov     rcx, [rcx]; Instance
0x140012301  call    cs:__imp_FltGetVolumeFromInstance
0x140012308  nop     dword ptr [rax+rax+00h]
0x14001230d  mov     r15d, eax
0x140012310  test    rdi, rdi
0x140012313  jz      short loc_14001231D
0x140012315  mov     rcx, rdi; this
  ... truncated ...
```
