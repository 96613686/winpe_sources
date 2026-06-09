# UnionFs::UnionFsFilter::PreCreate(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)

- ea: `0x140011e00`
- end: `0x140013701`
- name: `?PreCreate@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z`
- size: `6401`
- prototype: `enum _FLT_PREOP_CALLBACK_STATUS __fastcall(struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, void **)`
- caller_count: `1`
- callee_count: `44`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400747d0`

## callees

- `0x140002044`
- `0x140005574`
- `0x1400056b4`
- `0x140005d5c`
- `0x140006168`
- `0x140006340`
- `0x140006d38`
- `0x14000f7fc`
- `0x140010c08`
- `0x1400110a8`
- `0x14001124c`
- `0x1400119a4`
- `0x140011e00`
- `0x140013708`
- `0x140013bb0`
- `0x1400156a8`
- `0x140017370`
- `0x14001834c`
- `0x140019438`
- `0x14001a10c`
- `0x140023d9c`
- `0x140024094`
- `0x140027178`
- `0x1400276c4`
- `0x14002793c`
- `0x140036180`
- `0x140055d9c`
- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x140061798`
- `0x140064370`
- `0x14006e1a4`
- `0x14006efa8`
- `0x14006f8b8`
- `0x140078dc8`
- `0x140079a24`
- `0x140079c48`
- `0x140079da0`
- `0x140079df4`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140012656`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400127ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012915`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012a33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012c37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012cac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012ea8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013102`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001324c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013493`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013566`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013661`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012656`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400127ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012915`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012a33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012c37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012cac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012ea8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013102`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001324c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013493`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013566`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013661`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140012844`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140012d02`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400132a0`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140013388`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400134eb`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400135be`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400136b9`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140012844`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140012d02`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400132a0`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140013388`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400134eb`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400135be`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400136b9`
- `ntoskrnl!IoReplaceFileObjectName` at `0x140012492`
- `ntoskrnl!IoReplaceFileObjectName` at `0x140012e0a`
- `ntoskrnl!IoReplaceFileObjectName` at `0x140012492`
- `ntoskrnl!IoReplaceFileObjectName` at `0x140012e0a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140012d7d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140012e71`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400130cb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140013215`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140013315`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140012d7d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140012e71`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400130cb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140013215`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140013315`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140012b95`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140012b95`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x140012209`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x140012209`
- `FLTMGR!FltGetVolumeFromInstance` at `0x1400122d0`
- `FLTMGR!FltGetVolumeFromInstance` at `0x1400122d0`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001257b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001281f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140012cdd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001327d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140013361`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400134c8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001359b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140013696`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001257b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001281f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140012cdd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001327d`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140013361`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400134c8`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14001359b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140013696`
- `FLTMGR!FltReleaseContext` at `0x140011fef`
- `FLTMGR!FltReleaseContext` at `0x1400120d2`
- `FLTMGR!FltReleaseContext` at `0x1400121c8`
- `FLTMGR!FltReleaseContext` at `0x1400123d5`
- `FLTMGR!FltReleaseContext` at `0x140012461`
- `FLTMGR!FltReleaseContext` at `0x1400124f4`
- `FLTMGR!FltReleaseContext` at `0x1400129d6`
- `FLTMGR!FltReleaseContext` at `0x140012de0`
- `FLTMGR!FltReleaseContext` at `0x140013436`
- `FLTMGR!FltReleaseContext` at `0x140013509`
- `FLTMGR!FltReleaseContext` at `0x140013604`
- `FLTMGR!FltReleaseContext` at `0x140011fef`
- `FLTMGR!FltReleaseContext` at `0x1400120d2`
- `FLTMGR!FltReleaseContext` at `0x1400121c8`
- `FLTMGR!FltReleaseContext` at `0x1400123d5`
- `FLTMGR!FltReleaseContext` at `0x140012461`
- `FLTMGR!FltReleaseContext` at `0x1400124f4`
- `FLTMGR!FltReleaseContext` at `0x1400129d6`
- `FLTMGR!FltReleaseContext` at `0x140012de0`
- `FLTMGR!FltReleaseContext` at `0x140013436`
- `FLTMGR!FltReleaseContext` at `0x140013509`
- `FLTMGR!FltReleaseContext` at `0x140013604`
- `FLTMGR!FltObjectDereference` at `0x14001222d`
- `FLTMGR!FltObjectDereference` at `0x140012304`
- `FLTMGR!FltObjectDereference` at `0x1400123ab`
- `FLTMGR!FltObjectDereference` at `0x1400123c1`
- `FLTMGR!FltObjectDereference` at `0x14001240e`
- `FLTMGR!FltObjectDereference` at `0x140012424`
- `FLTMGR!FltObjectDereference` at `0x14001222d`
- `FLTMGR!FltObjectDereference` at `0x140012304`
- `FLTMGR!FltObjectDereference` at `0x1400123ab`
- `FLTMGR!FltObjectDereference` at `0x1400123c1`
- `FLTMGR!FltObjectDereference` at `0x14001240e`
- `FLTMGR!FltObjectDereference` at `0x140012424`
- `FLTMGR!FltSetCallbackDataDirty` at `0x1400124e0`
- `FLTMGR!FltSetCallbackDataDirty` at `0x1400124e0`

## string_xrefs

- `0x140011ecc`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140011f57`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140011fc0`: `UnionFs::UnionFsFilter::PreCreate`
- `0x14001206e`: `UnionFs::UnionFsFilter::PreCreate`
- `0x14001225a`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140012330`: `UnionFs::UnionFsFilter::PreCreate`
- `0x14001237a`: `UnionFs::UnionFsFilter::PreCreate`
- `0x1400124b5`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140012547`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140012613`: `UnionFs::UnionFsFilter::PreCreate`
- `0x1400126f4`: `UnionFs::UnionFsFilter::PreCreate`
- `0x14001289e`: `UnionFs::UnionFsFilter::PreCreate`
- `0x1400129aa`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140012aaa`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140012be7`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140012d3f`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140012e32`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140012edd`: `UnionFs::UnionFsFilter::PreCreate`
- `0x14001316e`: `UnionFs::UnionFsFilter::PreCreate`
- `0x1400131d7`: `UnionFs::UnionFsFilter::PreCreate`
- `0x14001340b`: `UnionFs::UnionFsFilter::PreCreate`
- `0x140011f44`: `ORIGIN: Open by file ID and delete on close flag both set`
- `0x14001205e`: `onecore\base\fs\unionfs\sys\create.cpp`
- `0x1400124a4`: `API: IoReplaceFileObjectName`
- `0x140012e21`: `API: IoReplaceFileObjectName`
- `0x140012536`: `PUSH: Getting pre-create name`
- `0x14001288d`: `PUSH: Getting relative path`
- `0x14001339f`: `lookupResult == MAPPING_LOOKUP_RESULT::MoreComponentsLeft`
- `0x1400133f5`: `PUSH: Query open processing`
- `0x1400135e8`: `IRP_MJ_NETWORK_QUERY_OPEN should have succeeded`
- `0x140012bd2`: `ORIGIN: Allocating create context`
- `0x140012d2a`: `ORIGIN: Unexpected create operation type`
- `0x140012f27`: `ORIGIN: Unexpected create disposition`
- `0x14001307f`: `PUSH: Pre-create processing`
- `0x14001315d`: `PUSH: Munging TagData for STATUS_REPARSE`
- `0x1400132d0`: `(callbackStatus == FLT_PREOP_SUCCESS_NO_CALLBACK) || (callbackStatus == FLT_PREOP_COMPLETE) || (callbackStatus == FLT_PREOP_PENDING)`

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
  PFLT_IO_PARAMETER_BLOCK v11; // rax
  ULONG Options; // edx
  PFILE_OBJECT v13; // rax
  struct _FILE_OBJECT *v14; // rdi
  struct _FLT_INSTANCE *v15; // rcx
  NTSTATUS v16; // ebx
  int v17; // r9d
  PFLT_CONTEXT v18; // rcx
  PFILE_OBJECT v19; // rdx
  int v20; // r8d
  _BYTE *Buffer; // rcx
  PFLT_CONTEXT v22; // rbx
  __int128 *v23; // rax
  _QWORD *v24; // rdx
  utl::_RefCountBase *v25; // r12
  __int128 v26; // xmm0
  struct _FLT_FILTER *v27; // rcx
  int VolumeFromFileObject; // edi
  PWSTR *v29; // r14
  PWSTR v30; // r15
  unsigned __int64 *v31; // rdx
  __int64 *v32; // rax
  volatile signed __int32 *v33; // rdi
  __int64 v34; // r15
  int VolumeFromInstance; // r15d
  PWSTR *v36; // rdi
  PWSTR v37; // r12
  PFLT_CONTEXT v38; // rcx
  struct UnionFs::UfsSiloCtx *v39; // rcx
  NTSTATUS NameFromFileID; // eax
  int v41; // edi
  NTSTATUS v42; // ebx
  struct _FLT_FILE_NAME_INFORMATION *v43; // rcx
  PFLT_FILE_NAME_INFORMATION v44; // r8
  struct _FLT_FILE_NAME_INFORMATION *v45; // rcx
  PFILE_OBJECT v46; // rax
  const struct _FLT_INSTANCE *v47; // rdx
  ULONG v48; // r9d
  struct _UNICODE_STRING *v49; // rdx
  NTSTATUS v50; // ebx
  struct _UNICODE_STRING *v51; // rdx
  __int64 v52; // rbx
  utl::_RefCountBase *v53; // rdi
  UnionFs::UfsLayerCtx *v54; // r12
  __int64 v55; // rbx
  int OwningUnion; // eax
  struct FsFltWil::Details::RundownRefCacheAware *v57; // rdx
  GUID *v58; // rax
  GUID v59; // xmm0
  __int128 v60; // xmm0
  UCHAR MajorFunction; // cl
  enum _FLT_PREOP_CALLBACK_STATUS v62; // ebx
  NTSTATUS RemainingPath; // r15d
  struct _UNICODE_STRING *v64; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v65; // rdx
  struct _UNICODE_STRING *v66; // rdx
  PFLT_IO_PARAMETER_BLOCK v67; // rax
  NTSTATUS v68; // r15d
  struct _UNICODE_STRING *v69; // rdx
  struct UnionFs::UfsStreamHandleCtx *v70; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v71; // rdx
  struct _UNICODE_STRING *v72; // rdx
  PFLT_IO_PARAMETER_BLOCK v73; // rcx
  UCHAR v74; // al
  utl::_RefCountBase *v75; // r14
  utl::_RefCountBase *v76; // rcx
  __int64 v77; // rdx
  PVOID v78; // rax
  __int64 v79; // r15
  struct _UNICODE_STRING *v80; // rdx
  unsigned int *v81; // r8
  struct _UNICODE_STRING *v82; // rdx
  struct _UNICODE_STRING *v83; // rdx
  bool v84; // zf
  _QWORD *v85; // rax
  struct _UNICODE_STRING *v86; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v87; // rcx
  __int64 v88; // rcx
  struct _FILE_OBJECT *RelatedFileObject; // r8
  _WORD *FsContext; // rax
  char v91; // r14
  int v92; // r12d
  struct _UNICODE_STRING *v93; // rdx
  struct _UNICODE_STRING *v94; // rdx
  struct UnionFs::UfsSiloCtx *v95; // r12
  NTSTATUS v96; // r13d
  int v97; // eax
  struct _UNICODE_STRING *v98; // rdx
  UnionFs::UnionFsFilter *v99; // rcx
  struct UnionFs::StackEventTracer *v100; // r9
  const char *v101; // rax
  __int64 v102; // r8
  struct _UNICODE_STRING *v103; // rdx
  struct _UNICODE_STRING *v104; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v105; // rcx
  NTSTATUS v106; // r14d
  const struct _FLT_RELATED_OBJECTS *v107; // rdx
  PFILE_OBJECT v108; // r9
  PFILE_OBJECT v109; // rax
  unsigned __int64 Length; // rcx
  struct _UNICODE_STRING *v111; // rdx
  struct _UNICODE_STRING *v112; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v113; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v114; // rcx
  struct UnionFs::UfsStreamHandleCtx *v115; // r15
  int Open; // eax
  struct _UNICODE_STRING *v117; // rdx
  struct _UNICODE_STRING *v118; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v119; // rdx
  struct _UNICODE_STRING *v120; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v121; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v122; // rdx
  struct _UNICODE_STRING *v123; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v124; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v125; // rdx
  struct _UNICODE_STRING *v126; // rdx
  struct UnionFs::StackEventTracer *v127; // [rsp+28h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v128; // [rsp+28h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v129; // [rsp+28h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v130; // [rsp+28h] [rbp-D8h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-B0h] BYREF
  struct UnionFs::UfsSiloCtx *v132; // [rsp+58h] [rbp-A8h] BYREF
  enum _FLT_PREOP_CALLBACK_STATUS v133; // [rsp+60h] [rbp-A0h] BYREF
  utl::_RefCountBase *v134[2]; // [rsp+68h] [rbp-98h] BYREF
  PFLT_CONTEXT Context; // [rsp+78h] [rbp-88h] BYREF
  int v136; // [rsp+80h] [rbp-80h] BYREF
  struct UnionFs::UfsStreamHandleCtx *v137; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING v138; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING v139; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v140; // [rsp+B0h] [rbp-50h]
  char *v141; // [rsp+C0h] [rbp-40h] BYREF
  __m256i v142; // [rsp+C8h] [rbp-38h] BYREF
  char *v143; // [rsp+E8h] [rbp-18h] BYREF
  PFLT_CONTEXT v144[4]; // [rsp+F0h] [rbp-10h] BYREF
  const struct _FLT_RELATED_OBJECTS *v145; // [rsp+110h] [rbp+10h]
  utl::_RefCountBase *v146[2]; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v147[17]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v148[4]; // [rsp+1B0h] [rbp+B0h] BYREF
  char v149; // [rsp+1D0h] [rbp+D0h]
  char v150[120]; // [rsp+1D8h] [rbp+D8h] BYREF
  struct UnionFs::UfsStreamHandleCtx *v151; // [rsp+250h] [rbp+150h]
  __int128 v152; // [rsp+258h] [rbp+158h]
  __int16 v153; // [rsp+268h] [rbp+168h]
  char v154; // [rsp+26Ah] [rbp+16Ah]
  __int64 v155; // [rsp+270h] [rbp+170h]
  char v156; // [rsp+278h] [rbp+178h]
  char v157[4]; // [rsp+280h] [rbp+180h] BYREF
  int v158; // [rsp+530h] [rbp+430h]
  __int128 v159; // [rsp+534h] [rbp+434h]
  GUID v160; // [rsp+544h] [rbp+444h]
  char v161; // [rsp+554h] [rbp+454h]
  __int128 v162; // [rsp+558h] [rbp+458h]
  char v163; // [rsp+568h] [rbp+468h]

  v145 = a2;
  *a3 = 0;
  Iopb = a1->Iopb;
  v143 = (char *)a3;
  if ( !Iopb->MajorFunction && ((Iopb->TargetFileObject->Flags & 0x400000) != 0 || (Iopb->OperationFlags & 2) != 0) )
    return 1;
  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v157, 0xCF0002002CuLL, a1);
  FileObject = a2->FileObject;
  Instance = a2->Instance;
  v132 = 0;
  v137 = 0;
  MappingTableForFileObject = UnionFs::Utils::GetMappingTableForFileObject(Instance, FileObject, &v137, v157, &v132);
  if ( MappingTableForFileObject < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)MappingTableForFileObject,
      (int)v157,
      (struct UnionFs::StackEventTracer *)0x2AE0002003FLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
      "PUSH: Getting FILE_OBJECT silo",
      (const char *)v127);
    a1->IoStatus.Status = MappingTableForFileObject;
LABEL_7:
    a1->IoStatus.Information = 0;
    goto LABEL_8;
  }
  if ( !v137 )
    goto LABEL_145;
  v11 = a1->Iopb;
  *(_OWORD *)v134 = 0;
  Options = v11->Parameters.Create.Options;
  LOBYTE(v136) = (Options & 0x2000) != 0;
  if ( v11->MajorFunction || (Options & 0x2000) == 0 )
  {
LABEL_99:
    FileNameInformation = 0;
    *(_QWORD *)&v139.Length = a1;
    v139.Buffer = 0;
    v140 = 0;
    v42 = UnionFs::Utils::GetFileNameInformation(&v139, 16777474, &FileNameInformation, v157);
    if ( v42 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v42,
        (int)v157,
        (struct UnionFs::StackEventTracer *)0xD000020111LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
        "PUSH: Getting pre-create name",
        (const char *)v127);
      a1->IoStatus.Status = v42;
      a1->IoStatus.Information = 0;
LABEL_101:
      v43 = FileNameInformation;
      FileNameInformation = 0;
      goto LABEL_102;
    }
    v44 = FileNameInformation;
    if ( FileNameInformation->Name.Length == FileNameInformation->Volume.Length )
    {
      FileNameInformation = 0;
      if ( !v44 )
        goto LABEL_143;
      v45 = v44;
LABEL_142:
      FltReleaseFileNameInformation(v45);
LABEL_143:
      if ( v134[1] )
        utl::_RefCountBase::_DecStrong(v134[1]);
      goto LABEL_145;
    }
    v46 = a2->FileObject;
    v47 = a2->Instance;
    v142.m256i_i64[0] = 1;
    v48 = v46->Flags >> 17;
    memset(&v142.m256i_u64[1], 0, 24);
    v50 = UnionFs::UfsScratchMappingTable::LookupScratchRoot(
            v137,
            v47,
            FileNameInformation,
            (v48 & 1) == 0,
            (struct UnionFs::LookupScratchRootResults *)&v142,
            (struct UnionFs::StackEventTracer *)v157);
    if ( v50 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v50,
        (int)v157,
        (struct UnionFs::StackEventTracer *)0xD100020127LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
        "PUSH: Looking up name",
        (const char *)v128);
      a1->IoStatus.Status = v50;
      v52 = v142.m256i_i64[3];
      a1->IoStatus.Information = 0;
      if ( v52 )
      {
        if ( !*(_BYTE *)(v52 + 16) )
          *(_OWORD *)v52 = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v52, v51);
        ExFreePoolWithTag((PVOID)v52, 0);
      }
      if ( v142.m256i_i64[2] )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v142.m256i_i64[2]);
      goto LABEL_101;
    }
    v53 = (utl::_RefCountBase *)v142.m256i_i64[2];
    v54 = (UnionFs::UfsLayerCtx *)v142.m256i_i64[1];
    if ( v142.m256i_i64[2] )
      _InterlockedIncrement((volatile signed __int32 *)(v142.m256i_i64[2] + 8));
    v55 = v142.m256i_i64[3];
    *(_QWORD *)&v139.Length = v142.m256i_i64[3];
    v142.m256i_i64[3] = 0;
    if ( !v54 )
    {
LABEL_135:
      if ( v55 )
      {
        if ( !*(_BYTE *)(v55 + 16) )
          *(_OWORD *)v55 = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v55, v49);
        ExFreePoolWithTag((PVOID)v55, 0);
      }
      if ( v53 )
      {
        utl::_RefCountBase::_DecStrong(v53);
        utl::_RefCountBase::_DecStrong(v53);
      }
      v45 = FileNameInformation;
      FileNameInformation = 0;
      if ( !v45 )
        goto LABEL_143;
      goto LABEL_142;
    }
    *(_OWORD *)v146 = 0;
    memset(v147, 0, sizeof(v147));
    OwningUnion = UnionFs::UfsLayerCtx::TryGetOwningUnion(
                    v54,
                    (struct UnionFs::UfsUnionCtxWithRundown *)v146,
                    (struct UnionFs::StackEventTracer *)v157);
    if ( OwningUnion < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)OwningUnion,
        (int)v157,
        (struct UnionFs::StackEventTracer *)0x4210002013BLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
        "PUSH: Union no longer available",
        (const char *)v128);
LABEL_131:
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v147, v57);
      if ( v147[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v147[16] + 24LL))(v147[16]);
      if ( v146[1] )
        utl::_RefCountBase::_DecStrong(v146[1]);
      goto LABEL_135;
    }
    if ( v146[0] && !v161 )
    {
      v158 = *((_DWORD *)v146[0] + 7);
      v159 = *(_OWORD *)((char *)v146[0] + 8);
      if ( *((_DWORD *)v146[0] + 7) == 2 && (v58 = (GUID *)*((_QWORD *)v146[0] + 4)) != 0 )
        v59 = v58[2];
      else
        v59 = GUID_NULL;
      v160 = v59;
      v161 = 1;
    }
    if ( !v163 )
    {
      v60 = *((_OWORD *)v54 + 3);
      v163 = 1;
      v162 = v60;
    }
    MajorFunction = a1->Iopb->MajorFunction;
    if ( (MajorFunction == 0xF2 || MajorFunction == 0xF9) && v142.m256i_i32[1] == 1 )
      goto LABEL_131;
    v138 = 0;
    *(_OWORD *)v144 = *(_OWORD *)v55;
    RemainingPath = UnionFs::Utils::GetRemainingPath(FileNameInformation, v144, &v138, v157);
    if ( RemainingPath < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)RemainingPath,
        (int)v157,
        (struct UnionFs::StackEventTracer *)0x1C40002015CLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
        "PUSH: Getting relative path",
        (const char *)v128);
      a1->IoStatus.Status = RemainingPath;
      a1->IoStatus.Information = 0;
      FsFltWil::Details::FreeUnicodeString(&v138, v64);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v147, v65);
      if ( v147[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v147[16] + 24LL))(v147[16]);
      if ( v146[1] )
        utl::_RefCountBase::_DecStrong(v146[1]);
      if ( !*(_BYTE *)(v55 + 16) )
        *(_OWORD *)v55 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v55, v66);
      ExFreePoolWithTag((PVOID)v55, 0);
      if ( v53 )
      {
        utl::_RefCountBase::_DecStrong(v53);
        utl::_RefCountBase::_DecStrong(v53);
      }
LABEL_157:
      v43 = FileNameInformation;
      FileNameInformation = 0;
      goto LABEL_102;
    }
    v67 = a1->Iopb;
    v137 = 0;
    v68 = UnionFs::UfsStreamHandleCtx::FltAllocAndInit(
            v54,
            a2->FileObject,
            v55,
            &v138,
            (v67->Parameters.Create.Options >> 10) & 4);
    if ( v68 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v68,
        (int)v157,
        (struct UnionFs::StackEventTracer *)0x1900002016CLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
        "PUSH: Creating handle context",
        (const char *)&v137);
      a1->IoStatus.Status = v68;
LABEL_160:
      v70 = v137;
      a1->IoStatus.Information = 0;
      if ( v70 )
        FltReleaseContext(v70);
      FsFltWil::Details::FreeUnicodeString(&v138, v69);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v147, v71);
      if ( v147[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v147[16] + 24LL))(v147[16]);
      if ( v146[1] )
        utl::_RefCountBase::_DecStrong(v146[1]);
      if ( !*(_BYTE *)(v55 + 16) )
        *(_OWORD *)v55 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v55, v72);
      ExFreePoolWithTag((PVOID)v55, 0);
      if ( v53 )
      {
        utl::_RefCountBase::_DecStrong(v53);
        utl::_RefCountBase::_DecStrong(v53);
      }
LABEL_170:
      v43 = FileNameInformation;
      FileNameInformation = 0;
LABEL_102:
      if ( v43 )
        FltReleaseFileNameInformation(v43);
      goto LABEL_93;
    }
    v73 = a1->Iopb;
    v74 = v73->MajorFunction;
    if ( v74 == 0xF2 || v74 == 0xF9 )
    {
      if ( v142.m256i_i32[1] != 2 )
        MicrosoftTelemetryAssertTriggeredMsgKM("lookupResult == MAPPING_LOOKUP_RESULT::MoreComponentsLeft");
      v95 = v132;
      v115 = v137;
      Open = UnionFs::UnionFsFilter::QueryOpen(
               (UnionFs::UnionFsFilter *)UnionFs::g_FilterState,
               a1,
               a2,
               FileNameInformation,
               v137,
               v146[0],
               (struct UnionFs::StackEventTracer *)v157,
               v132);
      if ( Open < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)Open,
          (int)v157,
          (struct UnionFs::StackEventTracer *)0x5F400020182LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
          "PUSH: Query open processing",
          (const char *)v130);
        if ( a1->Iopb->MajorFunction == 0xF9 )
        {
          if ( v115 )
            FltReleaseContext(v115);
          FsFltWil::Details::FreeUnicodeString(&v138, v118);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v147, v119);
          if ( v147[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v147[16] + 24LL))(v147[16]);
          if ( v146[1] )
            utl::_RefCountBase::_DecStrong(v146[1]);
          if ( !*(_BYTE *)(v55 + 16) )
            *(_OWORD *)v55 = 0;
          FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v55, v120);
          ExFreePoolWithTag((PVOID)v55, 0);
          if ( v53 )
          {
            utl::_RefCountBase::_DecStrong(v53);
            utl::_RefCountBase::_DecStrong(v53);
          }
          v121 = FileNameInformation;
          FileNameInformation = 0;
          if ( v121 )
            FltReleaseFileNameInformation(v121);
          if ( v134[1] )
            utl::_RefCountBase::_DecStrong(v134[1]);
          if ( v95 )
            PsDereferenceSiloContext(v95);
          v62 = FLT_PREOP_DISALLOW_FSFILTER_IO;
        }
        else
        {
          if ( v115 )
            FltReleaseContext(v115);
          FsFltWil::Details::FreeUnicodeString(&v138, v118);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v147, v122);
          if ( v147[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v147[16] + 24LL))(v147[16]);
          if ( v146[1] )
            utl::_RefCountBase::_DecStrong(v146[1]);
          if ( !*(_BYTE *)(v55 + 16) )
            *(_OWORD *)v55 = 0;
          FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v55, v123);
          ExFreePoolWithTag((PVOID)v55, 0);
          if ( v53 )
          {
            utl::_RefCountBase::_DecStrong(v53);
            utl::_RefCountBase::_DecStrong(v53);
          }
          v124 = FileNameInformation;
          FileNameInformation = 0;
          if ( v124 )
            FltReleaseFileNameInformation(v124);
          if ( v134[1] )
            utl::_RefCountBase::_DecStrong(v134[1]);
          if ( v95 )
            PsDereferenceSiloContext(v95);
          v62 = FLT_PREOP_DISALLOW_FASTIO;
        }
        goto LABEL_312;
      }
      if ( a1->IoStatus.Status )
        MicrosoftTelemetryAssertTriggeredMsgKM("IRP_MJ_NETWORK_QUERY_OPEN should have succeeded");
      a1->IoStatus.Status = 0;
      a1->IoStatus.Information = 0;
      if ( v115 )
        FltReleaseContext(v115);
      FsFltWil::Details::FreeUnicodeString(&v138, v117);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v147, v125);
      if ( v147[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v147[16] + 24LL))(v147[16]);
      if ( v146[1] )
        utl::_RefCountBase::_DecStrong(v146[1]);
      if ( !*(_BYTE *)(v55 + 16) )
        *(_OWORD *)v55 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v55, v126);
      ExFreePoolWithTag((PVOID)v55, 0);
      if ( v53 )
      {
        utl::_RefCountBase::_DecStrong(v53);
        utl::_RefCountBase::_DecStrong(v53);
      }
      v105 = FileNameInformation;
      FileNameInformation = 0;
LABEL_326:
      if ( v105 )
        FltReleaseFileNameInformation(v105);
      if ( v134[1] )
        utl::_RefCountBase::_DecStrong(v134[1]);
      if ( !v95 )
        goto LABEL_333;
      v10 = v95;
      goto LABEL_332;
    }
    if ( (v73->Parameters.Create.Options & 0x1000) != 0 && !UnionFs::UfsUnionCtx::ReserveSpaceForTombstone(v146[0]) )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)v157,
        (struct UnionFs::StackEventTracer *)0x32A0002019BLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
        "ORIGIN: Reserving tombstone space",
        (const char *)&v137);
      a1->IoStatus.Status = -1073741670;
      goto LABEL_160;
    }
    v75 = v146[1];
    v76 = v146[0];
    if ( v146[1] )
    {
      v77 = (__int64)v146[1] + 8;
      _InterlockedIncrement((volatile signed __int32 *)v146[1] + 2);
    }
    else
    {
      v77 = 8;
    }
    v148[0] = FileNameInformation;
    FileNameInformation = 0;
    v148[1] = v76;
    v148[2] = v75;
    if ( v75 )
      _InterlockedIncrement((volatile signed __int32 *)v77);
    v148[3] = v147[0];
    v149 = v147[1];
    wistd::function<void (bool)>::function<void (bool)>(v150, &v147[2]);
    memset(v147, 0, sizeof(v147));
    v151 = v137;
    v153 = 0;
    v154 = 0;
    v155 = 0;
    v156 = 0;
    v152 = 0;
    if ( v75 )
      utl::_RefCountBase::_DecStrong(v75);
    v78 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 224));
    if ( v78 )
      v79 = UnionFs::CreateContext::CreateContext(v78, v148);
    else
      v79 = 0;
    UnionFs::CreateContext::~CreateContext((UnionFs::CreateContext *)v148);
    if ( !v79 )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)v157,
        (struct UnionFs::StackEventTracer *)0xFE000201A9LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
        "ORIGIN: Allocating create context",
        (const char *)&v137);
      a1->IoStatus.Status = -1073741670;
      a1->IoStatus.Information = 0;
LABEL_188:
      FsFltWil::Details::FreeUnicodeString(&v138, v82);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v146);
      if ( !*(_BYTE *)(v55 + 16) )
        *(_OWORD *)v55 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v55, v83);
      ExFreePoolWithTag((PVOID)v55, 0);
      if ( v53 )
        utl::_RefCountBase::_DecStrong(v53);
      UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v142);
      goto LABEL_170;
    }
    v84 = v142.m256i_i32[1] == 1;
    *(_BYTE *)(v79 + 185) = v136;
    if ( v84 )
    {
      v85 = v143;
      *(_BYTE *)(v79 + 200) = 1;
      *v85 = v79;
      FsFltWil::Details::FreeUnicodeString(&v138, v80);
      UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v146);
      if ( !*(_BYTE *)(v55 + 16) )
        *(_OWORD *)v55 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v55, v86);
      ExFreePoolWithTag((PVOID)v55, 0);
      if ( v53 )
        utl::_RefCountBase::_DecStrong(v53);
      UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v142);
      v87 = FileNameInformation;
      FileNameInformation = 0;
      if ( v87 )
        FltReleaseFileNameInformation(v87);
      if ( v134[1] )
        utl::_RefCountBase::_DecStrong(v134[1]);
      if ( v132 )
        PsDereferenceSiloContext(v132);
      v62 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
      goto LABEL_312;
    }
    v136 = 0;
    if ( !UnionFs::Utils::GetCreateDisposition((UnionFs::Utils *)a1, (const struct _FLT_CALLBACK_DATA *)&v136, v81) )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC00000E5LL,
        (int)v157,
        (struct UnionFs::StackEventTracer *)0xD2000201CALL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
        "ORIGIN: Unexpected create operation type",
        (const char *)&v137);
      a1->IoStatus.Status = -1073741595;
      a1->IoStatus.Information = 0;
      UnionFs::CreateContext::~CreateContext((UnionFs::CreateContext *)v79);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 224), (PVOID)v79);
      goto LABEL_188;
    }
    RelatedFileObject = a2->FileObject->RelatedFileObject;
    if ( RelatedFileObject )
    {
      FsContext = RelatedFileObject->FsContext;
      if ( FsContext )
      {
        v88 = 17217;
        if ( *FsContext == 17217 )
        {
          UnionFs::UfsStreamHandleCtx::FltGet(v144, a2->Instance);
          v88 = (__int64)v144[0];
          if ( v144[0] )
          {
            v91 = *(_BYTE *)v144[0] & 1;
            FltReleaseContext(v144[0]);
            if ( v91 )
            {
              v92 = IoReplaceFileObjectName(
                      a2->FileObject,
                      *(PWSTR *)(*(_QWORD *)v79 + 112LL),
                      *(_WORD *)(*(_QWORD *)v79 + 88LL) + *(_WORD *)(*(_QWORD *)v79 + 104LL));
              if ( v92 < 0 )
              {
                UnionFs::ProcessTraceStatusFromApi(
                  (UnionFs *)(unsigned int)v92,
                  (int)v157,
                  (struct UnionFs::StackEventTracer *)0x78000201DDLL,
                  (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
                  "API: IoReplaceFileObjectName",
                  (const char *)&v137);
                a1->IoStatus.Status = v92;
                a1->IoStatus.Information = 0;
                UnionFs::CreateContext::~CreateContext((UnionFs::CreateContext *)v79);
                ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 224), (PVOID)v79);
                FsFltWil::Details::FreeUnicodeString(&v138, v93);
                UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v146);
                if ( !*(_BYTE *)(v55 + 16) )
                  *(_OWORD *)v55 = 0;
                FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v55, v94);
                ExFreePoolWithTag((PVOID)v55, 0);
                if ( v53 )
                  utl::_RefCountBase::_DecStrong(v53);
                UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v142);
                goto LABEL_157;
              }
              a2->FileObject->RelatedFileObject = 0;
            }
          }
        }
      }
    }
    v133 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
    v95 = v132;
    if ( v136 )
    {
      switch ( v136 )
      {
        case 1:
          v97 = UnionFs::UnionFsFilter::PreCreateFileOpen(
                  (UnionFs::UnionFsFilter *)UnionFs::g_FilterState,
                  a1,
                  a2,
                  &v133,
                  (struct UnionFs::CreateContext *)v79,
                  (struct UnionFs::StackEventTracer *)v157,
                  v132);
          break;
        case 2:
          v97 = UnionFs::UnionFsFilter::PreCreateFileCreate(
                  (UnionFs::UnionFsFilter *)v88,
                  a1,
                  a2,
                  &v133,
                  (struct UnionFs::CreateContext *)v79,
                  (struct UnionFs::StackEventTracer *)v157,
                  v132);
          break;
        case 3:
          v97 = UnionFs::UnionFsFilter::PreCreateFileOpenIf(
                  (UnionFs::UnionFsFilter *)UnionFs::g_FilterState,
                  a1,
                  a2,
                  &v133,
                  (struct UnionFs::CreateContext *)v79,
                  (struct UnionFs::StackEventTracer *)v157,
                  v132);
          break;
        case 4:
          v97 = UnionFs::UnionFsFilter::PreCreateFileOverwrite(
                  (UnionFs::UnionFsFilter *)UnionFs::g_FilterState,
                  a1,
                  a2,
                  &v133,
                  (struct UnionFs::CreateContext *)v79,
                  (struct UnionFs::StackEventTracer *)v157,
                  v132);
          break;
        case 5:
          v97 = UnionFs::UnionFsFilter::PreCreateFileOverwriteIf(
                  (UnionFs::UnionFsFilter *)UnionFs::g_FilterState,
                  a1,
                  a2,
                  &v133,
                  (struct UnionFs::CreateContext *)v79,
                  (struct UnionFs::StackEventTracer *)v157,
                  v132);
          break;
        default:
          MicrosoftTelemetryAssertTriggeredMsgKM("false");
          v96 = -1073741595;
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC00000E5LL,
            (int)v157,
            (struct UnionFs::StackEventTracer *)0xE600020223LL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
            "ORIGIN: Unexpected create disposition",
            (const char *)&v137);
          goto LABEL_233;
      }
    }
    else
    {
      v97 = UnionFs::UnionFsFilter::PreCreateFileSupersede(
              (UnionFs::UnionFsFilter *)UnionFs::g_FilterState,
              a1,
              a2,
              &v133,
              (struct UnionFs::CreateContext *)v79,
              (struct UnionFs::StackEventTracer *)v157,
              v132);
    }
    v96 = v97;
    if ( v97 >= 0 )
    {
      v106 = 260;
      if ( v97 != 260 )
      {
        v62 = v133;
        if ( v133 == FLT_PREOP_SUCCESS_WITH_CALLBACK )
          goto LABEL_264;
        if ( ((v133 - 1) & 0xFFFFFFFC) != 0 || v133 == FLT_PREOP_DISALLOW_FASTIO )
          MicrosoftTelemetryAssertTriggeredMsgKM(
            "(callbackStatus == FLT_PREOP_SUCCESS_NO_CALLBACK) || (callbackStatus == FLT_PREOP_COMPLETE) || (callbackStat"
            "us == FLT_PREOP_PENDING)");
        UnionFs::UnionFsFilter::AcknowledgeRedirectionEcp(
          v99,
          a1,
          *(const struct UnionFs::UfsStreamHandleCtx **)(v79 + 160));
        v62 = v133;
        if ( v133 )
        {
          UnionFs::CreateContext::~CreateContext((UnionFs::CreateContext *)v79);
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 224), (PVOID)v79);
        }
        else
        {
LABEL_264:
          *(_QWORD *)v143 = v79;
        }
        FsFltWil::Details::FreeUnicodeString(&v138, v98);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v146);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v139);
        if ( v53 )
          utl::_RefCountBase::_DecStrong(v53);
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v142);
        v114 = FileNameInformation;
        FileNameInformation = 0;
        if ( v114 )
          FltReleaseFileNameInformation(v114);
        if ( v134[1] )
          utl::_RefCountBase::_DecStrong(v134[1]);
        if ( v95 )
          PsDereferenceSiloContext(v95);
        goto LABEL_312;
      }
      v96 = UnionFs::Utils::VirtualizeReparseTagData(
              (UnionFs::Utils *)&a1->TagData,
              *(struct _FLT_TAG_DATA_BUFFER ***)(v79 + 8),
              (const struct UnionFs::UfsUnionCtx *)v157,
              v100);
      if ( v96 >= 0 )
      {
        v107 = v145;
        v108 = v145->FileObject;
        if ( v108->FileName.Buffer[((unsigned __int64)v108->FileName.Length >> 1) - 1] == 92 )
          v108->FileName.Length -= 2;
        v109 = v107->FileObject;
        Length = v109->FileName.Length;
        if ( (_WORD)Length && v109->FileName.Buffer[(Length >> 1) - 1] == 92 )
        {
          v106 = -1073741773;
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC0000033LL,
            (int)v157,
            (struct UnionFs::StackEventTracer *)0x3030002024DLL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
            "ORIGIN: Double trailing backslash",
            (const char *)v129);
          a1->IoStatus.Information = 0;
        }
        a1->IoStatus.Status = v106;
        UnionFs::CreateContext::~CreateContext((UnionFs::CreateContext *)v79);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 224), (PVOID)v79);
        FsFltWil::Details::FreeUnicodeString(&v138, v111);
        UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v146);
        if ( !*(_BYTE *)(v55 + 16) )
          *(_OWORD *)v55 = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v55, v112);
        ExFreePoolWithTag((PVOID)v55, 0);
        if ( v53 )
          utl::_RefCountBase::_DecStrong(v53);
        UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v142);
        v113 = FileNameInformation;
        FileNameInformation = 0;
        if ( v113 )
          FltReleaseFileNameInformation(v113);
        if ( v134[1] )
          utl::_RefCountBase::_DecStrong(v134[1]);
        if ( !v95 )
          goto LABEL_258;
        v39 = v95;
LABEL_257:
        PsDereferenceSiloContext(v39);
LABEL_258:
        v62 = FLT_PREOP_COMPLETE;
LABEL_312:
        UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v157);
        return (unsigned int)v62;
      }
      v101 = "PUSH: Munging TagData for STATUS_REPARSE";
      v102 = 0x6C60002023CLL;
      goto LABEL_234;
    }
LABEL_233:
    v101 = "PUSH: Pre-create processing";
    v102 = 0xD40002022ALL;
LABEL_234:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v96,
      (int)v157,
      (struct UnionFs::StackEventTracer *)v102,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
      v101,
      (const char *)v129);
    a1->IoStatus.Status = v96;
    a1->IoStatus.Information = 0;
    UnionFs::CreateContext::~CreateContext((UnionFs::CreateContext *)v79);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 224), (PVOID)v79);
    FsFltWil::Details::FreeUnicodeString(&v138, v103);
    UnionFs::UfsUnionCtxWithRundown::~UfsUnionCtxWithRundown((UnionFs::UfsUnionCtxWithRundown *)v146);
    if ( !*(_BYTE *)(v55 + 16) )
      *(_OWORD *)v55 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v55, v104);
    ExFreePoolWithTag((PVOID)v55, 0);
    if ( v53 )
      utl::_RefCountBase::_DecStrong(v53);
    UnionFs::LookupScratchRootResults::~LookupScratchRootResults((UnionFs::LookupScratchRootResults *)&v142);
    v105 = FileNameInformation;
    FileNameInformation = 0;
    goto LABEL_326;
  }
  if ( (Options & 0x1000) != 0 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000000DLL,
      (int)v157,
      (struct UnionFs::StackEventTracer *)0x5E10002005CLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
      "ORIGIN: Open by file ID and delete on close flag both set",
      (const char *)v127);
    a1->IoStatus.Status = -1073741811;
    goto LABEL_7;
  }
  v13 = a2->FileObject;
  v14 = v13->RelatedFileObject;
  if ( v14 )
    v13->RelatedFileObject = 0;
  v15 = a2->Instance;
  Context = 0;
  v16 = UnionFs::UfsInstanceCtx::FltGet(v15);
  if ( v16 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v16,
      (int)v157,
      (struct UnionFs::StackEventTracer *)0x38A00020071LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
      "PUSH: Getting instance context",
      (const char *)v127);
    v18 = Context;
    a1->IoStatus.Status = v16;
    a1->IoStatus.Information = 0;
    if ( v18 )
      FltReleaseContext(v18);
    goto LABEL_8;
  }
  v19 = a2->FileObject;
  v20 = v19->FileName.Length;
  if ( (((_WORD)v20 - 8) & 0xFFFD) != 0 )
  {
    if ( (((_WORD)v20 - 16) & 0xFFFD) != 0 )
    {
      if ( (unsigned int)dword_14009E178 > 4
        && (qword_14009E188 & 0x200) != 0
        && (qword_14009E190 & 0x200) == qword_14009E190 )
      {
        LOWORD(v136) = v19->FileName.Length;
        v143 = "onecore\\base\\fs\\unionfs\\sys\\create.cpp";
        LODWORD(v137) = 176;
        v144[0] = "Not supported file ID size.";
        v141 = "UnionFs::UnionFsFilter::PreCreate";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(
          qword_14009E190,
          (unsigned int)qword_140096180,
          v20,
          v17,
          (__int64)v144,
          (__int64)&v141,
          (__int64)&v143,
          (__int64)&v137,
          (__int64)&v136);
      }
LABEL_26:
      if ( Context )
        FltReleaseContext(Context);
LABEL_145:
      if ( v132 )
        PsDereferenceSiloContext(v132);
      v62 = FLT_PREOP_SUCCESS_NO_CALLBACK;
      goto LABEL_312;
    }
    Buffer = v19->FileName.Buffer;
    if ( (_WORD)v20 != 16 )
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
      goto LABEL_26;
    }
    v22 = Context;
    v139 = *(struct _UNICODE_STRING *)Buffer;
    v23 = (__int128 *)UnionFs::UfsFileID::UfsFileID(v144, &v139, Context, v134);
  }
  else
  {
    v24 = v19->FileName.Buffer;
    if ( (_WORD)v20 != 8 )
      v24 = (_QWORD *)((char *)v24 + 2);
    if ( *v24 == -1 )
      goto LABEL_26;
    v22 = Context;
    v23 = (__int128 *)UnionFs::UfsFileID::UfsFileID((UnionFs::UfsFileID *)v144);
  }
  v25 = v134[0];
  v26 = *v23;
  *(_OWORD *)&v142.m256i_u64[2] = v23[1];
  *(_OWORD *)v142.m256i_i8 = v26;
  if ( !v134[0] )
  {
    if ( v22 )
      FltReleaseContext(v22);
    goto LABEL_143;
  }
  if ( v14 )
  {
    Context = 0;
    *(_QWORD *)&v139.Length = &Context;
    v139.Buffer = 0;
    v27 = *(struct _FLT_FILTER **)UnionFs::g_FilterState;
    LOBYTE(v140) = 1;
    VolumeFromFileObject = FltGetVolumeFromFileObject(v27, v14, (PFLT_VOLUME *)&v139.Buffer);
    if ( (_BYTE)v140 )
    {
      v29 = *(PWSTR **)&v139.Length;
      v30 = v139.Buffer;
      if ( **(_QWORD **)&v139.Length )
        FltObjectDereference(**(PVOID **)&v139.Length);
      *v29 = v30;
    }
    if ( VolumeFromFileObject < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)VolumeFromFileObject,
        (int)v157,
        (struct UnionFs::StackEventTracer *)0x5FB000200C8LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
        "API: FltGetVolumeFromFileObject",
        (const char *)v127);
      a1->IoStatus.Status = VolumeFromFileObject;
      a1->IoStatus.Information = 0;
      goto LABEL_77;
    }
    v141 = 0;
    *(_QWORD *)&v139.Length = &v141;
    v139.Buffer = 0;
    LOBYTE(v140) = 1;
    FsFltWil::AcquirePushLockShared(v144, (char *)v25 + 72);
    v32 = (__int64 *)*((_QWORD *)v25 + 6);
    v33 = (volatile signed __int32 *)v32[1];
    v34 = *v32;
    if ( v33 )
      _InterlockedIncrement(v33 + 2);
    if ( v144[0] )
      FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)v144[0], v31);
    VolumeFromInstance = FltGetVolumeFromInstance(**(PFLT_INSTANCE **)(v34 + 8), (PFLT_VOLUME *)&v139.Buffer);
    if ( v33 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v33);
    if ( (_BYTE)v140 )
    {
      v36 = *(PWSTR **)&v139.Length;
      v37 = v139.Buffer;
      if ( **(_QWORD **)&v139.Length )
        FltObjectDereference(**(PVOID **)&v139.Length);
      *v36 = v37;
      v25 = v134[0];
    }
    if ( VolumeFromInstance < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)VolumeFromInstance,
        (int)v157,
        (struct UnionFs::StackEventTracer *)0x38C000200D4LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
        "API: FltGetVolumeFromInstance",
        (const char *)v127);
      a1->IoStatus.Status = VolumeFromInstance;
      a1->IoStatus.Information = 0;
      goto LABEL_75;
    }
    v38 = Context;
    if ( Context != v141 )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000000DLL,
        (int)v157,
        (struct UnionFs::StackEventTracer *)0x5FC000200DCLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
        "ORIGIN: FltGetVolumeFromInstance",
        (const char *)v127);
      a1->IoStatus.Status = -1073741811;
      a1->IoStatus.Information = 0;
LABEL_75:
      if ( v141 )
        FltObjectDereference(v141);
LABEL_77:
      if ( Context )
        FltObjectDereference(Context);
      if ( v22 )
        FltReleaseContext(v22);
      if ( v134[1] )
        utl::_RefCountBase::_DecStrong(v134[1]);
      v39 = v132;
      if ( !v132 )
        goto LABEL_258;
      goto LABEL_257;
    }
    if ( v141 )
    {
      FltObjectDereference(v141);
      v38 = Context;
    }
    if ( v38 )
      FltObjectDereference(v38);
  }
  v139 = 0;
  NameFromFileID = UnionFs::UfsUnionCtx::GetNameFromFileID(
                     v25,
                     (const struct UnionFs::UfsFileID *)&v142,
                     &v139,
                     (struct UnionFs::StackEventTracer *)v157);
  if ( NameFromFileID < 0 )
  {
    a1->IoStatus.Status = NameFromFileID;
    goto LABEL_91;
  }
  v41 = IoReplaceFileObjectName(a2->FileObject, v139.Buffer, v139.Length);
  if ( v41 >= 0 )
  {
    a1->Iopb->Parameters.Create.Options &= ~0x2000u;
    FltSetCallbackDataDirty(a1);
    if ( v22 )
      FltReleaseContext(v22);
    goto LABEL_99;
  }
  UnionFs::ProcessTraceStatusFromApi(
    (UnionFs *)(unsigned int)v41,
    (int)v157,
    (struct UnionFs::StackEventTracer *)0x5DE000200F4LL,
    (unsigned __int64)"UnionFs::UnionFsFilter::PreCreate",
    "API: IoReplaceFileObjectName",
    (const char *)v127);
  a1->IoStatus.Status = v41;
LABEL_91:
  a1->IoStatus.Information = 0;
  if ( v22 )
    FltReleaseContext(v22);
LABEL_93:
  if ( v134[1] )
    utl::_RefCountBase::_DecStrong(v134[1]);
LABEL_8:
  v10 = v132;
  if ( v132 )
LABEL_332:
    PsDereferenceSiloContext(v10);
LABEL_333:
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v157);
  return 4;
}

```

