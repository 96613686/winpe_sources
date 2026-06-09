# UnionFs::UfsPathTable::LookupPriv(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::LookupFlags,UnionFs::LookupResults &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,wistd::function<long (UnionFs::UfsInstanceTierNode const &,UnionFs::UfsPathTierNode const &,bool *,utl::pair<wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &,wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &> &,UnionFs::StackEventTracer &)> *)

- ea: `0x14004c74c`
- end: `0x14004dd39`
- name: `?LookupPriv@UfsPathTable@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4LookupFlags@2@AEAULookupResults@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEAV?$function@$$A6AJAEBVUfsInstanceTierNode@UnionFs@@AEBVUfsPathTierNode@2@PEA_NAEAU?$pair@AEAV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAV12@@utl@@AEAVStackEventTracer@2@@Z@wistd@@@Z`
- size: `5613`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, struct UnionFs::StackEventTracer *, int, __int64)`
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004c58c`
- `0x14004dd40`

## callees

- `0x1400069b4`
- `0x14000f7fc`
- `0x14003daf4`
- `0x14004408c`
- `0x1400441b4`
- `0x140044374`
- `0x140044bac`
- `0x140044e10`
- `0x140047ddc`
- `0x14004c4f8`
- `0x14004c74c`
- `0x14004f4ac`
- `0x14004f5d4`
- `0x140056afc`
- `0x1400790f0`
- `0x140079a24`
- `0x140079ab4`
- `0x140079afc`
- `0x140079da0`
- `0x140079df4`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14004caab`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004d37b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004d409`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004d9a1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004caab`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004d37b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004d409`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004d9a1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c7f2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c8f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c9f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cb50`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cd36`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cd5e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cf76`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cf9e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d082`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d184`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d1e0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d239`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d326`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d34b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d4a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d574`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d64d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d672`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d6e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d7e0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d82b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d88a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d8b6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d905`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004da8a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004daf4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004dc6a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004dce8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c7f2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c8f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c9f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cb50`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cd36`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cd5e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cf76`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cf9e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d082`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d184`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d1e0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d239`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d326`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d34b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d4a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d574`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d64d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d672`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d6e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d7e0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d82b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d88a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d8b6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d905`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004da8a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004daf4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004dc6a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004dce8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c7fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c902`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004ca02`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cb5c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cd42`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cd6a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cf82`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cfaa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d08e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d190`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d1ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d245`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d332`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d357`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d4ac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d580`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d659`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d67e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d6f5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d7ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d837`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d896`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d8c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d911`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004da96`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004db00`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004dc76`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004dcf4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c7fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c902`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004ca02`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cb5c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cd42`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cd6a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cf82`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cfaa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d08e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d190`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d1ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d245`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d332`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d357`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d4ac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d580`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d659`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d67e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d6f5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d7ec`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d837`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d896`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d8c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d911`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004da96`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004db00`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004dc76`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004dcf4`

## string_xrefs

- `0x14004dc16`: `!moreComponentsLeft`
- `0x14004c89c`: `PUSH: Allocating FoundPath`
- `0x14004c8ad`: `UnionFs::UfsPathTable::LookupPriv`
- `0x14004d45b`: `UnionFs::UfsPathTable::LookupPriv`
- `0x14004d791`: `UnionFs::UfsPathTable::LookupPriv`
- `0x14004d857`: `UnionFs::UfsPathTable::LookupPriv`
- `0x14004da10`: `UnionFs::UfsPathTable::LookupPriv`
- `0x14004c974`: `PUSH: Appending volume path to FoundPath`
- `0x14004d3c4`: `If nested paths not enabled, tree should be empty.`
- `0x14004d419`: `RtlEqualUnicodeString(volumeRootNode->GetPathComponent(), &g_RootName, false)`
- `0x14004d445`: `PUSH: Appending volume root to FoundPath`
- `0x14004d9fa`: `PUSH: Appending volume root to FoundPath`
- `0x14004d68f`: `PUSH: LookupCallback in PathTable.`
- `0x14004d850`: `PUSH: LookupCallback in PathTable.`
- `0x14004d78a`: `PUSH: Appending path component to FoundPath`
- `0x14004d9b1`: `RtlEqualUnicodeString(foundPayloadNode->GetPathComponent(), &g_RootName, false)`
- `0x14004d9cd`: `SearchPath.AsUnicodeString().Length > sizeof(WCHAR)`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathTable::LookupPriv(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int *a5,
        struct _UNICODE_STRING *a6,
        char a7,
        struct _ERESOURCE *a8)
{
  bool v8; // zf
  int v9; // esi
  _DWORD *v12; // r14
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v13; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *Length; // rdx
  _QWORD *i; // rax
  UnionFs::UfsInstanceTierNode *v16; // r12
  int v17; // eax
  const UNICODE_STRING **v18; // rsi
  int appended; // ebx
  const char *v20; // rax
  __int64 v21; // r8
  struct FsFltWil::Details::RundownRefCacheAware *v22; // rdx
  struct _ERESOURCE *v23; // rcx
  const UNICODE_STRING *v25; // r8
  PWSTR Buffer; // rcx
  __int64 v27; // rdx
  __int16 v28; // ax
  const UNICODE_STRING *v29; // rcx
  const UNICODE_STRING *v30; // rax
  char v31; // r15
  struct _ERESOURCE *v32; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v33; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v34; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v35; // rdx
  __int64 v36; // rsi
  __int64 v37; // r13
  __int64 v38; // rcx
  utl::_RefCountBase *v39; // r12
  struct _ERESOURCE *v40; // rbx
  int v41; // ecx
  volatile signed __int32 *v42; // r14
  __int64 v43; // rax
  char v44; // r15
  struct _ERESOURCE **v45; // rax
  struct _ERESOURCE *v46; // rcx
  unsigned __int64 *v47; // rdx
  unsigned __int16 v48; // r9
  volatile signed __int32 *v49; // r14
  FsFltWil::Details *v50; // rcx
  UnionFs::UfsPathTree *v51; // r13
  volatile signed __int32 *v52; // rsi
  struct _UNICODE_STRING *v53; // r8
  bool v54; // al
  const UNICODE_STRING *Node; // rax
  volatile signed __int32 *v56; // rdx
  UNICODE_STRING *v57; // r13
  int v58; // r15d
  __int64 v59; // rcx
  char v60; // al
  int v61; // ecx
  volatile signed __int32 *v62; // rdx
  __int64 v63; // rax
  char v64; // r15
  volatile signed __int32 *v65; // r15
  volatile signed __int32 **v66; // rax
  struct _ERESOURCE *v67; // rcx
  struct _ERESOURCE *v68; // rcx
  struct _LIST_ENTRY *v69; // rcx
  int v70; // eax
  volatile signed __int32 *v71; // rcx
  char v72; // al
  int v73; // r15d
  __int64 v74; // rax
  volatile signed __int32 *v75; // rax
  int v76; // r15d
  __int64 (__fastcall ***v77)(_QWORD, _QWORD); // rcx
  int v78; // eax
  volatile signed __int32 *v79; // rax
  __int64 v80; // rcx
  char v81; // al
  char v82; // r15
  unsigned int v83; // eax
  PWSTR v84; // r15
  volatile signed __int32 **v85; // rax
  struct _ERESOURCE *v86; // rcx
  struct _ERESOURCE *v87; // rcx
  __int64 v88; // rcx
  char v89; // al
  int v90; // ecx
  __int64 v91; // rax
  char v92; // r15
  struct _ERESOURCE *v93; // rcx
  utl::_RefCountBase *v94; // rcx
  __int64 v95; // r15
  volatile signed __int32 *v96; // rax
  utl::_RefCountBase *v97; // rcx
  struct _ERESOURCE *v98; // rax
  volatile signed __int32 *v99; // r15
  FsFltWil::Details *v100; // rcx
  utl::_RefCountBase *v101; // rcx
  struct _ERESOURCE *v102; // rcx
  struct _ERESOURCE *v103; // rcx
  struct _ERESOURCE *v104; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v105; // rdx
  struct _ERESOURCE *v106; // rcx
  __int64 v107; // rax
  __int64 v108; // rcx
  _QWORD *v109; // rbx
  utl::_RefCountBase *v110; // rcx
  __int64 *v111; // rax
  struct _ERESOURCE **v112; // r15
  __int64 v113; // rdx
  struct _ERESOURCE *v114; // rcx
  struct _ERESOURCE *v115; // rcx
  char v116; // r12
  volatile signed __int32 *v117; // r14
  UnionFs::UfsPathTree *v118; // rcx
  struct _UNICODE_STRING *v119; // r13
  int v120; // r14d
  struct FsFltWil::Details::RundownRefCacheAware *v121; // rdx
  struct _ERESOURCE *v122; // rcx
  struct _LIST_ENTRY *Blink; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v124; // rdx
  _DWORD *v125; // r14
  struct _ERESOURCE *v126; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v127; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v128; // rdx
  int v129; // ecx
  struct _ERESOURCE **v130; // rax
  struct _ERESOURCE *v131; // rdx
  struct _ERESOURCE *v132; // rcx
  struct _ERESOURCE *v133; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v134; // rdx
  int v135; // eax
  int v136; // eax
  struct FsFltWil::Details::RundownRefCacheAware *v137; // rdx
  struct _ERESOURCE *v138; // rcx
  struct _ERESOURCE *v139; // rcx
  struct _ERESOURCE *v140; // rcx
  UNICODE_STRING *v141; // r15
  PWSTR v142; // rax
  __int64 v143; // rcx
  utl::_RefCountBase *v144; // rcx
  struct _ERESOURCE *v145; // rcx
  unsigned __int64 *v146; // rdx
  const UNICODE_STRING *v147; // r13
  struct _ERESOURCE *v148; // r15
  volatile signed __int32 *v149; // rbx
  int v150; // r15d
  int v151; // eax
  struct FsFltWil::Details::RundownRefCacheAware *v152; // rdx
  struct _ERESOURCE *v153; // rcx
  int v154; // eax
  __int64 v155; // rcx
  int v156; // eax
  struct FsFltWil::Details::RundownRefCacheAware *v157; // rdx
  char *v158; // [rsp+28h] [rbp-D8h]
  unsigned int v159; // [rsp+40h] [rbp-C0h]
  PERESOURCE Resource; // [rsp+48h] [rbp-B8h] BYREF
  bool v161; // [rsp+50h] [rbp-B0h]
  char v162; // [rsp+51h] [rbp-AFh] BYREF
  int v163; // [rsp+54h] [rbp-ACh]
  int v164; // [rsp+58h] [rbp-A8h] BYREF
  PERESOURCE v165; // [rsp+60h] [rbp-A0h] BYREF
  UNICODE_STRING *v166; // [rsp+68h] [rbp-98h]
  unsigned __int16 v167[4]; // [rsp+70h] [rbp-90h]
  struct _UNICODE_STRING *v168; // [rsp+78h] [rbp-88h]
  UNICODE_STRING String1; // [rsp+80h] [rbp-80h] BYREF
  UnionFs::UfsInstanceTierNode *v170; // [rsp+90h] [rbp-70h]
  PERESOURCE v171; // [rsp+98h] [rbp-68h] BYREF
  PERESOURCE v172; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD *v173; // [rsp+A8h] [rbp-58h]
  struct _ERESOURCE *v174; // [rsp+B0h] [rbp-50h] BYREF
  UNICODE_STRING Source; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v176; // [rsp+C8h] [rbp-38h]
  PERESOURCE v177; // [rsp+D0h] [rbp-30h] BYREF
  volatile signed __int32 *v178; // [rsp+D8h] [rbp-28h]
  struct _ERESOURCE *v179; // [rsp+E0h] [rbp-20h]
  struct _ERESOURCE *v180; // [rsp+E8h] [rbp-18h] BYREF
  PERESOURCE v181; // [rsp+F0h] [rbp-10h] BYREF
  FsFltWil::Details *v182; // [rsp+F8h] [rbp-8h] BYREF
  volatile signed __int32 *v183; // [rsp+100h] [rbp+0h]
  PERESOURCE v184; // [rsp+108h] [rbp+8h] BYREF
  utl::_RefCountBase *v185; // [rsp+110h] [rbp+10h]
  utl::_RefCountBase *v186; // [rsp+118h] [rbp+18h]
  char *v187; // [rsp+120h] [rbp+20h] BYREF
  struct _UNICODE_STRING v188; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v189[2]; // [rsp+138h] [rbp+38h] BYREF
  utl::_RefCountBase *v190; // [rsp+148h] [rbp+48h]
  _QWORD v191[2]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD v192[2]; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v193[2]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v194; // [rsp+1F0h] [rbp+F0h]
  _QWORD v195[17]; // [rsp+1F8h] [rbp+F8h] BYREF
  _BYTE v196[128]; // [rsp+280h] [rbp+180h] BYREF
  __int64 v197; // [rsp+300h] [rbp+200h]
  int v198; // [rsp+380h] [rbp+280h]

