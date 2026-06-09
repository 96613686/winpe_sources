# UnionFs::UnionFsFilter::PreCreateFileOpenIf(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,_FLT_PREOP_CALLBACK_STATUS &,UnionFs::CreateContext &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *)

- ea: `0x1400156a8`
- end: `0x140017368`
- name: `?PreCreateFileOpenIf@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAW4_FLT_PREOP_CALLBACK_STATUS@@AEAUCreateContext@2@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@@Z`
- size: `7360`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, enum _FLT_PREOP_CALLBACK_STATUS *, struct UnionFs::CreateContext *, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsSiloCtx *)`
- caller_count: `1`
- callee_count: `49`
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
- `0x14000c20c`
- `0x14000efd0`
- `0x14000f4f4`
- `0x14000f7fc`
- `0x140010148`
- `0x140010b88`
- `0x140010d1c`
- `0x140010d94`
- `0x140011010`
- `0x140011148`
- `0x140011198`
- `0x1400114c4`
- `0x1400156a8`
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

- `ntoskrnl!ExFreePoolWithTag` at `0x140015952`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015ed5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001646a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016492`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400164d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400164f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016584`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400165af`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016b5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016b80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016cc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016d1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016d43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016dac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016ec7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016ff6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400170fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400171a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400172d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001734e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015952`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015ed5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001646a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016492`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400164d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400164f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016584`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400165af`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016b5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016b80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016cc1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016d1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016d43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016dac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016ec7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016f4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016ff6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400170fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400171a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400172d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001734e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015877`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400159c4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015b6b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015bc1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015ce5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015d3e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015d74`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015dec`
- `ntoskrnl!ExReleaseResourceLite` at `0x140016058`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001701d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015877`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400159c4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015b6b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015bc1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015ce5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015d3e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015d74`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015dec`
- `ntoskrnl!ExReleaseResourceLite` at `0x140016058`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001701d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015883`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400159d0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015b77`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015bcd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015cf1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015d4a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015d80`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015df8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140016064`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140017029`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015883`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400159d0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015b77`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015bcd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015cf1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015d4a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015d80`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015df8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140016064`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140017029`
- `FLTMGR!FltReferenceContext` at `0x140015975`
- `FLTMGR!FltReferenceContext` at `0x140015975`
- `FLTMGR!FltReleaseContext` at `0x140015be1`
- `FLTMGR!FltReleaseContext` at `0x140015d0a`
- `FLTMGR!FltReleaseContext` at `0x140015d9c`
- `FLTMGR!FltReleaseContext` at `0x140015e52`
- `FLTMGR!FltReleaseContext` at `0x140015be1`
- `FLTMGR!FltReleaseContext` at `0x140015d0a`
- `FLTMGR!FltReleaseContext` at `0x140015d9c`
- `FLTMGR!FltReleaseContext` at `0x140015e52`

## string_xrefs

- `0x14001571f`: `Checking requested access on non-create`
- `0x1400159af`: `Checking requested access on non-create`
- `0x140015af9`: `onecore\base\fs\unionfs\sys\create.cpp`
- `0x1400167e1`: `onecore\base\fs\unionfs\sys\create.cpp`
- `0x1400157bd`: `PUSH: Cache lookup`
- `0x140015855`: `results.CacheEntry->GetOriginalScratchPath()`
- `0x140015e86`: `PUSH: Allocating scratch path for layer lookup`
- `0x140015cb5`: `PUSH: Oplock and share access check`
- `0x14001661f`: `PUSH: Preparing for scratch create`
- `0x140015c17`: `PUSH: Checking caller access from cache`
- `0x140016277`: `!results.CacheEntry`
- `0x140016aee`: `PUSH: Allocating cache entry`
- `0x140016c6e`: `PUSH: Inserting path cache payload`
- `0x140015916`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140015b0b`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140015ba1`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140015cc6`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140015dc8`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140015f36`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140015fca`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x1400160e7`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x1400161e0`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x1400163bd`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x14001642f`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x14001668c`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140016aff`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140016c84`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x140016f7f`: `UnionFs::UnionFsFilter::PreCreateFileOpenIf`
- `0x1400167ef`: `FileOpenIfCowNotInCache`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PreCreateFileOpenIf(
        UnionFs::UnionFsFilter *this,
        struct _FLT_CALLBACK_DATA *a2,
        struct _FLT_RELATED_OBJECTS *a3,
        struct _LIST_ENTRY *a4,
        struct UnionFs::CreateContext *a5,
        struct UnionFs::StackEventTracer *a6,
        struct _FLT_TAG_DATA_BUFFER *a7)
{
  PFILE_OBJECT FileObject; // rax
  ULONG Flags; // ebx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  unsigned int v13; // ebx
  int v14; // ecx
  __int64 v15; // rax
  __int64 v16; // rcx
  signed int IsFileCowable; // edi
  const char *v18; // rax
  __int64 v19; // r8
  struct _ERESOURCE *v20; // rcx
  utl::_RefCountBase *v21; // rcx
  UnionFs::Rtl *v22; // rcx
  struct UnionFs::StackEventTracer *v23; // r9
  const char *v24; // rax
  __int64 v25; // r8
  struct _UNICODE_STRING *v26; // rdx
  struct _UNICODE_STRING *v27; // rbx
  utl::_RefCountBase *v28; // rbx
  _QWORD *v29; // rdi
  const struct _FLT_RELATED_OBJECTS *v30; // rbx
  PFLT_IO_PARAMETER_BLOCK v31; // rax
  __int64 v32; // rbx
  struct _FILE_OBJECT *v33; // r14
  unsigned __int64 *v34; // rdx
  __int64 v35; // rax
  volatile signed __int32 *v36; // rbx
  int v37; // r14d
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  struct _ERESOURCE *v41; // rcx
  const char *v42; // rax
  __int64 v43; // r8
  __int64 v44; // rax
  __int64 v45; // rcx
  struct _ERESOURCE *v46; // rcx
  void *v47; // rcx
  struct _ERESOURCE *v48; // rcx
  struct _LIST_ENTRY *v49; // rax
  PETHREAD Thread; // rax
  const struct UnionFs::UfsStreamHandleCtx **v51; // r14
  __int64 v52; // rcx
  __int64 v53; // rbx
  int v54; // r8d
  int v55; // ebx
  utl::_RefCountBase *v56; // rcx
  __int64 v57; // r8
  __int64 v58; // rax
  struct _ERESOURCE *v59; // rcx
  UnionFs::UfsUnionCtx *v60; // rcx
  volatile signed __int32 *v61; // rbx
  const struct UnionFs::UfsLayerCtx *v62; // rdx
  signed int v63; // eax
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
  __int16 v74; // ax
  unsigned __int16 v75; // ax
  __int64 v76; // rdx
  __int64 v77; // rcx
  _WORD *Information; // rdi
  __int64 v79; // rcx
  int v80; // eax
  struct _UNICODE_STRING *v81; // rdx
  unsigned int *v82; // r9
  int v83; // r8d
  const char *v84; // rax
  __int64 v85; // r8
  struct _UNICODE_STRING *v86; // rdx
  struct _UNICODE_STRING *Pointer; // rbx
  utl::_RefCountBase *v88; // rcx
  struct _UNICODE_STRING *v89; // rbx
  bool v90; // zf
  utl::_RefCountBase *v91; // rcx
  __int16 v93; // ax
  struct _LIST_ENTRY *Blink; // rax
  struct _UNICODE_STRING *v95; // rbx
  utl::_RefCountBase *v96; // rcx
  volatile signed __int32 *v97; // r14
  const struct UnionFs::UfsLayerCtx *v98; // rdx
  int v99; // eax
  int v100; // r8d
  int v101; // r9d
  PFLT_IO_PARAMETER_BLOCK v102; // rdx
  int v103; // ecx
  struct _UNICODE_STRING *v104; // rax
  UNICODE_STRING *p_Source; // rax
  struct _UNICODE_STRING *v106; // rdx
  UnionFs::UfsUnionCtx *v107; // rcx
  _DWORD *v108; // rcx
  struct _UNICODE_STRING *v109; // r12
  __int64 v110; // rbx
  unsigned __int64 *v111; // rdx
  __int64 v112; // rax
  volatile signed __int32 *v113; // rbx
  int inited; // r12d
  struct _UNICODE_STRING *v115; // rdx
  struct _UNICODE_STRING *v116; // rbx
  utl::_RefCountBase *v117; // rcx
  struct _FLT_TAG_DATA_BUFFER *v118; // r12
  __int64 v119; // rax
  __int64 v120; // rcx
  struct _FLT_RELATED_OBJECTS *v121; // rbx
  int inserted; // eax
  struct _UNICODE_STRING *v123; // rdx
  struct _UNICODE_STRING *v124; // rdx
  struct _UNICODE_STRING *v125; // rbx
  utl::_RefCountBase *v126; // rcx
  struct _UNICODE_STRING *v127; // rdx
  struct _UNICODE_STRING *v128; // rdx
  struct _FILE_OBJECT *v129; // rbx
  int v130; // eax
  struct _UNICODE_STRING *v131; // rdx
  struct _UNICODE_STRING *v132; // rbx
  utl::_RefCountBase *v133; // rcx
  utl::_RefCountBase *v134; // rcx
  struct _ERESOURCE *v135; // rcx
  struct _LIST_ENTRY *v136; // rax
  utl::_RefCountBase *v137; // rcx
  signed int v138; // eax
  utl::_RefCountBase *v139; // rcx
  __int64 v140; // r8
  __int64 v141; // r11
  int v142; // eax
  struct _UNICODE_STRING *v143; // rdx
  signed int v144; // r15d
  struct _UNICODE_STRING *v145; // rdx
  utl::_RefCountBase *v146; // rcx
  utl::_RefCountBase *v147; // rcx
  struct UnionFs::StackEventTracer *v148; // [rsp+20h] [rbp-F0h]
  char *Entry; // [rsp+28h] [rbp-E8h]
  const char *Entrya; // [rsp+28h] [rbp-E8h]
  const char *Entryb; // [rsp+28h] [rbp-E8h]
  const char *Entryc; // [rsp+28h] [rbp-E8h]
  const char *Entryd; // [rsp+28h] [rbp-E8h]
  const char *Entrye; // [rsp+28h] [rbp-E8h]
  char *Entryf; // [rsp+28h] [rbp-E8h]
  const char *Entryg; // [rsp+28h] [rbp-E8h]
  const char *Entryh; // [rsp+28h] [rbp-E8h]
  const char *Entryi; // [rsp+28h] [rbp-E8h]
  char v159; // [rsp+90h] [rbp-80h] BYREF
  _BYTE v160[7]; // [rsp+91h] [rbp-7Fh] BYREF
  struct _FLT_CALLBACK_DATA Context; // [rsp+98h] [rbp-78h] BYREF
  char v162[16]; // [rsp+F0h] [rbp-20h] BYREF
  PVOID v163; // [rsp+100h] [rbp-10h]
  struct _UNICODE_STRING v164; // [rsp+108h] [rbp-8h] BYREF
  __int128 v165; // [rsp+120h] [rbp+10h] BYREF
  utl::_RefCountBase *v166[2]; // [rsp+130h] [rbp+20h] BYREF
  PERESOURCE Resource; // [rsp+140h] [rbp+30h]
  __int64 v168; // [rsp+148h] [rbp+38h]
  __int128 v169; // [rsp+150h] [rbp+40h]
  struct _FLT_RELATED_OBJECTS *v170; // [rsp+160h] [rbp+50h] BYREF
  UNICODE_STRING Source; // [rsp+168h] [rbp+58h] BYREF
  char v172[8]; // [rsp+178h] [rbp+68h] BYREF
  PERESOURCE v173[2]; // [rsp+180h] [rbp+70h]
  utl::_RefCountBase *v174[2]; // [rsp+190h] [rbp+80h]
  __int64 v175; // [rsp+1A0h] [rbp+90h]
  int v176; // [rsp+1A8h] [rbp+98h]
  int v177; // [rsp+1B0h] [rbp+A0h] BYREF
  char v178[8]; // [rsp+1B8h] [rbp+A8h] BYREF
  volatile signed __int32 *v179; // [rsp+1C0h] [rbp+B0h]
  struct _UNICODE_STRING *v180; // [rsp+1C8h] [rbp+B8h] BYREF
  UNICODE_STRING *v181; // [rsp+1D0h] [rbp+C0h] BYREF
  const char *v182; // [rsp+1D8h] [rbp+C8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+1E0h] [rbp+D0h] BYREF
  char *v184; // [rsp+1F0h] [rbp+E0h]
  char v185; // [rsp+1F8h] [rbp+E8h]
  PWSTR *p_Buffer; // [rsp+250h] [rbp+140h]
  char v187[8]; // [rsp+260h] [rbp+150h] BYREF
  __int128 v188; // [rsp+268h] [rbp+158h]
  utl::_RefCountBase *v189[2]; // [rsp+278h] [rbp+168h]
  __int64 v190; // [rsp+288h] [rbp+178h]
  int v191; // [rsp+290h] [rbp+180h]
  struct _UNICODE_STRING v192; // [rsp+2A0h] [rbp+190h] BYREF
  char v193; // [rsp+2B0h] [rbp+1A0h]
  _BYTE v194[80]; // [rsp+2E0h] [rbp+1D0h] BYREF
  _BYTE v195[752]; // [rsp+330h] [rbp+220h] BYREF

