# TrustLabelAceHelpers::IsFileSystemObjectTrustable(ushort const *,void *,bool,bool,bool,bool *)

- ea: `0x1800b31d0`
- end: `0x1800b4e1f`
- name: `?IsFileSystemObjectTrustable@TrustLabelAceHelpers@@SAJPEBGPEAX_N22PEA_N@Z`
- size: `7247`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void *, bool, bool, bool, bool *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002af0c`
- `0x18004e3fc`

## callees

- `0x180013cb0`
- `0x1800222a0`
- `0x1800486a0`
- `0x180048f30`
- `0x180049440`
- `0x18004cb70`
- `0x18004df24`
- `0x1800b31b0`
- `0x1800b31d0`
- `0x1800b4e28`
- `0x1800b4ee8`
- `0x1800b5f1c`
- `0x180188eb9`
- `0x180197010`

## import_xrefs

- `ntdll!NtGetCachedSigningLevel` at `0x18019305d`
- `ntdll!NtGetCachedSigningLevel` at `0x18019305d`
- `ntdll!NtCompareSigningLevels` at `0x18019306e`
- `ntdll!NtCompareSigningLevels` at `0x18019306e`
- `ntdll!RtlFreeHeap` at `0x1800b342a`
- `ntdll!RtlFreeHeap` at `0x1800b3486`
- `ntdll!RtlFreeHeap` at `0x1800b352b`
- `ntdll!RtlFreeHeap` at `0x1800b392f`
- `ntdll!RtlFreeHeap` at `0x1800b3a1a`
- `ntdll!RtlFreeHeap` at `0x1800b3ac5`
- `ntdll!RtlFreeHeap` at `0x1800b3d79`
- `ntdll!RtlFreeHeap` at `0x1800b3db1`
- `ntdll!RtlFreeHeap` at `0x1800b3dd6`
- `ntdll!RtlFreeHeap` at `0x1800b47cf`
- `ntdll!RtlFreeHeap` at `0x1800b4807`
- `ntdll!RtlFreeHeap` at `0x1800b482c`
- `ntdll!RtlFreeHeap` at `0x1800b4890`
- `ntdll!RtlFreeHeap` at `0x1800b48c7`
- `ntdll!RtlFreeHeap` at `0x1800b48eb`
- `ntdll!RtlFreeHeap` at `0x1800b4912`
- `ntdll!RtlFreeHeap` at `0x1800b4949`
- `ntdll!RtlFreeHeap` at `0x1800b496d`
- `ntdll!RtlFreeHeap` at `0x1800b4994`
- `ntdll!RtlFreeHeap` at `0x1800b49c7`
- `ntdll!RtlFreeHeap` at `0x1800b49e7`
- `ntdll!RtlFreeHeap` at `0x1800b4a0a`
- `ntdll!RtlFreeHeap` at `0x1800b4a3d`
- `ntdll!RtlFreeHeap` at `0x1800b4a5d`
- `ntdll!RtlFreeHeap` at `0x1800b4b07`
- `ntdll!RtlFreeHeap` at `0x1800b4b2e`
- `ntdll!RtlFreeHeap` at `0x1800b4beb`
- `ntdll!RtlFreeHeap` at `0x1800b4c25`
- `ntdll!RtlFreeHeap` at `0x1800b4d13`
- `ntdll!RtlFreeHeap` at `0x1800b4d2d`
- `ntdll!RtlFreeHeap` at `0x1800b4d4f`
- `ntdll!RtlFreeHeap` at `0x1800b4d74`
- `ntdll!RtlFreeHeap` at `0x1800b4db3`
- `ntdll!RtlFreeHeap` at `0x1800b4dd0`
- `ntdll!RtlFreeHeap` at `0x1800b4ded`
- `ntdll!RtlFreeHeap` at `0x1800b342a`
- `ntdll!RtlFreeHeap` at `0x1800b3486`
- `ntdll!RtlFreeHeap` at `0x1800b352b`
- `ntdll!RtlFreeHeap` at `0x1800b392f`
- `ntdll!RtlFreeHeap` at `0x1800b3a1a`
- `ntdll!RtlFreeHeap` at `0x1800b3ac5`
- `ntdll!RtlFreeHeap` at `0x1800b3d79`
- `ntdll!RtlFreeHeap` at `0x1800b3db1`
- `ntdll!RtlFreeHeap` at `0x1800b3dd6`
- `ntdll!RtlFreeHeap` at `0x1800b47cf`
- `ntdll!RtlFreeHeap` at `0x1800b4807`
- `ntdll!RtlFreeHeap` at `0x1800b482c`
- `ntdll!RtlFreeHeap` at `0x1800b4890`
- `ntdll!RtlFreeHeap` at `0x1800b48c7`
- `ntdll!RtlFreeHeap` at `0x1800b48eb`
- `ntdll!RtlFreeHeap` at `0x1800b4912`
- `ntdll!RtlFreeHeap` at `0x1800b4949`
- `ntdll!RtlFreeHeap` at `0x1800b496d`
- `ntdll!RtlFreeHeap` at `0x1800b4994`
- `ntdll!RtlFreeHeap` at `0x1800b49c7`
- `ntdll!RtlFreeHeap` at `0x1800b49e7`
- `ntdll!RtlFreeHeap` at `0x1800b4a0a`
- `ntdll!RtlFreeHeap` at `0x1800b4a3d`
- `ntdll!RtlFreeHeap` at `0x1800b4a5d`
- `ntdll!RtlFreeHeap` at `0x1800b4b07`
- `ntdll!RtlFreeHeap` at `0x1800b4b2e`
- `ntdll!RtlFreeHeap` at `0x1800b4beb`
- `ntdll!RtlFreeHeap` at `0x1800b4c25`
- `ntdll!RtlFreeHeap` at `0x1800b4d13`
- `ntdll!RtlFreeHeap` at `0x1800b4d2d`
- `ntdll!RtlFreeHeap` at `0x1800b4d4f`
- `ntdll!RtlFreeHeap` at `0x1800b4d74`
- `ntdll!RtlFreeHeap` at `0x1800b4db3`
- `ntdll!RtlFreeHeap` at `0x1800b4dd0`
- `ntdll!RtlFreeHeap` at `0x1800b4ded`
- `ntdll!RtlAllocateHeap` at `0x1800b32c4`
- `ntdll!RtlAllocateHeap` at `0x1800b3364`
- `ntdll!RtlAllocateHeap` at `0x1800b33a8`
- `ntdll!RtlAllocateHeap` at `0x1800b38f9`
- `ntdll!RtlAllocateHeap` at `0x1800b39b2`
- `ntdll!RtlAllocateHeap` at `0x1800b3a8f`
- `ntdll!RtlAllocateHeap` at `0x1800b3ccc`
- `ntdll!RtlAllocateHeap` at `0x1800b3e07`
- `ntdll!RtlAllocateHeap` at `0x1800b3e9d`
- `ntdll!RtlAllocateHeap` at `0x1800b3eed`
- `ntdll!RtlAllocateHeap` at `0x1800b4075`
- `ntdll!RtlAllocateHeap` at `0x1800b40cd`
- `ntdll!RtlAllocateHeap` at `0x1800b4124`
- `ntdll!RtlAllocateHeap` at `0x1800b41ca`
- `ntdll!RtlAllocateHeap` at `0x1800b4667`
- `ntdll!RtlAllocateHeap` at `0x1800b32c4`
- `ntdll!RtlAllocateHeap` at `0x1800b3364`
- `ntdll!RtlAllocateHeap` at `0x1800b33a8`
- `ntdll!RtlAllocateHeap` at `0x1800b38f9`
- `ntdll!RtlAllocateHeap` at `0x1800b39b2`
- `ntdll!RtlAllocateHeap` at `0x1800b3a8f`
- `ntdll!RtlAllocateHeap` at `0x1800b3ccc`
- `ntdll!RtlAllocateHeap` at `0x1800b3e07`
- `ntdll!RtlAllocateHeap` at `0x1800b3e9d`
- `ntdll!RtlAllocateHeap` at `0x1800b3eed`
- `ntdll!RtlAllocateHeap` at `0x1800b4075`
- `ntdll!RtlAllocateHeap` at `0x1800b40cd`
- `ntdll!RtlAllocateHeap` at `0x1800b4124`
- `ntdll!RtlAllocateHeap` at `0x1800b41ca`
- `ntdll!RtlAllocateHeap` at `0x1800b4667`

## string_xrefs

- `0x180192af7`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall TrustLabelAceHelpers::IsFileSystemObjectTrustable(
        const unsigned __int16 *a1,
        void *a2,
        bool a3,
        __int64 a4,
        bool a5,
        bool *a6)
{
  bool *v6; // rdi
  void *v7; // r14
  bool v8; // al
  Common *FileW; // rax
  const char *v11; // r9
  Common *v12; // rbx
  unsigned __int8 *Heap; // rax
  unsigned __int8 *v14; // r13
  int v15; // esi
  _QWORD *v16; // rax
  PVOID v17; // rdi
  unsigned __int64 v18; // r15
  __int128 k; // rax
  unsigned int *v20; // r12
  int v21; // r15d
  unsigned int v22; // r15d
  PVOID v23; // rcx
  _QWORD *v24; // rsi
  int v25; // r15d
  int v26; // r13d
  unsigned __int64 v27; // rbx
  int v28; // edx
  int v29; // esi
  int v30; // edi
  unsigned __int8 *v31; // rax
  int v32; // esi
  int v33; // edi
  int v34; // r8d
  int v35; // r11d
  int v36; // r9d
  int v37; // r11d
  int v38; // r10d
  int v39; // r9d
  unsigned int v40; // r8d
  int v41; // edx
  int v42; // r8d
  int v43; // r9d
  int v44; // r10d
  int v45; // r8d
  unsigned int v46; // r9d
  unsigned int v47; // r10d
  int v48; // r8d
  int v49; // r9d
  int v50; // r10d
  int v51; // r8d
  int v52; // r9d
  int v53; // r11d
  int v54; // r8d
  int v55; // r10d
  unsigned int v56; // r9d
  int v57; // r11d
  int v58; // r8d
  int v59; // r10d
  unsigned int v60; // r11d
  int v61; // edx
  int v62; // r10d
  _BYTE *v63; // r12
  unsigned __int8 v64; // al
  unsigned __int8 *v65; // rsi
  _QWORD *v66; // r14
  unsigned __int64 v67; // r15
  char *v68; // rdx
  _DWORD *v69; // rax
  int v70; // r15d
  int v71; // eax
  unsigned int v72; // ecx
  unsigned int v73; // ecx
  unsigned int v74; // eax
  void *v75; // r8
  unsigned int *v76; // rax
  unsigned __int64 v77; // rcx
  unsigned __int64 v78; // r8
  __int64 v79; // r9
  char *v80; // rcx
  __int64 v81; // r10
  SIZE_T v82; // rcx
  unsigned int v83; // ecx
  unsigned int *v84; // rax
  unsigned int v85; // r11d
  unsigned int v86; // ecx
  __int64 v87; // rdi
  void *v88; // r8
  SIZE_T v89; // rax
  void *v90; // r8
  void *v91; // r8
  _QWORD *v92; // rax
  void *v93; // rsi
  const void *v94; // rsi
  unsigned int v95; // eax
  unsigned int v96; // r14d
  PVOID v97; // rax
  void *v98; // rsi
  unsigned int v99; // eax
  unsigned int v100; // r14d
  PVOID v101; // rax
  int v102; // ecx
  int v103; // ecx
  WCHAR *v104; // r10
  unsigned __int8 v105; // dl
  SIZE_T v106; // r11
  unsigned int v107; // r9d
  SIZE_T j; // rax
  unsigned int v109; // eax
  unsigned int v110; // r14d
  PVOID v111; // rax
  unsigned int v112; // edx
  PVOID v113; // rcx
  _OWORD *v114; // rcx
  _QWORD *v115; // rax
  SIZE_T v116; // rcx
  bool v117; // sf
  int v118; // ecx
  unsigned int m; // ecx
  unsigned int ii; // ecx
  _DWORD *v121; // rcx
  unsigned int *v122; // rdx
  _DWORD *v123; // rcx
  unsigned int *v124; // rax
  int i; // r9d
  unsigned int v126; // ecx
  PVOID v127; // rcx
  PVOID v128; // r8
  void *v129; // rax
  int v130; // r11d
  void *v131; // rcx
  _DWORD *v132; // r11
  __int64 v133; // rax
  _QWORD *v134; // rax
  int *v135; // rax
  void *v136; // r8
  void *v137; // r8
  void *v138; // r8
  _QWORD *v139; // rax
  void *v140; // r8
  void *v141; // r8
  void *v142; // r8
  void *v143; // r8
  void *v144; // r8
  void *v145; // r8
  void *v146; // r8
  void *v147; // r8
  void *v148; // r8
  void *v149; // r8
  void *v150; // r8
  void *v151; // r8
  SIZE_T v152; // rax
  unsigned __int8 *v153; // rcx
  int v154; // edx
  int v155; // ebx
  char *v156; // r8
  int v157; // r10d
  int v158; // r13d
  int v159; // edi
  int v160; // r10d
  unsigned __int8 *v161; // rdx
  _BYTE *v162; // rbx
  int v163; // r15d
  PVOID v164; // r12
  int v165; // r11d
  unsigned int n; // ecx
  __int64 v167; // r10
  unsigned int *v168; // r8
  void *v169; // rax
  int v170; // ebx
  unsigned int v171; // r8d
  int v172; // ecx
  unsigned int v173; // eax
  int v174; // ecx
  unsigned int v175; // r11d
  int v176; // r8d
  _BYTE *v177; // rbx
  char v178; // dl
  int v179; // eax
  int v180; // r14d
  int v181; // esi
  int v182; // r14d
  int v183; // ecx
  int v184; // esi
  unsigned int v185; // r9d
  int v186; // r10d
  unsigned int v187; // ecx
  int v188; // r9d
  int v189; // r10d
  unsigned int v190; // ecx
  int v191; // r9d
  int v192; // r11d
  int v193; // edi
  unsigned int v194; // r10d
  int v195; // ecx
  int v196; // r9d
  unsigned int v197; // r10d
  int v198; // ecx
  int v199; // r9d
  unsigned int v200; // r10d
  int v201; // ecx
  unsigned int v202; // r9d
  int v203; // r10d
  int v204; // ecx
  int v205; // r9d
  unsigned int v206; // r10d
  int v207; // ecx
  int v208; // r9d
  int v209; // r10d
  __int64 v210; // r8
  unsigned __int64 v211; // rcx
  __int64 v212; // rcx
  int CachedSigningLevel; // edi
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  bool v215; // [rsp+40h] [rbp-C0h] BYREF
  int v216; // [rsp+44h] [rbp-BCh]
  __int64 v217; // [rsp+48h] [rbp-B8h]
  SIZE_T v218; // [rsp+50h] [rbp-B0h]
  PVOID v219; // [rsp+58h] [rbp-A8h]
  PVOID P; // [rsp+60h] [rbp-A0h]
  SIZE_T Size; // [rsp+68h] [rbp-98h]
  PVOID v222; // [rsp+70h] [rbp-90h]
  int v223; // [rsp+78h] [rbp-88h]
  void *Src; // [rsp+80h] [rbp-80h]
  unsigned __int8 *v225; // [rsp+88h] [rbp-78h]
  PVOID v226; // [rsp+90h] [rbp-70h]
  unsigned __int8 *v227; // [rsp+98h] [rbp-68h]
  PVOID v228; // [rsp+A0h] [rbp-60h]
  unsigned int *v229; // [rsp+A8h] [rbp-58h]
  PVOID v230; // [rsp+B0h] [rbp-50h]
  char v231[8]; // [rsp+B8h] [rbp-48h] BYREF
  char *v232; // [rsp+C0h] [rbp-40h]
  SIZE_T v233; // [rsp+C8h] [rbp-38h] BYREF
  PVOID v234; // [rsp+D0h] [rbp-30h]
  bool v235; // [rsp+D8h] [rbp-28h]
  int v236; // [rsp+DCh] [rbp-24h]
  PVOID v237; // [rsp+E0h] [rbp-20h]
  void *v238; // [rsp+E8h] [rbp-18h]
  Common *v239; // [rsp+F0h] [rbp-10h]
  _DWORD *v240; // [rsp+F8h] [rbp-8h]
  void *v241; // [rsp+100h] [rbp+0h]
  unsigned __int64 v242; // [rsp+108h] [rbp+8h]
  int v243; // [rsp+110h] [rbp+10h]
  int v244; // [rsp+114h] [rbp+14h] BYREF
  __int128 v245; // [rsp+118h] [rbp+18h] BYREF
  __int128 v246; // [rsp+128h] [rbp+28h]
  unsigned __int64 v247; // [rsp+138h] [rbp+38h]
  bool *v248; // [rsp+140h] [rbp+40h]
  const unsigned __int16 *v249; // [rsp+148h] [rbp+48h]
  void *v250; // [rsp+150h] [rbp+50h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v6 = a6;
  v7 = 0;
  v250 = a2;
  v8 = a3;
  v235 = a3;
  v249 = a1;
  *a6 = 0;
  v248 = a6;
  if ( a3 )
    return TrustLabelAceHelpers::VerifyTrustSidPresentOnFilesystemObject(a1, a2, v8, v6);
  FileW = (Common *)CreateFileW(a1, a5 ? 1179785 : 8, 7u, 0, 3u, 0x20000000u, 0);
  v239 = FileW;
  v12 = FileW;
  if ( FileW )
  {
    if ( FileW == (Common *)-1LL )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x27,
               (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelacehelpers.cpp",
               v11);
  }
  else
  {
    v12 = 0;
    v239 = 0;
  }
  v215 = 0;
  if ( (int)TrustLabelAceHelpers::CheckForRemovableMediaEfsEncryption(v12, &v215) < 0 || !v215 )
  {
    if ( !v12 )
    {
      v21 = -2147024809;
      goto LABEL_44;
    }
    Heap = (unsigned __int8 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA0u);
    v14 = Heap;
    if ( !Heap )
    {
      v21 = -1073741801;
      goto LABEL_44;
    }
    v15 = 0;
    v223 = 0;
    *(_OWORD *)Heap = xmmword_18039D390;
    *((_OWORD *)Heap + 1) = xmmword_18039D3A0;
    *((_OWORD *)Heap + 2) = xmmword_18039D3B0;
    *((_OWORD *)Heap + 3) = xmmword_18039D3C0;
    *((_OWORD *)Heap + 4) = xmmword_18039D3D0;
    *((_OWORD *)Heap + 5) = xmmword_18039D3E0;
    *((_OWORD *)Heap + 6) = xmmword_18039D3F0;
    *((_OWORD *)Heap + 7) = xmmword_18039D400;
    *((_OWORD *)Heap + 8) = xmmword_18039D410;
    *((_OWORD *)Heap + 9) = xmmword_18039D420;
    v16 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 8u);
    v17 = v16;
    if ( v16 )
    {
      *v16 = qword_18039D2D8;
      v18 = __rdtsc();
      v247 = v18;
      *(_QWORD *)&k = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xD0u);
      v20 = (unsigned int *)k;
      if ( (_QWORD)k )
      {
        *((_QWORD *)&k + 1) = k + 4;
        v240 = 0;
        if ( (__int64)k + 4 < (unsigned __int64)k )
        {
LABEL_11:
          v21 = -1073741675;
LABEL_15:
          v15 = (int)v7;
          goto LABEL_32;
        }
        if ( (__int64)k + 8 > (unsigned __int64)(k + 208) )
          goto LABEL_323;
        *(_DWORD *)k = 4;
        v118 = 0;
        **((_DWORD **)&k + 1) = 24;
        *((_QWORD *)&k + 1) = k;
        while ( !v118 )
        {
          LODWORD(k) = **((_DWORD **)&k + 1) + 4;
          if ( **((_DWORD **)&k + 1) >= 0xFFFFFFFC
            || *((_QWORD *)&k + 1) + (unsigned __int64)(unsigned int)k < *((_QWORD *)&k + 1) )
          {
            goto LABEL_11;
          }
          *((_QWORD *)&k + 1) += (unsigned int)k;
          v118 = 1;
        }
        if ( (unsigned __int64)(*((_QWORD *)&k + 1) + 4LL) < *((_QWORD *)&k + 1) )
          goto LABEL_11;
        if ( *((_QWORD *)&k + 1) + 164LL > (unsigned __int64)(v20 + 52) )
        {
LABEL_323:
          v21 = -1073741789;
          goto LABEL_15;
        }
        **((_DWORD **)&k + 1) = 160;
        if ( v14 )
          memcpy_0((void *)(*((_QWORD *)&k + 1) + 4LL), v14, 0xA0u);
        if ( !v17 )
        {
          v21 = -1073741811;
          goto LABEL_14;
        }
        if ( !v20 )
        {
          v22 = 244;
LABEL_68:
          LODWORD(v228) = 5;
          *(_QWORD *)&k = __rdtsc();
          *((_QWORD *)&k + 1) = (unsigned __int64)DWORD1(k) << 32;
          Src = (void *)k;
          if ( v22 + 8 < 8 || (v152 = (v22 + 15) & 0xFFFFFFF8, v232 = (char *)v152, (unsigned int)v152 < v22 + 8) )
          {
            v21 = -805306219;
            goto LABEL_30;
          }
          v243 = 0;
          v241 = (void *)((v22 + 15) & 0xFFFFFFF8);
          *(_QWORD *)&k = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v152);
          v65 = (unsigned __int8 *)k;
          if ( !(_QWORD)k )
          {
            v21 = -805306345;
            goto LABEL_29;
          }
          *(_DWORD *)k = 5;
          v76 = (unsigned int *)(k + 4);
          if ( v76 < (unsigned int *)v65 || (*v76 = v22, v76 + 1 < v76) )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v65);
            v21 = -805306219;
            goto LABEL_29;
          }
          *(_QWORD *)((char *)v241 + (_QWORD)v65 - 8) = Src;
          memcpy_0(v76 + 1, v20, v22);
          v222 = 0;
          v67 = (unsigned int)v232;
          v66 = 0;
          v219 = 0;
          v238 = 0;
          P = 0;
          v234 = 0;
          v230 = 0;
          if ( !(_DWORD)v232
            || (v233 = (unsigned int)v232 + 8LL, v237 = (PVOID)PerfpAllocate(v233), (v68 = (char *)v237) == 0) )
          {
            v21 = -805306367;
            goto LABEL_315;
          }
          v64 = 0;
          v77 = 0;
          v215 = 0;
          if ( v67 )
          {
            do
              v64 ^= v65[v77++];
            while ( v77 < v67 );
            v215 = v64;
          }
          v227 = v14;
          v226 = v17;
          v78 = v67 >> 3;
          v229 = v20;
          v217 = 0xC81ECB17B1B54A58uLL;
          v236 = -1;
          if ( v67 >> 3 )
          {
            v62 = WORD1(v217);
            v31 = v65;
            v25 = WORD2(v217);
            v63 = v237;
            v26 = HIWORD(v217);
            v60 = -1;
            v242 = 0;
            v27 = v78;
            LODWORD(Size) = 0;
            v216 = 0;
            LODWORD(v218) = 0;
            v225 = v65;
            do
            {
              v28 = *v31;
              v29 = v31[1];
              v30 = v31[4];
              v31 += 8;
              v32 = *(v31 - 5) | ((*(v31 - 6) | (((v28 << 8) | v29) << 8)) << 8);
              v33 = *(v31 - 1) | ((*(v31 - 2) | ((*(v31 - 3) | (v30 << 8)) << 8)) << 8);
              v34 = v60 ^ v33;
              v35 = v218 ^ v32 ^ ((v60 ^ v33) - 19032);
              v36 = v35 ^ HIDWORD(v217);
              v37 = v34 ^ (__ROR4__(v35 ^ HIDWORD(v217), 7) + v62 * __ROR4__(v35, 15));
              v38 = v36 ^ (v25 * __ROR4__(v37 - 1313519016, 9) - __ROR4__(v37, 10));
              v39 = v37 ^ (__ROR4__(v38, 27) + v26 * __ROR4__(v25 ^ v38, 28));
              v40 = v38 ^ (HIDWORD(v217) - (v39 ^ 0xB1B54A58));
              v41 = v40 ^ (19032 * (v25 ^ __ROR4__(v39 ^ (WORD1(v217) * (v40 - 19032) - (v40 >> 6)), 15)));
              v42 = v39 ^ (WORD1(v217) * (v40 - 19032) - (v40 >> 6)) ^ (v25 * (v26 + __ROR4__(~v41, 3)));
              v43 = v41 ^ (v42 - HIDWORD(v217) - 19032);
              v44 = v42 ^ (WORD1(v217) * (v26 ^ v43)) ^ __ROR4__(v43, 10);
              v45 = v43 ^ __ROR4__(v44, 3) ^ (v25 * __ROR4__(v44 ^ 0x4A58, 26));
              v46 = v44 ^ (19032 * (__ROR4__(v45, 15) - v26));
              v47 = v45
                  ^ (19032 * (v26 ^ v46))
                  ^ ((v46 ^ (v46 >> 14)) >> 1)
                  ^ (19032 * (((unsigned __int64)(v46 - v25) >> 29) | (8 * (v46 - v25))));
              v48 = v46 ^ (WORD1(v217) * (v47 - v25) - (v47 >> 13));
              v49 = v47 ^ __ROR4__(v48, 11) ^ (v25 * __ROR4__(-1313519016 - v48, 9));
              v50 = v48 ^ (v49 + 1313519016 - v26);
              v51 = v49 ^ (19032 * (WORD1(v217) ^ v50) - __ROR4__(v50, 7));
              v52 = v50 ^ (WORD1(v217) * __ROR4__(v26 ^ v51, 28) - __ROR4__(v51, 16));
              v53 = v51 ^ (__ROR4__(v52, 4) + v25 * __ROR4__(-1313519016 - v52, 10));
              v54 = v52 ^ __ROR4__(v53, 9) ^ (v26 * __ROR4__(v53 + 1313519016, 4));
              v55 = v53 ^ (19032 * __ROR4__(HIDWORD(v217) ^ v54, 24) - __ROR4__(v54, 30));
              v56 = v54 ^ (WORD1(v217) * __ROR4__(HIDWORD(v217) - v55, 11) - __ROR4__(v55, 12));
              v57 = v216;
              v216 = v33;
              v58 = v55 ^ (v56 >> 8) ^ (v25 * (WORD1(v217) ^ v56));
              v59 = v58 ^ Size;
              LODWORD(Size) = v32;
              v63[3] = v59;
              v60 = v56 ^ HIDWORD(v217) ^ v58 ^ v57 ^ 0xB1B54A58;
              LODWORD(v218) = v59;
              v63[7] = v60;
              v63[2] = __ROR4__(v59, 8);
              v63[6] = __ROR4__(v60, 8);
              v63[1] = __ROR4__(v59, 16);
              v63[5] = __ROR4__(v60, 16);
              v61 = v59;
              v62 = WORD1(v217);
              *v63 = __ROR4__(v61, 24);
              v63[4] = __ROR4__(v60, 24);
              v63 += 8;
              ++v242;
            }
            while ( v242 < v27 );
            v12 = v239;
            v64 = v215;
            v20 = v229;
            v14 = v227;
            v17 = v226;
            v65 = v225;
            v66 = v238;
            v67 = (unsigned int)v232;
            v68 = (char *)v237;
          }
          *(_QWORD *)&v68[v67] = v64;
          v69 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x30u);
          v217 = (__int64)v69;
          if ( !v69 )
          {
            v70 = -1073741801;
            LODWORD(v242) = -1073741801;
            v216 = -1073741801;
            goto LABEL_51;
          }
          v112 = v233;
          *v69 = v233;
          v70 = -1073741801;
          v113 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v112);
          LODWORD(v242) = -1073741801;
          v89 = v217;
          if ( v113 )
          {
            *(_QWORD *)(v217 + 8) = v113;
            memcpy_0(v113, v237, (unsigned int)v233);
            *(_DWORD *)(v217 + 16) = 160;
            v114 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA0u);
            v89 = v217;
            if ( v114 )
            {
              *(_QWORD *)(v217 + 24) = v114;
              *v114 = xmmword_18039D2E0;
              v114[1] = xmmword_18039D2F0;
              v114[2] = xmmword_18039D300;
              v114[3] = xmmword_18039D310;
              v114[4] = xmmword_18039D320;
              v114[5] = xmmword_18039D330;
              v114[6] = xmmword_18039D340;
              v114[7] = xmmword_18039D350;
              v114[8] = xmmword_18039D360;
              v114[9] = xmmword_18039D370;
              *(_DWORD *)(v89 + 32) = 8;
              v115 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 8u);
              if ( v115 )
              {
                v116 = v217;
                *(_QWORD *)(v217 + 40) = v115;
                *v115 = qword_18039D380;
                v92 = (_QWORD *)v116;
                v216 = 0;
                goto LABEL_151;
              }
              v89 = v217;
            }
            v217 = v89;
          }
          v88 = *(void **)(v89 + 8);
          v216 = -1073741801;
          if ( v88 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v88);
            v89 = v217;
            *(_QWORD *)(v217 + 8) = 0;
          }
          v90 = *(void **)(v89 + 24);
          if ( v90 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v90);
            v89 = v217;
            *(_QWORD *)(v217 + 24) = 0;
          }
          v91 = *(void **)(v89 + 40);
          if ( v91 )
          {
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v91);
            v89 = v217;
            *(_QWORD *)(v217 + 40) = 0;
          }
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)v89);
          if ( v216 < 0 )
          {
LABEL_51:
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v237);
            *(_QWORD *)&k = v222;
            if ( v222 )
            {
              v136 = (void *)*((_QWORD *)v222 + 1);
              if ( v136 )
              {
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v136);
                *(_QWORD *)&k = v222;
                *((_QWORD *)v222 + 1) = 0;
              }
              v137 = *(void **)(k + 24);
              if ( v137 )
              {
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v137);
                *(_QWORD *)&k = v222;
                *((_QWORD *)v222 + 3) = 0;
              }
              v138 = *(void **)(k + 40);
              if ( v138 )
              {
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v138);
                *(_QWORD *)&k = v222;
                *((_QWORD *)v222 + 5) = 0;
              }
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)k);
            }
            v71 = v216 | 0x10000000;
            if ( v216 < 0 )
              goto LABEL_65;
            if ( *(_DWORD *)v66 >= 0xFFFFFFFC
              || (v72 = *(_DWORD *)v66 + 8, v72 < *(_DWORD *)v66 + 4)
              || (*((_QWORD *)&k + 1) = v72 + *((_DWORD *)v66 + 4), v233 = (SIZE_T)(v66 + 2), DWORD2(k) < v72)
              || (v73 = DWORD2(k) + 4, (unsigned int)(DWORD2(k) + 4) < DWORD2(k))
              || (v74 = v73 + *((_DWORD *)v66 + 8), LODWORD(v218) = v74, v74 < v73) )
            {
LABEL_64:
              v71 = -805306219;
LABEL_65:
              v21 = v71;
              goto LABEL_20;
            }
            *(_QWORD *)&k = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v74);
            v217 = k;
            if ( !(_QWORD)k )
              goto LABEL_100;
            *(_DWORD *)k = *(_DWORD *)v66;
            Src = (void *)(k + 4);
            if ( (__int64)k + 4 < (unsigned __int64)k )
            {
              v75 = (void *)k;
LABEL_63:
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v75);
              goto LABEL_64;
            }
            memcpy_0((void *)(k + 4), (const void *)v66[1], *(unsigned int *)v66);
            v121 = (char *)Src + *(unsigned int *)v66;
            if ( v121 < Src )
              goto LABEL_62;
            v122 = (unsigned int *)v233;
            *v121 = *(_DWORD *)v233;
            Src = v121 + 1;
            if ( v121 + 1 < v121
              || (memcpy_0(v121 + 1, (const void *)v66[3], *v122), v123 = (char *)Src + *(unsigned int *)v233,
                                                                   v123 < Src)
              || (*v123 = *((_DWORD *)v66 + 8), Src = v123 + 1, v123 + 1 < v123)
              || (memcpy_0(v123 + 1, (const void *)v66[5], *((unsigned int *)v66 + 8)),
                  (char *)Src + *((unsigned int *)v66 + 8) < Src) )
            {
LABEL_62:
              v75 = (void *)v217;
              goto LABEL_63;
            }
            v153 = (unsigned __int8 *)v217;
            v219 = (PVOID)v217;
            LODWORD(Size) = v218;
            if ( !v20 )
              goto LABEL_338;
            *((_QWORD *)&k + 1) = (unsigned int)v228;
            if ( (unsigned int)v228 <= 1 )
              goto LABEL_338;
            v124 = v20;
            for ( i = 0; ; i = 1 )
            {
              v167 = *v124;
              v168 = v124 + 1;
              if ( i )
                break;
              if ( v168 < v124 )
                goto LABEL_67;
              v124 = (unsigned int *)((char *)v168 + v167);
              if ( (unsigned int *)((char *)v168 + v167) < v168 )
                goto LABEL_67;
            }
            if ( v168 < v124 )
              goto LABEL_67;
            if ( (unsigned int)v228 <= 2 )
            {
LABEL_338:
              v21 = -1073741811;
              goto LABEL_20;
            }
            v232 = (char *)v20;
            for ( LODWORD(v218) = 0; ; LODWORD(v218) = v218 + 1 )
            {
              v169 = v153;
              v225 = v153;
              v222 = v17;
              v229 = v20;
              v227 = v65;
              v170 = *(_DWORD *)v232;
              v233 = (SIZE_T)(v232 + 4);
              v153 = (unsigned __int8 *)v219;
              LODWORD(v228) = v170;
              v12 = v239;
              v226 = v66;
              if ( (unsigned int)v218 >= 2 )
                break;
              *((_QWORD *)&k + 1) = v233;
              if ( v233 < (unsigned __int64)v232 )
                goto LABEL_67;
              v232 = (char *)(v233 + (unsigned int)v228);
              if ( (unsigned __int64)v232 < v233 )
                goto LABEL_67;
            }
            if ( v233 < (unsigned __int64)v232
              || (LODWORD(v218) = v167 + 48, (unsigned int)v167 >= 0xFFFFFFD0)
              || (v216 = v167 + 52, (int)v167 + 52 < (unsigned int)v218)
              || (v126 = (_DWORD)v228 + v167 + 52, LODWORD(v218) = v126, v126 < v216) )
            {
LABEL_67:
              v21 = -1073741675;
              goto LABEL_20;
            }
            if ( v126 > 0x400000 )
            {
              v21 = -2147418113;
              v219 = v169;
              goto LABEL_20;
            }
            P = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v126);
            *((_QWORD *)&k + 1) = P;
            if ( !P )
            {
              v219 = v225;
              v21 = -805306345;
              P = 0;
              goto LABEL_20;
            }
            *(_QWORD *)&k = v225;
            v23 = v225;
            v219 = v225;
            v233 = 0;
            v245 = 0;
            v246 = 0;
            if ( !v225 )
            {
              v21 = -2147024809;
LABEL_367:
              P = (PVOID)*((_QWORD *)&k + 1);
              goto LABEL_19;
            }
            v245 = k;
            LODWORD(v246) = Size;
            *(_QWORD *)((char *)&v246 + 4) = (unsigned int)v218;
            if ( GetModuleHandleExW(1u, L"ntdll.dll", (HMODULE *)&v233)
              && (*(_QWORD *)&k = GetProcAddress((HMODULE)v233, "NtQuerySystemInformation"), (_QWORD)k) )
            {
              LODWORD(k) = ((__int64 (__fastcall *)(__int64, __int128 *))k)(134, &v245) | 0x10000000;
              if ( (int)k >= 0 )
              {
                v171 = DWORD1(v246);
                goto LABEL_80;
              }
            }
            else
            {
              LODWORD(k) = NtCurrentTeb()->LastErrorValue;
              v117 = (int)k < 0;
              if ( (int)k > 0 )
              {
                LODWORD(k) = (unsigned __int16)k | 0x80070000;
                v117 = (int)k < 0;
              }
              if ( !v117 )
              {
                v21 = -2147467259;
                goto LABEL_366;
              }
            }
            v171 = v218;
            if ( (_DWORD)k == -805306333 )
            {
              v21 = -2147024774;
              goto LABEL_301;
            }
            if ( (int)k >= 0 )
            {
LABEL_80:
              if ( v171 < 4 )
              {
                v21 = -805306306;
                goto LABEL_301;
              }
              *((_QWORD *)&k + 1) = P;
              v79 = *(unsigned int *)P;
              v80 = (char *)P + 4;
              LODWORD(v218) = *(_DWORD *)P;
              v241 = (char *)P + 4;
              if ( (char *)P + 4 >= P )
              {
                if ( v171 - 4 < (unsigned int)v79 )
                  goto LABEL_300;
                v233 = (SIZE_T)&v80[v79];
                if ( &v80[v79] < v80 || (unsigned int)v79 >= 0xFFFFFFFC )
                  goto LABEL_18;
                if ( v171 - ((_DWORD)v79 + 4) < 4 )
                  goto LABEL_300;
                v81 = *(unsigned int *)&v80[v79];
                LODWORD(Size) = *(_DWORD *)&v80[v79];
                v82 = v233 + 4;
                if ( v233 + 4 < v233 )
                  goto LABEL_18;
                LODWORD(v228) = v79 + 8;
                if ( (int)v79 + 8 < (unsigned int)(v79 + 4) )
                  goto LABEL_18;
                if ( v171 - (unsigned int)v228 < (unsigned int)v81 )
                  goto LABEL_300;
                Src = (void *)(v82 + v81);
                if ( v82 + v81 < v82 )
                  goto LABEL_18;
                v83 = (_DWORD)v228 + v81;
                if ( (int)v228 + (int)v81 < (unsigned int)v228 )
                  goto LABEL_18;
                if ( v171 - v83 < 4 )
                {
LABEL_300:
                  v21 = -805306306;
LABEL_301:
                  v23 = v225;
                  goto LABEL_19;
                }
                v84 = (unsigned int *)Src;
                Src = (char *)Src + 4;
                if ( Src >= v84 )
                {
                  v85 = v83 + 4;
                  if ( v83 + 4 >= v83 )
                  {
                    v86 = *v84;
                    LODWORD(v237) = v86;
                    if ( v171 - v85 >= v86 )
                    {
                      if ( v85 + v86 < v85 )
                      {
                        v21 = -805306219;
                        goto LABEL_20;
                      }
                      if ( v171 == v85 + v86 && (unsigned int)v79 + (_DWORD)v81 + v86 + 12LL == v171 )
                      {
                        *(_QWORD *)&k = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x30u);
                        v228 = (PVOID)k;
                        v87 = k;
                        if ( !(_QWORD)k )
                        {
                          v20 = v229;
                          v17 = v222;
                          v219 = v225;
LABEL_100:
                          v21 = -805306345;
                          goto LABEL_20;
                        }
                        v93 = v241;
                        v232 = 0;
                        if ( v241 )
                        {
                          v109 = v218;
                          *(_DWORD *)v87 = v218;
                          v110 = v109;
                          v111 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v109);
                          if ( !v111 )
                          {
LABEL_254:
                            v66 = v226;
                            v65 = v227;
                            v20 = v229;
                            v17 = v222;
                            v139 = v228;
                            v216 = -1073741801;
                            v219 = v225;
                            v238 = v226;
                            v140 = (void *)*((_QWORD *)v228 + 1);
                            v225 = v227;
                            v226 = v222;
                            v227 = v14;
                            if ( v140 )
                            {
                              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v140);
                              v139 = v228;
                              *((_QWORD *)v228 + 1) = 0;
                            }
                            v141 = (void *)v139[3];
                            if ( v141 )
                            {
                              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v141);
                              v139 = v228;
                              *((_QWORD *)v228 + 3) = 0;
                            }
                            v142 = (void *)v139[5];
                            if ( v142 )
                            {
                              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v142);
                              v139 = v228;
                              *((_QWORD *)v228 + 5) = 0;
                            }
                            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v139);
                            *((_QWORD *)&k + 1) = v232;
                            goto LABEL_127;
                          }
                          *(_QWORD *)(v87 + 8) = v111;
                          v216 = 0;
                          memcpy_0(v111, v93, v110);
                        }
                        else
                        {
                          *(_DWORD *)k = 0;
                          *(_QWORD *)(k + 8) = 0;
                          v216 = 0;
                        }
                        v94 = (const void *)(v233 + 4);
                        if ( v233 == -4 )
                        {
                          *(_DWORD *)(v87 + 16) = 0;
                          *(_QWORD *)(v87 + 24) = 0;
                        }
                        else
                        {
                          v95 = Size;
                          *(_DWORD *)(v87 + 16) = Size;
                          v96 = v95;
                          v97 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v95);
                          if ( !v97 )
                          {
LABEL_303:
                            v228 = (PVOID)v87;
                            goto LABEL_254;
                          }
                          *(_QWORD *)(v87 + 24) = v97;
                          v216 = 0;
                          memcpy_0(v97, v94, v96);
                        }
                        v98 = Src;
                        if ( !Src )
                        {
                          *(_DWORD *)(v87 + 32) = 0;
                          *(_QWORD *)(v87 + 40) = 0;
                          goto LABEL_126;
                        }
                        v99 = (unsigned int)v237;
                        *(_DWORD *)(v87 + 32) = (_DWORD)v237;
                        v100 = v99;
                        v101 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v99);
                        if ( v101 )
                        {
                          *(_QWORD *)(v87 + 40) = v101;
                          v216 = 0;
                          memcpy_0(v101, v98, v100);
LABEL_126:
                          *((_QWORD *)&k + 1) = v87;
                          v66 = v226;
                          v65 = v227;
                          v17 = v222;
                          v20 = v229;
                          v226 = v222;
                          v232 = (char *)*((_QWORD *)&k + 1);
                          v219 = v225;
                          v238 = v66;
                          v225 = v227;
                          v227 = v14;
LABEL_127:
                          v102 = v216;
                          if ( v216 < 0 )
                          {
                            if ( *((_QWORD *)&k + 1) )
                            {
                              v143 = *(void **)(*((_QWORD *)&k + 1) + 8LL);
                              if ( v143 )
                              {
                                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v143);
                                *((_QWORD *)&k + 1) = v232;
                                *((_QWORD *)v232 + 1) = 0;
                              }
                              v144 = *(void **)(*((_QWORD *)&k + 1) + 24LL);
                              if ( v144 )
                              {
                                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v144);
                                *((_QWORD *)&k + 1) = v232;
                                *((_QWORD *)v232 + 3) = 0;
                              }
                              v145 = *(void **)(*((_QWORD *)&k + 1) + 40LL);
                              if ( v145 )
                              {
                                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v145);
                                *((_QWORD *)&k + 1) = v232;
                                *((_QWORD *)v232 + 5) = 0;
                              }
                              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *((PVOID *)&k + 1));
                              v102 = v216;
                            }
                            *(_QWORD *)&k = v234;
                          }
                          else
                          {
                            *(_QWORD *)&k = *((_QWORD *)&k + 1);
                            v234 = (PVOID)*((_QWORD *)&k + 1);
                          }
                          v103 = v102 | 0x10000000;
                          if ( v103 < 0 )
                          {
                            v21 = v103;
                            goto LABEL_20;
                          }
                          if ( (_QWORD)k )
                          {
                            Src = *(void **)(k + 8);
                            if ( Src )
                            {
                              if ( *(_DWORD *)k )
                              {
                                v217 = *(unsigned int *)k - 8LL;
                                v241 = (void *)PerfpAllocate(v217);
                                v104 = (WCHAR *)v241;
                                if ( !v241 )
                                {
LABEL_142:
                                  v21 = -805306367;
                                  v230 = 0;
                                  goto LABEL_20;
                                }
                                v105 = 0;
                                v106 = v217;
                                v232 = (char *)Src;
                                v215 = 0;
                                v233 = v217 & 7;
                                v230 = (PVOID)0x7F1137FAB69605ELL;
                                v222 = v241;
                                if ( (v217 & 7) != 0 )
                                {
                                  v236 = 0;
                                  LODWORD(v218) = 0;
                                  v154 = 0;
                                  v155 = 0;
                                  v156 = v232;
                                  v157 = 0;
                                  do
                                  {
                                    v172 = (unsigned __int8)*v156++;
                                    v216 = v172;
                                    LODWORD(v228) = 8 * v154;
                                    if ( (unsigned int)v154 >= 4 )
                                    {
                                      v216 <<= 56 - (_BYTE)v228;
                                      v157 |= v216;
                                    }
                                    else
                                    {
                                      v216 <<= 24 - (_BYTE)v228;
                                      v155 |= v216;
                                    }
                                    ++v154;
                                  }
                                  while ( v154 < (int)v233 );
                                  v105 = v215;
                                  v236 = v157;
                                  v104 = (WCHAR *)v241;
                                  LODWORD(v218) = v155;
                                  v12 = v239;
                                  v232 = v156;
                                  v173 = v233;
                                  v238 = v66;
                                  v225 = v65;
                                  v229 = v20;
                                  v226 = v17;
                                  v227 = v14;
                                  v174 = v236 ^ 0x699A899C;
                                  LODWORD(v228) = 0;
                                  v107 = v218 ^ 0x92F65A5;
                                  LODWORD(Size) = v236 ^ 0x699A899C;
                                  if ( (_DWORD)v233 )
                                  {
                                    v175 = (unsigned int)v228;
                                    v176 = v218 ^ 0x92F65A5;
                                    v177 = v241;
                                    do
                                    {
                                      v233 = (SIZE_T)(v177 + 1);
                                      if ( v175 >= 4 )
                                      {
                                        v174 = __ROR4__(v174, 24);
                                        v178 = v174;
                                      }
                                      else
                                      {
                                        v176 = __ROR4__(v176, 24);
                                        v178 = v176;
                                      }
                                      *v177 = v178;
                                      ++v175;
                                      v177 = (_BYTE *)v233;
                                    }
                                    while ( (int)v175 < (int)v173 );
                                    v12 = v239;
                                    v106 = v217;
                                    v222 = (PVOID)v233;
                                    v105 = v215;
                                  }
                                  if ( v173 <= 4 )
                                  {
                                    LODWORD(Size) = 0;
                                    if ( v173 < 4 )
                                      v107 = v107 >> (8 * (4 - v173)) << (8 * (4 - v173));
                                  }
                                  else
                                  {
                                    LODWORD(Size) = (unsigned int)Size >> (8 * (8 - v173)) << (8 * (8 - v173));
                                  }
                                }
                                else
                                {
                                  LODWORD(v218) = 0;
                                  LODWORD(Size) = 0;
                                  v107 = 0;
                                }
                                v237 = (PVOID)(v106 >> 3);
                                if ( v106 >> 3 )
                                {
                                  v158 = HIDWORD(v230);
                                  v159 = WORD1(v230);
                                  v160 = Size;
                                  v161 = (unsigned __int8 *)v232;
                                  v162 = v222;
                                  v163 = v218;
                                  v164 = v237;
                                  v165 = WORD2(v230);
                                  LODWORD(v228) = WORD2(v230);
                                  v233 = 0;
                                  v216 = 24670;
                                  do
                                  {
                                    v179 = *v161;
                                    v180 = v161[1];
                                    v181 = v161[4];
                                    v161 += 8;
                                    v182 = *(v161 - 5) | ((*(v161 - 6) | (((v179 << 8) | v180) << 8)) << 8);
                                    v183 = v107 ^ v182;
                                    v184 = *(v161 - 1) | ((*(v161 - 2) | ((*(v161 - 3) | (v181 << 8)) << 8)) << 8);
                                    v185 = v158 ^ v107 ^ v182 ^ v160 ^ v184 ^ 0xAB69605E;
                                    v186 = v183 ^ (__ROR4__(v185, 22) + v165 * __ROR4__(v185 + 1419157410, 27));
                                    v187 = v185 ^ (v159 * __ROR4__(v186 + v158, 9) - __ROR4__(v186, 30));
                                    v188 = v186 ^ (v216 * (v187 - v165) - (v187 >> 13));
                                    v189 = v187 ^ (HIWORD(v230) * __ROR4__(v188 ^ v159, 26) - __ROR4__(v188, 30));
                                    v190 = v188 ^ (v158 - (v189 ^ 0xAB69605E));
                                    v191 = v189 ^ (v159 * (v190 ^ v165)) ^ __ROR4__(v190, 6);
                                    v192 = v190 ^ (__ROR4__(v191, 30) + v216 * __ROR4__(v191 + v158, 15));
                                    v193 = v191 ^ (HIWORD(v230) * __ROR4__(v192 + 1419157410, 14) - __ROR4__(v192, 24));
                                    v194 = v192 ^ __ROR4__(v193, 10) ^ ((_DWORD)v228 * __ROR4__(v193 ^ 0xAB69605E, 12));
                                    v195 = v193 ^ (v194 >> 10) ^ (WORD1(v230) * (v194 ^ HIWORD(v230)));
                                    v159 = WORD1(v230);
                                    v196 = v194 ^ (HIWORD(v230) * (v216 + __ROR4__(~v195, 5)));
                                    v197 = v195 ^ (v196 - HIWORD(v230)) ^ 0xAB69605E;
                                    v165 = (int)v228;
                                    v198 = v196 ^ ((v197 >> 2) + (_DWORD)v228 * __ROR4__(v197 ^ HIWORD(v230), 30));
                                    v199 = v197 ^ (__ROR4__(v198, 25) + WORD1(v230) * __ROR4__(v198 - v158, 6));
                                    v200 = v198 ^ (v216 * (v199 ^ (unsigned int)v228) + __ROR4__(v199, 9));
                                    v201 = v199 ^ (__ROR4__(v200, 25) + HIWORD(v230) * __ROR4__(v200 ^ WORD1(v230), 27));
                                    v202 = v200 ^ v201 ^ v158 ^ 0xAB69605E;
                                    v203 = v201 ^ ((_DWORD)v228 * (__ROR4__(v202, 3) - WORD1(v230)));
                                    v204 = v202 ^ (v216 * __ROR4__(v203 - v158, 1) - __ROR4__(v203, 6));
                                    v205 = v203 ^ (__ROR4__(v204, 18) + HIWORD(v230) * __ROR4__(v204 - 1419157410, 29));
                                    v206 = v204 ^ ((_DWORD)v228 * __ROR4__(v205 - 1419157410, 17) - __ROR4__(v205, 14));
                                    v207 = v205 ^ (v206 >> 3) ^ (WORD1(v230) * (v206 ^ v216));
                                    v208 = v163 ^ __ROR4__(v207, 30) ^ (v216 * __ROR4__(v207 ^ v158, 28));
                                    v163 = v182;
                                    v107 = v206 ^ v208;
                                    v209 = v236;
                                    v162[3] = v107;
                                    v160 = v207 ^ v209;
                                    v162[7] = v160;
                                    v162[2] = __ROR4__(v107, 8);
                                    v162[6] = __ROR4__(v160, 8);
                                    v162[1] = __ROR4__(v107, 16);
                                    v162[5] = __ROR4__(v160, 16);
                                    *v162 = __ROR4__(v107, 24);
                                    v162[4] = __ROR4__(v160, 24);
                                    v162 += 8;
                                    v236 = v184;
                                    ++v233;
                                  }
                                  while ( v233 < (unsigned __int64)v164 );
                                  v12 = v239;
                                  v105 = v215;
                                  v70 = v242;
                                  v20 = v229;
                                  v14 = v227;
                                  v17 = v226;
                                  v65 = v225;
                                  v66 = v238;
                                  v104 = (WCHAR *)v241;
                                  v106 = v217;
                                }
                                for ( j = 0; j < v106; ++j )
                                  v105 ^= *((_BYTE *)v104 + j);
                                if ( v105 != *(_QWORD *)((char *)Src + v106) )
                                {
                                  FreeEnvironmentStringsW(v104);
                                  goto LABEL_142;
                                }
                                v127 = v219;
                                *((_QWORD *)&k + 1) = P;
                                v128 = v234;
                                v230 = v104;
                                if ( (unsigned int)v106 < 4 )
                                  goto LABEL_224;
                                Src = v104 + 2;
                                if ( v104 + 2 < v104 )
                                  goto LABEL_156;
                                if ( (unsigned int)(v106 - 4) >= 4 )
                                {
                                  v238 = v104 + 4;
                                  if ( v104 + 4 < Src )
                                    goto LABEL_156;
                                  if ( (unsigned int)(v106 - 8) >= *((_DWORD *)v104 + 1) )
                                  {
                                    if ( *((_DWORD *)v104 + 1) < 0xFFFFFFF8 )
                                    {
                                      v217 = *((unsigned int *)v104 + 1);
                                      v232 = (char *)v104 + v217 + 8;
                                      if ( (char *)v104 + (unsigned int)v106 >= v232
                                        && (unsigned __int64)(unsigned int)v106 - v217 - 8 < 8 )
                                      {
                                        v129 = v238;
                                        LODWORD(Size) = 0;
                                        if ( v238 )
                                        {
                                          if ( v232 < v238 )
                                          {
LABEL_103:
                                            v70 = -1073741675;
                                          }
                                          else
                                          {
                                            v132 = v238;
                                            v230 = v104;
                                            *(_QWORD *)&k = v232;
                                            while ( 1 )
                                            {
                                              LODWORD(v218) = 0;
                                              if ( (unsigned __int64)v132 >= (unsigned __int64)k )
                                                break;
                                              Src = v132 + 1;
                                              v12 = v239;
                                              if ( v132 + 1 < v132 )
                                                goto LABEL_103;
                                              if ( (unsigned __int64)Src > (unsigned __int64)k )
                                                goto LABEL_365;
                                              v133 = (unsigned int)(*v132 + 4);
                                              if ( *v132 >= 0xFFFFFFFC )
                                                goto LABEL_103;
                                              Src = (char *)v132 + v133;
                                              if ( (_DWORD *)((char *)v132 + v133) < v132 )
                                                goto LABEL_103;
                                              *(_QWORD *)&k = v232;
                                              v132 = Src;
                                              v219 = v127;
                                              P = (PVOID)*((_QWORD *)&k + 1);
                                              v234 = v128;
                                              v230 = v104;
                                              if ( Src > v232 )
                                              {
                                                v70 = -1073741811;
                                                v230 = v104;
                                                goto LABEL_158;
                                              }
                                              LODWORD(Size) = Size + 1;
                                            }
                                            if ( v132 == (_DWORD *)k )
                                            {
                                              v129 = v238;
                                              v130 = v218;
                                              goto LABEL_217;
                                            }
LABEL_365:
                                            v70 = -1073741811;
                                          }
                                          goto LABEL_104;
                                        }
                                        v130 = 0;
                                        v230 = v104;
                                        LODWORD(v218) = 0;
LABEL_217:
                                        LODWORD(v237) = *(_DWORD *)v104;
                                        v131 = 0;
                                        Src = 0;
                                        if ( *((_DWORD *)v104 + 1) )
                                        {
                                          Src = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v217);
                                          v131 = Src;
                                          if ( !Src )
                                          {
LABEL_104:
                                            v21 = v70 | 0x10000000;
                                            goto LABEL_20;
                                          }
                                          v129 = v238;
                                          v130 = 0;
                                          LODWORD(v218) = 0;
                                        }
                                        if ( v129 )
                                        {
                                          memcpy_0(v131, v129, v217);
                                          v130 = v218;
                                        }
                                        v240 = Src;
                                        v243 = Size;
                                        v70 = v130;
                                        if ( v130 < 0 || (_DWORD)v237 == (_DWORD)Size )
                                          goto LABEL_104;
LABEL_224:
                                        v70 = -1073741762;
                                        goto LABEL_104;
                                      }
                                      goto LABEL_310;
                                    }
LABEL_156:
                                    v70 = -1073741675;
                                    goto LABEL_157;
                                  }
                                }
LABEL_310:
                                v70 = -1073741762;
LABEL_157:
                                v230 = v104;
LABEL_158:
                                v234 = v128;
                                P = (PVOID)*((_QWORD *)&k + 1);
                                v219 = v127;
                                goto LABEL_104;
                              }
                            }
                          }
                          v21 = -805306355;
LABEL_20:
                          if ( !v65 )
                          {
LABEL_21:
                            if ( v66 )
                            {
                              v146 = (void *)v66[1];
                              if ( v146 )
                              {
                                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v146);
                                v66[1] = 0;
                              }
                              v147 = (void *)v66[3];
                              if ( v147 )
                              {
                                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v147);
                                v66[3] = 0;
                              }
                              v148 = (void *)v66[5];
                              if ( v148 )
                              {
                                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v148);
                                v66[5] = 0;
                              }
                              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v66);
                            }
                            if ( v219 )
                              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v219);
                            if ( P )
                              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
                            v24 = v234;
                            if ( v234 )
                            {
                              v149 = (void *)*((_QWORD *)v234 + 1);
                              if ( v149 )
                              {
                                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v149);
                                v24[1] = 0;
                              }
                              v150 = (void *)v24[3];
                              if ( v150 )
                              {
                                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v150);
                                v24[3] = 0;
                              }
                              v151 = (void *)v24[5];
                              if ( v151 )
                              {
                                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v151);
                                v24[5] = 0;
                              }
                              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v24);
                            }
                            if ( v230 )
                              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v230);
LABEL_29:
                            if ( v21 < 0 )
                            {
LABEL_30:
                              v7 = v240;
LABEL_31:
                              v15 = v223;
                              goto LABEL_32;
                            }
                            v7 = v240;
                            if ( v243 == 2 )
                            {
                              if ( !v240 )
                              {
                                v21 = -1073741811;
                                goto LABEL_31;
                              }
                              if ( v240 + 1 < v240 )
                                goto LABEL_106;
                              v134 = 0;
                              if ( *v240 )
                                v134 = v240 + 1;
                              if ( *v240 != 8 )
                              {
LABEL_371:
                                v21 = -1073741789;
                                goto LABEL_31;
                              }
                              if ( v247 == *v134 )
                              {
                                for ( k = (unsigned __int64)v240; ; *((_QWORD *)&k + 1) = 1 )
                                {
                                  v210 = *(unsigned int *)k;
                                  v211 = k + 4;
                                  if ( DWORD2(k) )
                                    break;
                                  if ( v211 < (unsigned __int64)k )
                                    goto LABEL_106;
                                  *(_QWORD *)&k = v211 + v210;
                                  if ( v211 + v210 < v211 )
                                    goto LABEL_106;
                                }
                                if ( v211 >= (unsigned __int64)k )
                                {
                                  v135 = 0;
                                  if ( (_DWORD)v210 )
                                    v135 = (int *)v211;
                                  if ( (_DWORD)v210 == 4 )
                                  {
                                    v15 = *v135;
                                    v21 = 0;
LABEL_32:
                                    if ( v20 )
                                      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
                                    if ( v7 )
                                      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
                                    if ( !v14 )
                                      goto LABEL_37;
                                    goto LABEL_17;
                                  }
                                  goto LABEL_371;
                                }
LABEL_106:
                                v21 = -1073741675;
                                goto LABEL_31;
                              }
                            }
                            v21 = -1073425151;
                            goto LABEL_31;
                          }
LABEL_315:
                          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v65);
                          goto LABEL_21;
                        }
                        goto LABEL_303;
                      }
                    }
                    goto LABEL_300;
                  }
                }
              }
LABEL_18:
              v23 = v219;
              v21 = -805306219;
LABEL_19:
              v219 = v23;
              goto LABEL_20;
            }
            v21 = k;
LABEL_366:
            *((_QWORD *)&k + 1) = P;
            v23 = v219;
            goto LABEL_367;
          }
          v92 = v222;
LABEL_151:
          v66 = v92;
          v222 = 0;
          goto LABEL_51;
        }
        *((_QWORD *)&k + 1) = v20;
        for ( m = 0; m < 2; ++m )
        {
          LODWORD(k) = **((_DWORD **)&k + 1) + 4;
          if ( **((_DWORD **)&k + 1) >= 0xFFFFFFFC
            || *((_QWORD *)&k + 1) + (unsigned __int64)(unsigned int)k < *((_QWORD *)&k + 1) )
          {
            goto LABEL_13;
          }
          *((_QWORD *)&k + 1) += (unsigned int)k;
        }
        if ( (unsigned __int64)(*((_QWORD *)&k + 1) + 4LL) < *((_QWORD *)&k + 1) )
          goto LABEL_13;
        if ( *((_QWORD *)&k + 1) + 12LL <= (unsigned __int64)(v20 + 52) )
        {
          **((_DWORD **)&k + 1) = 8;
          memcpy_0((void *)(*((_QWORD *)&k + 1) + 4LL), v17, 8u);
          *((_QWORD *)&k + 1) = v20;
          for ( n = 0; n < 3; ++n )
          {
            LODWORD(k) = **((_DWORD **)&k + 1) + 4;
            if ( **((_DWORD **)&k + 1) >= 0xFFFFFFFC
              || *((_QWORD *)&k + 1) + (unsigned __int64)(unsigned int)k < *((_QWORD *)&k + 1) )
            {
              goto LABEL_13;
            }
            *((_QWORD *)&k + 1) += (unsigned int)k;
          }
          if ( (unsigned __int64)(*((_QWORD *)&k + 1) + 4LL) < *((_QWORD *)&k + 1) )
            goto LABEL_13;
          if ( *((_QWORD *)&k + 1) + 12LL <= (unsigned __int64)(v20 + 52) )
          {
            **((_DWORD **)&k + 1) = 8;
            *(_QWORD *)(*((_QWORD *)&k + 1) + 4LL) = v18;
            *((_QWORD *)&k + 1) = v20;
            v22 = 208;
            for ( ii = 0; ii < 4; ++ii )
            {
              LODWORD(k) = **((_DWORD **)&k + 1) + 4;
              if ( **((_DWORD **)&k + 1) >= 0xFFFFFFFC
                || *((_QWORD *)&k + 1) + (unsigned __int64)(unsigned int)k < *((_QWORD *)&k + 1) )
              {
                goto LABEL_13;
              }
              *((_QWORD *)&k + 1) += (unsigned int)k;
            }
            if ( (unsigned __int64)(*((_QWORD *)&k + 1) + 4LL) >= *((_QWORD *)&k + 1) )
            {
              if ( *((_QWORD *)&k + 1) + 12LL <= (unsigned __int64)(v20 + 52) )
              {
                **((_DWORD **)&k + 1) = 8;
                *(_QWORD *)(*((_QWORD *)&k + 1) + 4LL) = v12;
                goto LABEL_68;
              }
              goto LABEL_335;
            }
LABEL_13:
            v21 = -1073741675;
LABEL_14:
            v7 = v240;
            goto LABEL_15;
          }
        }
LABEL_335:
        v21 = -1073741789;
        goto LABEL_14;
      }
      v21 = -1073741801;
      v15 = 0;
    }
    else
    {
      v21 = -1073741801;
      v17 = 0;
    }
LABEL_17:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
LABEL_37:
    if ( v17 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
    if ( v21 >= 0 )
      goto LABEL_40;
    if ( v21 == -1073425151 || v21 == -805306306 )
    {
      v15 = 1;
LABEL_40:
      if ( (unsigned int)(v15 - 2) <= 1 )
      {
        if ( !a5 )
        {
LABEL_42:
          Common::CloseHandleHelper(v12, *((void **)&k + 1));
          v8 = v235;
          a1 = v249;
          a2 = v250;
          v6 = v248;
          return TrustLabelAceHelpers::VerifyTrustSidPresentOnFilesystemObject(a1, a2, v8, v6);
        }
        v244 = 0;
        v231[0] = 0;
        CachedSigningLevel = NtGetCachedSigningLevel(v12, &v244, v231, 0, 0, 0);
        if ( CachedSigningLevel < 0 )
        {
          if ( CachedSigningLevel != -1073741275 )
          {
            Common::CloseHandleHelper(v12, *((void **)&k + 1));
            return CachedSigningLevel | 0x10000000u;
          }
        }
        else
        {
          LOBYTE(v212) = v231[0];
          BYTE8(k) = 6;
          if ( (int)NtCompareSigningLevels(v212, *((_QWORD *)&k + 1)) >= 0 )
            goto LABEL_42;
        }
      }
      v21 = 0;
LABEL_45:
      Common::CloseHandleHelper(v12, *((void **)&k + 1));
      return (unsigned int)v21;
    }
LABEL_44:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelacehelpers.cpp",
      (const char *)(unsigned int)v21,
      dwCreationDisposition);
    goto LABEL_45;
  }
  *a6 = 1;
  if ( v12 )
    CloseHandle(v12);
  return 0;
}

```