  v8 = (a7 & 1) == 0;
  v9 = a7 & 1;
  v163 = a4;
  v12 = a1;
  a5[1] = 0;
  v176 = a3;
  v173 = a1;
  v168 = a6;
  v172 = a8;
  v159 = 0;
  Resource = 0;
  v198 = v9;
  if ( v8 )
  {
    FsFltWil::AcquireResourceShared(&v174, a1 + 8);
    Resource = v174;
  }
  v13 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)v12 + 17);
  v194 = 0;
  FsFltWil::AcquireRundownReference(v195, v13);
  if ( !v195[0] )
    goto LABEL_4;
  for ( i = (_QWORD *)*((_QWORD *)v12 + 1); ; i = (_QWORD *)*i )
  {
    if ( i == (_QWORD *)(v12 + 2) )
    {
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v195, Length);
      goto LABEL_335;
    }
    v16 = (UnionFs::UfsInstanceTierNode *)(i + 2);
    Length = (struct FsFltWil::Details::RundownRefCacheAware *)i[3];
    v170 = (UnionFs::UfsInstanceTierNode *)(i + 2);
    if ( *(_QWORD *)Length == a2 )
      break;
  }
  v17 = *a5;
  *(_DWORD *)v167 = 0;
  if ( (v17 & 1) != 0 )
  {
    v18 = (const UNICODE_STRING **)(a5 + 14);
    appended = UnionFs::UfsPathName::AllocEmpty(*(unsigned __int16 *)(a3 + 2), a5 + 14, a6);
    if ( appended < 0 )
    {
      v20 = "PUSH: Allocating FoundPath";
      v21 = 0x1AB001408E9LL;
LABEL_12:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)appended,
        (int)a6,
        (struct UnionFs::StackEventTracer *)v21,
        (unsigned __int64)"UnionFs::UfsPathTable::LookupPriv",
        v20,
        v158);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v195, v22);
      if ( v195[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v195[16] + 24LL))(v195[16]);
      v23 = Resource;
      Resource = 0;
      goto LABEL_15;
    }
    v25 = *v18;
    Buffer = (*v18)->Buffer;
    v27 = *(unsigned __int16 *)(*((_QWORD *)v16 + 1) + 120LL);
    WORD1(v25[1].Buffer) = v27;
    LOWORD(v25[1].Buffer) = v27;
    *(_QWORD *)&v25[2].Length = Buffer;
    LOWORD(v25[3].Buffer) = 0;
    *(_QWORD *)&v25[3].Length = (char *)Buffer + v27;
    v28 = v25->Length - v27;
    WORD1(v25[2].Buffer) = v28;
    LOWORD(v25[2].Buffer) = v28;
    v29 = *v18;
    Source = *(UNICODE_STRING *)(*((_QWORD *)v16 + 1) + 120LL);
    appended = UnionFs::UfsPathName::AppendUnicodeString(v29, &Source, (struct UnionFs::StackEventTracer *)a6);
    if ( appended < 0 )
    {
      v20 = "PUSH: Appending volume path to FoundPath";
      v21 = 0x1B1001408F3LL;
      goto LABEL_12;
    }
    v30 = *v18;
    v9 = v198;
    Length = (struct FsFltWil::Details::RundownRefCacheAware *)v30->Length;
    *(_DWORD *)v167 = v30->Length;
  }
  v31 = 0;