  LODWORD(a4->Flink) = 0;
  Context.TagData = a7;
  FileObject = a3->FileObject;
  Context.QueueLinks.Blink = a4;
  v170 = a3;
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
  v165 = 0;
  *(_OWORD *)v166 = 0;
  v168 = 0;
  LODWORD(v165) = _mm_cvtsi128_si32((__m128i)0LL) | 3;
  v15 = *((_QWORD *)a5 + 1);
  v169 = 0;
  if ( *(_DWORD *)(v15 + 28) == 2 )
    v16 = *(_QWORD *)(*(_QWORD *)(v15 + 32) + 16LL);
  else
    v16 = *((_QWORD *)UnionFs::g_FilterState + 10);
  Entry = (char *)a6;
  IsFileCowable = UnionFs::UfsPathCache::LookupEntry(v16, a3->Instance, *(_QWORD *)a5, v13, &v165);
  if ( IsFileCowable < 0 )
  {
    v18 = "PUSH: Cache lookup";
    v19 = 0x11F00020AF7LL;
LABEL_105:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)IsFileCowable,
      (int)a6,
      (struct UnionFs::StackEventTracer *)v19,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
      v18,
      Entry);
    goto LABEL_180;
  }
  v159 = 0;
  if ( !DWORD1(v165) )
    goto LABEL_27;
  if ( (BYTE8(v165) & 4) != 0 )
  {
    if ( DWORD1(v165) == 1 )
    {
      UnionFs::CreateContext::OverwriteTombstone(a5, v166, 0);
    }
    else
    {
      a2->IoStatus.Status = -1073741766;
      a2->IoStatus.Information = 0;
      LODWORD(a4->Flink) = 4;
    }
    goto LABEL_18;
  }
  if ( (_DWORD)v168 == 1 )
  {
    **((_DWORD **)a5 + 20) |= 8u;
LABEL_18:
    IsFileCowable = 0;
    goto LABEL_180;
  }
  if ( *((_WORD *)v166[0] + 80) == 4 )
  {
    if ( !*((_QWORD *)v166[0] + 26) )
      MicrosoftTelemetryAssertTriggeredMsgKM("results.CacheEntry->GetOriginalScratchPath()");
    if ( DWORD1(v165) == 1 )
      goto LABEL_18;
    goto LABEL_23;
  }
  if ( DWORD1(v165) != 1 )
  {
LABEL_23:
    v20 = Resource;
    Resource = 0;
    if ( v20 )
    {
      ExReleaseResourceLite(v20);
      KeLeaveCriticalRegion();
    }
    v21 = v166[1];
    v166[1] = 0;
    v166[0] = 0;
    if ( v21 )
      utl::_RefCountBase::_DecStrong(v21);
LABEL_27:
    Context.Thread = 0;
    if ( (_DWORD)v168 != 2 )
      goto LABEL_92;
    v22 = (UnionFs::Rtl *)(*(_QWORD *)a5 + 8LL);
    Source = (UNICODE_STRING)**((_OWORD **)&v169 + 1);
    v164 = *(struct _UNICODE_STRING *)v169;
    IsFileCowable = UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(
                      v22,
                      &v164,
                      &Source,
                      (PVOID)&Context.Thread,
                      (int)a6);
    if ( IsFileCowable < 0 )
    {
      v24 = "PUSH: Replacing substring";
      v25 = 0x38200020BFALL;
      goto LABEL_30;
    }
    Thread = Context.Thread;
    if ( !Context.Thread )
    {
LABEL_92:
      IsFileCowable = UnionFs::UfsPathName::AllocAndInit(*(_QWORD *)a5, &Context.Thread, a6);
      if ( IsFileCowable < 0 )
      {
        v24 = "PUSH: Allocating scratch path for layer lookup";
        v25 = 0x39200020C05LL;
LABEL_30:
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)IsFileCowable,
          (int)a6,
          (struct UnionFs::StackEventTracer *)v25,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
          v24,
          Entry);
        v27 = (struct _UNICODE_STRING *)Context.Thread;
        if ( Context.Thread )
        {
          if ( !*((_BYTE *)Context.Thread + 16) )
            *(_OWORD *)Context.Thread = 0;
          FsFltWil::Details::FreeUnicodeString(v27, v26);
          ExFreePoolWithTag(v27, 0);
        }
        goto LABEL_180;
      }
      Thread = Context.Thread;
    }
    v51 = (const struct UnionFs::UfsStreamHandleCtx **)((char *)a5 + 160);
    v52 = *((_QWORD *)a5 + 20);
    Context.Thread = 0;
    v53 = *(_QWORD *)(v52 + 64);
    *(_QWORD *)(v52 + 64) = Thread;
    if ( v53 )
    {
      if ( !*(_BYTE *)(v53 + 16) )
        *(_OWORD *)v53 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v53, 0);
      ExFreePoolWithTag((PVOID)v53, 0);
    }
    if ( v159 )
    {
      if ( !DWORD1(v165) )
        MicrosoftTelemetryAssertTriggeredMsgKM("results.LookupResult != MAPPING_LOOKUP_RESULT::None");
      if ( (*(_DWORD *)(*((_QWORD *)a5 + 1) + 24LL) & 0x80u) != 0 )
      {
        v159 = 0;
        IsFileCowable = UnionFs::Utils::IsFileCowable((UnionFs::Utils *)&v159, (bool *)v166[0], a6, v23);
        if ( IsFileCowable < 0 )
        {
          v18 = "PUSH: Checking immutability";
          v19 = 0x78300020C16LL;
          goto LABEL_105;
        }
        if ( !v159 )
        {
          if ( (unsigned int)dword_14009E178 > 5
            && (qword_14009E188 & 0x400000000000LL) != 0
            && (qword_14009E190 & 0x400000000000LL) == qword_14009E190 )
          {
            Context.TagData = (struct _FLT_TAG_DATA_BUFFER *)0x1000000;
            Context.IoStatus.Information = 1;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
              1,
              (unsigned int)&unk_140095E98,
              v54,
              (unsigned int)&Context.TagData,
              (__int64)&Context.IoStatus.Information);
          }
          v55 = -1073741790;
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC0000022LL,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x78400020C23LL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
            "ORIGIN: Rejecting COW for immutable file",
            Entry);
LABEL_112:
          IsFileCowable = v55;
          goto LABEL_180;
        }
      }
      v56 = v166[0];
      v57 = v169;
      *(_QWORD *)&v164.Length = *((_QWORD *)a5 + 1);
      v58 = *((_QWORD *)a5 + 2);
      v164.Buffer = (PWSTR)v58;
      if ( v58 )
        _InterlockedIncrement((volatile signed __int32 *)(v58 + 8));
      IsFileCowable = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(v56, &v164, v57, 11, a6);
      if ( IsFileCowable < 0 )
      {
        v18 = "PUSH: ConvertToSoftTombstone for COW";
        v19 = 0x39800020C2FLL;
        goto LABEL_105;
      }
      Context.RequestorMode = 1;
      v59 = Resource;
      Context.QueueContext[1] = &v165;
      Resource = 0;
      if ( v59 )
      {
        ExReleaseResourceLite(v59);
        KeLeaveCriticalRegion();
      }
      v60 = (UnionFs::UfsUnionCtx *)*((_QWORD *)a5 + 1);
      v61 = (volatile signed __int32 *)*((_QWORD *)v166[0] + 5);
      v62 = (const struct UnionFs::UfsLayerCtx *)*((_QWORD *)v166[0] + 4);
      if ( v61 )
        _InterlockedIncrement(v61 + 2);
      v63 = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
              v60,
              a2,
              a3,
              *(const struct _FLT_FILE_NAME_INFORMATION **)a5,
              *((const struct UnionFs::UfsPathName **)*v51 + 8),
              *v51,
              v62,
              a6,
              (const struct UnionFs::UfsSiloCtx *)Context.TagData);
      v37 = 0;
      IsFileCowable = v63;
      if ( v61 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v61);
      if ( IsFileCowable < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)IsFileCowable,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x29700020C47LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
          "PUSH: Preparing for COW",
          Entryb);
