# UnionFs::UnionFsFilter::PreCreateFileOpenIf(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,_FLT_PREOP_CALLBACK_STATUS &,UnionFs::CreateContext &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *)

- ea: `0x14001568c`
- end: `0x1400173e7`
- name: `?PreCreateFileOpenIf@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAW4_FLT_PREOP_CALLBACK_STATUS@@AEAUCreateContext@2@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@@Z`
- size: `7515`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, enum _FLT_PREOP_CALLBACK_STATUS *, struct UnionFs::CreateContext *, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsSiloCtx *)`
- caller_count: `1`
- callee_count: `50`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140011e20`

## callees

- `0x140001008`
- `0x140001d38`
- `0x140002354`
- `0x1400055d0`
- `0x140005d5c`
- `0x140006168`
- `0x140009ab0`
- `0x14000a798`
- `0x14000ac98`
- `0x14000c1dc`
- `0x14000efa0`
- `0x14000f514`
- `0x14000f81c`
- `0x140010168`
- `0x140010ba8`
- `0x140010db8`
- `0x140010f28`
- `0x140011030`
- `0x140011168`
- `0x1400111b8`
- `0x1400114e4`
- `0x14001568c`
- `0x14003c854`
- `0x14003cea8`
- `0x140040110`
- `0x140041650`
- `0x140041b30`
- `0x140043a64`
- `0x140043afc`
- `0x140044074`
- `0x140056c44`
- `0x140056c7c`
- `0x14005913c`
- `0x140061058`
- `0x14006127c`
- `0x14006989c`
- `0x14006be98`
- `0x14006f9ec`
- `0x14007018c`
- `0x1400704d4`
- `0x140077910`
- `0x14007862c`
- `0x140079d44`
- `0x140079d8c`
- `0x140079f68`
- `0x14007a0c0`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bbd0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140015936`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015f7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016504`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001652c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016564`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001658c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400165e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001660f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016bb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016bd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016c3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016c60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016d60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016df9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f15`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017044`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001714a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400171f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017325`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400173a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015936`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015f7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016504`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001652c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016564`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001658c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400165e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001660f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016bb1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016bd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016c3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016c60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016d60`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016df9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f15`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017044`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001714a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400171f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017325`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400173a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001585a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015a12`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015bba`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015c10`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015ca3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015d8b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015de1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015e17`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015e8f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400160e7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001706b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001585a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015a12`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015bba`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015c10`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015ca3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015d8b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015de1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015e17`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015e8f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400160e7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001706b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015866`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015a1e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015bc6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015c1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015caf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015d97`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015ded`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015e23`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015e9b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400160f3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140017077`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015866`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015a1e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015bc6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015c1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015caf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015d97`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015ded`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015e23`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015e9b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400160f3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140017077`
- `FLTMGR!FltReferenceContext` at `0x1400159c3`
- `FLTMGR!FltReferenceContext` at `0x1400159c3`
- `FLTMGR!FltReleaseContext` at `0x140015c30`
- `FLTMGR!FltReleaseContext` at `0x140015cc3`
- `FLTMGR!FltReleaseContext` at `0x140015db0`
- `FLTMGR!FltReleaseContext` at `0x140015e3f`
- `FLTMGR!FltReleaseContext` at `0x140015ef7`
- `FLTMGR!FltReleaseContext` at `0x140015c30`
- `FLTMGR!FltReleaseContext` at `0x140015cc3`
- `FLTMGR!FltReleaseContext` at `0x140015db0`
- `FLTMGR!FltReleaseContext` at `0x140015e3f`
- `FLTMGR!FltReleaseContext` at `0x140015ef7`

## string_xrefs

- `0x140015703`: `Checking requested access on non-create`
- `0x1400159fd`: `Checking requested access on non-create`
- `0x140015b48`: `onecore\base\fs\unionfs\sys\create.cpp`
- `0x140016872`: `onecore\base\fs\unionfs\sys\create.cpp`
- `0x1400157a2`: `PUSH: Cache lookup`
- `0x140015839`: `results.CacheEntry->GetOriginalScratchPath()`
- `0x140015f2c`: `PUSH: Allocating scratch path for layer lookup`
- `0x140015d5b`: `PUSH: Oplock and share access check`
- `0x140016686`: `PUSH: Preparing for scratch create`
- `0x14001597d`: `PUSH: Completing create with cached reparse data`
- `0x140015c73`: `PUSH: Checking caller access from cache`
- `0x140016309`: `!results.CacheEntry`
- `0x140016b2d`: `PUSH: Allocating cache entry`
- `0x140016d0e`: `PUSH: Inserting path cache payload`
- `0x1400158fa`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x14001598e`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140015b5a`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140015bf0`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140015c89`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140015d6c`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140015e6b`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x14001605b`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140016178`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140016272`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140016452`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x1400164cf`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140016697`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x14001671d`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140016b3e`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140016d24`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140016fcd`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140016880`: `FileOpenIfCowNotInCache`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PreCreateFileOpenIf(
        UnionFs::UnionFsFilter *this,
        struct _FLT_CALLBACK_DATA *a2,
        struct _FLT_RELATED_OBJECTS *a3,
        enum _FLT_PREOP_CALLBACK_STATUS *a4,
        struct UnionFs::CreateContext *a5,
        struct _REPARSE_DATA_BUFFER *a6,
        const struct UnionFs::UfsSiloCtx *a7)
{
  enum _FLT_PREOP_CALLBACK_STATUS *v8; // r14
  PFILE_OBJECT FileObject; // rax
  ULONG Flags; // ebx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  unsigned int v13; // ebx
  int v14; // ecx
  __int64 v15; // rax
  __int64 v16; // rcx
  int IsFileCowable; // edi
  struct UnionFs::StackEventTracer *v18; // r9
  const char *v19; // rax
  __int64 v20; // r8
  struct _ERESOURCE *v21; // rcx
  utl::_RefCountBase *v22; // rcx
  UnionFs::Rtl *v23; // rcx
  struct UnionFs::StackEventTracer *v24; // r9
  const char *v25; // rax
  __int64 v26; // r8
  struct _UNICODE_STRING *v27; // rdx
  struct _UNICODE_STRING *v28; // rbx
  utl::_RefCountBase *v29; // rdi
  struct _FLT_CALLBACK_DATA *v30; // rdx
  _QWORD *v31; // rdi
  const struct _FLT_RELATED_OBJECTS *v32; // rbx
  PFLT_IO_PARAMETER_BLOCK v33; // rax
  __int64 v34; // rbx
  struct _FILE_OBJECT *v35; // r14
  unsigned __int64 *v36; // rdx
  __int64 v37; // rax
  volatile signed __int32 *v38; // rbx
  int v39; // r14d
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  struct _ERESOURCE *v43; // rcx
  int v45; // eax
  __int64 v46; // rax
  __int64 v47; // rcx
  struct _ERESOURCE *v48; // rcx
  PFLT_CONTEXT v49; // rcx
  struct _ERESOURCE *v50; // rcx
  enum _FLT_PREOP_CALLBACK_STATUS *v51; // rax
  PVOID v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rbx
  int v55; // r8d
  int v56; // ebx
  utl::_RefCountBase *v57; // rcx
  __int64 v58; // r8
  __int64 v59; // rax
  struct _ERESOURCE *v60; // rcx
  UnionFs::UfsUnionCtx *v61; // rcx
  volatile signed __int32 *v62; // rbx
  const struct UnionFs::UfsLayerCtx *v63; // rdx
  struct _ERESOURCE *v64; // rcx
  utl::_RefCountBase *v65; // rax
  utl::_RefCountBase *v66; // rcx
  PFLT_INSTANCE Instance; // r9
  volatile signed __int32 *v68; // rbx
  __int64 v69; // r8
  __int64 v70; // rdx
  struct _UNICODE_STRING *v71; // rdx
  struct _UNICODE_STRING *v72; // rdx
  __int64 v73; // r8
  USHORT SubstituteNameLength; // ax
  USHORT v75; // ax
  __int64 v76; // rdx
  __int64 v77; // rcx
  __int16 *v78; // rdi
  __int64 v79; // rcx
  int v80; // eax
  struct _UNICODE_STRING *v81; // rdx
  unsigned int *v82; // r9
  int v83; // r8d
  struct _UNICODE_STRING *v84; // rdx
  struct _UNICODE_STRING *v85; // rbx
  utl::_RefCountBase *v86; // rcx
  struct _UNICODE_STRING *v87; // rbx
  bool v88; // zf
  utl::_RefCountBase *v89; // rcx
  __int16 v90; // ax
  enum _FLT_PREOP_CALLBACK_STATUS *v91; // rax
  struct _UNICODE_STRING *v92; // rbx
  utl::_RefCountBase *v93; // rcx
  volatile signed __int32 *v94; // r14
  PVOID v95; // rdx
  int v96; // eax
  int v97; // r8d
  int v98; // r9d
  PFLT_IO_PARAMETER_BLOCK v99; // rdx
  int v100; // ecx
  struct _UNICODE_STRING *v101; // rax
  UNICODE_STRING *p_Source; // rax
  struct _UNICODE_STRING *v103; // rdx
  UnionFs::UfsUnionCtx *v104; // rcx
  _DWORD *v105; // rcx
  struct _UNICODE_STRING *v106; // rcx
  const UNICODE_STRING *v107; // r9
  int v108; // eax
  int inited; // r13d
  struct _UNICODE_STRING *v110; // rdx
  struct _UNICODE_STRING *v111; // rbx
  utl::_RefCountBase *v112; // rcx
  struct _UNICODE_STRING *v113; // rdx
  struct _UNICODE_STRING *v114; // rbx
  utl::_RefCountBase *v115; // rcx
  UnionFs::UfsPathCachePayload *v116; // r13
  __int64 v117; // rax
  __int64 v118; // rcx
  struct _FLT_RELATED_OBJECTS *v119; // rbx
  int inserted; // eax
  struct _UNICODE_STRING *v121; // rdx
  struct _UNICODE_STRING *v122; // rdx
  struct _UNICODE_STRING *v123; // rdx
  struct _FILE_OBJECT *v124; // rbx
  int v125; // eax
  struct _UNICODE_STRING *v126; // rdx
  struct _UNICODE_STRING *v127; // rbx
  utl::_RefCountBase *v128; // rcx
  utl::_RefCountBase *v129; // rcx
  struct _ERESOURCE *v130; // rcx
  enum _FLT_PREOP_CALLBACK_STATUS *v131; // rax
  utl::_RefCountBase *v132; // rcx
  int v133; // eax
  utl::_RefCountBase *v134; // rcx
  __int64 v135; // r8
  __int64 v136; // rax
  struct _UNICODE_STRING *v137; // rdx
  int v138; // r15d
  struct _UNICODE_STRING *v139; // rdx
  utl::_RefCountBase *v140; // rcx
  utl::_RefCountBase *v141; // rcx
  struct UnionFs::StackEventTracer *v142; // [rsp+20h] [rbp-F0h]
  char *v143; // [rsp+28h] [rbp-E8h]
  const char *v144; // [rsp+28h] [rbp-E8h]
  const char *v145; // [rsp+28h] [rbp-E8h]
  const char *v146; // [rsp+28h] [rbp-E8h]
  const char *v147; // [rsp+28h] [rbp-E8h]
  const char *v148; // [rsp+28h] [rbp-E8h]
  const char *v149; // [rsp+28h] [rbp-E8h]
  char *v150; // [rsp+28h] [rbp-E8h]
  const char *v151; // [rsp+28h] [rbp-E8h]
  const char *v152; // [rsp+28h] [rbp-E8h]
  const char *v153; // [rsp+28h] [rbp-E8h]
  bool v154; // [rsp+90h] [rbp-80h] BYREF
  char v155; // [rsp+91h] [rbp-7Fh] BYREF
  PFLT_CONTEXT Context; // [rsp+98h] [rbp-78h] BYREF
  int v157; // [rsp+A0h] [rbp-70h] BYREF
  PVOID P; // [rsp+A8h] [rbp-68h] BYREF
  PVOID v159; // [rsp+B0h] [rbp-60h] BYREF
  PVOID v160; // [rsp+B8h] [rbp-58h] BYREF
  UnionFs::UfsPathCachePayload *v161; // [rsp+C0h] [rbp-50h] BYREF
  struct _QUERY_ON_CREATE_ECP_CONTEXT *v162; // [rsp+C8h] [rbp-48h] BYREF
  enum _FLT_PREOP_CALLBACK_STATUS *v163; // [rsp+D0h] [rbp-40h] BYREF
  __int64 v164; // [rsp+D8h] [rbp-38h] BYREF
  utl::_RefCountBase *v165; // [rsp+E0h] [rbp-30h]
  char v166[16]; // [rsp+E8h] [rbp-28h] BYREF
  PVOID v167; // [rsp+F8h] [rbp-18h]
  utl::_RefCountBase *v168; // [rsp+100h] [rbp-10h] BYREF
  struct _UNICODE_STRING v169; // [rsp+108h] [rbp-8h] BYREF
  __int128 v170; // [rsp+120h] [rbp+10h] BYREF
  utl::_RefCountBase *v171[2]; // [rsp+130h] [rbp+20h] BYREF
  PERESOURCE Resource; // [rsp+140h] [rbp+30h]
  __int64 v173; // [rsp+148h] [rbp+38h]
  __int128 v174; // [rsp+150h] [rbp+40h]
  struct _FLT_RELATED_OBJECTS *v175; // [rsp+160h] [rbp+50h] BYREF
  UNICODE_STRING Source; // [rsp+168h] [rbp+58h] BYREF
  char v177[8]; // [rsp+178h] [rbp+68h] BYREF
  PERESOURCE v178[2]; // [rsp+180h] [rbp+70h]
  utl::_RefCountBase *v179[2]; // [rsp+190h] [rbp+80h]
  __int64 v180; // [rsp+1A0h] [rbp+90h]
  int v181; // [rsp+1A8h] [rbp+98h]
  int v182; // [rsp+1B0h] [rbp+A0h] BYREF
  char v183[8]; // [rsp+1B8h] [rbp+A8h] BYREF
  volatile signed __int32 *v184; // [rsp+1C0h] [rbp+B0h]
  struct _UNICODE_STRING *v185; // [rsp+1C8h] [rbp+B8h] BYREF
  UNICODE_STRING *v186; // [rsp+1D0h] [rbp+C0h] BYREF
  const char *v187; // [rsp+1D8h] [rbp+C8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+1E0h] [rbp+D0h] BYREF
  char *v189; // [rsp+1F0h] [rbp+E0h]
  char v190; // [rsp+1F8h] [rbp+E8h]
  PWSTR *p_Buffer; // [rsp+250h] [rbp+140h]
  char v192[8]; // [rsp+260h] [rbp+150h] BYREF
  __int128 v193; // [rsp+268h] [rbp+158h]
  utl::_RefCountBase *v194[2]; // [rsp+278h] [rbp+168h]
  __int64 v195; // [rsp+288h] [rbp+178h]
  int v196; // [rsp+290h] [rbp+180h]
  struct _UNICODE_STRING v197; // [rsp+2A0h] [rbp+190h] BYREF
  char v198; // [rsp+2B0h] [rbp+1A0h]
  _BYTE v199[80]; // [rsp+2E0h] [rbp+1D0h] BYREF
  _BYTE v200[752]; // [rsp+330h] [rbp+220h] BYREF

  v8 = a4;
  *a4 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
  v161 = a7;
  FileObject = a3->FileObject;
  v163 = a4;
  v175 = a3;
  Flags = FileObject->Flags;
  Iopb = a2->Iopb;
  v13 = (Flags & 0x20000) == 0;
  if ( Iopb->MajorFunction )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("Checking requested access on non-create");
  }
  else
  {
    v14 = *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
    if ( (v14 & 0x10D0106) != 0 || (v14 & 0x2000000) != 0 )
      v13 |= 8u;
  }
  Resource = 0;
  v170 = 0;
  *(_OWORD *)v171 = 0;
  v173 = 0;
  LODWORD(v170) = _mm_cvtsi128_si32((__m128i)0LL) | 3;
  v15 = *((_QWORD *)a5 + 1);
  v174 = 0;
  if ( *(_DWORD *)(v15 + 28) == 2 )
    v16 = *(_QWORD *)(*(_QWORD *)(v15 + 32) + 16LL);
  else
    v16 = *((_QWORD *)UnionFs::g_FilterState + 10);
  v143 = (char *)a6;
  IsFileCowable = UnionFs::UfsPathCache::LookupEntry(v16, a3->Instance, *(_QWORD *)a5, v13, &v170);
  if ( IsFileCowable < 0 )
  {
    v19 = "PUSH: Cache lookup";
    v20 = 0x11F00020AFALL;
LABEL_39:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)IsFileCowable,
      (int)a6,
      (struct UnionFs::StackEventTracer *)v20,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
      v19,
      v143);
    goto LABEL_69;
  }
  v154 = 0;
  if ( !DWORD1(v170) )
    goto LABEL_27;
  if ( (BYTE8(v170) & 4) != 0 )
  {
    if ( DWORD1(v170) == 1 )
    {
      UnionFs::CreateContext::OverwriteTombstone(a5, v171, 0);
    }
    else
    {
      a2->IoStatus.Status = -1073741766;
      a2->IoStatus.Information = 0;
      *v8 = FLT_PREOP_COMPLETE;
    }
    goto LABEL_18;
  }
  if ( (_DWORD)v173 == 1 )
  {
    **((_DWORD **)a5 + 20) |= 8u;
LABEL_18:
    IsFileCowable = 0;
    goto LABEL_69;
  }
  if ( *((_WORD *)v171[0] + 84) == 4 )
  {
    if ( !*((_QWORD *)v171[0] + 27) )
      MicrosoftTelemetryAssertTriggeredMsgKM("results.CacheEntry->GetOriginalScratchPath()");
    if ( DWORD1(v170) == 1 )
      goto LABEL_18;
    goto LABEL_23;
  }
  if ( DWORD1(v170) == 1 )
  {
    v29 = v171[0];
    v30 = (struct _FLT_CALLBACK_DATA *)*((_QWORD *)v171[0] + 12);
    if ( v30 && (a2->Iopb->Parameters.Create.Options & 0x200000) == 0 )
    {
      IsFileCowable = UnionFs::Utils::SetReparseDataFromCache(a2, v30, a6, v18);
      if ( IsFileCowable >= 0 )
      {
        a2->IoStatus.Status = 260;
        IsFileCowable = 0;
        *v8 = FLT_PREOP_COMPLETE;
        goto LABEL_69;
      }
      v19 = "PUSH: Completing create with cached reparse data";
      v20 = 0x79200020B4FLL;
      goto LABEL_39;
    }
    FltReferenceContext(*((PFLT_CONTEXT *)v171[0] + 9));
    v31 = (_QWORD *)*((_QWORD *)v29 + 9);
    Context = v31;
    v32 = (const struct _FLT_RELATED_OBJECTS *)v31[4];
    FsFltWil::AcquireResourceExclusive(&P, (char *)v32[2].Instance + 56);
    v33 = a2->Iopb;
    if ( v33->MajorFunction )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Checking requested access on non-create");
    }
    else
    {
      v40 = *(_DWORD *)(v33->Parameters.WMI.ProviderId + 16);
      if ( (v40 & 0x10D0106) != 0 || (v40 & 0x2000000) != 0 )
      {
        if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
        {
          v39 = UnionFs::Utils::BreakBatchAndHOplocks(
                  (UnionFs::Utils *)a2,
                  (struct _FLT_CALLBACK_DATA *)a3,
                  v32,
                  (struct UnionFs::UfsFsContext *)a6,
                  v142);
          if ( v39 == 259 )
          {
            if ( (unsigned int)dword_14009E178 > 4
              && (qword_14009E188 & 0x200200) != 0
              && (qword_14009E190 & 0x200200) == qword_14009E190 )
            {
              v157 = 2941;
              v160 = "onecore\\base\\fs\\unionfs\\sys\\create.cpp";
              v161 = (UnionFs::UfsPathCachePayload *)"UnionFs::UnionFsFilter::PreCreateFileOpenIf";
              Context = "Oplock break";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                qword_14009E190,
                (unsigned int)&byte_1400962F7,
                v41,
                v42,
                (__int64)&Context,
                (__int64)&v161,
                (__int64)&v160,
                (__int64)&v157);
            }
            v43 = (struct _ERESOURCE *)P;
            *v163 = FLT_PREOP_PENDING;
            if ( v43 )
            {
              ExReleaseResourceLite(v43);
              KeLeaveCriticalRegion();
            }
            goto LABEL_99;
          }
          if ( v39 < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v39,
              (int)a6,
              (struct UnionFs::StackEventTracer *)0x6FA00020B84LL,
              (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
              "PUSH: Breaking oplocks",
              (const char *)a6);
            if ( P )
            {
              ExReleaseResourceLite((PERESOURCE)P);
              KeLeaveCriticalRegion();
            }
            goto LABEL_66;
          }
          v8 = v163;
        }
        v45 = UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess(
                v171[0],
                a2,
                (struct UnionFs::StackEventTracer *)a6,
                1);
        v157 = v45;
        if ( v45 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v45,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x56A00020B8FLL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
            "PUSH: Checking caller access from cache",
            (const char *)a6);
          if ( P )
          {
            ExReleaseResourceLite((PERESOURCE)P);
            KeLeaveCriticalRegion();
          }
          if ( v31 )
            FltReleaseContext(v31);
          goto LABEL_76;
        }
        v46 = *(_QWORD *)(a2->Iopb->Parameters.WMI.ProviderId + 8);
        v47 = *(unsigned int *)(v46 + 20);
        if ( (v47 & 0x10D0106) != 0 )
        {
          *(_DWORD *)&v166[8] = *(_DWORD *)(v46 + 24);
          v166[12] = 0;
          *(_WORD *)&v166[13] = 0;
          v166[15] = 0;
          LODWORD(v167) = 0;
          *(_WORD *)((char *)&v167 + 5) = 0;
          HIBYTE(v167) = 0;
          v154 = 0;
          v143 = (char *)v32;
          *(_DWORD *)v166 = v47;
          *(_DWORD *)&v166[4] = 6;
          BYTE4(v167) = 1;
          IsFileCowable = UnionFs::UnionFsFilter::CheckOplockAndShareAccess(v47, a2, a3, &Context, v166);
          if ( IsFileCowable < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)IsFileCowable,
              (int)a6,
              (struct UnionFs::StackEventTracer *)0x6FB00020BB4LL,
              (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
              "PUSH: Oplock and share access check",
              (const char *)v32);
            if ( P )
            {
              ExReleaseResourceLite((PERESOURCE)P);
              KeLeaveCriticalRegion();
            }
            if ( Context )
              FltReleaseContext(Context);
            goto LABEL_69;
          }
          v48 = (struct _ERESOURCE *)P;
          if ( IsFileCowable != 259 )
          {
            v154 = 1;
            if ( P )
            {
              ExReleaseResourceLite((PERESOURCE)P);
              KeLeaveCriticalRegion();
            }
            if ( Context )
              FltReleaseContext(Context);
            goto LABEL_27;
          }
          *v8 = FLT_PREOP_PENDING;
          if ( v48 )
          {
            ExReleaseResourceLite(v48);
            KeLeaveCriticalRegion();
          }
          v49 = Context;
          if ( !Context )
            goto LABEL_18;
