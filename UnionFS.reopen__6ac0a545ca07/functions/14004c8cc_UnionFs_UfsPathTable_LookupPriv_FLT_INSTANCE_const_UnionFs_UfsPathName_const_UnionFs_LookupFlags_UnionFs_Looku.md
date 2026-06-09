# UnionFs::UfsPathTable::LookupPriv(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::LookupFlags,UnionFs::LookupResults &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,wistd::function<long (UnionFs::UfsInstanceTierNode const &,UnionFs::UfsPathTierNode const &,bool *,utl::pair<wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &,wistd::unique_ptr<_ERESOURCE,wil::function_deleter<void (*)(_ERESOURCE *),&FsFltWil::Details::ReleaseResource(_ERESOURCE *)>> &> &,UnionFs::StackEventTracer &)> *)

- ea: `0x14004c8cc`
- end: `0x14004deb9`
- name: `?LookupPriv@UfsPathTable@UnionFs@@AEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4LookupFlags@2@AEAULookupResults@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEAV?$function@$$A6AJAEBVUfsInstanceTierNode@UnionFs@@AEBVUfsPathTierNode@2@PEA_NAEAU?$pair@AEAV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAV12@@utl@@AEAVStackEventTracer@2@@Z@wistd@@@Z`
- size: `5613`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, struct UnionFs::StackEventTracer *, int, __int64)`
- caller_count: `2`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14004c70c`
- `0x14004dec0`

## callees

- `0x1400069b4`
- `0x14000f81c`
- `0x14003dc14`
- `0x14004420c`
- `0x140044334`
- `0x1400444f4`
- `0x140044d2c`
- `0x140044f90`
- `0x140047f5c`
- `0x14004c678`
- `0x14004c8cc`
- `0x14004f62c`
- `0x14004f754`
- `0x140056c7c`
- `0x140079404`
- `0x140079d44`
- `0x140079dd4`
- `0x140079e1c`
- `0x14007a0c0`
- `0x14007a114`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bbd0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14004cc2b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004d4fb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004d589`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004db21`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004cc2b`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004d4fb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004d589`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004db21`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c972`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ca76`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cb76`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ccd0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ceb6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cede`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d0f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d11e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d202`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d304`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d360`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d3b9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d4a6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d4cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d620`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d6f4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d7cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d7f2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d869`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d960`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d9ab`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004da0a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004da36`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004da85`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004dc0a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004dc74`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ddea`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004de68`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004c972`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ca76`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cb76`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ccd0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ceb6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004cede`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d0f6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d11e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d202`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d304`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d360`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d3b9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d4a6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d4cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d620`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d6f4`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d7cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d7f2`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d869`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d960`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004d9ab`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004da0a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004da36`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004da85`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004dc0a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004dc74`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004ddea`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004de68`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c97e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004ca82`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cb82`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004ccdc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cec2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004ceea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d102`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d12a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d20e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d310`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d36c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d3c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d4b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d4d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d62c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d700`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d7d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d7fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d875`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d96c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d9b7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004da16`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004da42`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004da91`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004dc16`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004dc80`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004ddf6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004de74`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004c97e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004ca82`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cb82`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004ccdc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004cec2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004ceea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d102`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d12a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d20e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d310`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d36c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d3c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d4b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d4d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d62c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d700`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d7d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d7fe`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d875`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d96c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d9b7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004da16`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004da42`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004da91`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004dc16`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004dc80`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004ddf6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004de74`

## string_xrefs