LABEL_125:
        wil::details::lambda_call__lambda_01df43a959510544996831cba597273e___::_lambda_call__lambda_01df43a959510544996831cba597273e___(&Context.FilterContext[3]);
        goto LABEL_180;
      }
      v64 = (struct _ERESOURCE *)v166[0];
      *(_QWORD *)v172 = *((_QWORD *)a5 + 1);
      v65 = v166[1];
      v175 = 0;
      v176 = 22;
      *(_OWORD *)v173 = 0;
      *(_OWORD *)v174 = 0;
      if ( v166[1] )
        _InterlockedIncrement((volatile signed __int32 *)v166[1] + 2);
      v173[1] = v64;
      v66 = v174[0];
      v174[0] = v65;
      if ( v66 )
        utl::_RefCountBase::_DecStrong(v66);
      UnionFs::UfsPathName::UfsPathName(
        (UnionFs::UfsPathName *)&UnicodeString,
        (const struct _UNICODE_STRING *)(*(_QWORD *)a5 + 8LL),
        *(_WORD *)(*(_QWORD *)a5 + 24LL));
      Instance = a3->Instance;
      v68 = (volatile signed __int32 *)*((_QWORD *)v166[0] + 5);
      v69 = *((_QWORD *)v166[0] + 6);
      v70 = *((_QWORD *)v166[0] + 4);
      if ( v68 )
        _InterlockedIncrement(v68 + 2);
      IsFileCowable = UnionFs::Utils::CopyItem(
                        (_DWORD)a2,
                        v70,
                        v69,
                        (_DWORD)Instance,
                        &UnicodeString,
                        (__int64)v172,
                        (struct _FILE_OBJECT *)a6,
                        0);
      if ( v68 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v68);
      if ( IsFileCowable < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)IsFileCowable,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x29000020C58LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
          "PUSH: Performing COW",
          Entryc);
        if ( !(_BYTE)v184 )
          UnicodeString = 0;
        FsFltWil::Details::FreeUnicodeString(&UnicodeString, v72);
        if ( v174[0] )
          utl::_RefCountBase::_DecStrong(v174[0]);
        goto LABEL_125;
      }
      Context.RequestorMode = 0;
      if ( !(_BYTE)v184 )
        UnicodeString = 0;
      FsFltWil::Details::FreeUnicodeString(&UnicodeString, v71);
      if ( v174[0] )
        utl::_RefCountBase::_DecStrong(v174[0]);
      wil::details::lambda_call__lambda_01df43a959510544996831cba597273e___::_lambda_call__lambda_01df43a959510544996831cba597273e___(&Context.FilterContext[3]);
LABEL_63:
      IsFileCowable = v37;
      goto LABEL_180;
    }
    if ( v166[0] )
      MicrosoftTelemetryAssertTriggeredMsgKM("!results.CacheEntry");
    UnicodeString.Buffer = (PWSTR)off_14007E740;
    p_Buffer = &UnicodeString.Buffer;
    UnionFs::StackEventTracer::SetIgnoreStatusCallback(a6, &UnicodeString);
    memset(v194, 0, 0x48u);
    Entry = (char *)a6;
    IsFileCowable = UnionFs::Utils::StatItemAsCaller(*(_QWORD *)a5 + 8LL, a3->Instance, v73, v194, a2);
    v74 = *((_WORD *)a6 + 245);
    if ( v74 )
    {
      v75 = v74 - 1;
      *((_WORD *)a6 + 245) = v75;
      v76 = 120 * (v75 + 1LL);
      v77 = *(_QWORD *)((char *)a6 + v76);
      *(_QWORD *)((char *)a6 + v76) = 0;
      if ( v77 )
        (*(void (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v77 + 24LL))(v77, v76, 0, 1);
    }
    if ( IsFileCowable == 260 )
    {
LABEL_179:
      IsFileCowable = 260;
      goto LABEL_180;
    }
    if ( IsFileCowable >= 0 )
      goto LABEL_18;
    if ( IsFileCowable == -1073741766 )
    {
      v159 = 0;
    }
    else
    {
      if ( IsFileCowable != -1073741772 )
      {
        v18 = "PUSH: Querying stat information";
        v19 = 0xE700020C7DLL;
        goto LABEL_105;
      }
      v159 = 1;
    }
    utl::make_unique<UnionFs::FindAndStatResults,,0>(&Context.IoStatus.Information);
    Information = (_WORD *)Context.IoStatus.Information;
    if ( !Context.IoStatus.Information )
    {
      IsFileCowable = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x3FD00020C94LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
        "ORIGIN: Allocating findAndStatResults",
        (const char *)a6);
      goto LABEL_180;
    }
    Context.IoStatus.Pointer = 0;
    *(_QWORD *)(Context.IoStatus.Information + 96) = &Context.IoStatus;
    v79 = *((_QWORD *)a5 + 1);
    Entryd = (const char *)Information;
    Source = *(UNICODE_STRING *)*((_QWORD *)*v51 + 8);
    v80 = UnionFs::UfsUnionCtx::FindAndStatItemInLayersAsCaller(v79, a2, &Source);
    v83 = 0;
    v37 = v80;
    if ( v80 < 0 )
    {
      v84 = "PUSH: Statting item in layers";
      v85 = 0xE900020CA1LL;
LABEL_161:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v37,
        (int)a6,
        (struct UnionFs::StackEventTracer *)v85,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
        v84,
        Entryd);
      Pointer = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
      if ( Context.IoStatus.Pointer )
      {
        if ( !*((_BYTE *)Context.IoStatus.Pointer + 16) )
          *(_OWORD *)Context.IoStatus.Pointer = 0;
        FsFltWil::Details::FreeUnicodeString(Pointer, v86);
        ExFreePoolWithTag(Pointer, 0);
      }
      if ( Information )
      {
        v88 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
        if ( v88 )
          utl::_RefCountBase::_DecStrong(v88);
        ExFreePoolWithTag(Information, 0);
      }
      goto LABEL_63;
    }
    if ( v80 == 260 )
    {
      v89 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
      if ( !Context.IoStatus.Pointer )
      {
LABEL_175:
        if ( Information )
        {
          v91 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
          if ( v91 )
            utl::_RefCountBase::_DecStrong(v91);
          ExFreePoolWithTag(Information, 0);
        }
        goto LABEL_179;
      }
      v90 = *((_BYTE *)Context.IoStatus.Pointer + 16) == 0;
LABEL_172:
      if ( v90 )
        *v89 = 0;
      FsFltWil::Details::FreeUnicodeString(v89, v81);
      ExFreePoolWithTag(v89, 0);
      goto LABEL_175;
    }
    v93 = *Information;
    if ( *Information == 2 )
    {
      if ( !v159 )
      {
        Blink = Context.QueueLinks.Blink;
        a2->IoStatus.Status = -1073741766;
        a2->IoStatus.Information = 0;
        LODWORD(Blink->Flink) = 4;
      }
      goto LABEL_184;
    }
    if ( v93 == 3 )
    {
      if ( !v159 )
      {
        v37 = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
                *((UnionFs::UfsUnionCtx **)a5 + 1),
                a2,
                a3,
                *(const struct _FLT_FILE_NAME_INFORMATION **)a5,
                *(const struct UnionFs::UfsPathName **)(*((_QWORD *)a5 + 20) + 64LL),
                *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
                *((const struct UnionFs::UfsLayerCtx **)Information + 10),
                a6,
                (const struct UnionFs::UfsSiloCtx *)Context.TagData);
        if ( v37 < 0 )
        {
          v84 = "PUSH: Preparing for scratch create";
          v85 = 0xEA00020CC9LL;
          goto LABEL_161;
        }
      }