LABEL_101:
          FltReleaseContext(v49);
          goto LABEL_18;
        }
      }
    }
    if ( P )
    {
      ExReleaseResourceLite((PERESOURCE)P);
      KeLeaveCriticalRegion();
    }
    v34 = *((_QWORD *)a5 + 1);
    v35 = a3->FileObject;
    v161 = v171[0];
    FsFltWil::AcquirePushLockShared(&v160, v34 + 72);
    v37 = *(_QWORD *)(v34 + 48);
    v38 = *(volatile signed __int32 **)(v37 + 8);
    P = *(PVOID *)v37;
    if ( v38 )
      _InterlockedIncrement(v38 + 2);
    if ( v160 )
      FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)v160, v36);
    LODWORD(v143) = 7;
    v39 = UnionFs::UfsShadowFileObject::SetUp(
            v35,
            a2,
            v161,
            (struct UnionFs::StackEventTracer *)v143,
            (__int64)a5 + 160,
            (struct UnionFs::Utils::CheckOplockHParams *)a6);
    if ( v38 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v38);
    if ( v39 == 259 )
    {
      *v163 = FLT_PREOP_PENDING;
LABEL_99:
      if ( !v31 )
        goto LABEL_18;
      v49 = v31;
      goto LABEL_101;
    }
    if ( v39 >= 0 )
    {
      v50 = Resource;
      Resource = 0;
      if ( v50 )
      {
        ExReleaseResourceLite(v50);
        KeLeaveCriticalRegion();
      }
      UnionFs::UnionFsFilter::HandleQoCEcpCached(
        (UnionFs::UnionFsFilter *)v50,
        a2,
        a3,
        *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
        *((struct UnionFs::UfsUnionCtx **)a5 + 1),
        v171[0],
        (struct UnionFs::StackEventTracer *)a6);
      v51 = v163;
      a2->IoStatus.Status = 0;
      a2->IoStatus.Information = 1;
      *v51 = FLT_PREOP_COMPLETE;
      goto LABEL_99;
    }
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v39,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x23000020BDDLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
      "PUSH: Setting up shadow file object",
      v144);