LABEL_22:
  if ( v31 )
  {
    if ( !v9 )
    {
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v195, Length);
      memset(v195, 0, sizeof(v195));
      FsFltWil::AcquireResourceShared(&v180, v12 + 8);
      v32 = Resource;
      Resource = v180;
      if ( v32 )
      {
        ExReleaseResourceLite(v32);
        KeLeaveCriticalRegion();
      }
      v33 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)v12 + 17);
      v180 = 0;
      v194 = 0;
      FsFltWil::AcquireRundownReference(v196, v33);
      wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&void FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>::operator=(
        (FsFltWil::Details *)v195,
        v196);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v196, v34);
      if ( v197 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v197 + 24LL))(v197);
      if ( !v195[0] )
      {
        a5[1] = 0;
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v195, v35);
        if ( v195[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v195[16] + 24LL))(v195[16]);
        v104 = Resource;
        Resource = 0;
LABEL_338:
        if ( v104 )
        {
          ExReleaseResourceLite(v104);
          KeLeaveCriticalRegion();
        }
        return 0;
      }
      goto LABEL_29;
    }
    MicrosoftTelemetryAssertTriggeredMsgKM("STATUS_RETRY with TableLockAcquired in Lookup");
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v195, v105);
    if ( v195[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v195[16] + 24LL))(v195[16]);
    v106 = Resource;
    Resource = 0;
LABEL_221:
    if ( v106 )
    {
      ExReleaseResourceLite(v106);
      KeLeaveCriticalRegion();
    }
    return 3221225701LL;
  }
LABEL_29:
  v36 = *(_QWORD *)v16;
  v164 = 0;
  if ( UnionFs::UfsInstanceTierNode::HasVolumeRootMapping(v16) )
  {
    v37 = v176;
    String1 = *(UNICODE_STRING *)(v176 + 40);
    if ( RtlEqualUnicodeString(&String1, &UnionFs::g_RootName, 0) || (*v12 & 2) == 0 )
    {
      v107 = *(_QWORD *)(v36 + 72);
      v108 = *(_QWORD *)(v36 + 64);
      if ( v107 )
        _InterlockedIncrement((volatile signed __int32 *)(v107 + 8));
      v109 = a5 + 4;
      *((_QWORD *)a5 + 2) = v108;
      v110 = (utl::_RefCountBase *)*((_QWORD *)a5 + 3);
      *((_QWORD *)a5 + 3) = v107;
      if ( v110 )
        utl::_RefCountBase::_DecStrong(v110);
      v111 = (__int64 *)UnionFs::UfsPathTable::LockPayloadPerCallerIntent(
                          (_DWORD)v110,
                          (unsigned int)&v171,
                          v163,
                          (int)a5 + 16,
                          (__int64)&v164);
      v112 = (struct _ERESOURCE **)(a5 + 8);
      v113 = *v111;
      *v111 = 0;
      v114 = (struct _ERESOURCE *)*((_QWORD *)a5 + 4);
      *((_QWORD *)a5 + 4) = v113;
      if ( v114 )
      {
        ExReleaseResourceLite(v114);
        KeLeaveCriticalRegion();
      }
      v115 = v171;
      v171 = 0;
      if ( v115 )
      {
        ExReleaseResourceLite(v115);
        KeLeaveCriticalRegion();
      }
      Source = *(UNICODE_STRING *)(v37 + 40);
      v116 = v159;
      a5[1] = 2 - (RtlEqualUnicodeString(&Source, &UnionFs::g_RootName, 0) != 0);
      a5[2] |= 8u;
      if ( (*v12 & 2) != 0 )
      {
        v117 = *(volatile signed __int32 **)&String1.Length;
      }
      else
      {
        v117 = *(volatile signed __int32 **)(v36 + 56);
        v116 = v159 | 1;
        v118 = *(UnionFs::UfsPathTree **)(v36 + 48);
        if ( v117 )
          _InterlockedIncrement(v117 + 2);
        if ( !UnionFs::UfsPathTree::IsEmpty(v118) )
          MicrosoftTelemetryAssertTriggeredMsgKM("If nested paths not enabled, tree should be empty.");
      }
      if ( (v116 & 1) != 0 && v117 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v117);
      if ( (*a5 & 1) != 0 )
      {
        if ( !RtlEqualUnicodeString((PCUNICODE_STRING)(v36 + 32), &UnionFs::g_RootName, 0) )
          MicrosoftTelemetryAssertTriggeredMsgKM("RtlEqualUnicodeString(volumeRootNode->GetPathComponent(), &g_RootName, false)");
        v119 = v168;
        v120 = UnionFs::UfsPathName::AppendPath(*((UnionFs::UfsPathName **)a5 + 7), (PCUNICODE_STRING)(v36 + 32), v168);
        if ( v120 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v120,
            (int)v119,
            (struct UnionFs::StackEventTracer *)0x1AD00140967LL,
            (unsigned __int64)"UnionFs::UfsPathTable::LookupPriv",
            "PUSH: Appending volume root to FoundPath",
            v158);
LABEL_193:
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v195, v121);
          if ( v195[16] )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v195[16] + 24LL))(v195[16]);
          v122 = Resource;
          Resource = 0;
          if ( v122 )
          {
            ExReleaseResourceLite(v122);
            KeLeaveCriticalRegion();
          }
          return (unsigned int)v120;
        }
      }
      else
      {
        v119 = v168;
      }
      if ( v172 )
      {
        *(_QWORD *)&Source.Length = a5 + 8;
        Source.Buffer = (PWSTR)&Resource;
        Blink = v172[1].SystemResourcesList.Blink;
        *(_QWORD *)&String1.Length = 0;
        if ( !Blink )
          wistd::__throw_bad_function_call(0);
        v120 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, UnionFs::UfsInstanceTierNode *, __int64, UNICODE_STRING *, UNICODE_STRING *))Blink->Flink[2].Flink)(
                 Blink,
                 v170,
                 v36,
                 &String1,
                 &Source);
        if ( v120 == -1073741267 )
        {
          if ( v198 )
          {
            MicrosoftTelemetryAssertTriggeredMsgKM("STATUS_RETRY with TableLockAcquired in Lookup");
            FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v195, v134);
            if ( v195[16] )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v195[16] + 24LL))(v195[16]);
            v106 = Resource;
            Resource = 0;
            goto LABEL_221;
          }
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v195, v124);
          memset(v195, 0, sizeof(v195));
          v125 = v173;
          FsFltWil::AcquireResourceShared(&String1, v173 + 8);
          v126 = Resource;
          Resource = *(PERESOURCE *)&String1.Length;
          if ( v126 )
          {
            ExReleaseResourceLite(v126);
            KeLeaveCriticalRegion();
          }
          v127 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)v125 + 17);
          v194 = 0;
          FsFltWil::AcquireRundownReference(v196, v127);
          wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&void FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>::operator=(
            (FsFltWil::Details *)v195,
            v196);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v196, v128);
          if ( v197 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v197 + 24LL))(v197);
          if ( !v195[0] )
          {
            a5[1] = 0;
LABEL_4:
            FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v195, Length);