LABEL_184:
      v95 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
      if ( Context.IoStatus.Pointer )
      {
        if ( !*((_BYTE *)Context.IoStatus.Pointer + 16) )
          *(_OWORD *)Context.IoStatus.Pointer = 0;
        FsFltWil::Details::FreeUnicodeString(v95, v81);
        ExFreePoolWithTag(v95, 0);
      }
      if ( Information )
      {
        v96 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
        if ( v96 )
          utl::_RefCountBase::_DecStrong(v96);
        ExFreePoolWithTag(Information, 0);
      }
      goto LABEL_18;
    }
    if ( v93 != 1 )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("findAndStatResults->FindResult == LAYER_FIND_RESULT::Found");
      v83 = 0;
    }
    v97 = (volatile signed __int32 *)*((_QWORD *)Information + 11);
    v98 = (const struct UnionFs::UfsLayerCtx *)*((_QWORD *)Information + 10);
    Context.IoStatus.Information = (ULONG_PTR)v98;
    if ( v97 )
      _InterlockedIncrement(v97 + 2);
    v99 = *(_DWORD *)(a2->Iopb->Parameters.WMI.ProviderId + 16);
    if ( (v99 & 0x2000000) != 0 )
    {
      if ( (*((_DWORD *)Information + 19) & 0x10D0106) != 0 )
        goto LABEL_202;
    }
    else if ( (v99 & 0x10D0106) != 0 )
    {
LABEL_202:
      if ( (unsigned int)dword_14009E178 > 5 )
      {
        v83 = 0x10000;
        if ( (qword_14009E188 & 0x10000) != 0 && (qword_14009E190 & 0x10000) == qword_14009E190 )
        {
          v164 = 0;
          UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v195, 0x1E00020DAAuLL);
          UnionFs::Utils::GetUserSidString(a2, &v164, v195);
          Source = *(UNICODE_STRING *)Context.IoStatus.Pointer;
          if ( (unsigned int)dword_14009E178 > 5
            && (qword_14009E188 & 0x30200) != 0
            && (qword_14009E190 & 0x30200) == qword_14009E190 )
          {
            v102 = a2->Iopb;
            LODWORD(Context.Iopb) = *((_DWORD *)Information + 19);
            *(_QWORD *)v178 = "UnionFs::UnionFsFilter::PreCreateFileOpenIf";
            LODWORD(Context.QueueLinks.Flink) = *(_DWORD *)(*(_QWORD *)(v102->Parameters.WMI.ProviderId + 8) + 24LL);
            v177 = *(_DWORD *)(*(_QWORD *)(v102->Parameters.WMI.ProviderId + 8) + 20LL);
            LODWORD(v170) = *(_DWORD *)(*(_QWORD *)(v102->Parameters.WMI.ProviderId + 8) + 16LL);
            LODWORD(Context.FilterContext[2]) = *(_DWORD *)(*(_QWORD *)(v102->Parameters.WMI.ProviderId + 8) + 12LL);
            LODWORD(Context.FilterContext[1]) = *(_DWORD *)(v102->Parameters.WMI.ProviderId + 16);
            v103 = *(_DWORD *)(v102->Parameters.WMI.ProviderId + 16);
            v104 = &v164;
            Context.Flags = 3525;
            v160[0] = (v103 & 0x2000000) != 0;
            if ( !v164.Buffer )
              v104 = (struct _UNICODE_STRING *)&FsTlEmptyUnicodeString;
            v180 = v104;
            p_Source = &Source;
            if ( !Source.Buffer )
              p_Source = (UNICODE_STRING *)&FsTlEmptyUnicodeString;
            v181 = p_Source;
            v182 = "onecore\\base\\fs\\unionfs\\sys\\create.cpp";
            Context.QueueContext[1] = "FileOpenIfCowNotInCache";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              (unsigned int)&FsTlEmptyUnicodeString,
              (unsigned int)&word_1400961CE,
              v100,
              v101,
              (__int64)&Context.QueueContext[1],
              (__int64)v178,
              (__int64)&v182,
              (__int64)&Context,
              (__int64)&v181,
              (__int64)&v180,
              (__int64)v160,
              (__int64)&Context.QueueLinks.Blink,
              (__int64)Context.QueueContext,
              (__int64)&v170,
              (__int64)&v177,
              (__int64)&Context.QueueLinks,
              (__int64)&Context.Iopb);
          }
          UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v195);
          FsFltWil::Details::FreeUnicodeString(&v164, v106);
          v98 = (const struct UnionFs::UfsLayerCtx *)Context.IoStatus.Information;
        }
      }
      v107 = (UnionFs::UfsUnionCtx *)*((_QWORD *)a5 + 1);
      if ( (*((_DWORD *)v107 + 6) & 0x80u) != 0 && (*((_DWORD *)Information + 16) & 0x800010) == 0 )
      {
        if ( (unsigned int)dword_14009E178 > 5
          && (qword_14009E188 & 0x400000000000LL) != 0
          && (qword_14009E190 & 0x400000000000LL) == qword_14009E190 )
        {
          Context.QueueContext[1] = (PVOID)1;
          *(_QWORD *)v178 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            0,
            (unsigned int)&byte_1400963EF,
            v83,
            (unsigned int)v178,
            (__int64)&Context.QueueContext[1]);
        }
        v55 = -1073741790;
        UnionFs::ProcessTraceStatusOrigin(
          (UnionFs *)0xC0000022LL,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x78500020DDCLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
          "ORIGIN: Rejecting COW for immutable file",
          Entryd);
LABEL_335:
        if ( v97 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v97);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.IoStatus);
        if ( Information )
        {
          v137 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
          if ( v137 )
            utl::_RefCountBase::_DecStrong(v137);
          ExFreePoolWithTag(Information, 0);
        }
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.Thread);
        goto LABEL_112;
      }
      v138 = UnionFs::UfsUnionCtx::EnsureParentPathInScratch(
               v107,
               a2,
               a3,
               *(const struct _FLT_FILE_NAME_INFORMATION **)a5,
               *(const struct UnionFs::UfsPathName **)(*((_QWORD *)a5 + 20) + 64LL),
               *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
               v98,
               a6,
               (const struct UnionFs::UfsSiloCtx *)Context.TagData);
      Context.Flags = v138;
      if ( v138 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v138,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x29600020DEFLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
          "PUSH: Preparing for COW",
          Entryh);
        if ( v97 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v97);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.IoStatus);
        if ( Information )
        {
          v139 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
          if ( v139 )
            utl::_RefCountBase::_DecStrong(v139);
          ExFreePoolWithTag(Information, 0);
        }
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.Thread);
        IsFileCowable = Context.Flags;
        goto LABEL_180;
      }
      v140 = *(_QWORD *)a5;
      *(_QWORD *)v187 = *((_QWORD *)a5 + 1);
      v188 = 0;
      v190 = 0;
      *(_OWORD *)v189 = 0;
      v191 = 22;
      UnionFs::UfsPathName::UfsPathName(
        (UnionFs::UfsPathName *)&v192,
        (const struct _UNICODE_STRING *)(v140 + 8),
        *(_WORD *)(v140 + 24));
      v142 = UnionFs::Utils::CopyItem(
               (_DWORD)a2,
               Context.IoStatus.Information,
               Context.IoStatus.Status,
               a3->Instance,
               &v192,
               (__int64)v187,
               (struct _FILE_OBJECT *)a6,
               v141);
      inited = 0;
      v144 = v142;
      if ( v142 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v142,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x29100020E02LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
          "PUSH: Performing COW",
          Entryi);
        if ( !v193 )
          v192 = 0;
        FsFltWil::Details::FreeUnicodeString(&v192, v145);
        if ( v189[0] )
          utl::_RefCountBase::_DecStrong(v189[0]);
        if ( v97 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v97);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.IoStatus);
        if ( Information )
        {
          v146 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
          if ( v146 )
            utl::_RefCountBase::_DecStrong(v146);
          ExFreePoolWithTag(Information, 0);
        }
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.Thread);
        IsFileCowable = v144;
        goto LABEL_180;
      }
      if ( !v193 )
        v192 = 0;
      FsFltWil::Details::FreeUnicodeString(&v192, v143);
      if ( v189[0] )
        utl::_RefCountBase::_DecStrong(v189[0]);
      if ( v97 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v97);
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.IoStatus);
      if ( Information )
      {
        v147 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
        if ( v147 )
          utl::_RefCountBase::_DecStrong(v147);
        ExFreePoolWithTag(Information, 0);
      }
      utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.Thread);
