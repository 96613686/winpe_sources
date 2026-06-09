# UnionFs::UnionFsFilter::PreCreateFileOpen(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,_FLT_PREOP_CALLBACK_STATUS &,UnionFs::CreateContext &,UnionFs::StackEventTracer &,UnionFs::UfsSiloCtx const *)

- ea: `0x140013b60`
- end: `0x140015684`
- name: `?PreCreateFileOpen@UnionFsFilter@UnionFs@@AEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAW4_FLT_PREOP_CALLBACK_STATUS@@AEAUCreateContext@2@AEAVStackEventTracer@2@PEBVUfsSiloCtx@2@@Z`
- size: `6948`
- prototype: `int(UnionFs::UnionFsFilter *__hidden this, struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, enum _FLT_PREOP_CALLBACK_STATUS *, struct UnionFs::CreateContext *, struct UnionFs::StackEventTracer *, const struct UnionFs::UfsSiloCtx *)`
- caller_count: `1`
- callee_count: `49`
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
- `0x14000efa0`
- `0x14000f514`
- `0x14000f81c`
- `0x140010168`
- `0x140010ba8`
- `0x140010d3c`
- `0x140010f28`
- `0x140011030`
- `0x140011168`
- `0x1400111b8`
- `0x1400114e4`
- `0x140013b60`
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

- `ntoskrnl!ExFreePoolWithTag` at `0x140013dee`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400143cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400145ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014665`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014693`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400146c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400146f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014788`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400147b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014818`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014849`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014b06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014d69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014d9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014e12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014e44`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014e72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014f76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014ffd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001510d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015155`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400151cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001529d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013dee`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400143cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400145ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014665`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014693`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400146c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400146f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014788`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400147b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014818`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014849`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014b06`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014d69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014d9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014e12`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014e44`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014e72`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014f76`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014ffd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001510d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015155`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400151cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001529d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152e3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013d17`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013eca`
- `ntoskrnl!ExReleaseResourceLite` at `0x140014069`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400140ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400141d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001421f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001425e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400142ec`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400151f9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015484`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013d17`
- `ntoskrnl!ExReleaseResourceLite` at `0x140013eca`
- `ntoskrnl!ExReleaseResourceLite` at `0x140014069`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400140ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400141d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001421f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001425e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400142ec`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400151f9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140015484`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013d23`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013ed6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014075`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400140c6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400141e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001422b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001426a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400142f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015205`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015490`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013d23`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013ed6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140014075`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400140c6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400141e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001422b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001426a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400142f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015205`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140015490`
- `FLTMGR!FltReferenceContext` at `0x140013e7a`
- `FLTMGR!FltReferenceContext` at `0x140013e7a`
- `FLTMGR!FltReleaseContext` at `0x1400140de`
- `FLTMGR!FltReleaseContext` at `0x140014244`
- `FLTMGR!FltReleaseContext` at `0x140014283`
- `FLTMGR!FltReleaseContext` at `0x1400142cb`
- `FLTMGR!FltReleaseContext` at `0x14001434a`
- `FLTMGR!FltReleaseContext` at `0x1400140de`
- `FLTMGR!FltReleaseContext` at `0x140014244`
- `FLTMGR!FltReleaseContext` at `0x140014283`
- `FLTMGR!FltReleaseContext` at `0x1400142cb`
- `FLTMGR!FltReleaseContext` at `0x14001434a`

## string_xrefs