LABEL_335:
            if ( v195[16] )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v195[16] + 24LL))(v195[16]);
            v104 = Resource;
            Resource = 0;
            goto LABEL_338;
          }
          v120 = 0;
        }
        if ( (**(unsigned int (__fastcall ***)(_QWORD))*v109)(*v109)
          && !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v109 + 40LL))(*v109) )
        {
          v130 = (struct _ERESOURCE **)UnionFs::UfsPathTable::LockPayloadPerCallerIntent(
                                         v129,
                                         (unsigned int)&v172,
                                         v163,
                                         (int)a5 + 16,
                                         (__int64)&v164);
          v131 = *v130;
          *v130 = 0;
          v132 = *v112;
          *v112 = v131;
          if ( v132 )
          {
            ExReleaseResourceLite(v132);
            KeLeaveCriticalRegion();
          }
          v133 = v172;
          v172 = 0;
          if ( v133 )
          {
            ExReleaseResourceLite(v133);
            KeLeaveCriticalRegion();
          }
        }
        if ( v120 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v120,
            (int)v119,
            (struct UnionFs::StackEventTracer *)0x37D001409A3LL,
            (unsigned __int64)"UnionFs::UfsPathTable::LookupPriv",
            "PUSH: LookupCallback in PathTable.",
            (const char *)v119);
          goto LABEL_193;
        }
      }
      if ( (*a5 & 2) != 0 && a5[1] == 1 )
      {
        *((_QWORD *)a5 + 5) = v36;
        a5[12] = 1;
      }
      if ( (**(unsigned int (__fastcall ***)(_QWORD))*v109)(*v109) )
      {
        v135 = a5[2];
        if ( (v164 & 4) != 0 )
        {
          a5[2] = v135 | 4;
          a5[2] |= ((*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v109 + 32LL))(*v109) != 0) + 1;
        }
        else
        {
          if ( (v164 & 1) != 0 )
            v136 = v135 | 1;
          else
            v136 = v135 | 2;
          a5[2] = v136;
        }
      }
      goto LABEL_4;
    }
  }
  v38 = *(_QWORD *)(v36 + 64);
  v39 = 0;
  v174 = 0;
  v166 = 0;
  v40 = 0;
  if ( v38 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v38 + 48LL))(v38) )
  {
    v42 = *(volatile signed __int32 **)(v36 + 72);
    v43 = *(_QWORD *)(v36 + 64);
    v166 = (UNICODE_STRING *)v36;
    v191[0] = v43;
    v191[1] = v42;
    if ( v42 )
      _InterlockedIncrement(v42 + 2);
    v44 = v163;
    v45 = (struct _ERESOURCE **)UnionFs::UfsPathTable::LockPayloadPerCallerIntent(
                                  v41,
                                  (unsigned int)&v181,
                                  v163,
                                  (unsigned int)v191,
                                  (__int64)&v164);
    v40 = *v45;
    *v45 = 0;
    v46 = v181;
    v181 = 0;
    if ( v46 )
    {
      ExReleaseResourceLite(v46);
      KeLeaveCriticalRegion();
    }
    if ( v42 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v42);
    a5[1] = 2;
  }
  else
  {
    v44 = v163;
  }
  FsFltWil::AcquirePushLockShared(&v182, v36 + 128);
  v49 = *(volatile signed __int32 **)(v36 + 88);
  v179 = *(struct _ERESOURCE **)(v36 + 80);
  if ( v49 )
    _InterlockedIncrement(v49 + 2);
  v50 = v182;
  v182 = 0;
  if ( v50 )
    FsFltWil::Details::ReleasePushLockShared(v50, v47);
  v51 = *(UnionFs::UfsPathTree **)(v36 + 48);
  v52 = *(volatile signed __int32 **)(v36 + 56);
  if ( v52 )
    _InterlockedIncrement(v52 + 2);
  v188 = 0;
  while ( 1 )
  {
    v53 = (struct _UNICODE_STRING *)*(unsigned __int16 *)(v176 + 24);
    String1 = *(UNICODE_STRING *)v176;
    v54 = UnionFs::Utils::WalkPath((UnionFs::Utils *)&String1, &v188, v53, v48);
    v161 = v54;
    if ( !v188.Length )
    {
      if ( v54 )
        MicrosoftTelemetryAssertTriggeredMsgKM("!moreComponentsLeft");
      if ( UnionFs::UfsInstanceTierNode::HasVolumeRootMapping(v170) )
        MicrosoftTelemetryAssertTriggeredMsgKM("!instanceTierNode->HasVolumeRootMapping()");
      if ( v52 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v52);
      if ( v39 )
        utl::_RefCountBase::_DecStrong(v39);
      if ( v49 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v49);
      if ( v40 )
      {
        ExReleaseResourceLite(v40);
        KeLeaveCriticalRegion();
      }
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v195, v157);
      if ( v195[16] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v195[16] + 24LL))(v195[16]);
      v104 = Resource;
      Resource = 0;
      goto LABEL_338;
    }
    v189[1] = v44 & 1;
    v189[0] = &v188;
    Node = (const UNICODE_STRING *)UnionFs::UfsPathTree::FindNode(v51, (const struct UnionFs::UFS_COMPARE_KEY *)v189);
    *(_QWORD *)&String1.Length = Node;
    v57 = (UNICODE_STRING *)Node;
    if ( !Node )
      break;
    if ( (*a5 & 1) != 0 )
    {
      v58 = UnionFs::UfsPathName::AppendPath(*((UnionFs::UfsPathName **)a5 + 7), Node + 2, v168);
      if ( v58 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v58,
          (int)v168,
          (struct UnionFs::StackEventTracer *)0x1AF00140A12LL,
          (unsigned __int64)"UnionFs::UfsPathTable::LookupPriv",
          "PUSH: Appending path component to FoundPath",
          v158);
LABEL_235:
        if ( v52 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v52);
        if ( v39 )
          utl::_RefCountBase::_DecStrong(v39);
        if ( v49 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v49);
        if ( v40 )
        {
          ExReleaseResourceLite(v40);
          KeLeaveCriticalRegion();
        }
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v195, v137);
        if ( v195[16] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v195[16] + 24LL))(v195[16]);
        v138 = Resource;
        Resource = 0;
        if ( v138 )
        {
          ExReleaseResourceLite(v138);
          KeLeaveCriticalRegion();
        }
        return (unsigned int)v58;
      }
      v44 = v163;
    }
    v165 = 0;
    v59 = *(_QWORD *)&v57[4].Length;
    if ( !v59 )
    {
      v61 = v159;
LABEL_62:
      v62 = v183;
LABEL_63:
      v64 = 0;
      goto LABEL_64;
    }
    v60 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 *, _QWORD))(*(_QWORD *)v59 + 48LL))(v59, v56, 0);
    v61 = v159;
    if ( !v60 )
      goto LABEL_62;
    v62 = (volatile signed __int32 *)v57[4].Buffer;
    v61 = v159 | 2;
    v63 = *(_QWORD *)&v57[4].Length;
    v159 |= 2u;
    v183 = v62;
    if ( v62 )
      _InterlockedIncrement(v62 + 2);
    if ( !*(_BYTE *)(v63 + 8) && (v44 & 2) == 0 )
      goto LABEL_63;
    v64 = 1;