LABEL_254:
      IsFileCowable = inited;
      goto LABEL_180;
    }
    *(_QWORD *)&v164.Length = *((_QWORD *)&v169 + 1);
    v163 = 0;
    *(_QWORD *)&Context.Flags = 0;
    LODWORD(Context.QueueLinks.Flink) = 0;
    v160[0] = 0;
    v159 = 0;
    v164.Buffer = (PWSTR)v169;
    *(_OWORD *)v162 = 0;
    if ( !UnionFs::Utils::GetQueryOnCreateEcp(
            a2,
            &Context,
            (struct _QUERY_ON_CREATE_ECP_CONTEXT **)&Context.QueueLinks,
            v82) )
    {
LABEL_233:
      v109 = &v164;
      *(_QWORD *)&UnicodeString.Length = v160;
      if ( (_DWORD)v168 != 2 )
        v109 = 0;
      v185 = 1;
      UnicodeString.Buffer = (PWSTR)&Context;
      v184 = &v159;
      LODWORD(Context.Iopb) = *((_DWORD *)Information + 16);
      Context.TagData = (struct _FLT_TAG_DATA_BUFFER *)Context.IoStatus.Pointer;
      *(_QWORD *)v178 = Context.IoStatus.Information;
      v179 = v97;
      if ( v97 )
        _InterlockedIncrement(v97 + 2);
      v110 = *((_QWORD *)a5 + 1);
      FsFltWil::AcquirePushLockShared(&Context.IoStatus.Information, v110 + 72);
      v112 = *(_QWORD *)(v110 + 48);
      v113 = *(volatile signed __int32 **)(v112 + 8);
      Context.QueueContext[0] = *(PVOID *)v112;
      if ( v113 )
        _InterlockedIncrement(v113 + 2);
      if ( Context.IoStatus.Information )
        FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Context.IoStatus.Information, v111);
      inited = UnionFs::UfsPathCachePayload::AllocAndInitShared(
                 a2,
                 (__int64)Context.QueueContext[0],
                 (struct _LIST_ENTRY **)v178,
                 (LIST_ENTRY *)Context.TagData,
                 (int)Context.Iopb,
                 (struct _UNICODE_STRING *)v162,
                 a6,
                 (__int64)v109);
      if ( v113 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v113);
      if ( inited < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)inited,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x45600020D33LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
          "PUSH: Allocating cache entry",
          Entrye);
        wil::details::lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___::_lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___(&UnicodeString);
        utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(v162);
        if ( v97 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v97);
        v116 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
        if ( Context.IoStatus.Pointer )
        {
          if ( !*((_BYTE *)Context.IoStatus.Pointer + 16) )
            *(_OWORD *)Context.IoStatus.Pointer = 0;
          FsFltWil::Details::FreeUnicodeString(v116, v115);
          ExFreePoolWithTag(v116, 0);
        }
        if ( Information )
        {
          v117 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
          if ( v117 )
            utl::_RefCountBase::_DecStrong(v117);
          ExFreePoolWithTag(Information, 0);
        }
        goto LABEL_254;
      }
      if ( inited == 260 )
      {
        wil::details::lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___::_lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___(&UnicodeString);
        utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(v162);
        if ( v97 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v97);
        v89 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
        if ( !Context.IoStatus.Pointer )
          goto LABEL_175;
        v90 = *((_BYTE *)Context.IoStatus.Pointer + 16) == 0;
        goto LABEL_172;
      }
      v118 = (struct _FLT_TAG_DATA_BUFFER *)v163;
      Context.QueueContext[1] = *(PVOID *)v162;
      *(_QWORD *)&Context.RequestorMode = *(_QWORD *)&v162[8];
      v119 = *((_QWORD *)a5 + 1);
      *(_OWORD *)v162 = 0;
      v163 = 0;
      Context.TagData = v118;
      v90 = *(_DWORD *)(v119 + 28) == 2;
      *(_QWORD *)v172 = 0;
      *(_OWORD *)v173 = 0;
      v174[0] = 0;
      v174[1] = 0;
      if ( v90 )
        v120 = *(_QWORD *)(*(_QWORD *)(v119 + 32) + 16LL);
      else
        v120 = *((_QWORD *)UnionFs::g_FilterState + 10);
      v121 = v170;
      Entryf = v172;
      inserted = UnionFs::UfsPathCache::InsertEntry(v120, v170->Instance, v118, 1, &Context.FilterContext[3]);
      LODWORD(Context.Iopb) = inserted;
      if ( inserted < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)inserted,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x45700020D4BLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
          "PUSH: Inserting path cache payload",
          v172);
        UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v172);
        if ( v118 )
        {
          if ( !v118->GenericGUIDReparseBuffer.TagGuid.Data4[0] )
            *(_OWORD *)&v118->FileTag = 0;
          FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v118, v123);
          ExFreePoolWithTag(v118, 0);
        }
        if ( *(_QWORD *)&Context.RequestorMode )
          utl::_RefCountBase::_DecStrong(*(utl::_RefCountBase **)&Context.RequestorMode);
        wil::details::lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___::_lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___(&UnicodeString);
        utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(v162);
        if ( v97 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v97);
        v125 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
        if ( Context.IoStatus.Pointer )
        {
          if ( !*((_BYTE *)Context.IoStatus.Pointer + 16) )
            *(_OWORD *)Context.IoStatus.Pointer = 0;
          FsFltWil::Details::FreeUnicodeString(v125, v124);
          ExFreePoolWithTag(v125, 0);
        }
        if ( Information )
        {
          v126 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
          if ( v126 )
            utl::_RefCountBase::_DecStrong(v126);
          ExFreePoolWithTag(Information, 0);
        }
        goto LABEL_280;
      }
      if ( *(_DWORD *)v172 == 2 )
      {
        Context.IoStatus.Information = (ULONG_PTR)v173[1];
        Context.QueueContext[0] = v174[0];
        if ( v174[0] )
          _InterlockedIncrement((volatile signed __int32 *)v174[0] + 2);
        if ( *(_QWORD *)&Context.RequestorMode )
          utl::_RefCountBase::_DecStrong(*(utl::_RefCountBase **)&Context.RequestorMode);
      }
      else
      {
        if ( *(_DWORD *)v172 == 3 )
        {
          if ( ((__int64)v174[1] & 1) == 0 )
            MicrosoftTelemetryAssertTriggeredMsgKM("WI_IsFlagSet(insertResults.Flags, InsertEntryResultsFlags::StoppedOnHardTombstone)");
          UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v172);
          if ( v118 )
          {
            if ( !v118->GenericGUIDReparseBuffer.TagGuid.Data4[0] )
              *(_OWORD *)&v118->FileTag = 0;
            FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v118, v127);
            ExFreePoolWithTag(v118, 0);
          }
          if ( *(_QWORD *)&Context.RequestorMode )
            utl::_RefCountBase::_DecStrong(*(utl::_RefCountBase **)&Context.RequestorMode);
          wil::details::lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___::_lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___(&UnicodeString);
          utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(v162);
          if ( !v97 )
            goto LABEL_309;
          goto LABEL_308;
        }
        Context.QueueContext[0] = *(PVOID *)&Context.RequestorMode;
        Context.IoStatus.Information = (ULONG_PTR)Context.QueueContext[1];
      }
      v129 = v121->FileObject;
      UnionFs::UfsUnionCtx::GetScratchLayer(*((_QWORD *)a5 + 1), &Source);
      LODWORD(Entryf) = 8;
      v130 = UnionFs::UfsShadowFileObject::SetUp(
               v129,
               a2,
               (UnionFs::UfsPathCachePayload *)Context.IoStatus.Information,
               (struct UnionFs::StackEventTracer *)Entryf,
               (__int64)a5 + 160,
               a6);
      v55 = 0;
      LODWORD(Context.Iopb) = v130;
      if ( Source.Buffer )
      {
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Source.Buffer);
        v130 = (int)Context.Iopb;
      }
      if ( v130 != 259 )
      {
        if ( v130 >= 0 )
        {
          v135 = v173[0];
          v173[0] = 0;
          if ( v135 )
          {
            ExReleaseResourceLite(v135);
            KeLeaveCriticalRegion();
          }
          if ( v159 )
          {
            *(_QWORD *)(*(_QWORD *)&Context.Flags + 152LL) = 0;
            *(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) |= 8u;
          }
          UnionFs::UnionFsFilter::VirtualizeQoCEcpIDs(
            (UnionFs::UnionFsFilter *)v135,
            a2,
            v170,
            *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
            *((struct UnionFs::UfsUnionCtx **)a5 + 1),
            a6,
            *(struct _QUERY_ON_CREATE_ECP_CONTEXT **)&Context.Flags,
            (unsigned int)Context.QueueLinks.Flink);
          v136 = Context.QueueLinks.Blink;
          a2->IoStatus.Status = 0;
          a2->IoStatus.Information = 1;
          LODWORD(v136->Flink) = 4;
          UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v172);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.TagData);
          if ( Context.QueueContext[0] )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Context.QueueContext[0]);
          wil::details::lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___::_lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___(&UnicodeString);
          utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(v162);
          goto LABEL_335;
        }
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v130,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x13000020D86LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
          "PUSH: Setting up shadow file object",
          Entryg);
        UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v172);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.TagData);
        if ( Context.QueueContext[0] )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Context.QueueContext[0]);
        wil::details::lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___::_lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___(&UnicodeString);
        utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(v162);
        if ( v97 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v97);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.IoStatus);
        if ( Information )
        {
          v134 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
          if ( v134 )
            utl::_RefCountBase::_DecStrong(v134);
          ExFreePoolWithTag(Information, 0);
        }
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.Thread);
LABEL_280:
        IsFileCowable = (signed int)Context.Iopb;
        goto LABEL_180;
      }
      LODWORD(Context.QueueLinks.Blink->Flink) = 2;
      UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v172);
      if ( v118 )
      {
        if ( !v118->GenericGUIDReparseBuffer.TagGuid.Data4[0] )
          *(_OWORD *)&v118->FileTag = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v118, v131);
        ExFreePoolWithTag(v118, 0);
      }
      if ( Context.QueueContext[0] )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Context.QueueContext[0]);
      wil::details::lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___::_lambda_call__lambda_561647cae8720c0d6129e86a42d579cf___(&UnicodeString);
      utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(v162);
      if ( !v97 )
        goto LABEL_309;
