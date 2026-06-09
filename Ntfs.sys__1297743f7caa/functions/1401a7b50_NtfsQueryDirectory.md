# NtfsQueryDirectory

- ea: `0x1401a7b50`
- end: `0x1401aa58e`
- name: `NtfsQueryDirectory`
- size: `10814`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64)`
- caller_count: `1`
- callee_count: `50`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401a7760`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x140009c80`
- `0x14000c290`
- `0x14000c450`
- `0x14000ea70`
- `0x140012e70`
- `0x14001e810`
- `0x140020de0`
- `0x1400210e0`
- `0x1400211b0`
- `0x140021220`
- `0x140025830`
- `0x140027f50`
- `0x140037200`
- `0x1400592c0`
- `0x140059330`
- `0x140059350`
- `0x140059440`
- `0x140059740`
- `0x140059c60`
- `0x1400bdc7c`
- `0x1400bddcc`
- `0x1400bde2c`
- `0x1400bde74`
- `0x1400bdebc`
- `0x1400d2000`
- `0x1400d205c`
- `0x14011f4dc`
- `0x140120670`
- `0x1401209b0`
- `0x140121a50`
- `0x140122350`
- `0x1401406b0`
- `0x140141400`
- `0x140153960`
- `0x140153b00`
- `0x140166564`
- `0x14017db70`
- `0x14018999c`
- `0x140197040`
- `0x14019f270`
- `0x1401a7b50`
- `0x1401aa5a0`
- `0x1401aab70`
- `0x1401be96c`
- `0x140223a3c`
- `0x14023ae60`
- `0x14023b80c`
- `0x14023b8f0`

## import_xrefs

- `ntoskrnl!FsRtlIsNameInUnUpcasedExpression` at `0x1401a9faa`
- `ntoskrnl!FsRtlIsNameInUnUpcasedExpression` at `0x1401a9faa`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x1401a7e94`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x1401aa481`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x1401a7e94`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x1401aa481`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1401a9847`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x1401a9847`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401a90f6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401a9cb4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401aa4ff`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402ada13`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401a90f6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401a9cb4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1401aa4ff`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402ada13`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402ad934`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1402ad934`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401a9193`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401a972b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401a989b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401a9ccf`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401aa519`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ada2c`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401a9193`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401a972b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401a989b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401a9ccf`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401aa519`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402ada2c`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401aa34d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ad9b9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401aa34d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402ad9b9`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401a8de8`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401a8de8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401aa17b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401aa55a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401aa570`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402adaac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402adac7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401aa17b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401aa55a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401aa570`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402adaac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402adac7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a7db0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a9ecf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401aa0f0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a7db0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401a9ecf`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401aa0f0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a8c90`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a97bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ad9ea`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402cb094`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a8c90`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a97bf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ad9ea`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402cb094`
- `ntoskrnl!ExRaiseStatus` at `0x1401a9240`
- `ntoskrnl!ExRaiseStatus` at `0x1401a9240`

## pseudocode