LABEL_64:
    if ( (v61 & 2) != 0 )
    {
      v61 &= ~2u;
      v159 = v61;
      if ( v62 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v62);
    }
    if ( v64 )
    {
      v65 = (volatile signed __int32 *)v57[4].Buffer;
      v192[0] = *(_QWORD *)&v57[4].Length;
      v192[1] = v65;
      if ( v65 )
        _InterlockedIncrement(v65 + 2);
      v66 = (volatile signed __int32 **)UnionFs::UfsPathTable::LockPayloadPerCallerIntent(
                                          v61,
                                          (unsigned int)&v184,
                                          v163,
                                          (unsigned int)v192,
                                          (__int64)&v164);
      v62 = *v66;
      *v66 = 0;
      v67 = v165;
      v165 = (PERESOURCE)v62;
      if ( v67 )
      {
        ExReleaseResourceLite(v67);
        KeLeaveCriticalRegion();
      }
      v68 = v184;
      v184 = 0;
      if ( v68 )
      {
        ExReleaseResourceLite(v68);
        KeLeaveCriticalRegion();
      }
      if ( v65 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v65);
    }
    v162 = 0;
    if ( v172 )
    {
      v193[0] = &v165;
      v193[1] = &Resource;
      v187 = &v162;
      v69 = v172[1].SystemResourcesList.Blink;
      if ( !v69 )
        wistd::__throw_bad_function_call(0);
      v158 = (char *)v168;
      v70 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, UnionFs::UfsInstanceTierNode *, UNICODE_STRING *, char **, _QWORD *))v69->Flink[2].Flink)(
              v69,
              v170,
              v57,
              &v187,
              v193);
      v58 = v70;
      if ( v70 == -1073741267 )
      {
        if ( (*a5 & 1) != 0 )
          UnionFs::UfsPathName::PathLength(*((UnionFs::UfsPathName **)a5 + 7), *(_WORD *)(*((_QWORD *)a5 + 7) + 24LL));
        v103 = v165;
        a5[1] = 0;
        v31 = 1;
        v165 = 0;
        if ( v103 )
        {
          ExReleaseResourceLite(v103);
          KeLeaveCriticalRegion();
        }
        if ( v52 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v52);
        if ( v39 )
          utl::_RefCountBase::_DecStrong(v39);
        if ( v49 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v49);
        v12 = v173;
        v16 = v170;
        v9 = v198;
        if ( v40 )
        {
          ExReleaseResourceLite(v40);
          KeLeaveCriticalRegion();
        }
        goto LABEL_22;
      }
      v62 = 0;
      if ( v70 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v70,
          (int)v168,
          (struct UnionFs::StackEventTracer *)0x32000140A3BLL,
          (unsigned __int64)"UnionFs::UfsPathTable::LookupPriv",
          "PUSH: LookupCallback in PathTable.",
          v158);
        v139 = v165;
        v165 = 0;
        if ( v139 )
        {
          ExReleaseResourceLite(v139);
          KeLeaveCriticalRegion();
        }
        goto LABEL_235;
      }
      v71 = *(volatile signed __int32 **)&v57[4].Length;
      if ( !v71 )
        goto LABEL_92;
      v72 = (*(__int64 (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)v71 + 48LL))(v71, 0);
      v62 = 0;
      if ( !v72 )
        goto LABEL_92;
      v71 = (volatile signed __int32 *)v57[4].Buffer;
      v73 = v159 | 4;
      v74 = *(_QWORD *)&v57[4].Length;
      v159 |= 4u;
      v186 = (utl::_RefCountBase *)v71;
      if ( v71 )
        _InterlockedIncrement(v71 + 2);
      if ( !*(_BYTE *)(v74 + 8) && (v163 & 2) == 0 )
        goto LABEL_92;
      v75 = (volatile signed __int32 *)v57[4].Buffer;
      v76 = v73 | 8;
      v77 = *(__int64 (__fastcall ****)(_QWORD, _QWORD))&v57[4].Length;
      v159 = v76;
      v185 = (utl::_RefCountBase *)v75;
      if ( v75 )
        _InterlockedIncrement(v75 + 2);
      v78 = (**v77)(v77, 0);
      v62 = 0;
      if ( !v78 )
        goto LABEL_92;
      v79 = (volatile signed __int32 *)v57[4].Buffer;
      v80 = *(_QWORD *)&v57[4].Length;
      v159 = v76 | 0x10;
      v190 = (utl::_RefCountBase *)v79;
      if ( v79 )
        _InterlockedIncrement(v79 + 2);
      v81 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v80 + 40LL))(v80, 0);
      v62 = 0;
      v82 = 1;
      if ( v81 )
LABEL_92:
        v82 = 0;
      v83 = v159;
      if ( (v159 & 0x10) != 0 )
      {
        LODWORD(v71) = (_DWORD)v190;
        v83 = v159 & 0xFFFFFFEF;
        v159 &= ~0x10u;
        if ( v190 )
        {
          utl::_RefCountBase::_DecStrong(v190);
          v83 = v159;
        }
      }
      if ( (v83 & 8) != 0 )
      {
        LODWORD(v71) = (_DWORD)v185;
        v83 &= ~8u;
        v159 = v83;
        if ( v185 )
        {
          utl::_RefCountBase::_DecStrong(v185);
          v83 = v159;
        }
      }
      if ( (v83 & 4) != 0 )
      {
        v159 = v83 & 0xFFFFFFFB;
        if ( v186 )
          utl::_RefCountBase::_DecStrong(v186);
      }
      if ( v82 )
      {
        v84 = v57[4].Buffer;
        *(_QWORD *)&Source.Length = *(_QWORD *)&v57[4].Length;
        Source.Buffer = v84;
        if ( v84 )
          _InterlockedIncrement((volatile signed __int32 *)v84 + 2);
        v85 = (volatile signed __int32 **)UnionFs::UfsPathTable::LockPayloadPerCallerIntent(
                                            (_DWORD)v71,
                                            (unsigned int)&v177,
                                            v163,
                                            (unsigned int)&Source,
                                            (__int64)&v164);
        v62 = *v85;
        *v85 = 0;
        v86 = v165;
        v165 = (PERESOURCE)v62;
        if ( v86 )
        {
          ExReleaseResourceLite(v86);
          KeLeaveCriticalRegion();
        }
        v87 = v177;
        v177 = 0;
        if ( v87 )
        {
          ExReleaseResourceLite(v87);
          KeLeaveCriticalRegion();
        }
        if ( v84 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v84);
      }
    }
    if ( (*a5 & 2) != 0 && !v161 )
    {
      *((_QWORD *)a5 + 5) = v57;
      a5[12] = 1;
    }
    v88 = *(_QWORD *)&v57[4].Length;
    if ( !v88 )
    {
      v90 = v159;
LABEL_122:
      v56 = v178;
LABEL_123:
      v92 = 0;
      goto LABEL_124;
    }
    v89 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 *, _QWORD))(*(_QWORD *)v88 + 48LL))(v88, v62, 0);
    v90 = v159;
    if ( !v89 )
      goto LABEL_122;
    v56 = (volatile signed __int32 *)v57[4].Buffer;
    v90 = v159 | 0x20;
    v91 = *(_QWORD *)&v57[4].Length;
    v159 |= 0x20u;
    v178 = v56;
    if ( v56 )
      _InterlockedIncrement(v56 + 2);
    if ( !*(_BYTE *)(v91 + 8) && (v163 & 2) == 0 )
      goto LABEL_123;
    v92 = 1;
LABEL_124:
    if ( (v90 & 0x20) != 0 )
    {
      v159 = v90 & 0xFFFFFFDF;
      if ( v56 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v56);
    }
    if ( v92 )
    {
      v93 = v40;
      v166 = v57;
      v40 = v165;
      v165 = 0;
      if ( v93 )
      {
        ExReleaseResourceLite(v93);
        KeLeaveCriticalRegion();
      }
      if ( v49 )
        _InterlockedIncrement(v49 + 2);
      v94 = v39;
      v174 = v179;
      v39 = (utl::_RefCountBase *)v49;
      if ( v94 )
        utl::_RefCountBase::_DecStrong(v94);
      if ( (*a5 & 1) != 0 )
        *(_DWORD *)v167 = **((unsigned __int16 **)a5 + 7);
      a5[1] = v161 + 1;
      if ( (*v173 & 2) == 0 || v162 )
      {
        v140 = v165;
        v165 = 0;
        if ( v140 )
        {
          ExReleaseResourceLite(v140);
          KeLeaveCriticalRegion();
        }
        v141 = v57;
        goto LABEL_253;
      }
    }
    v51 = *(UnionFs::UfsPathTree **)&v57[3].Length;
    if ( !v51 )
    {
      v153 = v165;
      v165 = 0;
      if ( v153 )
      {
        ExReleaseResourceLite(v153);
        KeLeaveCriticalRegion();
      }
LABEL_285:
      v141 = v166;
      if ( !v166 )
      {
        if ( a5[1] )
          goto LABEL_287;
        goto LABEL_288;
      }
      goto LABEL_253;
    }
    v95 = *(_QWORD *)&String1.Length;
    v96 = *(volatile signed __int32 **)(*(_QWORD *)&String1.Length + 56LL);
    if ( v96 )
      _InterlockedIncrement(v96 + 2);
    v97 = (utl::_RefCountBase *)v52;
    v52 = v96;
    if ( v97 )
      utl::_RefCountBase::_DecStrong(v97);
    FsFltWil::AcquirePushLockShared(&v171, v95 + 128);
    v98 = *(struct _ERESOURCE **)(v95 + 80);
    v99 = *(volatile signed __int32 **)(v95 + 88);
    v179 = v98;
    if ( v99 )
      _InterlockedIncrement(v99 + 2);
    v100 = (FsFltWil::Details *)v171;
    v171 = 0;
    if ( v100 )
      FsFltWil::Details::ReleasePushLockShared(v100, (unsigned __int64 *)v56);
    v101 = (utl::_RefCountBase *)v49;
    v49 = v99;
    if ( v101 )
      utl::_RefCountBase::_DecStrong(v101);
    v102 = v165;
    v165 = 0;
    if ( v102 )
    {
      ExReleaseResourceLite(v102);
      KeLeaveCriticalRegion();
    }
    if ( !v161 )
      goto LABEL_285;
    v44 = v163;
  }
  v141 = v166;
  if ( !v166 )
  {
    if ( a5[1] )
LABEL_287:
      MicrosoftTelemetryAssertTriggeredMsgKM("Results.LookupResult == MAPPING_LOOKUP_RESULT::None");
LABEL_288:
    if ( v52 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v52);
    if ( v39 )
      utl::_RefCountBase::_DecStrong(v39);
    if ( v49 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v49);
    if ( v40 )
    {
      ExReleaseResourceLite(v40);
      KeLeaveCriticalRegion();
    }
LABEL_296:
    FsFltWil::Details::ReleaseRundownProtectionCacheAware(
      (FsFltWil::Details *)v195,
      (struct FsFltWil::Details::RundownRefCacheAware *)v56);
    if ( v195[16] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v195[16] + 24LL))(v195[16]);
    v104 = Resource;
    Resource = 0;
    goto LABEL_338;
  }