## disassembly

```asm
0x140011e00  mov     [rsp-8+arg_18], rbx
0x140011e05  push    rbp
0x140011e06  push    rsi
0x140011e07  push    rdi
0x140011e08  push    r12
0x140011e0a  push    r13
0x140011e0c  push    r14
0x140011e0e  push    r15
0x140011e10  lea     rbp, [rsp-480h]
0x140011e18  sub     rsp, 580h
0x140011e1f  mov     rax, cs:__security_cookie
0x140011e26  xor     rax, rsp
0x140011e29  mov     [rbp+4B0h+var_40], rax
0x140011e30  xor     r12d, r12d
0x140011e33  mov     [rbp+4B0h+var_4A0], rdx
0x140011e37  mov     [r8], r12
0x140011e3a  mov     r13, rdx
0x140011e3d  mov     rdx, [rcx+10h]
0x140011e41  mov     rsi, rcx
0x140011e44  mov     [rbp+4B0h+var_4C8], r8
0x140011e48  cmp     [rdx+4], r12b
0x140011e4c  jnz     short loc_140011E6B
0x140011e4e  mov     rax, [rdx+8]
0x140011e52  test    dword ptr [rax+50h], 400000h
0x140011e59  jnz     short loc_140011E61
0x140011e5b  test    byte ptr [rdx+6], 2
0x140011e5f  jz      short loc_140011E6B
0x140011e61  mov     eax, 1
0x140011e66  jmp     loc_1400136D6
0x140011e6b  mov     r8, rsi; struct _FLT_CALLBACK_DATA *
0x140011e6e  lea     rcx, [rbp+4B0h+var_330]; this
0x140011e75  mov     rdx, 0CF0002002Ch; unsigned __int64
0x140011e7f  call    ??0StackEventTracer@UnionFs@@QEAA@_KPEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64,_FLT_CALLBACK_DATA const *)
0x140011e84  mov     rdx, [r13+20h]
0x140011e88  lea     rax, [rsp+5B0h+var_558]
0x140011e8d  mov     rcx, [r13+18h]
0x140011e91  lea     r9, [rbp+4B0h+var_330]
0x140011e98  lea     r8, [rbp+4B0h+var_530.Thread]
0x140011e9c  mov     [rsp+5B0h+var_590], rax
0x140011ea1  mov     [rsp+5B0h+var_558], r12
0x140011ea6  mov     [rbp+4B0h+var_530.Thread], r12
0x140011eaa  call    ?GetMappingTableForFileObject@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@PEAPEAVUfsScratchMappingTable@2@AEAVStackEventTracer@2@PEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@@Z; UnionFs::Utils::GetMappingTableForFileObject(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::UfsScratchMappingTable * *,UnionFs::StackEventTracer &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> *)
0x140011eaf  mov     ebx, eax
0x140011eb1  mov     r14d, 4
0x140011eb7  test    eax, eax
0x140011eb9  jns     short loc_140011F00
0x140011ebb  lea     rax, aPushGettingFil; "PUSH: Getting FILE_OBJECT silo"
0x140011ec2  mov     r8, 2AE0002003Fh; struct UnionFs::StackEventTracer *
0x140011ecc  lea     r9, aUnionfsUnionfs_30; "UnionFs::UnionFsFilter::PreCreate"
0x140011ed3  mov     [rsp+5B0h+var_590], rax; char *
0x140011ed8  lea     rdx, [rbp+4B0h+var_330]; int
0x140011edf  mov     ecx, ebx; this
0x140011ee1  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140011ee6  mov     [rsi+18h], ebx
0x140011ee9  mov     [rsi+20h], r12
0x140011eed  mov     rcx, [rsp+5B0h+var_558]
0x140011ef2  test    rcx, rcx
0x140011ef5  jz      loc_1400136C5
0x140011efb  jmp     loc_1400136B9
0x140011f00  cmp     [rbp+4B0h+var_530.Thread], r12
0x140011f04  jz      loc_14001283A
0x140011f0a  mov     rax, [rsi+10h]
0x140011f0e  xorps   xmm0, xmm0
0x140011f11  movdqu  xmmword ptr [rsp+5B0h+var_548], xmm0
0x140011f17  mov     r15d, 8
0x140011f1d  mov     edx, [rax+20h]
0x140011f20  mov     ecx, edx
0x140011f22  and     ecx, 2000h
0x140011f28  setnz   byte ptr [rbp+4B0h+var_530.Flags]
0x140011f2c  cmp     [rax+4], r12b
0x140011f30  jnz     loc_140012502
0x140011f36  test    ecx, ecx
0x140011f38  jz      loc_140012502
0x140011f3e  bt      edx, 0Ch
0x140011f42  jnb     short loc_140011F7C
0x140011f44  lea     rax, aOriginOpenByFi; "ORIGIN: Open by file ID and delete on c"...
0x140011f4b  mov     edi, 0C000000Dh
0x140011f50  mov     ecx, edi; this
0x140011f52  mov     [rsp+5B0h+var_590], rax; char *
0x140011f57  lea     r9, aUnionfsUnionfs_30; "UnionFs::UnionFsFilter::PreCreate"
0x140011f5e  mov     r8, 5E10002005Ch; struct UnionFs::StackEventTracer *
0x140011f68  lea     rdx, [rbp+4B0h+var_330]; int
0x140011f6f  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140011f74  mov     [rsi+18h], edi
0x140011f77  jmp     loc_140011EE9
0x140011f7c  mov     rax, [r13+20h]
0x140011f80  mov     rdi, [rax+40h]
0x140011f84  test    rdi, rdi
0x140011f87  jz      short loc_140011F8D
0x140011f89  mov     [rax+40h], r12
0x140011f8d  mov     rcx, [r13+18h]; Instance
0x140011f91  lea     r9, [rbp+4B0h+var_330]
0x140011f98  lea     r8, [rsp+5B0h+Context]
0x140011f9d  mov     [rsp+5B0h+Context], r12
0x140011fa2  xor     edx, edx
0x140011fa4  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FLT_INSTANCE const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140011fa9  mov     ebx, eax
0x140011fab  test    eax, eax
0x140011fad  jns     short loc_140012000
0x140011faf  lea     rax, aPushGettingIns_0; "PUSH: Getting instance context"
0x140011fb6  mov     r8, 38A00020071h; struct UnionFs::StackEventTracer *
0x140011fc0  lea     r9, aUnionfsUnionfs_30; "UnionFs::UnionFsFilter::PreCreate"
0x140011fc7  mov     [rsp+5B0h+var_590], rax; char *
0x140011fcc  lea     rdx, [rbp+4B0h+var_330]; int
0x140011fd3  mov     ecx, ebx; this
0x140011fd5  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140011fda  mov     rcx, [rsp+5B0h+Context]; Context
0x140011fdf  mov     [rsi+18h], ebx
0x140011fe2  mov     [rsi+20h], r12
0x140011fe6  test    rcx, rcx
0x140011fe9  jz      loc_140011EED
0x140011fef  call    cs:__imp_FltReleaseContext
0x140011ff6  nop     dword ptr [rax+rax+00h]
0x140011ffb  jmp     loc_140011EED
0x140012000  mov     rdx, [r13+20h]
0x140012004  mov     ecx, 0FFFDh
0x140012009  movzx   r8d, word ptr [rdx+58h]
0x14001200e  movzx   eax, r8w
0x140012012  sub     ax, r15w
0x140012016  test    cx, ax
0x140012019  jz      loc_14001216D
0x14001201f  lea     eax, [r8-10h]
0x140012023  test    cx, ax
0x140012026  jz      loc_1400120E3
0x14001202c  mov     eax, cs:dword_14009E178
0x140012032  cmp     eax, r14d
0x140012035  jbe     loc_1400120C4
0x14001203b  mov     rcx, cs:qword_14009E190
0x140012042  mov     edx, 200h
0x140012047  mov     rax, cs:qword_14009E188
0x14001204e  test    rdx, rax
0x140012051  jz      short loc_1400120C4
0x140012053  mov     rax, rcx
0x140012056  and     rax, rdx
0x140012059  cmp     rax, rcx
0x14001205c  jnz     short loc_1400120C4
0x14001205e  lea     rax, aOnecoreBaseFsU_14; "onecore\\base\\fs\\unionfs\\sys\\create"...
0x140012065  mov     word ptr [rbp+4B0h+var_530.Flags], r8w
0x14001206a  mov     [rbp+4B0h+var_4C8], rax
0x14001206e  lea     r14, aUnionfsUnionfs_30; "UnionFs::UnionFsFilter::PreCreate"
0x140012075  lea     rax, aNotSupportedFi; "Not supported file ID size."
0x14001207c  mov     dword ptr [rbp+4B0h+var_530.Thread], 0B0h
0x140012083  mov     [rbp+4B0h+var_4C0], rax
0x140012087  lea     rdx, qword_140096180
0x14001208e  lea     rax, [rbp+4B0h+var_530]
0x140012092  mov     qword ptr [rbp+4B0h+var_530.30h+10h], r14
0x140012096  mov     [rsp+5B0h+var_570], rax
0x14001209b  lea     rax, [rbp+4B0h+var_530.Thread]
0x14001209f  mov     [rsp+5B0h+var_578], rax
0x1400120a4  lea     rax, [rbp+4B0h+var_4C8]
0x1400120a8  mov     [rsp+5B0h+var_580], rax
0x1400120ad  lea     rax, [rbp+4B0h+var_530.30h+10h]
0x1400120b1  mov     [rsp+5B0h+var_588], rax
0x1400120b6  lea     rax, [rbp+4B0h+var_4C0]
0x1400120ba  mov     [rsp+5B0h+var_590], rax
0x1400120bf  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &)
0x1400120c4  mov     rcx, [rsp+5B0h+Context]; Context
0x1400120c9  test    rcx, rcx
0x1400120cc  jz      loc_14001283A
0x1400120d2  call    cs:__imp_FltReleaseContext
0x1400120d9  nop     dword ptr [rax+rax+00h]
0x1400120de  jmp     loc_14001283A
0x1400120e3  mov     rcx, [rdx+60h]
0x1400120e7  cmp     r8w, 10h
0x1400120ec  lea     rax, [rcx+2]
0x1400120f0  cmovnz  rcx, rax
0x1400120f4  mov     al, 0FFh
0x1400120f6  cmp     [rcx], al
0x1400120f8  jnz     short loc_140012149
0x1400120fa  cmp     [rcx+1], al
0x1400120fd  jnz     short loc_140012149
0x1400120ff  cmp     [rcx+2], al
0x140012102  jnz     short loc_140012149
0x140012104  cmp     [rcx+3], al
0x140012107  jnz     short loc_140012149
0x140012109  cmp     [rcx+4], al
0x14001210c  jnz     short loc_140012149
0x14001210e  cmp     [rcx+5], al
0x140012111  jnz     short loc_140012149
0x140012113  cmp     [rcx+6], al
0x140012116  jnz     short loc_140012149
0x140012118  cmp     [rcx+7], al
0x14001211b  jnz     short loc_140012149
0x14001211d  cmp     [rcx+8], al
0x140012120  jnz     short loc_140012149
0x140012122  cmp     [rcx+9], al
0x140012125  jnz     short loc_140012149
0x140012127  cmp     [rcx+0Ah], al
0x14001212a  jnz     short loc_140012149
0x14001212c  cmp     [rcx+0Bh], al
0x14001212f  jnz     short loc_140012149
0x140012131  cmp     [rcx+0Ch], al
0x140012134  jnz     short loc_140012149
0x140012136  cmp     [rcx+0Dh], al
0x140012139  jnz     short loc_140012149
0x14001213b  cmp     [rcx+0Eh], al
0x14001213e  jnz     short loc_140012149
0x140012140  cmp     [rcx+0Fh], al
0x140012143  jz      loc_1400120C4
0x140012149  movups  xmm0, xmmword ptr [rcx]
0x14001214c  mov     rbx, [rsp+5B0h+Context]
0x140012151  lea     r9, [rsp+5B0h+var_548]
0x140012156  mov     r8, rbx
0x140012159  lea     rdx, [rbp+4B0h+var_530.IoStatus.Information]
0x14001215d  lea     rcx, [rbp+4B0h+var_4C0]
0x140012161  movdqu  xmmword ptr [rbp+4B0h+var_530.IoStatus.Information], xmm0
0x140012166  call    ??0UfsFileID@UnionFs@@QEAA@U_FILE_ID_128@@AEBVUfsInstanceCtx@1@AEAV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@@Z; UnionFs::UfsFileID::UfsFileID(_FILE_ID_128,UnionFs::UfsInstanceCtx const &,utl::shared_ptr<UnionFs::UfsUnionCtx> &)
0x14001216b  jmp     short loc_1400121A0
0x14001216d  mov     rdx, [rdx+60h]
0x140012171  cmp     r8w, r15w
0x140012175  lea     rax, [rdx+2]
0x140012179  cmovnz  rdx, rax
0x14001217d  mov     rdx, [rdx]
0x140012180  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x140012184  jz      loc_1400120C4
0x14001218a  mov     rbx, [rsp+5B0h+Context]
0x14001218f  lea     r9, [rsp+5B0h+var_548]
0x140012194  mov     r8, rbx
0x140012197  lea     rcx, [rbp+4B0h+var_4C0]; this
0x14001219b  call    ??0UfsFileID@UnionFs@@QEAA@T_LARGE_INTEGER@@AEBVUfsInstanceCtx@1@AEAV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@@Z; UnionFs::UfsFileID::UfsFileID(_LARGE_INTEGER,UnionFs::UfsInstanceCtx const &,utl::shared_ptr<UnionFs::UfsUnionCtx> &)
0x1400121a0  movups  xmm1, xmmword ptr [rax+10h]
0x1400121a4  mov     r12, [rsp+5B0h+var_548]
0x1400121a9  xor     r15d, r15d
0x1400121ac  movups  xmm0, xmmword ptr [rax]
0x1400121af  movups  xmmword ptr [rbp+4B0h+P], xmm1
0x1400121b3  movups  xmmword ptr [rbp+4B0h+var_530.30h+18h], xmm0
0x1400121b7  test    r12, r12
0x1400121ba  jnz     short loc_1400121D9
0x1400121bc  test    rbx, rbx
0x1400121bf  jz      loc_14001282B
0x1400121c5  mov     rcx, rbx; Context
0x1400121c8  call    cs:__imp_FltReleaseContext
0x1400121cf  nop     dword ptr [rax+rax+00h]
0x1400121d4  jmp     loc_14001282B
0x1400121d9  test    rdi, rdi
0x1400121dc  jz      loc_140012430
0x1400121e2  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400121e9  lea     rax, [rsp+5B0h+Context]
0x1400121ee  lea     r8, [rbp+4B0h+var_530.TagData]; RetVolume
0x1400121f2  mov     [rsp+5B0h+Context], r15
0x1400121f7  mov     rdx, rdi; FileObject
0x1400121fa  mov     [rbp+4B0h+var_530.IoStatus.Information], rax
0x1400121fe  mov     [rbp+4B0h+var_530.TagData], r15
0x140012202  mov     rcx, [rcx]; Filter
0x140012205  mov     byte ptr [rbp+4B0h+var_530.30h], 1
0x140012209  call    cs:__imp_FltGetVolumeFromFileObject
0x140012210  nop     dword ptr [rax+rax+00h]
0x140012215  mov     edi, eax
0x140012217  cmp     byte ptr [rbp+4B0h+var_530.30h], r15b
0x14001221b  jz      short loc_140012245
0x14001221d  mov     r14, [rbp+4B0h+var_530.IoStatus.Information]
0x140012221  mov     r15, [rbp+4B0h+var_530.TagData]
0x140012225  mov     rcx, [r14]; FltObject
0x140012228  test    rcx, rcx
0x14001222b  jz      short loc_140012239
0x14001222d  call    cs:__imp_FltObjectDereference
0x140012234  nop     dword ptr [rax+rax+00h]
0x140012239  mov     [r14], r15
0x14001223c  mov     r14d, 4
0x140012242  xor     r15d, r15d
0x140012245  test    edi, edi
0x140012247  jns     short loc_140012280
0x140012249  lea     rax, aApiFltgetvolum; "API: FltGetVolumeFromFileObject"
0x140012250  mov     r8, 5FB000200C8h; struct UnionFs::StackEventTracer *
0x14001225a  lea     r9, aUnionfsUnionfs_30; "UnionFs::UnionFsFilter::PreCreate"
0x140012261  mov     [rsp+5B0h+var_590], rax; char *
0x140012266  lea     rdx, [rbp+4B0h+var_330]; int
0x14001226d  mov     ecx, edi; this
0x14001226f  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140012274  mov     [rsi+18h], edi
0x140012277  mov     [rsi+20h], r15
0x14001227b  jmp     loc_1400123B7
0x140012280  lea     rax, [rbp+4B0h+var_530.30h+10h]
0x140012284  mov     qword ptr [rbp+4B0h+var_530.30h+10h], r15
0x140012288  lea     rdx, [r12+48h]
0x14001228d  mov     [rbp+4B0h+var_530.IoStatus.Information], rax
0x140012291  lea     rcx, [rbp+4B0h+var_4C0]
0x140012295  mov     [rbp+4B0h+var_530.TagData], r15
0x140012299  mov     byte ptr [rbp+4B0h+var_530.30h], 1
0x14001229d  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x1400122a2  mov     rax, [r12+30h]
0x1400122a7  mov     rdi, [rax+8]
0x1400122ab  mov     r15, [rax]
0x1400122ae  test    rdi, rdi
0x1400122b1  jz      short loc_1400122B7
0x1400122b3  lock inc dword ptr [rdi+8]
0x1400122b7  mov     rcx, [rbp+4B0h+var_4C0]; this
0x1400122bb  test    rcx, rcx
0x1400122be  jz      short loc_1400122C5
0x1400122c0  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x1400122c5  mov     rcx, [r15+8]
0x1400122c9  lea     rdx, [rbp+4B0h+var_530.TagData]; RetVolume
0x1400122cd  mov     rcx, [rcx]; Instance
0x1400122d0  call    cs:__imp_FltGetVolumeFromInstance
0x1400122d7  nop     dword ptr [rax+rax+00h]
0x1400122dc  mov     r15d, eax
0x1400122df  test    rdi, rdi
0x1400122e2  jz      short loc_1400122EC
0x1400122e4  mov     rcx, rdi; this
0x1400122e7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
  ... truncated ...
```