LABEL_308:
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v97);
LABEL_309:
      v132 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
      if ( Context.IoStatus.Pointer )
      {
        if ( !*((_BYTE *)Context.IoStatus.Pointer + 16) )
          *(_OWORD *)Context.IoStatus.Pointer = 0;
        FsFltWil::Details::FreeUnicodeString(v132, v128);
        ExFreePoolWithTag(v132, 0);
      }
      if ( Information )
      {
        v133 = (utl::_RefCountBase *)*((_QWORD *)Information + 11);
        if ( v133 )
          utl::_RefCountBase::_DecStrong(v133);
        ExFreePoolWithTag(Information, 0);
      }
      IsFileCowable = 0;
      goto LABEL_180;
    }
    v108 = *(_DWORD **)&Context.Flags;
    if ( (**(_DWORD **)&Context.Flags & 4) == 0 )
    {
LABEL_231:
      if ( (*v108 & 8) != 0 )
      {
        *v108 &= ~8u;
        v159 = 1;
      }
      goto LABEL_233;
    }
    if ( LODWORD(Context.QueueLinks.Flink) >= 0x88 )
    {
      if ( (int)UnionFs::UnionFsFilter::HandleQoCEcpEaInfo(
                  *(UnionFs::UnionFsFilter **)&Context.Flags,
                  a2,
                  a3,
                  *((struct UnionFs::UfsUnionCtx **)a5 + 1),
                  *(struct _QUERY_ON_CREATE_ECP_CONTEXT **)&Context.Flags,
                  a6) >= 0 )
        goto LABEL_229;
      *(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) |= 4u;
    }
    else
    {
      *(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) |= 4u;
    }
    *(_DWORD *)(*(_QWORD *)&Context.Flags + 8LL) |= 4u;
LABEL_229:
    v108 = *(_DWORD **)&Context.Flags;
    if ( (*(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) & 4) != 0 )
    {
      **(_DWORD **)&Context.Flags &= ~4u;
      *(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) &= ~4u;
      v108 = *(_DWORD **)&Context.Flags;
      v160[0] = 1;
    }
    goto LABEL_231;
  }
  v28 = v166[0];
  FltReferenceContext(*((PFLT_CONTEXT *)v166[0] + 9));
  v29 = (_QWORD *)*((_QWORD *)v28 + 9);
  *(_QWORD *)&Context.Flags = v29;
  v30 = (const struct _FLT_RELATED_OBJECTS *)v29[4];
  FsFltWil::AcquireResourceExclusive(&Context.Thread, (char *)v30[2].Instance + 56);
  v31 = a2->Iopb;
  if ( v31->MajorFunction )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("Checking requested access on non-create");
LABEL_37:
    if ( Context.Thread )
    {
      ExReleaseResourceLite((PERESOURCE)Context.Thread);
      KeLeaveCriticalRegion();
    }
    v32 = *((_QWORD *)a5 + 1);
    v33 = a3->FileObject;
    Context.TagData = (struct _FLT_TAG_DATA_BUFFER *)v166[0];
    FsFltWil::AcquirePushLockShared(&Context.IoStatus.Information, v32 + 72);
    v35 = *(_QWORD *)(v32 + 48);
    v36 = *(volatile signed __int32 **)(v35 + 8);
    Context.Thread = *(const PETHREAD *)v35;
    if ( v36 )
      _InterlockedIncrement(v36 + 2);
    if ( Context.IoStatus.Information )
      FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Context.IoStatus.Information, v34);
    LODWORD(Entry) = 7;
    v37 = UnionFs::UfsShadowFileObject::SetUp(
            v33,
            a2,
            (UnionFs::UfsPathCachePayload *)Context.TagData,
            (struct UnionFs::StackEventTracer *)Entry,
            (__int64)a5 + 160,
            a6);
    if ( v36 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v36);
    if ( v37 == 259 )
    {
      LODWORD(Context.QueueLinks.Blink->Flink) = 2;
LABEL_88:
      if ( !v29 )
        goto LABEL_18;
      v47 = v29;
      goto LABEL_90;
    }
    if ( v37 >= 0 )
    {
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
        a3,
        *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
        *((struct UnionFs::UfsUnionCtx **)a5 + 1),
        v166[0],
        a6);
      v49 = Context.QueueLinks.Blink;
      a2->IoStatus.Status = 0;
      a2->IoStatus.Information = 1;
      LODWORD(v49->Flink) = 4;
      goto LABEL_88;
    }
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v37,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x23000020BC9LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
      "PUSH: Setting up shadow file object",
      Entrya);
LABEL_61:
    if ( v29 )
      FltReleaseContext(v29);
    goto LABEL_63;
  }
  v38 = *(_DWORD *)(v31->Parameters.WMI.ProviderId + 16);
  if ( (v38 & 0x10D0106) == 0 && (v38 & 0x2000000) == 0 )
    goto LABEL_37;
  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    v37 = UnionFs::Utils::BreakBatchAndHOplocks((UnionFs::Utils *)a2, (struct _FLT_CALLBACK_DATA *)a3, v30, a6, v148);
    if ( v37 == 259 )
    {
      if ( (unsigned int)dword_14009E178 > 4
        && (qword_14009E188 & 0x200200) != 0
        && (qword_14009E190 & 0x200200) == qword_14009E190 )
      {
        LODWORD(Context.Iopb) = 2921;
        Context.IoStatus.Information = (ULONG_PTR)"onecore\\base\\fs\\unionfs\\sys\\create.cpp";
        Context.TagData = (struct _FLT_TAG_DATA_BUFFER *)"UnionFs::UnionFsFilter::PreCreateFileOpenIf";
        *(_QWORD *)&Context.Flags = "Oplock break";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          qword_14009E190,
          (unsigned int)&dword_140095E1C,
          v39,
          v40,
          (__int64)&Context,
          (__int64)&Context.TagData,
          (__int64)&Context.IoStatus.Information,
          (__int64)&Context.Iopb);
      }
      v41 = (struct _ERESOURCE *)Context.Thread;
      LODWORD(Context.QueueLinks.Blink->Flink) = 2;
      if ( v41 )
      {
        ExReleaseResourceLite(v41);
        KeLeaveCriticalRegion();
      }
      goto LABEL_88;
    }
    if ( v37 < 0 )
    {
      v42 = "PUSH: Breaking oplocks";
      v43 = 0x6FA00020B70LL;
      goto LABEL_59;
    }
  }
  v37 = UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess(v166[0], a2, a6, 1);
  if ( v37 < 0 )
  {
    v42 = "PUSH: Checking caller access from cache";
    v43 = 0x56A00020B7BLL;
LABEL_59:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v37,
      (int)a6,
      (struct UnionFs::StackEventTracer *)v43,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
      v42,
      (const char *)a6);
    if ( Context.Thread )
    {
      ExReleaseResourceLite((PERESOURCE)Context.Thread);
      KeLeaveCriticalRegion();
    }
    goto LABEL_61;
  }
  v44 = *(_QWORD *)(a2->Iopb->Parameters.WMI.ProviderId + 8);
  v45 = *(unsigned int *)(v44 + 20);
  if ( (v45 & 0x10D0106) == 0 )
    goto LABEL_37;
  *(_DWORD *)&v162[8] = *(_DWORD *)(v44 + 24);
  v162[12] = 0;
  *(_WORD *)&v162[13] = 0;
  v162[15] = 0;
  LODWORD(v163) = 0;
  *(_WORD *)((char *)&v163 + 5) = 0;
  HIBYTE(v163) = 0;
  v159 = 0;
  Entry = (char *)v30;
  BYTE4(v163) = 1;
  *(_DWORD *)v162 = v45;
  *(_DWORD *)&v162[4] = 6;
  IsFileCowable = UnionFs::UnionFsFilter::CheckOplockAndShareAccess(v45, a2, a3, &Context, v162);
  if ( IsFileCowable >= 0 )
  {
    v46 = (struct _ERESOURCE *)Context.Thread;
    if ( IsFileCowable != 259 )
    {
      v159 = 1;
      if ( Context.Thread )
      {
        ExReleaseResourceLite((PERESOURCE)Context.Thread);
        KeLeaveCriticalRegion();
      }
      if ( *(_QWORD *)&Context.Flags )
        FltReleaseContext(*(PFLT_CONTEXT *)&Context.Flags);
      goto LABEL_27;
    }
    LODWORD(Context.QueueLinks.Blink->Flink) = 2;
    if ( v46 )
    {
      ExReleaseResourceLite(v46);
      KeLeaveCriticalRegion();
    }
    v47 = *(void **)&Context.Flags;
    if ( !*(_QWORD *)&Context.Flags )
      goto LABEL_18;
LABEL_90:
    FltReleaseContext(v47);
    goto LABEL_18;
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)IsFileCowable,
    (int)a6,
    (struct UnionFs::StackEventTracer *)0x6FB00020BA0LL,
    (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpenIf",
    "PUSH: Oplock and share access check",
    (const char *)v30);
  if ( Context.Thread )
  {
    ExReleaseResourceLite((PERESOURCE)Context.Thread);
    KeLeaveCriticalRegion();
  }
  if ( *(_QWORD *)&Context.Flags )
    FltReleaseContext(*(PFLT_CONTEXT *)&Context.Flags);