LABEL_253:
  v142 = v141[4].Buffer;
  v143 = *(_QWORD *)&v141[4].Length;
  if ( v142 )
    _InterlockedIncrement((volatile signed __int32 *)v142 + 2);
  *((_QWORD *)a5 + 2) = v143;
  v144 = (utl::_RefCountBase *)*((_QWORD *)a5 + 3);
  *((_QWORD *)a5 + 3) = v142;
  if ( v144 )
    utl::_RefCountBase::_DecStrong(v144);
  v145 = (struct _ERESOURCE *)*((_QWORD *)a5 + 4);
  *((_QWORD *)a5 + 4) = v40;
  if ( v145 )
  {
    ExReleaseResourceLite(v145);
    KeLeaveCriticalRegion();
  }
  FsFltWil::AcquirePushLockShared(&String1, &v141[8]);
  v147 = v166;
  v148 = *(struct _ERESOURCE **)&v141[5].Length;
  v149 = (volatile signed __int32 *)v166[5].Buffer;
  if ( v149 )
    _InterlockedIncrement(v149 + 2);
  if ( *(_QWORD *)&String1.Length )
    FsFltWil::Details::ReleasePushLockShared(*(FsFltWil::Details **)&String1.Length, v146);
  if ( v149 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v149);
  if ( v174 != v148 )
    a5[2] |= 8u;
  if ( (*a5 & 1) == 0 )
  {
LABEL_303:
    if ( (***((unsigned int (__fastcall ****)(_QWORD))a5 + 2))(*((_QWORD *)a5 + 2)) )
    {
      v154 = a5[2];
      if ( (v164 & 4) != 0 )
      {
        v155 = *((_QWORD *)a5 + 2);
        a5[2] = v154 | 4;
        a5[2] |= ((*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v155 + 32LL))(v155) != 0) + 1;
      }
      else
      {
        if ( (v164 & 1) != 0 )
          v156 = v154 | 1;
        else
          v156 = v154 | 2;
        a5[2] = v156;
      }
    }
    if ( !a5[1] )
      MicrosoftTelemetryAssertTriggeredMsgKM("Results.LookupResult != MAPPING_LOOKUP_RESULT::None");
    if ( v52 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v52);
    if ( v39 )
      utl::_RefCountBase::_DecStrong(v39);
    if ( v49 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v49);
    goto LABEL_296;
  }
  UnionFs::UfsPathName::PathLength(*((UnionFs::UfsPathName **)a5 + 7), v167[0]);
  if ( **((_WORD **)a5 + 7) != *(_WORD *)(*((_QWORD *)a5 + 7) + 24LL) )
    goto LABEL_302;
  if ( !RtlEqualUnicodeString(v147 + 2, &UnionFs::g_RootName, 0) )
    MicrosoftTelemetryAssertTriggeredMsgKM("RtlEqualUnicodeString(foundPayloadNode->GetPathComponent(), &g_RootName, false)");
  if ( *(_WORD *)(v176 + 40) <= 2u )
    MicrosoftTelemetryAssertTriggeredMsgKM("SearchPath.AsUnicodeString().Length > sizeof(WCHAR)");
  v150 = (int)v168;
  v151 = UnionFs::UfsPathName::AppendPath(*((UnionFs::UfsPathName **)a5 + 7), v147 + 2, v168);
  appended = v151;
  if ( v151 >= 0 )
  {
LABEL_302:
    UnionFs::UfsPathName::StripTrailingBackslash(*((UnionFs::UfsPathName **)a5 + 7));
    goto LABEL_303;
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v151,
    v150,
    (struct UnionFs::StackEventTracer *)0x1000140AADLL,
    (unsigned __int64)"UnionFs::UfsPathTable::LookupPriv",
    "PUSH: Appending volume root to FoundPath",
    v158);
  if ( v52 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v52);
  if ( v39 )
    utl::_RefCountBase::_DecStrong(v39);
  if ( v49 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v49);
  FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v195, v152);
  if ( v195[16] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v195[16] + 24LL))(v195[16]);
  v23 = Resource;
  Resource = 0;