LABEL_66:
    if ( v31 )
      FltReleaseContext(v31);
    goto LABEL_68;
  }
LABEL_23:
  v21 = Resource;
  Resource = 0;
  if ( v21 )
  {
    ExReleaseResourceLite(v21);
    KeLeaveCriticalRegion();
  }
  v22 = v171[1];
  v171[1] = 0;
  v171[0] = 0;
  if ( v22 )
    utl::_RefCountBase::_DecStrong(v22);
LABEL_27:
  P = 0;
  if ( (_DWORD)v173 != 2 )
    goto LABEL_103;
  v23 = (UnionFs::Rtl *)(*(_QWORD *)a5 + 8LL);
  Source = (UNICODE_STRING)**((_OWORD **)&v174 + 1);
  v169 = *(struct _UNICODE_STRING *)v174;
  IsFileCowable = UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(v23, &v169, &Source, &P, (int)a6);
  if ( IsFileCowable < 0 )
  {
    v25 = "PUSH: Replacing substring";
    v26 = 0x38200020C0ELL;
    goto LABEL_30;
  }
  v52 = P;
  if ( !P )
  {
LABEL_103:
    IsFileCowable = UnionFs::UfsPathName::AllocAndInit(*(_QWORD *)a5, &P, a6);
    if ( IsFileCowable < 0 )
    {
      v25 = "PUSH: Allocating scratch path for layer lookup";
      v26 = 0x39200020C19LL;
LABEL_30:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)IsFileCowable,
        (int)a6,
        (struct UnionFs::StackEventTracer *)v26,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
        v25,
        v143);
      v28 = (struct _UNICODE_STRING *)P;
      if ( P )
      {
        if ( !*((_BYTE *)P + 16) )
          *(_OWORD *)P = 0;
        FsFltWil::Details::FreeUnicodeString(v28, v27);
        ExFreePoolWithTag(v28, 0);
      }
      goto LABEL_69;
    }
    v52 = P;
  }
  v53 = *((_QWORD *)a5 + 20);
  P = 0;
  v54 = *(_QWORD *)(v53 + 64);
  *(_QWORD *)(v53 + 64) = v52;
  if ( v54 )
  {
    if ( !*(_BYTE *)(v54 + 16) )
      *(_OWORD *)v54 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v54, 0);
    ExFreePoolWithTag((PVOID)v54, 0);
  }
  if ( v154 )
  {
    if ( !DWORD1(v170) )
      MicrosoftTelemetryAssertTriggeredMsgKM("results.LookupResult != MAPPING_LOOKUP_RESULT::None");
    if ( (*(_DWORD *)(*((_QWORD *)a5 + 1) + 24LL) & 0x80u) != 0 )
    {
      v154 = 0;
      IsFileCowable = UnionFs::Utils::IsFileCowable(
                        (UnionFs::Utils *)&v154,
                        (bool *)v171[0],
                        (struct UnionFs::UfsPathCachePayload *)a6,
                        v24);
      if ( IsFileCowable < 0 )
      {
        v19 = "PUSH: Checking immutability";
        v20 = 0x78300020C2ALL;
        goto LABEL_39;
      }
      if ( !v154 )
      {
        if ( (unsigned int)dword_14009E178 > 5
          && (qword_14009E188 & 0x400000000000LL) != 0
          && (qword_14009E190 & 0x400000000000LL) == qword_14009E190 )
        {
          v160 = (PVOID)1;
          v161 = (UnionFs::UfsPathCachePayload *)0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            0,
            (unsigned int)&unk_140095F18,
            v55,
            (unsigned int)&v161,
            (__int64)&v160);
        }
        v56 = -1073741790;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0000022LL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x78400020C37LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
          "ORIGIN: Rejecting COW for immutable file",
          v143);
LABEL_122:
        IsFileCowable = v56;
        goto LABEL_69;
      }
    }
    v57 = v171[0];
    v58 = v174;
    *(_QWORD *)&v169.Length = *((_QWORD *)a5 + 1);
    v59 = *((_QWORD *)a5 + 2);
    v169.Buffer = (PWSTR)v59;
    if ( v59 )
      _InterlockedIncrement((volatile signed __int32 *)(v59 + 8));
    IsFileCowable = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(v57, &v169, v58, 11, a6);
    if ( IsFileCowable < 0 )
    {
      v19 = "PUSH: ConvertToSoftTombstone for COW";
      v20 = 0x39800020C43LL;
      goto LABEL_39;
    }
    v60 = Resource;
    v164 = (__int64)&v170;
    LOBYTE(v165) = 1;
    Resource = 0;
    if ( v60 )
    {
      ExReleaseResourceLite(v60);
      KeLeaveCriticalRegion();
    }
    v61 = (UnionFs::UfsUnionCtx *)*((_QWORD *)a5 + 1);
    v62 = (volatile signed __int32 *)*((_QWORD *)v171[0] + 5);
    v63 = (const struct UnionFs::UfsLayerCtx *)*((_QWORD *)v171[0] + 4);
    if ( v62 )
      _InterlockedIncrement(v62 + 2);
    v39 = 0;
    IsFileCowable = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
                      v61,
                      a2,
                      a3,
                      *(const struct _FLT_FILE_NAME_INFORMATION **)a5,
                      *(const struct UnionFs::UfsPathName **)(*((_QWORD *)a5 + 20) + 64LL),
                      *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
                      v63,
                      (struct UnionFs::StackEventTracer *)a6,
                      v161);
    if ( v62 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v62);
    if ( IsFileCowable < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)IsFileCowable,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x29700020C5BLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
        "PUSH: Preparing for COW",
        v145);
