# UnionFs::UfsPathTable::Delete(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,UnionFs::UfsUnionCtx const *)

- ea: `0x140046510`
- end: `0x140047dd4`
- name: `?Delete@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEBVUfsUnionCtx@2@@Z`
- size: `6340`
- prototype: `int __high(const struct _FLT_INSTANCE *, const struct UnionFs::UfsPathName *, struct UnionFs::StackEventTracer *, enum UnionFs::PathTableOptions, const struct UnionFs::UfsUnionCtx *)`
- caller_count: `5`
- callee_count: `31`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002349c`
- `0x14003c5ec`
- `0x14004dd90`
- `0x14005588c`
- `0x14006b59c`

## callees

- `0x140001c08`
- `0x140002354`
- `0x140002500`
- `0x140005d9c`
- `0x14000f7fc`
- `0x140020078`
- `0x1400454f4`
- `0x1400455f8`
- `0x1400456f8`
- `0x1400458d0`
- `0x14004591c`
- `0x140045aac`
- `0x140045dac`
- `0x1400464c8`
- `0x140046510`
- `0x14004e1fc`
- `0x14004f18c`
- `0x14004f4ac`
- `0x14004f5d4`
- `0x140056ac4`
- `0x140056afc`
- `0x1400790f0`
- `0x140079a24`
- `0x140079a6c`
- `0x140079afc`
- `0x140079da0`
- `0x140079dcc`
- `0x140079df4`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140046758`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046861`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046966`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046ab7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046b2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046b9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046d94`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046dc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046e41`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400473fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004761f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400476be`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047756`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047885`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047a1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047b35`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047b6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047c89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047d28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046758`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046861`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046966`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046ab7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046b2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046b9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046d94`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046dc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046e41`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400473fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004761f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400476be`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047756`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047885`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047a1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047b35`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047b6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047c89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047d28`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400466f0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400466f0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004660c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400468b0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140046e90`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004729d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004770b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400478d2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140047bf8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140047d8c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004660c`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400468b0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140046e90`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004729d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004770b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400478d2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140047bf8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140047d8c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140046618`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400468bc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140046e9c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400472a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047717`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400478de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047c04`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047d98`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140046618`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400468bc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140046e9c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400472a9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047717`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400478de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047c04`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140047d98`
- `FLTMGR!FltReleaseContext` at `0x140046a9d`
- `FLTMGR!FltReleaseContext` at `0x140046d7a`
- `FLTMGR!FltReleaseContext` at `0x140047b1b`
- `FLTMGR!FltReleaseContext` at `0x140046a9d`
- `FLTMGR!FltReleaseContext` at `0x140046d7a`
- `FLTMGR!FltReleaseContext` at `0x140047b1b`

## string_xrefs

- `0x1400465b4`: `ORIGIN: Table already run down`
- `0x140046a2a`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x140046d07`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004712d`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x14004736f`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x140047aa6`: `onecore\base\fs\unionfs\sys\pathtable.cpp`
- `0x1400465c7`: `UnionFs::UfsPathTable::Delete`
- `0x14004671d`: `UnionFs::UfsPathTable::Delete`
- `0x140046826`: `UnionFs::UfsPathTable::Delete`
- `0x14004692b`: `UnionFs::UfsPathTable::Delete`
- `0x140046a14`: `UnionFs::UfsPathTable::Delete`
- `0x140046b59`: `UnionFs::UfsPathTable::Delete`
- `0x140046cf1`: `UnionFs::UfsPathTable::Delete`
- `0x140046e11`: `UnionFs::UfsPathTable::Delete`
- `0x140047126`: `UnionFs::UfsPathTable::Delete`
- `0x140047449`: `UnionFs::UfsPathTable::Delete`
- `0x140047494`: `UnionFs::UfsPathTable::Delete`
- `0x1400474d2`: `UnionFs::UfsPathTable::Delete`
- `0x1400475d4`: `UnionFs::UfsPathTable::Delete`
- `0x14004767a`: `UnionFs::UfsPathTable::Delete`
- `0x140047846`: `UnionFs::UfsPathTable::Delete`
- `0x1400479da`: `UnionFs::UfsPathTable::Delete`
- `0x140047a91`: `UnionFs::UfsPathTable::Delete`
- `0x140047c3e`: `UnionFs::UfsPathTable::Delete`
- `0x140047cdf`: `UnionFs::UfsPathTable::Delete`
- `0x140047d47`: `UnionFs::UfsPathTable::Delete`
- `0x14004670a`: `ORIGIN: Non-recursive delete of volume root node.`
- `0x1400467bb`: `Recursive delete at table root that is not a union root`
- `0x140046815`: `ORIGIN: Recursive delete requested for \, but it is not a union root`
- `0x140046a36`: `Removing instance tier node: no dependent unions on delete of root`
- `0x140046b50`: `ORIGIN: Nested paths not enabled.`
- `0x140047438`: `ORIGIN: Nested paths not enabled.`
- `0x140047c9d`: `!moreComponentsLeft`
- `0x1400475c3`: `ORIGIN: Recursive delete on non-root node`
- `0x14004737b`: `Removing instance tier node: removed last path`
- `0x140047ab2`: `Removing instance tier node: removed last path`
- `0x140047165`: `Delete found a node with no payload and no descendant tree`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathTable::Delete(
        UnionFs::UfsPathTable *a1,
        __int64 a2,
        const char *a3,
        __int64 a4,
        int a5,
        struct UnionFs::UfsUnionCtx *a6)
{
  int v9; // r13d
  struct _ERESOURCE *v10; // rbx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v11; // rdx
  unsigned int v12; // esi
  struct FsFltWil::Details::RundownRefCacheAware *v13; // rdx
  _QWORD *v15; // rax
  _QWORD *v16; // rdi
  char v17; // si
  struct UnionFs::UfsPathTierNode *v18; // r15
  PVOID v19; // r8
  _QWORD *v20; // rcx
  __int64 v21; // rax
  unsigned __int64 *v22; // rdx
  volatile signed __int32 *v23; // rsi
  __int64 v24; // r13
  unsigned __int64 *v25; // rdx
  volatile signed __int32 *v26; // rsi
  __int64 v27; // r13
  struct FsFltWil::Details::RundownRefCacheAware *v28; // rdx
  PVOID v29; // r8
  _QWORD *v30; // rcx
  __int64 v31; // rax
  unsigned __int64 *v32; // rdx
  volatile signed __int32 *v33; // rsi
  struct UnionFs::UfsUnionCtx *v34; // r14
  bool v35; // r14
  PVOID v36; // r8
  _QWORD *v37; // rcx
  __int64 v38; // rax
  UnionFs::UfsPathTierNode *v39; // rsi
  UnionFs::UfsPathTierNode *v40; // rcx
  utl::_RefCountBase *v41; // rcx
  int v42; // r8d
  int v43; // r9d
  UnionFs::UfsPathTierNode *v44; // rcx
  utl::_RefCountBase *v45; // rax
  FsFltWil::Details **v46; // rax
  FsFltWil::Details *v47; // rcx
  _QWORD *v48; // rdx
  _QWORD *v49; // rax
  void *v50; // rcx
  struct FsFltWil::Details::RundownRefCacheAware *v51; // rdx
  UnionFs::UfsPathTierNode *v52; // rcx
  utl::_RefCountBase *v53; // rcx
  PVOID v54; // rcx
  _QWORD *v55; // rdx
  __int64 v56; // rax
  struct FsFltWil::Details::RundownRefCacheAware *v57; // rdx
  PVOID v58; // rcx
  _QWORD *v59; // rdx
  __int64 v60; // rax
  unsigned __int64 *v61; // rdx
  volatile signed __int32 *v62; // rsi
  utl::_RefCountBase *v63; // r14
  utl::_RefCountBase *v64; // rcx
  UnionFs::UfsPathTierNode *v65; // rsi
  UnionFs::UfsPathTierNode *v66; // rcx
  utl::_RefCountBase *v67; // rcx
  int v68; // r8d
  int v69; // r9d
  UnionFs::UfsPathTierNode *v70; // rdx
  utl::_RefCountBase *v71; // rcx
  FsFltWil::Details **v72; // rax
  FsFltWil::Details *v73; // rcx
  _QWORD *v74; // rcx
  _QWORD *v75; // rax
  void *v76; // rcx
  PVOID v77; // rcx
  _QWORD *v78; // rdx
  __int64 v79; // rax
  int v80; // eax
  unsigned __int16 v81; // r9
  unsigned int v82; // r14d
  struct FsFltWil::Details::RundownRefCacheAware *v83; // rdx
  PVOID v84; // rcx
  _QWORD *v85; // rdx
  __int64 v86; // rax
  volatile signed __int32 *v87; // r14
  UnionFs::UfsPathTree *v88; // rsi
  struct _UNICODE_STRING *v89; // r8
  bool v90; // al
  struct UnionFs::UfsPathTierNode *Node; // rax
  int v92; // r9d
  int v93; // r8d
  struct UnionFs::UfsPathTierNode *v94; // rsi
  utl::_RefCountBase **v95; // rax
  _DWORD *v96; // rax
  volatile signed __int32 *v97; // rdx
  struct UnionFs::UfsPathTierNode *v98; // rax
  int v99; // eax
  volatile signed __int32 *v100; // rax
  utl::_RefCountBase *v101; // rcx
  __int64 v102; // rax
  utl::_RefCountBase *v103; // rcx
  utl::_RefCountBase *v104; // rdx
  utl::_RefCountBase *v105; // rcx
  struct _UNICODE_STRING *v106; // rax
  int v107; // eax
  struct FsFltWil::Details::RundownRefCacheAware *v108; // rdx
  volatile signed __int32 *v109; // r12
  char v110; // r13
  UnionFs::UfsPathTree *v111; // rcx
  int v112; // r8d
  int v113; // r9d
  _QWORD *OwningUnion; // rax
  char v115; // r15
  FsFltWil::Details **v116; // rax
  FsFltWil::Details *v117; // rcx
  UnionFs::UfsPathTierNode **v118; // rdi
  _QWORD *v119; // rcx
  __int64 v120; // rax
  FsFltWil::Details *v121; // rsi
  const char *v122; // rax
  __int64 v123; // r8
  struct FsFltWil::Details::RundownRefCacheAware *v124; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v125; // rdx
  struct _ERESOURCE *v126; // rdx
  char v127; // r13
  volatile signed __int32 *v128; // rax
  char v129; // r13
  PVOID v130; // rcx
  _QWORD *v131; // rdx
  __int64 v132; // rax
  int v133; // edi
  struct FsFltWil::Details::RundownRefCacheAware *v134; // rdx
  PVOID v135; // rcx
  _QWORD *v136; // rdx
  __int64 v137; // rax
  PVOID v138; // rcx
  _QWORD *v139; // rdx
  __int64 v140; // rax
  volatile signed __int32 *v141; // rax
  int v142; // eax
  PVOID v143; // rcx
  _QWORD *v144; // rdx
  __int64 v145; // rax
  UnionFs::UfsPathTierNode *v146; // rcx
  utl::_RefCountBase *v147; // rcx
  volatile signed __int32 *v148; // r12
  char v149; // r13
  UnionFs::UfsPathTree *v150; // rcx
  __int64 v151; // r8
  int v152; // r9d
  unsigned __int64 *v153; // rdx
  volatile signed __int32 *v154; // rsi
  const char *v155; // rax
  char v156; // r15
  int v157; // eax
  PVOID v158; // rcx
  _QWORD *v159; // rdx
  __int64 v160; // rax
  FsFltWil::Details **v161; // rax
  FsFltWil::Details *v162; // rcx
  _QWORD *v163; // rcx
  _QWORD *v164; // rax
  void *v165; // rcx
  UnionFs::UfsPathTierNode **v166; // rdi
  _QWORD *v167; // rcx
  __int64 v168; // rax
  FsFltWil::Details *v169; // rsi
  PVOID v170; // rcx
  _QWORD *v171; // rdx
  __int64 v172; // rax
  __int64 v173; // rcx
  PVOID v174; // rcx
  _QWORD *v175; // rdx
  __int64 v176; // rax
  char *v177; // [rsp+28h] [rbp-D8h]
  bool v178; // [rsp+50h] [rbp-B0h]
  char v179; // [rsp+50h] [rbp-B0h]
  char v180; // [rsp+50h] [rbp-B0h]
  char v181; // [rsp+50h] [rbp-B0h]
  char v182; // [rsp+51h] [rbp-AFh]
  bool v183; // [rsp+52h] [rbp-AEh] BYREF
  unsigned int v184; // [rsp+54h] [rbp-ACh] BYREF
  FsFltWil::Details *v185; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v187; // [rsp+70h] [rbp-90h]
  char *v188; // [rsp+78h] [rbp-88h] BYREF
  char v189[8]; // [rsp+80h] [rbp-80h] BYREF
  FsFltWil::Details *v190; // [rsp+88h] [rbp-78h] BYREF
  utl::_RefCountBase *v191[2]; // [rsp+90h] [rbp-70h] BYREF
  struct UnionFs::UfsPathTierNode *v192; // [rsp+A0h] [rbp-60h] BYREF
  const char *v193; // [rsp+A8h] [rbp-58h] BYREF
  struct UnionFs::UfsInstanceTierNode *v194; // [rsp+B0h] [rbp-50h] BYREF
  UnionFs::UfsPathTable *v195; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v196; // [rsp+C0h] [rbp-40h] BYREF
  struct UnionFs::UfsUnionCtx *v197; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v198; // [rsp+D8h] [rbp-28h]
  struct _UNICODE_STRING v199; // [rsp+E0h] [rbp-20h] BYREF
  UNICODE_STRING String1; // [rsp+F0h] [rbp-10h] BYREF
  char v201[8]; // [rsp+100h] [rbp+0h] BYREF
  utl::_RefCountBase *v202; // [rsp+108h] [rbp+8h]
  UnionFs::UfsPathTable *v203; // [rsp+110h] [rbp+10h] BYREF
  int v204; // [rsp+118h] [rbp+18h]
  struct UnionFs::UfsUnionCtx **v205; // [rsp+120h] [rbp+20h]
  struct UnionFs::UfsInstanceTierNode **v206; // [rsp+128h] [rbp+28h]
  __int64 v207; // [rsp+130h] [rbp+30h]
  PVOID *v208; // [rsp+138h] [rbp+38h]
  bool *v209; // [rsp+140h] [rbp+40h]
  int v210; // [rsp+148h] [rbp+48h] BYREF
  struct UnionFs::UfsUnionCtx **v211; // [rsp+150h] [rbp+50h]
  utl::_RefCountBase **v212; // [rsp+158h] [rbp+58h]
  UnionFs::UfsPathTable *v213; // [rsp+160h] [rbp+60h]
  _QWORD v214[2]; // [rsp+168h] [rbp+68h] BYREF
  int v215; // [rsp+178h] [rbp+78h]
  struct UnionFs::UfsUnionCtx *v216; // [rsp+180h] [rbp+80h]
  char v217[8]; // [rsp+188h] [rbp+88h] BYREF
  utl::_RefCountBase *v218; // [rsp+190h] [rbp+90h]
  __int64 v219; // [rsp+208h] [rbp+108h]
  _QWORD v220[16]; // [rsp+210h] [rbp+110h] BYREF
  __int64 v221; // [rsp+290h] [rbp+190h]

  v197 = a6;
  v188 = (char *)a3;
  v195 = a1;
  LODWORD(v196) = 0;
  v9 = 0;
  v10 = 0;
  if ( (a5 & 1) == 0 )
  {
    FsFltWil::AcquireResourceExclusive(&v190, (char *)a1 + 32);
    v10 = (struct _ERESOURCE *)v190;
  }
  v11 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)a1 + 17);
  v219 = 0;
  FsFltWil::AcquireRundownReference(v220, v11);
  if ( !v220[0] )
  {
    v12 = -1058209782;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0ED000ALL,
      a4,
      (struct UnionFs::StackEventTracer *)0x1BB0014062CLL,
      (unsigned __int64)"UnionFs::UfsPathTable::Delete",
      "ORIGIN: Table already run down",
      v177);
LABEL_5:
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v220, v13);
    if ( v221 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v221 + 24LL))(v221);
    if ( v10 )
    {
      ExReleaseResourceLite(v10);
      KeLeaveCriticalRegion();
    }
    return v12;
  }
  v15 = (_QWORD *)((char *)a1 + 8);
  v194 = 0;
  v16 = (_QWORD *)*((_QWORD *)a1 + 1);
  v198 = (_QWORD *)((char *)a1 + 8);
  while ( 1 )
  {
    if ( v16 == v15 )
      goto LABEL_359;
    if ( *(_QWORD *)v16[3] == a2 )
      break;
    v16 = (_QWORD *)*v16;
    v15 = (_QWORD *)((char *)a1 + 8);
  }
  v194 = (struct UnionFs::UfsInstanceTierNode *)(v16 + 2);
  if ( v16 == (_QWORD *)-16LL )
  {
LABEL_359:
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0000225LL,
      a4,
      (struct UnionFs::StackEventTracer *)0x3170014063ELL,
      (unsigned __int64)"UnionFs::UfsPathTable::Delete",
      "ORIGIN: Instance tier node not found.",
      v177);
LABEL_360:
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v220, v57);
    if ( v221 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v221 + 24LL))(v221);
    if ( v10 )
    {
      ExReleaseResourceLite(v10);
      KeLeaveCriticalRegion();
    }
    return 3221226021LL;
  }
  v17 = a5;
  P[0] = P;
  v192 = 0;
  P[1] = P;
  v183 = 0;
  v214[0] = P;
  v214[1] = &v192;
  v190 = v197;
  v216 = v197;
  *(_OWORD *)v191 = 0;
  v187 = 0;
  v211 = &v197;
  v212 = v191;
  v213 = a1;
  v18 = (struct UnionFs::UfsPathTierNode *)v16[2];
  v215 = a5;
  v210 = a5;
  String1 = *(UNICODE_STRING *)(v188 + 40);
  if ( RtlEqualUnicodeString(&String1, &UnionFs::g_RootName, 0) )
  {
    if ( (a5 & 2) == 0 )
    {
      v12 = -1073741595;
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC00000E5LL,
        a4,
        (struct UnionFs::StackEventTracer *)0x481001406B0LL,
        (unsigned __int64)"UnionFs::UfsPathTable::Delete",
        "ORIGIN: Non-recursive delete of volume root node.",
        v177);
      while ( 1 )
      {
        v19 = P[0];
        if ( P[0] == P )
          break;
        v20 = (_QWORD *)*((_QWORD *)P[0] + 1);
        v21 = *(_QWORD *)P[0];
        *v20 = *(_QWORD *)P[0];
        *(_QWORD *)(v21 + 8) = v20;
        ExFreePoolWithTag(v19, 0);
      }
      v187 = 0;
      if ( v191[1] )
        utl::_RefCountBase::_DecStrong(v191[1]);
      goto LABEL_5;
    }
    FsFltWil::AcquirePushLockShared(&v190, (char *)v18 + 128);
    v23 = (volatile signed __int32 *)*((_QWORD *)v18 + 11);
    v24 = *((_QWORD *)v18 + 10);
    if ( v23 )
      _InterlockedIncrement(v23 + 2);
    if ( v190 )
      FsFltWil::Details::ReleasePushLockShared(v190, v22);
    if ( !v24 )
      MicrosoftTelemetryAssertTriggeredMsgKM("Recursive delete at table root that is not a union root");
    if ( v23 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v23);
    FsFltWil::AcquirePushLockShared(&v190, (char *)v18 + 128);
    v26 = (volatile signed __int32 *)*((_QWORD *)v18 + 11);
    v27 = *((_QWORD *)v18 + 10);
    if ( v26 )
      _InterlockedIncrement(v26 + 2);
    if ( v190 )
      FsFltWil::Details::ReleasePushLockShared(v190, v25);
    if ( v26 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v26);
    if ( !v27 )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000000DLL,
        a4,
        (struct UnionFs::StackEventTracer *)0x491001406BBLL,
        (unsigned __int64)"UnionFs::UfsPathTable::Delete",
        "ORIGIN: Recursive delete requested for \\, but it is not a union root",
        v177);
      while ( 1 )
      {
        v29 = P[0];
        if ( P[0] == P )
          break;
        v30 = (_QWORD *)*((_QWORD *)P[0] + 1);
        v31 = *(_QWORD *)P[0];
        *v30 = *(_QWORD *)P[0];
        *(_QWORD *)(v31 + 8) = v30;
        ExFreePoolWithTag(v29, 0);
      }
      goto LABEL_40;
    }
    FsFltWil::AcquirePushLockShared(&v190, (char *)v18 + 128);
    v33 = (volatile signed __int32 *)*((_QWORD *)v18 + 11);
    v34 = (struct UnionFs::UfsUnionCtx *)*((_QWORD *)v18 + 10);
    if ( v33 )
      _InterlockedIncrement(v33 + 2);
    if ( v190 )
      FsFltWil::Details::ReleasePushLockShared(v190, v32);
    v35 = v34 != v197;
    if ( v33 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v33);
    if ( v35 )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000000DLL,
        a4,
        (struct UnionFs::StackEventTracer *)0x496001406C3LL,
        (unsigned __int64)"UnionFs::UfsPathTable::Delete",
        "ORIGIN: Root mapping doesn't belong to OwningUnion",
        v177);
      while ( 1 )
      {
        v36 = P[0];
        if ( P[0] == P )
          break;
        v37 = (_QWORD *)*((_QWORD *)P[0] + 1);
        v38 = *(_QWORD *)P[0];
        *v37 = *(_QWORD *)P[0];
        *(_QWORD *)(v38 + 8) = v37;
        ExFreePoolWithTag(v36, 0);
      }
      v187 = 0;
      goto LABEL_41;
    }
    if ( *((_QWORD *)v18 + 15) )
    {
      UnionFs::UfsPathTable::RecursiveDeleteKeepDependents(v195, v194, v18, 0);
      v52 = (UnionFs::UfsPathTierNode *)*((_QWORD *)v18 + 18);
      if ( v52 )
        UnionFs::UfsPathTierNode::ClearPayload(v52);
      v53 = (utl::_RefCountBase *)*((_QWORD *)v18 + 9);
      *((_QWORD *)v18 + 8) = 0;
      *((_QWORD *)v18 + 9) = 0;
      if ( v53 )
        utl::_RefCountBase::_DecStrong(v53);
      UnionFs::UfsPathTierNode::ClearOwningUnion(v18);
    }
    else
    {
      v39 = *(UnionFs::UfsPathTierNode **)v194;
      v40 = *(UnionFs::UfsPathTierNode **)(*(_QWORD *)v194 + 144LL);
      if ( v40 )
        UnionFs::UfsPathTierNode::ClearPayload(v40);
      v41 = (utl::_RefCountBase *)*((_QWORD *)v39 + 9);
      *((_QWORD *)v39 + 8) = 0;
      *((_QWORD *)v39 + 9) = 0;
      if ( v41 )
        utl::_RefCountBase::_DecStrong(v41);
      UnionFs::UfsPathTierNode::ClearOwningUnion(v39);
      v44 = *(UnionFs::UfsPathTierNode **)v194;
      if ( *(_QWORD *)(*(_QWORD *)v194 + 48LL) )
      {
        v45 = (utl::_RefCountBase *)*((_QWORD *)v44 + 7);
        *((_QWORD *)v44 + 6) = 0;
        *((_QWORD *)v44 + 7) = 0;
        if ( v45 )
          utl::_RefCountBase::_DecStrong(v45);
      }
      if ( (unsigned int)dword_14009E178 > 4
        && (qword_14009E188 & 0x10) != 0
        && (qword_14009E190 & 0x10) == qword_14009E190 )
      {
        v46 = (FsFltWil::Details **)v16[3];
        v188 = "UnionFs::UfsPathTable::Delete";
        v47 = *v46;
        v185 = (FsFltWil::Details *)"onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
        *(_QWORD *)v189 = "Removing instance tier node: no dependent unions on delete of root";
        v190 = v47;
        v184 = 1742;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          (_DWORD)v47,
          (unsigned int)&word_1400976AE,
          v42,
          v43,
          (__int64)v189,
          (__int64)&v188,
          (__int64)&v185,
          (__int64)&v184,
          (__int64)&v190);
      }
      v48 = (_QWORD *)v16[1];
      v49 = (_QWORD *)*v16;
      *v48 = *v16;
      v49[1] = v48;
      v50 = (void *)v16[3];
      v16[3] = 0;
      if ( v50 )
        FltReleaseContext(v50);
      utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(v16 + 2);
      ExFreePoolWithTag(v16, 0);
      --v198[2];
    }
    while ( 1 )
    {
      v54 = P[0];
      if ( P[0] == P )
        break;
      v55 = (_QWORD *)*((_QWORD *)P[0] + 1);
      v56 = *(_QWORD *)P[0];
      *v55 = *(_QWORD *)P[0];
      *(_QWORD *)(v56 + 8) = v55;
      ExFreePoolWithTag(v54, 0);
    }
    v187 = 0;
LABEL_338:
    if ( v191[1] )
      utl::_RefCountBase::_DecStrong(v191[1]);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v220, v51);
    if ( v221 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v221 + 24LL))(v221);
    if ( v10 )
    {
      ExReleaseResourceLite(v10);
      KeLeaveCriticalRegion();
    }
    return 0;
  }
  if ( (*(_DWORD *)v195 & 2) == 0 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0000225LL,
      a4,
      (struct UnionFs::StackEventTracer *)0x330001406EELL,
      (unsigned __int64)"UnionFs::UfsPathTable::Delete",
      "ORIGIN: Nested paths not enabled.",
      v177);
    while ( 1 )
    {
      v58 = P[0];
      if ( P[0] == P )
        break;
      v59 = (_QWORD *)*((_QWORD *)P[0] + 1);
      v60 = *(_QWORD *)P[0];
      *v59 = *(_QWORD *)P[0];
      *(_QWORD *)(v60 + 8) = v59;
      ExFreePoolWithTag(v58, 0);
    }
LABEL_86:
    v187 = 0;
LABEL_87:
    if ( v191[1] )
      utl::_RefCountBase::_DecStrong(v191[1]);
    goto LABEL_360;
  }
  if ( (unsigned __int8)lambda_1ce04d05065b34531c8e00b101e67e6e_::operator()(&v210, v18) )
  {
    v192 = v18;
    FsFltWil::AcquirePushLockShared(&v185, (char *)v18 + 128);
    v62 = (volatile signed __int32 *)*((_QWORD *)v18 + 11);
    v63 = (utl::_RefCountBase *)*((_QWORD *)v18 + 10);
    if ( v62 )
      _InterlockedIncrement(v62 + 2);
    if ( v185 )
      FsFltWil::Details::ReleasePushLockShared(v185, v61);
    v64 = v191[1];
    v191[0] = v63;
    v191[1] = (utl::_RefCountBase *)v62;
    if ( v64 )
      utl::_RefCountBase::_DecStrong(v64);
    v17 = a5;
    v183 = 1;
  }
  v184 = v17 & 2;
  if ( (v17 & 2) != 0 && *((_QWORD *)v18 + 15) && UnionFs::UfsPathTierNode::OnlyDependentUnion(v18, v197) && !v192 )
  {
    v65 = *(UnionFs::UfsPathTierNode **)v194;
    v66 = *(UnionFs::UfsPathTierNode **)(*(_QWORD *)v194 + 144LL);
    if ( v66 )
      UnionFs::UfsPathTierNode::ClearPayload(v66);
    v67 = (utl::_RefCountBase *)*((_QWORD *)v65 + 9);
    *((_QWORD *)v65 + 8) = 0;
    *((_QWORD *)v65 + 9) = 0;
    if ( v67 )
      utl::_RefCountBase::_DecStrong(v67);
    UnionFs::UfsPathTierNode::ClearOwningUnion(v65);
    v70 = *(UnionFs::UfsPathTierNode **)v194;
    if ( *(_QWORD *)(*(_QWORD *)v194 + 48LL) )
    {
      v71 = (utl::_RefCountBase *)*((_QWORD *)v70 + 7);
      *((_QWORD *)v70 + 6) = 0;
      *((_QWORD *)v70 + 7) = 0;
      if ( v71 )
        utl::_RefCountBase::_DecStrong(v71);
    }
    if ( (unsigned int)dword_14009E178 > 4
      && (qword_14009E188 & 0x10) != 0
      && (qword_14009E190 & 0x10) == qword_14009E190 )
    {
      v72 = (FsFltWil::Details **)v16[3];
      v188 = "UnionFs::UfsPathTable::Delete";
      v73 = *v72;
      v185 = (FsFltWil::Details *)"onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
      *(_QWORD *)v189 = "Removing instance tier node: no root mapping and removing last union root node";
      v190 = v73;
      v184 = 1796;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (_DWORD)v73,
        (unsigned int)&word_1400976F6,
        v68,
        v69,
        (__int64)v189,
        (__int64)&v188,
        (__int64)&v185,
        (__int64)&v184,
        (__int64)&v190);
    }
    v74 = (_QWORD *)v16[1];
    v75 = (_QWORD *)*v16;
    *v74 = *v16;
    v75[1] = v74;
    v76 = (void *)v16[3];
    v16[3] = 0;
    if ( v76 )
      FltReleaseContext(v76);
    utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(v16 + 2);
    ExFreePoolWithTag(v16, 0);
    --v198[2];
    while ( 1 )
    {
      v77 = P[0];
      if ( P[0] == P )
        break;
      v78 = (_QWORD *)*((_QWORD *)P[0] + 1);
      v79 = *(_QWORD *)P[0];
      *v78 = *(_QWORD *)P[0];
      *(_QWORD *)(v79 + 8) = v78;
      ExFreePoolWithTag(v77, 0);
    }
    v187 = 0;
    goto LABEL_338;
  }
  v80 = lambda_2f919d4ddf8d051d9a3e31225519f38b_::operator()(v214, v18, a4);
  v82 = v80;
  if ( v80 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v80,
      a4,
      (struct UnionFs::StackEventTracer *)0x48F00140710LL,
      (unsigned __int64)"UnionFs::UfsPathTable::Delete",
      "PUSH: Updating intermediateNodes",
      v177);
    while ( 1 )
    {
      v84 = P[0];
      if ( P[0] == P )
        break;
      v85 = (_QWORD *)*((_QWORD *)P[0] + 1);
      v86 = *(_QWORD *)P[0];
      *v85 = *(_QWORD *)P[0];
      *(_QWORD *)(v86 + 8) = v85;
      ExFreePoolWithTag(v84, 0);
    }
    v187 = 0;
    if ( v191[1] )
      utl::_RefCountBase::_DecStrong(v191[1]);
    FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v220, v83);
    if ( v221 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v221 + 24LL))(v221);
    if ( v10 )
    {
      ExReleaseResourceLite(v10);
      KeLeaveCriticalRegion();
    }
    return v82;
  }
  *(_QWORD *)v189 = 0;
  v199 = 0;
  v87 = (volatile signed __int32 *)*((_QWORD *)v18 + 7);
  v88 = (UnionFs::UfsPathTree *)*((_QWORD *)v18 + 6);
  if ( v87 )
    _InterlockedIncrement(v87 + 2);
  v203 = v195;
  v204 = a5;
  v205 = &v197;
  v206 = &v194;
  v208 = P;
  v209 = &v183;
  v193 = 0;
  v182 = 1;
  v207 = a4;
  while ( 1 )
  {
    v89 = (struct _UNICODE_STRING *)*((unsigned __int16 *)v188 + 12);
    v196 = *(_OWORD *)v188;
    v90 = UnionFs::Utils::WalkPath((UnionFs::Utils *)&v196, &v199, v89, v81);
    v178 = v90;
    if ( !v199.Length )
    {
      if ( v90 )
        MicrosoftTelemetryAssertTriggeredMsgKM("!moreComponentsLeft");
      v173 = *((_QWORD *)v18 + 8);
      if ( v173 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v173 + 48LL))(v173) )
        MicrosoftTelemetryAssertTriggeredMsgKM("!volumeRootNode->HasMappingPayload()");
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000225LL,
        a4,
        (struct UnionFs::StackEventTracer *)0x33100140794LL,
        (unsigned __int64)"UnionFs::UfsPathTable::Delete",
        "ORIGIN: Payload not found for root.",
        v177);
      if ( v87 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v87);
      while ( 1 )
      {
        v174 = P[0];
        if ( P[0] == P )
          break;
        v175 = (_QWORD *)*((_QWORD *)P[0] + 1);
        v176 = *(_QWORD *)P[0];
        *v175 = *(_QWORD *)P[0];
        *(_QWORD *)(v176 + 8) = v175;
        ExFreePoolWithTag(v174, 0);
      }
      goto LABEL_86;
    }
    String1.Buffer = 0;
    *(_QWORD *)&String1.Length = &v199;
    Node = UnionFs::UfsPathTree::FindNode(v88, (const struct UnionFs::UFS_COMPARE_KEY *)&String1);
    v93 = 0;
    v94 = Node;
    if ( !Node )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000225LL,
        a4,
        (struct UnionFs::StackEventTracer *)0x3320014079FLL,
        (unsigned __int64)"UnionFs::UfsPathTable::Delete",
        "ORIGIN: Node not found in lookup.",
        v177);
      if ( v87 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v87);
      while ( 1 )
      {
        v170 = P[0];
        if ( P[0] == P )
          break;
        v171 = (_QWORD *)*((_QWORD *)P[0] + 1);
        v172 = *(_QWORD *)P[0];
        *v171 = *(_QWORD *)P[0];
        *(_QWORD *)(v172 + 8) = v171;
        ExFreePoolWithTag(v170, 0);
      }
      goto LABEL_86;
    }
    if ( *(_QWORD *)v189 )
    {
      if ( (*((_DWORD *)Node + 6) & 1) != 0 || !*((_QWORD *)Node + 18) )
      {
        v192 = *(struct UnionFs::UfsPathTierNode **)v189;
        v182 = 1;
      }
      *(_QWORD *)v189 = 0;
    }
    if ( v182 )
    {
      v193 = (const char *)Node;
      v182 = 0;
    }
    if ( !v178 )
      break;
    if ( !*((_QWORD *)Node + 8) && !*((_QWORD *)Node + 6) )
    {
      if ( (unsigned int)dword_14009E178 > 2 )
      {
        v106 = &v199;
        v184 = 2086;
        if ( !v199.Buffer )
          v106 = (struct _UNICODE_STRING *)&FsTlEmptyUnicodeString;
        v188 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
        v185 = (FsFltWil::Details *)v106;
        *(_QWORD *)v189 = "UnionFs::UfsPathTable::Delete";
        v195 = (UnionFs::UfsPathTable *)"Delete found a node with no payload and no descendant tree";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
          (unsigned int)"onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp",
          (unsigned int)word_140097B22,
          0,
          v92,
          (__int64)&v195,
          (__int64)v189,
          (__int64)&v188,
          (__int64)&v184,
          (__int64)&v185);
      }
      if ( (unsigned int)dword_14009E178 > 5
        && (qword_14009E188 & 0x400000000000LL) != 0
        && (qword_14009E190 & 0x400000000000LL) == qword_14009E190 )
      {
        v185 = (FsFltWil::Details *)1;
        v188 = (char *)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          qword_14009E190,
          (unsigned int)&byte_140097DEF,
          v93,
          (unsigned int)&v188,
          (__int64)&v185);
      }
      v107 = lambda_6f9dbe8414ad27d0719ae05117461c52_::operator()(&v203, v192, &v193);
      v184 = v107;
      if ( v107 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v107,
          a4,
          (struct UnionFs::StackEventTracer *)0x43B00140831LL,
          (unsigned __int64)"UnionFs::UfsPathTable::Delete",
          "PUSH: Deleting invalid node",
          v177);
        if ( v87 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v87);
        utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(P);
        if ( v191[1] )
          utl::_RefCountBase::_DecStrong(v191[1]);
        FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v220, v108);
        if ( v221 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v221 + 24LL))(v221);
        if ( v10 )
        {
          ExReleaseResourceLite(v10);
          KeLeaveCriticalRegion();
        }
        return v184;
      }
      v109 = (volatile signed __int32 *)*((_QWORD *)v18 + 7);
      v110 = v9 | 0x20;
      v111 = (UnionFs::UfsPathTree *)*((_QWORD *)v18 + 6);
      if ( v109 )
        _InterlockedIncrement(v109 + 2);
      if ( !UnionFs::UfsPathTree::IsEmpty(v111)
        || (v110 |= 0x40u,
            OwningUnion = (_QWORD *)UnionFs::UfsPathTierNode::GetOwningUnion(v18, v201),
            v112 = 0,
            *OwningUnion) )
      {
        v115 = v112;
      }
      else
      {
        v115 = 1;
      }
      if ( (v110 & 0x40) != 0 && v202 )
        utl::_RefCountBase::_DecStrong(v202);
      if ( v109 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v109);
      if ( v115 )
      {
        if ( (unsigned int)dword_14009E178 > 4
          && (qword_14009E188 & 0x10) != 0
          && (qword_14009E190 & 0x10) == qword_14009E190 )
        {
          v116 = (FsFltWil::Details **)v16[3];
          *(_QWORD *)v189 = "UnionFs::UfsPathTable::Delete";
          v117 = *v116;
          v188 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
          v193 = "Removing instance tier node: removed last path";
          v185 = v117;
          v184 = 2106;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (_DWORD)v117,
            (unsigned int)&word_14009778E,
            v112,
            v113,
            (__int64)&v193,
            (__int64)v189,
            (__int64)&v188,
            (__int64)&v184,
            (__int64)&v185);
        }
        utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::erase(v198, &v185, v16);
        while ( 1 )
        {
          v118 = (UnionFs::UfsPathTierNode **)P[0];
          if ( P[0] == P )
            break;
          v119 = (_QWORD *)*((_QWORD *)P[0] + 1);
          v120 = *(_QWORD *)P[0];
          *v119 = *(_QWORD *)P[0];
          *(_QWORD *)(v120 + 8) = v119;
          ExFreePoolWithTag(v118, 0);
        }
        v187 = 0;
      }
      else
      {
        v118 = (UnionFs::UfsPathTierNode **)P[0];
      }
      v121 = v190;
      while ( v118 != (UnionFs::UfsPathTierNode **)P )
      {
        UnionFs::UfsPathTierNode::RemoveDependentUnion(v118[2], v121);
        v118 = (UnionFs::UfsPathTierNode **)*v118;
      }
      goto LABEL_335;
    }
    if ( (unsigned __int8)lambda_1ce04d05065b34531c8e00b101e67e6e_::operator()(&v210, Node) )
    {
      v192 = v94;
      v182 = 1;
      v95 = (utl::_RefCountBase **)UnionFs::UfsPathTierNode::GetOwningUnion(v94, v217);
      v183 = *v95 != v191[0];
      if ( v218 )
        utl::_RefCountBase::_DecStrong(v218);
      goto LABEL_161;
    }
    if ( (*(_DWORD *)v195 & 1) != 0 && (v96 = (_DWORD *)*((_QWORD *)v94 + 6)) != 0 )
    {
      v97 = (volatile signed __int32 *)*((_QWORD *)v94 + 7);
      v9 |= 0x80u;
      v185 = (FsFltWil::Details *)v97;
      if ( v97 )
        _InterlockedIncrement(v97 + 2);
      if ( *v96 == 2 )
      {
        v179 = 1;
        goto LABEL_155;
      }
    }
    else
    {
      v97 = (volatile signed __int32 *)v185;
    }
    v179 = 0;
LABEL_155:
    if ( (v9 & 0x80u) != 0 )
    {
      v9 &= ~0x80u;
      if ( v97 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v97);
    }
    v98 = *(struct UnionFs::UfsPathTierNode **)v189;
    if ( v179 )
      v98 = v94;
    *(_QWORD *)v189 = v98;
LABEL_161:
    if ( *((_QWORD *)v94 + 8) && (*(_DWORD *)v195 & 2) == 0 )
    {
      v122 = "ORIGIN: Nested paths not enabled.";
      v123 = 0x3340014085CLL;
LABEL_216:
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000225LL,
        a4,
        (struct UnionFs::StackEventTracer *)v123,
        (unsigned __int64)"UnionFs::UfsPathTable::Delete",
        v122,
        v177);
      if ( v87 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v87);
      utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(P);
      goto LABEL_87;
    }
    if ( !*((_QWORD *)v94 + 6) )
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC0000225LL,
        a4,
        (struct UnionFs::StackEventTracer *)0x33500140874LL,
        (unsigned __int64)"UnionFs::UfsPathTable::Delete",
        "ORIGIN: Node not found.",
        v177);
      if ( v87 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v87);
      utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(P);
      if ( v191[1] )
        utl::_RefCountBase::_DecStrong(v191[1]);
      FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v220, v125);
      if ( v221 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v221 + 24LL))(v221);
      if ( v10 )
        FsFltWil::Details::ReleaseResource((FsFltWil::Details *)v10, v126);
      return 3221226021LL;
    }
    v99 = lambda_2f919d4ddf8d051d9a3e31225519f38b_::operator()(v214, v94, a4);
    LODWORD(v196) = v99;
    if ( v99 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v99,
        a4,
        (struct UnionFs::StackEventTracer *)0x4900014086BLL,
        (unsigned __int64)"UnionFs::UfsPathTable::Delete",
        "PUSH: Updating intermediateNodes",
        v177);
      if ( v87 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v87);
      utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(P);
      goto LABEL_287;
    }
    *(_QWORD *)&v196 = *((_QWORD *)v94 + 6);
    v100 = (volatile signed __int32 *)*((_QWORD *)v94 + 7);
    if ( v100 )
      _InterlockedIncrement(v100 + 2);
    v101 = (utl::_RefCountBase *)v87;
    v87 = v100;
    if ( v101 )
      utl::_RefCountBase::_DecStrong(v101);
    v102 = UnionFs::UfsPathTierNode::GetOwningUnion(v94, v201);
    v103 = *(utl::_RefCountBase **)v102;
    v104 = *(utl::_RefCountBase **)(v102 + 8);
    *(_QWORD *)v102 = 0;
    *(_QWORD *)(v102 + 8) = 0;
    v191[0] = v103;
    v105 = v191[1];
    v191[1] = v104;
    if ( v105 )
      utl::_RefCountBase::_DecStrong(v105);
    v88 = (UnionFs::UfsPathTree *)v196;
    if ( v202 )
      utl::_RefCountBase::_DecStrong(v202);
  }
  v127 = v9 | 2;
  FsFltWil::AcquirePushLockShared(&v185, (char *)Node + 128);
  *(_QWORD *)v189 = *((_QWORD *)v94 + 10);
  v128 = (volatile signed __int32 *)*((_QWORD *)v94 + 11);
  v188 = (char *)v128;
  if ( v128 )
    _InterlockedIncrement(v128 + 2);
  if ( v185 )
  {
    FsFltWil::Details::ReleasePushLockShared(v185, 0);
    v128 = (volatile signed __int32 *)v188;
  }
  if ( *(utl::_RefCountBase **)v189 != v191[0] || (v180 = 1, !v184) )
    v180 = 0;
  v129 = v127 & 0xFD;
  if ( v128 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v128);
  if ( !v180 )
  {
    if ( (a5 & 0x10) != 0 )
    {
      if ( !*((_QWORD *)v94 + 8) && !*((_QWORD *)v94 + 6) )
      {
        v133 = lambda_6f9dbe8414ad27d0719ae05117461c52_::operator()(&v203, v192, &v193);
        if ( v133 < 0 )
        {
          UnionFs::ProcessTraceStatusPushLocation(
            (UnionFs *)(unsigned int)v133,
            a4,
            (struct UnionFs::StackEventTracer *)0x5DB001407D8LL,
            (unsigned __int64)"UnionFs::UfsPathTable::Delete",
            "PUSH: Pruning empty node",
            v177);
          if ( v87 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v87);
          while ( 1 )
          {
            v135 = P[0];
            if ( P[0] == P )
              break;
            v136 = (_QWORD *)*((_QWORD *)P[0] + 1);
            v137 = *(_QWORD *)P[0];
            *v136 = *(_QWORD *)P[0];
            *(_QWORD *)(v137 + 8) = v136;
            ExFreePoolWithTag(v135, 0);
          }
          v187 = 0;
          if ( v191[1] )
            utl::_RefCountBase::_DecStrong(v191[1]);
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v220, v134);
          if ( v221 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v221 + 24LL))(v221);
          if ( v10 )
          {
            ExReleaseResourceLite(v10);
            KeLeaveCriticalRegion();
          }
          return (unsigned int)v133;
        }
      }
      if ( v87 )
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v87);
      while ( 1 )
      {
        v138 = P[0];
        if ( P[0] == P )
          break;
        v139 = (_QWORD *)*((_QWORD *)P[0] + 1);
        v140 = *(_QWORD *)P[0];
        *v139 = *(_QWORD *)P[0];
        *(_QWORD *)(v140 + 8) = v139;
        ExFreePoolWithTag(v138, 0);
      }
      v51 = 0;
      v187 = 0;
      goto LABEL_338;
    }
    if ( v184 )
    {
      v141 = (volatile signed __int32 *)v190;
    }
    else
    {
      if ( !*((_QWORD *)v94 + 8) )
      {
        v141 = (volatile signed __int32 *)v190;
LABEL_273:
        v181 = 0;
LABEL_276:
        if ( (v129 & 4) != 0 )
        {
          v129 &= ~4u;
          if ( v141 )
            utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v141);
        }
        if ( !v181 )
        {
          v122 = "ORIGIN: Found node does not have payload.";
          v123 = 0x33300140819LL;
          goto LABEL_216;
        }
        if ( *((_QWORD *)v94 + 6) )
        {
          if ( v184 )
          {
            v157 = lambda_6f9dbe8414ad27d0719ae05117461c52_::operator()(&v203, v192, &v193);
            LODWORD(v196) = v157;
            if ( v157 < 0 )
            {
              UnionFs::ProcessTraceStatusPushLocation(
                (UnionFs *)(unsigned int)v157,
                a4,
                (struct UnionFs::StackEventTracer *)0x408001407FFLL,
                (unsigned __int64)"UnionFs::UfsPathTable::Delete",
                "PUSH: Pruning from inner node",
                v177);
              if ( v87 )
                utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v87);
              while ( 1 )
              {
                v158 = P[0];
                if ( P[0] == P )
                  break;
                v159 = (_QWORD *)*((_QWORD *)P[0] + 1);
                v160 = *(_QWORD *)P[0];
                *v159 = *(_QWORD *)P[0];
                *(_QWORD *)(v160 + 8) = v159;
                ExFreePoolWithTag(v158, 0);
              }
              goto LABEL_286;
            }
          }
          else
          {
            v146 = (UnionFs::UfsPathTierNode *)*((_QWORD *)v94 + 18);
            if ( v146 )
              UnionFs::UfsPathTierNode::ClearPayload(v146);
            v147 = (utl::_RefCountBase *)*((_QWORD *)v94 + 9);
            *((_QWORD *)v94 + 8) = 0;
            *((_QWORD *)v94 + 9) = 0;
            if ( v147 )
              utl::_RefCountBase::_DecStrong(v147);
          }
        }
        else
        {
          v142 = lambda_6f9dbe8414ad27d0719ae05117461c52_::operator()(&v203, v192, &v193);
          LODWORD(v196) = v142;
          if ( v142 < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v142,
              a4,
              (struct UnionFs::StackEventTracer *)0x407001407F0LL,
              (unsigned __int64)"UnionFs::UfsPathTable::Delete",
              "PUSH: Pruning from leaf",
              v177);
            if ( v87 )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v87);
            while ( 1 )
            {
              v143 = P[0];
              if ( P[0] == P )
                break;
              v144 = (_QWORD *)*((_QWORD *)P[0] + 1);
              v145 = *(_QWORD *)P[0];
              *v144 = *(_QWORD *)P[0];
              *(_QWORD *)(v145 + 8) = v144;
              ExFreePoolWithTag(v143, 0);
            }
LABEL_286:
            v187 = 0;
LABEL_287:
            if ( v191[1] )
              utl::_RefCountBase::_DecStrong(v191[1]);
            FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v220, v124);
            if ( v221 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v221 + 24LL))(v221);
            if ( v10 )
            {
              ExReleaseResourceLite(v10);
              KeLeaveCriticalRegion();
            }
            return (unsigned int)v196;
          }
        }
        v148 = (volatile signed __int32 *)*((_QWORD *)v18 + 7);
        v149 = v129 | 8;
        v150 = (UnionFs::UfsPathTree *)*((_QWORD *)v18 + 6);
        if ( v148 )
          _InterlockedIncrement(v148 + 2);
        if ( UnionFs::UfsPathTree::IsEmpty(v150) )
        {
          v149 |= 0x10u;
          FsFltWil::AcquirePushLockShared(&v185, (char *)v18 + 128);
          v154 = (volatile signed __int32 *)*((_QWORD *)v18 + 11);
          v151 = 0;
          v155 = (const char *)*((_QWORD *)v18 + 10);
          v188 = (char *)v155;
          if ( v154 )
            _InterlockedIncrement(v154 + 2);
          if ( v185 )
          {
            FsFltWil::Details::ReleasePushLockShared(v185, v153);
            v155 = v188;
            v151 = 0;
          }
          if ( !v155 )
          {
            v156 = 1;
            goto LABEL_315;
          }
        }
        else
        {
          v154 = (volatile signed __int32 *)v190;
        }
        v156 = v151;
LABEL_315:
        if ( (v149 & 0x10) != 0 && v154 )
        {
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v154);
          v151 = 0;
        }
        if ( v148 )
        {
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v148);
          v151 = 0;
        }
        if ( v156 )
        {
          if ( (unsigned int)dword_14009E178 > 4
            && (qword_14009E188 & 0x10) != 0
            && (qword_14009E190 & 0x10) == qword_14009E190 )
          {
            v161 = (FsFltWil::Details **)v16[3];
            *(_QWORD *)v189 = "UnionFs::UfsPathTable::Delete";
            v162 = *v161;
            v188 = "onecore\\base\\fs\\unionfs\\sys\\pathtable.cpp";
            v193 = "Removing instance tier node: removed last path";
            v185 = v162;
            LODWORD(v196) = 2058;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              (_DWORD)v162,
              (unsigned int)&word_1400977D6,
              v151,
              v152,
              (__int64)&v193,
              (__int64)v189,
              (__int64)&v188,
              (__int64)&v196,
              (__int64)&v185);
            v151 = 0;
          }
          v163 = (_QWORD *)v16[1];
          v164 = (_QWORD *)*v16;
          *v163 = *v16;
          v164[1] = v163;
          v165 = (void *)v16[3];
          v16[3] = v151;
          if ( v165 )
            FltReleaseContext(v165);
          utl::unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>::~unique_ptr<UnionFs::UfsPathTierNode,utl::default_delete<UnionFs::UfsPathTierNode>>(v16 + 2);
          ExFreePoolWithTag(v16, 0);
          --v198[2];
          while ( 1 )
          {
            v166 = (UnionFs::UfsPathTierNode **)P[0];
            if ( P[0] == P )
              break;
            v167 = (_QWORD *)*((_QWORD *)P[0] + 1);
            v168 = *(_QWORD *)P[0];
            *v167 = *(_QWORD *)P[0];
            *(_QWORD *)(v168 + 8) = v167;
            ExFreePoolWithTag(v166, 0);
          }
          v187 = 0;
        }
        else
        {
          v166 = (UnionFs::UfsPathTierNode **)P[0];
        }
        v169 = v190;
        while ( v166 != (UnionFs::UfsPathTierNode **)P )
        {
          UnionFs::UfsPathTierNode::RemoveDependentUnion(v166[2], v169);
          v166 = (UnionFs::UfsPathTierNode **)*v166;
        }
LABEL_335:
        if ( v87 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v87);
        utl::list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>::~list<UnionFs::UfsPathTierNode *,utl::allocator<UnionFs::UfsPathTierNode *>>(P);
        goto LABEL_338;
      }
      v129 |= 4u;
      FsFltWil::AcquirePushLockShared(&v185, (char *)v94 + 128);
      *(_QWORD *)v189 = *((_QWORD *)v94 + 10);
      v141 = (volatile signed __int32 *)*((_QWORD *)v94 + 11);
      v188 = (char *)v141;
      if ( v141 )
        _InterlockedIncrement(v141 + 2);
      if ( v185 )
      {
        FsFltWil::Details::ReleasePushLockShared(v185, 0);
        v141 = (volatile signed __int32 *)v188;
      }
      if ( *(utl::_RefCountBase **)v189 != v191[0] )
        goto LABEL_273;
    }
    v181 = 1;
    goto LABEL_276;
  }
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)0xC000000DLL,
    a4,
    (struct UnionFs::StackEventTracer *)0x48C001407CDLL,
    (unsigned __int64)"UnionFs::UfsPathTable::Delete",
    "ORIGIN: Recursive delete on non-root node",
    v177);
  if ( v87 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v87);
  while ( 1 )
  {
    v130 = P[0];
    if ( P[0] == P )
      break;
    v131 = (_QWORD *)*((_QWORD *)P[0] + 1);
    v132 = *(_QWORD *)P[0];
    *v131 = *(_QWORD *)P[0];
    *(_QWORD *)(v132 + 8) = v131;
    ExFreePoolWithTag(v130, 0);
  }
LABEL_40:
  v187 = 0;
LABEL_41:
  if ( v191[1] )
    utl::_RefCountBase::_DecStrong(v191[1]);
  FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)v220, v28);
  if ( v221 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v221 + 24LL))(v221);
  if ( v10 )
  {
    ExReleaseResourceLite(v10);
    KeLeaveCriticalRegion();
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140046510  mov     [rsp-8+arg_8], rbx
0x140046515  push    rbp
0x140046516  push    rsi
0x140046517  push    rdi
0x140046518  push    r12
0x14004651a  push    r13
0x14004651c  push    r14
0x14004651e  push    r15
0x140046520  lea     rbp, [rsp-1A0h]
0x140046528  sub     rsp, 2A0h
0x14004652f  mov     rax, cs:__security_cookie
0x140046536  xor     rax, rsp
0x140046539  mov     [rbp+1D0h+var_38], rax
0x140046540  mov     rax, [rbp+1D0h+arg_28]
0x140046547  xor     edi, edi
0x140046549  mov     [rbp+1D0h+var_200], rax
0x14004654d  mov     r12, r9
0x140046550  mov     eax, [rbp+1D0h+arg_20]
0x140046556  mov     rsi, rdx
0x140046559  mov     [rsp+2D0h+var_258], r8
0x14004655e  mov     r15, rcx
0x140046561  lea     r14d, [rdi+1]
0x140046565  mov     [rbp+1D0h+var_218], rcx
0x140046569  mov     dword ptr [rbp+1D0h+var_210], edi
0x14004656c  mov     r13d, edi
0x14004656f  mov     ebx, edi
0x140046571  test    r14b, al
0x140046574  jnz     short loc_140046587
0x140046576  lea     rdx, [rcx+20h]
0x14004657a  lea     rcx, [rbp+1D0h+var_248]
0x14004657e  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x140046583  mov     rbx, [rbp+1D0h+var_248]
0x140046587  mov     rdx, [r15+88h]; RunRefCacheAware
0x14004658e  lea     r9, [rbp+1D0h+var_138]
0x140046595  mov     r8b, r14b
0x140046598  mov     [rbp+1D0h+var_C8], rdi
0x14004659f  lea     rcx, [rbp+1D0h+var_C0]; void *
0x1400465a6  call    ?AcquireRundownReference@FsFltWil@@YA?AV?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@PEAU_EX_RUNDOWN_REF_CACHE_AWARE@@_NV?$function@$$A6AX_N@Z@wistd@@@Z; FsFltWil::AcquireRundownReference(_EX_RUNDOWN_REF_CACHE_AWARE *,bool,wistd::function<void (bool)>)
0x1400465ab  cmp     [rbp+1D0h+var_C0], rdi
0x1400465b2  jnz     short loc_14004662B
0x1400465b4  lea     rax, aOriginTableAlr; "ORIGIN: Table already run down"
0x1400465bb  mov     esi, 0C0ED000Ah
0x1400465c0  mov     ecx, esi; this
0x1400465c2  mov     [rsp+2D0h+var_2B0], rax; char *
0x1400465c7  lea     r9, aUnionfsUfspath_27; "UnionFs::UfsPathTable::Delete"
0x1400465ce  mov     r8, 1BB0014062Ch; struct UnionFs::StackEventTracer *
0x1400465d8  mov     rdx, r12; int
0x1400465db  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400465e0  lea     rcx, [rbp+1D0h+var_C0]; this
0x1400465e7  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x1400465ec  mov     rcx, [rbp+1D0h+var_40]
0x1400465f3  test    rcx, rcx
0x1400465f6  jz      short loc_140046604
0x1400465f8  mov     rax, [rcx]
0x1400465fb  mov     rax, [rax+18h]
0x1400465ff  call    _guard_dispatch_icall
0x140046604  test    rbx, rbx
0x140046607  jz      short loc_140046624
0x140046609  mov     rcx, rbx; Resource
0x14004660c  call    cs:__imp_ExReleaseResourceLite
0x140046613  nop     dword ptr [rax+rax+00h]
0x140046618  call    cs:__imp_KeLeaveCriticalRegion
0x14004661f  nop     dword ptr [rax+rax+00h]
0x140046624  mov     eax, esi
0x140046626  jmp     loc_140047DA9
0x14004662b  lea     rax, [r15+8]
0x14004662f  mov     [rbp+1D0h+var_220], rdi
0x140046633  mov     rdi, [rax]
0x140046636  mov     [rbp+1D0h+var_1F8], rax
0x14004663a  cmp     rdi, rax
0x14004663d  jz      loc_140047D36
0x140046643  mov     rax, [rdi+18h]
0x140046647  cmp     [rax], rsi
0x14004664a  jz      short loc_140046655
0x14004664c  mov     rdi, [rdi]
0x14004664f  lea     rax, [r15+8]
0x140046653  jmp     short loc_14004663A
0x140046655  lea     rax, [rdi+10h]
0x140046659  xor     edx, edx
0x14004665b  mov     [rbp+1D0h+var_220], rax
0x14004665f  test    rax, rax
0x140046662  jz      loc_140047D36
0x140046668  mov     esi, [rbp+1D0h+arg_20]
0x14004666e  lea     rcx, [rsp+2D0h+P]
0x140046673  mov     [rsp+2D0h+P], rcx
0x140046678  xorps   xmm0, xmm0
0x14004667b  mov     [rbp+1D0h+var_230], rdx
0x14004667f  lea     rcx, [rsp+2D0h+P]
0x140046684  mov     [rsp+2D0h+var_268], rcx
0x140046689  xor     r8d, r8d; CaseInSensitive
0x14004668c  mov     [rsp+2D0h+var_27E], dl
0x140046690  lea     rcx, [rsp+2D0h+P]
0x140046695  mov     [rbp+1D0h+var_168], rcx
0x140046699  lea     rcx, [rbp+1D0h+var_230]
0x14004669d  mov     [rbp+1D0h+var_160], rcx
0x1400466a1  mov     rcx, [rbp+1D0h+var_200]
0x1400466a5  mov     [rbp+1D0h+var_248], rcx
0x1400466a9  mov     [rbp+1D0h+var_150], rcx
0x1400466b0  lea     rcx, [rbp+1D0h+var_200]
0x1400466b4  movdqu  xmmword ptr [rbp+1D0h+var_240], xmm0
0x1400466b9  mov     [rsp+2D0h+var_260], rdx
0x1400466be  lea     rdx, ?g_RootName@UnionFs@@3U_UNICODE_STRING@@B; String2
0x1400466c5  mov     [rbp+1D0h+var_180], rcx
0x1400466c9  lea     rcx, [rbp+1D0h+var_240]
0x1400466cd  mov     [rbp+1D0h+var_178], rcx
0x1400466d1  lea     rcx, [rbp+1D0h+String1]; String1
0x1400466d5  mov     [rbp+1D0h+var_170], r15
0x1400466d9  mov     r15, [rax]
0x1400466dc  mov     rax, [rsp+2D0h+var_258]
0x1400466e1  mov     [rbp+1D0h+var_158], esi
0x1400466e4  mov     [rbp+1D0h+var_188], esi
0x1400466e7  movups  xmm0, xmmword ptr [rax+28h]
0x1400466eb  movdqu  xmmword ptr [rbp+1D0h+String1.Length], xmm0
0x1400466f0  call    cs:__imp_RtlEqualUnicodeString
0x1400466f7  nop     dword ptr [rax+rax+00h]
0x1400466fc  test    al, al
0x1400466fe  jz      loc_140046B46
0x140046704  test    sil, 2
0x140046708  jnz     short loc_140046784
0x14004670a  lea     rax, aOriginNonRecur; "ORIGIN: Non-recursive delete of volume "...
0x140046711  mov     esi, 0C00000E5h
0x140046716  mov     ecx, esi; this
0x140046718  mov     [rsp+2D0h+var_2B0], rax; char *
0x14004671d  lea     r9, aUnionfsUfspath_27; "UnionFs::UfsPathTable::Delete"
0x140046724  mov     r8, 481001406B0h; struct UnionFs::StackEventTracer *
0x14004672e  mov     rdx, r12; int
0x140046731  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140046736  mov     r8, [rsp+2D0h+P]
0x14004673b  lea     rax, [rsp+2D0h+P]
0x140046740  cmp     r8, rax
0x140046743  jz      short loc_140046766
0x140046745  mov     rcx, [r8+8]
0x140046749  xor     edx, edx; Tag
0x14004674b  mov     rax, [r8]
0x14004674e  mov     [rcx], rax
0x140046751  mov     [rax+8], rcx
0x140046755  mov     rcx, r8; P
0x140046758  call    cs:__imp_ExFreePoolWithTag
0x14004675f  nop     dword ptr [rax+rax+00h]
0x140046764  jmp     short loc_140046736
0x140046766  mov     rcx, [rbp+1D0h+var_240+8]; this
0x14004676a  xor     edi, edi
0x14004676c  mov     [rsp+2D0h+var_260], rdi
0x140046771  test    rcx, rcx
0x140046774  jz      loc_1400465E0
0x14004677a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004677f  jmp     loc_1400465E0
0x140046784  lea     r14, [r15+80h]
0x14004678b  mov     rdx, r14
0x14004678e  lea     rcx, [rbp+1D0h+var_248]
0x140046792  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x140046797  mov     rsi, [r15+58h]
0x14004679b  mov     r13, [r15+50h]
0x14004679f  test    rsi, rsi
0x1400467a2  jz      short loc_1400467A8
0x1400467a4  lock inc dword ptr [rsi+8]
0x1400467a8  mov     rcx, [rbp+1D0h+var_248]; this
0x1400467ac  test    rcx, rcx
0x1400467af  jz      short loc_1400467B6
0x1400467b1  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x1400467b6  test    r13, r13
0x1400467b9  jnz     short loc_1400467C7
0x1400467bb  lea     rcx, aRecursiveDelet; "Recursive delete at table root that is "...
0x1400467c2  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400467c7  test    rsi, rsi
0x1400467ca  jz      short loc_1400467D4
0x1400467cc  mov     rcx, rsi; this
0x1400467cf  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400467d4  mov     rdx, r14
0x1400467d7  lea     rcx, [rbp+1D0h+var_248]
0x1400467db  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x1400467e0  mov     rsi, [r15+58h]
0x1400467e4  mov     r13, [r15+50h]
0x1400467e8  test    rsi, rsi
0x1400467eb  jz      short loc_1400467F1
0x1400467ed  lock inc dword ptr [rsi+8]
0x1400467f1  mov     rcx, [rbp+1D0h+var_248]; this
0x1400467f5  test    rcx, rcx
0x1400467f8  jz      short loc_1400467FF
0x1400467fa  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x1400467ff  test    rsi, rsi
0x140046802  jz      short loc_14004680C
0x140046804  mov     rcx, rsi; this
0x140046807  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004680c  test    r13, r13
0x14004680f  jnz     loc_1400468D2
0x140046815  lea     rax, aOriginRecursiv_1; "ORIGIN: Recursive delete requested for "...
0x14004681c  mov     r8, 491001406BBh; struct UnionFs::StackEventTracer *
0x140046826  lea     r9, aUnionfsUfspath_27; "UnionFs::UfsPathTable::Delete"
0x14004682d  mov     [rsp+2D0h+var_2B0], rax; char *
0x140046832  mov     rdx, r12; int
0x140046835  mov     ecx, 0C000000Dh; this
0x14004683a  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004683f  mov     r8, [rsp+2D0h+P]
0x140046844  lea     rax, [rsp+2D0h+P]
0x140046849  cmp     r8, rax
0x14004684c  jz      short loc_14004686F
0x14004684e  mov     rcx, [r8+8]
0x140046852  xor     edx, edx; Tag
0x140046854  mov     rax, [r8]
0x140046857  mov     [rcx], rax
0x14004685a  mov     [rax+8], rcx
0x14004685e  mov     rcx, r8; P
0x140046861  call    cs:__imp_ExFreePoolWithTag
0x140046868  nop     dword ptr [rax+rax+00h]
0x14004686d  jmp     short loc_14004683F
0x14004686f  xor     edi, edi
0x140046871  mov     [rsp+2D0h+var_260], rdi
0x140046876  mov     rcx, [rbp+1D0h+var_240+8]; this
0x14004687a  test    rcx, rcx
0x14004687d  jz      short loc_140046884
0x14004687f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140046884  lea     rcx, [rbp+1D0h+var_C0]; this
0x14004688b  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140046890  mov     rcx, [rbp+1D0h+var_40]
0x140046897  test    rcx, rcx
0x14004689a  jz      short loc_1400468A8
0x14004689c  mov     rax, [rcx]
0x14004689f  mov     rax, [rax+18h]
0x1400468a3  call    _guard_dispatch_icall
0x1400468a8  test    rbx, rbx
0x1400468ab  jz      short loc_1400468C8
0x1400468ad  mov     rcx, rbx; Resource
0x1400468b0  call    cs:__imp_ExReleaseResourceLite
0x1400468b7  nop     dword ptr [rax+rax+00h]
0x1400468bc  call    cs:__imp_KeLeaveCriticalRegion
0x1400468c3  nop     dword ptr [rax+rax+00h]
0x1400468c8  mov     eax, 0C000000Dh
0x1400468cd  jmp     loc_140047DA9
0x1400468d2  mov     rdx, r14
0x1400468d5  lea     rcx, [rbp+1D0h+var_248]
0x1400468d9  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x1400468de  mov     rsi, [r15+58h]
0x1400468e2  xor     r13d, r13d
0x1400468e5  mov     r14, [r15+50h]
0x1400468e9  test    rsi, rsi
0x1400468ec  jz      short loc_1400468F2
0x1400468ee  lock inc dword ptr [rsi+8]
0x1400468f2  mov     rcx, [rbp+1D0h+var_248]; this
0x1400468f6  test    rcx, rcx
0x1400468f9  jz      short loc_140046900
0x1400468fb  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x140046900  cmp     r14, [rbp+1D0h+var_200]
0x140046904  setnz   r14b
0x140046908  test    rsi, rsi
0x14004690b  jz      short loc_140046915
0x14004690d  mov     rcx, rsi; this
0x140046910  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140046915  test    r14b, r14b
0x140046918  jz      short loc_14004697E
0x14004691a  lea     rax, aOriginRootMapp; "ORIGIN: Root mapping doesn't belong to "...
0x140046921  mov     r8, 496001406C3h; struct UnionFs::StackEventTracer *
0x14004692b  lea     r9, aUnionfsUfspath_27; "UnionFs::UfsPathTable::Delete"
0x140046932  mov     [rsp+2D0h+var_2B0], rax; char *
0x140046937  mov     rdx, r12; int
0x14004693a  mov     ecx, 0C000000Dh; this
0x14004693f  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140046944  mov     r8, [rsp+2D0h+P]
0x140046949  lea     rax, [rsp+2D0h+P]
0x14004694e  cmp     r8, rax
0x140046951  jz      short loc_140046974
0x140046953  mov     rcx, [r8+8]
0x140046957  xor     edx, edx; Tag
0x140046959  mov     rax, [r8]
0x14004695c  mov     [rcx], rax
0x14004695f  mov     [rax+8], rcx
0x140046963  mov     rcx, r8; P
0x140046966  call    cs:__imp_ExFreePoolWithTag
0x14004696d  nop     dword ptr [rax+rax+00h]
0x140046972  jmp     short loc_140046944
0x140046974  mov     [rsp+2D0h+var_260], r13
0x140046979  jmp     loc_140046876
0x14004697e  cmp     [r15+78h], r13
0x140046982  ja      loc_140046ACD
0x140046988  mov     rax, [rbp+1D0h+var_220]
0x14004698c  mov     rsi, [rax]
0x14004698f  mov     rcx, [rsi+90h]; this
0x140046996  test    rcx, rcx
0x140046999  jz      short loc_1400469A0
0x14004699b  call    ?ClearPayload@UfsPathTierNode@UnionFs@@QEAAXXZ; UnionFs::UfsPathTierNode::ClearPayload(void)
0x1400469a0  mov     rcx, [rsi+48h]; this
0x1400469a4  mov     [rsi+40h], r13
0x1400469a8  mov     [rsi+48h], r13
0x1400469ac  test    rcx, rcx
0x1400469af  jz      short loc_1400469B6
0x1400469b1  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400469b6  mov     rcx, rsi; this
0x1400469b9  call    ?ClearOwningUnion@UfsPathTierNode@UnionFs@@AEAAXXZ; UnionFs::UfsPathTierNode::ClearOwningUnion(void)
0x1400469be  mov     rax, [rbp+1D0h+var_220]
0x1400469c2  mov     rcx, [rax]
0x1400469c5  cmp     [rcx+30h], r13
0x1400469c9  jz      short loc_1400469E4
0x1400469cb  mov     rax, [rcx+38h]
0x1400469cf  mov     [rcx+30h], r13
0x1400469d3  mov     [rcx+38h], r13
0x1400469d7  test    rax, rax
0x1400469da  jz      short loc_1400469E4
0x1400469dc  mov     rcx, rax; this
0x1400469df  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400469e4  mov     eax, cs:dword_14009E178
  ... truncated ...
```