- `0x140013bd8`: `Checking requested access on non-create`
- `0x140013eb5`: `Checking requested access on non-create`
- `0x140013ffa`: `onecore\base\fs\unionfs\sys\create.cpp`
- `0x140014a15`: `onecore\base\fs\unionfs\sys\create.cpp`
- `0x140013c6e`: `PUSH: Cache lookup`
- `0x140013cf9`: `results.CacheEntry->GetOriginalScratchPath()`
- `0x14001437f`: `PUSH: Allocating scratch path for layer lookup`
- `0x1400141a6`: `PUSH: Oplock and share access check`
- `0x140013db1`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x140013e46`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x14001400c`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x14001409b`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x1400141b7`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x1400142ac`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x1400143da`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x140014545`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x140014590`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x14001463a`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x140014758`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x140014d0e`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x140014f3a`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x14001518c`: `UnionFs::UnionFsFilter::PreCreateFileOpen`
- `0x140013e35`: `PUSH: Completing create with cached reparse data`
- `0x14001410a`: `PUSH: Checking caller access from cache`
- `0x14001441e`: `!results.CacheEntry`
- `0x140014cfd`: `PUSH: Allocating cache entry`
- `0x140014f24`: `PUSH: Inserting path cache payload`
- `0x140014a23`: `FileOpenCowNotInCache`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PreCreateFileOpen(
        UnionFs::UnionFsFilter *this,
        struct _FLT_CALLBACK_DATA *a2,
        struct _LIST_ENTRY *a3,
        enum _FLT_PREOP_CALLBACK_STATUS *a4,
        struct UnionFs::CreateContext *a5,
        struct _FLT_TAG_DATA_BUFFER *a6,
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
  struct UnionFs::StackEventTracer *v19; // r9
  const char *v20; // rax
  __int64 v21; // r8
  int v22; // ecx
  NTSTATUS v23; // eax
  struct _ERESOURCE *v24; // rcx
  utl::_RefCountBase *v25; // rcx
  UnionFs::Rtl *v26; // rcx
  struct _UNICODE_STRING *v27; // rdx
  const char *v28; // rax
  __int64 v29; // r8
  struct _UNICODE_STRING *v30; // rdx
  struct _UNICODE_STRING *v31; // rbx
  utl::_RefCountBase *v32; // rdi
  struct _FLT_CALLBACK_DATA *v33; // rdx
  _QWORD *v34; // rdi
  __int64 v35; // rbx
  PFLT_IO_PARAMETER_BLOCK v36; // rax
  __int64 v37; // rbx
  unsigned __int64 *v38; // rdx
  __int64 v39; // rax
  volatile signed __int32 *v40; // rbx
  int inited; // r15d
  int v42; // ecx
  int v43; // r8d
  int v44; // r9d
  struct _ERESOURCE *Thread; // rcx
  const char *v46; // rax
  __int64 v47; // r8
  void *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rcx
  struct _ERESOURCE *v51; // rcx
  struct _ERESOURCE *v52; // rcx
  PETHREAD v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rbx
  utl::_RefCountBase *v56; // r10
  unsigned int Data1; // r8d
  volatile signed __int32 *v58; // rbx
  __int64 v59; // r8
  struct _UNICODE_STRING *v60; // rdx
  USHORT PrintNameLength; // ax
  USHORT v62; // ax
  __int64 v63; // rcx
  NTSTATUS v64; // ebx
  struct _FLT_TAG_DATA_BUFFER *v65; // rdi
  struct _UNICODE_STRING *v66; // rdx
  struct _UNICODE_STRING *v67; // rbx
  bool v68; // zf
  __int64 v69; // rcx
  int v70; // eax
  struct _UNICODE_STRING *v71; // rdx
  utl::_RefCountBase *v72; // rcx
  struct _UNICODE_STRING *v73; // rbx
  utl::_RefCountBase *v74; // rcx
  struct _UNICODE_STRING *v75; // rbx
  int FileTag_low; // eax
  struct _UNICODE_STRING *v77; // rdx
  utl::_RefCountBase *v78; // rcx
  struct _UNICODE_STRING *v79; // rbx
  enum _FLT_PREOP_CALLBACK_STATUS *v80; // rax
  utl::_RefCountBase *v81; // rcx
  struct _UNICODE_STRING *Pointer; // rbx
  PFLT_IO_PARAMETER_BLOCK v84; // rax
  const UNICODE_STRING *v85; // rbx
  PIO_SECURITY_CONTEXT SecurityContext; // rcx
  ACCESS_MASK DesiredAccess; // eax
  int v88; // r8d
  int v89; // r9d
  PFLT_IO_PARAMETER_BLOCK v90; // rdx
  int v91; // ecx
  struct _UNICODE_STRING *p_UnicodeString; // rax
  UNICODE_STRING *p_Source; // rax
  struct _UNICODE_STRING *v94; // rdx
  utl::_RefCountBase *v95; // rcx
  _DWORD *v96; // rcx
  PWSTR *v97; // rcx
  char *v98; // rdx
  __int64 v99; // rdx
  struct _UNICODE_STRING *v100; // rdx
  struct _UNICODE_STRING *v101; // rbx
  utl::_RefCountBase *v102; // rcx
  int v103; // esi
  struct _UNICODE_STRING *v104; // rbx
  utl::_RefCountBase *v105; // rcx
  struct _UNICODE_STRING *v106; // rbx
  bool v107; // zf
  struct _UNICODE_STRING *v108; // r15
  __int64 v109; // rax
  __int64 v110; // rcx
  struct _LIST_ENTRY *v111; // rbx
  int inserted; // eax
  struct _UNICODE_STRING *v113; // rdx
  utl::_RefCountBase *v114; // rcx
  struct _UNICODE_STRING *v115; // rdx
  utl::_RefCountBase *v116; // rsi
  struct _FILE_OBJECT *v117; // rbx
  __int64 *ScratchLayer; // rax
  int v119; // ebx
  struct _UNICODE_STRING *v120; // rdx
  utl::_RefCountBase *v121; // rcx
  struct _UNICODE_STRING *v122; // rdx
  struct _ERESOURCE *v123; // rcx
  enum _FLT_PREOP_CALLBACK_STATUS *v124; // rax
  struct _UNICODE_STRING *v125; // rdx
  utl::_RefCountBase *v126; // rcx
  bool v127; // al
  __int64 v128; // r8
  __int64 v129; // rax
  const char *v130; // rax
  __int64 v131; // r8
  utl::_RefCountBase *v132; // rax
  utl::_RefCountBase *v133; // rcx
  utl::_RefCountBase *v134; // rcx
  struct _ERESOURCE *v135; // rcx
  utl::_RefCountBase *v136; // rcx
  utl::_RefCountBase *v137; // rax
  utl::_RefCountBase *v138; // rcx
  struct _UNICODE_STRING *v139; // rdx
  struct _UNICODE_STRING *v140; // rdx
  struct UnionFs::StackEventTracer *v141; // [rsp+20h] [rbp-F0h]
  struct _FLT_TAG_DATA_BUFFER *TagData; // [rsp+28h] [rbp-E8h]
  const char *v143; // [rsp+28h] [rbp-E8h]
  const char *v144; // [rsp+28h] [rbp-E8h]
  char *v145; // [rsp+28h] [rbp-E8h]
  const char *v146; // [rsp+28h] [rbp-E8h]
  const char *v147; // [rsp+28h] [rbp-E8h]
  struct UnionFs::Utils::CheckOplockHParams *v148; // [rsp+38h] [rbp-D8h]
  bool v149; // [rsp+90h] [rbp-80h] BYREF
  char v150; // [rsp+91h] [rbp-7Fh] BYREF
  struct _FLT_CALLBACK_DATA Context; // [rsp+98h] [rbp-78h] BYREF
  PVOID v152; // [rsp+F0h] [rbp-20h]
  enum _FLT_PREOP_CALLBACK_STATUS *v153; // [rsp+F8h] [rbp-18h] BYREF
  UnionFs::UfsPathCachePayload *v154; // [rsp+100h] [rbp-10h] BYREF
  __int128 v155; // [rsp+110h] [rbp+0h] BYREF
  utl::_RefCountBase *v156[2]; // [rsp+120h] [rbp+10h]
  PERESOURCE Resource; // [rsp+130h] [rbp+20h]
  __int64 v158; // [rsp+138h] [rbp+28h]
  __int128 v159; // [rsp+140h] [rbp+30h]
  UNICODE_STRING Source; // [rsp+150h] [rbp+40h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+160h] [rbp+50h] BYREF
  utl::_RefCountBase *v162; // [rsp+170h] [rbp+60h] BYREF
  UnionFs::UfsPathCachePayload *Blink; // [rsp+178h] [rbp+68h] BYREF
  utl::_RefCountBase *v164[2]; // [rsp+180h] [rbp+70h] BYREF
  int v165; // [rsp+190h] [rbp+80h] BYREF
  int v166; // [rsp+194h] [rbp+84h] BYREF
  char v167[8]; // [rsp+198h] [rbp+88h] BYREF
  PERESOURCE v168[2]; // [rsp+1A0h] [rbp+90h]
  volatile signed __int32 *v169; // [rsp+1B0h] [rbp+A0h]
  __int64 v170; // [rsp+1B8h] [rbp+A8h]
  char v171[8]; // [rsp+1C0h] [rbp+B0h] BYREF
  __int64 v172; // [rsp+1C8h] [rbp+B8h]
  _QWORD v173[3]; // [rsp+1D0h] [rbp+C0h] BYREF
  char v174; // [rsp+1E8h] [rbp+D8h]
  struct _UNICODE_STRING *v175; // [rsp+1F0h] [rbp+E0h] BYREF
  UNICODE_STRING *v176; // [rsp+1F8h] [rbp+E8h] BYREF
  const char *v177; // [rsp+200h] [rbp+F0h] BYREF
  char v178[8]; // [rsp+208h] [rbp+F8h] BYREF
  __int128 v179; // [rsp+210h] [rbp+100h]
  utl::_RefCountBase *v180[2]; // [rsp+220h] [rbp+110h]
  __int64 v181; // [rsp+230h] [rbp+120h]
  int v182; // [rsp+238h] [rbp+128h]
  struct _UNICODE_STRING v183; // [rsp+240h] [rbp+130h] BYREF
  char v184; // [rsp+250h] [rbp+140h]
  char v185[8]; // [rsp+280h] [rbp+170h] BYREF
  _QWORD v186[15]; // [rsp+288h] [rbp+178h] BYREF
  _BYTE v187[80]; // [rsp+300h] [rbp+1F0h] BYREF
  _BYTE v188[752]; // [rsp+350h] [rbp+240h] BYREF

  IsFileCowable = 0;
  v8 = a4;
  v9 = (struct _FLT_CALLBACK_DATA *)a3;
  *a4 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
  v154 = a7;
  Flink = (PFILE_OBJECT)a3[2].Flink;
  v153 = a4;
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
  v155 = 0;
  *(_OWORD *)v156 = 0;
  v158 = 0;
  LODWORD(v155) = _mm_cvtsi128_si32((__m128i)0LL) | 3;
  v16 = *((_QWORD *)a5 + 1);
  v159 = 0;
  if ( *(_DWORD *)(v16 + 28) == 2 )
    v17 = *(_QWORD *)(*(_QWORD *)(v16 + 32) + 16LL);
  else
    v17 = *((_QWORD *)UnionFs::g_FilterState + 10);
  TagData = a6;
  v18 = UnionFs::UfsPathCache::LookupEntry(v17, v9->IoStatus.Pointer, *(_QWORD *)a5, v14, &v155);
  if ( v18 < 0 )
  {
    v20 = "PUSH: Cache lookup";
    v21 = 0x21D000207DBLL;
LABEL_40:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v18,
      (int)a6,
      (struct UnionFs::StackEventTracer *)v21,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
      v20,
      (const char *)a6);
    goto LABEL_176;
  }
  v22 = DWORD1(v155);
  v149 = 0;
  if ( !DWORD1(v155) )
    goto LABEL_27;
  if ( (BYTE8(v155) & 4) != 0 )
  {
    v23 = -1073741772;
    a2->IoStatus.Information = 0;
    if ( v22 != 1 )
      v23 = -1073741766;
    a2->IoStatus.Status = v23;
    *v8 = FLT_PREOP_COMPLETE;
    goto LABEL_16;
  }
  if ( (_DWORD)v158 == 1 )
  {
    **((_DWORD **)a5 + 20) |= 8u;
LABEL_16:
    v18 = IsFileCowable;
    goto LABEL_176;
  }
  if ( *((_WORD *)v156[0] + 84) == 4 )
  {
    if ( !*((_QWORD *)v156[0] + 27) )
      MicrosoftTelemetryAssertTriggeredMsgKM("results.CacheEntry->GetOriginalScratchPath()");
    if ( DWORD1(v155) == 1 )
      goto LABEL_16;
    goto LABEL_23;
  }
  if ( DWORD1(v155) == 1 )
  {
    v32 = v156[0];
    v33 = (struct _FLT_CALLBACK_DATA *)*((_QWORD *)v156[0] + 12);
    if ( v33 && (a2->Iopb->Parameters.Create.Options & 0x200000) == 0 )
    {
      v18 = UnionFs::Utils::SetReparseDataFromCache(a2, v33, (const struct _REPARSE_DATA_BUFFER *)a6, v19);
      if ( v18 >= 0 )
      {
        a2->IoStatus.Status = 260;
        v18 = 0;
        *v8 = FLT_PREOP_COMPLETE;
        goto LABEL_176;
      }
      v20 = "PUSH: Completing create with cached reparse data";
      v21 = 0x7910002081ELL;
      goto LABEL_40;
    }
    FltReferenceContext(*((PFLT_CONTEXT *)v156[0] + 9));
    v34 = (_QWORD *)*((_QWORD *)v32 + 9);
    *(_QWORD *)&Context.Flags = v34;
    v35 = v34[4];
    Context.TagData = (struct _FLT_TAG_DATA_BUFFER *)v35;
    FsFltWil::AcquireResourceExclusive(&Context.Thread, *(_QWORD *)(v35 + 120) + 56LL);
    v36 = a2->Iopb;
    if ( v36->MajorFunction )
    {
      MicrosoftTelemetryAssertTriggeredMsgKM("Checking requested access on non-create");
      goto LABEL_44;
    }
    v42 = *(_DWORD *)(v36->Parameters.WMI.ProviderId + 16);
    if ( (v42 & 0x10D0106) != 0 || (v42 & 0x2000000) != 0 )
    {
      if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
      {
        v18 = UnionFs::Utils::BreakBatchAndHOplocks(
                (UnionFs::Utils *)a2,
                v9,
                (const struct _FLT_RELATED_OBJECTS *)v35,
                (struct UnionFs::UfsFsContext *)a6,
                v141);
        if ( v18 == 259 )
        {
          if ( (unsigned int)dword_14009E178 > 4
            && (qword_14009E188 & 0x200200) != 0
            && (qword_14009E190 & 0x200200) == qword_14009E190 )
          {
            LODWORD(Context.Iopb) = 2122;
            Context.TagData = (struct _FLT_TAG_DATA_BUFFER *)"onecore\\base\\fs\\unionfs\\sys\\create.cpp";
            v154 = (UnionFs::UfsPathCachePayload *)"UnionFs::UnionFsFilter::PreCreateFileOpen";
            Context.QueueLinks.Flink = (struct _LIST_ENTRY *)"Oplock break";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              qword_14009E190,
              (unsigned int)word_140095EDA,
              v43,
              v44,
              (__int64)&Context.QueueLinks,
              (__int64)&v154,
              (__int64)&Context.TagData,
              (__int64)&Context.Iopb);
            v8 = v153;
          }
          Thread = (struct _ERESOURCE *)Context.Thread;
          *v8 = FLT_PREOP_PENDING;
          if ( Thread )
          {
            ExReleaseResourceLite(Thread);
            KeLeaveCriticalRegion();
          }
          goto LABEL_97;
        }
        if ( v18 < 0 )
        {
          v46 = "PUSH: Breaking oplocks";
          v47 = 0x6F500020851LL;
LABEL_66:
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v18,
            (int)a6,
            (struct UnionFs::StackEventTracer *)v47,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
            v46,
            (const char *)a6);
          if ( Context.Thread )
          {
            ExReleaseResourceLite((PERESOURCE)Context.Thread);
            KeLeaveCriticalRegion();
          }
          if ( !v34 )
            goto LABEL_176;
          v48 = v34;
          goto LABEL_70;
        }
      }
      v18 = UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess(
              v156[0],
              a2,
              (struct UnionFs::StackEventTracer *)a6,
              1);
      if ( v18 < 0 )
      {
        v46 = "PUSH: Checking caller access from cache";
        v47 = 0x2890002085CLL;
        goto LABEL_66;
      }
      v49 = *(_QWORD *)(a2->Iopb->Parameters.WMI.ProviderId + 8);
      v50 = *(unsigned int *)(v49 + 20);
      if ( (v50 & 0x10D0106) != 0 )
      {
        *(_DWORD *)&Context.RequestorMode = *(_DWORD *)(v49 + 24);
        IsFileCowable = 0;
        TagData = Context.TagData;
        *(_WORD *)(&Context.RequestorMode + 5) = 0;
        *(&Context.RequestorMode + 7) = 0;
        *(_WORD *)((char *)&v152 + 5) = 0;
        HIBYTE(v152) = 0;
        *(&Context.RequestorMode + 4) = 0;
        LODWORD(v152) = 0;
        Context.QueueContext[1] = (PVOID)((unsigned int)v50 | 0x300000000LL);
        BYTE4(v152) = 1;
        v149 = 0;
        v18 = UnionFs::UnionFsFilter::CheckOplockAndShareAccess(v50, a2, v9, &Context, &Context.FilterContext[3]);
        if ( v18 >= 0 )
        {
          v51 = (struct _ERESOURCE *)Context.Thread;
          if ( v18 == 259 )
          {
            *v8 = FLT_PREOP_PENDING;
            if ( v51 )
            {
              ExReleaseResourceLite(v51);
              KeLeaveCriticalRegion();
            }
            if ( *(_QWORD *)&Context.Flags )
              FltReleaseContext(*(PFLT_CONTEXT *)&Context.Flags);
            goto LABEL_16;
          }
          v149 = 1;
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
          (struct UnionFs::StackEventTracer *)0x59E00020882LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
          "PUSH: Oplock and share access check",
          (const char *)TagData);
        if ( Context.Thread )
        {
          ExReleaseResourceLite((PERESOURCE)Context.Thread);
          KeLeaveCriticalRegion();
        }
        v48 = *(void **)&Context.Flags;
        if ( !*(_QWORD *)&Context.Flags )
          goto LABEL_176;
LABEL_70:
        FltReleaseContext(v48);
        goto LABEL_176;
      }
    }
LABEL_44:
    if ( Context.Thread )
    {
      ExReleaseResourceLite((PERESOURCE)Context.Thread);
      KeLeaveCriticalRegion();
    }
    v37 = *((_QWORD *)a5 + 1);
    *(_QWORD *)&Context.Flags = v9->IoStatus.Information;
    v154 = v156[0];
    FsFltWil::AcquirePushLockShared(&Context.TagData, v37 + 72);
    v39 = *(_QWORD *)(v37 + 48);
    v40 = *(volatile signed __int32 **)(v39 + 8);
    Context.Thread = *(const PETHREAD *)v39;
    if ( v40 )
      _InterlockedIncrement(v40 + 2);
    if ( Context.TagData )
      FsFltWil::Details::ReleasePushLockShared((FsFltWil::Details *)Context.TagData, v38);
    LODWORD(TagData) = 4;
    inited = UnionFs::UfsShadowFileObject::SetUp(
               *(struct _FILE_OBJECT **)&Context.Flags,
               a2,
               v9,
               (__int64)Context.Thread,
               (PFLT_CONTEXT *)v154,
               (struct UnionFs::StackEventTracer *)TagData,
               (__int64 *)a5 + 20,
               (struct UnionFs::Utils::CheckOplockHParams *)a6);
    if ( v40 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v40);
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
          (struct UnionFs::StackEventTracer *)0x21E000208ABLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
          "PUSH: Setting up shadow file object",
          v143);
        if ( v34 )
          FltReleaseContext(v34);
        goto LABEL_93;
      }
      v52 = Resource;
      Resource = 0;
      if ( v52 )
      {
        ExReleaseResourceLite(v52);
        KeLeaveCriticalRegion();
      }
      UnionFs::UnionFsFilter::HandleQoCEcpCached(
        (UnionFs::UnionFsFilter *)v52,
        a2,
        (const struct _FLT_RELATED_OBJECTS *)Context.QueueLinks.Flink,
        *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
        *((struct UnionFs::UfsUnionCtx **)a5 + 1),
        v156[0],
        (struct UnionFs::StackEventTracer *)a6);
      a2->IoStatus.Status = 0;
      a2->IoStatus.Information = 1;
      *v8 = FLT_PREOP_COMPLETE;
    }
LABEL_97:
    if ( v34 )
      FltReleaseContext(v34);
    IsFileCowable = 0;
    goto LABEL_16;
  }
LABEL_23:
  v24 = Resource;
  Resource = 0;
  if ( v24 )
  {
    ExReleaseResourceLite(v24);
    KeLeaveCriticalRegion();
  }
  v25 = v156[1];
  v156[1] = 0;
  v156[0] = 0;
  if ( v25 )
    utl::_RefCountBase::_DecStrong(v25);
LABEL_27:
  Context.Thread = 0;
  if ( (_DWORD)v158 != 2 )
    goto LABEL_101;
  v26 = (UnionFs::Rtl *)(*(_QWORD *)a5 + 8LL);
  Source = (UNICODE_STRING)**((_OWORD **)&v159 + 1);
  UnicodeString = *(struct _UNICODE_STRING *)v159;
  IsFileCowable = UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(
                    v26,
                    &UnicodeString,
                    &Source,
                    (PVOID)&Context.Thread,
                    (int)a6);
  if ( IsFileCowable < 0 )
  {
    v28 = "PUSH: Replacing substring";
    v29 = 0x381000208DCLL;
LABEL_30:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)IsFileCowable,
      (int)a6,
      (struct UnionFs::StackEventTracer *)v29,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
      v28,
      (const char *)TagData);
    v31 = (struct _UNICODE_STRING *)Context.Thread;
    goto LABEL_31;
  }
  v53 = Context.Thread;
  if ( !Context.Thread )
  {
LABEL_101:
    IsFileCowable = UnionFs::UfsPathName::AllocAndInit(*(_QWORD *)a5, &Context.Thread, a6);
    if ( IsFileCowable < 0 )
    {
      v28 = "PUSH: Allocating scratch path for layer lookup";
      v29 = 0x391000208E7LL;
      goto LABEL_30;
    }
    v53 = Context.Thread;
  }
  v54 = *((_QWORD *)a5 + 20);
  Context.Thread = 0;
  v55 = *(_QWORD *)(v54 + 64);
  *(_QWORD *)(v54 + 64) = v53;
  if ( v55 )
  {
    if ( !*(_BYTE *)(v55 + 16) )
      *(_OWORD *)v55 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v55, v27);
    ExFreePoolWithTag((PVOID)v55, 0);
  }
  Context.IoStatus.Pointer = 0;
  if ( !v149 )
  {
    if ( v156[0] )
      MicrosoftTelemetryAssertTriggeredMsgKM("!results.CacheEntry");
    v186[0] = off_14007E770;
    v186[13] = v186;
    UnionFs::StackEventTracer::SetIgnoreStatusCallback(a6, v185);
    memset(v187, 0, 0x48u);
    inited = UnionFs::Utils::StatItemAsCaller(*(_QWORD *)a5 + 8LL, v9->IoStatus.Pointer, v59, v187, a2);
    PrintNameLength = a6[17].SymbolicLinkReparseBuffer.PrintNameLength;
    if ( PrintNameLength )
    {
      v62 = PrintNameLength - 1;
      a6[17].SymbolicLinkReparseBuffer.PrintNameLength = v62;
      v63 = 120 * (v62 + 1LL);
      v60 = *(struct _UNICODE_STRING **)((char *)&a6->FileTag + v63);
      *(_QWORD *)((char *)&a6->FileTag + v63) = 0;
      if ( v60 )
        (*(void (__fastcall **)(struct _UNICODE_STRING *))(*(_QWORD *)&v60->Length + 24LL))(v60);
    }
    if ( inited == 260 )
      goto LABEL_147;
    if ( (a2->Iopb->OperationFlags & 4) != 0 && inited == -1073741772 )
    {
      v64 = -1073741766;
      inited = -1073741766;
    }
    else
    {
      if ( inited >= 0 )
      {
LABEL_171:
        Pointer = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
        if ( Context.IoStatus.Pointer )
        {
          if ( !*((_BYTE *)Context.IoStatus.Pointer + 16) )
            *(_OWORD *)Context.IoStatus.Pointer = 0;
          FsFltWil::Details::FreeUnicodeString(Pointer, v60);
          ExFreePoolWithTag(Pointer, 0);
        }
        v18 = 0;
        goto LABEL_176;
      }
      v64 = -1073741766;
      if ( inited != -1073741766 && inited != -1073741772 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)inited,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x28B00020928LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
          "PUSH: Querying stat information",
          (const char *)a6);
        v67 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
        if ( !Context.IoStatus.Pointer )
        {
LABEL_93:
          v18 = inited;
          goto LABEL_176;
        }
        v68 = *((_BYTE *)Context.IoStatus.Pointer + 16) == 0;
LABEL_128:
        if ( v68 )
          *v67 = 0;
        FsFltWil::Details::FreeUnicodeString(v67, v66);
        ExFreePoolWithTag(v67, 0);
        goto LABEL_93;
      }
    }
    utl::make_unique<UnionFs::FindAndStatResults,,0>(&Context.TagData);
    v65 = Context.TagData;
    if ( !Context.TagData )
    {
      IsFileCowable = -1073741670;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x3FC0002093ALL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
        "ORIGIN: Allocating findAndStatResults",
        (const char *)a6);
      v31 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
LABEL_31:
      if ( v31 )
      {
        if ( !LOBYTE(v31[1].Length) )
          *v31 = 0;
        FsFltWil::Details::FreeUnicodeString(v31, v30);
        ExFreePoolWithTag(v31, 0);
      }
      goto LABEL_16;
    }
    *(_QWORD *)&Context.TagData[3].GenericGUIDReparseBuffer.TagGuid.Data2 = &Context.IoStatus;
    v69 = *((_QWORD *)a5 + 1);
    TagData = v65;
    Source = *(UNICODE_STRING *)*(_QWORD *)(*((_QWORD *)a5 + 20) + 64LL);
    v70 = UnionFs::UfsUnionCtx::FindAndStatItemInLayersAsCaller(v69, a2, &Source);
    LODWORD(Context.Iopb) = v70;
    if ( v70 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v70,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x28C00020945LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
        "PUSH: Statting item in layers",
        (const char *)v65);
LABEL_133:
      if ( v65 )
      {
        v72 = *(utl::_RefCountBase **)&v65[3].TagDataLength;
        if ( v72 )
          utl::_RefCountBase::_DecStrong(v72);
        ExFreePoolWithTag(v65, 0);
      }
      v73 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
      if ( Context.IoStatus.Pointer )
      {
        if ( !*((_BYTE *)Context.IoStatus.Pointer + 16) )
          *(_OWORD *)Context.IoStatus.Pointer = 0;
        FsFltWil::Details::FreeUnicodeString(v73, v71);
        ExFreePoolWithTag(v73, 0);
      }
      v18 = (int)Context.Iopb;
      goto LABEL_176;
    }
    if ( v70 == 260 )
    {
      if ( v65 )
      {
        v74 = *(utl::_RefCountBase **)&v65[3].TagDataLength;
        if ( v74 )
          utl::_RefCountBase::_DecStrong(v74);
        ExFreePoolWithTag(v65, 0);
      }
LABEL_147:
      v75 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
      if ( Context.IoStatus.Pointer )
      {
        if ( !*((_BYTE *)Context.IoStatus.Pointer + 16) )
          *(_OWORD *)Context.IoStatus.Pointer = 0;
        FsFltWil::Details::FreeUnicodeString(v75, v60);
        ExFreePoolWithTag(v75, 0);
      }
      v18 = 260;
      goto LABEL_176;
    }
    FileTag_low = LOWORD(v65->FileTag);
    if ( (_WORD)FileTag_low != 1 )
    {
      if ( FileTag_low == 2 )
      {
        if ( inited == -1073741772 )
          v64 = -1073741772;
      }
      else
      {
        if ( FileTag_low != 3 )
        {
          MicrosoftTelemetryAssertTriggeredMsgKM("false");
          UnionFs::ProcessTraceStatusOrigin(
            (UnionFs *)0xC00000E5LL,
            (int)a6,
            (struct UnionFs::StackEventTracer *)0x60B0002096BLL,
            (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
            "ORIGIN: Unexpected LAYER_FIND_RESULT",
            (const char *)v65);
          if ( v65 )
          {
            v78 = *(utl::_RefCountBase **)&v65[3].TagDataLength;
            if ( v78 )
              utl::_RefCountBase::_DecStrong(v78);
            ExFreePoolWithTag(v65, 0);
          }
          v79 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
          if ( Context.IoStatus.Pointer )
          {
            if ( !*((_BYTE *)Context.IoStatus.Pointer + 16) )
              *(_OWORD *)Context.IoStatus.Pointer = 0;
            FsFltWil::Details::FreeUnicodeString(v79, v77);
            ExFreePoolWithTag(v79, 0);
          }
          v18 = -1073741595;
          goto LABEL_176;
        }
        v64 = (a2->Iopb->OperationFlags & 4) != 0 ? -1073741766 : -1073741772;
      }
      v80 = v153;
      a2->IoStatus.Status = v64;
      a2->IoStatus.Information = 0;
      *v80 = FLT_PREOP_COMPLETE;
      if ( v65 )
      {
        v81 = *(utl::_RefCountBase **)&v65[3].TagDataLength;
        if ( v81 )
          utl::_RefCountBase::_DecStrong(v81);
        ExFreePoolWithTag(v65, 0);
      }
      goto LABEL_171;
    }
    v84 = a2->Iopb;
    v85 = (const UNICODE_STRING *)Context.IoStatus.Pointer;
    Data1 = v65[2].GenericGUIDReparseBuffer.TagGuid.Data1;
    Context.TagData = (struct _FLT_TAG_DATA_BUFFER *)Context.IoStatus.Pointer;
    SecurityContext = v84->Parameters.Create.SecurityContext;
    LODWORD(Context.Iopb) = Data1;
    DesiredAccess = SecurityContext->DesiredAccess;
    if ( (DesiredAccess & 0x2000000) != 0 )
    {
      if ( (*(_DWORD *)&v65[2].GenericGUIDReparseBuffer.TagGuid.Data4[4] & 0x10D0106) != 0 )
        goto LABEL_179;
    }
    else if ( (DesiredAccess & 0x10D0106) != 0 )
    {
LABEL_179:
      if ( (unsigned int)dword_14009E178 > 5
        && (qword_14009E188 & 0x10000) != 0
        && (qword_14009E190 & 0x10000) == qword_14009E190 )
      {
        UnicodeString = 0;
        UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v188, 0x1D00020A4BuLL);
        UnionFs::Utils::GetUserSidString(a2, &UnicodeString, v188);
        Source = *v85;
        if ( (unsigned int)dword_14009E178 > 5
          && (qword_14009E188 & 0x30200) != 0
          && (qword_14009E190 & 0x30200) == qword_14009E190 )
        {
          v90 = a2->Iopb;
          LODWORD(Context.IoStatus.Information) = *(_DWORD *)&v65[2].GenericGUIDReparseBuffer.TagGuid.Data4[4];
          *(_QWORD *)v171 = "UnionFs::UnionFsFilter::PreCreateFileOpen";
          v165 = *(_DWORD *)(*(_QWORD *)(v90->Parameters.WMI.ProviderId + 8) + 24LL);
          v166 = *(_DWORD *)(*(_QWORD *)(v90->Parameters.WMI.ProviderId + 8) + 20LL);
          LODWORD(v162) = *(_DWORD *)(*(_QWORD *)(v90->Parameters.WMI.ProviderId + 8) + 16LL);
          LODWORD(Blink) = *(_DWORD *)(*(_QWORD *)(v90->Parameters.WMI.ProviderId + 8) + 12LL);
          LODWORD(v153) = *(_DWORD *)(v90->Parameters.WMI.ProviderId + 16);
          v91 = *(_DWORD *)(v90->Parameters.WMI.ProviderId + 16);
          p_UnicodeString = &UnicodeString;
          Context.Flags = 2664;
          v149 = (v91 & 0x2000000) != 0;
          if ( !UnicodeString.Buffer )
            p_UnicodeString = (struct _UNICODE_STRING *)&FsTlEmptyUnicodeString;
          v175 = p_UnicodeString;
          p_Source = &Source;
          if ( !Source.Buffer )
            p_Source = (UNICODE_STRING *)&FsTlEmptyUnicodeString;
          v176 = p_Source;
          v177 = "onecore\\base\\fs\\unionfs\\sys\\create.cpp";
          Context.QueueLinks.Blink = (struct _LIST_ENTRY *)"FileOpenCowNotInCache";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&FsTlEmptyUnicodeString,
            (unsigned int)byte_1400964CB,
            v88,
            v89,
            (__int64)&Context.QueueLinks.Blink,
            (__int64)v171,
            (__int64)&v177,
            (__int64)&Context,
            (__int64)&v176,
            (__int64)&v175,
            (__int64)&v149,
            (__int64)&v153,
            (__int64)&Blink,
            (__int64)&v162,
            (__int64)&v166,
            (__int64)&v165,
            (__int64)&Context.IoStatus.Information);
        }
        UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v188);
        FsFltWil::Details::FreeUnicodeString(&UnicodeString, v94);
        Data1 = (unsigned int)Context.Iopb;
      }
      v58 = *(volatile signed __int32 **)&v65[3].TagDataLength;
      *(_QWORD *)&Context.Flags = *(_QWORD *)v65[2].GenericGUIDReparseBuffer.DataBuffer;
      if ( v58 )
        _InterlockedIncrement(v58 + 2);
      if ( v65 )
      {
        v95 = *(utl::_RefCountBase **)&v65[3].TagDataLength;
        if ( v95 )
          utl::_RefCountBase::_DecStrong(v95);
        ExFreePoolWithTag(v65, 0);
        Data1 = (unsigned int)Context.Iopb;
      }
      v9 = (struct _FLT_CALLBACK_DATA *)Context.QueueLinks.Flink;
      v56 = v156[0];
      goto LABEL_198;
    }
    *(_QWORD *)v171 = *((_QWORD *)&v159 + 1);
    v172 = v159;
    *(_OWORD *)&Context.FilterContext[3] = 0;
    v152 = 0;
    *(_QWORD *)&Context.Flags = 0;
    LODWORD(Context.IoStatus.Information) = 0;
    v149 = 0;
    v150 = 0;
    if ( !UnionFs::Utils::GetQueryOnCreateEcp(
            a2,
            &Context,
            (struct _QUERY_ON_CREATE_ECP_CONTEXT **)&Context.IoStatus.Information,
            0) )
    {
LABEL_217:
      v97 = *(PWSTR **)v65[2].GenericGUIDReparseBuffer.DataBuffer;
      v98 = v171;
      v173[0] = &v149;
      v174 = 1;
      v173[1] = &Context;
      if ( (_DWORD)v158 != 2 )
        v98 = 0;
      v173[2] = &v150;
      UnicodeString = 0;
      _InterlockedIncrement((volatile signed __int32 *)*v97 + 2);
      v148 = (struct UnionFs::Utils::CheckOplockHParams *)v98;
      v99 = *((_QWORD *)a5 + 1);
      *(_QWORD *)&UnicodeString.Length = v97;
      UnicodeString.Buffer = *v97;
      inited = UnionFs::UfsPathCachePayload::AllocAndInitShared(
                 a2,
                 v99,
                 (__int64)&UnicodeString,
                 v85,
                 (int)Context.Iopb,
                 &Context.QueueContext[1],
                 (struct UnionFs::Utils::CallerAccessParams *)a6,
                 (__int64)v148);
      if ( inited < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)inited,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x438000209D7LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
          "PUSH: Allocating cache entry",
          v144);
        if ( v149 )
        {
          **(_DWORD **)&Context.Flags |= 4u;
          *(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) |= 4u;
        }
        if ( v150 )
          **(_DWORD **)&Context.Flags |= 8u;
        v101 = (struct _UNICODE_STRING *)v152;
        if ( v152 )
        {
          if ( !*((_BYTE *)v152 + 16) )
            *(_OWORD *)v152 = 0;
          FsFltWil::Details::FreeUnicodeString(v101, v66);
          ExFreePoolWithTag(v101, 0);
        }
        if ( *(_QWORD *)&Context.RequestorMode )
          utl::_RefCountBase::_DecStrong(*(utl::_RefCountBase **)&Context.RequestorMode);
        if ( v65 )
        {
          v102 = *(utl::_RefCountBase **)&v65[3].TagDataLength;
          if ( v102 )
            utl::_RefCountBase::_DecStrong(v102);
          ExFreePoolWithTag(v65, 0);
        }
        v67 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
        if ( !Context.IoStatus.Pointer )
          goto LABEL_93;
        v68 = *((_BYTE *)Context.IoStatus.Pointer + 16) == 0;
        goto LABEL_128;
      }
      v103 = 260;
      if ( inited == 260 )
      {
        if ( v149 )
        {
          **(_DWORD **)&Context.Flags |= 4u;
          *(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) |= 4u;
        }
        if ( v150 )
          **(_DWORD **)&Context.Flags |= 8u;
        v104 = (struct _UNICODE_STRING *)v152;
        if ( v152 )
        {
          if ( !*((_BYTE *)v152 + 16) )
            *(_OWORD *)v152 = 0;
          FsFltWil::Details::FreeUnicodeString(v104, v100);
          ExFreePoolWithTag(v104, 0);
        }
        if ( *(_QWORD *)&Context.RequestorMode )
          utl::_RefCountBase::_DecStrong(*(utl::_RefCountBase **)&Context.RequestorMode);
        if ( v65 )
        {
          v105 = *(utl::_RefCountBase **)&v65[3].TagDataLength;
          if ( v105 )
            utl::_RefCountBase::_DecStrong(v105);
          ExFreePoolWithTag(v65, 0);
        }
        v106 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
        if ( !Context.IoStatus.Pointer )
          goto LABEL_256;
        v107 = *((_BYTE *)Context.IoStatus.Pointer + 16) == 0;
LABEL_253:
        if ( v107 )
          *v106 = 0;
        FsFltWil::Details::FreeUnicodeString(v106, v100);
        ExFreePoolWithTag(v106, 0);
LABEL_256:
        v18 = v103;
        goto LABEL_176;
      }
      v103 = 0;
      v108 = (struct _UNICODE_STRING *)v152;
      *(_OWORD *)&Context.FilterContext[1] = *(_OWORD *)&Context.FilterContext[3];
      v109 = *((_QWORD *)a5 + 1);
      *(_OWORD *)&Context.FilterContext[3] = 0;
      v152 = 0;
      *(_QWORD *)v167 = 0;
      v68 = *(_DWORD *)(v109 + 28) == 2;
      *(_OWORD *)v168 = 0;
      v169 = 0;
      v170 = 0;
      if ( v68 )
        v110 = *(_QWORD *)(*(_QWORD *)(v109 + 32) + 16LL);
      else
        v110 = *((_QWORD *)UnionFs::g_FilterState + 10);
      v111 = Context.QueueLinks.Flink;
      v145 = v167;
      inserted = UnionFs::UfsPathCache::InsertEntry(
                   v110,
                   Context.QueueLinks.Flink[1].Blink,
                   v108,
                   1,
                   &Context.FilterContext[1]);
      LODWORD(Context.Iopb) = inserted;
      if ( inserted < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)inserted,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x43E000209EDLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
          "PUSH: Inserting path cache payload",
          v167);
        UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v167);
        if ( v108 )
        {
          if ( !LOBYTE(v108[1].Length) )
            *v108 = 0;
          FsFltWil::Details::FreeUnicodeString(v108, v113);
          ExFreePoolWithTag(v108, 0);
        }
        v114 = (utl::_RefCountBase *)Context.QueueContext[0];
LABEL_266:
        if ( v114 )
          utl::_RefCountBase::_DecStrong(v114);
        wil::details::lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___::_lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___(v173);
        utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(&Context.FilterContext[3]);
        goto LABEL_133;
      }
      if ( *(_DWORD *)v167 == 2 )
      {
        v116 = (utl::_RefCountBase *)v169;
        Blink = (UnionFs::UfsPathCachePayload *)v168[1];
        v162 = (utl::_RefCountBase *)v169;
        if ( v169 )
          _InterlockedIncrement(v169 + 2);
        if ( Context.QueueContext[0] )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Context.QueueContext[0]);
      }
      else
      {
        if ( *(_DWORD *)v167 == 3 )
        {
          if ( (v170 & 1) == 0 )
            MicrosoftTelemetryAssertTriggeredMsgKM("WI_IsFlagSet(insertResults.Flags, InsertEntryResultsFlags::StoppedOnHardTombstone)");
          UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v167);
          if ( v108 )
          {
            if ( !LOBYTE(v108[1].Length) )
              *v108 = 0;
            FsFltWil::Details::FreeUnicodeString(v108, v115);
            ExFreePoolWithTag(v108, 0);
          }
          if ( Context.QueueContext[0] )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Context.QueueContext[0]);
          wil::details::lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___::_lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___(v173);
          utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(&Context.FilterContext[3]);
          goto LABEL_295;
        }
        v116 = (utl::_RefCountBase *)Context.QueueContext[0];
        v162 = (utl::_RefCountBase *)Context.QueueContext[0];
        Blink = (UnionFs::UfsPathCachePayload *)Context.QueueLinks.Blink;
      }
      v117 = (struct _FILE_OBJECT *)v111[2].Flink;
      ScratchLayer = (__int64 *)UnionFs::UfsUnionCtx::GetScratchLayer(*((_QWORD *)a5 + 1), &Source);
      LODWORD(v145) = 5;
      v119 = UnionFs::UfsShadowFileObject::SetUp(
               v117,
               a2,
               (struct _FLT_CALLBACK_DATA *)Context.QueueLinks.Flink,
               *ScratchLayer,
               (PFLT_CONTEXT *)Blink,
               (struct UnionFs::StackEventTracer *)v145,
               (__int64 *)a5 + 20,
               (struct UnionFs::Utils::CheckOplockHParams *)a6);
      LODWORD(Context.Iopb) = v119;
      if ( Source.Buffer )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)Source.Buffer);
      if ( v119 != 259 )
      {
        if ( v119 >= 0 )
        {
          v123 = v168[0];
          v18 = 0;
          v168[0] = 0;
          if ( v123 )
          {
            ExReleaseResourceLite(v123);
            KeLeaveCriticalRegion();
          }
          if ( v150 )
          {
            *(_QWORD *)(*(_QWORD *)&Context.Flags + 152LL) = 0;
            *(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) |= 8u;
          }
          UnionFs::UnionFsFilter::VirtualizeQoCEcpIDs(
            (UnionFs::UnionFsFilter *)v123,
            a2,
            (const struct _FLT_RELATED_OBJECTS *)Context.QueueLinks.Flink,
            *((const struct UnionFs::UfsStreamHandleCtx **)a5 + 20),
            *((struct UnionFs::UfsUnionCtx **)a5 + 1),
            (struct UnionFs::StackEventTracer *)a6,
            *(struct _QUERY_ON_CREATE_ECP_CONTEXT **)&Context.Flags,
            Context.IoStatus.Information);
          v124 = v153;
          a2->IoStatus.Status = 0;
          a2->IoStatus.Information = 1;
          *v124 = FLT_PREOP_COMPLETE;
          UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v167);
          if ( v108 )
          {
            if ( !LOBYTE(v108[1].Length) )
              *v108 = 0;
            FsFltWil::Details::FreeUnicodeString(v108, v125);
            ExFreePoolWithTag(v108, 0);
          }
          if ( v116 )
            utl::_RefCountBase::_DecStrong(v116);
          wil::details::lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___::_lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___(v173);
          utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(&Context.FilterContext[3]);
          if ( v65 )
          {
            v126 = *(utl::_RefCountBase **)&v65[3].TagDataLength;
            if ( v126 )
              utl::_RefCountBase::_DecStrong(v126);
            ExFreePoolWithTag(v65, 0);
          }
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.IoStatus);
          utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.Thread);
          goto LABEL_176;
        }
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v119,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x45100020A27LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
          "PUSH: Setting up shadow file object",
          v146);
        UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v167);
        if ( v108 )
        {
          if ( !LOBYTE(v108[1].Length) )
            *v108 = 0;
          FsFltWil::Details::FreeUnicodeString(v108, v122);
          ExFreePoolWithTag(v108, 0);
        }
        v114 = v162;
        goto LABEL_266;
      }
      *v153 = FLT_PREOP_PENDING;
      UnionFs::InsertEaResults::~InsertEaResults((UnionFs::InsertEaResults *)v167);
      if ( v108 )
      {
        if ( !LOBYTE(v108[1].Length) )
          *v108 = 0;
        FsFltWil::Details::FreeUnicodeString(v108, v120);
        ExFreePoolWithTag(v108, 0);
      }
      if ( v116 )
        utl::_RefCountBase::_DecStrong(v116);
      wil::details::lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___::_lambda_call__lambda_cd500c22a50728045e24f9f9318e0169___(v173);
      utl::pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>::~pair<utl::shared_ptr<UnionFs::UfsPathCachePayload>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>(&Context.FilterContext[3]);
      v103 = 0;
LABEL_295:
      if ( v65 )
      {
        v121 = *(utl::_RefCountBase **)&v65[3].TagDataLength;
        if ( v121 )
          utl::_RefCountBase::_DecStrong(v121);
        ExFreePoolWithTag(v65, 0);
      }
      v106 = (struct _UNICODE_STRING *)Context.IoStatus.Pointer;
      if ( !Context.IoStatus.Pointer )
        goto LABEL_256;
      v107 = *((_BYTE *)Context.IoStatus.Pointer + 16) == 0;
      goto LABEL_253;
    }
    v96 = *(_DWORD **)&Context.Flags;
    if ( (**(_DWORD **)&Context.Flags & 4) == 0 )
    {
LABEL_215:
      if ( (*v96 & 8) != 0 )
      {
        *v96 &= ~8u;
        v150 = 1;
      }
      goto LABEL_217;
    }
    if ( LODWORD(Context.IoStatus.Information) >= 0x88 )
    {
      if ( (int)UnionFs::UnionFsFilter::HandleQoCEcpEaInfo(
                  *(UnionFs::UnionFsFilter **)&Context.Flags,
                  a2,
                  (const struct _FLT_RELATED_OBJECTS *)Context.QueueLinks.Flink,
                  *((struct UnionFs::UfsUnionCtx **)a5 + 1),
                  *(struct _QUERY_ON_CREATE_ECP_CONTEXT **)&Context.Flags,
                  (struct UnionFs::StackEventTracer *)a6) >= 0 )
        goto LABEL_213;
      *(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) |= 4u;
    }
    else
    {
      *(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) |= 4u;
    }
    *(_DWORD *)(*(_QWORD *)&Context.Flags + 8LL) |= 4u;
LABEL_213:
    v96 = *(_DWORD **)&Context.Flags;
    if ( (*(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) & 4) != 0 )
    {
      **(_DWORD **)&Context.Flags &= ~4u;
      *(_DWORD *)(*(_QWORD *)&Context.Flags + 4LL) &= ~4u;
      v96 = *(_DWORD **)&Context.Flags;
      v149 = 1;
    }
    goto LABEL_215;
  }
  v56 = v156[0];
  Data1 = 0;
  v58 = (volatile signed __int32 *)*((_QWORD *)v156[0] + 5);
  *(_QWORD *)&Context.Flags = *((_QWORD *)v156[0] + 4);
  if ( v58 )
  {
    _InterlockedIncrement(v58 + 2);
    v56 = v156[0];
  }
  Context.TagData = (struct _FLT_TAG_DATA_BUFFER *)*((_QWORD *)v56 + 6);
LABEL_198:
  if ( (*(_DWORD *)(*((_QWORD *)a5 + 1) + 24LL) & 0x80u) != 0 )
  {
    v149 = 0;
    if ( v56 )
    {
      IsFileCowable = UnionFs::Utils::IsFileCowable(
                        (UnionFs::Utils *)&v149,
                        (bool *)v56,
                        (struct UnionFs::UfsPathCachePayload *)a6,
                        0);
      if ( IsFileCowable < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)IsFileCowable,
          (int)a6,
          (struct UnionFs::StackEventTracer *)0x78100020A7FLL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
          "PUSH: Checking immutability",
          (const char *)TagData);
LABEL_202:
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.IoStatus);
        if ( v58 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v58);
        utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.Thread);
        goto LABEL_16;
      }
      v56 = v156[0];
      v127 = v149;
    }
    else
    {
      v127 = (Data1 & 0x800010) != 0;
    }
    if ( !v127 )
    {
      if ( (unsigned int)dword_14009E178 > 5
        && (qword_14009E188 & 0x400000000000LL) != 0
        && (qword_14009E190 & 0x400000000000LL) == qword_14009E190 )
      {
        Context.QueueLinks.Blink = (struct _LIST_ENTRY *)1;
        *(_QWORD *)v171 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          qword_14009E190,
          (unsigned int)&dword_140096384,
          Data1,
          (unsigned int)v171,
          (__int64)&Context.QueueLinks.Blink);
      }
      IsFileCowable = -1073741790;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000022LL,
        (int)a6,
        (struct UnionFs::StackEventTracer *)0x78200020A91LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
        "ORIGIN: Rejecting COW for immutable file",
        (const char *)TagData);
      goto LABEL_202;
    }
  }
  LOBYTE(Context.FilterContext[2]) = 1;
  Context.QueueLinks.Blink = (struct _LIST_ENTRY *)v164;
  *(_OWORD *)v164 = 0;
  if ( v56 )
  {
    v128 = v159;
    *(_QWORD *)&Source.Length = *((_QWORD *)a5 + 1);
    v129 = *((_QWORD *)a5 + 2);
    Source.Buffer = (PWSTR)v129;
    if ( v129 )
      _InterlockedIncrement((volatile signed __int32 *)(v129 + 8));
    IsFileCowable = UnionFs::UfsPathCachePayload::ConvertToSoftTombstone(v56, &Source, v128, 10, a6);
    if ( IsFileCowable < 0 )
    {
      v130 = "PUSH: ConvertToSoftTombstone for COW";
      v131 = 0x38E00020AADLL;
LABEL_335:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)IsFileCowable,
        (int)a6,
        (struct UnionFs::StackEventTracer *)v131,
        (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
        v130,
        (const char *)TagData);
LABEL_336:
      wil::details::lambda_call__lambda_23c17448f3ca8015a5b979fa7520c7f3___::_lambda_call__lambda_23c17448f3ca8015a5b979fa7520c7f3___(&Context.FilterContext[1]);
      if ( v164[1] )
        utl::_RefCountBase::_DecStrong(v164[1]);
      goto LABEL_202;
    }
    v132 = v156[1];
    v133 = v156[0];
    if ( v156[1] )
      _InterlockedIncrement((volatile signed __int32 *)v156[1] + 2);
    v164[0] = v133;
    v134 = v164[1];
    v164[1] = v132;
    if ( v134 )
      utl::_RefCountBase::_DecStrong(v134);
    v135 = Resource;
    Resource = 0;
    if ( v135 )
    {
      ExReleaseResourceLite(v135);
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
                    (struct UnionFs::StackEventTracer *)a6,
                    v154);
  if ( IsFileCowable < 0 )
  {
    v130 = "PUSH: Preparing for COW";
    v131 = 0x29800020ABFLL;
    goto LABEL_335;
  }
  v136 = v156[0];
  *(_QWORD *)v178 = *((_QWORD *)a5 + 1);
  v137 = v156[1];
  v181 = 0;
  v182 = 22;
  v179 = 0;
  *(_OWORD *)v180 = 0;
  if ( v156[1] )
    _InterlockedIncrement((volatile signed __int32 *)v156[1] + 2);
  *((_QWORD *)&v179 + 1) = v136;
  v138 = v180[0];
  v180[0] = v137;
  if ( v138 )
    utl::_RefCountBase::_DecStrong(v138);
  UnionFs::UfsPathName::UfsPathName(
    (UnionFs::UfsPathName *)&v183,
    (const struct _UNICODE_STRING *)(*(_QWORD *)a5 + 8LL),
    *(_WORD *)(*(_QWORD *)a5 + 24LL));
  IsFileCowable = UnionFs::Utils::CopyItem(
                    (_DWORD)a2,
                    Context.Flags,
                    Context.TagData,
                    v9->IoStatus.Pointer,
                    &v183,
                    (__int64)v178,
                    (struct _FILE_OBJECT *)a6,
                    0);
  if ( IsFileCowable < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)IsFileCowable,
      (int)a6,
      (struct UnionFs::StackEventTracer *)0x28F00020AD0LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PreCreateFileOpen",
      "PUSH: Performing COW",
      v147);
    if ( !v184 )
      v183 = 0;
    FsFltWil::Details::FreeUnicodeString(&v183, v140);
    if ( v180[0] )
      utl::_RefCountBase::_DecStrong(v180[0]);
    goto LABEL_336;
  }
  LOBYTE(Context.FilterContext[2]) = 0;
  if ( !v184 )
    v183 = 0;
  FsFltWil::Details::FreeUnicodeString(&v183, v139);
  if ( v180[0] )
    utl::_RefCountBase::_DecStrong(v180[0]);
  wil::details::lambda_call__lambda_23c17448f3ca8015a5b979fa7520c7f3___::_lambda_call__lambda_23c17448f3ca8015a5b979fa7520c7f3___(&Context.FilterContext[1]);
  if ( v164[1] )
    utl::_RefCountBase::_DecStrong(v164[1]);
  utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.IoStatus);
  if ( v58 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v58);
  utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>::~unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>(&Context.Thread);
  v18 = 0;
LABEL_176:
  UnionFs::LookupEntryResults::~LookupEntryResults((UnionFs::LookupEntryResults *)&v155);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x140013b60  mov     [rsp-8+arg_0], rbx
0x140013b65  push    rbp
0x140013b66  push    rsi
0x140013b67  push    rdi
0x140013b68  push    r12
0x140013b6a  push    r13
0x140013b6c  push    r14
0x140013b6e  push    r15
0x140013b70  lea     rbp, [rsp-540h]
0x140013b78  sub     rsp, 650h
0x140013b7f  mov     rax, cs:__security_cookie
0x140013b86  xor     rax, rsp
0x140013b89  mov     [rbp+570h+var_40], rax
0x140013b90  mov     rax, [rbp+570h+arg_30]
0x140013b97  xor     edi, edi
0x140013b99  mov     r12, [rbp+570h+arg_20]
0x140013ba0  mov     rsi, r9
0x140013ba3  mov     r14, [rbp+570h+arg_28]
0x140013baa  mov     r15, r8
0x140013bad  mov     [r9], edi
0x140013bb0  mov     r13, rdx
0x140013bb3  mov     [rbp+570h+var_580], rax
0x140013bb7  mov     rax, [r8+20h]
0x140013bbb  mov     [rbp+570h+var_588], r9
0x140013bbf  mov     [rbp+570h+var_5B8], r8
0x140013bc3  mov     ebx, [rax+50h]
0x140013bc6  mov     rax, [rdx+10h]
0x140013bca  shr     ebx, 11h
0x140013bcd  not     ebx
0x140013bcf  and     ebx, 1
0x140013bd2  cmp     [rax+4], dil
0x140013bd6  jz      short loc_140013BE6
0x140013bd8  lea     rcx, aCheckingReques; "Checking requested access on non-create"
0x140013bdf  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140013be4  jmp     short loc_140013BFE
0x140013be6  mov     rax, [rax+18h]
0x140013bea  mov     ecx, [rax+10h]
0x140013bed  test    ecx, 10D0106h
0x140013bf3  jnz     short loc_140013BFB
0x140013bf5  bt      ecx, 19h
0x140013bf9  jnb     short loc_140013BFE
0x140013bfb  or      ebx, 8
0x140013bfe  xorps   xmm1, xmm1
0x140013c01  mov     [rbp+570h+Resource], rdi
0x140013c05  movd    eax, xmm1
0x140013c09  xorps   xmm0, xmm0
0x140013c0c  movdqa  [rbp+570h+var_570], xmm1
0x140013c11  movdqa  xmmword ptr [rbp+570h+var_560], xmm0
0x140013c16  or      eax, 3
0x140013c19  mov     [rbp+570h+var_548], rdi
0x140013c1d  mov     dword ptr [rbp+570h+var_570], eax
0x140013c20  mov     rax, [r12+8]
0x140013c25  movdqa  [rbp+570h+var_540], xmm0
0x140013c2a  cmp     dword ptr [rax+1Ch], 2
0x140013c2e  jnz     short loc_140013C3A
0x140013c30  mov     rax, [rax+20h]
0x140013c34  mov     rcx, [rax+10h]
0x140013c38  jmp     short loc_140013C45
0x140013c3a  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140013c41  mov     rcx, [rax+50h]
0x140013c45  mov     r8, [r12]
0x140013c49  lea     rax, [rbp+570h+var_570]
0x140013c4d  mov     rdx, [r15+18h]
0x140013c51  mov     r9d, ebx
0x140013c54  mov     qword ptr [rsp+680h+var_650], r13
0x140013c59  mov     [rsp+680h+var_658], r14; char *
0x140013c5e  mov     [rsp+680h+var_660], rax; struct UnionFs::StackEventTracer *
0x140013c63  call    ?LookupEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEAU_FLT_FILE_NAME_INFORMATION@@W4LookupEntryFlags@2@AEAULookupEntryResults@2@AEAVStackEventTracer@2@PEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::UfsPathCache::LookupEntry(_FLT_INSTANCE const &,_FLT_FILE_NAME_INFORMATION &,UnionFs::LookupEntryFlags,UnionFs::LookupEntryResults &,UnionFs::StackEventTracer &,_FLT_CALLBACK_DATA const *)
0x140013c68  mov     ebx, eax
0x140013c6a  test    eax, eax
0x140013c6c  jns     short loc_140013C84
0x140013c6e  lea     rax, aPushCacheLooku; "PUSH: Cache lookup"
0x140013c75  mov     r8, 21D000207DBh
0x140013c7f  jmp     loc_140013E46
0x140013c84  mov     ecx, dword ptr [rbp+570h+var_570+4]
0x140013c87  mov     edx, 4
0x140013c8c  mov     [rbp+570h+var_5F0], dil
0x140013c90  test    ecx, ecx
0x140013c92  jz      loc_140013D45
0x140013c98  test    byte ptr [rbp+570h+var_570+8], dl
0x140013c9b  jz      short loc_140013CC0
0x140013c9d  mov     eax, 0C0000034h
0x140013ca2  mov     [r13+20h], rdi
0x140013ca6  lea     r8d, [rdx-3]
0x140013caa  cmp     ecx, r8d
0x140013cad  lea     ebx, [rax+6]
0x140013cb0  cmovnz  eax, ebx
0x140013cb3  mov     [r13+18h], eax
0x140013cb7  mov     [rsi], edx
0x140013cb9  mov     ebx, edi
0x140013cbb  jmp     loc_14001485B
0x140013cc0  mov     ebx, 1
0x140013cc5  cmp     dword ptr [rbp+570h+var_548], ebx
0x140013cc8  jnz     short loc_140013CD7
0x140013cca  mov     rax, [r12+0A0h]
0x140013cd2  or      dword ptr [rax], 8
0x140013cd5  jmp     short loc_140013CB9
0x140013cd7  mov     rax, [rbp+570h+var_560]
0x140013cdb  movzx   ecx, word ptr [rax+0A8h]
0x140013ce2  nop
0x140013ce3  cmp     cx, dx
0x140013ce6  jnz     loc_140013DFF
0x140013cec  mov     rax, [rbp+570h+var_560]
0x140013cf0  cmp     [rax+0D8h], rdi
0x140013cf7  jnz     short loc_140013D05
0x140013cf9  lea     rcx, aResultsCacheen; "results.CacheEntry->GetOriginalScratchP"...
0x140013d00  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140013d05  cmp     dword ptr [rbp+570h+var_570+4], ebx
0x140013d08  jz      short loc_140013CB9
0x140013d0a  mov     rcx, [rbp+570h+Resource]; Resource
0x140013d0e  mov     [rbp+570h+Resource], rdi
0x140013d12  test    rcx, rcx
0x140013d15  jz      short loc_140013D2F
0x140013d17  call    cs:__imp_ExReleaseResourceLite
0x140013d1e  nop     dword ptr [rax+rax+00h]
0x140013d23  call    cs:__imp_KeLeaveCriticalRegion
0x140013d2a  nop     dword ptr [rax+rax+00h]
0x140013d2f  mov     rcx, [rbp+570h+var_560+8]; this
0x140013d33  mov     [rbp+570h+var_560+8], rdi
0x140013d37  mov     [rbp+570h+var_560], rdi
0x140013d3b  test    rcx, rcx
0x140013d3e  jz      short loc_140013D45
0x140013d40  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140013d45  cmp     dword ptr [rbp+570h+var_548], 2
0x140013d49  mov     [rbp+570h+P], rdi
0x140013d4d  jnz     loc_140014366
0x140013d53  mov     rax, qword ptr [rbp+570h+var_540+8]
0x140013d57  lea     r8, [rbp+570h+Source]; Source
0x140013d5b  mov     rcx, [r12]
0x140013d5f  lea     rdx, [rbp+570h+UnicodeString]; struct _UNICODE_STRING *
0x140013d63  add     rcx, 8; this
0x140013d67  mov     [rsp+680h+var_658], r14; char *
0x140013d6c  movzx   r9d, word ptr [rax+18h]
0x140013d71  movups  xmm0, xmmword ptr [rax]
0x140013d74  mov     rax, qword ptr [rbp+570h+var_540]
0x140013d78  movdqu  xmmword ptr [rbp+570h+Source.Length], xmm0
0x140013d7d  movups  xmm1, xmmword ptr [rax]
0x140013d80  lea     rax, [rbp+570h+P]
0x140013d84  mov     [rsp+680h+var_660], rax; P
0x140013d89  movdqu  xmmword ptr [rbp+570h+UnicodeString.Length], xmm1
0x140013d8e  call    ?AllocAndInitWithReplacedPathPrefix@UfsPathName@UnionFs@@SAJAEBU_UNICODE_STRING@@00GAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInitWithReplacedPathPrefix(_UNICODE_STRING const &,_UNICODE_STRING const &,_UNICODE_STRING const &,ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140013d93  xor     r9d, r9d
0x140013d96  mov     edi, eax
0x140013d98  test    eax, eax
0x140013d9a  jns     loc_14001435D
0x140013da0  lea     rax, aPushReplacingS_3; "PUSH: Replacing substring"
0x140013da7  mov     r8, 381000208DCh; struct UnionFs::StackEventTracer *
0x140013db1  lea     r9, aUnionfsUnionfs_32; "UnionFs::UnionFsFilter::PreCreateFileOp"...
0x140013db8  mov     [rsp+680h+var_660], rax; char *
0x140013dbd  mov     rdx, r14; int
0x140013dc0  mov     ecx, edi; this
0x140013dc2  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140013dc7  mov     rbx, [rbp+570h+P]
0x140013dcb  xor     eax, eax
0x140013dcd  test    rbx, rbx
0x140013dd0  jz      loc_140013CB9
0x140013dd6  cmp     [rbx+10h], al
0x140013dd9  jnz     short loc_140013DE1
0x140013ddb  xorps   xmm0, xmm0
0x140013dde  movups  xmmword ptr [rbx], xmm0
0x140013de1  mov     rcx, rbx; UnicodeString
0x140013de4  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140013de9  xor     edx, edx; Tag
0x140013deb  mov     rcx, rbx; P
0x140013dee  call    cs:__imp_ExFreePoolWithTag
0x140013df5  nop     dword ptr [rax+rax+00h]
0x140013dfa  jmp     loc_140013CB9
0x140013dff  cmp     dword ptr [rbp+570h+var_570+4], ebx
0x140013e02  jnz     loc_140013D0A
0x140013e08  mov     rdi, [rbp+570h+var_560]
0x140013e0c  mov     rdx, [rdi+60h]; Src
0x140013e10  test    rdx, rdx
0x140013e13  jz      short loc_140013E76
0x140013e15  mov     rax, [r13+10h]
0x140013e19  test    dword ptr [rax+20h], 200000h
0x140013e20  jnz     short loc_140013E76
0x140013e22  mov     r8, r14; struct _REPARSE_DATA_BUFFER *
0x140013e25  mov     rcx, r13; Data
0x140013e28  call    ?SetReparseDataFromCache@Utils@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_REPARSE_DATA_BUFFER@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::SetReparseDataFromCache(_FLT_CALLBACK_DATA &,_REPARSE_DATA_BUFFER const &,UnionFs::StackEventTracer &)
0x140013e2d  mov     ebx, eax
0x140013e2f  xor     eax, eax
0x140013e31  test    ebx, ebx
0x140013e33  jns     short loc_140013E61
0x140013e35  lea     rax, aPushCompleting; "PUSH: Completing create with cached rep"...
0x140013e3c  mov     r8, 7910002081Eh; struct UnionFs::StackEventTracer *
0x140013e46  lea     r9, aUnionfsUnionfs_32; "UnionFs::UnionFsFilter::PreCreateFileOp"...
0x140013e4d  mov     [rsp+680h+var_660], rax; char *
0x140013e52  mov     rdx, r14; int
0x140013e55  mov     ecx, ebx; this
0x140013e57  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140013e5c  jmp     loc_14001485B
0x140013e61  mov     dword ptr [r13+18h], 104h
0x140013e69  mov     ebx, eax
0x140013e6b  mov     dword ptr [rsi], 4
0x140013e71  jmp     loc_14001485B
0x140013e76  mov     rcx, [rdi+48h]; Context
0x140013e7a  call    cs:__imp_FltReferenceContext
0x140013e81  nop     dword ptr [rax+rax+00h]
0x140013e86  mov     rdi, [rdi+48h]
0x140013e8a  lea     rcx, [rbp+570h+P]
0x140013e8e  mov     [rbp+570h+Context], rdi
0x140013e92  mov     rbx, [rdi+20h]
0x140013e96  mov     [rbp+570h+var_5C0], rbx
0x140013e9a  mov     rdx, [rbx+78h]
0x140013e9e  add     rdx, 38h ; '8'
0x140013ea2  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x140013ea7  mov     rax, [r13+10h]
0x140013eab  cmp     byte ptr [rax+4], 0
0x140013eaf  jz      loc_140013F88
0x140013eb5  lea     rcx, aCheckingReques; "Checking requested access on non-create"
0x140013ebc  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140013ec1  mov     rcx, [rbp+570h+P]; Resource
0x140013ec5  test    rcx, rcx
0x140013ec8  jz      short loc_140013EE2
0x140013eca  call    cs:__imp_ExReleaseResourceLite
0x140013ed1  nop     dword ptr [rax+rax+00h]
0x140013ed6  call    cs:__imp_KeLeaveCriticalRegion
0x140013edd  nop     dword ptr [rax+rax+00h]
0x140013ee2  mov     rax, [r15+20h]
0x140013ee6  lea     rcx, [rbp+570h+var_5C0]
0x140013eea  mov     rbx, [r12+8]
0x140013eef  mov     [rbp+570h+Context], rax
0x140013ef3  mov     rax, [rbp+570h+var_560]
0x140013ef7  mov     [rbp+570h+var_580], rax
0x140013efb  lea     rdx, [rbx+48h]
0x140013eff  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140013f04  mov     rax, [rbx+30h]
0x140013f08  mov     rbx, [rax+8]
0x140013f0c  mov     rcx, [rax]
0x140013f0f  mov     [rbp+570h+P], rcx
0x140013f13  test    rbx, rbx
0x140013f16  jz      short loc_140013F1C
0x140013f18  lock inc dword ptr [rbx+8]
0x140013f1c  mov     rcx, [rbp+570h+var_5C0]; this
0x140013f20  test    rcx, rcx
0x140013f23  jz      short loc_140013F2A
0x140013f25  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140013f2a  mov     r9, [rbp+570h+P]
0x140013f2e  lea     rax, [r12+0A0h]
0x140013f36  mov     rcx, [rbp+570h+Context]; struct _FILE_OBJECT *
0x140013f3a  mov     r8, r15
0x140013f3d  mov     [rsp+680h+var_648], r14; struct UnionFs::Utils::CheckOplockHParams *
0x140013f42  mov     rdx, r13; struct _FLT_CALLBACK_DATA *
0x140013f45  mov     qword ptr [rsp+680h+var_650], rax; __int64
0x140013f4a  mov     rax, [rbp+570h+var_580]
0x140013f4e  mov     dword ptr [rsp+680h+var_658], 4; char *
0x140013f56  mov     [rsp+680h+var_660], rax; UnionFs::UfsPathCachePayload *
0x140013f5b  call    ?SetUp@UfsShadowFileObject@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEBVUfsLayerCtx@2@AEAVUfsPathCachePayload@2@W4ShareAccessCaller@2@AEAV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsShadowFileObject::SetUp(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsLayerCtx const &,UnionFs::UfsPathCachePayload &,UnionFs::ShareAccessCaller,wistd::unique_ptr<UnionFs::UfsStreamHandleCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x140013f60  mov     r15d, eax
0x140013f63  test    rbx, rbx
0x140013f66  jz      short loc_140013F70
0x140013f68  mov     rcx, rbx; this
0x140013f6b  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140013f70  cmp     r15d, 103h
0x140013f77  jnz     loc_140014294
0x140013f7d  mov     dword ptr [rsi], 2
0x140013f83  jmp     loc_140014342
0x140013f88  mov     rax, [rax+18h]
0x140013f8c  mov     ecx, [rax+10h]
0x140013f8f  test    ecx, 10D0106h
0x140013f95  jnz     short loc_140013FA1
0x140013f97  bt      ecx, 19h
0x140013f9b  jnb     loc_140013EC1
0x140013fa1  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x140013fa6  test    eax, eax
0x140013fa8  jz      loc_1400140EF
0x140013fae  mov     r9, r14; struct UnionFs::UfsFsContext *
0x140013fb1  mov     r8, rbx; struct _FLT_RELATED_OBJECTS *
0x140013fb4  mov     rdx, r15; struct _FLT_CALLBACK_DATA *
0x140013fb7  mov     rcx, r13; this
0x140013fba  call    ?BreakBatchAndHOplocks@Utils@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAVUfsFsContext@2@AEAVStackEventTracer@2@@Z; UnionFs::Utils::BreakBatchAndHOplocks(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,UnionFs::UfsFsContext &,UnionFs::StackEventTracer &)
0x140013fbf  mov     ebx, eax
0x140013fc1  cmp     eax, 103h
0x140013fc6  jnz     loc_140014086
0x140013fcc  mov     eax, cs:dword_14009E178
0x140013fd2  cmp     eax, 4
0x140013fd5  jbe     short loc_140014056
0x140013fd7  mov     rcx, cs:qword_14009E190
0x140013fde  mov     edx, 200200h
0x140013fe3  mov     rax, cs:qword_14009E188
0x140013fea  test    rdx, rax
0x140013fed  jz      short loc_140014056
0x140013fef  mov     rax, rcx
0x140013ff2  and     rax, rdx
0x140013ff5  cmp     rax, rcx
0x140013ff8  jnz     short loc_140014056
0x140013ffa  lea     rax, aOnecoreBaseFsU_14; "onecore\\base\\fs\\unionfs\\sys\\create"...
0x140014001  mov     [rbp+570h+var_5D8], 84Ah
0x140014008  mov     [rbp+570h+var_5C0], rax
0x14001400c  lea     rsi, aUnionfsUnionfs_32; "UnionFs::UnionFsFilter::PreCreateFileOp"...
0x140014013  lea     rax, aOplockBreak; "Oplock break"
0x14001401a  mov     [rbp+570h+var_580], rsi
0x14001401e  mov     [rbp+570h+var_5B8], rax
0x140014022  lea     rdx, word_140095EDA
0x140014029  lea     rax, [rbp+570h+var_5D8]
0x14001402d  mov     [rsp+680h+var_648], rax
0x140014032  lea     rax, [rbp+570h+var_5C0]
0x140014036  mov     qword ptr [rsp+680h+var_650], rax
0x14001403b  lea     rax, [rbp+570h+var_580]
0x14001403f  mov     [rsp+680h+var_658], rax
  ... truncated ...
```