LABEL_135:
      wil::details::lambda_call__lambda_32be77dcd1b34d4ec915836608e69756___::_lambda_call__lambda_32be77dcd1b34d4ec915836608e69756___(&v164);
      goto LABEL_69;
    }
    v64 = (struct _ERESOURCE *)v171[0];
    *(_QWORD *)v177 = *((_QWORD *)a5 + 1);
    v65 = v171[1];
    v180 = 0;
    v181 = 22;
    *(_OWORD *)v178 = 0;
    *(_OWORD *)v179 = 0;
    if ( v171[1] )
      _InterlockedIncrement((volatile signed __int32 *)v171[1] + 2);
    v178[1] = v64;
    v66 = v179[0];
    v179[0] = v65;
    if ( v66 )
      utl::_RefCountBase::_DecStrong(v66);
    UnionFs::UfsPathName::UfsPathName(
      (UnionFs::UfsPathName *)&UnicodeString,
      (const struct _UNICODE_STRING *)(*(_QWORD *)a5 + 8LL),
      *(_WORD *)(*(_QWORD *)a5 + 24LL));
    Instance = a3->Instance;
    v68 = (volatile signed __int32 *)*((_QWORD *)v171[0] + 5);
    v69 = *((_QWORD *)v171[0] + 6);
    v70 = *((_QWORD *)v171[0] + 4);
    if ( v68 )
      _InterlockedIncrement(v68 + 2);
    IsFileCowable = UnionFs::Utils::CopyItem(
                      (_DWORD)a2,
                      v70,
                      v69,
                      (_DWORD)Instance,
                      &UnicodeString,
                      (__int64)v177,
                      (struct _FILE_OBJECT *)a6,
                      0);
    if ( v68 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v68);
    if ( IsFileCowable < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)IsFileCowable,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x29000020C6CLL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
        "PUSH: Performing COW",
        v146);
      if ( !(_BYTE)v189 )
        UnicodeString = 0;
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v72);
      if ( v179[0] )
        utl::_RefCountBase::_DecStrong(v179[0]);
      goto LABEL_135;
    }
    LOBYTE(v165) = 0;
    if ( !(_BYTE)v189 )
      UnicodeString = 0;
    FsFltWil::Details::FreeUnicodeString(&UnicodeString, v71);
    if ( v179[0] )
      utl::_RefCountBase::_DecStrong(v179[0]);
    wil::details::lambda_call__lambda_32be77dcd1b34d4ec915836608e69756___::_lambda_call__lambda_32be77dcd1b34d4ec915836608e69756___(&v164);
LABEL_68:
    IsFileCowable = v39;
    goto LABEL_69;
  }
  if ( v171[0] )
    MicrosoftTelemetryAssertTriggeredMsgKM("!results.CacheEntry");
  UnicodeString.Buffer = (PWSTR)off_14007E748;
  p_Buffer = &UnicodeString.Buffer;
  UnionFs::StackEventTracer::SetIgnoreStatusCallback(a6, &UnicodeString);
  memset(v199, 0, 0x48u);
  v143 = (char *)a6;
  IsFileCowable = UnionFs::Utils::StatItemAsCaller(*(_QWORD *)a5 + 8LL, a3->Instance, v73, v199, a2);
  SubstituteNameLength = a6[20].SymbolicLinkReparseBuffer.SubstituteNameLength;
  if ( SubstituteNameLength )
  {
    v75 = SubstituteNameLength - 1;
    a6[20].SymbolicLinkReparseBuffer.SubstituteNameLength = v75;
    v76 = 5 * (v75 + 1LL);
    v77 = *(_QWORD *)&a6[v76].ReparseTag;
    *(_QWORD *)&a6[v76].ReparseTag = 0;
    if ( v77 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v77 + 24LL))(v77, v76 * 24, 0, 1);
  }
  v39 = 260;
  if ( IsFileCowable == 260 )
    goto LABEL_68;
  if ( IsFileCowable >= 0 )
    goto LABEL_18;
  if ( IsFileCowable == -1073741766 )
  {
    v155 = 0;
  }
  else
  {
    if ( IsFileCowable != -1073741772 )
    {
      v19 = "PUSH: Querying stat information";
      v20 = 0xE700020C91LL;
      goto LABEL_39;
    }
    v155 = 1;
  }
  utl::make_unique<UnionFs::FindAndStatResults,,0>(&v160);
  v78 = (__int16 *)v160;
  if ( !v160 )
  {
    IsFileCowable = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x3FD00020CA8LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
      "ORIGIN: Allocating findAndStatResults",
      (const char *)a6);
    goto LABEL_69;
  }
  v159 = 0;
  *((_QWORD *)v160 + 12) = &v159;
  v79 = *((_QWORD *)a5 + 1);
  v147 = (const char *)v78;
  Source = *(UNICODE_STRING *)*(_QWORD *)(*((_QWORD *)a5 + 20) + 64LL);
  v80 = UnionFs::UfsUnionCtx::FindAndStatItemInLayersAsCaller(v79, a2, &Source);
  v83 = 0;
  v157 = v80;
  if ( v80 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v80,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0xE900020CB5LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
      "PUSH: Statting item in layers",
      (const char *)v78);
LABEL_171:
    v85 = (struct _UNICODE_STRING *)v159;
    if ( v159 )
    {
      if ( !*((_BYTE *)v159 + 16) )
        *(_OWORD *)v159 = 0;
      FsFltWil::Details::FreeUnicodeString(v85, v84);
      ExFreePoolWithTag(v85, 0);
    }
    if ( v78 )
    {
      v86 = (utl::_RefCountBase *)*((_QWORD *)v78 + 11);
      if ( v86 )
        utl::_RefCountBase::_DecStrong(v86);
      ExFreePoolWithTag(v78, 0);
    }