## disassembly

```asm
0x1800b31d0  mov     [rsp-8+arg_10], rbx
0x1800b31d5  push    rbp
0x1800b31d6  push    rsi
0x1800b31d7  push    rdi
0x1800b31d8  push    r12
0x1800b31da  push    r13
0x1800b31dc  push    r14
0x1800b31de  push    r15
0x1800b31e0  lea     rbp, [rsp-70h]
0x1800b31e5  sub     rsp, 170h
0x1800b31ec  mov     rdi, [rbp+0A0h+arg_28]
0x1800b31f3  xor     r14d, r14d
0x1800b31f6  mov     [rbp+0A0h+var_50], rdx
0x1800b31fa  mov     al, r8b
0x1800b31fd  mov     [rbp+0A0h+var_C8], al
0x1800b3200  mov     [rbp+0A0h+var_58], rcx
0x1800b3204  mov     [rdi], r14b
0x1800b3207  mov     [rbp+0A0h+var_60], rdi
0x1800b320b  test    r8b, r8b
0x1800b320e  jz      short loc_1800B3236
0x1800b3210  mov     r9, rdi; bool *
0x1800b3213  mov     r8b, al; bool
0x1800b3216  call    ?VerifyTrustSidPresentOnFilesystemObject@TrustLabelAceHelpers@@SAJPEBGPEAX_NPEA_N@Z; TrustLabelAceHelpers::VerifyTrustSidPresentOnFilesystemObject(ushort const *,void *,bool,bool *)
0x1800b321b  mov     rbx, [rsp+1A0h+arg_10]
0x1800b3223  add     rsp, 170h
0x1800b322a  pop     r15
0x1800b322c  pop     r14
0x1800b322e  pop     r13
0x1800b3230  pop     r12
0x1800b3232  pop     rdi
0x1800b3233  pop     rsi
0x1800b3234  pop     rbp
0x1800b3235  retn
0x1800b3236  mov     al, [rbp+0A0h+arg_20]
0x1800b323c  mov     r12d, 8
0x1800b3242  neg     al
0x1800b3244  mov     [rsp+1A0h+hTemplateFile], r14; hTemplateFile
0x1800b3249  mov     [rsp+1A0h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x1800b3251  sbb     edx, edx
0x1800b3253  mov     [rsp+1A0h+dwCreationDisposition], 3; int
0x1800b325b  and     edx, 120081h
0x1800b3261  lea     r8d, [r12-1]; dwShareMode
0x1800b3266  add     edx, r12d; dwDesiredAccess
0x1800b3269  xor     r9d, r9d; lpSecurityAttributes
0x1800b326c  call    CreateFileW
0x1800b3271  mov     [rbp+0A0h+var_B0], rax
0x1800b3275  mov     rbx, rax
0x1800b3278  test    rax, rax
0x1800b327b  jz      loc_1800B4A68
0x1800b3281  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b3285  jz      loc_1800B33D3
0x1800b328b  lea     rdx, [rsp+1A0h+var_160]; bool *
0x1800b3290  mov     [rsp+1A0h+var_160], r14b
0x1800b3295  mov     rcx, rbx; hFile
0x1800b3298  call    ?CheckForRemovableMediaEfsEncryption@TrustLabelAceHelpers@@CAJPEAXPEA_N@Z; TrustLabelAceHelpers::CheckForRemovableMediaEfsEncryption(void *,bool *)
0x1800b329d  test    eax, eax
0x1800b329f  jns     loc_1800B4A74
0x1800b32a5  test    rbx, rbx
0x1800b32a8  jz      loc_1800B4A84
0x1800b32ae  mov     rcx, gs:60h
0x1800b32b7  mov     r8d, 0A0h; Size
0x1800b32bd  mov     edx, r12d; Flags
0x1800b32c0  mov     rcx, [rcx+30h]; HeapHandle
0x1800b32c4  call    cs:__imp_RtlAllocateHeap
0x1800b32ca  mov     r13, rax
0x1800b32cd  test    rax, rax
0x1800b32d0  jz      loc_1800B3536
0x1800b32d6  movups  xmm0, cs:xmmword_18039D390
0x1800b32dd  mov     esi, r14d
0x1800b32e0  mov     [rsp+1A0h+var_128], r14d
0x1800b32e5  movups  xmmword ptr [rax], xmm0
0x1800b32e8  movups  xmm1, cs:xmmword_18039D3A0
0x1800b32ef  movups  xmmword ptr [rax+10h], xmm1
0x1800b32f3  movups  xmm0, cs:xmmword_18039D3B0
0x1800b32fa  movups  xmmword ptr [rax+20h], xmm0
0x1800b32fe  movups  xmm1, cs:xmmword_18039D3C0
0x1800b3305  movups  xmmword ptr [rax+30h], xmm1
0x1800b3309  movups  xmm0, cs:xmmword_18039D3D0
0x1800b3310  movups  xmmword ptr [rax+40h], xmm0
0x1800b3314  movups  xmm1, cs:xmmword_18039D3E0
0x1800b331b  movups  xmmword ptr [rax+50h], xmm1
0x1800b331f  movups  xmm0, cs:xmmword_18039D3F0
0x1800b3326  movups  xmmword ptr [rax+60h], xmm0
0x1800b332a  movups  xmm1, cs:xmmword_18039D400
0x1800b3331  movups  xmmword ptr [rax+70h], xmm1
0x1800b3335  movups  xmm0, cs:xmmword_18039D410
0x1800b333c  movups  xmmword ptr [rax+80h], xmm0
0x1800b3343  movups  xmm1, cs:xmmword_18039D420
0x1800b334a  movups  xmmword ptr [rax+90h], xmm1
0x1800b3351  mov     rcx, gs:60h
0x1800b335a  mov     r8, r12; Size
0x1800b335d  mov     edx, r12d; Flags
0x1800b3360  mov     rcx, [rcx+30h]; HeapHandle
0x1800b3364  call    cs:__imp_RtlAllocateHeap
0x1800b336a  mov     rdi, rax
0x1800b336d  test    rax, rax
0x1800b3370  jz      loc_1800B340F
0x1800b3376  mov     rax, cs:qword_18039D2D8
0x1800b337d  mov     [rdi], rax
0x1800b3380  rdtsc
0x1800b3382  shl     rdx, 20h
0x1800b3386  or      rax, rdx
0x1800b3389  mov     r15, rax
0x1800b338c  mov     [rbp+0A0h+var_68], rax
0x1800b3390  mov     rcx, gs:60h
0x1800b3399  mov     esi, 0D0h
0x1800b339e  mov     r8d, esi; Size
0x1800b33a1  mov     edx, r12d; Flags
0x1800b33a4  mov     rcx, [rcx+30h]; HeapHandle
0x1800b33a8  call    cs:__imp_RtlAllocateHeap
0x1800b33ae  mov     r12, rax
0x1800b33b1  test    rax, rax
0x1800b33b4  jz      loc_1800B3567
0x1800b33ba  lea     rdx, [rax+4]
0x1800b33be  mov     [rbp+0A0h+var_A8], r14
0x1800b33c2  cmp     rdx, rax
0x1800b33c5  jnb     loc_1800B4A8F
0x1800b33cb  mov     r15d, 0C0000095h
0x1800b33d1  jmp     short loc_1800B3407
0x1800b33d3  mov     rcx, [rbp+0A8h]; this
0x1800b33da  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\trust\\trustla"...
0x1800b33e1  mov     edx, 27h ; '''; void *
0x1800b33e6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b33eb  jmp     loc_1800B321B
0x1800b33f0  lea     r15d, [rsi+0Ch]
0x1800b33f4  cmp     r15d, esi
0x1800b33f7  jnb     loc_1800B3A45
0x1800b33fd  mov     r15d, 0C0000095h
0x1800b3403  mov     r14, [rbp+0A0h+var_A8]
0x1800b3407  mov     esi, r14d
0x1800b340a  jmp     loc_1800B34B7
0x1800b340f  mov     r15d, 0C0000017h
0x1800b3415  mov     rdi, r14
0x1800b3418  mov     rcx, gs:60h
0x1800b3421  mov     r8, r13; P
0x1800b3424  xor     edx, edx; Flags
0x1800b3426  mov     rcx, [rcx+30h]; HeapHandle
0x1800b342a  call    cs:__imp_RtlFreeHeap
0x1800b3430  jmp     loc_1800B34D2
0x1800b3435  mov     rcx, [rsp+1A0h+var_148]
0x1800b343a  mov     r15d, 0D0000095h
0x1800b3440  mov     [rsp+1A0h+P], rdx
0x1800b3445  mov     [rsp+1A0h+var_148], rcx
0x1800b344a  test    rsi, rsi
0x1800b344d  jnz     loc_1800B4D01
0x1800b3453  test    r14, r14
0x1800b3456  jnz     loc_1800B497C
0x1800b345c  mov     rax, [rsp+1A0h+var_148]
0x1800b3461  test    rax, rax
0x1800b3464  jnz     loc_1800B3519
0x1800b346a  mov     rax, [rsp+1A0h+P]
0x1800b346f  test    rax, rax
0x1800b3472  jz      short loc_1800B348C
0x1800b3474  mov     rcx, gs:60h
0x1800b347d  mov     r8, rax; P
0x1800b3480  xor     edx, edx; Flags
0x1800b3482  mov     rcx, [rcx+30h]; HeapHandle
0x1800b3486  call    cs:__imp_RtlFreeHeap
0x1800b348c  mov     rsi, [rbp+0A0h+var_D0]
0x1800b3490  test    rsi, rsi
0x1800b3493  jnz     loc_1800B49F2
0x1800b3499  mov     rax, [rbp+0A0h+var_F0]
0x1800b349d  test    rax, rax
0x1800b34a0  jnz     loc_1800B4D62
0x1800b34a6  test    r15d, r15d
0x1800b34a9  jns     loc_1800B4D7F
0x1800b34af  mov     r14, [rbp+0A0h+var_A8]
0x1800b34b3  mov     esi, [rsp+1A0h+var_128]
0x1800b34b7  test    r12, r12
0x1800b34ba  jnz     loc_1800B4DA1
0x1800b34c0  test    r14, r14
0x1800b34c3  jnz     loc_1800B4DBE
0x1800b34c9  test    r13, r13
0x1800b34cc  jnz     loc_1800B3418
0x1800b34d2  test    rdi, rdi
0x1800b34d5  jnz     loc_1800B4DDB
0x1800b34db  test    r15d, r15d
0x1800b34de  js      loc_1800B4DF8
0x1800b34e4  lea     eax, [rsi-2]
0x1800b34e7  cmp     eax, 1
0x1800b34ea  ja      loc_1800B4E17
0x1800b34f0  cmp     [rbp+0A0h+arg_20], 0
0x1800b34f7  jnz     loc_180193032
0x1800b34fd  mov     rcx, rbx; this
0x1800b3500  call    ?CloseHandleHelper@Common@@YAXPEAX@Z; Common::CloseHandleHelper(void *)
0x1800b3505  mov     al, [rbp+0A0h+var_C8]
0x1800b3508  mov     rcx, [rbp+0A0h+var_58]
0x1800b350c  mov     rdx, [rbp+0A0h+var_50]
0x1800b3510  mov     rdi, [rbp+0A0h+var_60]
0x1800b3514  jmp     loc_1800B3210
0x1800b3519  mov     rcx, gs:60h
0x1800b3522  mov     r8, rax; P
0x1800b3525  xor     edx, edx; Flags
0x1800b3527  mov     rcx, [rcx+30h]; HeapHandle
0x1800b352b  call    cs:__imp_RtlFreeHeap
0x1800b3531  jmp     loc_1800B346A
0x1800b3536  mov     r15d, 0C0000017h
0x1800b353c  mov     rcx, [rbp+0A8h]; this
0x1800b3543  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\trust\\trustla"...
0x1800b354a  mov     r9d, r15d; char *
0x1800b354d  mov     edx, 33h ; '3'; void *
0x1800b3552  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b3557  mov     rcx, rbx; this
0x1800b355a  call    ?CloseHandleHelper@Common@@YAXPEAX@Z; Common::CloseHandleHelper(void *)
0x1800b355f  mov     eax, r15d
0x1800b3562  jmp     loc_1800B321B
0x1800b3567  mov     r15d, 0C0000017h
0x1800b356d  mov     esi, r14d
0x1800b3570  jmp     loc_1800B3418
0x1800b3575  movzx   r10d, [rsp+1A0h+var_156]
0x1800b357b  mov     rax, rsi
0x1800b357e  movzx   r15d, word ptr [rsp+1A0h+var_154]
0x1800b3584  mov     r12, rdx
0x1800b3587  movzx   r13d, word ptr [rsp+1A0h+var_154+2]
0x1800b358d  mov     r11d, r9d
0x1800b3590  mov     [rbp+0A0h+var_98], r14
0x1800b3594  mov     rbx, r8
0x1800b3597  movzx   r14d, cx
0x1800b359b  mov     dword ptr [rsp+1A0h+Size], 0
0x1800b35a3  mov     [rsp+1A0h+var_15C], 0
0x1800b35ab  mov     dword ptr [rsp+1A0h+var_150], 0
0x1800b35b3  mov     [rbp+0A0h+var_118], rsi
0x1800b35b7  movzx   edx, byte ptr [rax]
0x1800b35ba  movzx   esi, byte ptr [rax+1]
0x1800b35be  movzx   edi, byte ptr [rax+4]
0x1800b35c2  lea     rax, [rax+8]
0x1800b35c6  mov     r9d, [rsp+1A0h+var_154]
0x1800b35cb  shl     edx, 8
0x1800b35ce  or      esi, edx
0x1800b35d0  shl     edi, 8
0x1800b35d3  movzx   edx, byte ptr [rax-6]
0x1800b35d7  shl     esi, 8
0x1800b35da  or      esi, edx
0x1800b35dc  movzx   edx, byte ptr [rax-5]
0x1800b35e0  shl     esi, 8
0x1800b35e3  or      esi, edx
0x1800b35e5  movzx   edx, byte ptr [rax-3]
0x1800b35e9  or      edi, edx
0x1800b35eb  movzx   edx, byte ptr [rax-2]
0x1800b35ef  shl     edi, 8
0x1800b35f2  or      edi, edx
0x1800b35f4  movzx   edx, byte ptr [rax-1]
0x1800b35f8  shl     edi, 8
0x1800b35fb  or      edi, edx
0x1800b35fd  mov     r8d, edi
0x1800b3600  xor     r8d, r11d
0x1800b3603  mov     r11d, r8d
0x1800b3606  sub     r11d, r14d
0x1800b3609  xor     r11d, esi
0x1800b360c  xor     r11d, dword ptr [rsp+1A0h+var_150]
0x1800b3611  xor     r9d, r11d
0x1800b3614  ror     r11d, 0Fh
0x1800b3618  imul    r11d, r10d
0x1800b361c  mov     edx, r9d
0x1800b361f  ror     edx, 7
0x1800b3622  add     r11d, edx
0x1800b3625  xor     r11d, r8d
0x1800b3628  mov     r8d, [rsp+1A0h+var_154]
0x1800b362d  mov     edx, r11d
0x1800b3630  ror     edx, 0Ah
0x1800b3633  lea     r10d, [rcx+r11]
0x1800b3637  ror     r10d, 9
0x1800b363b  imul    r10d, r15d
0x1800b363f  sub     r10d, edx
0x1800b3642  xor     r10d, r9d
0x1800b3645  mov     r9d, r10d
0x1800b3648  mov     edx, r10d
0x1800b364b  ror     edx, 1Bh
0x1800b364e  xor     r9d, r15d
0x1800b3651  ror     r9d, 1Ch
0x1800b3655  imul    r9d, r13d
0x1800b3659  add     r9d, edx
0x1800b365c  xor     r9d, r11d
0x1800b365f  movzx   r11d, [rsp+1A0h+var_156]
0x1800b3665  mov     edx, r9d
0x1800b3668  xor     edx, ecx
0x1800b366a  sub     r8d, edx
0x1800b366d  xor     r8d, r10d
0x1800b3670  mov     r10d, r8d
0x1800b3673  mov     edx, r8d
0x1800b3676  shr     edx, 6
0x1800b3679  sub     r10d, r14d
0x1800b367c  imul    r10d, r11d
0x1800b3680  sub     r10d, edx
0x1800b3683  xor     r10d, r9d
0x1800b3686  mov     edx, r10d
0x1800b3689  ror     edx, 0Fh
0x1800b368c  xor     edx, r15d
0x1800b368f  imul    edx, r14d
0x1800b3693  xor     edx, r8d
0x1800b3696  mov     r8d, edx
0x1800b3699  not     r8d
0x1800b369c  ror     r8d, 3
0x1800b36a0  add     r8d, r13d
0x1800b36a3  imul    r8d, r15d
0x1800b36a7  xor     r8d, r10d
0x1800b36aa  mov     r9d, r8d
0x1800b36ad  sub     r9d, [rsp+1A0h+var_154]
0x1800b36b2  sub     r9d, r14d
0x1800b36b5  xor     r9d, edx
  ... truncated ...
```