LABEL_180:
  UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v165);
  return (unsigned int)IsFileCowable;
}

```

## disassembly

```asm
0x1400156a8  mov     [rsp-8+arg_0], rbx
0x1400156ad  push    rbp
0x1400156ae  push    rsi
0x1400156af  push    rdi
0x1400156b0  push    r12
0x1400156b2  push    r13
0x1400156b4  push    r14
0x1400156b6  push    r15
0x1400156b8  lea     rbp, [rsp-520h]
0x1400156c0  sub     rsp, 630h
0x1400156c7  mov     rax, cs:__security_cookie
0x1400156ce  xor     rax, rsp
0x1400156d1  mov     [rbp+550h+var_40], rax
0x1400156d8  mov     rax, [rbp+550h+arg_30]
0x1400156df  mov     r13, rdx
0x1400156e2  mov     r15, [rbp+550h+arg_20]
0x1400156e9  xor     edx, edx
0x1400156eb  mov     rsi, [rbp+550h+arg_28]
0x1400156f2  mov     r14, r9
0x1400156f5  mov     [r9], edx
0x1400156f8  mov     r12, r8
0x1400156fb  mov     [rbp+550h+var_5A0], rax
0x1400156ff  mov     rax, [r8+20h]
0x140015703  mov     [rbp+550h+var_590], r9
0x140015707  mov     [rbp+550h+var_500], r8
0x14001570b  mov     ebx, [rax+50h]
0x14001570e  mov     rax, [r13+10h]
0x140015712  shr     ebx, 11h
0x140015715  not     ebx
0x140015717  and     ebx, 1
0x14001571a  cmp     [rax+4], dl
0x14001571d  jz      short loc_14001572F
0x14001571f  lea     rcx, aCheckingReques; "Checking requested access on non-create"
0x140015726  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14001572b  xor     edx, edx
0x14001572d  jmp     short loc_140015747
0x14001572f  mov     rax, [rax+18h]
0x140015733  mov     ecx, [rax+10h]
0x140015736  test    ecx, 10D0106h
0x14001573c  jnz     short loc_140015744
0x14001573e  bt      ecx, 19h
0x140015742  jnb     short loc_140015747
0x140015744  or      ebx, 8
0x140015747  xorps   xmm1, xmm1
0x14001574a  mov     [rbp+550h+Resource], rdx
0x14001574e  movd    eax, xmm1
0x140015752  xorps   xmm0, xmm0
0x140015755  movdqa  [rbp+550h+var_540], xmm1
0x14001575a  movdqa  xmmword ptr [rbp+550h+var_530], xmm0
0x14001575f  or      eax, 3
0x140015762  mov     [rbp+550h+var_518], 0
0x14001576a  mov     dword ptr [rbp+550h+var_540], eax
0x14001576d  mov     rax, [r15+8]
0x140015771  movdqa  [rbp+550h+var_510], xmm0
0x140015776  cmp     dword ptr [rax+1Ch], 2
0x14001577a  jnz     short loc_140015786
0x14001577c  mov     rax, [rax+20h]
0x140015780  mov     rcx, [rax+10h]
0x140015784  jmp     short loc_140015791
0x140015786  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14001578d  mov     rcx, [rax+50h]
0x140015791  mov     r8, [r15]
0x140015794  lea     rax, [rbp+550h+var_540]
0x140015798  mov     rdx, [r12+18h]
0x14001579d  mov     r9d, ebx
0x1400157a0  mov     [rsp+660h+var_630], r13
0x1400157a5  mov     [rsp+660h+Entry], rsi; char *
0x1400157aa  mov     [rsp+660h+var_640], rax; struct UnionFs::StackEventTracer *
0x1400157af  call    ?LookupEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@W4LookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,UnionFs::LookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x1400157b4  xor     r8d, r8d
0x1400157b7  mov     edi, eax
0x1400157b9  test    eax, eax
0x1400157bb  jns     short loc_1400157D3
0x1400157bd  lea     rax, aPushCacheLooku; "PUSH: Cache lookup"
0x1400157c4  mov     r8, 11F00020AF7h
0x1400157ce  jmp     loc_140015F36
0x1400157d3  mov     eax, dword ptr [rbp+550h+var_540+4]
0x1400157d6  mov     edx, 4
0x1400157db  mov     [rbp+550h+var_5D0], r8b
0x1400157df  test    eax, eax
0x1400157e1  jz      loc_1400158AB
0x1400157e7  test    byte ptr [rbp+550h+var_540+8], dl
0x1400157ea  jz      short loc_140015815
0x1400157ec  lea     ecx, [rdx-3]
0x1400157ef  cmp     eax, ecx
0x1400157f1  jz      short loc_140015804
0x1400157f3  mov     dword ptr [r13+18h], 0C000003Ah
0x1400157fb  mov     [r13+20h], r8
0x1400157ff  mov     [r14], edx
0x140015802  jmp     short loc_14001582B
0x140015804  lea     rdx, [rbp+550h+var_530]
0x140015808  mov     rcx, r15
0x14001580b  call    ?OverwriteTombstone@CreateContext@UnionFs@@QEAAX$$QEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@@Z; UnionFs::CreateContext::OverwriteTombstone(utl::shared_ptr<UnionFs::UfsPathCachePayload> &&)
0x140015810  jmp     loc_1400165BB
0x140015815  mov     r14d, 1
0x14001581b  cmp     dword ptr [rbp+550h+var_518], r14d
0x14001581f  jnz     short loc_140015833
0x140015821  mov     rax, [r15+0A0h]
0x140015828  or      dword ptr [rax], 8
0x14001582b  mov     edi, r8d
0x14001582e  jmp     loc_140016507
0x140015833  mov     rax, [rbp+550h+var_530]
0x140015837  movzx   ecx, word ptr [rax+0A0h]
0x14001583e  nop
0x14001583f  cmp     cx, dx
0x140015842  jnz     loc_140015963
0x140015848  mov     rax, [rbp+550h+var_530]
0x14001584c  cmp     [rax+0D0h], r8
0x140015853  jnz     short loc_140015864
0x140015855  lea     rcx, aResultsCacheen; "results.CacheEntry->GetOriginalScratchP"...
0x14001585c  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140015861  xor     r8d, r8d
0x140015864  cmp     dword ptr [rbp+550h+var_540+4], r14d
0x140015868  jz      short loc_14001582B
0x14001586a  mov     rcx, [rbp+550h+Resource]; Resource
0x14001586e  mov     [rbp+550h+Resource], r8
0x140015872  test    rcx, rcx
0x140015875  jz      short loc_140015892
0x140015877  call    cs:__imp_ExReleaseResourceLite
0x14001587e  nop     dword ptr [rax+rax+00h]
0x140015883  call    cs:__imp_KeLeaveCriticalRegion
0x14001588a  nop     dword ptr [rax+rax+00h]
0x14001588f  xor     r8d, r8d
0x140015892  mov     rcx, [rbp+550h+var_530+8]; this
0x140015896  mov     [rbp+550h+var_530+8], r8
0x14001589a  mov     [rbp+550h+var_530], r8
0x14001589e  test    rcx, rcx
0x1400158a1  jz      short loc_1400158AB
0x1400158a3  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400158a8  xor     r8d, r8d
0x1400158ab  cmp     dword ptr [rbp+550h+var_518], 2
0x1400158af  mov     [rbp+550h+P], r8
0x1400158b3  jnz     loc_140015E6E
0x1400158b9  mov     rax, qword ptr [rbp+550h+var_510+8]
0x1400158bd  lea     r8, [rbp+550h+Source]; Source
0x1400158c1  mov     rcx, [r15]
0x1400158c4  lea     rdx, [rbp+550h+var_558]; struct _UNICODE_STRING *
0x1400158c8  add     rcx, 8; this
0x1400158cc  mov     [rsp+660h+Entry], rsi; char *
0x1400158d1  movzx   r9d, word ptr [rax+18h]
0x1400158d6  movups  xmm0, xmmword ptr [rax]
0x1400158d9  mov     rax, qword ptr [rbp+550h+var_510]
0x1400158dd  movdqu  xmmword ptr [rbp+550h+Source.Length], xmm0
0x1400158e2  movups  xmm1, xmmword ptr [rax]
0x1400158e5  lea     rax, [rbp+550h+P]
0x1400158e9  mov     [rsp+660h+var_640], rax; P
0x1400158ee  movdqu  xmmword ptr [rbp+550h+var_558.Length], xmm1
0x1400158f3  call    ?AllocAndInitWithReplacedPathPrefix@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@00GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x1400158f8  xor     r14d, r14d
0x1400158fb  mov     edi, eax
0x1400158fd  test    eax, eax
0x1400158ff  jns     loc_140015E63
0x140015905  lea     rax, aPushReplacingS_3; "PUSH: Replacing substring"
0x14001590c  mov     r8, 38200020BFAh; struct UnionFs::StackEventTracer *
0x140015916  lea     r9, aUnionfsUnionfs_62; "UnionFs::UnionFsFilter::PreCreateFileOp"...
0x14001591d  mov     [rsp+660h+var_640], rax; char *
0x140015922  mov     rdx, rsi; int
0x140015925  mov     ecx, edi; this
0x140015927  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14001592c  mov     rbx, [rbp+550h+P]
0x140015930  test    rbx, rbx
0x140015933  jz      loc_140016507
0x140015939  cmp     [rbx+10h], r14b
0x14001593d  jnz     short loc_140015945
0x14001593f  xorps   xmm0, xmm0
0x140015942  movups  xmmword ptr [rbx], xmm0
0x140015945  mov     rcx, rbx; UnicodeString
0x140015948  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14001594d  xor     edx, edx; Tag
0x14001594f  mov     rcx, rbx; P
0x140015952  call    cs:__imp_ExFreePoolWithTag
0x140015959  nop     dword ptr [rax+rax+00h]
0x14001595e  jmp     loc_140016507
0x140015963  cmp     dword ptr [rbp+550h+var_540+4], r14d
0x140015967  jnz     loc_14001586A
0x14001596d  mov     rbx, [rbp+550h+var_530]
0x140015971  mov     rcx, [rbx+48h]; Context
0x140015975  call    cs:__imp_FltReferenceContext
0x14001597c  nop     dword ptr [rax+rax+00h]
0x140015981  mov     rdi, [rbx+48h]
0x140015985  lea     rcx, [rbp+550h+P]
0x140015989  mov     [rbp+550h+Context], rdi
0x14001598d  mov     rbx, [rdi+20h]
0x140015991  mov     rdx, [rbx+78h]
0x140015995  add     rdx, 38h ; '8'
0x140015999  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x14001599e  mov     rax, [r13+10h]
0x1400159a2  xor     r8d, r8d
0x1400159a5  cmp     [rax+4], r8b
0x1400159a9  jz      loc_140015A86
0x1400159af  lea     rcx, aCheckingReques; "Checking requested access on non-create"
0x1400159b6  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400159bb  mov     rcx, [rbp+550h+P]; Resource
0x1400159bf  test    rcx, rcx
0x1400159c2  jz      short loc_1400159DC
0x1400159c4  call    cs:__imp_ExReleaseResourceLite
0x1400159cb  nop     dword ptr [rax+rax+00h]
0x1400159d0  call    cs:__imp_KeLeaveCriticalRegion
0x1400159d7  nop     dword ptr [rax+rax+00h]
0x1400159dc  mov     rbx, [r15+8]
0x1400159e0  lea     rcx, [rbp+550h+var_5A8]
0x1400159e4  mov     rax, [rbp+550h+var_530]
0x1400159e8  mov     r14, [r12+20h]
0x1400159ed  mov     [rbp+550h+var_5A0], rax
0x1400159f1  lea     rdx, [rbx+48h]
0x1400159f5  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x1400159fa  mov     rax, [rbx+30h]
0x1400159fe  mov     rbx, [rax+8]
0x140015a02  mov     rcx, [rax]
0x140015a05  mov     [rbp+550h+P], rcx
0x140015a09  test    rbx, rbx
0x140015a0c  jz      short loc_140015A12
0x140015a0e  lock inc dword ptr [rbx+8]
0x140015a12  mov     rcx, [rbp+550h+var_5A8]; this
0x140015a16  test    rcx, rcx
0x140015a19  jz      short loc_140015A20
0x140015a1b  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140015a20  mov     r9, [rbp+550h+P]
0x140015a24  lea     rax, [r15+0A0h]
0x140015a2b  mov     [rsp+660h+var_628], rsi; struct UnionFs::Utils::CheckOplockHParams *
0x140015a30  mov     r8, r12
0x140015a33  mov     [rsp+660h+var_630], rax; __int64
0x140015a38  mov     rdx, r13; struct _FLT_CALLBACK_DATA *
0x140015a3b  mov     rax, [rbp+550h+var_5A0]
0x140015a3f  mov     rcx, r14; struct _FILE_OBJECT *
0x140015a42  mov     dword ptr [rsp+660h+Entry], 7; char *
0x140015a4a  mov     [rsp+660h+var_640], rax; UnionFs::UfsPathCachePayload *
0x140015a4f  call    ?SetUp@UfsShadowFileObject@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsLayerCtx@2@AEAVUfsPathCachePayload@2@W4ShareAccessCaller@2@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsShadowFileObject::SetUp(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsLayerCtx const &,UnionFs::UfsPathCachePayload &,UnionFs::ShareAccessCaller,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140015a54  xor     r8d, r8d
0x140015a57  mov     r14d, eax
0x140015a5a  test    rbx, rbx
0x140015a5d  jz      short loc_140015A6A
0x140015a5f  mov     rcx, rbx; this
0x140015a62  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140015a67  xor     r8d, r8d
0x140015a6a  cmp     r14d, 103h
0x140015a71  jnz     loc_140015DAD
0x140015a77  mov     rax, [rbp+550h+var_590]
0x140015a7b  mov     dword ptr [rax], 2
0x140015a81  jmp     loc_140015E46
0x140015a86  mov     rax, [rax+18h]
0x140015a8a  mov     ecx, [rax+10h]
0x140015a8d  test    ecx, 10D0106h
0x140015a93  jnz     short loc_140015A9F
0x140015a95  bt      ecx, 19h
0x140015a99  jnb     loc_1400159BB
0x140015a9f  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x140015aa4  test    eax, eax
0x140015aa6  jz      loc_140015BFB
0x140015aac  mov     r9, rsi; struct UnionFs::UfsFsContext *
0x140015aaf  mov     r8, rbx; struct _FLT_RELATED_OBJECTS *
0x140015ab2  mov     rdx, r12; struct _FLT_CALLBACK_DATA *
0x140015ab5  mov     rcx, r13; this
0x140015ab8  call    ?BreakBatchAndHOplocks@Utils@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsFsContext@2@AEAVStackEventTracer@2@@Z; UnionFs::Utils::BreakBatchAndHOplocks(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsFsContext &,UnionFs::StackEventTracer &)
0x140015abd  mov     r14d, eax
0x140015ac0  cmp     eax, 103h
0x140015ac5  jnz     loc_140015B8B
0x140015acb  mov     eax, cs:dword_14009E178
0x140015ad1  cmp     eax, 4
0x140015ad4  jbe     short loc_140015B51
0x140015ad6  mov     rcx, cs:qword_14009E190
0x140015add  mov     edx, 200200h
0x140015ae2  mov     rax, cs:qword_14009E188
0x140015ae9  test    rdx, rax
0x140015aec  jz      short loc_140015B51
0x140015aee  mov     rax, rcx
0x140015af1  and     rax, rdx
0x140015af4  cmp     rax, rcx
0x140015af7  jnz     short loc_140015B51
0x140015af9  lea     rax, aOnecoreBaseFsU_14; "onecore\\base\\fs\\unionfs\\sys\\create"...
0x140015b00  mov     [rbp+550h+var_5B8], 0B69h
0x140015b07  mov     [rbp+550h+var_5A8], rax
0x140015b0b  lea     rbx, aUnionfsUnionfs_62; "UnionFs::UnionFsFilter::PreCreateFileOp"...
0x140015b12  lea     rax, aOplockBreak; "Oplock break"
0x140015b19  mov     [rbp+550h+var_5A0], rbx
0x140015b1d  mov     [rbp+550h+Context], rax
0x140015b21  lea     rdx, dword_140095E1C
0x140015b28  lea     rax, [rbp+550h+var_5B8]
0x140015b2c  mov     [rsp+660h+var_628], rax
0x140015b31  lea     rax, [rbp+550h+var_5A8]
0x140015b35  mov     [rsp+660h+var_630], rax
0x140015b3a  lea     rax, [rbp+550h+var_5A0]
0x140015b3e  mov     [rsp+660h+Entry], rax
0x140015b43  lea     rax, [rbp+550h+Context]
0x140015b47  mov     [rsp+660h+var_640], rax
0x140015b4c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140015b51  mov     rax, [rbp+550h+var_590]
0x140015b55  xor     r8d, r8d
0x140015b58  mov     rcx, [rbp+550h+P]; Resource
0x140015b5c  mov     dword ptr [rax], 2
0x140015b62  test    rcx, rcx
0x140015b65  jz      loc_140015E46
0x140015b6b  call    cs:__imp_ExReleaseResourceLite
0x140015b72  nop     dword ptr [rax+rax+00h]
0x140015b77  call    cs:__imp_KeLeaveCriticalRegion
0x140015b7e  nop     dword ptr [rax+rax+00h]
0x140015b83  xor     r8d, r8d
0x140015b86  jmp     loc_140015E46
0x140015b8b  test    r14d, r14d
0x140015b8e  jns     short loc_140015BF5
  ... truncated ...
```