LABEL_76:
    IsFileCowable = v157;
    goto LABEL_69;
  }
  if ( v80 == 260 )
  {
    v87 = (struct _UNICODE_STRING *)v159;
    if ( v159 )
    {
      v88 = *((_BYTE *)v159 + 16) == 0;
LABEL_182:
      if ( v88 )
        *v87 = 0;
      FsFltWil::Details::FreeUnicodeString(v87, v81);
      ExFreePoolWithTag(v87, 0);
      goto LABEL_185;
    }
    goto LABEL_185;
  }
  v90 = *v78;
  if ( *v78 == 2 )
  {
    if ( !v155 )
    {
      v91 = v163;
      a2->IoStatus.Status = -1073741766;
      a2->IoStatus.Information = 0;
      *v91 = FLT_PREOP_COMPLETE;
    }
    goto LABEL_192;
  }
  if ( v90 == 3 )
  {
    if ( !v155 )
    {
      v39 = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
              *((UnionFs::UfsUnionCtx **)a5 + 1),
              a2,
              a3,
              *(const struct _FLT_FILE_NAME_INFORMATION **)a5,
              *(const struct UnionFs::UfsPathName **)(*((_QWORD *)a5 + 20) + 64LL),
              *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
              *((const struct UnionFs::UfsLayerCtx **)v78 + 10),
              (struct UnionFs::StackEventTracer *)a6,
              v161);
      if ( v39 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v39,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0xEA00020CDDLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
          "PUSH: Preparing for scratch create",
          v148);
        v87 = (struct _UNICODE_STRING *)v159;
        if ( v159 )
        {
          v88 = *((_BYTE *)v159 + 16) == 0;
          goto LABEL_182;
        }
LABEL_185:
        if ( v78 )
        {
          v89 = (utl::_RefCountBase *)*((_QWORD *)v78 + 11);
          if ( v89 )
            utl::_RefCountBase::_DecStrong(v89);
          ExFreePoolWithTag(v78, 0);
        }
        goto LABEL_68;
      }
    }
LABEL_192:
    v92 = (struct _UNICODE_STRING *)v159;
    if ( v159 )
    {
      if ( !*((_BYTE *)v159 + 16) )
        *(_OWORD *)v159 = 0;
      FsFltWil::Details::FreeUnicodeString(v92, v81);
      ExFreePoolWithTag(v92, 0);
    }
    if ( v78 )
    {
      v93 = (utl::_RefCountBase *)*((_QWORD *)v78 + 11);
      if ( v93 )
        utl::_RefCountBase::_DecStrong(v93);
      ExFreePoolWithTag(v78, 0);
    }
    goto LABEL_18;
  }
  if ( v90 != 1 )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("findAndStatResults->FindResult == LAYER_FIND_RESULT::Found");
    v83 = 0;
  }
  v94 = (volatile signed __int32 *)*((_QWORD *)v78 + 11);
  v95 = (PVOID)*((_QWORD *)v78 + 10);
  v160 = v95;
  if ( v94 )
    _InterlockedIncrement(v94 + 2);
  v96 = *(_DWORD *)(a2->Iopb->Parameters.WMI.ProviderId + 16);
  if ( (v96 & 0x2000000) != 0 )
  {
    if ( (*((_DWORD *)v78 + 19) & 0x10D0106) != 0 )
      goto LABEL_211;
LABEL_231:
    *(_QWORD *)&v169.Length = *((_QWORD *)&v174 + 1);
    v167 = 0;
    Context = 0;
    LODWORD(v162) = 0;
    v154 = 0;
    v155 = 0;
    v169.Buffer = (PWSTR)v174;
    *(_OWORD *)v166 = 0;
    if ( !UnionFs::Utils::GetQueryOnCreateEcp(a2, (const struct _FLT_CALLBACK_DATA *)&Context, &v162, v82) )
      goto LABEL_242;
    v105 = Context;
    if ( (*(_DWORD *)Context & 4) == 0 )
    {
LABEL_240:
      if ( (*v105 & 8) != 0 )
      {
        *v105 &= ~8u;
        v155 = 1;
      }
LABEL_242:
      v106 = &v169;
      v107 = (const UNICODE_STRING *)v159;
      if ( (_DWORD)v173 != 2 )
        v106 = 0;
      *(_QWORD *)&UnicodeString.Length = &v154;
      UnicodeString.Buffer = (PWSTR)&Context;
      v189 = &v155;
      v108 = *((_DWORD *)v78 + 16);
      *(_QWORD *)v183 = v160;
      v184 = v94;
      v190 = 1;
      if ( v94 )
        _InterlockedIncrement(v94 + 2);
      inited = UnionFs::UfsPathCachePayload::AllocAndInitShared(
                 a2,
                 *((_QWORD *)a5 + 1),
                 (__int64)v183,
                 v107,
                 v108,
                 v166,
                 (struct UnionFs::Utils::CallerAccessParams *)a6,
                 (__int64)v106);
      if ( inited < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)inited,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x45600020D47LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
          "PUSH: Allocating cache entry",
          v149);
        if ( v154 )
        {
          *(_DWORD *)Context |= 4u;
          *((_DWORD *)Context + 1) |= 4u;
        }
        if ( v155 )
          *(_DWORD *)Context |= 8u;
        utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(v166);
        if ( v94 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v94);
        v111 = (struct _UNICODE_STRING *)v159;
        if ( v159 )
        {
          if ( !*((_BYTE *)v159 + 16) )
            *(_OWORD *)v159 = 0;
          FsFltWil::Details::FreeUnicodeString(v111, v110);
          ExFreePoolWithTag(v111, 0);
        }
        if ( v78 )
        {
          v112 = (utl::_RefCountBase *)*((_QWORD *)v78 + 11);
          if ( v112 )
            utl::_RefCountBase::_DecStrong(v112);
          ExFreePoolWithTag(v78, 0);
        }
        IsFileCowable = inited;
        goto LABEL_69;
      }
      if ( inited == 260 )
      {
        wil::details::lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___::_lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___(&UnicodeString);
        utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(v166);
        if ( v94 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v94);
        v114 = (struct _UNICODE_STRING *)v159;
        if ( v159 )
        {
          if ( !*((_BYTE *)v159 + 16) )
            *(_OWORD *)v159 = 0;
          FsFltWil::Details::FreeUnicodeString(v114, v113);
          ExFreePoolWithTag(v114, 0);
        }
        if ( v78 )
        {
          v115 = (utl::_RefCountBase *)*((_QWORD *)v78 + 11);
          if ( v115 )
            utl::_RefCountBase::_DecStrong(v115);
          ExFreePoolWithTag(v78, 0);
        }
        IsFileCowable = 260;
        goto LABEL_69;
      }
      v116 = (UnionFs::UfsPathCachePayload *)v167;
      v164 = *(_QWORD *)v166;
      v165 = *(utl::_RefCountBase **)&v166[8];
      v117 = *((_QWORD *)a5 + 1);
      *(_OWORD *)v166 = 0;
      v167 = 0;
      v161 = v116;
      v88 = *(_DWORD *)(v117 + 28) == 2;
      *(_QWORD *)v177 = 0;
      *(_OWORD *)v178 = 0;
      v179[0] = 0;
      v179[1] = 0;
      if ( v88 )
        v118 = *(_QWORD *)(*(_QWORD *)(v117 + 32) + 16LL);
      else
        v118 = *((_QWORD *)UnionFs::g_FilterState + 10);
      v119 = v175;
      v150 = v177;
      inserted = UnionFs::UfsPathCache::InsertEntry(v118, v175->Instance, v116, 1, &v164);
      v157 = inserted;
      if ( inserted < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)inserted,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x45700020D5FLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
          "PUSH: Inserting path cache payload",
          v177);
        UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v177);
        if ( v116 )
        {
          if ( !*((_BYTE *)v116 + 16) )
            *(_OWORD *)v116 = 0;
          FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v116, v121);
          ExFreePoolWithTag(v116, 0);
        }
        if ( v165 )
          utl::_RefCountBase::_DecStrong(v165);
        wil::details::lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___::_lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___(&UnicodeString);
        utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(v166);
        if ( v94 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v94);
        goto LABEL_171;
      }
      if ( *(_DWORD *)v177 == 2 )
      {
        v160 = v178[1];
        v168 = v179[0];
        if ( v179[0] )
          _InterlockedIncrement((volatile signed __int32 *)v179[0] + 2);
        if ( v165 )
          utl::_RefCountBase::_DecStrong(v165);
      }
      else
      {
        if ( *(_DWORD *)v177 == 3 )
        {
          if ( ((__int64)v179[1] & 1) == 0 )
            MicrosoftTelemetryAssertTriggeredMsgKM("WI_IsFlagSet(insertResults.Flags, InsertEntryResultsFlags::StoppedOnHardTombstone)");
          UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v177);
          if ( v116 )
          {
            if ( !*((_BYTE *)v116 + 16) )
              *(_OWORD *)v116 = 0;
            FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v116, v122);
            ExFreePoolWithTag(v116, 0);
          }
          if ( v165 )
            utl::_RefCountBase::_DecStrong(v165);
          wil::details::lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___::_lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___(&UnicodeString);
          utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(v166);
          if ( !v94 )
            goto LABEL_314;
          goto LABEL_313;
        }
        v168 = v165;
        v160 = (PVOID)v164;
      }
      v124 = v119->FileObject;
      UnionFs::UfsUnionCtx::GetScratchLayer(*((_QWORD *)a5 + 1), &Source);
      LODWORD(v150) = 8;
      v125 = UnionFs::UfsShadowFileObject::SetUp(
               v124,
               a2,
               (UnionFs::UfsPathCachePayload *)v160,
               (struct UnionFs::StackEventTracer *)v150,
               (__int64)a5 + 160,
               (struct UnionFs::Utils::CheckOplockHParams *)a6);
      v56 = 0;
      v157 = v125;
      if ( Source.Buffer )
      {
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Source.Buffer);
        v125 = v157;
      }
      if ( v125 != 259 )
      {
        if ( v125 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v125,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x13000020D9ALL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
            "PUSH: Setting up shadow file object",
            v151);
          UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v177);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v161);
          if ( v168 )
            utl::_RefCountBase::_DecStrong(v168);
          wil::details::lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___::_lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___(&UnicodeString);
          utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(v166);
          if ( v94 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v94);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v159);
          if ( v78 )
          {
            v129 = (utl::_RefCountBase *)*((_QWORD *)v78 + 11);
            if ( v129 )
              utl::_RefCountBase::_DecStrong(v129);
            ExFreePoolWithTag(v78, 0);
          }
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
          goto LABEL_76;
        }
        v130 = v178[0];
        v178[0] = 0;
        if ( v130 )
        {
          ExReleaseResourceLite(v130);
          KeLeaveCriticalRegion();
        }
        if ( v155 )
        {
          *((_QWORD *)Context + 19) = 0;
          *((_DWORD *)Context + 1) |= 8u;
        }
        UnionFs::UnionFsFilter::VirtualizeQoCEcpIDs(
          (UnionFs::UnionFsFilter *)v130,
          a2,
          v175,
          *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
          *((struct UnionFs::UfsUnionCtx **)a5 + 1),
          (struct UnionFs::StackEventTracer *)a6,
          (struct _QUERY_ON_CREATE_ECP_CONTEXT *)Context,
          (unsigned int)v162);
        v131 = v163;
        a2->IoStatus.Status = 0;
        a2->IoStatus.Information = 1;
        *v131 = FLT_PREOP_COMPLETE;
        UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v177);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v161);
        if ( v168 )
          utl::_RefCountBase::_DecStrong(v168);
        wil::details::lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___::_lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___(&UnicodeString);
        utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(v166);