```c
__int64 __fastcall NtfsQueryDirectory(__int64 a1, __int64 a2, __int64 a3, __int64 a4, volatile signed __int32 *a5)
{
  volatile signed __int32 *LocalIndexCcb; // rdx
  struct _UNICODE_STRING *v8; // rsi
  char v9; // r14
  char v10; // bl
  bool v11; // r15
  char v12; // r12
  char v13; // r14
  int v14; // edi
  unsigned __int16 v15; // r9
  PVOID v16; // r8
  size_t Length; // rbx
  NTSTATUS v18; // esi
  __int64 v19; // r8
  WCHAR *QueryFileName; // rbx
  __int64 v21; // r8
  volatile signed __int32 *v22; // r14
  __int64 v23; // rcx
  int v24; // esi
  __int64 v25; // rdi
  int v26; // eax
  unsigned int v27; // eax
  __int64 v28; // rcx
  bool v29; // al
  __int64 *v30; // r10
  char v31; // r15
  _DWORD *v32; // rax
  _WORD *v33; // rbx
  __int64 v34; // r12
  int v35; // eax
  bool v36; // r14
  int v37; // ebx
  __int64 *v38; // rbx
  __int64 *OtherFileName; // r15
  __int64 v40; // rdx
  __int64 v41; // rcx
  int v42; // edx
  __int64 v43; // rcx
  size_t v44; // r8
  void *v45; // rcx
  unsigned int v46; // r8d
  unsigned int v47; // eax
  size_t v48; // rax
  void *v49; // rdx
  void *v50; // rcx
  __int64 v51; // r14
  char v52; // r12
  __int64 v53; // r15
  int v54; // ecx
  _QWORD *v55; // rcx
  _QWORD *v56; // rcx
  int v57; // eax
  __int64 v58; // rdx
  _QWORD *v59; // rax
  __int64 v60; // rdx
  _QWORD *v61; // rcx
  unsigned int v62; // r12d
  _QWORD *v63; // rcx
  _QWORD *v64; // rcx
  __int64 v65; // r12
  unsigned int v66; // r8d
  __int64 v67; // rdx
  _DWORD *v68; // rcx
  unsigned int v69; // r9d
  int v70; // eax
  char v71; // dl
  unsigned int v72; // eax
  unsigned int *v73; // rcx
  __int64 v74; // r9
  int restarted; // eax
  int v76; // ebx
  PVOID v77; // r8
  __int64 NextParentLcb; // rax
  __int64 v79; // rdi
  char v80; // bl
  PVOID v81; // rax
  char v82; // al
  __int64 ShortName; // rax
  __int64 v84; // rdx
  __int64 v85; // rdi
  char v86; // bl
  _BYTE *v87; // rcx
  void *v88; // rdx
  void *v89; // rcx
  unsigned int v90; // eax
  unsigned int *v91; // rcx
  char EaSize; // al
  unsigned int *v93; // rcx
  unsigned __int8 v94; // al
  int v95; // edx
  __int64 v96; // rax
  __int64 v97; // rdx
  __int64 v98; // r14
  char v99; // di
  _BYTE *v100; // rcx
  void *v101; // rdx
  void *v102; // rcx
  struct _ERESOURCE *v103; // rcx
  int v104; // ecx
  char v105; // dl
  char v106; // dl
  unsigned int v107; // eax
  unsigned int *v108; // rcx
  char v109; // al
  unsigned int v110; // eax
  unsigned int *v111; // rcx
  __int64 v112; // rdx
  __int64 v113; // r8
  __int64 v114; // r9
  __int64 v115; // rax
  __int64 v116; // r9
  char IsEqual; // al
  _QWORD *v118; // rcx
  _QWORD *v119; // rax
  char v120; // r10
  unsigned __int64 v121; // r8
  unsigned __int64 v122; // r9
  __int64 v123; // rcx
  __int64 v124; // rdx
  __int64 v125; // rbx
  int v126; // ecx
  char v127; // di
  _BYTE *v128; // rcx
  void *v129; // rdx
  void *v130; // rcx
  unsigned int v131; // eax
  unsigned int *v132; // rcx
  char v133; // al
  char v134; // di
  _BYTE *v135; // rcx
  void *v136; // rdx
  void *v137; // rcx
  unsigned __int8 v138; // al
  __int64 v139; // rcx
  struct _ERESOURCE *v140; // rcx
  __int64 v141; // r8
  __int64 v142; // rcx
  _WORD *v143; // rbx
  __int64 v144; // rax
  __int64 v145; // rdx
  __int64 v146; // r14
  __int64 v147; // rax
  __int64 v148; // rdx
  __int64 v149; // r14
  __int64 v150; // rbx
  __int64 v151; // rbx
  int v152; // edx
  WCHAR *v153; // r15
  PWSTR Buffer; // rax
  int v155; // edx
  void *v156; // rcx
  PVOID v157; // rbx
  __int64 v158; // r15
  __int64 v159; // rbx
  __int64 v160; // r9
  unsigned int v162; // eax
  unsigned int v163; // ebx
  struct _ERESOURCE *v164; // rcx
  __int64 v165; // rbx
  int v166; // [rsp+20h] [rbp-238h]
  __int64 v167; // [rsp+28h] [rbp-230h]
  __int64 v168; // [rsp+28h] [rbp-230h]
  __int64 v169; // [rsp+28h] [rbp-230h]
  char v170; // [rsp+50h] [rbp-208h]
  char v171; // [rsp+52h] [rbp-206h]
  char v172; // [rsp+53h] [rbp-205h] BYREF
  char v173; // [rsp+54h] [rbp-204h]
  char v174; // [rsp+55h] [rbp-203h]
  char v175; // [rsp+56h] [rbp-202h] BYREF
  char v176; // [rsp+57h] [rbp-201h]
  bool v177; // [rsp+58h] [rbp-200h]
  char v178; // [rsp+59h] [rbp-1FFh]
  PVOID v179; // [rsp+60h] [rbp-1F8h]
  unsigned int v180; // [rsp+68h] [rbp-1F0h]
  int v181; // [rsp+6Ch] [rbp-1ECh]
  bool v182; // [rsp+70h] [rbp-1E8h]
  char v183; // [rsp+71h] [rbp-1E7h]
  bool v184; // [rsp+72h] [rbp-1E6h]
  char v185; // [rsp+73h] [rbp-1E5h]
  unsigned int Size; // [rsp+74h] [rbp-1E4h]
  char Size_4; // [rsp+78h] [rbp-1E0h]
  char Size_5; // [rsp+79h] [rbp-1DFh]
  bool Size_6; // [rsp+7Ah] [rbp-1DEh]
  __int64 v190; // [rsp+80h] [rbp-1D8h]
  __int64 v191; // [rsp+88h] [rbp-1D0h]
  __int64 v192; // [rsp+90h] [rbp-1C8h]
  int v193; // [rsp+98h] [rbp-1C0h]
  __int64 v194; // [rsp+A0h] [rbp-1B8h]
  char v195; // [rsp+A8h] [rbp-1B0h]
  char v196; // [rsp+A9h] [rbp-1AFh]
  unsigned int v197; // [rsp+ACh] [rbp-1ACh]
  PVOID Entry; // [rsp+B0h] [rbp-1A8h] BYREF
  __int64 v199; // [rsp+B8h] [rbp-1A0h]
  __int64 v200; // [rsp+C0h] [rbp-198h]
  _BYTE *v201; // [rsp+C8h] [rbp-190h]
  __int64 v202; // [rsp+D0h] [rbp-188h] BYREF
  PVOID PoolWithTag; // [rsp+D8h] [rbp-180h]
  __int64 *v204; // [rsp+E0h] [rbp-178h] BYREF
  int v205; // [rsp+E8h] [rbp-170h]
  WCHAR *v206; // [rsp+F0h] [rbp-168h]
  unsigned int v207; // [rsp+F8h] [rbp-160h]
  unsigned int v208; // [rsp+FCh] [rbp-15Ch]
  unsigned int v209; // [rsp+100h] [rbp-158h] BYREF
  unsigned int v210; // [rsp+104h] [rbp-154h] BYREF
  unsigned int v211; // [rsp+108h] [rbp-150h] BYREF
  unsigned int v212; // [rsp+10Ch] [rbp-14Ch]
  int v213; // [rsp+110h] [rbp-148h]
  __int64 v214; // [rsp+118h] [rbp-140h]
  __int64 v215; // [rsp+120h] [rbp-138h]
  PVOID P; // [rsp+128h] [rbp-130h]
  struct _UNICODE_STRING Name; // [rsp+130h] [rbp-128h] BYREF
  unsigned int v218; // [rsp+140h] [rbp-118h]
  _DWORD *v219; // [rsp+148h] [rbp-110h]
  __int64 *v220; // [rsp+150h] [rbp-108h]
  __int64 v221; // [rsp+158h] [rbp-100h]
  _QWORD *v222; // [rsp+160h] [rbp-F8h]
  __int64 v223; // [rsp+168h] [rbp-F0h]
  volatile signed __int32 *v224; // [rsp+170h] [rbp-E8h]
  __int64 v225; // [rsp+178h] [rbp-E0h]
  volatile signed __int32 *v226; // [rsp+180h] [rbp-D8h]
  _OWORD v227[2]; // [rsp+188h] [rbp-D0h] BYREF
  __int64 v228; // [rsp+1A8h] [rbp-B0h]
  _QWORD Src[12]; // [rsp+1B0h] [rbp-A8h] BYREF

  v190 = a4;
  v194 = a3;
  v191 = a2;
  v215 = a1;
  v223 = a3;
  v225 = a4;
  LocalIndexCcb = a5;
  v179 = (PVOID)a5;
  v224 = a5;
  Entry = 0;
  v175 = 0;
  v221 = *(_QWORD *)(a2 + 184);
  v8 = *(struct _UNICODE_STRING **)(v221 + 16);
  v9 = *(_BYTE *)(v221 + 2);
  v195 = v9 & 2;
  v10 = v9 & 0x10;
  v207 = *(_DWORD *)(v221 + 8);
  v193 = *(_DWORD *)(v221 + 24);
  v11 = v8 && v8->Length;
  if ( (*(_DWORD *)(a1 + 12) & 1) == 0 )
  {
    if ( !v10 )
      goto LABEL_544;
    if ( (v9 & 2) != 0 )
      goto LABEL_4;
    if ( !v11 || FsRtlDoesNameContainWildCards(v8) )
    {
LABEL_544:
      v162 = NtfsPostRequest((PVOID)a1);
      v163 = v162;
      if ( NtfsStatusDebugFlags
        && v162
        && v162 != 294
        && v162 - 298 > 1
        && v162 < 0xFFFFFFED
        && v162 != -1073741608
        && v162 != -1073741802
        && v162 != -1073741807
        && v162 + 2147483643 > 1
        && v162 != 259 )
      {
        NtfsStatusTraceAndDebugInternal(0, v162, 852606);
      }
      return v163;
    }
    LocalIndexCcb = (volatile signed __int32 *)v179;
  }
LABEL_4:
  v226 = LocalIndexCcb;
  if ( !v10 )
    goto LABEL_5;
  if ( *((_QWORD *)LocalIndexCcb + 10) )
  {
    v163 = -1072103334;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3222863962LL, 852627);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3222863962LL, 852628);
    LOBYTE(a4) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3222863962LL, a4, 0);
    return v163;
  }
  LocalIndexCcb = (volatile signed __int32 *)AllocateLocalIndexCcb(LocalIndexCcb);
  v179 = (PVOID)LocalIndexCcb;
  v224 = LocalIndexCcb;
LABEL_5:
  v12 = v9 & 1;
  v13 = v9 & 4;
  P = 0;
  v199 = 0;
  v200 = 0;
  PoolWithTag = 0;
  v183 = 0;
  v174 = 0;
  v185 = 0;
  v184 = 0;
  Size_6 = 0;
  if ( v207 >= 0x10000 )
    *(_DWORD *)(a1 + 4) |= 0x2000000u;
  if ( (*(_DWORD *)(*(_QWORD *)(v221 + 48) + 80LL) & 2) == 0 && !v10 )
  {
    memset(v227, 0, sizeof(v227));
    v228 = 0;
    NtfsAcquireIndexCcb(v190, LocalIndexCcb, v227);
    v185 = 1;
  }
  if ( v193 > 50 )
  {
    if ( v193 == 60 )
    {
      v180 = 88;
      goto LABEL_15;
    }
    v15 = 3;
    switch ( v193 )
    {
      case '?':
        v180 = 114;
        break;
      case 'N':
        v180 = 80;
        break;
      case 'O':
        v180 = 106;
        break;
      case 'P':
        v180 = 96;
        break;
      case 'Q':
        v180 = 122;
        break;
      default:
        goto LABEL_464;
    }
    v14 = 68;
    goto LABEL_17;
  }
  switch ( v193 )
  {
    case 50:
      v180 = 92;
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x60u, 0x6446744Eu);
      goto LABEL_15;
    case 1:
      v180 = 64;
      goto LABEL_15;
    case 2:
      v14 = 68;
      v180 = 68;
      goto LABEL_16;
    case 3:
      v180 = 94;
      goto LABEL_15;
  }
  if ( v193 != 12 )
  {
    if ( v193 == 37 )
    {
      v180 = 104;
      goto LABEL_15;
    }
    if ( v193 == 38 )
    {
      v180 = 80;
      goto LABEL_15;
    }
LABEL_464:
    v18 = -1073741821;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_449;
    v19 = 852764;
    goto LABEL_448;
  }
  v180 = 12;
LABEL_15:
  v14 = 68;
LABEL_16:
  v15 = 3;
LABEL_17:
  if ( !v10 && (v16 = v179, *((_QWORD *)v179 + 19)) )
  {
    LOBYTE(v16) = 0;
    v176 = 0;
    if ( !v11 || !v12 && !v13 )
    {
      v22 = (volatile signed __int32 *)v179;
      QueryFileName = (WCHAR *)NtfsGetQueryFileName(v179, LocalIndexCcb, v16, 3);
      v206 = QueryFileName;
      goto LABEL_41;
    }
  }
  else
  {
    LOBYTE(v16) = 1;
    v176 = 1;
  }
  if ( v11 )
  {
    Length = v8->Length;
    if ( (unsigned __int16)Length <= 0x1FEu
      && (LOBYTE(LocalIndexCcb) = 1, (unsigned __int8)NtfsIsFileNameValid(v8, LocalIndexCcb))
      || !(_BYTE)v16
      && (unsigned __int16)(Length - 1) <= v15
      && (Buffer = v8->Buffer, *Buffer == 46)
      && ((_WORD)Length != 4 || Buffer[1] == 46) )
    {
      v14 = Length + 66;
      v153 = (WCHAR *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned int)(Length + 66), 0x6446744Eu);
      v206 = v153;
      memmove(v153 + 33, v8->Buffer, Length);
      *(_QWORD *)v153 = *(_QWORD *)(*(_QWORD *)(v190 + 184) + 8LL);
      *((_BYTE *)v153 + 64) = Length >> 1;
      QueryFileName = v153;
      *((_BYTE *)v153 + 65) = 0;
      goto LABEL_32;
    }
    v18 = -1073741773;
    if ( !NtfsStatusDebugFlags )
    {
LABEL_449:
      v181 = v18;
      v30 = 0;
      v34 = v191;
      v22 = (volatile signed __int32 *)v179;
      goto LABEL_450;
    }
    v19 = 852833;
LABEL_448:
    NtfsStatusTraceAndDebugInternal(0, (unsigned int)v18, v19);
    goto LABEL_449;
  }
  QueryFileName = (WCHAR *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x44u, 0x6446744Eu);
  v206 = QueryFileName;
  *(_QWORD *)QueryFileName = *(_QWORD *)(*(_QWORD *)(v190 + 184) + 8LL);
  *((_DWORD *)QueryFileName + 16) = 2752513;
LABEL_32:
  if ( !v176 && v13 )
  {
    P = QueryFileName;
    v12 = 0;
    v22 = (volatile signed __int32 *)v179;
    goto LABEL_41;
  }
  Name = 0;
  v22 = (volatile signed __int32 *)v179;
  if ( !v176 )
  {
    v156 = (void *)*((_QWORD *)v179 + 19);
    if ( (*((_DWORD *)v179 + 1) & 0x1000000) != 0 )
      NtOfsFreeReadContext(v156);
    else
      ExFreePoolWithTag(v156, 0);
    *((_QWORD *)v179 + 19) = 0;
    ClearFlagInterlocked(v22 + 1, 0x1000000);
  }
  if ( (v22[1] & 0x1000000) != 0 )
    _InterlockedAnd(v22 + 1, 0xFEFFFFFF);
  QueryFileName = v206;
  *((_QWORD *)v22 + 19) = v206;
  *((_DWORD *)v22 + 36) = v14;
  Name.Length = 2 * *((unsigned __int8 *)QueryFileName + 64);
  Name.MaximumLength = Name.Length;
  Name.Buffer = QueryFileName + 33;
  if ( (v22[1] & 0x300) != 0 )
    _InterlockedAnd(v22 + 1, 0xFFFFFCFF);
  v23 = v194;
  if ( v190 != *(_QWORD *)(v194 + 32) )
  {
    if ( FsRtlDoesNameContainWildCards(&Name) )
    {
      if ( (unsigned __int8)FsRtlIsNameInUnUpcasedExpression(&Name, &word_140092198, 0, 0) )
        SetFlagInterlocked(v22 + 1, 768);
      goto LABEL_41;
    }
    if ( Name.Length == word_140092198 && !memcmp(Name.Buffer, Buf2, Name.Length) )
    {
      v23 = v194;
      if ( (v22[1] & 0x300) != 0x300 )
        _InterlockedOr(v22 + 1, 0x300u);
      goto LABEL_42;
    }
LABEL_41:
    v23 = v194;
  }
LABEL_42:
  *(_QWORD *)(v191 + 56) = 0;
  Size_4 = 0;
  if ( (*(_DWORD *)(a1 + 12) & 0x200) != 0 || *((_QWORD *)v22 + 22) )
  {
    v24 = 3932169;
  }
  else
  {
    v24 = 3932169;
    if ( (unsigned int)(v193 - 60) > 0x15 || !_bittest(&v24, v193 - 60) )
    {
      v25 = 1;
      goto LABEL_46;
    }
  }
  v25 = 1;
  LOBYTE(v21) = 1;
  NtfsAcquireSharedVcb(a1, v23, v21);
  v174 = 1;
LABEL_46:
  if ( !*((_QWORD *)v22 + 22) )
    goto LABEL_47;
  ExAcquirePushLockSharedEx(v194 + 656, 0);
  v119 = *(_QWORD **)(v194 + 1344);
  v222 = v119;
  v120 = 0;
  Size_4 = 0;
  if ( !v119 )
    goto LABEL_308;
  while ( 1 )
  {
    v121 = *(v119 - 2) & 0xFFFFFFFFFFFFLL;
    v122 = *((_QWORD *)v22 + 22) & 0xFFFFFFFFFFFFLL;
    if ( v122 >= v121 )
    {
      if ( v122 > v121 )
        goto LABEL_299;
      v123 = HIWORD(*((_QWORD *)v22 + 22));
      v124 = HIWORD(*(v119 - 2));
      if ( (unsigned __int16)v123 >= (unsigned __int16)v124 )
        break;
    }
    v118 = (_QWORD *)*v119;
LABEL_300:
    if ( !v118 )
      goto LABEL_308;
    v119 = v118;
    v222 = v118;
  }
  if ( (unsigned __int16)v123 > (unsigned __int16)v124 )
  {
LABEL_299:
    v118 = (_QWORD *)v119[1];
    goto LABEL_300;
  }
  v120 = 1;
  Size_4 = 1;
LABEL_308:
  if ( v120 )
  {
    v199 = *(v119 - 1);
    _InterlockedAdd((volatile signed __int32 *)(v199 + 28), 1u);
  }
  ExReleasePushLockEx(v194 + 656, 0);
  if ( v199 )
    NtfsAcquireSharedFcb(a1, v199, 0, 1);
  *((_QWORD *)v22 + 22) = 0;
  QueryFileName = v206;
LABEL_47:
  NtfsAcquireSharedFcb(a1, *(_QWORD *)(v190 + 184), v190, 0);
  v175 = 1;
  if ( v174 && (*(_DWORD *)(a1 + 12) & 0x200) == 0 && ((unsigned int)(v193 - 60) > 0x15 || !_bittest(&v24, v193 - 60)) )
  {
    NtfsReleaseVcb(a1, v194);
    v174 = 0;
  }
  v219 = v22 + 1;
  v26 = *((_DWORD *)v22 + 1);
  v177 = (v26 & 1) != 0 && ((v26 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v190 + 184) + 16LL) & 0x400) == 0);
  v27 = TxfSetupTransactionContextFromCcb(a1, *(_QWORD *)(v221 + 48), 0, 0, 0);
  v18 = v27;
  v181 = v27;
  if ( v27 )
  {
    if ( NtfsStatusDebugFlags
      && (((v27 - 294) & 0xFFFFFFFA) != 0 || v27 == 295)
      && v27 < 0xFFFFFFED
      && v27 != -1073741608
      && v27 != -1073741802
      && v27 != -1073741807
      && v27 + 2147483643 > 1
      && v27 != 259 )
    {
      NtfsStatusTraceAndDebugInternal(a1, v27, 853079);
    }
    ExRaiseStatus(v18);
  }
  v28 = *((_QWORD *)v22 + 10);
  v29 = v28 && (*(_DWORD *)(v28 + 4) & 2) != 0 && *(_DWORD *)(v28 + 36);
  v184 = v29;
  Size_6 = v29;
  if ( (*(_DWORD *)(v190 + 512) & 0x10000) != 0 )
  {
    v18 = -1073741202;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221226094LL, 853096);
    v181 = -1073741202;
    v34 = v191;
    v30 = 0;
    goto LABEL_450;
  }
  v214 = NtfsMapUserBuffer(v191, 16);
  v30 = 0;
  if ( *(_QWORD *)(v191 + 8) )
    v170 = 0;
  else
    v170 = *(_BYTE *)(v191 + 64);
  if ( v176 || v12 )
  {
    v171 = 1;
    v173 = 0;
    if ( (v22[1] & 0xC00) != 0 )
      _InterlockedAnd(v22 + 1, 0xFFFFF3FF);
  }
  else
  {
    if ( !P )
    {
      v171 = 0;
      goto LABEL_202;
    }
    v171 = 1;
    v173 = 1;
    v138 = *((_BYTE *)QueryFileName + 64);
    if ( v138 <= 2u && QueryFileName[33] == 46 )
    {
      if ( v138 == 1 )
      {
        ClearFlagInterlocked(v22 + 1, 2048);
        SetFlagInterlocked(v139, 1024);
        QueryFileName[33] = 42;
        goto LABEL_202;
      }
      if ( QueryFileName[34] == 46 )
      {
        SetFlagInterlocked(v22 + 1, 3072);
        *(_DWORD *)(QueryFileName + 33) = 2752554;
LABEL_202:
        v173 = (char)v30;
      }
    }
    else
    {
      SetFlagInterlocked(v22 + 1, 3072);
    }
  }
  v212 = (unsigned int)v30;
  v197 = (unsigned int)v30;
  if ( QueryFileName[33] == 42
    && ((v94 = *((_BYTE *)QueryFileName + 64), v94 == 1)
     || v94 == 3 && QueryFileName[34] == 46 && QueryFileName[35] == 42) )
  {
    Size_5 = 1;
  }
  else
  {
    Size_5 = (char)v30;
  }
  while ( 2 )
  {
    while ( 2 )
    {
      while ( 2 )
      {
        v31 = v171;
LABEL_62:
        v202 = (__int64)v30;
        v220 = v30;
        v192 = (__int64)v30;
        v204 = v30;
        Size = (unsigned int)v30;
        v172 = (char)v30;
        if ( v200 )
        {
          if ( *(_WORD *)v200 == 1794 )
            v103 = (struct _ERESOURCE *)(*(_QWORD *)(v200 + 104) + 64LL);
          else
            v103 = *(struct _ERESOURCE **)(v200 + 8);
          ExReleaseResourceLite(v103);
          v30 = 0;
          v200 = 0;
        }
        v32 = PoolWithTag;
        if ( PoolWithTag )
        {
          *(_OWORD *)PoolWithTag = 0;
          v32[4] = 0;
        }
        v33 = Entry;
        if ( Entry )
        {
          if ( (*((_BYTE *)Entry + 330) & 1) != 0 )
          {
            ExReleasePushLockEx(*(_QWORD *)(a1 + 104) + 656LL, 0);
            v33[165] &= ~1u;
            v30 = 0;
          }
          v32 = PoolWithTag;
        }
        v34 = (__int64)v30;
        if ( v31 )
        {
          if ( v183 == (_BYTE)v30 )
            v74 = (__int64)v206;
          else
            v74 = *((_QWORD *)v22 + 21) + 16LL;
          LOBYTE(v166) = v177;
          restarted = NtfsRestartIndexEnumeration(a1, v22, v190, v74);
          v36 = restarted >= 0;
          v182 = restarted >= 0;
          v30 = 0;
          v76 = 0;
          if ( restarted != -1073741275 )
            v76 = restarted;
          v171 = 0;
          v183 = 0;
          v196 = 0;
          if ( v76 < 0 )
          {
            if ( NtfsStatusDebugFlags
              && (unsigned int)v76 < 0xFFFFFFED
              && v76 != -1073741802
              && v76 != -1073741807
              && (unsigned int)(v76 + 2147483643) > 1
              && v76 != -1073741608 )
            {
              NtfsStatusTraceAndDebugInternal(0, (unsigned int)v76, 853298);
              v30 = 0;
            }
            v18 = v76;
            v181 = v76;
            v22 = (volatile signed __int32 *)v179;
            v34 = v191;
            goto LABEL_450;
          }
        }
        else
        {
          v35 = NtfsContinueIndexEnumeration(a1, (_DWORD)v22, v190, (__int64)&v202, (__int64)v32);
          v36 = v35 >= 0;
          v182 = v35 >= 0;
          v30 = 0;
          v37 = 0;
          if ( v35 != -1073741275 )
            v37 = v35;
          if ( v37 < 0 )
          {
            if ( NtfsStatusDebugFlags
              && (unsigned int)v37 < 0xFFFFFFED
              && v37 != -1073741802
              && v37 != -1073741807
              && (unsigned int)(v37 + 2147483643) > 1
              && v37 != -1073741608 )
            {
              NtfsStatusTraceAndDebugInternal(0, (unsigned int)v37, 853317);
              v30 = 0;
            }
            v18 = v37;
            v181 = v37;
            v22 = (volatile signed __int32 *)v179;
            v34 = v191;
            goto LABEL_450;
          }
        }
        if ( v195 && v197 )
          goto LABEL_167;
        v38 = 0;
        v204 = 0;
        OtherFileName = NtfsDotDotName;
        v220 = NtfsDotDotName;
        v40 = *(_QWORD *)(v190 + 184);
        v192 = v40 + 128;
        v173 = 0;
        v178 = 0;
        if ( (*v219 & 0x500) == 0x100 )
        {
          Size = 2;
          v36 = 1;
          v182 = 1;
          v38 = *(__int64 **)(v40 + 8);
          v204 = v38;
          v178 = 1;
          if ( v193 == 50 )
            memset(PoolWithTag, 0, 0x60u);
          SetFlagInterlocked(v219, 1024);
          goto LABEL_74;
        }
        v41 = *v219 & 0xA00;
        if ( (_DWORD)v41 == 512 )
        {
          Size = 4;
          v36 = 1;
          v182 = 1;
          if ( v193 == 12 )
          {
LABEL_180:
            if ( v193 == 50 )
              memset(PoolWithTag, 0, 0x60u);
            SetFlagInterlocked(v219, 2048);
            v30 = 0;
LABEL_74:
            v42 = Size;
            goto LABEL_75;
          }
          v77 = v179;
          NextParentLcb = *((_QWORD *)v179 + 9);
          if ( !NextParentLcb )
          {
            NextParentLcb = NtfsGetNextParentLcb(v41, v40, 0);
            if ( !NextParentLcb )
            {
              v81 = VirtualAddress;
LABEL_179:
              v192 = (__int64)v81;
              goto LABEL_180;
            }
          }
          v79 = *(_QWORD *)(*(_QWORD *)(NextParentLcb + 24) + 184LL);
          v80 = v174;
          LOBYTE(v77) = v174;
          if ( (unsigned __int8)NtfsAcquireResourceShared(v41, v79, v77) )
          {
            v200 = v79;
            if ( (*(_DWORD *)(v79 + 4) & 8) != 0 )
            {
LABEL_177:
              if ( v80 )
              {
                if ( (unsigned int)(v193 - 60) > 0x15 || (v104 = 3932169, !_bittest(&v104, v193 - 60)) )
                {
                  NtfsReleaseVcb(a1, v194);
                  v174 = 0;
                  *(_DWORD *)(a1 + 12) &= ~0x200u;
                }
              }
              v38 = *(__int64 **)(v79 + 8);
              v204 = v38;
              v81 = (PVOID)(v79 + 128);
              v25 = 1;
              v178 = 1;
              goto LABEL_179;
            }
          }
          else
          {
            *(_DWORD *)(a1 + 12) |= 0x200u;
            NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 853407);
          }
          if ( *(_WORD *)v79 == 1794 )
            v140 = (struct _ERESOURCE *)(*(_QWORD *)(v79 + 104) + 64LL);
          else
            v140 = *(struct _ERESOURCE **)(v79 + 8);
          ExReleaseResourceLite(v140);
          v200 = 0;
          LOBYTE(v141) = v80;
          if ( !(unsigned __int8)NtfsAcquireResourceExclusive(v142, v79, v141) )
          {
            *(_DWORD *)(a1 + 12) |= 0x200u;
            NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 853420);
          }
          v200 = v79;
          if ( (*(_DWORD *)(v79 + 4) & 8) == 0 )
            NtfsUpdateFcbInfoFromDisk(a1, 0, 0);
          ExConvertExclusiveToSharedLite((PERESOURCE)(*(_QWORD *)(v79 + 104) + 64LL));
          goto LABEL_177;
        }
        if ( !v36 )
          goto LABEL_74;
        v38 = *(__int64 **)v202;
        v204 = *(__int64 **)v202;
        OtherFileName = (__int64 *)(v202 + 16);
        v220 = (__int64 *)(v202 + 16);
        v70 = *(unsigned __int16 *)(v202 + 10);
        if ( (unsigned __int16)v70 < 0x42u || (v42 = 2 * *(unsigned __int8 *)(v202 + 80), Size = v42, v42 != v70 - 66) )
        {
          v143 = Entry;
          if ( Entry && (*((_BYTE *)Entry + 330) & 1) != 0 )
          {
            ExReleasePushLockEx(*(_QWORD *)(a1 + 104) + 656LL, 0);
            v143[165] &= ~1u;
          }
          v125 = v190;
          NtfsAttachRepairInfo_IndexOffset(a1, v166, v190, *((_QWORD *)v179 + 17), 0, 0, 0);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 853534);
          v82 = NtfsRaiseStatusInternal(
                  a1,
                  -1073741566,
                  (unsigned int)*(_QWORD *)(v125 + 184) + 8,
                  *(_QWORD *)(v125 + 184),
                  853534);
LABEL_347:
          if ( v82 )
          {
            NtfsStatusTraceAndDebugInternal(0, 3221225487LL, 853589);
            v30 = 0;
          }
          v18 = -1073741809;
          v181 = -1073741809;
          v22 = (volatile signed __int32 *)v179;
          v34 = v191;
          goto LABEL_450;
        }
        v192 = v202 + 24;
        v173 = 1;
        if ( (unsigned int)v38 < 0x10 )
          goto LABEL_130;
LABEL_75:
        if ( !v36 )
        {
          if ( v197 != (_DWORD)v30 )
          {
LABEL_167:
            v18 = (int)v30;
            v181 = (int)v30;
            v22 = (volatile signed __int32 *)v179;
            v34 = v191;
            goto LABEL_450;
          }
          v82 = NtfsStatusDebugFlags;
          if ( v176 == (_BYTE)v30 )
          {
            v18 = -2147483642;
            v181 = -2147483642;
            v22 = (volatile signed __int32 *)v179;
            v34 = v191;
            goto LABEL_450;
          }
          goto LABEL_347;
        }
        if ( (*((_BYTE *)OtherFileName + 65) & 3) != 2 )
        {
          v22 = (volatile signed __int32 *)v179;
          goto LABEL_78;
        }
        if ( Entry == v30 )
        {
          v25 = (__int64)ExAllocateFromLookasideListEx(&NtfsIndexContextLookasideList);
          Entry = (PVOID)v25;
          memset((void *)(v25 + 88), 0, 0x118u);
          memset((void *)v25, 0, 0x58u);
          *(_QWORD *)(v25 + 96) = v25 + 112;
          *(_WORD *)(v25 + 328) = 3;
        }
        else
        {
          NtfsReinitializeIndexContext(a1, Entry);
        }
        v30 = 0;
        if ( Size_5 )
        {
          v25 = 1;
LABEL_130:
          v22 = (volatile signed __int32 *)v179;
          continue;
        }
        break;
      }
      v34 = (__int64)OtherFileName;
      v22 = (volatile signed __int32 *)v179;
      OtherFileName = (__int64 *)NtfsRetrieveOtherFileName(a1, Entry, v199, (__int64)&v172, 0);
      v220 = OtherFileName;
      v30 = 0;
      if ( OtherFileName )
      {
        if ( (v22[1] & 4) != 0 )
        {
          v115 = NtfsGetQueryFileName(v22, v112, v113, v114);
          LOBYTE(v116) = v177;
          IsEqual = NtfsFileNameIsInExpression(*(_QWORD *)(v194 + 784), v115, OtherFileName, v116);
        }
        else
        {
          NtfsGetQueryFileName(v22, v112, v113, v114);
          IsEqual = NtfsFileNameIsEqual(*(PCWCH *)(v194 + 784));
        }
        v30 = 0;
        if ( IsEqual )
        {
LABEL_407:
          v25 = 1;
          continue;
        }
        v42 = 2 * *((unsigned __int8 *)OtherFileName + 64);
        Size = v42;
LABEL_78:
        v208 = v207 - v197;
        if ( v197 && (v207 < v197 || v42 + v180 > v207 - v197) )
        {
          v30 = 0;
          v18 = 0;
          v181 = 0;
          v34 = v191;
          goto LABEL_450;
        }
        v43 = *(_QWORD *)(v191 + 56);
        v25 = v197 + v180;
        v44 = v25 - v43;
        v45 = (void *)(v214 + v43);
        LOBYTE(v22) = v170;
        if ( v170 )
          RtlSetUserMemory(v45);
        else
          RtlSetVolatileMemory(v45, 0, v44);
        v46 = v180;
        v47 = v208;
        if ( v208 >= Size + v180 )
        {
          v48 = Size;
          goto LABEL_83;
        }
      }
      else
      {
        if ( !v172 )
          goto LABEL_407;
        v34 = v191;
        if ( *(_QWORD *)(v191 + 56) )
        {
          v18 = 0;
          v181 = 0;
          goto LABEL_450;
        }
        v47 = NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 853678);
      }
      break;
    }
    v48 = v47 - v46;
LABEL_83:
    v213 = v48;
    *(_QWORD *)&Name.Length = v48;
    v49 = (char *)OtherFileName + 66;
    v50 = (void *)(v25 + v214);
    if ( (_BYTE)v22 )
      RtlCopyToUser(v50, v49, v48);
    else
      RtlCopyVolatileMemory(v50, v49, v48);
    v51 = v214 + v197;
    v201 = (_BYTE *)v51;
    v30 = 0;
    if ( v193 <= 50 )
    {
      if ( v193 != 50 )
      {
        switch ( v193 )
        {
          case 1:
            v25 = 1;
            v53 = v192;
            goto LABEL_95;
          case 2:
LABEL_89:
            v25 = 1;
            goto LABEL_90;
          case 3:
            v25 = 1;
            goto LABEL_191;
          case 12:
            v25 = 1;
            v62 = Size;
            if ( !v170 )
            {
              *(_DWORD *)(v51 + 8) = Size;
              v53 = v192;
              goto LABEL_115;
            }
            RtlWriteULongToUser(v51 + 8, Size);
            v53 = v192;
            goto LABEL_144;
        }
        if ( v193 != 37 )
        {
          if ( v193 != 38 )
          {
LABEL_355:
            v18 = -1073741821;
            if ( NtfsStatusDebugFlags )
            {
              NtfsStatusTraceAndDebugInternal(0, 3221225475LL, 854258);
              v30 = 0;
            }
            v181 = -1073741821;
            v22 = (volatile signed __int32 *)v179;
            v34 = v191;
            break;
          }
          v25 = 1;
          v52 = v170;
          if ( v170 )
          {
            RtlWriteULong64ToUser(v51 + 72, v38);
            v30 = 0;
          }
          else
          {
            *(_QWORD *)(v51 + 72) = v38;
          }
          goto LABEL_91;
        }
        v25 = 1;
        if ( v170 )
        {
          RtlWriteULong64ToUser(v51 + 96, v38);
          v30 = 0;
        }
        else
        {
          *(_QWORD *)(v51 + 96) = v38;
        }
LABEL_191:
        if ( (*((_BYTE *)OtherFileName + 65) & 3) != 1 )
        {
LABEL_90:
          v52 = v170;
LABEL_91:
          v53 = v192;
          goto LABEL_92;
        }
        ShortName = NtfsQueryDirectoryGetShortName(a1, v202, v34, (__int64)&Entry, (__int64)&v172);
        v85 = ShortName;
        v30 = 0;
        if ( ShortName )
        {
          v86 = 2 * *(_BYTE *)(ShortName + 64);
          v87 = (_BYTE *)(v51 + 68);
          v52 = v170;
          if ( v170 )
          {
            LOBYTE(v84) = 2 * *(_BYTE *)(ShortName + 64);
            RtlWriteUCharToUser(v87, v84);
          }
          else
          {
            *v87 = v86;
          }
          v88 = (void *)(v85 + 66);
          v89 = (void *)(v51 + 70);
          if ( v170 )
            RtlCopyToUser(v89, v88, v86);
          else
            RtlCopyVolatileMemory(v89, v88, v86);
          v25 = 1;
          v30 = 0;
          goto LABEL_91;
        }
        if ( !v172 )
          goto LABEL_89;
        v34 = v191;
        if ( *(_QWORD *)(v191 + 56) )
        {
          v18 = 0;
          v181 = 0;
          v22 = (volatile signed __int32 *)v179;
          break;
        }
        NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 854069);
      }
      memset(Src, 0, sizeof(Src));
      v53 = v192;
      Src[1] = *(_QWORD *)v192;
      Src[2] = *(_QWORD *)(v192 + 24);
      v126 = *(_DWORD *)(v192 + 48) & 0xDAFFB7;
      LODWORD(Src[7]) = v126;
      Src[3] = *(_QWORD *)(v192 + 8);
      Src[4] = *(_QWORD *)(v192 + 16);
      if ( v178 )
        v126 = Src[7];
      if ( (*(_DWORD *)(v192 + 48) & 0x30000000) != 0 )
      {
        v126 |= 0x10u;
        LODWORD(Src[7]) = v126;
      }
      if ( !v126 )
        v126 = 128;
      Src[7] = __PAIR64__(Size, v126);
      v62 = Size;
      Src[5] = *(_QWORD *)(v192 + 40);
      Src[6] = *(_QWORD *)(v192 + 32);
      Src[8] = __PAIR64__(HIDWORD(v204), (unsigned int)v38);
      LODWORD(Src[11]) = *(_DWORD *)PoolWithTag;
      *(_OWORD *)&Src[9] = *(_OWORD *)((char *)PoolWithTag + 4);
      v25 = 1;
      if ( v170 )
        RtlCopyToUser((void *)v51, Src, v180);
      else
        RtlCopyVolatileMemory((void *)v51, Src, v180);
LABEL_144:
      v30 = 0;
      goto LABEL_115;
    }
    if ( v193 == 60 )
      goto LABEL_267;
    if ( v193 != 63 )
    {
      switch ( v193 )
      {
        case 'N':
          v25 = 1;
LABEL_136:
          LODWORD(v34) = (_DWORD)v179;
LABEL_137:
          v71 = v170;
          if ( v170 )
          {
            RtlWriteULong64ToUser(v51 + 72, v38);
            v71 = v170;
            v30 = 0;
          }
          else
          {
            *(_QWORD *)(v51 + 72) = v38;
          }
          v53 = v192;
          if ( (*(_DWORD *)(v192 + 48) & 0x400) == 0
            || ((v90 = *(_DWORD *)(v192 + 52), v91 = (unsigned int *)(v51 + 68), v71)
              ? (RtlWriteULongToUser(v91, v90), v30 = 0)
              : (__int64 *)(*v91 = v90),
                (*(_DWORD *)(v53 + 48) & 0x40000) == 0 || !(_DWORD)v38) )
          {
            v52 = v170;
            goto LABEL_92;
          }
          v210 = (unsigned int)v30;
          EaSize = NtfsQueryDirectoryGetEaSize(
                     a1,
                     v194,
                     v190,
                     v34,
                     v200,
                     (__int64)&v204,
                     v53,
                     (__int64)&Entry,
                     (__int64)&v175,
                     (__int64)&v210);
          v30 = 0;
          if ( EaSize )
          {
            v93 = (unsigned int *)(v51 + 64);
            v52 = v170;
            if ( v170 )
            {
              RtlWriteULongToUser(v93, v210);
              v30 = 0;
            }
            else
            {
              *v93 = v210;
            }
            goto LABEL_92;
          }
          break;
        case 'O':
          v25 = 1;
          if ( (*((_BYTE *)OtherFileName + 65) & 3) != 1 )
            goto LABEL_136;
          v167 = v34;
          LODWORD(v34) = (_DWORD)v179;
          v96 = NtfsQueryDirectoryGetShortName(a1, v202, v167, (__int64)&Entry, (__int64)&v172);
          v98 = v96;
          v30 = 0;
          if ( v96 )
          {
            v99 = 2 * *(_BYTE *)(v96 + 64);
            v100 = v201 + 80;
            if ( v170 )
            {
              LOBYTE(v97) = 2 * *(_BYTE *)(v96 + 64);
              RtlWriteUCharToUser(v100, v97);
            }
            else
            {
              *v100 = v99;
            }
            v101 = (void *)(v98 + 66);
            v51 = (__int64)v201;
            v102 = v201 + 82;
            if ( v170 )
              RtlCopyToUser(v102, v101, v99);
            else
              RtlCopyVolatileMemory(v102, v101, v99);
            v25 = 1;
            v30 = 0;
          }
          else
          {
            if ( v172 )
            {
              v34 = v191;
              if ( *(_QWORD *)(v191 + 56) )
              {
                v18 = 0;
                v181 = 0;
                v22 = (volatile signed __int32 *)v179;
                goto LABEL_450;
              }
              NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 853895);
            }
            v51 = (__int64)v201;
          }
          goto LABEL_137;
        case 'P':
          goto LABEL_256;
        case 'Q':
          if ( (*((_BYTE *)OtherFileName + 65) & 3) == 1 )
          {
            v168 = v34;
            LODWORD(v34) = (_DWORD)v179;
            v144 = NtfsQueryDirectoryGetShortName(a1, v202, v168, (__int64)&Entry, (__int64)&v172);
            v146 = v144;
            v30 = 0;
            if ( v144 )
            {
              v127 = 2 * *(_BYTE *)(v144 + 64);
              v128 = v201 + 96;
              if ( v170 )
              {
                LOBYTE(v145) = 2 * *(_BYTE *)(v144 + 64);
                RtlWriteUCharToUser(v128, v145);
              }
              else
              {
                *v128 = v127;
              }
              v129 = (void *)(v146 + 66);
              v51 = (__int64)v201;
              v130 = v201 + 98;
              if ( v170 )
                RtlCopyToUser(v130, v129, v127);
              else
                RtlCopyVolatileMemory(v130, v129, v127);
              v30 = 0;
            }
            else
            {
              if ( v172 )
              {
                v34 = v191;
                if ( *(_QWORD *)(v191 + 56) )
                {
                  v18 = 0;
                  v181 = 0;
                  v22 = (volatile signed __int32 *)v179;
                  goto LABEL_450;
                }
                NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 853978);
              }
              v51 = (__int64)v201;
            }
          }
          else
          {
LABEL_256:
            LODWORD(v34) = (_DWORD)v179;
          }
          v105 = v170;
          if ( v170 )
          {
            RtlWriteULong64ToUser(v51 + 72, v38);
            v105 = v170;
            v30 = 0;
          }
          else
          {
            *(_QWORD *)(v51 + 72) = v38;
          }
          if ( v105 )
          {
            RtlWriteULong64ToUser(v51 + 88, 0);
            v105 = v170;
            v30 = 0;
          }
          else
          {
            *(_QWORD *)(v51 + 88) = v30;
          }
          if ( v105 )
          {
            RtlWriteULong64ToUser(v51 + 80, v38);
            v105 = v170;
            v30 = 0;
          }
          else
          {
            *(_QWORD *)(v51 + 80) = v38;
          }
          v53 = v192;
          if ( (*(_DWORD *)(v192 + 48) & 0x400) == 0
            || ((v131 = *(_DWORD *)(v192 + 52), v132 = (unsigned int *)(v51 + 68), !v105)
              ? (__int64 *)(*v132 = v131)
              : (RtlWriteULongToUser(v132, v131), v30 = 0),
                (*(_DWORD *)(v53 + 48) & 0x40000) == 0 || !(_DWORD)v38) )
          {
LABEL_264:
            v52 = v170;
            goto LABEL_265;
          }
          v211 = (unsigned int)v30;
          v133 = NtfsQueryDirectoryGetEaSize(
                   a1,
                   v194,
                   v190,
                   v34,
                   v200,
                   (__int64)&v204,
                   v53,
                   (__int64)&Entry,
                   (__int64)&v175,
                   (__int64)&v211);
          v30 = 0;
          if ( v133 )
          {
            v110 = v211;
            goto LABEL_279;
          }
LABEL_442:
          v25 = 1;
          break;
        default:
          goto LABEL_355;
      }
      v31 = 1;
      v171 = 1;
      v183 = 1;
      v196 = 1;
      v173 = 0;
      v22 = (volatile signed __int32 *)v179;
      goto LABEL_62;
    }
    if ( (*((_BYTE *)OtherFileName + 65) & 3) != 1 )
    {
LABEL_267:
      LODWORD(v34) = (_DWORD)v179;
    }
    else
    {
      v169 = v34;
      LODWORD(v34) = (_DWORD)v179;
      v147 = NtfsQueryDirectoryGetShortName(a1, v202, v169, (__int64)&Entry, (__int64)&v172);
      v149 = v147;
      v30 = 0;
      if ( v147 )
      {
        v134 = 2 * *(_BYTE *)(v147 + 64);
        v135 = v201 + 88;
        if ( v170 )
        {
          LOBYTE(v148) = 2 * *(_BYTE *)(v147 + 64);
          RtlWriteUCharToUser(v135, v148);
        }
        else
        {
          *v135 = v134;
        }
        v136 = (void *)(v149 + 66);
        v51 = (__int64)v201;
        v137 = v201 + 90;
        if ( v170 )
          RtlCopyToUser(v137, v136, v134);
        else
          RtlCopyVolatileMemory(v137, v136, v134);
        v30 = 0;
      }
      else
      {
        if ( v172 )
        {
          v34 = v191;
          if ( *(_QWORD *)(v191 + 56) )
          {
            v18 = 0;
            v181 = 0;
            v22 = (volatile signed __int32 *)v179;
            break;
          }
          NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 853813);
        }
        v51 = (__int64)v201;
      }
    }
    v106 = v170;
    if ( v170 )
    {
      RtlWriteULong64ToUser(v51 + 80, 0);
      v106 = v170;
      v30 = 0;
    }
    else
    {
      *(_QWORD *)(v51 + 80) = v30;
    }
    if ( v106 )
    {
      RtlWriteULong64ToUser(v51 + 72, v38);
      v106 = v170;
      v30 = 0;
    }
    else
    {
      *(_QWORD *)(v51 + 72) = v38;
    }
    v53 = v192;
    if ( (*(_DWORD *)(v192 + 48) & 0x400) == 0 )
      goto LABEL_264;
    v107 = *(_DWORD *)(v192 + 52);
    v108 = (unsigned int *)(v51 + 68);
    if ( v106 )
    {
      RtlWriteULongToUser(v108, v107);
      v30 = 0;
    }
    else
    {
      *v108 = v107;
    }
    if ( (*(_DWORD *)(v53 + 48) & 0x40000) == 0 || !(_DWORD)v38 )
      goto LABEL_264;
    v209 = (unsigned int)v30;
    v109 = NtfsQueryDirectoryGetEaSize(
             a1,
             v194,
             v190,
             v34,
             v200,
             (__int64)&v204,
             v53,
             (__int64)&Entry,
             (__int64)&v175,
             (__int64)&v209);
    v30 = 0;
    if ( !v109 )
      goto LABEL_442;
    v110 = v209;
LABEL_279:
    v52 = v170;
    v111 = (unsigned int *)(v51 + 64);
    if ( v170 )
    {
      RtlWriteULongToUser(v111, v110);
      v30 = 0;
    }
    else
    {
      *v111 = v110;
    }
LABEL_265:
    v25 = 1;
LABEL_92:
    if ( (*(_DWORD *)(v53 + 48) & 0x400) != 0 )
    {
      if ( (unsigned int)(v193 - 60) <= 0x15 )
      {
        v54 = 3932169;
        if ( _bittest(&v54, v193 - 60) )
          goto LABEL_95;
      }
      v72 = *(_DWORD *)(v53 + 52);
    }
    else
    {
      v72 = *(unsigned __int16 *)(v53 + 52);
      v218 = v72;
      if ( v72 )
      {
        v95 = 4;
        if ( *(_WORD *)(v53 + 54) > 4u )
          v95 = *(unsigned __int16 *)(v53 + 54);
        v72 += v95;
        v218 = v72;
      }
    }
    v73 = (unsigned int *)(v51 + 64);
    if ( v52 )
    {
      RtlWriteULongToUser(v73, v72);
      v30 = 0;
    }
    else
    {
      *v73 = v72;
    }
LABEL_95:
    v55 = (_QWORD *)(v51 + 8);
    if ( v170 )
    {
      RtlWriteULong64ToUser(v55, *(_QWORD *)v53);
      v30 = 0;
    }
    else
    {
      *v55 = *(_QWORD *)v53;
    }
    v56 = (_QWORD *)(v51 + 16);
    if ( v170 )
    {
      RtlWriteULong64ToUser(v56, *(_QWORD *)(v53 + 24));
      v30 = 0;
    }
    else
    {
      *v56 = *(_QWORD *)(v53 + 24);
    }
    v205 = (int)v30;
    v57 = *(_DWORD *)(v53 + 48);
    v58 = v57 & 0xDAFFB7;
    v205 = v57 & 0xDAFFB7;
    if ( (v57 & 0x30000000) != 0 )
    {
      v58 = v57 & 0xDAFFA7 | 0x10u;
      v205 = v57 & 0xDAFFA7 | 0x10;
    }
    if ( !(_DWORD)v58 )
      v58 = 128;
    v205 = v58;
    if ( v170 )
    {
      RtlWriteULongToUser(v51 + 56, v58);
      v30 = 0;
    }
    else
    {
      *(_DWORD *)(v51 + 56) = v58;
    }
    v59 = (_QWORD *)(v51 + 24);
    v60 = *(_QWORD *)(v53 + 8);
    if ( v170 )
    {
      RtlWriteULong64ToUser(v59, v60);
      v30 = 0;
    }
    else
    {
      *v59 = v60;
    }
    v61 = (_QWORD *)(v51 + 32);
    if ( v170 )
    {
      RtlWriteULong64ToUser(v61, *(_QWORD *)(v53 + 16));
      v30 = 0;
    }
    else
    {
      *v61 = *(_QWORD *)(v53 + 16);
    }
    v62 = Size;
    if ( v170 )
    {
      RtlWriteULongToUser(v51 + 60, Size);
      v30 = 0;
    }
    else
    {
      *(_DWORD *)(v51 + 60) = Size;
    }
    v63 = (_QWORD *)(v51 + 40);
    if ( v170 )
    {
      RtlWriteULong64ToUser(v63, *(_QWORD *)(v53 + 40));
      v30 = 0;
    }
    else
    {
      *v63 = *(_QWORD *)(v53 + 40);
    }
    v64 = (_QWORD *)(v51 + 48);
    if ( v170 )
    {
      RtlWriteULong64ToUser(v64, *(_QWORD *)(v53 + 32));
      goto LABEL_144;
    }
    *v64 = *(_QWORD *)(v53 + 32);
LABEL_115:
    if ( v208 < v62 + v180 )
    {
      v18 = -2147483643;
      v181 = -2147483643;
    }
    v65 = v199;
    v22 = (volatile signed __int32 *)v179;
    if ( v199 && v53 != *(_QWORD *)(v190 + 184) + 128LL && *(_DWORD *)v202 == *((_DWORD *)v179 + 44) )
    {
      v150 = v194;
      ExAcquirePushLockSharedEx(v194 + 656, 0);
      _InterlockedDecrement((volatile signed __int32 *)(v65 + 28));
      ExReleasePushLockEx(v150 + 656, 0);
      NtfsReleaseFcbEx(a1, v65, 0);
      v30 = 0;
      v199 = 0;
    }
    v66 = v197;
    v67 = v197 - v212;
    v68 = (_DWORD *)(v212 + v214);
    if ( v170 == (_BYTE)v30 )
    {
      *v68 = v67;
    }
    else
    {
      RtlWriteULongToUser(v68, v67);
      v66 = v197;
      v30 = 0;
    }
    v34 = v191;
    v69 = v180;
    *(_QWORD *)(v191 + 56) = v180 + *(_QWORD *)&Name.Length + ((*(_QWORD *)(v191 + 56) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL);
    if ( v18 >= 0 )
    {
      v212 = v66;
      v197 = ((v69 + v213 + 7) & 0xFFFFFFF8) + v66;
      continue;
    }
    break;
  }
LABEL_450:
  v151 = *(_QWORD *)(a1 + 144);
  if ( a1 != v151 && *(_BYTE *)(a1 + 32) == 3 )
    v151 = a1;
  v152 = *(_DWORD *)(v151 + 24);
  if ( v152 < 0 )
  {
    NtfsRaiseStatusInternal(a1, v152, 0, 0, (__int64)v30);
    __debugbreak();
  }
  if ( v18 < 0 && *(_DWORD *)(v151 + 28) != (_DWORD)v30 )
  {
    NtfsRaiseStatusInternal(a1, v18, 0, 0, (__int64)v30);
    __debugbreak();
  }
  if ( *(_DWORD *)(a1 + 256) != (_DWORD)v30 || *(_DWORD *)(a1 + 260) != (_DWORD)v30 )
  {
    NtfsWriteUsnJournalChanges(a1);
    NtfsCommitCurrentTransaction(a1);
    v155 = *(_DWORD *)(v151 + 24);
    LOBYTE(v30) = 0;
    if ( v155 < 0 )
    {
      NtfsRaiseStatusInternal(a1, v155, 0, 0, 0);
      __debugbreak();
    }
  }
  if ( v18 >= 0 || (unsigned int)(v18 + 2147483643) <= 1 || v18 == -1073741809 )
  {
    NtfsUpdateFileTimestampsForAccess(*(_QWORD *)(v221 + 48), *(_QWORD *)(v190 + 184), v22);
    LOBYTE(v30) = 0;
  }
  if ( v174 != (_BYTE)v30 )
  {
    NtfsReleaseVcb(a1, v194);
    *(_DWORD *)(a1 + 12) &= ~0x200u;
    LOBYTE(v30) = 0;
  }
  v157 = Entry;
  if ( Entry )
  {
    NtfsCleanupIndexContext(a1, Entry);
    ExFreeToLookasideListEx(&NtfsIndexContextLookasideList, v157);
    LOBYTE(v30) = 0;
  }
  if ( v200 )
  {
    if ( *(_WORD *)v200 == 1794 )
      v164 = (struct _ERESOURCE *)(*(_QWORD *)(v200 + 104) + 64LL);
    else
      v164 = *(struct _ERESOURCE **)(v200 + 8);
    ExReleaseResourceLite(v164);
    LOBYTE(v30) = 0;
  }
  v158 = v199;
  if ( v199 )
  {
    v165 = v194;
    ExAcquirePushLockSharedEx(v194 + 656, 0);
    _InterlockedDecrement((volatile signed __int32 *)(v158 + 28));
    ExReleasePushLockEx(v165 + 656, 0);
    NtfsReleaseFcbEx(a1, v158, 0);
    LOBYTE(v30) = 0;
  }
  v159 = v190;
  if ( v175 != (_BYTE)v30 )
    NtfsReleaseFcbEx(a1, *(_QWORD *)(v190 + 184), 0);
  NtfsCleanupAfterEnumeration(a1, v22);
  if ( v184 )
    TxfDereferenceForDefaultReader(v22);
  if ( v185 )
    NtfsReleaseIndexCcb(v159, v22);
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
  if ( v22 != v226 )
    DeallocateLocalIndexCcb((PVOID)v22);
  if ( NtfsStatusDebugFlags
    && v18
    && v18 != 294
    && (unsigned int)(v18 - 298) > 1
    && (unsigned int)v18 < 0xFFFFFFED
    && v18 != -1073741608
    && v18 != -1073741802
    && v18 != -1073741807
    && (unsigned int)(v18 + 2147483643) > 1
    && v18 != 259 )
  {
    NtfsStatusTraceAndDebugInternal(a1, (unsigned int)v18, 854459);
  }
  LOBYTE(v160) = v34 != 0;
  NtfsExtendedCompleteRequestInternal(a1, v34, (unsigned int)v18, v160, v18 >= 0);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1401a7b50  push    rbx
0x1401a7b52  push    rsi
0x1401a7b53  push    rdi
0x1401a7b54  push    r12
0x1401a7b56  push    r13
0x1401a7b58  push    r14
0x1401a7b5a  push    r15
0x1401a7b5c  sub     rsp, 220h
0x1401a7b63  mov     rax, cs:__security_cookie
0x1401a7b6a  xor     rax, rsp
0x1401a7b6d  mov     [rsp+258h+var_48], rax
0x1401a7b75  mov     rax, r9
0x1401a7b78  mov     [rsp+258h+var_1D8], rax
0x1401a7b80  mov     [rsp+258h+var_1B8], r8
0x1401a7b88  mov     r12, rdx
0x1401a7b8b  mov     [rsp+258h+var_1D0], rdx
0x1401a7b93  mov     r13, rcx
0x1401a7b96  mov     [rsp+258h+var_138], rcx
0x1401a7b9e  mov     [rsp+258h+var_F0], r8
0x1401a7ba6  mov     [rsp+258h+var_E0], rax
0x1401a7bae  mov     rdx, [rsp+258h+arg_20]
0x1401a7bb6  mov     [rsp+258h+var_1F8], rdx
0x1401a7bbb  mov     [rsp+258h+var_E8], rdx
0x1401a7bc3  xor     r10d, r10d
0x1401a7bc6  mov     [rsp+258h+Entry], r10
0x1401a7bce  mov     byte ptr [rsp+258h+var_205+3], r10b
0x1401a7bd3  mov     r8, [r12+0B8h]
0x1401a7bdb  mov     [rsp+258h+var_100], r8
0x1401a7be3  mov     rsi, [r8+10h]
0x1401a7be7  mov     r14b, [r8+2]
0x1401a7beb  mov     cl, r14b
0x1401a7bee  and     cl, 2
0x1401a7bf1  mov     [rsp+258h+var_1B0], cl
0x1401a7bf8  mov     bl, r14b
0x1401a7bfb  and     bl, 10h
0x1401a7bfe  mov     eax, [r8+8]
0x1401a7c02  mov     [rsp+258h+var_160], eax
0x1401a7c09  mov     eax, [r8+18h]
0x1401a7c0d  mov     [rsp+258h+var_1C0], eax
0x1401a7c14  test    rsi, rsi
0x1401a7c17  jnz     loc_1401AA361
0x1401a7c1d  mov     r15b, r10b
0x1401a7c20  mov     edi, 1
0x1401a7c25  mov     eax, [r13+0Ch]
0x1401a7c29  test    dil, al
0x1401a7c2c  jz      loc_1401AA465
0x1401a7c32  mov     [rsp+258h+var_D8], rdx
0x1401a7c3a  test    bl, bl
0x1401a7c3c  jnz     loc_1401AA4A2
0x1401a7c42  mov     r12b, r14b
0x1401a7c45  and     r12b, dil
0x1401a7c48  and     r14b, 4
0x1401a7c4c  mov     [rsp+258h+P], r10
0x1401a7c54  mov     [rsp+258h+var_1A0], r10
0x1401a7c5c  mov     [rsp+258h+var_198], r10
0x1401a7c64  mov     [rsp+258h+var_180], r10
0x1401a7c6c  mov     [rsp+258h+var_207], r10b
0x1401a7c71  mov     [rsp+258h+var_1E7], r10b
0x1401a7c76  mov     byte ptr [rsp+258h+var_205+2], r10b
0x1401a7c7b  mov     [rsp+258h+var_1E5], r10b
0x1401a7c80  mov     al, r10b
0x1401a7c83  mov     [rsp+258h+var_1E6], al
0x1401a7c87  mov     byte ptr [rsp+258h+Size+6], al
0x1401a7c8b  cmp     [rsp+258h+var_160], 10000h
0x1401a7c96  jnb     loc_1401AA4CC
0x1401a7c9c  mov     rax, [rsp+258h+var_100]
0x1401a7ca4  mov     rax, [rax+30h]
0x1401a7ca8  mov     ecx, [rax+50h]
0x1401a7cab  test    cl, 2
0x1401a7cae  jz      loc_1401AA090
0x1401a7cb4  mov     ecx, [rsp+258h+var_1C0]
0x1401a7cbb  cmp     ecx, 32h ; '2'
0x1401a7cbe  jg      loc_1401A7D62
0x1401a7cc4  jz      loc_1401AA0D4
0x1401a7cca  sub     ecx, 1
0x1401a7ccd  jz      loc_1401A9FE8
0x1401a7cd3  sub     ecx, 1
0x1401a7cd6  jz      loc_1401A9FDA
0x1401a7cdc  sub     ecx, 1
0x1401a7cdf  jz      loc_1401A9F1F
0x1401a7ce5  sub     ecx, 9
0x1401a7ce8  jnz     loc_1401A9E43
0x1401a7cee  mov     dword ptr [rsp+258h+var_1F0], 0Ch
0x1401a7cf6  mov     edi, 44h ; 'D'
0x1401a7cfb  mov     r9d, 3
0x1401a7d01  test    bl, bl
0x1401a7d03  jnz     short loc_1401A7D18
0x1401a7d05  mov     r8, [rsp+258h+var_1F8]
0x1401a7d0a  cmp     qword ptr [r8+98h], 0
0x1401a7d12  jnz     loc_1401A9F4D
0x1401a7d18  mov     r8b, 1
0x1401a7d1b  mov     byte ptr [rsp+258h+var_205+4], r8b
0x1401a7d20  test    r15b, r15b
0x1401a7d23  jz      short loc_1401A7D9E
0x1401a7d25  movzx   ebx, word ptr [rsi]
0x1401a7d28  mov     eax, 1FEh
0x1401a7d2d  mov     edi, 1
0x1401a7d32  cmp     bx, ax
0x1401a7d35  jbe     loc_1401A9EA8
0x1401a7d3b  test    r8b, r8b
0x1401a7d3e  jz      loc_1401AA002
0x1401a7d44  mov     al, cs:NtfsStatusDebugFlags
0x1401a7d4a  mov     esi, 0C0000033h
0x1401a7d4f  test    al, al
0x1401a7d51  jz      loc_1401A9DA7
0x1401a7d57  mov     r8d, 0D0361h
0x1401a7d5d  jmp     loc_1401A9D9E
0x1401a7d62  sub     ecx, 3Ch ; '<'
0x1401a7d65  jz      loc_1401A9FF5
0x1401a7d6b  mov     r9d, 3
0x1401a7d71  sub     ecx, r9d
0x1401a7d74  jz      loc_1401AA123
0x1401a7d7a  sub     ecx, 0Fh
0x1401a7d7d  jz      loc_1401A9F2C
0x1401a7d83  sub     ecx, 1
0x1401a7d86  jnz     loc_1401A9E5E
0x1401a7d8c  mov     dword ptr [rsp+258h+var_1F0], 6Ah ; 'j'
0x1401a7d94  mov     edi, 44h ; 'D'
0x1401a7d99  jmp     loc_1401A7D01
0x1401a7d9e  mov     ecx, cs:PoolType
0x1401a7da4  or      ecx, 10h; PoolType
0x1401a7da7  mov     r8d, 6446744Eh; Tag
0x1401a7dad  mov     rdx, rdi; NumberOfBytes
0x1401a7db0  call    cs:__imp_ExAllocatePoolWithTag
0x1401a7db7  nop     dword ptr [rax+rax+00h]
0x1401a7dbc  mov     rbx, rax
0x1401a7dbf  mov     [rsp+258h+var_168], rax
0x1401a7dc7  mov     rax, [rsp+258h+var_1D8]
0x1401a7dcf  mov     rax, [rax+0B8h]
0x1401a7dd6  mov     rcx, [rax+8]
0x1401a7dda  mov     [rbx], rcx
0x1401a7ddd  mov     dword ptr [rbx+40h], 2A0001h
0x1401a7de4  mov     r15d, 2Ah ; '*'
0x1401a7dea  mov     r8b, byte ptr [rsp+258h+var_205+4]
0x1401a7def  test    r8b, r8b
0x1401a7df2  jz      loc_1401AA147
0x1401a7df8  xorps   xmm0, xmm0
0x1401a7dfb  movups  xmmword ptr [rsp+258h+Name.Length], xmm0
0x1401a7e03  mov     r14, [rsp+258h+var_1F8]
0x1401a7e08  mov     ebx, 1000000h
0x1401a7e0d  test    r8b, r8b
0x1401a7e10  jz      loc_1401AA165
0x1401a7e16  lea     rsi, [r14+4]
0x1401a7e1a  mov     eax, [rsi]
0x1401a7e1c  test    ebx, eax
0x1401a7e1e  jz      short loc_1401A7E27
0x1401a7e20  lock and dword ptr [rsi], 0FEFFFFFFh
0x1401a7e27  mov     rbx, [rsp+258h+var_168]
0x1401a7e2f  mov     [r14+98h], rbx
0x1401a7e36  mov     [r14+90h], edi
0x1401a7e3d  movzx   eax, byte ptr [rbx+40h]
0x1401a7e41  add     ax, ax
0x1401a7e44  mov     [rsp+258h+Name.Length], ax
0x1401a7e4c  mov     [rsp+258h+Name.MaximumLength], ax
0x1401a7e54  lea     rax, [rbx+42h]
0x1401a7e58  mov     [rsp+258h+Name.Buffer], rax
0x1401a7e60  mov     eax, [r14+4]
0x1401a7e64  mov     edi, 300h
0x1401a7e69  test    edi, eax
0x1401a7e6b  jz      short loc_1401A7E76
0x1401a7e6d  lock and dword ptr [r14+4], 0FFFFFCFFh
0x1401a7e76  mov     rax, [rsp+258h+var_1D8]
0x1401a7e7e  mov     rcx, [rsp+258h+var_1B8]
0x1401a7e86  cmp     rax, [rcx+20h]
0x1401a7e8a  jz      short loc_1401A7EC5
0x1401a7e8c  lea     rcx, [rsp+258h+Name]; Name
0x1401a7e94  call    cs:__imp_FsRtlDoesNameContainWildCards
0x1401a7e9b  nop     dword ptr [rax+rax+00h]
0x1401a7ea0  test    al, al
0x1401a7ea2  jnz     loc_1401A9F95
0x1401a7ea8  movzx   eax, [rsp+258h+Name.Length]
0x1401a7eb0  cmp     ax, cs:word_140092198
0x1401a7eb7  jz      loc_1401AA1A2
0x1401a7ebd  mov     rcx, [rsp+258h+var_1B8]
0x1401a7ec5  mov     rax, [rsp+258h+var_1D0]
0x1401a7ecd  mov     qword ptr [rax+38h], 0
0x1401a7ed5  mov     byte ptr [rsp+258h+Size+4], 0
0x1401a7eda  test    dword ptr [r13+0Ch], 200h
0x1401a7ee2  jnz     short loc_1401A7EF2
0x1401a7ee4  cmp     qword ptr [r14+0B0h], 0
0x1401a7eec  jz      loc_1401A8B82
0x1401a7ef2  mov     esi, 3C0009h
0x1401a7ef7  mov     edi, 1
0x1401a7efc  mov     r8b, dil
0x1401a7eff  mov     rdx, rcx
0x1401a7f02  mov     rcx, r13
0x1401a7f05  call    NtfsAcquireSharedVcb
0x1401a7f0a  mov     byte ptr [rsp+258h+var_205+2], dil
0x1401a7f0f  cmp     qword ptr [r14+0B0h], 0
0x1401a7f17  jnz     loc_1401A90E5
0x1401a7f1d  xor     r9d, r9d
0x1401a7f20  mov     rax, [rsp+258h+var_1D8]
0x1401a7f28  mov     r8, rax
0x1401a7f2b  mov     rdx, [rax+0B8h]
0x1401a7f32  mov     rcx, r13
0x1401a7f35  call    NtfsAcquireSharedFcb
0x1401a7f3a  mov     byte ptr [rsp+258h+var_205+3], dil
0x1401a7f3f  cmp     byte ptr [rsp+258h+var_205+2], 0
0x1401a7f44  jnz     loc_1401A88AF
0x1401a7f4a  lea     rax, [r14+4]
0x1401a7f4e  mov     [rsp+258h+var_110], rax
0x1401a7f56  mov     eax, [rax]
0x1401a7f58  test    dil, al
0x1401a7f5b  jnz     loc_1401A8769
0x1401a7f61  mov     byte ptr [rsp+258h+var_205+5], 0
0x1401a7f66  mov     [rsp+258h+var_238], 0
0x1401a7f6f  xor     r9d, r9d
0x1401a7f72  xor     r8d, r8d
0x1401a7f75  mov     rax, [rsp+258h+var_100]
0x1401a7f7d  mov     rdx, [rax+30h]
0x1401a7f81  mov     rcx, r13
0x1401a7f84  call    TxfSetupTransactionContextFromCcb
0x1401a7f89  mov     esi, eax
0x1401a7f8b  mov     dword ptr [rsp+258h+var_1F0+4], eax
0x1401a7f8f  test    eax, eax
0x1401a7f91  jnz     loc_1401A91E4
0x1401a7f97  mov     rcx, [r14+50h]
0x1401a7f9b  test    rcx, rcx
0x1401a7f9e  jnz     loc_1401A9667
0x1401a7fa4  xor     al, al
0x1401a7fa6  mov     [rsp+258h+var_1E6], al
0x1401a7faa  mov     byte ptr [rsp+258h+Size+6], al
0x1401a7fae  mov     rax, [rsp+258h+var_1D8]
0x1401a7fb6  test    dword ptr [rax+200h], 10000h
0x1401a7fc0  jnz     loc_1401A924C
0x1401a7fc6  mov     edx, 10h
0x1401a7fcb  mov     rcx, [rsp+258h+var_1D0]
0x1401a7fd3  call    NtfsMapUserBuffer
0x1401a7fd8  mov     [rsp+258h+var_140], rax
0x1401a7fe0  mov     rax, [rsp+258h+var_1D0]
0x1401a7fe8  xor     r10d, r10d
0x1401a7feb  cmp     [rax+8], r10
0x1401a7fef  jnz     loc_1401A9684
0x1401a7ff5  mov     al, [rax+40h]
0x1401a7ff8  mov     [rsp+258h+var_208], al
0x1401a7ffc  cmp     byte ptr [rsp+258h+var_205+4], r10b
0x1401a8001  jz      loc_1401A89B6
0x1401a8007  mov     [rsp+258h+var_206], dil
0x1401a800c  mov     byte ptr [rsp+258h+var_205+1], r10b
0x1401a8011  mov     eax, [r14+4]
0x1401a8015  test    eax, 0C00h
0x1401a801a  jz      short loc_1401A8025
0x1401a801c  lock and dword ptr [r14+4], 0FFFFF3FFh
0x1401a8025  mov     [rsp+258h+var_14C], r10d
0x1401a802d  mov     [rsp+258h+var_1AC], r10d
0x1401a8035  cmp     [rbx+42h], r15w
0x1401a803a  jz      loc_1401A8AFD
0x1401a8040  mov     byte ptr [rsp+258h+Size+5], r10b
0x1401a8045  mov     r15b, [rsp+258h+var_206]
0x1401a804a  mov     r12d, 0FFFEh
0x1401a8050  mov     ecx, 702h
0x1401a8055  mov     [rsp+258h+var_188], r10
0x1401a805d  mov     [rsp+258h+var_108], r10
0x1401a8065  mov     [rsp+258h+var_1C8], r10
0x1401a806d  mov     [rsp+258h+var_178], r10
0x1401a8075  mov     dword ptr [rsp+258h+Size], r10d
0x1401a807a  mov     byte ptr [rsp+258h+var_205], r10b
0x1401a807f  mov     rax, [rsp+258h+var_198]
0x1401a8087  test    rax, rax
0x1401a808a  jnz     loc_1401A8C7F
0x1401a8090  mov     rax, [rsp+258h+var_180]
0x1401a8098  test    rax, rax
0x1401a809b  jnz     loc_1401A970E
0x1401a80a1  mov     rbx, [rsp+258h+Entry]
0x1401a80a9  test    rbx, rbx
0x1401a80ac  jnz     loc_1401A8624
0x1401a80b2  mov     r12, r10
0x1401a80b5  test    r15b, r15b
0x1401a80b8  jnz     loc_1401A86A9
0x1401a80be  mov     [rsp+258h+var_230], rax
0x1401a80c3  lea     rax, [rsp+258h+var_188]
0x1401a80cb  mov     [rsp+258h+var_238], rax; int
0x1401a80d0  mov     r9b, byte ptr [rsp+258h+var_205+1]
0x1401a80d5  mov     r8, [rsp+258h+var_1D8]
0x1401a80dd  mov     rdx, r14
0x1401a80e0  mov     rcx, r13
0x1401a80e3  call    NtfsContinueIndexEnumeration
0x1401a80e8  mov     ecx, eax
0x1401a80ea  shr     ecx, 1Fh
0x1401a80ed  xor     cl, dil
0x1401a80f0  mov     r14b, cl
0x1401a80f3  mov     [rsp+258h+var_1E8], cl
0x1401a80f7  xor     r10d, r10d
0x1401a80fa  mov     ebx, r10d
0x1401a80fd  cmp     eax, 0C0000225h
0x1401a8102  cmovnz  ebx, eax
0x1401a8105  test    ebx, ebx
0x1401a8107  js      loc_1401A92E5
0x1401a810d  cmp     [rsp+258h+var_1B0], r10b
0x1401a8115  jnz     loc_1401A85B1
0x1401a811b  mov     rbx, r10
0x1401a811e  mov     [rsp+258h+var_178], rbx
0x1401a8126  lea     r15, NtfsDotDotName
0x1401a812d  mov     [rsp+258h+var_108], r15
0x1401a8135  mov     rax, [rsp+258h+var_1D8]
0x1401a813d  mov     rdx, [rax+0B8h]
0x1401a8144  lea     r8, [rdx+80h]
0x1401a814b  mov     [rsp+258h+var_1C8], r8
0x1401a8153  mov     byte ptr [rsp+258h+var_205+1], r10b
0x1401a8158  mov     byte ptr [rsp+258h+var_205+6], r10b
  ... truncated ...
```
