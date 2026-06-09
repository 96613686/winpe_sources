# UnionFs::UnionFsFilter::PreCreateFileOpen(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,_FLT_PREOP_CALLBACK_STATUS &,UnionFs::CreateContext &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *)

- ea: `0x140013bb0`
- end: `0x1400156a0`
- name: `?PreCreateFileOpen@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAW4_FLT_PREOP_CALLBACK_STATUS@@AEAUCreateContext@2@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@@Z`
- size: `6896`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, enum _FLT_PREOP_CALLBACK_STATUS *, struct UnionFs::CreateContext *, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsSiloCtx *)`
- caller_count: `1`
- callee_count: `48`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140011e00`

## callees

- `0x140001008`
- `0x140001d38`
- `0x140002354`
- `0x1400055d0`
- `0x140005d5c`
- `0x140006168`
- `0x140009ae0`
- `0x14000a7c8`
- `0x14000acc8`
- `0x14000efd0`
- `0x14000f4f4`
- `0x14000f7fc`
- `0x140010148`
- `0x140010b88`
- `0x140010d94`
- `0x140010ed8`
- `0x140011010`
- `0x140011148`
- `0x140011198`
- `0x1400114c4`
- `0x140013bb0`
- `0x14003c734`
- `0x14003cd88`
- `0x14003ff88`
- `0x1400414c8`
- `0x1400419a8`
- `0x1400438e4`
- `0x14004397c`
- `0x140043ef4`
- `0x140056ac4`
- `0x140056afc`
- `0x140058fbc`
- `0x140060ed8`
- `0x1400610fc`
- `0x1400696ac`
- `0x14006bca8`
- `0x14006f7fc`
- `0x14006ff9c`
- `0x1400702e4`
- `0x140078304`
- `0x140079a24`
- `0x140079a6c`
- `0x140079c48`
- `0x140079da0`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140013e54`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400143c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400145ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014661`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001468f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400146c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400146f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014784`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400147b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014814`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014845`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014b03`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014da9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014ddb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014e4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014e80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014f95`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001501c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001512c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015174`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400151a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001520d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013e54`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400143c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400145ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014661`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001468f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400146c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400146f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014784`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400147b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014814`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014845`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014b03`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014da9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014ddb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014e4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014e80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014f95`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001501c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001512c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015174`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400151a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001520d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152ff`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013d7d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013ec6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140014065`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400140b6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400141d2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001421b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001425a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400142e8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015237`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400154a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013d7d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013ec6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140014065`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400140b6`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400141d2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001421b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001425a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400142e8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015237`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400154a0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013d89`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013ed2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014071`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400140c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400141de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014227`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014266`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400142f4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015243`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400154ac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013d89`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013ed2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014071`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400140c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400141de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014227`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014266`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400142f4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015243`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400154ac`
- `FLTMGR!FltReferenceContext` at `0x140013e76`
- `FLTMGR!FltReferenceContext` at `0x140013e76`
- `FLTMGR!FltReleaseContext` at `0x1400140da`
- `FLTMGR!FltReleaseContext` at `0x140014240`
- `FLTMGR!FltReleaseContext` at `0x14001427f`
- `FLTMGR!FltReleaseContext` at `0x1400142c7`
- `FLTMGR!FltReleaseContext` at `0x140014346`
- `FLTMGR!FltReleaseContext` at `0x1400140da`
- `FLTMGR!FltReleaseContext` at `0x140014240`
- `FLTMGR!FltReleaseContext` at `0x14001427f`
- `FLTMGR!FltReleaseContext` at `0x1400142c7`
- `FLTMGR!FltReleaseContext` at `0x140014346`

## string_xrefs

- `0x140013c28`: `Checking requested access on non-create`
- `0x140013eb1`: `Checking requested access on non-create`
- `0x140013ff6`: `onecore\base\fs\unionfs\sys\create.cpp`
- `0x140014a12`: `onecore\base\fs\unionfs\sys\create.cpp`
- `0x140013cbe`: `PUSH: Cache lookup`
- `0x140013d5f`: `results.CacheEntry->GetOriginalScratchPath()`
- `0x14001437b`: `PUSH: Allocating scratch path for layer lookup`
- `0x1400141a2`: `PUSH: Oplock and share access check`
- `0x140013ccf`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x140013e17`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x140014008`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x140014097`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x1400141b3`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x1400142a8`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x1400143d6`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x140014541`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x14001458c`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x140014636`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x140014754`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x140014d4e`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x140014f59`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x1400151ca`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x140014106`: `PUSH: Checking caller access from cache`
- `0x14001441a`: `!results.CacheEntry`
- `0x140014d3d`: `PUSH: Allocating cache entry`
- `0x140014f43`: `PUSH: Inserting path cache payload`
- `0x140014a20`: `FileOpenCowNotInCache`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PreCreateFileOpen(
        UnionFs::UnionFsFilter *this,
        struct _FLT_CALLBACK_DATA *a2,
        struct _LIST_ENTRY *a3,
        enum _FLT_PREOP_CALLBACK_STATUS *a4,
        struct UnionFs::CreateContext *a5,
        struct UnionFs::StackEventTracer *a6,
        const struct UnionFs::UfsSiloCtx *a7)
{
  int IsFileCowable; // edi
  enum _FLT_PREOP_CALLBACK_STATUS *v8; // rsi
  struct _FLT_CALLBACK_DATA *v9; // r15
  PFILE_OBJECT Flink; // rax
  ULONG Flags; // ebx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  unsigned int v14; // ebx
  int v15; // ecx
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // ebx
  int v19; // ecx
  NTSTATUS v20; // eax
  struct _ERESOURCE *v21; // rcx
  utl::_RefCountBase *v22; // rcx
  UnionFs::Rtl *v23; // rcx
  struct _UNICODE_STRING *v24; // rdx
  const char *v25; // rax
  __int64 v26; // r8
  struct _UNICODE_STRING *v27; // rdx
  struct _UNICODE_STRING *v28; // rbx
  utl::_RefCountBase *v29; // rbx
  _QWORD *v30; // rdi
  const struct _FLT_RELATED_OBJECTS *v31; // rbx
  PFLT_IO_PARAMETER_BLOCK v32; // rax
  __int64 v33; // rbx
  unsigned __int64 *v34; // rdx
  __int64 v35; // rax
  volatile signed __int32 *v36; // rbx
  int inited; // r15d
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  struct _ERESOURCE *Thread; // rcx
  const char *v42; // rax
  __int64 v43; // r8
  void *v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  struct _ERESOURCE *v47; // rcx
  struct _ERESOURCE *v48; // rcx
  PETHREAD v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rbx
  utl::_RefCountBase *v52; // r10
  int v53; // r8d
  volatile signed __int32 *v54; // rbx
  __int64 v55; // r8
  struct _UNICODE_STRING *v56; // rdx
  __int16 v57; // ax
  unsigned __int16 v58; // ax
  __int64 v59; // rcx
  NTSTATUS v60; // ebx
  unsigned __int16 *Information; // rdi
  struct _UNICODE_STRING *v62; // rdx
  struct _UNICODE_STRING *v63; // rbx
  bool v64; // zf
  __int64 v65; // rcx
  int v66; // eax
  struct _UNICODE_STRING *v67; // rdx
  utl::_RefCountBase *v68; // rcx
  struct _UNICODE_STRING *v69; // rbx
  utl::_RefCountBase *v70; // rcx
  struct _UNICODE_STRING *v71; // rbx
  bool v72; // zf
  int v73; // eax
  struct _UNICODE_STRING *v74; // rdx
  utl::_RefCountBase *v75; // rcx
  struct _UNICODE_STRING *v76; // rbx
  enum _FLT_PREOP_CALLBACK_STATUS *v77; // rax
  utl::_RefCountBase *v78; // rcx
  struct _UNICODE_STRING *Pointer; // rbx
  PFLT_IO_PARAMETER_BLOCK v81; // rax
  UNICODE_STRING *v82; // r15
  PIO_SECURITY_CONTEXT SecurityContext; // rcx
  ACCESS_MASK DesiredAccess; // eax
  int v85; // r8d
  int v86; // r9d
  PFLT_IO_PARAMETER_BLOCK v87; // rdx
  int v88; // ecx
  struct _UNICODE_STRING *p_UnicodeString; // rax
  UNICODE_STRING *p_Source; // rax
  struct _UNICODE_STRING *v91; // rdx
  utl::_RefCountBase *v92; // rcx
  _DWORD *v93; // rcx
  PWSTR *v94; // rcx
  char *v95; // rsi
  __int64 v96; // rbx
  unsigned __int64 *v97; // rdx
  __int64 v98; // rax
  volatile signed __int32 *v99; // rbx
  struct _UNICODE_STRING *v100; // rbx
  utl::_RefCountBase *v101; // rcx
  struct _UNICODE_STRING *v102; // rbx
  utl::_RefCountBase *v103; // rcx
  struct _UNICODE_STRING *v104; // r15
  __int64 v105; // rax
  __int64 v106; // rcx
  struct _LIST_ENTRY *v107; // rbx
  int inserted; // eax
  struct _UNICODE_STRING *v109; // rdx
  utl::_RefCountBase *v110; // rcx
  struct _UNICODE_STRING *v111; // rdx
  utl::_RefCountBase *v112; // rsi
  struct _FILE_OBJECT *v113; // rbx
  int v114; // ebx
  struct _UNICODE_STRING *v115; // rdx
  struct _UNICODE_STRING *v116; // rdx
  utl::_RefCountBase *v117; // rcx
  struct _UNICODE_STRING *v118; // rbx
  struct _UNICODE_STRING *v119; // rdx
  struct _ERESOURCE *v120; // rcx
  enum _FLT_PREOP_CALLBACK_STATUS *v121; // rax
  utl::_RefCountBase *v122; // rcx
  bool v123; // al
  __int64 v124; // r8
  __int64 v125; // rax
  const char *v126; // rax
  __int64 v127; // r8
  utl::_RefCountBase *v128; // rax
  utl::_RefCountBase *v129; // rcx
  utl::_RefCountBase *v130; // rcx
  struct _ERESOURCE *v131; // rcx
  utl::_RefCountBase *v132; // rcx
  utl::_RefCountBase *v133; // rax
  utl::_RefCountBase *v134; // rcx
  struct _UNICODE_STRING *v135; // rdx
  struct _UNICODE_STRING *v136; // rdx
  struct UnionFs::StackEventTracer *v137; // [rsp+20h] [rbp-F0h]
  char *Entry; // [rsp+28h] [rbp-E8h]
  const char *Entrya; // [rsp+28h] [rbp-E8h]
  const char *Entryb; // [rsp+28h] [rbp-E8h]
  char *Entryc; // [rsp+28h] [rbp-E8h]
  const char *Entryd; // [rsp+28h] [rbp-E8h]
  const char *Entrye; // [rsp+28h] [rbp-E8h]
  bool v144; // [rsp+90h] [rbp-80h] BYREF
  char v145; // [rsp+91h] [rbp-7Fh] BYREF
  struct _FLT_CALLBACK_DATA Context; // [rsp+98h] [rbp-78h] BYREF
  PVOID v147; // [rsp+F0h] [rbp-20h]
  UnionFs::UfsPathCachePayload *v148; // [rsp+F8h] [rbp-18h] BYREF
  enum _FLT_PREOP_CALLBACK_STATUS *v149; // [rsp+100h] [rbp-10h] BYREF
  __int128 v150; // [rsp+110h] [rbp+0h] BYREF
  utl::_RefCountBase *v151[2]; // [rsp+120h] [rbp+10h]
  PERESOURCE Resource; // [rsp+130h] [rbp+20h]
  __int64 v153; // [rsp+138h] [rbp+28h]
  __int128 v154; // [rsp+140h] [rbp+30h]
  UNICODE_STRING Source; // [rsp+150h] [rbp+40h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+160h] [rbp+50h] BYREF
  utl::_RefCountBase *v157; // [rsp+170h] [rbp+60h] BYREF
  UnionFs::UfsPathCachePayload *Blink; // [rsp+178h] [rbp+68h] BYREF
  utl::_RefCountBase *v159[2]; // [rsp+180h] [rbp+70h] BYREF
  int v160; // [rsp+190h] [rbp+80h] BYREF
  int v161; // [rsp+194h] [rbp+84h] BYREF
  char v162[8]; // [rsp+198h] [rbp+88h] BYREF
  PERESOURCE v163[2]; // [rsp+1A0h] [rbp+90h]
  volatile signed __int32 *v164; // [rsp+1B0h] [rbp+A0h]
  __int64 v165; // [rsp+1B8h] [rbp+A8h]
  char v166[8]; // [rsp+1C0h] [rbp+B0h] BYREF
  __int64 v167; // [rsp+1C8h] [rbp+B8h]
  _QWORD v168[3]; // [rsp+1D0h] [rbp+C0h] BYREF
  char v169; // [rsp+1E8h] [rbp+D8h]
  struct _UNICODE_STRING *v170; // [rsp+1F0h] [rbp+E0h] BYREF
  UNICODE_STRING *v171; // [rsp+1F8h] [rbp+E8h] BYREF
  const char *v172; // [rsp+200h] [rbp+F0h] BYREF
  char v173[8]; // [rsp+208h] [rbp+F8h] BYREF
  __int128 v174; // [rsp+210h] [rbp+100h]
  utl::_RefCountBase *v175[2]; // [rsp+220h] [rbp+110h]
  __int64 v176; // [rsp+230h] [rbp+120h]
  int v177; // [rsp+238h] [rbp+128h]
  struct _UNICODE_STRING v178; // [rsp+240h] [rbp+130h] BYREF
  char v179; // [rsp+250h] [rbp+140h]
  char v180[8]; // [rsp+280h] [rbp+170h] BYREF
  _QWORD v181[15]; // [rsp+288h] [rbp+178h] BYREF
  _BYTE v182[80]; // [rsp+300h] [rbp+1F0h] BYREF
  _BYTE v183[752]; // [rsp+350h] [rbp+240h] BYREF

  IsFileCowable = 0;
  v8 = a4;
  v9 = (struct _FLT_CALLBACK_DATA *)a3;
  *a4 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
  v148 = a7;
  Flink = (PFILE_OBJECT)a3[2].Flink;
  v149 = a4;
  Context.QueueLinks.Flink = a3;
  Flags = Flink->Flags;
  Iopb = a2->Iopb;
  v14 = (Flags & 0x20000) == 0;
  if ( Iopb->MajorFunction )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("Checking requested access on non-create");
  }
  else
  {
    v15 = *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
    if ( (v15 & 0x10D0106) != 0 || (v15 & 0x2000000) != 0 )
      v14 |= 8u;
  }
  Resource = 0;
  v150 = 0;
  *(_OWORD *)v151 = 0;
  v153 = 0;
  LODWORD(v150) = _mm_cvtsi128_si32((__m128i)0LL) | 3;
  v16 = *((_QWORD *)a5 + 1);
  v154 = 0;
  if ( *(_DWORD *)(v16 + 28) == 2 )
    v17 = *(_QWORD *)(*(_QWORD *)(v16 + 32) + 16LL);
  else
    v17 = *((_QWORD *)UnionFs::g_FilterState + 10);
  Entry = (char *)a6;
  v18 = UnionFs::UfsPathCache::LookupEntry(v17, v9->IoStatus.Pointer, *(_QWORD *)a5, v14, &v150);
  if ( v18 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v18,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x21D000207EBLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
      "PUSH: Cache lookup",
      (const char *)a6);
    goto LABEL_171;
  }
  v19 = DWORD1(v150);
  v144 = 0;
  if ( !DWORD1(v150) )
    goto LABEL_27;
  if ( (BYTE8(v150) & 4) != 0 )
  {
    v20 = -1073741772;
    a2->IoStatus.Information = 0;
    if ( v19 != 1 )
      v20 = -1073741766;
    a2->IoStatus.Status = v20;
    *v8 = FLT_PREOP_COMPLETE;
    goto LABEL_16;
  }
  if ( (_DWORD)v153 == 1 )
  {
    **((_DWORD **)a5 + 20) |= 8u;
LABEL_16:
    v18 = IsFileCowable;
    goto LABEL_171;
  }
  if ( *((_WORD *)v151[0] + 80) == 4 )
  {
    if ( !*((_QWORD *)v151[0] + 26) )
      MicrosoftTelemetryAssertTriggeredMsgKM("results.CacheEntry->GetOriginalScratchPath()");
    if ( DWORD1(v150) == 1 )
      goto LABEL_16;
    goto LABEL_23;
  }
  if ( DWORD1(v150) == 1 )
  {
    v29 = v151[0];
    FltReferenceContext(*((PFLT_CONTEXT *)v151[0] + 9));
    v30 = (_QWORD *)*((_QWORD *)v29 + 9);
    *(_QWORD *)&Context.Flags = v30;
    v31 = (const struct _FLT_RELATED_OBJECTS *)v30[4];
    Context.IoStatus.Information = (ULONG_PTR)v31;
    FsFltWil::AcquireResourceExclusive(&Context.Thread, (char *)v31[2].Instance + 56);
    v32 = a2->Iopb;
    if ( v32->MajorFunction )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Checking requested access on non-create");
      goto LABEL_38;
    }
    v38 = *(_DWORD *)(v32->Parameters.WMI.ProviderId + 16);
    if ( (v38 & 0x10D0106) != 0 || (v38 & 0x2000000) != 0 )
    {
      if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
      {
        v18 = UnionFs::Utils::BreakBatchAndHOplocks((UnionFs::Utils *)a2, v9, v31, a6, v137);
        if ( v18 == 259 )
        {
          if ( (unsigned int)dword_14009E178 > 4
            && (qword_14009E188 & 0x200200) != 0
            && (qword_14009E190 & 0x200200) == qword_14009E190 )
          {
            LODWORD(Context.Iopb) = 2119;
            Context.IoStatus.Information = (ULONG_PTR)"onecore\\base\\fs\\unionfs\\sys\\create.cpp";
            v148 = (UnionFs::UfsPathCachePayload *)"UnionFs::UnionFsFilter::PreCreateFileOpen";
            Context.QueueLinks.Flink = (struct _LIST_ENTRY *)"Oplock break";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              qword_14009E190,
              (unsigned int)byte_1400963B1,
              v39,
              v40,
              (__int64)&Context.QueueLinks,
              (__int64)&v148,
              (__int64)&Context.IoStatus.Information,
              (__int64)&Context.Iopb);
            v8 = v149;
          }
          Thread = (struct _ERESOURCE *)Context.Thread;
          *v8 = FLT_PREOP_PENDING;
          if ( Thread )
          {
            ExReleaseResourceLite(Thread);
            KeLeaveCriticalRegion();
          }
          goto LABEL_91;
        }
        if ( v18 < 0 )
        {
          v42 = "PUSH: Breaking oplocks";
          v43 = 0x6F50002084ELL;
LABEL_60:
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v18,
            (int)a6,
            (struct UnionFs::StackEventTracer *)v43,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
            v42,
            (const char *)a6);
          if ( Context.Thread )
          {
            ExReleaseResourceLite((PERESOURCE)Context.Thread);
            KeLeaveCriticalRegion();
          }
          if ( !v30 )
            goto LABEL_171;
          v44 = v30;
          goto LABEL_64;
        }
      }
      v18 = UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess(v151[0], a2, a6, 1);
      if ( v18 < 0 )
      {
        v42 = "PUSH: Checking caller access from cache";
        v43 = 0x28900020859LL;
        goto LABEL_60;
      }
      v45 = *(_QWORD *)(a2->Iopb->Parameters.WMI.ProviderId + 8);
      v46 = *(unsigned int *)(v45 + 20);
      if ( (v46 & 0x10D0106) != 0 )
      {
        *(_DWORD *)&Context.RequestorMode = *(_DWORD *)(v45 + 24);
        IsFileCowable = 0;
        Entry = (char *)Context.IoStatus.Information;
        *(_WORD *)(&Context.RequestorMode + 5) = 0;
        *(&Context.RequestorMode + 7) = 0;
        *(_WORD *)((char *)&v147 + 5) = 0;
        HIBYTE(v147) = 0;
        *(&Context.RequestorMode + 4) = 0;
        LODWORD(v147) = 0;
        Context.QueueContext[1] = (PVOID)((unsigned int)v46 | 0x300000000LL);
        BYTE4(v147) = 1;
        v144 = 0;
        v18 = UnionFs::UnionFsFilter::CheckOplockAndShareAccess(v46, a2, v9, &Context, &Context.FilterContext[3]);
        if ( v18 >= 0 )
        {
          v47 = (struct _ERESOURCE *)Context.Thread;
          if ( v18 == 259 )
          {
            *v8 = FLT_PREOP_PENDING;
            if ( v47 )
            {
              ExReleaseResourceLite(v47);
              KeLeaveCriticalRegion();
            }
            if ( *(_QWORD *)&Context.Flags )
              FltReleaseContext(*(PFLT_CONTEXT *)&Context.Flags);
            goto LABEL_16;
          }
          v144 = 1;
          if ( Context.Thread )
          {
            ExReleaseResourceLite((PERESOURCE)Context.Thread);
            KeLeaveCriticalRegion();
          }
          if ( *(_QWORD *)&Context.Flags )
            FltReleaseContext(*(PFLT_CONTEXT *)&Context.Flags);
          goto LABEL_27;
        }
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v18,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x59E0002087FLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
          "PUSH: Oplock and share access check",
          Entry);
        if ( Context.Thread )
        {
          ExReleaseResourceLite((PERESOURCE)Context.Thread);
          KeLeaveCriticalRegion();
        }
        v44 = *(void **)&Context.Flags;
        if ( !*(_QWORD *)&Context.Flags )
          goto LABEL_171;
LABEL_64:
        FltReleaseContext(v44);
        goto LABEL_171;
      }
    }
LABEL_38:
    if ( Context.Thread )
    {
      ExReleaseResourceLite((PERESOURCE)Context.Thread);
      KeLeaveCriticalRegion();
    }
    v33 = *((_QWORD *)a5 + 1);
    *(_QWORD *)&Context.Flags = v9->IoStatus.Information;
    v148 = v151[0];
    FsFltWil::AcquirePushLockShared(&Context.IoStatus.Information, v33 + 72);
    v35 = *(_QWORD *)(v33 + 48);
    v36 = *(volatile signed __int32 **)(v35 + 8);
    Context.Thread = *(const PETHREAD *)v35;
    if ( v36 )
      _InterlockedIncrement(v36 + 2);
    if ( Context.IoStatus.Information )
      FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Context.IoStatus.Information, v34);
    LODWORD(Entry) = 4;
    inited = UnionFs::UfsShadowFileObject::SetUp(
               *(struct _FILE_OBJECT **)&Context.Flags,
               a2,
               v148,
               (struct UnionFs::StackEventTracer *)Entry,
               (__int64)a5 + 160,
               a6);
    if ( v36 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v36);
    if ( inited == 259 )
    {
      *v8 = FLT_PREOP_PENDING;
    }
    else
    {
      if ( inited < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)inited,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x21E000208A8LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
          "PUSH: Setting up shadow file object",
          Entrya);
        if ( v30 )
          FltReleaseContext(v30);
        goto LABEL_87;
      }
      v48 = Resource;
      Resource = 0;
      if ( v48 )
      {
        ExReleaseResourceLite(v48);
        KeLeaveCriticalRegion();
      }
      UnionFs::UnionFsFilter::HandleQoCEcpCached(
        (UnionFs::UnionFsFilter *)v48,
        a2,
        (const struct _FLT_RELATED_OBJECTS *)Context.QueueLinks.Flink,
        *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
        *((struct UnionFs::UfsUnionCtx **)a5 + 1),
        v151[0],
        a6);
      a2->IoStatus.Status = 0;
      a2->IoStatus.Information = 1;
      *v8 = FLT_PREOP_COMPLETE;
    }
LABEL_91:
    if ( v30 )
      FltReleaseContext(v30);
    IsFileCowable = 0;
    goto LABEL_16;
  }
LABEL_23:
  v21 = Resource;
  Resource = 0;
  if ( v21 )
  {
    ExReleaseResourceLite(v21);
    KeLeaveCriticalRegion();
  }
  v22 = v151[1];
  v151[1] = 0;
  v151[0] = 0;
  if ( v22 )
    utl::_RefCountBase::_DecStrong(v22);
LABEL_27:
  Context.Thread = 0;
  if ( (_DWORD)v153 != 2 )
    goto LABEL_95;
  v23 = (UnionFs::Rtl *)(*(_QWORD *)a5 + 8LL);
  Source = (UNICODE_STRING)**((_OWORD **)&v154 + 1);
  UnicodeString = *(struct _UNICODE_STRING *)v154;
  IsFileCowable = UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(
                    v23,
                    &UnicodeString,
                    &Source,
                    (PVOID)&Context.Thread,
                    (int)a6);
  if ( IsFileCowable < 0 )
  {
    v25 = "PUSH: Replacing substring";
    v26 = 0x381000208D9LL;
LABEL_30:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)IsFileCowable,
      (int)a6,
      (struct UnionFs::StackEventTracer *)v26,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
      v25,
      Entry);
    v28 = (struct _UNICODE_STRING *)Context.Thread;
    goto LABEL_31;
  }
  v49 = Context.Thread;
  if ( !Context.Thread )
  {
LABEL_95:
    IsFileCowable = UnionFs::UfsPathName::AllocAndInit(*(_QWORD *)a5, &Context.Thread, a6);
    if ( IsFileCowable < 0 )
    {
      v25 = "PUSH: Allocating scratch path for layer lookup";
      v26 = 0x391000208E4LL;
      goto LABEL_30;
    }
    v49 = Context.Thread;
  }
  v50 = *((_QWORD *)a5 + 20);
  Context.Thread = 0;
  v51 = *(_QWORD *)(v50 + 64);
  *(_QWORD *)(v50 + 64) = v49;
  if ( v51 )
  {
    if ( !*(_BYTE *)(v51 + 16) )
      *(_OWORD *)v51 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v51, v24);
    ExFreePoolWithTag((PVOID)v51, 0);
  }
  Context.IoStatus.Pointer = 0;
  if ( !v144 )
  {
    if ( v151[0] )
      MicrosoftTelemetryAssertTriggeredMsgKM("!results.CacheEntry");
    v181[0] = off_14007E768;
    v181[13] = v181;
    UnionFs::StackEventTracer::SetIgnoreStatusCallback(a6, v180);
    memset(v182, 0, 0x48u);
    inited = UnionFs::Utils::StatItemAsCaller(*(_QWORD *)a5 + 8LL, v9->IoStatus.Pointer, v55, v182, a2);
    v57 = *((_WORD *)a6 + 245);
    if ( v57 )
    {
      v58 = v57 - 1;
      *((_WORD *)a6 + 245) = v58;
      v59 = 120 * (v58 + 1LL);
      v56 = *(struct _UNICODE_STRING **)((char *)a6 + v59);
      *(_QWORD *)((char *)a6 + v59) = 0;
      if ( v56 )
        (*(void (__fastcall **)(struct _UNICODE_STRING *))(*(_QWORD *)&v56->Length + 24LL))(v56);
    }
    if ( inited == 260 )
      goto LABEL_141;
    if ( (a2->Iopb->OperationFlags & 4) != 0 && inited == -1073741772 )
    {
      v60 = -1073741766;
      inited = -1073741766;
    }
    else
    {
      if ( inited >= 0 )
      {
LABEL_166:
        Pointer = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
        if ( Context.IoStatus.Pointer )
        {
          if ( !*((_BYTE *)Context.IoStatus.Pointer + 16) )
            *(_OWORD *)Context.IoStatus.Pointer = 0;
          FsFltWil::Details::FreeUnicodeString(Pointer, v56);
          ExFreePoolWithTag(Pointer, 0);
        }
        v18 = 0;
        goto LABEL_171;
      }
      v60 = -1073741766;
      if ( inited != -1073741766 && inited != -1073741772 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)inited,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x28B00020925LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
          "PUSH: Querying stat information",
          (const char *)a6);
        v63 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
        if ( !Context.IoStatus.Pointer )
        {
LABEL_87:
          v18 = inited;
          goto LABEL_171;
        }
        v64 = *((_BYTE *)Context.IoStatus.Pointer + 16) == 0;
LABEL_122:
        if ( v64 )
          *v63 = 0;
        FsFltWil::Details::FreeUnicodeString(v63, v62);
        ExFreePoolWithTag(v63, 0);
        goto LABEL_87;
      }
    }
    utl::make_unique<UnionFs::FindAndStatResults,,0>(&Context.IoStatus.Information);
    Information = (unsigned __int16 *)Context.IoStatus.Information;
    if ( !Context.IoStatus.Information )
    {
      IsFileCowable = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x3FC00020937LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
        "ORIGIN: Allocating findAndStatResults",
        (const char *)a6);
      v28 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
LABEL_31:
      if ( v28 )
      {
        if ( !LOBYTE(v28[1].Length) )
          *v28 = 0;
        FsFltWil::Details::FreeUnicodeString(v28, v27);
        ExFreePoolWithTag(v28, 0);
      }
      goto LABEL_16;
    }
    *(_QWORD *)(Context.IoStatus.Information + 96) = &Context.IoStatus;
    v65 = *((_QWORD *)a5 + 1);
    Entry = (char *)Information;
    Source = *(UNICODE_STRING *)*(_QWORD *)(*((_QWORD *)a5 + 20) + 64LL);
    v66 = UnionFs::UfsUnionCtx::FindAndStatItemInLayersAsCaller(v65, a2, &Source);
    LODWORD(Context.Iopb) = v66;
    if ( v66 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v66,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x28C00020942LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
        "PUSH: Statting item in layers",
        (const char *)Information);
LABEL_127:
      if ( Information )
      {
        v68 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
        if ( v68 )
          utl::_RefCountBase::_DecStrong(v68);
        ExFreePoolWithTag(Information, 0);
      }
      v69 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
      if ( Context.IoStatus.Pointer )
      {
        if ( !*((_BYTE *)Context.IoStatus.Pointer + 16) )
          *(_OWORD *)Context.IoStatus.Pointer = 0;
        FsFltWil::Details::FreeUnicodeString(v69, v67);
        ExFreePoolWithTag(v69, 0);
      }
      v18 = (int)Context.Iopb;
      goto LABEL_171;
    }
    if ( v66 == 260 )
    {
      if ( Information )
      {
        v70 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
        if ( v70 )
          utl::_RefCountBase::_DecStrong(v70);
        ExFreePoolWithTag(Information, 0);
      }
LABEL_141:
      v71 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
      if ( !Context.IoStatus.Pointer )
      {
LABEL_146:
        v18 = 260;
        goto LABEL_171;
      }
      v72 = *((_BYTE *)Context.IoStatus.Pointer + 16) == 0;
LABEL_143:
      if ( v72 )
        *v71 = 0;
      FsFltWil::Details::FreeUnicodeString(v71, v56);
      ExFreePoolWithTag(v71, 0);
      goto LABEL_146;
    }
    v73 = *Information;
    if ( (_WORD)v73 != 1 )
    {
      if ( v73 == 2 )
      {
        if ( inited == -1073741772 )
          v60 = -1073741772;
      }
      else
      {
        if ( v73 != 3 )
        {
          MicrosoftTelemetryAssertTriggeredMsgKM("false");
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC00000E5LL,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x60B00020968LL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
            "ORIGIN: Unexpected LAYER_FIND_RESULT",
            (const char *)Information);
          if ( Information )
          {
            v75 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
            if ( v75 )
              utl::_RefCountBase::_DecStrong(v75);
            ExFreePoolWithTag(Information, 0);
          }
          v76 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
          if ( Context.IoStatus.Pointer )
          {
            if ( !*((_BYTE *)Context.IoStatus.Pointer + 16) )
              *(_OWORD *)Context.IoStatus.Pointer = 0;
            FsFltWil::Details::FreeUnicodeString(v76, v74);
            ExFreePoolWithTag(v76, 0);
          }
          v18 = -1073741595;
          goto LABEL_171;
        }
        v60 = (a2->Iopb->OperationFlags & 4) != 0 ? -1073741766 : -1073741772;
      }
      v77 = v149;
      a2->IoStatus.Status = v60;
      a2->IoStatus.Information = 0;
      *v77 = FLT_PREOP_COMPLETE;
      if ( Information )
      {
        v78 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
        if ( v78 )
          utl::_RefCountBase::_DecStrong(v78);
        ExFreePoolWithTag(Information, 0);
      }
      goto LABEL_166;
    }
    v81 = a2->Iopb;
    v82 = (UNICODE_STRING *)Context.IoStatus.Pointer;
    v53 = *((_DWORD *)Information + 16);
    Context.IoStatus.Information = (ULONG_PTR)Context.IoStatus.Pointer;
    SecurityContext = v81->Parameters.Create.SecurityContext;
    LODWORD(Context.Iopb) = v53;
    DesiredAccess = SecurityContext->DesiredAccess;
    if ( (DesiredAccess & 0x2000000) != 0 )
    {
      if ( (*((_DWORD *)Information + 19) & 0x10D0106) != 0 )
        goto LABEL_174;
    }
    else if ( (DesiredAccess & 0x10D0106) != 0 )
    {
LABEL_174:
      if ( (unsigned int)dword_14009E178 > 5
        && (qword_14009E188 & 0x10000) != 0
        && (qword_14009E190 & 0x10000) == qword_14009E190 )
      {
        UnicodeString = 0;
        UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v183, 0x1D00020A48uLL);
        UnionFs::Utils::GetUserSidString(a2, &UnicodeString, v183);
        Source = *v82;
        if ( (unsigned int)dword_14009E178 > 5
          && (qword_14009E188 & 0x30200) != 0
          && (qword_14009E190 & 0x30200) == qword_14009E190 )
        {
          v87 = a2->Iopb;
          LODWORD(Context.TagData) = *((_DWORD *)Information + 19);
          *(_QWORD *)v166 = "UnionFs::UnionFsFilter::PreCreateFileOpen";
          v160 = *(_DWORD *)(*(_QWORD *)(v87->Parameters.WMI.ProviderId + 8) + 24LL);
          v161 = *(_DWORD *)(*(_QWORD *)(v87->Parameters.WMI.ProviderId + 8) + 20LL);
          LODWORD(v157) = *(_DWORD *)(*(_QWORD *)(v87->Parameters.WMI.ProviderId + 8) + 16LL);
          LODWORD(Blink) = *(_DWORD *)(*(_QWORD *)(v87->Parameters.WMI.ProviderId + 8) + 12LL);
          LODWORD(v149) = *(_DWORD *)(v87->Parameters.WMI.ProviderId + 16);
          v88 = *(_DWORD *)(v87->Parameters.WMI.ProviderId + 16);
          p_UnicodeString = &UnicodeString;
          Context.Flags = 2661;
          v144 = (v88 & 0x2000000) != 0;
          if ( !UnicodeString.Buffer )
            p_UnicodeString = (struct _UNICODE_STRING *)&FsTlEmptyUnicodeString;
          v170 = p_UnicodeString;
          p_Source = &Source;
          if ( !Source.Buffer )
            p_Source = (UNICODE_STRING *)&FsTlEmptyUnicodeString;
          v171 = p_Source;
          v172 = "onecore\\base\\fs\\unionfs\\sys\\create.cpp";
          Context.QueueLinks.Blink = (struct _LIST_ENTRY *)"FileOpenCowNotInCache";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&FsTlEmptyUnicodeString,
            (unsigned int)&word_14009601E,
            v85,
            v86,
            (__int64)&Context.QueueLinks.Blink,
            (__int64)v166,
            (__int64)&v172,
            (__int64)&Context,
            (__int64)&v171,
            (__int64)&v170,
            (__int64)&v144,
            (__int64)&v149,
            (__int64)&Blink,
            (__int64)&v157,
            (__int64)&v161,
            (__int64)&v160,
            (__int64)&Context.TagData);
        }
        UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v183);
        FsFltWil::Details::FreeUnicodeString(&UnicodeString, v91);
        v53 = (int)Context.Iopb;
      }
      v54 = (volatile signed __int32 *)*((_QWORD *)Information + 11);
      *(_QWORD *)&Context.Flags = *((_QWORD *)Information + 10);
      if ( v54 )
        _InterlockedIncrement(v54 + 2);
      if ( Information )
      {
        v92 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
        if ( v92 )
          utl::_RefCountBase::_DecStrong(v92);
        ExFreePoolWithTag(Information, 0);
        v53 = (int)Context.Iopb;
      }
      v9 = (struct _FLT_CALLBACK_DATA *)Context.QueueLinks.Flink;
      v52 = v151[0];
      goto LABEL_193;
    }
    *(_QWORD *)v166 = *((_QWORD *)&v154 + 1);
    v167 = v154;
    *(_OWORD *)&Context.FilterContext[3] = 0;
    v147 = 0;
    *(_QWORD *)&Context.Flags = 0;
    LODWORD(Context.TagData) = 0;
    v144 = 0;
    v145 = 0;
    if ( !UnionFs::Utils::GetQueryOnCreateEcp(a2, &Context, (struct _QUERY_ON_CREATE_ECP_CONTEXT **)&Context.TagData, 0) )
    {
LABEL_212:
      v94 = (PWSTR *)*((_QWORD *)Information + 10);
      v95 = v166;
      v168[0] = &v144;
      v169 = 1;
      v168[1] = &Context;
      if ( (_DWORD)v153 != 2 )
        v95 = 0;
      v168[2] = &v145;
      UnicodeString = 0;
      _InterlockedIncrement((volatile signed __int32 *)*v94 + 2);
      v96 = *((_QWORD *)a5 + 1);
      *(_QWORD *)&UnicodeString.Length = v94;
      UnicodeString.Buffer = *v94;
      FsFltWil::AcquirePushLockShared(&Context.IoStatus.Information, v96 + 72);
      v98 = *(_QWORD *)(v96 + 48);
      v99 = *(volatile signed __int32 **)(v98 + 8);
      v148 = *(UnionFs::UfsPathCachePayload **)v98;
      if ( v99 )
        _InterlockedIncrement(v99 + 2);
      if ( Context.IoStatus.Information )
        FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Context.IoStatus.Information, v97);
      inited = UnionFs::UfsPathCachePayload::AllocAndInitShared(
                 a2,
                 (__int64)v148,
                 (struct _LIST_ENTRY **)&UnicodeString,
                 (LIST_ENTRY *)v82,
                 (int)Context.Iopb,
                 (struct _UNICODE_STRING *)&Context.FilterContext[3],
                 a6,
                 (__int64)v95);
      if ( v99 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v99);
      if ( inited < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)inited,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x438000209D4LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
          "PUSH: Allocating cache entry",
          Entryb);
        if ( v144 )
        {
          **(_DWORD **)&Context.Flags |= 4u;
          *(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) |= 4u;
        }
        if ( v145 )
          **(_DWORD **)&Context.Flags |= 8u;
        v100 = (struct _UNICODE_STRING *)v147;
        if ( v147 )
        {
          if ( !*((_BYTE *)v147 + 16) )
            *(_OWORD *)v147 = 0;
          FsFltWil::Details::FreeUnicodeString(v100, v62);
          ExFreePoolWithTag(v100, 0);
        }
        if ( *(_QWORD *)&Context.RequestorMode )
          utl::_RefCountBase::_DecStrong(*(utl::_RefCountBase **)&Context.RequestorMode);
        if ( Information )
        {
          v101 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
          if ( v101 )
            utl::_RefCountBase::_DecStrong(v101);
          ExFreePoolWithTag(Information, 0);
        }
        v63 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
        if ( !Context.IoStatus.Pointer )
          goto LABEL_87;
        v64 = *((_BYTE *)Context.IoStatus.Pointer + 16) == 0;
        goto LABEL_122;
      }
      if ( inited == 260 )
      {
        if ( v144 )
        {
          **(_DWORD **)&Context.Flags |= 4u;
          *(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) |= 4u;
        }
        if ( v145 )
          **(_DWORD **)&Context.Flags |= 8u;
        v102 = (struct _UNICODE_STRING *)v147;
        if ( v147 )
        {
          if ( !*((_BYTE *)v147 + 16) )
            *(_OWORD *)v147 = 0;
          FsFltWil::Details::FreeUnicodeString(v102, v56);
          ExFreePoolWithTag(v102, 0);
        }
        if ( *(_QWORD *)&Context.RequestorMode )
          utl::_RefCountBase::_DecStrong(*(utl::_RefCountBase **)&Context.RequestorMode);
        if ( Information )
        {
          v103 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
          if ( v103 )
            utl::_RefCountBase::_DecStrong(v103);
          ExFreePoolWithTag(Information, 0);
        }
        v71 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
        if ( !Context.IoStatus.Pointer )
          goto LABEL_146;
        v72 = *((_BYTE *)Context.IoStatus.Pointer + 16) == 0;
        goto LABEL_143;
      }
      v104 = (struct _UNICODE_STRING *)v147;
      *(_OWORD *)&Context.FilterContext[1] = *(_OWORD *)&Context.FilterContext[3];
      v105 = *((_QWORD *)a5 + 1);
      *(_OWORD *)&Context.FilterContext[3] = 0;
      v147 = 0;
      Context.IoStatus.Information = (ULONG_PTR)v104;
      v64 = *(_DWORD *)(v105 + 28) == 2;
      *(_QWORD *)v162 = 0;
      *(_OWORD *)v163 = 0;
      v164 = 0;
      v165 = 0;
      if ( v64 )
        v106 = *(_QWORD *)(*(_QWORD *)(v105 + 32) + 16LL);
      else
        v106 = *((_QWORD *)UnionFs::g_FilterState + 10);
      v107 = Context.QueueLinks.Flink;
      Entryc = v162;
      inserted = UnionFs::UfsPathCache::InsertEntry(
                   v106,
                   Context.QueueLinks.Flink[1].Blink,
                   v104,
                   1,
                   &Context.FilterContext[1]);
      LODWORD(Context.Iopb) = inserted;
      if ( inserted < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)inserted,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x43E000209EALL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
          "PUSH: Inserting path cache payload",
          v162);
        UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v162);
        if ( v104 )
        {
          if ( !LOBYTE(v104[1].Length) )
            *v104 = 0;
          FsFltWil::Details::FreeUnicodeString(v104, v109);
          ExFreePoolWithTag(v104, 0);
        }
        v110 = (utl::_RefCountBase *)Context.QueueContext[0];
LABEL_263:
        if ( v110 )
          utl::_RefCountBase::_DecStrong(v110);
        wil::details::lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___::_lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___(v168);
        utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(&Context.FilterContext[3]);
        goto LABEL_127;
      }
      if ( *(_DWORD *)v162 == 2 )
      {
        v112 = (utl::_RefCountBase *)v164;
        Blink = (UnionFs::UfsPathCachePayload *)v163[1];
        v157 = (utl::_RefCountBase *)v164;
        if ( v164 )
          _InterlockedIncrement(v164 + 2);
        if ( Context.QueueContext[0] )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Context.QueueContext[0]);
      }
      else
      {
        if ( *(_DWORD *)v162 == 3 )
        {
          if ( (v165 & 1) == 0 )
            MicrosoftTelemetryAssertTriggeredMsgKM("WI_IsFlagSet(insertResults.Flags, InsertEntryResultsFlags::StoppedOnHardTombstone)");
          UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v162);
          if ( v104 )
          {
            if ( !LOBYTE(v104[1].Length) )
              *v104 = 0;
            FsFltWil::Details::FreeUnicodeString(v104, v111);
            ExFreePoolWithTag(v104, 0);
          }
          if ( Context.QueueContext[0] )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Context.QueueContext[0]);
          goto LABEL_291;
        }
        v112 = (utl::_RefCountBase *)Context.QueueContext[0];
        v157 = (utl::_RefCountBase *)Context.QueueContext[0];
        Blink = (UnionFs::UfsPathCachePayload *)Context.QueueLinks.Blink;
      }
      v113 = (struct _FILE_OBJECT *)v107[2].Flink;
      UnionFs::UfsUnionCtx::GetScratchLayer(*((_QWORD *)a5 + 1), &Source);
      LODWORD(Entryc) = 5;
      v114 = UnionFs::UfsShadowFileObject::SetUp(
               v113,
               a2,
               Blink,
               (struct UnionFs::StackEventTracer *)Entryc,
               (__int64)a5 + 160,
               a6);
      LODWORD(Context.Iopb) = v114;
      if ( Source.Buffer )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Source.Buffer);
      if ( v114 != 259 )
      {
        if ( v114 >= 0 )
        {
          v120 = v163[0];
          v18 = 0;
          v163[0] = 0;
          if ( v120 )
          {
            ExReleaseResourceLite(v120);
            KeLeaveCriticalRegion();
          }
          if ( v145 )
          {
            *(_QWORD *)(*(_QWORD *)&Context.Flags + 152LL) = 0;
            *(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) |= 8u;
          }
          UnionFs::UnionFsFilter::VirtualizeQoCEcpIDs(
            (UnionFs::UnionFsFilter *)v120,
            a2,
            (const struct _FLT_RELATED_OBJECTS *)Context.QueueLinks.Flink,
            *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
            *((struct UnionFs::UfsUnionCtx **)a5 + 1),
            a6,
            *(struct _QUERY_ON_CREATE_ECP_CONTEXT **)&Context.Flags,
            (unsigned int)Context.TagData);
          v121 = v149;
          a2->IoStatus.Status = 0;
          a2->IoStatus.Information = 1;
          *v121 = FLT_PREOP_COMPLETE;
          UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v162);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.IoStatus.Information);
          if ( v112 )
            utl::_RefCountBase::_DecStrong(v112);
          wil::details::lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___::_lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___(v168);
          utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(&Context.FilterContext[3]);
          if ( Information )
          {
            v122 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
            if ( v122 )
              utl::_RefCountBase::_DecStrong(v122);
            ExFreePoolWithTag(Information, 0);
          }
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.IoStatus);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.Thread);
          goto LABEL_171;
        }
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v114,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x45100020A24LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
          "PUSH: Setting up shadow file object",
          Entryd);
        UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v162);
        if ( v104 )
        {
          if ( !LOBYTE(v104[1].Length) )
            *v104 = 0;
          FsFltWil::Details::FreeUnicodeString(v104, v119);
          ExFreePoolWithTag(v104, 0);
        }
        v110 = v157;
        goto LABEL_263;
      }
      *v149 = FLT_PREOP_PENDING;
      UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v162);
      if ( v104 )
      {
        if ( !LOBYTE(v104[1].Length) )
          *v104 = 0;
        FsFltWil::Details::FreeUnicodeString(v104, v115);
        ExFreePoolWithTag(v104, 0);
      }
      if ( v112 )
        utl::_RefCountBase::_DecStrong(v112);
LABEL_291:
      wil::details::lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___::_lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___(v168);
      utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(&Context.FilterContext[3]);
      if ( Information )
      {
        v117 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
        if ( v117 )
          utl::_RefCountBase::_DecStrong(v117);
        ExFreePoolWithTag(Information, 0);
      }
      v118 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
      if ( Context.IoStatus.Pointer )
      {
        if ( !*((_BYTE *)Context.IoStatus.Pointer + 16) )
          *(_OWORD *)Context.IoStatus.Pointer = 0;
        FsFltWil::Details::FreeUnicodeString(v118, v116);
        ExFreePoolWithTag(v118, 0);
      }
      v18 = 0;
      goto LABEL_171;
    }
    v93 = *(_DWORD **)&Context.Flags;
    if ( (**(_DWORD **)&Context.Flags & 4) == 0 )
    {
LABEL_210:
      if ( (*v93 & 8) != 0 )
      {
        *v93 &= ~8u;
        v145 = 1;
      }
      goto LABEL_212;
    }
    if ( LODWORD(Context.TagData) >= 0x88 )
    {
      if ( (int)UnionFs::UnionFsFilter::HandleQoCEcpEaInfo(
                  *(UnionFs::UnionFsFilter **)&Context.Flags,
                  a2,
                  (const struct _FLT_RELATED_OBJECTS *)Context.QueueLinks.Flink,
                  *((struct UnionFs::UfsUnionCtx **)a5 + 1),
                  *(struct _QUERY_ON_CREATE_ECP_CONTEXT **)&Context.Flags,
                  a6) >= 0 )
        goto LABEL_208;
      *(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) |= 4u;
    }
    else
    {
      *(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) |= 4u;
    }
    *(_DWORD *)(*(_QWORD *)&Context.Flags + 8LL) |= 4u;
LABEL_208:
    v93 = *(_DWORD **)&Context.Flags;
    if ( (*(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) & 4) != 0 )
    {
      **(_DWORD **)&Context.Flags &= ~4u;
      *(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) &= ~4u;
      v93 = *(_DWORD **)&Context.Flags;
      v144 = 1;
    }
    goto LABEL_210;
  }
  v52 = v151[0];
  v53 = 0;
  v54 = (volatile signed __int32 *)*((_QWORD *)v151[0] + 5);
  *(_QWORD *)&Context.Flags = *((_QWORD *)v151[0] + 4);
  if ( v54 )
  {
    _InterlockedIncrement(v54 + 2);
    v52 = v151[0];
  }
  Context.IoStatus.Information = *((_QWORD *)v52 + 6);
LABEL_193:
  if ( (*(_DWORD *)(*((_QWORD *)a5 + 1) + 24LL) & 0x80u) != 0 )
  {
    v144 = 0;
    if ( v52 )
    {
      IsFileCowable = UnionFs::Utils::IsFileCowable((UnionFs::Utils *)&v144, (bool *)v52, a6, 0);
      if ( IsFileCowable < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)IsFileCowable,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x78100020A7CLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
          "PUSH: Checking immutability",
          Entry);
LABEL_197:
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.IoStatus);
        if ( v54 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v54);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.Thread);
        goto LABEL_16;
      }
      v52 = v151[0];
      v123 = v144;
    }
    else
    {
      v123 = (v53 & 0x800010) != 0;
    }
    if ( !v123 )
    {
      if ( (unsigned int)dword_14009E178 > 5
        && (qword_14009E188 & 0x400000000000LL) != 0
        && (qword_14009E190 & 0x400000000000LL) == qword_14009E190 )
      {
        Context.QueueLinks.Blink = (struct _LIST_ENTRY *)1;
        *(_QWORD *)v166 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          qword_14009E190,
          (unsigned int)&word_140096486,
          v53,
          (unsigned int)v166,
          (__int64)&Context.QueueLinks.Blink);
      }
      IsFileCowable = -1073741790;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000022LL,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x78200020A8ELL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
        "ORIGIN: Rejecting COW for immutable file",
        Entry);
      goto LABEL_197;
    }
  }
  LOBYTE(Context.FilterContext[2]) = 1;
  Context.QueueLinks.Blink = (struct _LIST_ENTRY *)v159;
  *(_OWORD *)v159 = 0;
  if ( v52 )
  {
    v124 = v154;
    *(_QWORD *)&Source.Length = *((_QWORD *)a5 + 1);
    v125 = *((_QWORD *)a5 + 2);
    Source.Buffer = (PWSTR)v125;
    if ( v125 )
      _InterlockedIncrement((volatile signed __int32 *)(v125 + 8));
    IsFileCowable = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(v52, &Source, v124, 10, a6);
    if ( IsFileCowable < 0 )
    {
      v126 = "PUSH: ConvertToSoftTombstone for COW";
      v127 = 0x38E00020AAALL;
LABEL_330:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)IsFileCowable,
        (int)a6,
        (struct UnionFs::StackEventTracer *)v127,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
        v126,
        Entry);
LABEL_331:
      wil::details::lambda_call__lambda_8adacc60e5fc4569c8f45e3a3a515882___::_lambda_call__lambda_8adacc60e5fc4569c8f45e3a3a515882___(&Context.FilterContext[1]);
      if ( v159[1] )
        utl::_RefCountBase::_DecStrong(v159[1]);
      goto LABEL_197;
    }
    v128 = v151[1];
    v129 = v151[0];
    if ( v151[1] )
      _InterlockedIncrement((volatile signed __int32 *)v151[1] + 2);
    v159[0] = v129;
    v130 = v159[1];
    v159[1] = v128;
    if ( v130 )
      utl::_RefCountBase::_DecStrong(v130);
    v131 = Resource;
    Resource = 0;
    if ( v131 )
    {
      ExReleaseResourceLite(v131);
      KeLeaveCriticalRegion();
    }
  }
  IsFileCowable = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
                    *((UnionFs::UfsUnionCtx **)a5 + 1),
                    a2,
                    (const struct _FLT_RELATED_OBJECTS *)v9,
                    *(const struct _FLT_FILE_NAME_INFORMATION **)a5,
                    *(const struct UnionFs::UfsPathName **)(*((_QWORD *)a5 + 20) + 64LL),
                    *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
                    *(const struct UnionFs::UfsLayerCtx **)&Context.Flags,
                    a6,
                    v148);
  if ( IsFileCowable < 0 )
  {
    v126 = "PUSH: Preparing for COW";
    v127 = 0x29800020ABCLL;
    goto LABEL_330;
  }
  v132 = v151[0];
  *(_QWORD *)v173 = *((_QWORD *)a5 + 1);
  v133 = v151[1];
  v176 = 0;
  v177 = 22;
  v174 = 0;
  *(_OWORD *)v175 = 0;
  if ( v151[1] )
    _InterlockedIncrement((volatile signed __int32 *)v151[1] + 2);
  *((_QWORD *)&v174 + 1) = v132;
  v134 = v175[0];
  v175[0] = v133;
  if ( v134 )
    utl::_RefCountBase::_DecStrong(v134);
  UnionFs::UfsPathName::UfsPathName(
    (UnionFs::UfsPathName *)&v178,
    (const struct _UNICODE_STRING *)(*(_QWORD *)a5 + 8LL),
    *(_WORD *)(*(_QWORD *)a5 + 24LL));
  IsFileCowable = UnionFs::Utils::CopyItem(
                    (_DWORD)a2,
                    Context.Flags,
                    Context.IoStatus.Information,
                    v9->IoStatus.Pointer,
                    &v178,
                    (__int64)v173,
                    (struct _FILE_OBJECT *)a6,
                    0);
  if ( IsFileCowable < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)IsFileCowable,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x28F00020ACDLL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
      "PUSH: Performing COW",
      Entrye);
    if ( !v179 )
      v178 = 0;
    FsFltWil::Details::FreeUnicodeString(&v178, v136);
    if ( v175[0] )
      utl::_RefCountBase::_DecStrong(v175[0]);
    goto LABEL_331;
  }
  LOBYTE(Context.FilterContext[2]) = 0;
  if ( !v179 )
    v178 = 0;
  FsFltWil::Details::FreeUnicodeString(&v178, v135);
  if ( v175[0] )
    utl::_RefCountBase::_DecStrong(v175[0]);
  wil::details::lambda_call__lambda_8adacc60e5fc4569c8f45e3a3a515882___::_lambda_call__lambda_8adacc60e5fc4569c8f45e3a3a515882___(&Context.FilterContext[1]);
  if ( v159[1] )
    utl::_RefCountBase::_DecStrong(v159[1]);
  utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.IoStatus);
  if ( v54 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v54);
  utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.Thread);
  v18 = 0;
LABEL_171:
  UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v150);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x140013bb0  mov     [rsp-8+arg_0], rbx
0x140013bb5  push    rbp
0x140013bb6  push    rsi
0x140013bb7  push    rdi
0x140013bb8  push    r12
0x140013bba  push    r13
0x140013bbc  push    r14
0x140013bbe  push    r15
0x140013bc0  lea     rbp, [rsp-540h]
0x140013bc8  sub     rsp, 650h
0x140013bcf  mov     rax, cs:__security_cookie
0x140013bd6  xor     rax, rsp
0x140013bd9  mov     [rbp+570h+var_40], rax
0x140013be0  mov     rax, [rbp+570h+arg_30]
0x140013be7  xor     edi, edi
0x140013be9  mov     r12, [rbp+570h+arg_20]
0x140013bf0  mov     rsi, r9
0x140013bf3  mov     r14, [rbp+570h+arg_28]
0x140013bfa  mov     r15, r8
0x140013bfd  mov     [r9], edi
0x140013c00  mov     r13, rdx
0x140013c03  mov     [rbp+570h+var_588], rax
0x140013c07  mov     rax, [r8+20h]
0x140013c0b  mov     [rbp+570h+var_580], r9
0x140013c0f  mov     [rbp+570h+var_5B8], r8
0x140013c13  mov     ebx, [rax+50h]
0x140013c16  mov     rax, [rdx+10h]
0x140013c1a  shr     ebx, 11h
0x140013c1d  not     ebx
0x140013c1f  and     ebx, 1
0x140013c22  cmp     [rax+4], dil
0x140013c26  jz      short loc_140013C36
0x140013c28  lea     rcx, aCheckingReques; "Checking requested access on non-create"
0x140013c2f  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140013c34  jmp     short loc_140013C4E
0x140013c36  mov     rax, [rax+18h]
0x140013c3a  mov     ecx, [rax+10h]
0x140013c3d  test    ecx, 10D0106h
0x140013c43  jnz     short loc_140013C4B
0x140013c45  bt      ecx, 19h
0x140013c49  jnb     short loc_140013C4E
0x140013c4b  or      ebx, 8
0x140013c4e  xorps   xmm1, xmm1
0x140013c51  mov     [rbp+570h+Resource], rdi
0x140013c55  movd    eax, xmm1
0x140013c59  xorps   xmm0, xmm0
0x140013c5c  movdqa  [rbp+570h+var_570], xmm1
0x140013c61  movdqa  xmmword ptr [rbp+570h+var_560], xmm0
0x140013c66  or      eax, 3
0x140013c69  mov     [rbp+570h+var_548], rdi
0x140013c6d  mov     dword ptr [rbp+570h+var_570], eax
0x140013c70  mov     rax, [r12+8]
0x140013c75  movdqa  [rbp+570h+var_540], xmm0
0x140013c7a  cmp     dword ptr [rax+1Ch], 2
0x140013c7e  jnz     short loc_140013C8A
0x140013c80  mov     rax, [rax+20h]
0x140013c84  mov     rcx, [rax+10h]
0x140013c88  jmp     short loc_140013C95
0x140013c8a  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140013c91  mov     rcx, [rax+50h]
0x140013c95  mov     r8, [r12]
0x140013c99  lea     rax, [rbp+570h+var_570]
0x140013c9d  mov     rdx, [r15+18h]
0x140013ca1  mov     r9d, ebx
0x140013ca4  mov     [rsp+680h+var_650], r13
0x140013ca9  mov     [rsp+680h+Entry], r14; char *
0x140013cae  mov     [rsp+680h+var_660], rax; struct UnionFs::StackEventTracer *
0x140013cb3  call    ?LookupEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@W4LookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,UnionFs::LookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x140013cb8  mov     ebx, eax
0x140013cba  test    eax, eax
0x140013cbc  jns     short loc_140013CEA
0x140013cbe  lea     rax, aPushCacheLooku; "PUSH: Cache lookup"
0x140013cc5  mov     r8, 21D000207EBh; struct UnionFs::StackEventTracer *
0x140013ccf  lea     r9, aUnionfsUnionfs_31; "UnionFs::UnionFsFilter::PreCreateFileOp"...
0x140013cd6  mov     [rsp+680h+var_660], rax; char *
0x140013cdb  mov     rdx, r14; int
0x140013cde  mov     ecx, ebx; this
0x140013ce0  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140013ce5  jmp     loc_140014857
0x140013cea  mov     ecx, dword ptr [rbp+570h+var_570+4]
0x140013ced  mov     edx, 4
0x140013cf2  mov     [rbp+570h+var_5F0], dil
0x140013cf6  test    ecx, ecx
0x140013cf8  jz      loc_140013DAB
0x140013cfe  test    byte ptr [rbp+570h+var_570+8], dl
0x140013d01  jz      short loc_140013D26
0x140013d03  mov     eax, 0C0000034h
0x140013d08  mov     [r13+20h], rdi
0x140013d0c  lea     r8d, [rdx-3]
0x140013d10  cmp     ecx, r8d
0x140013d13  lea     ebx, [rax+6]
0x140013d16  cmovnz  eax, ebx
0x140013d19  mov     [r13+18h], eax
0x140013d1d  mov     [rsi], edx
0x140013d1f  mov     ebx, edi
0x140013d21  jmp     loc_140014857
0x140013d26  mov     ebx, 1
0x140013d2b  cmp     dword ptr [rbp+570h+var_548], ebx
0x140013d2e  jnz     short loc_140013D3D
0x140013d30  mov     rax, [r12+0A0h]
0x140013d38  or      dword ptr [rax], 8
0x140013d3b  jmp     short loc_140013D1F
0x140013d3d  mov     rax, [rbp+570h+var_560]
0x140013d41  movzx   ecx, word ptr [rax+0A0h]
0x140013d48  nop
0x140013d49  cmp     cx, dx
0x140013d4c  jnz     loc_140013E65
0x140013d52  mov     rax, [rbp+570h+var_560]
0x140013d56  cmp     [rax+0D0h], rdi
0x140013d5d  jnz     short loc_140013D6B
0x140013d5f  lea     rcx, aResultsCacheen; "results.CacheEntry->GetOriginalScratchP"...
0x140013d66  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140013d6b  cmp     dword ptr [rbp+570h+var_570+4], ebx
0x140013d6e  jz      short loc_140013D1F
0x140013d70  mov     rcx, [rbp+570h+Resource]; Resource
0x140013d74  mov     [rbp+570h+Resource], rdi
0x140013d78  test    rcx, rcx
0x140013d7b  jz      short loc_140013D95
0x140013d7d  call    cs:__imp_ExReleaseResourceLite
0x140013d84  nop     dword ptr [rax+rax+00h]
0x140013d89  call    cs:__imp_KeLeaveCriticalRegion
0x140013d90  nop     dword ptr [rax+rax+00h]
0x140013d95  mov     rcx, [rbp+570h+var_560+8]; this
0x140013d99  mov     [rbp+570h+var_560+8], rdi
0x140013d9d  mov     [rbp+570h+var_560], rdi
0x140013da1  test    rcx, rcx
0x140013da4  jz      short loc_140013DAB
0x140013da6  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140013dab  cmp     dword ptr [rbp+570h+var_548], 2
0x140013daf  mov     [rbp+570h+P], rdi
0x140013db3  jnz     loc_140014362
0x140013db9  mov     rax, qword ptr [rbp+570h+var_540+8]
0x140013dbd  lea     r8, [rbp+570h+Source]; Source
0x140013dc1  mov     rcx, [r12]
0x140013dc5  lea     rdx, [rbp+570h+UnicodeString]; struct _UNICODE_STRING *
0x140013dc9  add     rcx, 8; this
0x140013dcd  mov     [rsp+680h+Entry], r14; char *
0x140013dd2  movzx   r9d, word ptr [rax+18h]
0x140013dd7  movups  xmm0, xmmword ptr [rax]
0x140013dda  mov     rax, qword ptr [rbp+570h+var_540]
0x140013dde  movdqu  xmmword ptr [rbp+570h+Source.Length], xmm0
0x140013de3  movups  xmm1, xmmword ptr [rax]
0x140013de6  lea     rax, [rbp+570h+P]
0x140013dea  mov     [rsp+680h+var_660], rax; P
0x140013def  movdqu  xmmword ptr [rbp+570h+UnicodeString.Length], xmm1
0x140013df4  call    ?AllocAndInitWithReplacedPathPrefix@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@00GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140013df9  xor     r9d, r9d
0x140013dfc  mov     edi, eax
0x140013dfe  test    eax, eax
0x140013e00  jns     loc_140014359
0x140013e06  lea     rax, aPushReplacingS_3; "PUSH: Replacing substring"
0x140013e0d  mov     r8, 381000208D9h; struct UnionFs::StackEventTracer *
0x140013e17  lea     r9, aUnionfsUnionfs_31; "UnionFs::UnionFsFilter::PreCreateFileOp"...
0x140013e1e  mov     [rsp+680h+var_660], rax; char *
0x140013e23  mov     rdx, r14; int
0x140013e26  mov     ecx, edi; this
0x140013e28  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140013e2d  mov     rbx, [rbp+570h+P]
0x140013e31  xor     eax, eax
0x140013e33  test    rbx, rbx
0x140013e36  jz      loc_140013D1F
0x140013e3c  cmp     [rbx+10h], al
0x140013e3f  jnz     short loc_140013E47
0x140013e41  xorps   xmm0, xmm0
0x140013e44  movups  xmmword ptr [rbx], xmm0
0x140013e47  mov     rcx, rbx; UnicodeString
0x140013e4a  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140013e4f  xor     edx, edx; Tag
0x140013e51  mov     rcx, rbx; P
0x140013e54  call    cs:__imp_ExFreePoolWithTag
0x140013e5b  nop     dword ptr [rax+rax+00h]
0x140013e60  jmp     loc_140013D1F
0x140013e65  cmp     dword ptr [rbp+570h+var_570+4], ebx
0x140013e68  jnz     loc_140013D70
0x140013e6e  mov     rbx, [rbp+570h+var_560]
0x140013e72  mov     rcx, [rbx+48h]; Context
0x140013e76  call    cs:__imp_FltReferenceContext
0x140013e7d  nop     dword ptr [rax+rax+00h]
0x140013e82  mov     rdi, [rbx+48h]
0x140013e86  lea     rcx, [rbp+570h+P]
0x140013e8a  mov     [rbp+570h+Context], rdi
0x140013e8e  mov     rbx, [rdi+20h]
0x140013e92  mov     [rbp+570h+var_5C8], rbx
0x140013e96  mov     rdx, [rbx+78h]
0x140013e9a  add     rdx, 38h ; '8'
0x140013e9e  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x140013ea3  mov     rax, [r13+10h]
0x140013ea7  cmp     byte ptr [rax+4], 0
0x140013eab  jz      loc_140013F84
0x140013eb1  lea     rcx, aCheckingReques; "Checking requested access on non-create"
0x140013eb8  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140013ebd  mov     rcx, [rbp+570h+P]; Resource
0x140013ec1  test    rcx, rcx
0x140013ec4  jz      short loc_140013EDE
0x140013ec6  call    cs:__imp_ExReleaseResourceLite
0x140013ecd  nop     dword ptr [rax+rax+00h]
0x140013ed2  call    cs:__imp_KeLeaveCriticalRegion
0x140013ed9  nop     dword ptr [rax+rax+00h]
0x140013ede  mov     rax, [r15+20h]
0x140013ee2  lea     rcx, [rbp+570h+var_5C8]
0x140013ee6  mov     rbx, [r12+8]
0x140013eeb  mov     [rbp+570h+Context], rax
0x140013eef  mov     rax, [rbp+570h+var_560]
0x140013ef3  mov     [rbp+570h+var_588], rax
0x140013ef7  lea     rdx, [rbx+48h]
0x140013efb  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140013f00  mov     rax, [rbx+30h]
0x140013f04  mov     rbx, [rax+8]
0x140013f08  mov     rcx, [rax]
0x140013f0b  mov     [rbp+570h+P], rcx
0x140013f0f  test    rbx, rbx
0x140013f12  jz      short loc_140013F18
0x140013f14  lock inc dword ptr [rbx+8]
0x140013f18  mov     rcx, [rbp+570h+var_5C8]; this
0x140013f1c  test    rcx, rcx
0x140013f1f  jz      short loc_140013F26
0x140013f21  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140013f26  mov     r9, [rbp+570h+P]
0x140013f2a  lea     rax, [r12+0A0h]
0x140013f32  mov     rcx, [rbp+570h+Context]; struct _FILE_OBJECT *
0x140013f36  mov     r8, r15
0x140013f39  mov     [rsp+680h+var_648], r14; struct UnionFs::Utils::CheckOplockHParams *
0x140013f3e  mov     rdx, r13; struct _FLT_CALLBACK_DATA *
0x140013f41  mov     [rsp+680h+var_650], rax; __int64
0x140013f46  mov     rax, [rbp+570h+var_588]
0x140013f4a  mov     dword ptr [rsp+680h+Entry], 4; char *
0x140013f52  mov     [rsp+680h+var_660], rax; UnionFs::UfsPathCachePayload *
0x140013f57  call    ?SetUp@UfsShadowFileObject@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsLayerCtx@2@AEAVUfsPathCachePayload@2@W4ShareAccessCaller@2@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsShadowFileObject::SetUp(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsLayerCtx const &,UnionFs::UfsPathCachePayload &,UnionFs::ShareAccessCaller,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140013f5c  mov     r15d, eax
0x140013f5f  test    rbx, rbx
0x140013f62  jz      short loc_140013F6C
0x140013f64  mov     rcx, rbx; this
0x140013f67  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140013f6c  cmp     r15d, 103h
0x140013f73  jnz     loc_140014290
0x140013f79  mov     dword ptr [rsi], 2
0x140013f7f  jmp     loc_14001433E
0x140013f84  mov     rax, [rax+18h]
0x140013f88  mov     ecx, [rax+10h]
0x140013f8b  test    ecx, 10D0106h
0x140013f91  jnz     short loc_140013F9D
0x140013f93  bt      ecx, 19h
0x140013f97  jnb     loc_140013EBD
0x140013f9d  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x140013fa2  test    eax, eax
0x140013fa4  jz      loc_1400140EB
0x140013faa  mov     r9, r14; struct UnionFs::UfsFsContext *
0x140013fad  mov     r8, rbx; struct _FLT_RELATED_OBJECTS *
0x140013fb0  mov     rdx, r15; struct _FLT_CALLBACK_DATA *
0x140013fb3  mov     rcx, r13; this
0x140013fb6  call    ?BreakBatchAndHOplocks@Utils@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsFsContext@2@AEAVStackEventTracer@2@@Z; UnionFs::Utils::BreakBatchAndHOplocks(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsFsContext &,UnionFs::StackEventTracer &)
0x140013fbb  mov     ebx, eax
0x140013fbd  cmp     eax, 103h
0x140013fc2  jnz     loc_140014082
0x140013fc8  mov     eax, cs:dword_14009E178
0x140013fce  cmp     eax, 4
0x140013fd1  jbe     short loc_140014052
0x140013fd3  mov     rcx, cs:qword_14009E190
0x140013fda  mov     edx, 200200h
0x140013fdf  mov     rax, cs:qword_14009E188
0x140013fe6  test    rdx, rax
0x140013fe9  jz      short loc_140014052
0x140013feb  mov     rax, rcx
0x140013fee  and     rax, rdx
0x140013ff1  cmp     rax, rcx
0x140013ff4  jnz     short loc_140014052
0x140013ff6  lea     rax, aOnecoreBaseFsU_14; "onecore\\base\\fs\\unionfs\\sys\\create"...
0x140013ffd  mov     [rbp+570h+var_5D8], 847h
0x140014004  mov     [rbp+570h+var_5C8], rax
0x140014008  lea     rsi, aUnionfsUnionfs_31; "UnionFs::UnionFsFilter::PreCreateFileOp"...
0x14001400f  lea     rax, aOplockBreak; "Oplock break"
0x140014016  mov     [rbp+570h+var_588], rsi
0x14001401a  mov     [rbp+570h+var_5B8], rax
0x14001401e  lea     rdx, byte_1400963B1
0x140014025  lea     rax, [rbp+570h+var_5D8]
0x140014029  mov     [rsp+680h+var_648], rax
0x14001402e  lea     rax, [rbp+570h+var_5C8]
0x140014032  mov     [rsp+680h+var_650], rax
0x140014037  lea     rax, [rbp+570h+var_588]
0x14001403b  mov     [rsp+680h+Entry], rax
0x140014040  lea     rax, [rbp+570h+var_5B8]
0x140014044  mov     [rsp+680h+var_660], rax
0x140014049  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x14001404e  mov     rsi, [rbp+570h+var_580]
0x140014052  mov     rcx, [rbp+570h+P]; Resource
0x140014056  mov     dword ptr [rsi], 2
0x14001405c  test    rcx, rcx
0x14001405f  jz      loc_14001433E
0x140014065  call    cs:__imp_ExReleaseResourceLite
0x14001406c  nop     dword ptr [rax+rax+00h]
0x140014071  call    cs:__imp_KeLeaveCriticalRegion
0x140014078  nop     dword ptr [rax+rax+00h]
0x14001407d  jmp     loc_14001433E
0x140014082  test    ebx, ebx
0x140014084  jns     short loc_1400140EB
0x140014086  lea     rax, aPushBreakingOp; "PUSH: Breaking oplocks"
0x14001408d  mov     r8, 6F50002084Eh; struct UnionFs::StackEventTracer *
0x140014097  lea     r9, aUnionfsUnionfs_31; "UnionFs::UnionFsFilter::PreCreateFileOp"...
0x14001409e  mov     [rsp+680h+var_660], rax; char *
0x1400140a3  mov     rdx, r14; int
  ... truncated ...
```