LABEL_340:
        if ( v94 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v94);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v159);
        if ( v78 )
        {
          v132 = (utl::_RefCountBase *)*((_QWORD *)v78 + 11);
          if ( v132 )
            utl::_RefCountBase::_DecStrong(v132);
          ExFreePoolWithTag(v78, 0);
        }
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
        goto LABEL_122;
      }
      *v163 = FLT_PREOP_PENDING;
      UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v177);
      if ( v116 )
      {
        if ( !*((_BYTE *)v116 + 16) )
          *(_OWORD *)v116 = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v116, v126);
        ExFreePoolWithTag(v116, 0);
      }
      if ( v168 )
        utl::_RefCountBase::_DecStrong(v168);
      wil::details::lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___::_lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___(&UnicodeString);
      utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(v166);
      if ( !v94 )
        goto LABEL_314;
LABEL_313:
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v94);
LABEL_314:
      v127 = (struct _UNICODE_STRING *)v159;
      if ( v159 )
      {
        if ( !*((_BYTE *)v159 + 16) )
          *(_OWORD *)v159 = 0;
        FsFltWil::Details::FreeUnicodeString(v127, v123);
        ExFreePoolWithTag(v127, 0);
      }
      if ( v78 )
      {
        v128 = (utl::_RefCountBase *)*((_QWORD *)v78 + 11);
        if ( v128 )
          utl::_RefCountBase::_DecStrong(v128);
        ExFreePoolWithTag(v78, 0);
      }
      IsFileCowable = 0;
      goto LABEL_69;
    }
    if ( (unsigned int)v162 >= 0x88 )
    {
      if ( (int)UnionFs::UnionFsFilter::HandleQoCEcpEaInfo(
                  (UnionFs::UnionFsFilter *)Context,
                  a2,
                  a3,
                  *((struct UnionFs::UfsUnionCtx **)a5 + 1),
                  (struct _QUERY_ON_CREATE_ECP_CONTEXT *)Context,
                  (struct UnionFs::StackEventTracer *)a6) >= 0 )
        goto LABEL_238;
      *((_DWORD *)Context + 1) |= 4u;
    }
    else
    {
      *((_DWORD *)Context + 1) |= 4u;
    }
    *((_DWORD *)Context + 2) |= 4u;
LABEL_238:
    v105 = Context;
    if ( (*((_DWORD *)Context + 1) & 4) != 0 )
    {
      *(_DWORD *)Context &= ~4u;
      *((_DWORD *)Context + 1) &= ~4u;
      v105 = Context;
      v154 = 1;
    }
    goto LABEL_240;
  }
  if ( (v96 & 0x10D0106) == 0 )
    goto LABEL_231;
LABEL_211:
  if ( (unsigned int)dword_14009E178 > 5 )
  {
    v83 = 0x10000;
    if ( (qword_14009E188 & 0x10000) != 0 && (qword_14009E190 & 0x10000) == qword_14009E190 )
    {
      v169 = 0;
      UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v200, 0x1E00020DBEuLL);
      UnionFs::Utils::GetUserSidString(a2, &v169, v200);
      Source = *(UNICODE_STRING *)v159;
      if ( (unsigned int)dword_14009E178 > 5
        && (qword_14009E188 & 0x30200) != 0
        && (qword_14009E190 & 0x30200) == qword_14009E190 )
      {
        v99 = a2->Iopb;
        v157 = *((_DWORD *)v78 + 19);
        *(_QWORD *)v183 = "UnionFs::UnionFsFilter::PreCreateFileOpenIf";
        LODWORD(v162) = *(_DWORD *)(*(_QWORD *)(v99->Parameters.WMI.ProviderId + 8) + 24LL);
        v182 = *(_DWORD *)(*(_QWORD *)(v99->Parameters.WMI.ProviderId + 8) + 20LL);
        LODWORD(v175) = *(_DWORD *)(*(_QWORD *)(v99->Parameters.WMI.ProviderId + 8) + 16LL);
        LODWORD(v168) = *(_DWORD *)(*(_QWORD *)(v99->Parameters.WMI.ProviderId + 8) + 12LL);
        LODWORD(v163) = *(_DWORD *)(v99->Parameters.WMI.ProviderId + 16);
        v100 = *(_DWORD *)(v99->Parameters.WMI.ProviderId + 16);
        v101 = &v169;
        LODWORD(Context) = 3545;
        v154 = (v100 & 0x2000000) != 0;
        if ( !v169.Buffer )
          v101 = (struct _UNICODE_STRING *)&FsTlEmptyUnicodeString;
        v185 = v101;
        p_Source = &Source;
        if ( !Source.Buffer )
          p_Source = (UNICODE_STRING *)&FsTlEmptyUnicodeString;
        v186 = p_Source;
        v187 = "onecore\\base\\fs\\unionfs\\sys\\create.cpp";
        v164 = (__int64)"FileOpenIfCowNotInCache";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&FsTlEmptyUnicodeString,
          (unsigned int)byte_140096085,
          v97,
          v98,
          (__int64)&v164,
          (__int64)v183,
          (__int64)&v187,
          (__int64)&Context,
          (__int64)&v186,
          (__int64)&v185,
          (__int64)&v154,
          (__int64)&v163,
          (__int64)&v168,
          (__int64)&v175,
          (__int64)&v182,
          (__int64)&v162,
          (__int64)&v157);
      }
      UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v200);
      FsFltWil::Details::FreeUnicodeString(&v169, v103);
      v95 = v160;
    }
  }
  v104 = (UnionFs::UfsUnionCtx *)*((_QWORD *)a5 + 1);
  if ( (*((_DWORD *)v104 + 6) & 0x80u) != 0 && (*((_DWORD *)v78 + 16) & 0x800010) == 0 )
  {
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x400000000000LL) != 0
      && (qword_14009E190 & 0x400000000000LL) == qword_14009E190 )
    {
      v164 = 1;
      *(_QWORD *)v183 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        0,
        (unsigned int)&word_14009624E,
        v83,
        (unsigned int)v183,
        (__int64)&v164);
    }
    v56 = -1073741790;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0000022LL,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x78500020DF0LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
      "ORIGIN: Rejecting COW for immutable file",
      v147);
    goto LABEL_340;
  }
  v133 = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
           v104,
           a2,
           a3,
           *(const struct _FLT_FILE_NAME_INFORMATION **)a5,
           *(const struct UnionFs::UfsPathName **)(*((_QWORD *)a5 + 20) + 64LL),
           *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
           (const struct UnionFs::UfsLayerCtx *)v95,
           (struct UnionFs::StackEventTracer *)a6,
           v161);
  LODWORD(Context) = v133;
  if ( v133 >= 0 )
  {
    v135 = *(_QWORD *)a5;
    v136 = *((_QWORD *)a5 + 1);
    v195 = 0;
    *(_QWORD *)v192 = v136;
    v196 = 22;
    v193 = 0;
    *(_OWORD *)v194 = 0;
    UnionFs::UfsPathName::UfsPathName(
      (UnionFs::UfsPathName *)&v197,
      (const struct _UNICODE_STRING *)(v135 + 8),
      *(_WORD *)(v135 + 24));
    v138 = UnionFs::Utils::CopyItem(
             (_DWORD)a2,
             (_DWORD)v160,
             (_DWORD)v159,
             a3->Instance,
             &v197,
             (__int64)v192,
             (struct _FILE_OBJECT *)a6,
             0);
    if ( v138 >= 0 )
    {
      if ( !v198 )
        v197 = 0;
      FsFltWil::Details::FreeUnicodeString(&v197, v137);
      if ( v194[0] )
        utl::_RefCountBase::_DecStrong(v194[0]);
      if ( v94 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v94);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v159);
      if ( v78 )
      {
        v141 = (utl::_RefCountBase *)*((_QWORD *)v78 + 11);
        if ( v141 )
          utl::_RefCountBase::_DecStrong(v141);
        ExFreePoolWithTag(v78, 0);
      }
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
      IsFileCowable = 0;
    }
    else
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v138,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x29100020E16LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
        "PUSH: Performing COW",
        v153);
      if ( !v198 )
        v197 = 0;
      FsFltWil::Details::FreeUnicodeString(&v197, v139);
      if ( v194[0] )
        utl::_RefCountBase::_DecStrong(v194[0]);
      if ( v94 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v94);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v159);
      if ( v78 )
      {
        v140 = (utl::_RefCountBase *)*((_QWORD *)v78 + 11);
        if ( v140 )
          utl::_RefCountBase::_DecStrong(v140);
        ExFreePoolWithTag(v78, 0);
      }
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
      IsFileCowable = v138;
    }
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v133,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x29600020E03LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
      "PUSH: Preparing for COW",
      v152);
    if ( v94 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v94);
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&v159);
    if ( v78 )
    {
      v134 = (utl::_RefCountBase *)*((_QWORD *)v78 + 11);
      if ( v134 )
        utl::_RefCountBase::_DecStrong(v134);
      ExFreePoolWithTag(v78, 0);
    }
    utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&P);
    IsFileCowable = (int)Context;
  }