- `0x14004dd96`: `!moreComponentsLeft`
- `0x14004ca1c`: `PUSH: Allocating FoundPath`
- `0x14004ca2d`: `UnionFs::UfsPathTable::LookupPriv`
- `0x14004d5db`: `UnionFs::UfsPathTable::LookupPriv`
- `0x14004d911`: `UnionFs::UfsPathTable::LookupPriv`
- `0x14004d9d7`: `UnionFs::UfsPathTable::LookupPriv`
- `0x14004db90`: `UnionFs::UfsPathTable::LookupPriv`
- `0x14004caf4`: `PUSH: Appending volume path to FoundPath`
- `0x14004d544`: `If nested paths not enabled, tree should be empty.`
- `0x14004d599`: `RtlEqualUnicodeString(volumeRootNode->GetPathComponent(), &g_RootName, false)`
- `0x14004d5c5`: `PUSH: Appending volume root to FoundPath`
- `0x14004db7a`: `PUSH: Appending volume root to FoundPath`
- `0x14004d80f`: `PUSH: LookupCallback in PathTable.`
- `0x14004d9d0`: `PUSH: LookupCallback in PathTable.`
- `0x14004d90a`: `PUSH: Appending path component to FoundPath`
- `0x14004db31`: `RtlEqualUnicodeString(foundPayloadNode->GetPathComponent(), &g_RootName, false)`
- `0x14004db4d`: `SearchPath.AsUnicodeString().Length > sizeof(WCHAR)`

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
0x14004c8cc  mov     [rsp-8+arg_8], rbx
0x14004c8d1  push    rbp
0x14004c8d2  push    rsi
0x14004c8d3  push    rdi
0x14004c8d4  push    r12
0x14004c8d6  push    r13
0x14004c8d8  push    r14
0x14004c8da  push    r15
0x14004c8dc  lea     rbp, [rsp-210h]
0x14004c8e4  sub     rsp, 310h
0x14004c8eb  mov     rax, cs:__security_cookie
0x14004c8f2  xor     rax, rsp
0x14004c8f5  mov     [rbp+240h+var_38], rax
0x14004c8fc  mov     esi, [rbp+240h+arg_30]
0x14004c902  xor     r12d, r12d
0x14004c905  mov     rdi, [rbp+240h+arg_20]
0x14004c90c  and     esi, 1
0x14004c90f  mov     r13, [rbp+240h+arg_28]
0x14004c916  mov     r15, r8
0x14004c919  mov     rax, [rbp+240h+arg_38]
0x14004c920  mov     rbx, rdx
0x14004c923  mov     [rsp+340h+var_2EC], r9d
0x14004c928  mov     r14, rcx
0x14004c92b  mov     [rdi+4], r12d
0x14004c92f  mov     [rbp+240h+var_278], r8
0x14004c933  mov     [rbp+240h+var_298], rcx
0x14004c937  mov     [rsp+340h+var_2C8], r13
0x14004c93c  mov     [rbp+240h+var_2A0], rax
0x14004c940  mov     [rsp+340h+var_300], r12d
0x14004c945  mov     [rsp+340h+Resource], r12
0x14004c94a  mov     [rbp+240h+arg_30], esi
0x14004c950  jnz     short loc_14004C98A
0x14004c952  lea     rdx, [rcx+20h]
0x14004c956  lea     rcx, [rbp+240h+var_290]
0x14004c95a  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x14004c95f  mov     rcx, [rsp+340h+Resource]; Resource
0x14004c964  mov     rax, [rbp+240h+var_290]
0x14004c968  mov     [rsp+340h+Resource], rax
0x14004c96d  test    rcx, rcx
0x14004c970  jz      short loc_14004C98A
0x14004c972  call    cs:__imp_ExReleaseResourceLite
0x14004c979  nop     dword ptr [rax+rax+00h]
0x14004c97e  call    cs:__imp_KeLeaveCriticalRegion
0x14004c985  nop     dword ptr [rax+rax+00h]
0x14004c98a  mov     rdx, [r14+88h]; RunRefCacheAware
0x14004c991  lea     r9, [rbp+240h+var_1C0]
0x14004c998  mov     r8b, 1
0x14004c99b  mov     [rbp+240h+var_150], r12
0x14004c9a2  lea     rcx, [rbp+240h+var_148]; void *
0x14004c9a9  call    ?AcquireRundownReference@FsFltWil@@YA?AV?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@PEAU_EX_RUNDOWN_REF_CACHE_AWARE@@_NV?$function@$$A6AX_N@Z@wistd@@@Z; FsFltWil::AcquireRundownReference(_EX_RUNDOWN_REF_CACHE_AWARE *,bool,wistd::function<void (bool)>)
0x14004c9ae  cmp     [rbp+240h+var_148], r12
0x14004c9b5  jnz     short loc_14004C9C8
0x14004c9b7  lea     rcx, [rbp+240h+var_148]; this
0x14004c9be  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14004c9c3  jmp     loc_14004DE41
0x14004c9c8  lea     rcx, [r14+8]
0x14004c9cc  mov     rax, [rcx]
0x14004c9cf  cmp     rax, rcx
0x14004c9d2  jz      loc_14004DE32
0x14004c9d8  lea     r12, [rax+10h]
0x14004c9dc  mov     rdx, [r12+8]
0x14004c9e1  mov     [rbp+240h+var_2B0], r12
0x14004c9e5  cmp     [rdx], rbx
0x14004c9e8  jz      short loc_14004C9EF
0x14004c9ea  mov     rax, [rax]
0x14004c9ed  jmp     short loc_14004C9CF
0x14004c9ef  mov     eax, [rdi]
0x14004c9f1  xor     ecx, ecx
0x14004c9f3  mov     dword ptr [rsp+340h+var_2D0], ecx
0x14004c9f7  test    al, 1
0x14004c9f9  jz      loc_14004CB1A
0x14004c9ff  movzx   ecx, word ptr [r15+2]
0x14004ca04  lea     rsi, [rdi+38h]
0x14004ca08  mov     rdx, rsi
0x14004ca0b  mov     r8, r13
0x14004ca0e  call    ?AllocEmpty@UfsPathName@UnionFs@@SAJGAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocEmpty(ushort,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14004ca13  xor     r15d, r15d
0x14004ca16  mov     ebx, eax
0x14004ca18  test    eax, eax
0x14004ca1a  jns     short loc_14004CA95
0x14004ca1c  lea     rax, aPushAllocating_30; "PUSH: Allocating FoundPath"
0x14004ca23  mov     r8, 1AB001408E9h; struct UnionFs::StackEventTracer *
0x14004ca2d  lea     r9, aUnionfsUfspath_67; "UnionFs::UfsPathTable::LookupPriv"
0x14004ca34  mov     [rsp+340h+var_320], rax; char *
0x14004ca39  mov     rdx, r13; int
0x14004ca3c  mov     ecx, ebx; this
0x14004ca3e  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004ca43  lea     rcx, [rbp+240h+var_148]; this
0x14004ca4a  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14004ca4f  mov     rcx, [rbp+240h+var_C8]
0x14004ca56  test    rcx, rcx
0x14004ca59  jz      short loc_14004CA67
0x14004ca5b  mov     rax, [rcx]
0x14004ca5e  mov     rax, [rax+18h]
0x14004ca62  call    _guard_dispatch_icall
0x14004ca67  mov     rcx, [rsp+340h+Resource]; Resource
0x14004ca6c  mov     [rsp+340h+Resource], r15
0x14004ca71  test    rcx, rcx
0x14004ca74  jz      short loc_14004CA8E
0x14004ca76  call    cs:__imp_ExReleaseResourceLite
0x14004ca7d  nop     dword ptr [rax+rax+00h]
0x14004ca82  call    cs:__imp_KeLeaveCriticalRegion
0x14004ca89  nop     dword ptr [rax+rax+00h]
0x14004ca8e  mov     eax, ebx
0x14004ca90  jmp     loc_14004DE82
0x14004ca95  mov     r8, [rsi]
0x14004ca98  mov     rax, [r12+8]
0x14004ca9d  mov     rcx, [r8+8]
0x14004caa1  movzx   edx, word ptr [rax+78h]
0x14004caa5  mov     [r8+1Ah], dx
0x14004caaa  mov     [r8+18h], dx
0x14004caaf  mov     [r8+20h], rcx
0x14004cab3  lea     rax, [rcx+rdx]
0x14004cab7  mov     [r8+38h], r15w
0x14004cabc  mov     [r8+30h], rax
0x14004cac0  movzx   eax, word ptr [r8]
0x14004cac4  sub     ax, dx
0x14004cac7  lea     rdx, [rbp+240h+Source]; Source
0x14004cacb  mov     [r8+2Ah], ax
0x14004cad0  mov     [r8+28h], ax
0x14004cad5  mov     r8, r13; struct UnionFs::StackEventTracer *
0x14004cad8  mov     rax, [r12+8]
0x14004cadd  mov     rcx, [rsi]; SourceString
0x14004cae0  movups  xmm0, xmmword ptr [rax+78h]
0x14004cae4  movdqu  xmmword ptr [rbp+240h+Source.Length], xmm0
0x14004cae9  call    ?AppendUnicodeString@UfsPathName@UnionFs@@QEAAJAEBU_UNICODE_STRING@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AppendUnicodeString(_UNICODE_STRING const &,UnionFs::StackEventTracer &)
0x14004caee  mov     ebx, eax
0x14004caf0  test    eax, eax
0x14004caf2  jns     short loc_14004CB0A
0x14004caf4  lea     rax, aPushAppendingV; "PUSH: Appending volume path to FoundPat"...
0x14004cafb  mov     r8, 1B1001408F3h
0x14004cb05  jmp     loc_14004CA2D
0x14004cb0a  mov     rax, [rsi]
0x14004cb0d  mov     esi, [rbp+240h+arg_30]
0x14004cb13  movzx   edx, word ptr [rax]; struct FsFltWil::Details::RundownRefCacheAware *
0x14004cb16  mov     dword ptr [rsp+340h+var_2D0], edx
0x14004cb1a  xor     r13d, r13d
0x14004cb1d  mov     r15b, r13b
0x14004cb20  mov     ebx, 2
0x14004cb25  test    r15b, r15b
0x14004cb28  jz      loc_14004CBFA
0x14004cb2e  test    esi, esi
0x14004cb30  jnz     loc_14004D40D
0x14004cb36  lea     rcx, [rbp+240h+var_148]; this
0x14004cb3d  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14004cb42  xor     edx, edx; Val
0x14004cb44  lea     rcx, [rbp+240h+var_148]; void *
0x14004cb4b  mov     r8d, 88h; Size
0x14004cb51  call    memset
0x14004cb56  lea     rdx, [r14+20h]
0x14004cb5a  lea     rcx, [rbp+240h+var_258]
0x14004cb5e  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x14004cb63  mov     rcx, [rsp+340h+Resource]; Resource
0x14004cb68  mov     rax, [rbp+240h+var_258]
0x14004cb6c  mov     [rsp+340h+Resource], rax
0x14004cb71  test    rcx, rcx
0x14004cb74  jz      short loc_14004CB8E
0x14004cb76  call    cs:__imp_ExReleaseResourceLite
0x14004cb7d  nop     dword ptr [rax+rax+00h]
0x14004cb82  call    cs:__imp_KeLeaveCriticalRegion
0x14004cb89  nop     dword ptr [rax+rax+00h]
0x14004cb8e  mov     rdx, [r14+88h]; RunRefCacheAware
0x14004cb95  lea     r9, [rbp+240h+var_1C0]
0x14004cb9c  mov     r8b, 1
0x14004cb9f  mov     [rbp+240h+var_258], r13
0x14004cba3  lea     rcx, [rbp+240h+var_C0]; void *
0x14004cbaa  mov     [rbp+240h+var_150], r13
0x14004cbb1  call    ?AcquireRundownReference@FsFltWil@@YA?AV?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@PEAU_EX_RUNDOWN_REF_CACHE_AWARE@@_NV?$function@$$A6AX_N@Z@wistd@@@Z; FsFltWil::AcquireRundownReference(_EX_RUNDOWN_REF_CACHE_AWARE *,bool,wistd::function<void (bool)>)
0x14004cbb6  lea     rdx, [rbp+240h+var_C0]; void *
0x14004cbbd  lea     rcx, [rbp+240h+var_148]; this
0x14004cbc4  call    ??4?$unique_struct@URundownRefCacheAware@Details@FsFltWil@@P6AXPEAU123@@Z$1?ReleaseRundownProtectionCacheAware@23@YAX0@Z$$T$0A@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0>::operator=(wil::unique_struct<FsFltWil::Details::RundownRefCacheAware,void (*)(FsFltWil::Details::RundownRefCacheAware *),&FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *),std::nullptr_t,0> &&)
0x14004cbc9  lea     rcx, [rbp+240h+var_C0]; this
0x14004cbd0  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14004cbd5  mov     rcx, [rbp+240h+var_40]
0x14004cbdc  test    rcx, rcx
0x14004cbdf  jz      short loc_14004CBED
0x14004cbe1  mov     rax, [rcx]
0x14004cbe4  mov     rax, [rax+18h]
0x14004cbe8  call    _guard_dispatch_icall
0x14004cbed  cmp     [rbp+240h+var_148], r13
0x14004cbf4  jz      loc_14004D3D6
0x14004cbfa  mov     rsi, [r12]
0x14004cbfe  mov     rcx, r12; this
0x14004cc01  mov     [rsp+340h+var_2E8], r13d
0x14004cc06  call    ?HasVolumeRootMapping@UfsInstanceTierNode@UnionFs@@QEBA_NXZ; UnionFs::UfsInstanceTierNode::HasVolumeRootMapping(void)
0x14004cc0b  test    al, al
0x14004cc0d  jz      short loc_14004CC50
0x14004cc0f  mov     r13, [rbp+240h+var_278]
0x14004cc13  lea     rdx, ?g_RootName@UnionFs@@3U_UNICODE_STRING@@B; String2
0x14004cc1a  xor     r8d, r8d; CaseInSensitive
0x14004cc1d  lea     rcx, [rbp+240h+String1]; String1
0x14004cc21  movups  xmm0, xmmword ptr [r13+28h]
0x14004cc26  movdqu  xmmword ptr [rbp+240h+String1.Length], xmm0
0x14004cc2b  call    cs:__imp_RtlEqualUnicodeString
0x14004cc32  nop     dword ptr [rax+rax+00h]
0x14004cc37  xor     r12d, r12d
0x14004cc3a  test    al, al
0x14004cc3c  jnz     loc_14004D44C
0x14004cc42  mov     eax, [r14]
0x14004cc45  test    bl, al
0x14004cc47  jz      loc_14004D44C
0x14004cc4d  xor     r13d, r13d
0x14004cc50  mov     rcx, [rsi+40h]
0x14004cc54  mov     r12, r13
0x14004cc57  mov     [rbp+240h+var_290], r13
0x14004cc5b  mov     [rsp+340h+var_2D8], r13
0x14004cc60  xor     r13d, r13d
0x14004cc63  mov     ebx, r13d
0x14004cc66  test    rcx, rcx
0x14004cc69  jz      loc_14004CCFE
0x14004cc6f  mov     rax, [rcx]
0x14004cc72  mov     rax, [rax+30h]
0x14004cc76  call    _guard_dispatch_icall
0x14004cc7b  test    al, al
0x14004cc7d  jz      short loc_14004CCFE
0x14004cc7f  mov     r14, [rsi+48h]
0x14004cc83  mov     rax, [rsi+40h]
0x14004cc87  mov     [rsp+340h+var_2D8], rsi
0x14004cc8c  mov     [rbp+240h+var_1F0], rax
0x14004cc90  mov     [rbp+240h+var_1E8], r14
0x14004cc94  test    r14, r14
0x14004cc97  jz      short loc_14004CC9E
0x14004cc99  lock inc dword ptr [r14+8]
0x14004cc9e  mov     r15d, [rsp+340h+var_2EC]
0x14004cca3  lea     rax, [rsp+340h+var_2E8]
0x14004cca8  mov     r8d, r15d
0x14004ccab  mov     [rsp+340h+var_320], rax
0x14004ccb0  lea     r9, [rbp+240h+var_1F0]
0x14004ccb4  lea     rdx, [rbp+240h+var_250]
0x14004ccb8  call    ?LockPayloadPerCallerIntent@UfsPathTable@UnionFs@@AEBA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@W4LookupFlags@2@AEBV?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@PEAW4PayloadLockType@2@@Z; UnionFs::UfsPathTable::LockPayloadPerCallerIntent(UnionFs::LookupFlags,utl::shared_ptr<UnionFs::UfsTablePayload> const &,UnionFs::PayloadLockType *)
0x14004ccbd  mov     rbx, [rax]
0x14004ccc0  mov     [rax], r13
0x14004ccc3  mov     rcx, [rbp+240h+var_250]; Resource
0x14004ccc7  mov     [rbp+240h+var_250], r13
0x14004cccb  test    rcx, rcx
0x14004ccce  jz      short loc_14004CCE8
0x14004ccd0  call    cs:__imp_ExReleaseResourceLite
0x14004ccd7  nop     dword ptr [rax+rax+00h]
0x14004ccdc  call    cs:__imp_KeLeaveCriticalRegion
0x14004cce3  nop     dword ptr [rax+rax+00h]
0x14004cce8  test    r14, r14
0x14004cceb  jz      short loc_14004CCF5
0x14004cced  mov     rcx, r14; this
0x14004ccf0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004ccf5  mov     dword ptr [rdi+4], 2
0x14004ccfc  jmp     short loc_14004CD03
0x14004ccfe  mov     r15d, [rsp+340h+var_2EC]
0x14004cd03  lea     rdx, [rsi+80h]
0x14004cd0a  lea     rcx, [rbp+240h+var_248]
0x14004cd0e  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14004cd13  mov     r14, [rsi+58h]
0x14004cd17  mov     rax, [rsi+50h]
0x14004cd1b  mov     [rbp+240h+var_260], rax
0x14004cd1f  test    r14, r14
0x14004cd22  jz      short loc_14004CD29
0x14004cd24  lock inc dword ptr [r14+8]
0x14004cd29  mov     rcx, [rbp+240h+var_248]; this
0x14004cd2d  mov     [rbp+240h+var_248], r13
0x14004cd31  test    rcx, rcx
0x14004cd34  jz      short loc_14004CD3B
0x14004cd36  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x14004cd3b  mov     r13, [rsi+30h]
0x14004cd3f  mov     rsi, [rsi+38h]
0x14004cd43  test    rsi, rsi
0x14004cd46  jz      short loc_14004CD4C
0x14004cd48  lock inc dword ptr [rsi+8]
0x14004cd4c  xorps   xmm0, xmm0
0x14004cd4f  movups  xmmword ptr [rbp+240h+var_218.Length], xmm0
0x14004cd53  mov     rax, [rbp+240h+var_278]
0x14004cd57  lea     rdx, [rbp+240h+var_218]; struct _UNICODE_STRING *
0x14004cd5b  lea     rcx, [rbp+240h+String1]; this
0x14004cd5f  movups  xmm0, xmmword ptr [rax]
0x14004cd62  movzx   r8d, word ptr [rax+18h]; struct _UNICODE_STRING *
0x14004cd67  movdqu  xmmword ptr [rbp+240h+String1.Length], xmm0
0x14004cd6c  call    ?WalkPath@Utils@UnionFs@@YA_NAEBU_UNICODE_STRING@@AEAU3@G@Z; UnionFs::Utils::WalkPath(_UNICODE_STRING const &,_UNICODE_STRING &,ushort)
0x14004cd71  xor     ecx, ecx
0x14004cd73  mov     [rsp+340h+var_2F0], al
0x14004cd77  cmp     [rbp+240h+var_218.Length], cx
0x14004cd7b  jz      loc_14004DD90
0x14004cd81  mov     dl, r15b
0x14004cd84  lea     rax, [rbp+240h+var_218]
0x14004cd88  and     dl, 1
0x14004cd8b  xorps   xmm0, xmm0
0x14004cd8e  movups  [rbp+240h+var_208], xmm0
0x14004cd92  mov     byte ptr [rbp+240h+var_208+8], dl
0x14004cd95  mov     rcx, r13; this
0x14004cd98  lea     rdx, [rbp+240h+var_208]; struct UnionFs::UFS_COMPARE_KEY *
0x14004cd9c  mov     qword ptr [rbp+240h+var_208], rax
0x14004cda0  call    ?FindNode@UfsPathTree@UnionFs@@QEAAPEAVUfsPathTierNode@2@AEBUUFS_COMPARE_KEY@2@@Z; UnionFs::UfsPathTree::FindNode(UnionFs::UFS_COMPARE_KEY const &)
0x14004cda5  xor     r8d, r8d
0x14004cda8  mov     qword ptr [rbp+240h+String1.Length], rax
0x14004cdac  mov     r13, rax
0x14004cdaf  test    rax, rax
0x14004cdb2  jz      loc_14004DCC1
0x14004cdb8  mov     ecx, [rdi]
0x14004cdba  test    cl, 1
0x14004cdbd  jz      short loc_14004CDE4
0x14004cdbf  mov     r8, [rsp+340h+var_2C8]; struct _UNICODE_STRING *
0x14004cdc4  lea     rdx, [rax+20h]; Source
0x14004cdc8  mov     rcx, [rdi+38h]; this
  ... truncated ...
```