LABEL_15:
  if ( v23 )
  {
    ExReleaseResourceLite(v23);
    KeLeaveCriticalRegion();
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14004c74c  mov     [rsp-8+arg_8], rbx
0x14004c751  push    rbp
0x14004c752  push    rsi
0x14004c753  push    rdi
0x14004c754  push    r12
0x14004c756  push    r13
0x14004c758  push    r14
0x14004c75a  push    r15
0x14004c75c  lea     rbp, [rsp-210h]
0x14004c764  sub     rsp, 310h
0x14004c76b  mov     rax, cs:__security_cookie
0x14004c772  xor     rax, rsp
0x14004c775  mov     [rbp+240h+var_38], rax
0x14004c77c  mov     esi, [rbp+240h+arg_30]
0x14004c782  xor     r12d, r12d
0x14004c785  mov     rdi, [rbp+240h+arg_20]
0x14004c78c  and     esi, 1
0x14004c78f  mov     r13, [rbp+240h+arg_28]
0x14004c796  mov     r15, r8
0x14004c799  mov     rax, [rbp+240h+arg_38]
0x14004c7a0  mov     rbx, rdx
0x14004c7a3  mov     [rsp+340h+var_2EC], r9d
0x14004c7a8  mov     r14, rcx
0x14004c7ab  mov     [rdi+4], r12d
0x14004c7af  mov     [rbp+240h+var_278], r8
0x14004c7b3  mov     [rbp+240h+var_298], rcx
0x14004c7b7  mov     [rsp+340h+var_2C8], r13
0x14004c7bc  mov     [rbp+240h+var_2A0], rax
0x14004c7c0  mov     [rsp+340h+var_300], r12d
0x14004c7c5  mov     [rsp+340h+Resource], r12
0x14004c7ca  mov     [rbp+240h+arg_30], esi
0x14004c7d0  jnz     short loc_14004C80A
0x14004c7d2  lea     rdx, [rcx+20h]
0x14004c7d6  lea     rcx, [rbp+240h+var_290]
0x14004c7da  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x14004c7df  mov     rcx, [rsp+340h+Resource]; Resource
0x14004c7e4  mov     rax, [rbp+240h+var_290]
0x14004c7e8  mov     [rsp+340h+Resource], rax
0x14004c7ed  test    rcx, rcx
0x14004c7f0  jz      short loc_14004C80A
0x14004c7f2  call    cs:__imp_ExReleaseResourceLite
0x14004c7f9  nop     dword ptr [rax+rax+00h]
0x14004c7fe  call    cs:__imp_KeLeaveCriticalRegion
0x14004c805  nop     dword ptr [rax+rax+00h]
0x14004c80a  mov     rdx, [r14+88h]; RunRefCacheAware
0x14004c811  lea     r9, [rbp+240h+var_1C0]
0x14004c818  mov     r8b, 1
0x14004c81b  mov     [rbp+240h+var_150], r12
0x14004c822  lea     rcx, [rbp+240h+var_148]; void *
0x14004c829  call    ?AcquireRundownReference@FsFltWil@@YA?AV?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@PEAU_EX_RUNDOWN_REF_CACHE_AWARE@@_NV?$function@$$A6AX_N@Z@wistd@@@Z; FsFltWil::AcquireRundownReference(_EX_RUNDOWN_REF_CACHE_AWARE *,bool,wistd::function<void (bool)>)
0x14004c82e  cmp     [rbp+240h+var_148], r12
0x14004c835  jnz     short loc_14004C848
0x14004c837  lea     rcx, [rbp+240h+var_148]; this
0x14004c83e  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14004c843  jmp     loc_14004DCC1
0x14004c848  lea     rcx, [r14+8]
0x14004c84c  mov     rax, [rcx]
0x14004c84f  cmp     rax, rcx
0x14004c852  jz      loc_14004DCB2
0x14004c858  lea     r12, [rax+10h]
0x14004c85c  mov     rdx, [r12+8]
0x14004c861  mov     [rbp+240h+var_2B0], r12
0x14004c865  cmp     [rdx], rbx
0x14004c868  jz      short loc_14004C86F
0x14004c86a  mov     rax, [rax]
0x14004c86d  jmp     short loc_14004C84F
0x14004c86f  mov     eax, [rdi]
0x14004c871  xor     ecx, ecx
0x14004c873  mov     dword ptr [rsp+340h+var_2D0], ecx
0x14004c877  test    al, 1
0x14004c879  jz      loc_14004C99A
0x14004c87f  movzx   ecx, word ptr [r15+2]
0x14004c884  lea     rsi, [rdi+38h]
0x14004c888  mov     rdx, rsi
0x14004c88b  mov     r8, r13
0x14004c88e  call    ?AllocEmpty@UfsPathName@UnionFs@@SAJGAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocEmpty(ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14004c893  xor     r15d, r15d
0x14004c896  mov     ebx, eax
0x14004c898  test    eax, eax
0x14004c89a  jns     short loc_14004C915
0x14004c89c  lea     rax, aPushAllocating_30; "PUSH: Allocating FoundPath"
0x14004c8a3  mov     r8, 1AB001408E9h; struct UnionFs::StackEventTracer *
0x14004c8ad  lea     r9, aUnionfsUfspath_67; "UnionFs::UfsPathTable::LookupPriv"
0x14004c8b4  mov     [rsp+340h+var_320], rax; char *
0x14004c8b9  mov     rdx, r13; int
0x14004c8bc  mov     ecx, ebx; this
0x14004c8be  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004c8c3  lea     rcx, [rbp+240h+var_148]; this
0x14004c8ca  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14004c8cf  mov     rcx, [rbp+240h+var_C8]
0x14004c8d6  test    rcx, rcx
0x14004c8d9  jz      short loc_14004C8E7
0x14004c8db  mov     rax, [rcx]
0x14004c8de  mov     rax, [rax+18h]
0x14004c8e2  call    _guard_dispatch_icall
0x14004c8e7  mov     rcx, [rsp+340h+Resource]; Resource
0x14004c8ec  mov     [rsp+340h+Resource], r15
0x14004c8f1  test    rcx, rcx
0x14004c8f4  jz      short loc_14004C90E
0x14004c8f6  call    cs:__imp_ExReleaseResourceLite
0x14004c8fd  nop     dword ptr [rax+rax+00h]
0x14004c902  call    cs:__imp_KeLeaveCriticalRegion
0x14004c909  nop     dword ptr [rax+rax+00h]
0x14004c90e  mov     eax, ebx
0x14004c910  jmp     loc_14004DD02
0x14004c915  mov     r8, [rsi]
0x14004c918  mov     rax, [r12+8]
0x14004c91d  mov     rcx, [r8+8]
0x14004c921  movzx   edx, word ptr [rax+78h]
0x14004c925  mov     [r8+1Ah], dx
0x14004c92a  mov     [r8+18h], dx
0x14004c92f  mov     [r8+20h], rcx
0x14004c933  lea     rax, [rcx+rdx]
0x14004c937  mov     [r8+38h], r15w
0x14004c93c  mov     [r8+30h], rax
0x14004c940  movzx   eax, word ptr [r8]
0x14004c944  sub     ax, dx
0x14004c947  lea     rdx, [rbp+240h+Source]; Source
0x14004c94b  mov     [r8+2Ah], ax
0x14004c950  mov     [r8+28h], ax
0x14004c955  mov     r8, r13; struct UnionFs::StackEventTracer *
0x14004c958  mov     rax, [r12+8]
0x14004c95d  mov     rcx, [rsi]; SourceString
0x14004c960  movups  xmm0, xmmword ptr [rax+78h]
0x14004c964  movdqu  xmmword ptr [rbp+240h+Source.Length], xmm0
0x14004c969  call    ?AppendUnicodeString@UfsPathName@UnionFs@@QEAAJAEBU_UNICODE_STRING@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AppendUnicodeString(_UNICODE_STRING const &,UnionFs::StackEventTracer &)
0x14004c96e  mov     ebx, eax
0x14004c970  test    eax, eax
0x14004c972  jns     short loc_14004C98A
0x14004c974  lea     rax, aPushAppendingV; "PUSH: Appending volume path to FoundPat"...
0x14004c97b  mov     r8, 1B1001408F3h
0x14004c985  jmp     loc_14004C8AD
0x14004c98a  mov     rax, [rsi]
0x14004c98d  mov     esi, [rbp+240h+arg_30]
0x14004c993  movzx   edx, word ptr [rax]; struct FsFltWil::Details::RundownRefCacheAware *
0x14004c996  mov     dword ptr [rsp+340h+var_2D0], edx
0x14004c99a  xor     r13d, r13d
0x14004c99d  mov     r15b, r13b
0x14004c9a0  mov     ebx, 2
0x14004c9a5  test    r15b, r15b
0x14004c9a8  jz      loc_14004CA7A
0x14004c9ae  test    esi, esi
0x14004c9b0  jnz     loc_14004D28D
0x14004c9b6  lea     rcx, [rbp+240h+var_148]; this
0x14004c9bd  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14004c9c2  xor     edx, edx; Val
0x14004c9c4  lea     rcx, [rbp+240h+var_148]; void *
0x14004c9cb  mov     r8d, 88h; Size
0x14004c9d1  call    memset
0x14004c9d6  lea     rdx, [r14+20h]
0x14004c9da  lea     rcx, [rbp+240h+var_258]
0x14004c9de  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x14004c9e3  mov     rcx, [rsp+340h+Resource]; Resource
0x14004c9e8  mov     rax, [rbp+240h+var_258]
0x14004c9ec  mov     [rsp+340h+Resource], rax
0x14004c9f1  test    rcx, rcx
0x14004c9f4  jz      short loc_14004CA0E
0x14004c9f6  call    cs:__imp_ExReleaseResourceLite
0x14004c9fd  nop     dword ptr [rax+rax+00h]
0x14004ca02  call    cs:__imp_KeLeaveCriticalRegion
0x14004ca09  nop     dword ptr [rax+rax+00h]
0x14004ca0e  mov     rdx, [r14+88h]; RunRefCacheAware
0x14004ca15  lea     r9, [rbp+240h+var_1C0]
0x14004ca1c  mov     r8b, 1
0x14004ca1f  mov     [rbp+240h+var_258], r13
0x14004ca23  lea     rcx, [rbp+240h+var_C0]; void *
0x14004ca2a  mov     [rbp+240h+var_150], r13
0x14004ca31  call    ?AcquireRundownReference@FsFltWil@@YA?AV?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@PEAU_EX_RUNDOWN_REF_CACHE_AWARE@@_NV?$function@$$A6AX_N@Z@wistd@@@Z; FsFltWil::AcquireRundownReference(_EX_RUNDOWN_REF_CACHE_AWARE *,bool,wistd::function<void (bool)>)
0x14004ca36  lea     rdx, [rbp+240h+var_C0]; void *
0x14004ca3d  lea     rcx, [rbp+240h+var_148]; this
0x14004ca44  call    ??4?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>::operator=(wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0> &&)
0x14004ca49  lea     rcx, [rbp+240h+var_C0]; this
0x14004ca50  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14004ca55  mov     rcx, [rbp+240h+var_40]
0x14004ca5c  test    rcx, rcx
0x14004ca5f  jz      short loc_14004CA6D
0x14004ca61  mov     rax, [rcx]
0x14004ca64  mov     rax, [rax+18h]
0x14004ca68  call    _guard_dispatch_icall
0x14004ca6d  cmp     [rbp+240h+var_148], r13
0x14004ca74  jz      loc_14004D256
0x14004ca7a  mov     rsi, [r12]
0x14004ca7e  mov     rcx, r12; this
0x14004ca81  mov     [rsp+340h+var_2E8], r13d
0x14004ca86  call    ?HasVolumeRootMapping@UfsInstanceTierNode@UnionFs@@QEBA_NXZ; UnionFs::UfsInstanceTierNode::HasVolumeRootMapping(void)
0x14004ca8b  test    al, al
0x14004ca8d  jz      short loc_14004CAD0
0x14004ca8f  mov     r13, [rbp+240h+var_278]
0x14004ca93  lea     rdx, ?g_RootName@UnionFs@@3U_UNICODE_STRING@@B; String2
0x14004ca9a  xor     r8d, r8d; CaseInSensitive
0x14004ca9d  lea     rcx, [rbp+240h+String1]; String1
0x14004caa1  movups  xmm0, xmmword ptr [r13+28h]
0x14004caa6  movdqu  xmmword ptr [rbp+240h+String1.Length], xmm0
0x14004caab  call    cs:__imp_RtlEqualUnicodeString
0x14004cab2  nop     dword ptr [rax+rax+00h]
0x14004cab7  xor     r12d, r12d
0x14004caba  test    al, al
0x14004cabc  jnz     loc_14004D2CC
0x14004cac2  mov     eax, [r14]
0x14004cac5  test    bl, al
0x14004cac7  jz      loc_14004D2CC
0x14004cacd  xor     r13d, r13d
0x14004cad0  mov     rcx, [rsi+40h]
0x14004cad4  mov     r12, r13
0x14004cad7  mov     [rbp+240h+var_290], r13
0x14004cadb  mov     [rsp+340h+var_2D8], r13
0x14004cae0  xor     r13d, r13d
0x14004cae3  mov     ebx, r13d
0x14004cae6  test    rcx, rcx
0x14004cae9  jz      loc_14004CB7E
0x14004caef  mov     rax, [rcx]
0x14004caf2  mov     rax, [rax+30h]
0x14004caf6  call    _guard_dispatch_icall
0x14004cafb  test    al, al
0x14004cafd  jz      short loc_14004CB7E
0x14004caff  mov     r14, [rsi+48h]
0x14004cb03  mov     rax, [rsi+40h]
0x14004cb07  mov     [rsp+340h+var_2D8], rsi
0x14004cb0c  mov     [rbp+240h+var_1F0], rax
0x14004cb10  mov     [rbp+240h+var_1E8], r14
0x14004cb14  test    r14, r14
0x14004cb17  jz      short loc_14004CB1E
0x14004cb19  lock inc dword ptr [r14+8]
0x14004cb1e  mov     r15d, [rsp+340h+var_2EC]
0x14004cb23  lea     rax, [rsp+340h+var_2E8]
0x14004cb28  mov     r8d, r15d
0x14004cb2b  mov     [rsp+340h+var_320], rax
0x14004cb30  lea     r9, [rbp+240h+var_1F0]
0x14004cb34  lea     rdx, [rbp+240h+var_250]
0x14004cb38  call    ?LockPayloadPerCallerIntent@UfsPathTable@UnionFs@@AEBA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@W4LookupFlags@2@AEBV?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@PEAW4PayloadLockType@2@@Z; UnionFs::UfsPathTable::LockPayloadPerCallerIntent(UnionFs::LookupFlags,utl::shared_ptr<UnionFs::UfsTablePayload> const &,UnionFs::PayloadLockType *)
0x14004cb3d  mov     rbx, [rax]
0x14004cb40  mov     [rax], r13
0x14004cb43  mov     rcx, [rbp+240h+var_250]; Resource
0x14004cb47  mov     [rbp+240h+var_250], r13
0x14004cb4b  test    rcx, rcx
0x14004cb4e  jz      short loc_14004CB68
0x14004cb50  call    cs:__imp_ExReleaseResourceLite
0x14004cb57  nop     dword ptr [rax+rax+00h]
0x14004cb5c  call    cs:__imp_KeLeaveCriticalRegion
0x14004cb63  nop     dword ptr [rax+rax+00h]
0x14004cb68  test    r14, r14
0x14004cb6b  jz      short loc_14004CB75
0x14004cb6d  mov     rcx, r14; this
0x14004cb70  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004cb75  mov     dword ptr [rdi+4], 2
0x14004cb7c  jmp     short loc_14004CB83
0x14004cb7e  mov     r15d, [rsp+340h+var_2EC]
0x14004cb83  lea     rdx, [rsi+80h]
0x14004cb8a  lea     rcx, [rbp+240h+var_248]
0x14004cb8e  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14004cb93  mov     r14, [rsi+58h]
0x14004cb97  mov     rax, [rsi+50h]
0x14004cb9b  mov     [rbp+240h+var_260], rax
0x14004cb9f  test    r14, r14
0x14004cba2  jz      short loc_14004CBA9
0x14004cba4  lock inc dword ptr [r14+8]
0x14004cba9  mov     rcx, [rbp+240h+var_248]; this
0x14004cbad  mov     [rbp+240h+var_248], r13
0x14004cbb1  test    rcx, rcx
0x14004cbb4  jz      short loc_14004CBBB
0x14004cbb6  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x14004cbbb  mov     r13, [rsi+30h]
0x14004cbbf  mov     rsi, [rsi+38h]
0x14004cbc3  test    rsi, rsi
0x14004cbc6  jz      short loc_14004CBCC
0x14004cbc8  lock inc dword ptr [rsi+8]
0x14004cbcc  xorps   xmm0, xmm0
0x14004cbcf  movups  xmmword ptr [rbp+240h+var_218.Length], xmm0
0x14004cbd3  mov     rax, [rbp+240h+var_278]
0x14004cbd7  lea     rdx, [rbp+240h+var_218]; struct _UNICODE_STRING *
0x14004cbdb  lea     rcx, [rbp+240h+String1]; this
0x14004cbdf  movups  xmm0, xmmword ptr [rax]
0x14004cbe2  movzx   r8d, word ptr [rax+18h]; struct _UNICODE_STRING *
0x14004cbe7  movdqu  xmmword ptr [rbp+240h+String1.Length], xmm0
0x14004cbec  call    ?WalkPath@Utils@UnionFs@@YA_NAEBU_UNICODE_STRING@@AEAU3@G@Z; UnionFs::Utils::WalkPath(_UNICODE_STRING const &,_UNICODE_STRING &,ushort)
0x14004cbf1  xor     ecx, ecx
0x14004cbf3  mov     [rsp+340h+var_2F0], al
0x14004cbf7  cmp     [rbp+240h+var_218.Length], cx
0x14004cbfb  jz      loc_14004DC10
0x14004cc01  mov     dl, r15b
0x14004cc04  lea     rax, [rbp+240h+var_218]
0x14004cc08  and     dl, 1
0x14004cc0b  xorps   xmm0, xmm0
0x14004cc0e  movups  [rbp+240h+var_208], xmm0
0x14004cc12  mov     byte ptr [rbp+240h+var_208+8], dl
0x14004cc15  mov     rcx, r13; this
0x14004cc18  lea     rdx, [rbp+240h+var_208]; struct UnionFs::UFS_COMPARE_KEY *
0x14004cc1c  mov     qword ptr [rbp+240h+var_208], rax
0x14004cc20  call    ?FindNode@UfsPathTree@UnionFs@@QEAAPEAVUfsPathTierNode@2@AEBUUFS_COMPARE_KEY@2@@Z; UnionFs::UfsPathTree::FindNode(UnionFs::UFS_COMPARE_KEY const &)
0x14004cc25  xor     r8d, r8d
0x14004cc28  mov     qword ptr [rbp+240h+String1.Length], rax
0x14004cc2c  mov     r13, rax
0x14004cc2f  test    rax, rax
0x14004cc32  jz      loc_14004DB41
0x14004cc38  mov     ecx, [rdi]
0x14004cc3a  test    cl, 1
0x14004cc3d  jz      short loc_14004CC64
0x14004cc3f  mov     r8, [rsp+340h+var_2C8]; struct _UNICODE_STRING *
0x14004cc44  lea     rdx, [rax+20h]; Source
0x14004cc48  mov     rcx, [rdi+38h]; this
  ... truncated ...
```