LABEL_69:
  UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v170);
  return (unsigned int)IsFileCowable;
}

```

## disassembly

```asm
0x14001568c  mov     [rsp-8+arg_0], rbx
0x140015691  push    rbp
0x140015692  push    rsi
0x140015693  push    rdi
0x140015694  push    r12
0x140015696  push    r13
0x140015698  push    r14
0x14001569a  push    r15
0x14001569c  lea     rbp, [rsp-520h]
0x1400156a4  sub     rsp, 630h
0x1400156ab  mov     rax, cs:__security_cookie
0x1400156b2  xor     rax, rsp
0x1400156b5  mov     [rbp+550h+var_40], rax
0x1400156bc  mov     rax, [rbp+550h+arg_30]
0x1400156c3  mov     r15, rdx
0x1400156c6  mov     r12, [rbp+550h+arg_20]
0x1400156cd  xor     edx, edx
0x1400156cf  mov     rsi, [rbp+550h+arg_28]
0x1400156d6  mov     r14, r9
0x1400156d9  mov     [r9], edx
0x1400156dc  mov     r13, r8
0x1400156df  mov     [rbp+550h+var_5A0], rax
0x1400156e3  mov     rax, [r8+20h]
0x1400156e7  mov     [rbp+550h+var_590], r9
0x1400156eb  mov     [rbp+550h+var_500], r8
0x1400156ef  mov     ebx, [rax+50h]
0x1400156f2  mov     rax, [r15+10h]
0x1400156f6  shr     ebx, 11h
0x1400156f9  not     ebx
0x1400156fb  and     ebx, 1
0x1400156fe  cmp     [rax+4], dl
0x140015701  jz      short loc_140015713
0x140015703  lea     rcx, aCheckingReques; "Checking requested access on non-create"
0x14001570a  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14001570f  xor     edx, edx
0x140015711  jmp     short loc_14001572B
0x140015713  mov     rax, [rax+18h]
0x140015717  mov     ecx, [rax+10h]
0x14001571a  test    ecx, 10D0106h
0x140015720  jnz     short loc_140015728
0x140015722  bt      ecx, 19h
0x140015726  jnb     short loc_14001572B
0x140015728  or      ebx, 8
0x14001572b  xorps   xmm1, xmm1
0x14001572e  mov     [rbp+550h+Resource], rdx
0x140015732  movd    eax, xmm1
0x140015736  xorps   xmm0, xmm0
0x140015739  movdqa  [rbp+550h+var_540], xmm1
0x14001573e  movdqa  xmmword ptr [rbp+550h+var_530], xmm0
0x140015743  or      eax, 3
0x140015746  mov     [rbp+550h+var_518], 0
0x14001574e  mov     dword ptr [rbp+550h+var_540], eax
0x140015751  mov     rax, [r12+8]
0x140015756  movdqa  [rbp+550h+var_510], xmm0
0x14001575b  cmp     dword ptr [rax+1Ch], 2
0x14001575f  jnz     short loc_14001576B
0x140015761  mov     rax, [rax+20h]
0x140015765  mov     rcx, [rax+10h]
0x140015769  jmp     short loc_140015776
0x14001576b  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140015772  mov     rcx, [rax+50h]
0x140015776  mov     r8, [r12]
0x14001577a  lea     rax, [rbp+550h+var_540]
0x14001577e  mov     rdx, [r13+18h]
0x140015782  mov     r9d, ebx
0x140015785  mov     qword ptr [rsp+660h+var_630], r15
0x14001578a  mov     [rsp+660h+var_638], rsi; char *
0x14001578f  mov     [rsp+660h+var_640], rax; struct UnionFs::StackEventTracer *
0x140015794  call    ?LookupEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@W4LookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,UnionFs::LookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x140015799  xor     r8d, r8d
0x14001579c  mov     edi, eax
0x14001579e  test    eax, eax
0x1400157a0  jns     short loc_1400157B8
0x1400157a2  lea     rax, aPushCacheLooku; "PUSH: Cache lookup"
0x1400157a9  mov     r8, 11F00020AFAh
0x1400157b3  jmp     loc_14001598E
0x1400157b8  mov     eax, dword ptr [rbp+550h+var_540+4]
0x1400157bb  mov     edx, 4
0x1400157c0  mov     [rbp+550h+var_5D0], r8b
0x1400157c4  test    eax, eax
0x1400157c6  jz      loc_14001588E
0x1400157cc  test    byte ptr [rbp+550h+var_540+8], dl
0x1400157cf  jz      short loc_1400157FA
0x1400157d1  lea     ecx, [rdx-3]
0x1400157d4  cmp     eax, ecx
0x1400157d6  jz      short loc_1400157E9
0x1400157d8  mov     dword ptr [r15+18h], 0C000003Ah
0x1400157e0  mov     [r15+20h], r8
0x1400157e4  mov     [r14], edx
0x1400157e7  jmp     short loc_14001580F
0x1400157e9  lea     rdx, [rbp+550h+var_530]
0x1400157ed  mov     rcx, r12
0x1400157f0  call    ?OverwriteTombstone@CreateContext@UnionFs@@QEAAX$$QEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@@Z; UnionFs::CreateContext::OverwriteTombstone(utl::shared_ptr<UnionFs::UfsPathCachePayload> &&)
0x1400157f5  jmp     loc_14001661B
0x1400157fa  mov     ebx, 1
0x1400157ff  cmp     dword ptr [rbp+550h+var_518], ebx
0x140015802  jnz     short loc_140015817
0x140015804  mov     rax, [r12+0A0h]
0x14001580c  or      dword ptr [rax], 8
0x14001580f  mov     edi, r8d
0x140015812  jmp     loc_140015C3F
0x140015817  mov     rax, [rbp+550h+var_530]
0x14001581b  movzx   ecx, word ptr [rax+0A8h]
0x140015822  nop
0x140015823  cmp     cx, dx
0x140015826  jnz     loc_140015947
0x14001582c  mov     rax, [rbp+550h+var_530]
0x140015830  cmp     [rax+0D8h], r8
0x140015837  jnz     short loc_140015848
0x140015839  lea     rcx, aResultsCacheen; "results.CacheEntry->GetOriginalScratchP"...
0x140015840  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140015845  xor     r8d, r8d
0x140015848  cmp     dword ptr [rbp+550h+var_540+4], ebx
0x14001584b  jz      short loc_14001580F
0x14001584d  mov     rcx, [rbp+550h+Resource]; Resource
0x140015851  mov     [rbp+550h+Resource], r8
0x140015855  test    rcx, rcx
0x140015858  jz      short loc_140015875
0x14001585a  call    cs:__imp_ExReleaseResourceLite
0x140015861  nop     dword ptr [rax+rax+00h]
0x140015866  call    cs:__imp_KeLeaveCriticalRegion
0x14001586d  nop     dword ptr [rax+rax+00h]
0x140015872  xor     r8d, r8d
0x140015875  mov     rcx, [rbp+550h+var_530+8]; this
0x140015879  mov     [rbp+550h+var_530+8], r8
0x14001587d  mov     [rbp+550h+var_530], r8
0x140015881  test    rcx, rcx
0x140015884  jz      short loc_14001588E
0x140015886  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14001588b  xor     r8d, r8d
0x14001588e  cmp     dword ptr [rbp+550h+var_518], 2
0x140015892  mov     [rbp+550h+P], r8
0x140015896  jnz     loc_140015F13
0x14001589c  mov     rax, qword ptr [rbp+550h+var_510+8]
0x1400158a0  lea     r8, [rbp+550h+Source]; Source
0x1400158a4  mov     rcx, [r12]
0x1400158a8  lea     rdx, [rbp+550h+var_558]; struct _UNICODE_STRING *
0x1400158ac  add     rcx, 8; this
0x1400158b0  mov     [rsp+660h+var_638], rsi; char *
0x1400158b5  movzx   r9d, word ptr [rax+18h]
0x1400158ba  movups  xmm0, xmmword ptr [rax]
0x1400158bd  mov     rax, qword ptr [rbp+550h+var_510]
0x1400158c1  movdqu  xmmword ptr [rbp+550h+Source.Length], xmm0
0x1400158c6  movups  xmm1, xmmword ptr [rax]
0x1400158c9  lea     rax, [rbp+550h+P]
0x1400158cd  mov     [rsp+660h+var_640], rax; P
0x1400158d2  movdqu  xmmword ptr [rbp+550h+var_558.Length], xmm1
0x1400158d7  call    ?AllocAndInitWithReplacedPathPrefix@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@00GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x1400158dc  xor     r14d, r14d
0x1400158df  mov     edi, eax
0x1400158e1  test    eax, eax
0x1400158e3  jns     loc_140015F08
0x1400158e9  lea     rax, aPushReplacingS_3; "PUSH: Replacing substring"
0x1400158f0  mov     r8, 38200020C0Eh; struct UnionFs::StackEventTracer *
0x1400158fa  lea     r9, aUnionfsUnionfs_62; "UnionFs::UnionFsFilter::PreCreateFileOp"...
0x140015901  mov     [rsp+660h+var_640], rax; char *
0x140015906  mov     rdx, rsi; int
0x140015909  mov     ecx, edi; this
0x14001590b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140015910  mov     rbx, [rbp+550h+P]
0x140015914  test    rbx, rbx
0x140015917  jz      loc_140015C3F
0x14001591d  cmp     [rbx+10h], r14b
0x140015921  jnz     short loc_140015929
0x140015923  xorps   xmm0, xmm0
0x140015926  movups  xmmword ptr [rbx], xmm0
0x140015929  mov     rcx, rbx; UnicodeString
0x14001592c  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140015931  xor     edx, edx; Tag
0x140015933  mov     rcx, rbx; P
0x140015936  call    cs:__imp_ExFreePoolWithTag
0x14001593d  nop     dword ptr [rax+rax+00h]
0x140015942  jmp     loc_140015C3F
0x140015947  cmp     dword ptr [rbp+550h+var_540+4], ebx
0x14001594a  jnz     loc_14001584D
0x140015950  mov     rdi, [rbp+550h+var_530]
0x140015954  mov     rdx, [rdi+60h]; Src
0x140015958  test    rdx, rdx
0x14001595b  jz      short loc_1400159BF
0x14001595d  mov     rax, [r15+10h]
0x140015961  test    dword ptr [rax+20h], 200000h
0x140015968  jnz     short loc_1400159BF
0x14001596a  mov     r8, rsi; struct _REPARSE_DATA_BUFFER *
0x14001596d  mov     rcx, r15; Data
0x140015970  call    ?SetReparseDataFromCache@Utils@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_REPARSE_DATA_BUFFER@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::SetReparseDataFromCache(_FLT_CALLBACK_DATA &,_REPARSE_DATA_BUFFER const &,UnionFs::StackEventTracer &)
0x140015975  mov     edi, eax
0x140015977  xor     eax, eax
0x140015979  test    edi, edi
0x14001597b  jns     short loc_1400159A9
0x14001597d  lea     rax, aPushCompleting; "PUSH: Completing create with cached rep"...
0x140015984  mov     r8, 79200020B4Fh; struct UnionFs::StackEventTracer *
0x14001598e  lea     r9, aUnionfsUnionfs_62; "UnionFs::UnionFsFilter::PreCreateFileOp"...
0x140015995  mov     [rsp+660h+var_640], rax; char *
0x14001599a  mov     rdx, rsi; int
0x14001599d  mov     ecx, edi; this
0x14001599f  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400159a4  jmp     loc_140015C3F
0x1400159a9  mov     dword ptr [r15+18h], 104h
0x1400159b1  mov     edi, eax
0x1400159b3  mov     dword ptr [r14], 4
0x1400159ba  jmp     loc_140015C3F
0x1400159bf  mov     rcx, [rdi+48h]; Context
0x1400159c3  call    cs:__imp_FltReferenceContext
0x1400159ca  nop     dword ptr [rax+rax+00h]
0x1400159cf  mov     rdi, [rdi+48h]
0x1400159d3  lea     rcx, [rbp+550h+P]
0x1400159d7  mov     [rbp+550h+Context], rdi
0x1400159db  mov     rbx, [rdi+20h]
0x1400159df  mov     rdx, [rbx+78h]
0x1400159e3  add     rdx, 38h ; '8'
0x1400159e7  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x1400159ec  mov     rax, [r15+10h]
0x1400159f0  xor     r8d, r8d
0x1400159f3  cmp     [rax+4], r8b
0x1400159f7  jz      loc_140015AD5
0x1400159fd  lea     rcx, aCheckingReques; "Checking requested access on non-create"
0x140015a04  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140015a09  mov     rcx, [rbp+550h+P]; Resource
0x140015a0d  test    rcx, rcx
0x140015a10  jz      short loc_140015A2A
0x140015a12  call    cs:__imp_ExReleaseResourceLite
0x140015a19  nop     dword ptr [rax+rax+00h]
0x140015a1e  call    cs:__imp_KeLeaveCriticalRegion
0x140015a25  nop     dword ptr [rax+rax+00h]
0x140015a2a  mov     rbx, [r12+8]
0x140015a2f  lea     rcx, [rbp+550h+var_5A8]
0x140015a33  mov     rax, [rbp+550h+var_530]
0x140015a37  mov     r14, [r13+20h]
0x140015a3b  mov     [rbp+550h+var_5A0], rax
0x140015a3f  lea     rdx, [rbx+48h]
0x140015a43  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140015a48  mov     rax, [rbx+30h]
0x140015a4c  mov     rbx, [rax+8]
0x140015a50  mov     rcx, [rax]
0x140015a53  mov     [rbp+550h+P], rcx
0x140015a57  test    rbx, rbx
0x140015a5a  jz      short loc_140015A60
0x140015a5c  lock inc dword ptr [rbx+8]
0x140015a60  mov     rcx, [rbp+550h+var_5A8]; this
0x140015a64  test    rcx, rcx
0x140015a67  jz      short loc_140015A6E
0x140015a69  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140015a6e  mov     r9, [rbp+550h+P]
0x140015a72  lea     rax, [r12+0A0h]
0x140015a7a  mov     [rsp+660h+var_628], rsi; struct UnionFs::Utils::CheckOplockHParams *
0x140015a7f  mov     r8, r13
0x140015a82  mov     qword ptr [rsp+660h+var_630], rax; __int64
0x140015a87  mov     rdx, r15; struct _FLT_CALLBACK_DATA *
0x140015a8a  mov     rax, [rbp+550h+var_5A0]
0x140015a8e  mov     rcx, r14; struct _FILE_OBJECT *
0x140015a91  mov     dword ptr [rsp+660h+var_638], 7; char *
0x140015a99  mov     [rsp+660h+var_640], rax; UnionFs::UfsPathCachePayload *
0x140015a9e  call    ?SetUp@UfsShadowFileObject@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsLayerCtx@2@AEAVUfsPathCachePayload@2@W4ShareAccessCaller@2@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsShadowFileObject::SetUp(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsLayerCtx const &,UnionFs::UfsPathCachePayload &,UnionFs::ShareAccessCaller,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140015aa3  xor     r8d, r8d
0x140015aa6  mov     r14d, eax
0x140015aa9  test    rbx, rbx
0x140015aac  jz      short loc_140015AB9
0x140015aae  mov     rcx, rbx; this
0x140015ab1  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140015ab6  xor     r8d, r8d
0x140015ab9  cmp     r14d, 103h
0x140015ac0  jnz     loc_140015E50
0x140015ac6  mov     rax, [rbp+550h+var_590]
0x140015aca  mov     dword ptr [rax], 2
0x140015ad0  jmp     loc_140015EEB
0x140015ad5  mov     rax, [rax+18h]
0x140015ad9  mov     ecx, [rax+10h]
0x140015adc  test    ecx, 10D0106h
0x140015ae2  jnz     short loc_140015AEE
0x140015ae4  bt      ecx, 19h
0x140015ae8  jnb     loc_140015A09
0x140015aee  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x140015af3  test    eax, eax
0x140015af5  jz      loc_140015C54
0x140015afb  mov     r9, rsi; struct UnionFs::UfsFsContext *
0x140015afe  mov     r8, rbx; struct _FLT_RELATED_OBJECTS *
0x140015b01  mov     rdx, r13; struct _FLT_CALLBACK_DATA *
0x140015b04  mov     rcx, r15; this
0x140015b07  call    ?BreakBatchAndHOplocks@Utils@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsFsContext@2@AEAVStackEventTracer@2@@Z; UnionFs::Utils::BreakBatchAndHOplocks(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsFsContext &,UnionFs::StackEventTracer &)
0x140015b0c  mov     r14d, eax
0x140015b0f  cmp     eax, 103h
0x140015b14  jnz     loc_140015BDA
0x140015b1a  mov     eax, cs:dword_14009E178
0x140015b20  cmp     eax, 4
0x140015b23  jbe     short loc_140015BA0
0x140015b25  mov     rcx, cs:qword_14009E190
0x140015b2c  mov     edx, 200200h
0x140015b31  mov     rax, cs:qword_14009E188
0x140015b38  test    rdx, rax
0x140015b3b  jz      short loc_140015BA0
0x140015b3d  mov     rax, rcx
0x140015b40  and     rax, rdx
0x140015b43  cmp     rax, rcx
0x140015b46  jnz     short loc_140015BA0
0x140015b48  lea     rax, aOnecoreBaseFsU_14; "onecore\\base\\fs\\unionfs\\sys\\create"...
0x140015b4f  mov     [rbp+550h+var_5C0], 0B7Dh
0x140015b56  mov     [rbp+550h+var_5A8], rax
0x140015b5a  lea     rbx, aUnionfsUnionfs_62; "UnionFs::UnionFsFilter::PreCreateFileOp"...
0x140015b61  lea     rax, aOplockBreak; "Oplock break"
0x140015b68  mov     [rbp+550h+var_5A0], rbx
  ... truncated ...
```
