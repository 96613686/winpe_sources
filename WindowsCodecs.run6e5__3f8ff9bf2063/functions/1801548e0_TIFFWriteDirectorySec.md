# TIFFWriteDirectorySec

- ea: `0x1801548e0`
- end: `0x180157210`
- name: `TIFFWriteDirectorySec`
- size: `10544`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `35`
- tags: `broker_com_uri`

## callers

- `0x1801544a0`
- `0x1801548c0`

## callees

- `0x18014df00`
- `0x18014df40`
- `0x18014edc0`
- `0x18014ef80`
- `0x18014f1f0`
- `0x18014f270`
- `0x180153020`
- `0x180153970`
- `0x1801539c0`
- `0x180153c30`
- `0x180153ed0`
- `0x1801544a0`
- `0x1801548e0`
- `0x180157310`
- `0x180157610`
- `0x1801577f0`
- `0x180157ae0`
- `0x180158510`
- `0x180158760`
- `0x1801598d0`
- `0x18015a210`
- `0x18015a320`
- `0x18015a540`
- `0x18015a5d0`
- `0x18015b590`
- `0x18015b5f0`
- `0x18015b630`
- `0x18015b6b0`
- `0x18015b6e0`
- `0x18015b730`
- `0x1801636f0`
- `0x180163b40`
- `0x180164390`
- `0x18017b504`
- `0x1801ca010`

## string_xrefs

- `0x180157100`: `Starting directory %u at offset 0x%llx (%llu) might cause an IFD loop`
- `0x18015495b`: `TIFFWriteDirectorySec`
- `0x180154a03`: `TIFFWriteDirectorySec`
- `0x180156c0d`: `TIFFWriteDirectorySec`
- `0x180156d41`: `TIFFWriteDirectorySec`
- `0x180156dad`: `TIFFWriteDirectorySec`
- `0x180156dff`: `TIFFWriteDirectorySec`
- `0x180156ffa`: `TIFFWriteDirectorySec`
- `0x180157043`: `TIFFWriteDirectorySec`
- `0x18015710e`: `TIFFWriteDirectorySec`
- `0x180157174`: `TIFFWriteDirectorySec`
- `0x180156bbd`: `TIFFWriteDirectoryTagShortPerSample`
- `0x180156c25`: `TIFFWriteDirectoryTagLong8Array`
- `0x180156c2e`: `TIFFWriteDirectoryTagLong8Array`
- `0x180156c41`: `TIFFWriteDirectoryTagSlong8Array`
- `0x180156c7b`: `TIFFWriteDirectoryTagSlong8Array`
- `0x180156bc9`: `TIFFWriteDirectoryTagColormap`
- `0x180156b8a`: `TIFFWriteDirectoryTagCheckedRational`
- `0x180156bd5`: `TIFFWriteDirectoryTagCheckedRationalArray`
- `0x180156cbd`: `TIFFWriteDirectoryTagCheckedRationalArray`
- `0x180156d15`: `TIFFWriteDirectoryTagCheckedSrationalArray`
- `0x180156c91`: `TIFFWriteDirectoryTagCheckedRationalDoubleArray`
- `0x180156ce9`: `TIFFWriteDirectoryTagCheckedSrationalDoubleArray`
- `0x180154954`: `Error post-encoding before directory write`
- `0x18015499b`: `Error flushing data before directory write`
- `0x1801549f9`: `Creating TIFF with legacy Deflate codec identifier, COMPRESSION_ADOBE_DEFLATE is more widely supported`
- `0x180156c03`: `Cannot write tag %u (%s)`
- `0x180156799`: `TIFFLib: _TIFFWriteDirectorySec()`
- `0x180156ff0`: `IO error writing directory at seek to offset`
- `0x18015703c`: `IO error writing directory`
- `0x180156c1e`: `Attempt to write unsigned long value %llu larger than 0xFFFFFFFF for tag %d in Classic TIFF file. TIFF file writing aborted`
- `0x180156c72`: `Attempt to write signed long value %lli larger than 0x7FFFFFFF (2147483647) for tag %d in Classic TIFF file. TIFF writing to file aborted`
- `0x180156c3a`: `Attempt to write signed long value %lli smaller than 0x80000000 (-2147483648) for tag %d in Classic TIFF file. TIFF writing to file aborted`
- `0x180156370`: `TIFFWriteDirectoryTagCheckedLong8Array`
- `0x1801564be`: `TIFFWriteDirectoryTagCheckedSlong8Array`

## pseudocode

```c
_BOOL8 __fastcall TIFFWriteDirectorySec(__int64 a1, int a2, int a3, _QWORD *a4)
{
  int v5; // r14d
  __int64 v7; // r12
  unsigned __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  int v11; // eax
  unsigned __int64 v13; // rbx
  _WORD *v14; // r13
  __int64 v15; // r9
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  unsigned __int64 v45; // rax
  __int16 v46; // bx
  __int64 v47; // rax
  void *v48; // rsi
  unsigned __int16 v49; // r9
  __int64 v50; // r8
  _WORD *i; // rdx
  int v52; // ebx
  int v53; // ebx
  int v54; // eax
  unsigned __int64 v55; // rax
  __int16 v56; // bx
  __int64 v57; // rax
  void *v58; // rsi
  unsigned __int16 v59; // r9
  __int64 v60; // r8
  _WORD *j; // rdx
  int v62; // ebx
  int v63; // ebx
  unsigned __int64 v64; // rax
  __int16 v65; // bx
  __int64 v66; // rax
  void *v67; // rsi
  unsigned __int16 v68; // r9
  __int64 v69; // r8
  _WORD *k; // rdx
  int v71; // ebx
  int v72; // ebx
  __int64 v73; // r14
  unsigned __int64 v74; // rax
  char *v75; // rax
  char *v76; // rsi
  __int64 v77; // r8
  int v78; // ebx
  int v79; // ebx
  int v80; // eax
  unsigned __int64 v81; // rcx
  bool v82; // cf
  unsigned __int64 v83; // rax
  void *v84; // rsi
  unsigned __int64 v85; // rax
  __int16 v86; // bx
  __int64 v87; // rax
  void *v88; // rsi
  unsigned __int16 v89; // r9
  __int64 v90; // r8
  _WORD *m; // rdx
  int v92; // ebx
  int v93; // ebx
  __int64 v94; // rax
  __int64 v95; // rcx
  char *v96; // rsi
  __int64 v97; // rcx
  __int64 v98; // rcx
  __int64 v99; // rcx
  __int64 v100; // rcx
  __int64 v101; // rcx
  int v102; // ebx
  unsigned __int64 v103; // rcx
  unsigned __int64 v104; // rax
  unsigned __int64 v105; // rax
  __int64 n; // r14
  unsigned int *v107; // rsi
  unsigned __int16 v108; // dx
  int v109; // eax
  unsigned __int64 v110; // rax
  __int64 v111; // rax
  int v112; // eax
  __int64 v113; // rdx
  __int64 v114; // r8
  __int64 v115; // r9
  unsigned int v116; // eax
  unsigned __int64 v117; // rcx
  __int64 v118; // rdx
  __int64 v119; // rax
  __int64 v120; // rax
  __int64 v121; // rdx
  __int64 v122; // rsi
  unsigned __int16 *v123; // r8
  unsigned __int64 v124; // kr08_8
  __int64 v125; // kr10_8
  int v126; // eax
  unsigned __int64 v127; // rax
  unsigned __int64 v128; // rax
  int v129; // eax
  unsigned __int64 v130; // rcx
  unsigned __int64 v131; // rax
  void *v132; // rsi
  unsigned __int64 v133; // rax
  unsigned __int64 v134; // rcx
  void *v135; // rsi
  void *v136; // rsi
  void *v137; // rsi
  bool v138; // zf
  int v139; // eax
  _QWORD *v140; // rsi
  unsigned int v141; // eax
  __int64 v142; // rax
  void *v143; // r14
  int v144; // r8d
  _DWORD *v145; // rcx
  unsigned int v146; // eax
  int v147; // eax
  __int64 *v148; // rsi
  __int64 v149; // rax
  void *v150; // r14
  int v151; // r8d
  _DWORD *v152; // rcx
  signed __int64 v153; // r9
  int v154; // edx
  __int64 v155; // r15
  __int64 v156; // rax
  __int64 v157; // rcx
  unsigned int v158; // r14d
  __int64 ii; // rsi
  unsigned __int64 v160; // rax
  unsigned __int64 v161; // rcx
  __int64 v162; // r15
  __int64 v163; // rax
  __int64 v164; // rcx
  unsigned int v165; // r14d
  __int64 jj; // rsi
  __int64 v167; // r15
  __int64 v168; // rax
  __int64 v169; // rcx
  unsigned int v170; // r14d
  __int64 kk; // rsi
  __int64 v172; // r15
  __int64 v173; // rax
  __int64 v174; // rcx
  unsigned int v175; // r14d
  __int64 mm; // rsi
  void *v177; // rsi
  void *v178; // rsi
  void *v179; // rsi
  __int64 v180; // rax
  unsigned __int64 v181; // rax
  unsigned __int64 v182; // rax
  const char *v183; // rdx
  const char *v184; // rbx
  int v185; // eax
  const char *v186; // r8
  const char *v187; // rdx
  int v188; // eax
  _WORD *v189; // rcx
  __int64 v190; // rcx
  __int64 v191; // rax
  __int64 v192; // rcx
  __int64 v193; // rdx
  __int64 v194; // r8
  __int64 v195; // r9
  _QWORD *v196; // r12
  char *v197; // rbx
  unsigned int v198; // r15d
  _WORD *v199; // rsi
  _WORD *v200; // r14
  __int64 v201; // rdx
  __int64 v202; // r8
  __int64 v203; // r9
  unsigned int v204; // r15d
  _WORD *v205; // rsi
  _WORD *v206; // r14
  __int64 v207; // rsi
  int v208; // eax
  int v209; // ebx
  int v210; // eax
  void (__fastcall *v211)(__int64); // rax
  int v212; // eax
  int v213; // [rsp+28h] [rbp-89h]
  int v214; // [rsp+30h] [rbp-81h]
  int v215; // [rsp+30h] [rbp-81h]
  size_t Size; // [rsp+38h] [rbp-79h]
  void *v217; // [rsp+40h] [rbp-71h]
  void *v218; // [rsp+40h] [rbp-71h]
  int v219; // [rsp+48h] [rbp-69h] BYREF
  int v220[2]; // [rsp+50h] [rbp-61h]
  unsigned int v221; // [rsp+58h] [rbp-59h]
  unsigned __int16 v222; // [rsp+5Ch] [rbp-55h] BYREF
  __int16 v223[2]; // [rsp+60h] [rbp-51h] BYREF
  int v224; // [rsp+64h] [rbp-4Dh]
  int v225; // [rsp+68h] [rbp-49h]
  _BYTE v226[4]; // [rsp+70h] [rbp-41h] BYREF
  _BYTE v227[4]; // [rsp+74h] [rbp-3Dh] BYREF
  _BYTE v228[4]; // [rsp+78h] [rbp-39h] BYREF
  _BYTE v229[4]; // [rsp+7Ch] [rbp-35h] BYREF
  _BYTE v230[4]; // [rsp+80h] [rbp-31h] BYREF
  _BYTE v231[4]; // [rsp+84h] [rbp-2Dh] BYREF
  _BYTE v232[4]; // [rsp+88h] [rbp-29h] BYREF
  _BYTE v233[4]; // [rsp+8Ch] [rbp-25h] BYREF
  unsigned int v234; // [rsp+90h] [rbp-21h] BYREF
  int v235; // [rsp+94h] [rbp-1Dh] BYREF
  void *v236[2]; // [rsp+98h] [rbp-19h] BYREF
  char *Str; // [rsp+A8h] [rbp-9h] BYREF
  int Src; // [rsp+118h] [rbp+67h] BYREF
  int v239; // [rsp+120h] [rbp+6Fh]
  int v240; // [rsp+128h] [rbp+77h]
  _QWORD *v241; // [rsp+130h] [rbp+7Fh]

  v241 = a4;
  v240 = a3;
  v239 = a2;
  v5 = a2;
  v7 = 1;
  if ( !*(_DWORD *)(a1 + 12) )
    return 1;
  TIFFFillStriles();
  if ( a3 )
  {
    v11 = *(_DWORD *)(a1 + 16);
    if ( (v11 & 0x1000) != 0 )
    {
      *(_DWORD *)(a1 + 16) = v11 & 0xFFFFEFFF;
      if ( !(*(unsigned int (__fastcall **)(__int64))(a1 + 976))(a1) )
      {
        TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Error post-encoding before directory write");
        return 0;
      }
    }
    (*(void (__fastcall **)(__int64))(a1 + 1032))(a1);
    if ( *(__int64 *)(a1 + 1136) > 0 && (*(_BYTE *)(a1 + 16) & 0x40) != 0 && !(unsigned int)TIFFFlushData1(a1) )
    {
      TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Error flushing data before directory write");
      return 0;
    }
    if ( (*(_DWORD *)(a1 + 16) & 0x200) != 0 )
    {
      v8 = *(_QWORD *)(a1 + 1096);
      if ( v8 )
      {
        TIFFfreeExt(a1);
        *(_QWORD *)(a1 + 1096) = 0;
        *(_QWORD *)(a1 + 1136) = 0;
        *(_QWORD *)(a1 + 1104) = 0;
        *(_QWORD *)(a1 + 1112) = 0;
        *(_QWORD *)(a1 + 1120) = 0;
      }
    }
    *(_DWORD *)(a1 + 16) &= 0xFFFFFFAF;
  }
  if ( *(char *)(a1 + 72) < 0 && *(_WORD *)(a1 + 120) == 0x80B2 )
    TIFFWarningExtR(
      a1,
      "TIFFWriteDirectorySec",
      "Creating TIFF with legacy Deflate codec identifier, COMPRESSION_ADOBE_DEFLATE is more widely supported");
  v13 = a1 + 416;
  v14 = 0;
  *(_QWORD *)v220 = 0;
  v221 = 0;
  while ( 1 )
  {
    v219 = 0;
    v15 = 8;
    if ( !v14 )
      *(_QWORD *)v13 = 0;
    if ( !v5 )
      goto LABEL_358;
    if ( (*(_BYTE *)(a1 + 72) & 2) != 0 )
    {
      if ( *(_DWORD *)(a1 + 88) > 0xFFFFu )
      {
        if ( v14 )
        {
          v138 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 88);
          if ( !v138 )
            TIFFSwabLong(&Src, v8, v10, 8);
          LODWORD(Size) = 4;
          LOWORD(v213) = 4;
          v16 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 256, v213, 1, Size, &Src);
        }
        else
        {
          v219 = 1;
          v16 = 1;
        }
      }
      else if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 88);
        if ( !v138 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v213) = 3;
        v16 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 256, v213, 1, Size, &Src);
      }
      else
      {
        v219 = 1;
        v16 = 1;
      }
      if ( !v16 )
        goto LABEL_522;
      if ( *(_DWORD *)(a1 + 92) > 0xFFFFu )
      {
        if ( v14 )
        {
          v138 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 92);
          if ( !v138 )
            TIFFSwabLong(&Src, v8, v10, v15);
          LODWORD(Size) = 4;
          LOWORD(v213) = 4;
          v17 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 257, v213, 1, Size, &Src);
        }
        else
        {
          ++v219;
          v17 = 1;
        }
      }
      else if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 92);
        if ( !v138 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v213) = 3;
        v17 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 257, v213, 1, Size, &Src);
      }
      else
      {
        ++v219;
        v17 = 1;
      }
      if ( !v17 )
        goto LABEL_522;
    }
    if ( (*(_BYTE *)(a1 + 72) & 4) != 0 )
    {
      if ( *(_DWORD *)(a1 + 100) > 0xFFFFu )
      {
        if ( v14 )
        {
          v138 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 100);
          if ( !v138 )
            TIFFSwabLong(&Src, v8, v10, v15);
          LODWORD(Size) = 4;
          LOWORD(v213) = 4;
          v18 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 322, v213, 1, Size, &Src);
        }
        else
        {
          ++v219;
          v18 = 1;
        }
      }
      else if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 100);
        if ( !v138 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v213) = 3;
        v18 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 322, v213, 1, Size, &Src);
      }
      else
      {
        ++v219;
        v18 = 1;
      }
      if ( !v18 )
        goto LABEL_522;
      if ( *(_DWORD *)(a1 + 104) > 0xFFFFu )
      {
        if ( v14 )
        {
          v138 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 104);
          if ( !v138 )
            TIFFSwabLong(&Src, v8, v10, v15);
          LODWORD(Size) = 4;
          LOWORD(v213) = 4;
          v19 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 323, v213, 1, Size, &Src);
        }
        else
        {
          ++v219;
          v19 = 1;
        }
      }
      else if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 104);
        if ( !v138 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v213) = 3;
        v19 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 323, v213, 1, Size, &Src);
      }
      else
      {
        ++v219;
        v19 = 1;
      }
      if ( !v19 )
      {
LABEL_522:
        if ( !v14 )
          return 0;
LABEL_523:
        TIFFfreeExt(a1);
        return 0;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 8) != 0 )
    {
      if ( *(float *)(a1 + 160) < 0.0 )
        goto LABEL_524;
      if ( v14 )
      {
        DoubleToRational(v9, v226, v227);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v226, v21, v22, v23);
          TIFFSwabLong(v227, v24, v25, v26);
        }
        LODWORD(Size) = 8;
        LOWORD(v213) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 282, v213, 1, Size, v226) )
          goto LABEL_523;
      }
      else
      {
        v20 = *(_QWORD *)v13 + (((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8);
        ++v219;
        *(_QWORD *)(a1 + 416) = v20;
      }
      if ( *(float *)(a1 + 164) < 0.0 )
        goto LABEL_524;
      if ( v14 )
      {
        DoubleToRational(v9, v228, v229);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v228, v27, v28, v29);
          TIFFSwabLong(v229, v30, v31, v32);
        }
        LODWORD(Size) = 8;
        LOWORD(v213) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 283, v213, 1, Size, v228) )
          goto LABEL_523;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v219;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x10) != 0 )
    {
      if ( *(float *)(a1 + 172) < 0.0 )
        goto LABEL_524;
      if ( v14 )
      {
        DoubleToRational(v9, v230, v231);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v230, v33, v34, v35);
          TIFFSwabLong(v231, v36, v37, v38);
        }
        LODWORD(Size) = 8;
        LOWORD(v213) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 286, v213, 1, Size, v230) )
          goto LABEL_523;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v219;
      }
      if ( *(float *)(a1 + 176) < 0.0 )
      {
LABEL_524:
        TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRational", "Negative value is illegal");
        goto LABEL_522;
      }
      if ( v14 )
      {
        DoubleToRational(v9, v232, v233);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v232, v39, v40, v41);
          TIFFSwabLong(v233, v42, v43, v44);
        }
        LODWORD(Size) = 8;
        LOWORD(v213) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 287, v213, 1, Size, v232) )
          goto LABEL_523;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v219;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x20) != 0 )
    {
      if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 112);
        if ( !v138 )
          TIFFSwabLong(&Src, v8, v10, v15);
        LODWORD(Size) = 4;
        LOWORD(v213) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 254, v213, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v219;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x40) != 0 )
    {
      v8 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v14 )
      {
        v46 = *(_WORD *)(a1 + 116);
        v47 = TIFFmallocExt(a1, v8);
        v48 = (void *)v47;
        if ( !v47 )
          goto LABEL_525;
        v49 = *(_WORD *)(a1 + 130);
        v50 = 0;
        for ( i = (_WORD *)v47; (unsigned __int16)v50 < v49; LOWORD(v50) = v50 + 1 )
        {
          *i++ = v46;
          v49 = *(_WORD *)(a1 + 130);
        }
        v52 = v49;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v47, v49, v50);
        LODWORD(Size) = 2 * v52;
        LOWORD(v213) = 3;
        v53 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 258, v213, v52, Size, v48);
        TIFFfreeExt(a1);
        if ( !v53 )
          goto LABEL_523;
      }
      else
      {
        v45 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v45 = 8;
        if ( v8 > v45 )
          *(_QWORD *)(a1 + 416) += v8;
        ++v219;
      }
    }
    if ( *(char *)(a1 + 72) < 0 )
    {
      if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 120);
        if ( !v138 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v213) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 259, v213, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v219;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x100) != 0 )
    {
      if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 122);
        if ( !v138 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v213) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 262, v213, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v219;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x200) != 0 )
    {
      if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 124);
        if ( !v138 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v213) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 263, v213, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v219;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x400) != 0 )
    {
      if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 126);
        if ( !v138 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v213) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 266, v213, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v219;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x8000) != 0 )
    {
      if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 128);
        if ( !v138 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v213) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 274, v213, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v219;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x10000) != 0 )
    {
      if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 130);
        if ( !v138 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v213) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 277, v213, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v219;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x20000) != 0 )
    {
      if ( *(_DWORD *)(a1 + 132) > 0xFFFFu )
      {
        if ( v14 )
        {
          v138 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 132);
          if ( !v138 )
            TIFFSwabLong(&Src, v8, v10, v15);
          LODWORD(Size) = 4;
          LOWORD(v213) = 4;
          v54 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 278, v213, 1, Size, &Src);
        }
        else
        {
          ++v219;
          v54 = 1;
        }
      }
      else if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 132);
        if ( !v138 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v213) = 3;
        v54 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 278, v213, 1, Size, &Src);
      }
      else
      {
        ++v219;
        v54 = 1;
      }
      if ( !v54 )
        goto LABEL_522;
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x40000) != 0 )
    {
      v8 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v14 )
      {
        v56 = *(_WORD *)(a1 + 136);
        v57 = TIFFmallocExt(a1, v8);
        v58 = (void *)v57;
        if ( !v57 )
          goto LABEL_525;
        v59 = *(_WORD *)(a1 + 130);
        v60 = 0;
        for ( j = (_WORD *)v57; (unsigned __int16)v60 < v59; LOWORD(v60) = v60 + 1 )
        {
          *j++ = v56;
          v59 = *(_WORD *)(a1 + 130);
        }
        v62 = v59;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v57, v59, v60);
        LODWORD(Size) = 2 * v62;
        LOWORD(v213) = 3;
        v63 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 280, v213, v62, Size, v58);
        TIFFfreeExt(a1);
        if ( !v63 )
          goto LABEL_523;
      }
      else
      {
        v55 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v55 = 8;
        if ( v8 > v55 )
          *(_QWORD *)(a1 + 416) += v8;
        ++v219;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x80000) != 0 )
    {
      v8 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v14 )
      {
        v65 = *(_WORD *)(a1 + 138);
        v66 = TIFFmallocExt(a1, v8);
        v67 = (void *)v66;
        if ( !v66 )
          goto LABEL_525;
        v68 = *(_WORD *)(a1 + 130);
        v69 = 0;
        for ( k = (_WORD *)v66; (unsigned __int16)v69 < v68; LOWORD(v69) = v69 + 1 )
        {
          *k++ = v65;
          v68 = *(_WORD *)(a1 + 130);
        }
        v71 = v68;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v66, v68, v69);
        LODWORD(Size) = 2 * v71;
        LOWORD(v213) = 3;
        v72 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 281, v213, v71, Size, v67);
        TIFFfreeExt(a1);
        if ( !v72 )
          goto LABEL_523;
      }
      else
      {
        v64 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v64 = 8;
        if ( v8 > v64 )
          *(_QWORD *)(a1 + 416) += v8;
        ++v219;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x100000) != 0 )
    {
      if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 170);
        if ( !v138 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v213) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 284, v213, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v219;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x400000) != 0 )
    {
      if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 168);
        if ( !v138 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v213) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 296, v213, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v219;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x800000) != 0 )
    {
      if ( v14 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 180, 2, v10);
        LODWORD(Size) = 4;
        LOWORD(v213) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 297, v213, 2, Size, (void *)(a1 + 180)) )
          goto LABEL_523;
      }
      else
      {
        ++v219;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x1000000) != 0
      && !(unsigned int)TIFFWriteDirectoryTagLongLong8Array(
                          a1,
                          (int)&v219,
                          (int)v14,
                          *(_DWORD *)(a1 + 228),
                          *(void **)(a1 + 240))
      || (*(_DWORD *)(a1 + 72) & 0x2000000) != 0
      && ((*(_DWORD *)(a1 + 16) & 0x400) != 0 || *(_QWORD *)(a1 + 232))
      && !(unsigned int)TIFFWriteDirectoryTagLongLong8Array(
                          a1,
                          (int)&v219,
                          (int)v14,
                          *(_DWORD *)(a1 + 228),
                          *(void **)(a1 + 232)) )
    {
      goto LABEL_522;
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x4000000) != 0 )
    {
      v73 = (unsigned int)(1 << *(_BYTE *)(a1 + 116));
      v8 = 2LL * (unsigned int)(3 * v73);
      if ( v14 )
      {
        v75 = (char *)TIFFmallocExt(a1, v8);
        v76 = v75;
        if ( !v75 )
        {
          v183 = "TIFFWriteDirectoryTagColormap";
          goto LABEL_556;
        }
        TIFFmemcpy(v75, *(const void **)(a1 + 184), 2 * v73);
        TIFFmemcpy(&v76[2 * v73], *(const void **)(a1 + 192), 2 * v73);
        TIFFmemcpy(&v76[2 * (unsigned int)(2 * v73)], *(const void **)(a1 + 200), 2 * v73);
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v76, (unsigned int)(3 * v73), v77);
        LODWORD(Size) = 6 * v73;
        LOWORD(v213) = 3;
        v78 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 320, v213, 3 * (int)v73, Size, v76);
        TIFFfreeExt(a1);
        if ( !v78 )
          goto LABEL_523;
        v7 = 1;
      }
      else
      {
        v74 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v74 = 8;
        if ( v8 > v74 )
          *(_QWORD *)(a1 + 416) += v8;
        ++v219;
        v7 = 1;
      }
    }
    if ( *(int *)(a1 + 72) < 0 && *(_WORD *)(a1 + 212) )
    {
      TIFFGetFieldDefaulted(a1, 338, &v222, v236);
      v79 = v222;
      v80 = *(_DWORD *)(a1 + 16);
      if ( v14 )
      {
        v84 = v236[0];
        if ( (v80 & 0x80u) != 0 )
          TIFFSwabArrayOfShort(v236[0], v222, v10);
        LODWORD(Size) = 2 * v79;
        LOWORD(v213) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 338, v213, v79, Size, v84) )
          goto LABEL_523;
      }
      else
      {
        v81 = 2LL * v222;
        v82 = (v80 & 0x80000) != 0;
        v83 = 4;
        if ( v82 )
          v83 = 8;
        if ( v81 > v83 )
          *(_QWORD *)(a1 + 416) += v81;
        ++v219;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 1) != 0 )
    {
      v8 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v14 )
      {
        v86 = *(_WORD *)(a1 + 118);
        v87 = TIFFmallocExt(a1, v8);
        v88 = (void *)v87;
        if ( !v87 )
        {
LABEL_525:
          v183 = "TIFFWriteDirectoryTagShortPerSample";
          goto LABEL_556;
        }
        v89 = *(_WORD *)(a1 + 130);
        v90 = 0;
        for ( m = (_WORD *)v87; (unsigned __int16)v90 < v89; LOWORD(v90) = v90 + 1 )
        {
          *m++ = v86;
          v89 = *(_WORD *)(a1 + 130);
        }
        v92 = v89;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v87, v89, v90);
        LODWORD(Size) = 2 * v92;
        LOWORD(v213) = 3;
        v93 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 339, v213, v92, Size, v88);
        TIFFfreeExt(a1);
        if ( !v93 )
          goto LABEL_523;
      }
      else
      {
        v85 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v85 = 8;
        if ( v8 > v85 )
          *(_QWORD *)(a1 + 416) += v8;
        ++v219;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 2) != 0
      && !(unsigned int)TIFFWriteDirectoryTagSampleformatArray(
                          a1,
                          (int)&v219,
                          (int)v14,
                          *(unsigned __int16 *)(a1 + 130),
                          *(void **)(a1 + 144))
      || (*(_BYTE *)(a1 + 76) & 4) != 0
      && !(unsigned int)TIFFWriteDirectoryTagSampleformatArray(
                          a1,
                          (int)&v219,
                          (int)v14,
                          *(unsigned __int16 *)(a1 + 130),
                          *(void **)(a1 + 152)) )
    {
      goto LABEL_522;
    }
    if ( (*(_BYTE *)(a1 + 76) & 8) != 0 )
    {
      if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 96);
        if ( !v138 )
          TIFFSwabLong(&Src, v8, v10, v15);
        LODWORD(Size) = 4;
        LOWORD(v213) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 32997, v213, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v219;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 0x10) != 0 )
    {
      if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 108);
        if ( !v138 )
          TIFFSwabLong(&Src, v8, v10, v15);
        LODWORD(Size) = 4;
        LOWORD(v213) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 32998, v213, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v219;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 0x20) != 0 )
    {
      if ( v14 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 208, 2, v10);
        LODWORD(Size) = 4;
        v13 = 3;
        LOWORD(v213) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 321, v213, 2, Size, (void *)(a1 + 208)) )
          goto LABEL_523;
        goto LABEL_275;
      }
      ++v219;
    }
    v13 = 3;
LABEL_275:
    if ( *(char *)(a1 + 76) < 0 )
    {
      if ( v14 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 336, 2, v10);
        LODWORD(Size) = 4;
        v13 = 3;
        LOWORD(v213) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 530, v213, 2, Size, (void *)(a1 + 336)) )
          goto LABEL_523;
      }
      else
      {
        ++v219;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x100) != 0 )
    {
      if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 340);
        if ( !v138 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v213) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 531, v213, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v219;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x200) != 0 )
    {
      if ( v14 )
      {
        v94 = TIFFmallocExt(a1, 48);
        v96 = (char *)v94;
        if ( !v94 )
        {
          v183 = "TIFFWriteDirectoryTagCheckedRationalArray";
          goto LABEL_556;
        }
        DoubleToRational(v95, v94, v94 + 4);
        DoubleToRational(v97, v96 + 8, v96 + 12);
        DoubleToRational(v98, v96 + 16, v96 + 20);
        DoubleToRational(v99, v96 + 24, v96 + 28);
        DoubleToRational(v100, v96 + 32, v96 + 36);
        DoubleToRational(v101, v96 + 40, v96 + 44);
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfFloat(v96, 12);
        LODWORD(Size) = 48;
        LOWORD(v213) = 5;
        v102 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 532, v213, 6, Size, v96);
        TIFFfreeExt(a1);
        if ( !v102 )
          goto LABEL_523;
        v13 = 3;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += 48LL;
        ++v219;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x1000) != 0
      && !(unsigned int)TIFFWriteDirectoryTagTransferfunction(a1, (int)&v219, (int)v14) )
    {
      goto LABEL_522;
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x4000) != 0 )
    {
      v103 = *(unsigned int *)(a1 + 376);
      if ( v14 )
      {
        LODWORD(Size) = *(_DWORD *)(a1 + 376);
        LOWORD(v213) = 2;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(
                              a1,
                              (int)&v219,
                              (int)v14,
                              333,
                              v213,
                              v103,
                              Size,
                              *(void **)(a1 + 384)) )
          goto LABEL_523;
      }
      else
      {
        v104 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v104 = 8;
        if ( v103 > v104 )
        {
          v105 = v103 + 1;
          if ( (v103 & 1) == 0 )
            v105 = *(unsigned int *)(a1 + 376);
          *(_QWORD *)(a1 + 416) += v105;
        }
        ++v219;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x40000) != 0 )
    {
      if ( v14 )
      {
        v138 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 392);
        if ( !v138 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v213) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, 334, v213, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v219;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x20000) != 0 && !(unsigned int)TIFFWriteDirectoryTagSubifd(a1, (int)&v219, (int)v14) )
      goto LABEL_522;
    for ( n = 0; (unsigned __int64)(unsigned int)n < *(_QWORD *)(a1 + 1240); n = (unsigned int)(n + 1) )
    {
      v107 = *(unsigned int **)(*(_QWORD *)(a1 + 1232) + 8 * n);
      v108 = *((_WORD *)v107 + 12);
      if ( v108 >= 0x42u )
      {
        v109 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)v108 >> 5) + 72);
        if ( _bittest(&v109, v108 & 0x1F) )
        {
          switch ( v107[4] )
          {
            case 1u:
              TIFFGetField(a1, *v107, &Str);
              v13 = (unsigned __int64)Str;
              v116 = strlen_0(Str);
              if ( v14 )
              {
                LODWORD(Size) = v116;
                LOWORD(v213) = 2;
                v112 = TIFFWriteDirectoryTagData(
                         a1,
                         (int)&v219,
                         (int)v14,
                         *(unsigned __int16 *)v107,
                         v213,
                         v116,
                         Size,
                         (void *)v13);
                goto LABEL_356;
              }
              v117 = 4;
              v118 = v116;
              if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                v117 = 8;
              if ( v116 > v117 )
              {
                v138 = (v116 & 1) == 0;
                v119 = v116 + 1LL;
                if ( v138 )
                  v119 = v118;
                *(_QWORD *)(a1 + 416) += v119;
              }
              ++v219;
              break;
            case 4u:
              TIFFGetField(a1, *v107, v223);
              if ( v14 )
              {
                v138 = *(_BYTE *)(a1 + 16) >= 0;
                v13 = *(unsigned __int16 *)v107;
                LOWORD(Src) = v223[0];
                if ( !v138 )
                  TIFFSwabShort(&Src);
                LODWORD(Size) = 2;
                LOWORD(v213) = 3;
                v112 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, (unsigned __int16)v13, v213, 1, Size, &Src);
LABEL_356:
                if ( !v112 )
                  goto LABEL_523;
                continue;
              }
              ++v219;
              break;
            case 6u:
              TIFFGetField(a1, *v107, &v235);
              if ( v14 )
              {
                v138 = *(_BYTE *)(a1 + 16) >= 0;
                v13 = *(unsigned __int16 *)v107;
                Src = v235;
                if ( !v138 )
                  TIFFSwabLong(&Src, v113, v114, v115);
                LODWORD(Size) = 4;
                LOWORD(v213) = 4;
                v112 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, (unsigned __int16)v13, v213, 1, Size, &Src);
                goto LABEL_356;
              }
              ++v219;
              break;
            case 0x28u:
              TIFFGetField(a1, *v107, &v234);
              if ( v14 )
              {
                LODWORD(Size) = v234;
                LOWORD(v213) = 7;
                v112 = TIFFWriteDirectoryTagData(
                         a1,
                         (int)&v219,
                         (int)v14,
                         *(unsigned __int16 *)v107,
                         v213,
                         v234,
                         Size,
                         v236[1]);
                goto LABEL_356;
              }
              v110 = 4;
              if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                v110 = 8;
              if ( v234 > v110 )
              {
                v111 = v234 + 1LL;
                if ( (v234 & 1) == 0 )
                  v111 = v234;
                *(_QWORD *)(a1 + 416) += v111;
              }
              ++v219;
              break;
            default:
              v184 = "unknown";
              if ( *((_QWORD *)v107 + 4) )
                v184 = (const char *)*((_QWORD *)v107 + 4);
              v185 = TIFFFieldTag(v107);
              TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Cannot write tag %u (%s)", v185, v184);
              goto LABEL_522;
          }
        }
      }
    }
LABEL_358:
    v120 = 0;
    v225 = 0;
    if ( *(_DWORD *)(a1 + 396) )
    {
      while ( 1 )
      {
        v121 = *(_QWORD *)(a1 + 400);
        v122 = 3 * v120;
        v123 = *(unsigned __int16 **)(v121 + 24 * v120);
        v124 = v13;
        v125 = v7;
        v7 = *v123;
        v13 = *(unsigned int *)(v121 + 24 * v120 + 8);
        v126 = *((_DWORD *)v123 + 2) - 1;
        LOWORD(Src) = *v123;
        switch ( v126 )
        {
          case 0:
            if ( !v14 )
              goto LABEL_361;
            LODWORD(Size) = v13;
            LOWORD(v213) = 1;
            v129 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v219,
                     (int)v14,
                     (unsigned __int16)v7,
                     v213,
                     v13,
                     Size,
                     *(void **)(v121 + 8 * v122 + 16));
            goto LABEL_369;
          case 1:
            if ( !v14 )
              goto LABEL_361;
            LODWORD(Size) = v13;
            LOWORD(v213) = 2;
            v129 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v219,
                     (int)v14,
                     (unsigned __int16)v7,
                     v213,
                     v13,
                     Size,
                     *(void **)(v121 + 8 * v122 + 16));
            goto LABEL_369;
          case 2:
            if ( !v14 )
            {
              v130 = 2 * v13;
              goto LABEL_379;
            }
            v132 = *(void **)(v121 + 8 * v122 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfShort(v132, v13, v123);
            LODWORD(Size) = 2 * v13;
            LOWORD(v213) = 3;
            v129 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, (unsigned __int16)v7, v213, v13, Size, v132);
            goto LABEL_369;
          case 3:
            if ( !v14 )
            {
              v130 = 4 * v13;
              goto LABEL_379;
            }
            v136 = *(void **)(v121 + 8 * v122 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v136, v13);
            LODWORD(Size) = 4 * v13;
            LOWORD(v213) = 4;
            v129 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, (unsigned __int16)v7, v213, v13, Size, v136);
            goto LABEL_369;
          case 4:
            v224 = TIFFFieldSetGetSize(v123);
            v154 = v224;
            if ( v224 == 8 )
            {
              if ( !v14 )
                goto LABEL_440;
              v155 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v122 + 16);
              v156 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v13));
              v7 = v156;
              if ( !v156 )
              {
                TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRationalDoubleArray", "Out of memory");
                TIFFfreeExt(a1);
                return 0;
              }
              v158 = 0;
              for ( ii = v156; v158 < (unsigned int)v13; ++v158 )
              {
                DoubleToRational(v157, ii, ii + 4);
                ii += 8;
                v155 += 8;
              }
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v13));
              v217 = (void *)v7;
              LODWORD(Size) = 8 * v13;
              v214 = v13;
              LOWORD(v213) = 5;
              goto LABEL_447;
            }
            if ( !v14 )
              goto LABEL_450;
            v162 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v122 + 16);
            v163 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v13));
            v7 = v163;
            if ( !v163 )
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRationalArray", "Out of memory");
              TIFFfreeExt(a1);
              return 0;
            }
            v165 = 0;
            for ( jj = v163; v165 < (unsigned int)v13; ++v165 )
            {
              DoubleToRational(v164, jj, jj + 4);
              jj += 8;
              v162 += 4;
            }
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v13));
            v218 = (void *)v7;
            LODWORD(Size) = 8 * v13;
            v215 = v13;
            LOWORD(v213) = 5;
            goto LABEL_461;
          case 5:
            if ( !v14 )
              goto LABEL_361;
            LODWORD(Size) = v13;
            LOWORD(v213) = 6;
            v129 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v219,
                     (int)v14,
                     (unsigned __int16)v7,
                     v213,
                     v13,
                     Size,
                     *(void **)(v121 + 8 * v122 + 16));
            goto LABEL_369;
          case 6:
            if ( v14 )
            {
              LODWORD(Size) = v13;
              LOWORD(v213) = 7;
              v129 = TIFFWriteDirectoryTagData(
                       a1,
                       (int)&v219,
                       (int)v14,
                       (unsigned __int16)v7,
                       v213,
                       v13,
                       Size,
                       *(void **)(v121 + 8 * v122 + 16));
              goto LABEL_369;
            }
LABEL_361:
            v127 = 4;
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
              v127 = 8;
            if ( v13 > v127 )
            {
              v128 = v13 + 1;
              if ( (v13 & 1) == 0 )
                v128 = v13;
              *(_QWORD *)(a1 + 416) += v128;
            }
            goto LABEL_367;
          case 7:
            if ( v14 )
            {
              v135 = *(void **)(v121 + 8 * v122 + 16);
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfShort(v135, v13, v123);
              LODWORD(Size) = 2 * v13;
              LOWORD(v213) = 8;
              v129 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, (unsigned __int16)v7, v213, v13, Size, v135);
              goto LABEL_369;
            }
            v133 = 4;
            v134 = 2 * v13;
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
              v133 = 8;
            if ( v134 > v133 )
            {
              *(_QWORD *)(a1 + 416) += v134;
              ++v219;
              goto LABEL_497;
            }
            goto LABEL_367;
          case 8:
            if ( !v14 )
            {
              v130 = 4 * v13;
              goto LABEL_379;
            }
            v137 = *(void **)(v121 + 8 * v122 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v137, v13);
            LODWORD(Size) = 4 * v13;
            LOWORD(v213) = 9;
            v129 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, (unsigned __int16)v7, v213, v13, Size, v137);
            goto LABEL_369;
          case 9:
            v224 = TIFFFieldSetGetSize(v123);
            v154 = v224;
            if ( v224 == 8 )
            {
              if ( v14 )
              {
                v167 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v122 + 16);
                v168 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v13));
                v7 = v168;
                if ( !v168 )
                {
                  TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSrationalDoubleArray", "Out of memory");
                  TIFFfreeExt(a1);
                  return 0;
                }
                v170 = 0;
                for ( kk = v168; v170 < (unsigned int)v13; ++v170 )
                {
                  DoubleToSrational(v169, kk, kk + 4);
                  kk += 8;
                  v167 += 8;
                }
                if ( *(char *)(a1 + 16) < 0 )
                  TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v13));
                v217 = (void *)v7;
                LODWORD(Size) = 8 * v13;
                v214 = v13;
                LOWORD(v213) = 10;
LABEL_447:
                v14 = *(_WORD **)v220;
                v13 = (unsigned int)TIFFWriteDirectoryTagData(
                                      a1,
                                      (int)&v219,
                                      v220[0],
                                      (unsigned __int16)Src,
                                      v213,
                                      v214,
                                      Size,
                                      v217);
                TIFFfreeExt(a1);
                if ( !(_DWORD)v13 )
                  goto LABEL_523;
              }
              else
              {
LABEL_440:
                v130 = 4LL * (unsigned int)(2 * v13);
LABEL_379:
                v131 = 4;
                if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                  v131 = 8;
                if ( v130 <= v131 )
                {
LABEL_367:
                  ++v219;
                }
                else
                {
                  *(_QWORD *)(a1 + 416) += v130;
                  ++v219;
                }
              }
            }
            else
            {
              if ( v14 )
              {
                v172 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v122 + 16);
                v173 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v13));
                v7 = v173;
                if ( !v173 )
                {
                  TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSrationalArray", "Out of memory");
                  TIFFfreeExt(a1);
                  return 0;
                }
                v175 = 0;
                for ( mm = v173; v175 < (unsigned int)v13; ++v175 )
                {
                  DoubleToSrational(v174, mm, mm + 4);
                  mm += 8;
                  v172 += 4;
                }
                if ( *(char *)(a1 + 16) < 0 )
                  TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v13));
                v218 = (void *)v7;
                LODWORD(Size) = 8 * v13;
                v215 = v13;
                LOWORD(v213) = 10;
LABEL_461:
                v14 = *(_WORD **)v220;
                v13 = (unsigned int)TIFFWriteDirectoryTagData(
                                      a1,
                                      (int)&v219,
                                      v220[0],
                                      (unsigned __int16)Src,
                                      v213,
                                      v215,
                                      Size,
                                      v218);
                TIFFfreeExt(a1);
                if ( !(_DWORD)v13 )
                  goto LABEL_523;
                v154 = v224;
              }
              else
              {
LABEL_450:
                v160 = 4;
                v161 = 4LL * (unsigned int)(2 * v13);
                if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                  v160 = 8;
                if ( v161 > v160 )
                  *(_QWORD *)(a1 + 416) += v161;
                ++v219;
              }
              if ( v154 != 4 )
                TIFFErrorExtR(
                  a1,
                  "TIFFLib: _TIFFWriteDirectorySec()",
                  "Rational2Double: .set_field_type is not 4 but %d",
                  v154);
            }
            goto LABEL_497;
          case 10:
            if ( !v14 )
            {
              v130 = 4 * v13;
              goto LABEL_379;
            }
            v177 = *(void **)(v121 + 8 * v122 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v177, v13);
            LODWORD(Size) = 4 * v13;
            LOWORD(v213) = 11;
            v129 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, (unsigned __int16)v7, v213, v13, Size, v177);
            goto LABEL_369;
          case 11:
            if ( !v14 )
            {
              v130 = 8 * v13;
              goto LABEL_379;
            }
            v178 = *(void **)(v121 + 8 * v122 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfDouble(v178, v13, v123, 8);
            LODWORD(Size) = 8 * v13;
            LOWORD(v213) = 12;
            v129 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, (unsigned __int16)v7, v213, v13, Size, v178);
            goto LABEL_369;
          case 12:
            if ( !v14 )
            {
              v130 = 4 * v13;
              goto LABEL_379;
            }
            v179 = *(void **)(v121 + 8 * v122 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v179, v13);
            LODWORD(Size) = 4 * v13;
            LOWORD(v213) = 13;
            v129 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, (unsigned __int16)v7, v213, v13, Size, v179);
LABEL_369:
            if ( !v129 )
              goto LABEL_523;
            goto LABEL_497;
          case 15:
            if ( v14 )
            {
              v139 = *(_DWORD *)(a1 + 16);
              v140 = *(_QWORD **)(v121 + 8 * v122 + 16);
              if ( (v139 & 0x80000) != 0 )
              {
                if ( (v139 & 0x80u) != 0 )
                  TIFFSwabArrayOfDouble(v140, v13, v123, 8);
                LODWORD(Size) = 8 * v13;
                LOWORD(v213) = 16;
                v141 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, (unsigned __int16)v7, v213, v13, Size, v140);
LABEL_414:
                v13 = v141;
                v138 = v141 == 0;
                goto LABEL_496;
              }
              v142 = TIFFmallocExt(a1, 4 * v13);
              v143 = (void *)v142;
              if ( !v142 )
              {
                v183 = "TIFFWriteDirectoryTagLong8Array";
                goto LABEL_556;
              }
              v144 = 0;
              v145 = (_DWORD *)v142;
              if ( (_DWORD)v13 )
              {
                while ( *v140 <= 0xFFFFFFFF )
                {
                  *v145++ = *v140++;
                  if ( ++v144 >= (unsigned int)v13 )
                    goto LABEL_419;
                }
                v186 = "Attempt to write unsigned long value %llu larger than 0xFFFFFFFF for tag %d in Classic TIFF file."
                       " TIFF file writing aborted";
                v187 = "TIFFWriteDirectoryTagLong8Array";
LABEL_535:
                TIFFErrorExtR(a1, v187, v186);
                TIFFfreeExt(a1);
                TIFFfreeExt(a1);
                return 0;
              }
LABEL_419:
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v142, v13);
              LODWORD(Size) = 4 * v13;
              LOWORD(v213) = 4;
              v146 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, (unsigned __int16)v7, v213, v13, Size, v143);
LABEL_422:
              v13 = v146;
              TIFFfreeExt(a1);
              v138 = (_DWORD)v13 == 0;
              goto LABEL_496;
            }
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) == 0 )
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedLong8Array", "LONG8 not allowed for ClassicTIFF", 8);
              v13 = 0;
              v138 = 1;
              goto LABEL_496;
            }
            goto LABEL_407;
          case 16:
            if ( v14 )
            {
              v147 = *(_DWORD *)(a1 + 16);
              v148 = *(__int64 **)(v121 + 8 * v122 + 16);
              if ( (v147 & 0x80000) != 0 )
              {
                if ( (v147 & 0x80u) != 0 )
                  TIFFSwabArrayOfDouble(v148, v13, v123, 8);
                LODWORD(Size) = 8 * v13;
                LOWORD(v213) = 17;
                v141 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, (unsigned __int16)v7, v213, v13, Size, v148);
                goto LABEL_414;
              }
              v149 = TIFFmallocExt(a1, 4 * v13);
              v150 = (void *)v149;
              if ( !v149 )
              {
                v183 = "TIFFWriteDirectoryTagSlong8Array";
                goto LABEL_556;
              }
              v151 = 0;
              v152 = (_DWORD *)v149;
              if ( (_DWORD)v13 )
              {
                while ( 1 )
                {
                  v153 = *v148;
                  if ( *v148 > 0x7FFFFFFF )
                    break;
                  if ( v153 < (__int64)0xFFFFFFFF80000000uLL )
                  {
                    v186 = "Attempt to write signed long value %lli smaller than 0x80000000 (-2147483648) for tag %d in C"
                           "lassic TIFF file. TIFF writing to file aborted";
                    goto LABEL_534;
                  }
                  *v152 = v153;
                  ++v148;
                  ++v152;
                  if ( ++v151 >= (unsigned int)v13 )
                    goto LABEL_435;
                }
                v186 = "Attempt to write signed long value %lli larger than 0x7FFFFFFF (2147483647) for tag %d in Classic"
                       " TIFF file. TIFF writing to file aborted";
LABEL_534:
                v187 = "TIFFWriteDirectoryTagSlong8Array";
                goto LABEL_535;
              }
LABEL_435:
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v149, v13);
              LODWORD(Size) = 4 * v13;
              LOWORD(v213) = 9;
              v146 = TIFFWriteDirectoryTagData(a1, (int)&v219, (int)v14, (unsigned __int16)v7, v213, v13, Size, v150);
              goto LABEL_422;
            }
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
            {
LABEL_407:
              if ( 8 * v13 > 8 )
                *(_QWORD *)(a1 + 416) += 8 * v13;
              ++v219;
              v13 = 1;
              v138 = 0;
            }
            else
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSlong8Array", "SLONG8 not allowed for ClassicTIFF", 8);
              v13 = 0;
              v138 = 1;
            }
LABEL_496:
            if ( v138 )
              goto LABEL_522;
LABEL_497:
            v120 = (unsigned int)(v225 + 1);
            v225 = v120;
            if ( (unsigned int)v120 >= *(_DWORD *)(a1 + 396) )
              goto LABEL_498;
            break;
          case 17:
            v138 = (unsigned int)TIFFWriteDirectoryTagIfdIfd8Array(
                                   a1,
                                   (int)&v219,
                                   (int)v14,
                                   v13,
                                   *(void **)(v121 + 8 * v122 + 16)) == 0;
            goto LABEL_496;
          default:
            v7 = v125;
            v13 = v124;
            goto LABEL_497;
        }
      }
    }
LABEL_498:
    if ( v14 )
      break;
    v13 = a1 + 416;
    if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
      v180 = (unsigned int)(20 * v219 + 16);
    else
      v180 = (unsigned int)(12 * v219 + 6);
    *(_QWORD *)v13 = *(_QWORD *)(a1 + 416) + v180;
    *(_QWORD *)v220 = TIFFmallocExt(a1, 32LL * (unsigned int)v219);
    v14 = *(_WORD **)v220;
    if ( !*(_QWORD *)v220 )
    {
      TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Out of memory");
      return 0;
    }
    v5 = v239;
    if ( v239 )
    {
      if ( *(_QWORD *)(a1 + 24) )
      {
        if ( *(_QWORD *)v13 > *(_QWORD *)(a1 + 424) )
        {
          TIFFfreeExt(a1);
          return (unsigned int)TIFFRewriteDirectorySec(a1) != 0;
        }
      }
      else if ( !(unsigned int)TIFFLinkDirectory(a1) )
      {
        goto LABEL_523;
      }
    }
    else
    {
      v181 = *(_QWORD *)(a1 + 424);
      if ( !v181 || *(_QWORD *)v13 > v181 )
        *(_QWORD *)(a1 + 24) = ((*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 1200))(
                                  *(_QWORD *)(a1 + 1176),
                                  0,
                                  2)
                              + 1)
                             & 0xFFFFFFFFFFFFFFFEuLL;
    }
    if ( v241 )
      *v241 = *(_QWORD *)(a1 + 24);
    v8 = *(_QWORD *)(a1 + 24);
    if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
    {
      v10 = (unsigned int)(20 * v219 + 16);
      v182 = v10 + v8;
    }
    else
    {
      v10 = (unsigned int)(12 * v219 + 6);
      v182 = (unsigned int)(v8 + v10);
    }
    *(_QWORD *)(a1 + 880) = v182;
    v9 = (unsigned int)v10;
    v221 = v10;
    if ( v182 < v8 || v182 < (unsigned int)v10 )
    {
      TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Maximum TIFF file size exceeded");
      TIFFfreeExt(a1);
      return 0;
    }
    if ( (v182 & 1) != 0 )
      *(_QWORD *)(a1 + 880) = v182 + 1;
    v7 = 1;
  }
  if ( !v239 || (*(_DWORD *)(a1 + 76) & 0x20000) == 0 || *(_QWORD *)(a1 + 896) )
    goto LABEL_554;
  v188 = 0;
  v189 = v14;
  if ( !v219 )
  {
LABEL_550:
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Cannot find SubIFD tag", 8);
    TIFFfreeExt(a1);
    return 0;
  }
  while ( *v189 != 330 )
  {
    ++v188;
    v189 += 16;
    if ( v188 == v219 )
      goto LABEL_550;
  }
  v190 = *(_QWORD *)(a1 + 24);
  if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
  {
    v191 = (unsigned int)(20 * v188);
    v192 = v190 + 20;
  }
  else
  {
    v191 = (unsigned int)(12 * v188);
    v192 = v190 + 10;
  }
  *(_QWORD *)(a1 + 896) = v191 + v192;
LABEL_554:
  v196 = (_QWORD *)TIFFmallocExt(a1, v221);
  if ( !v196 )
  {
    v183 = "TIFFWriteDirectorySec";
LABEL_556:
    TIFFErrorExtR(a1, v183, "Out of memory");
    goto LABEL_523;
  }
  v197 = (char *)(a1 + 16);
  if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
  {
    *v196 = (unsigned int)v219;
    if ( *v197 < 0 )
      TIFFSwabLong8(v196);
    v204 = 0;
    v205 = v196 + 1;
    v206 = v14;
    if ( v219 )
    {
      do
      {
        *v205 = *v206;
        if ( *v197 < 0 )
          TIFFSwabShort(v205);
        v205[1] = v206[1];
        if ( *v197 < 0 )
          TIFFSwabShort(v205 + 1);
        TIFFmemcpy(v205 + 2, v206 + 4, 8u);
        if ( *v197 < 0 )
          TIFFSwabLong8(v205 + 2);
        TIFFmemcpy(v205 + 6, v206 + 8, 8u);
        v205 += 10;
        v206 += 16;
        ++v204;
      }
      while ( v204 < v219 );
      v197 = (char *)(a1 + 16);
    }
    TIFFmemcpy(v205, (const void *)(a1 + 32), 8u);
    if ( *v197 < 0 )
      TIFFSwabLong8(v205);
  }
  else
  {
    *(_WORD *)v196 = v219;
    if ( *v197 < 0 )
      TIFFSwabShort(v196);
    v198 = 0;
    v199 = (_WORD *)v196 + 1;
    v200 = v14;
    if ( v219 )
    {
      do
      {
        *v199 = *v200;
        if ( *v197 < 0 )
          TIFFSwabShort(v199);
        v199[1] = v200[1];
        if ( *v197 < 0 )
          TIFFSwabShort(v199 + 1);
        Src = *((_DWORD *)v200 + 2);
        TIFFmemcpy(v199 + 2, &Src, 4u);
        if ( *v197 < 0 )
          TIFFSwabLong(v199 + 2, v201, v202, v203);
        TIFFmemcpy(v199 + 4, v200 + 8, 4u);
        v199 += 6;
        v200 += 16;
        ++v198;
      }
      while ( v198 < v219 );
      v197 = (char *)(a1 + 16);
    }
    v138 = *v197 >= 0;
    Src = *(_DWORD *)(a1 + 32);
    if ( !v138 )
      TIFFSwabLong(&Src, v193, v194, v195);
    TIFFmemcpy(v199, &Src, 4u);
    v197 = (char *)(a1 + 16);
  }
  TIFFfreeExt(a1);
  if ( !(unsigned int)TIFFSeekOK(a1, *(_QWORD *)(a1 + 24)) )
  {
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "IO error writing directory at seek to offset");
    TIFFfreeExt(a1);
    return 0;
  }
  v207 = v221;
  if ( (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD))(a1 + 1192))(*(_QWORD *)(a1 + 1176), v196, v221) != v207 )
  {
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "IO error writing directory");
    TIFFfreeExt(a1);
    return 0;
  }
  TIFFfreeExt(a1);
  if ( !v239 || *(_BYTE *)(a1 + 409) )
  {
LABEL_600:
    v209 = v240;
    *(_BYTE *)(a1 + 409) = 1;
    if ( v209 )
    {
      v210 = *(_DWORD *)(a1 + 16);
      if ( (v210 & 0x2000) != 0 && !*(_WORD *)(a1 + 888) )
        *(_DWORD *)(a1 + 16) = v210 & 0xFFFFDFFF;
    }
    if ( !(unsigned int)TIFFCheckDirNumberAndOffset(a1, *(unsigned int *)(a1 + 848), *(_QWORD *)(a1 + 24)) )
      TIFFErrorExtR(
        a1,
        "TIFFWriteDirectorySec",
        "Starting directory %u at offset 0x%llx (%llu) might cause an IFD loop",
        *(_DWORD *)(a1 + 848),
        *(_QWORD *)(a1 + 24),
        *(_QWORD *)(a1 + 24));
    if ( v209 )
    {
      TIFFFreeDirectory(a1);
      v211 = *(void (__fastcall **)(__int64))(a1 + 1048);
      *(_DWORD *)(a1 + 16) &= 0xFFDFFFF7;
      v211(a1);
      TIFFCreateDirectory(a1);
    }
    else
    {
      *(_QWORD *)(a1 + 424) = *(_QWORD *)(a1 + 416);
    }
    return 1;
  }
  if ( (*(_DWORD *)v197 & 0x2000) != 0 && (*(_DWORD *)(a1 + 76) & 0x20000) == 0 )
  {
    v208 = 0;
    goto LABEL_597;
  }
  v208 = *(_DWORD *)(a1 + 852);
  if ( v208 != -1 )
  {
LABEL_597:
    *(_DWORD *)(a1 + 848) = v208;
    if ( (*(_DWORD *)(a1 + 16) & 0x2000) == 0 || (*(_DWORD *)(a1 + 76) & 0x20000) != 0 )
      ++*(_DWORD *)(a1 + 852);
    goto LABEL_600;
  }
  v212 = TIFFNumberOfDirectories(a1);
  *(_DWORD *)(a1 + 852) = v212;
  *(_DWORD *)(a1 + 848) = v212;
  TIFFErrorExtR(
    a1,
    "TIFFWriteDirectorySec",
    "tif_curdircount is TIFF_NON_EXISTENT_DIR_NUMBER, not expected !! Line %d",
    1330);
  TIFFfreeExt(a1);
  return 0;
}

```

## disassembly

```asm
0x1801548e0  mov     rax, rsp
0x1801548e3  mov     [rax+20h], r9
0x1801548e7  mov     [rax+18h], r8d
0x1801548eb  mov     [rax+10h], edx
0x1801548ee  push    rbp
0x1801548ef  push    rbx
0x1801548f0  push    rsi
0x1801548f1  push    rdi
0x1801548f2  push    r12
0x1801548f4  push    r13
0x1801548f6  push    r14
0x1801548f8  push    r15
0x1801548fa  lea     rbp, [rax-5Fh]
0x1801548fe  sub     rsp, 0C8h
0x180154905  cmp     dword ptr [rcx+0Ch], 0
0x180154909  mov     ebx, r8d
0x18015490c  movaps  xmmword ptr [rax-58h], xmm6
0x180154910  mov     r14d, edx
0x180154913  mov     rdi, rcx
0x180154916  mov     r12d, 1
0x18015491c  jz      loc_1801571A6
0x180154922  call    _TIFFFillStriles
0x180154927  xor     esi, esi
0x180154929  test    ebx, ebx
0x18015492b  jz      loc_1801549E8
0x180154931  mov     eax, [rdi+10h]
0x180154934  bt      eax, 0Ch
0x180154938  jnb     short loc_180154971
0x18015493a  btr     eax, 0Ch
0x18015493e  mov     rcx, rdi
0x180154941  mov     [rdi+10h], eax
0x180154944  mov     rax, [rdi+3D0h]
0x18015494b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154950  test    eax, eax
0x180154952  jnz     short loc_180154971
0x180154954  lea     r8, aErrorPostEncod; "Error post-encoding before directory wr"...
0x18015495b  lea     rdx, aTiffwritedirec_1; "TIFFWriteDirectorySec"
0x180154962  mov     rcx, rdi
0x180154965  call    TIFFErrorExtR
0x18015496a  xor     eax, eax
0x18015496c  jmp     loc_1801571A9
0x180154971  mov     rax, [rdi+408h]
0x180154978  mov     rcx, rdi
0x18015497b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154980  cmp     [rdi+470h], rsi
0x180154987  jle     short loc_1801549A4
0x180154989  test    byte ptr [rdi+10h], 40h
0x18015498d  jz      short loc_1801549A4
0x18015498f  mov     rcx, rdi
0x180154992  call    TIFFFlushData1
0x180154997  test    eax, eax
0x180154999  jnz     short loc_1801549A4
0x18015499b  lea     r8, aErrorFlushingD; "Error flushing data before directory wr"...
0x1801549a2  jmp     short loc_18015495B
0x1801549a4  test    dword ptr [rdi+10h], 200h
0x1801549ab  jz      short loc_1801549E4
0x1801549ad  mov     rdx, [rdi+448h]
0x1801549b4  test    rdx, rdx
0x1801549b7  jz      short loc_1801549E4
0x1801549b9  mov     rcx, rdi
0x1801549bc  call    _TIFFfreeExt
0x1801549c1  mov     [rdi+448h], rsi
0x1801549c8  mov     [rdi+470h], rsi
0x1801549cf  mov     [rdi+450h], rsi
0x1801549d6  mov     [rdi+458h], rsi
0x1801549dd  mov     [rdi+460h], rsi
0x1801549e4  and     dword ptr [rdi+10h], 0FFFFFFAFh
0x1801549e8  test    byte ptr [rdi+48h], 80h
0x1801549ec  jz      short loc_180154A0F
0x1801549ee  mov     eax, 80B2h
0x1801549f3  cmp     [rdi+78h], ax
0x1801549f7  jnz     short loc_180154A0F
0x1801549f9  lea     r8, aCreatingTiffWi; "Creating TIFF with legacy Deflate codec"...
0x180154a00  mov     rcx, rdi
0x180154a03  lea     rdx, aTiffwritedirec_1; "TIFFWriteDirectorySec"
0x180154a0a  call    TIFFWarningExtR
0x180154a0f  xor     eax, eax
0x180154a11  lea     rbx, [rdi+1A0h]
0x180154a18  mov     r13d, eax
0x180154a1b  mov     qword ptr [rbp+57h+var_B8], rax
0x180154a1f  mov     [rbp+57h+var_B0], eax
0x180154a22  xorps   xmm6, xmm6
0x180154a25  mov     [rbp+57h+var_C0], eax
0x180154a28  lea     r10, __ImageBase
0x180154a2f  mov     r11d, 7
0x180154a35  mov     r9d, 8
0x180154a3b  mov     r15d, 4
0x180154a41  mov     esi, 2
0x180154a46  test    r13, r13
0x180154a49  jnz     short loc_180154A4E
0x180154a4b  mov     [rbx], rax
0x180154a4e  test    r14d, r14d
0x180154a51  jz      loc_1801560DB
0x180154a57  test    byte ptr [rdi+48h], 2
0x180154a5b  jz      loc_180154BBB
0x180154a61  mov     eax, [rdi+58h]
0x180154a64  cmp     eax, 0FFFFh
0x180154a69  ja      short loc_180154AC4
0x180154a6b  test    r13, r13
0x180154a6e  jnz     short loc_180154A7C
0x180154a70  mov     [rbp+57h+var_C0], r12d
0x180154a74  mov     eax, r12d
0x180154a77  jmp     loc_180154B12
0x180154a7c  test    byte ptr [rdi+10h], 80h
0x180154a80  mov     word ptr [rbp+57h+Src], ax
0x180154a84  jz      short loc_180154A8F
0x180154a86  lea     rcx, [rbp+57h+Src]
0x180154a8a  call    TIFFSwabShort
0x180154a8f  lea     rax, [rbp+57h+Src]
0x180154a93  mov     r14d, 3
0x180154a99  mov     [rsp+38h], rax; Src
0x180154a9e  lea     rdx, [rbp+57h+var_C0]; int
0x180154aa2  mov     dword ptr [rsp+100h+Size], esi; Size
0x180154aa6  mov     r9d, 100h; int
0x180154aac  mov     dword ptr [rsp+100h+var_D8], r12d; int
0x180154ab1  mov     r8, r13; int
0x180154ab4  mov     rcx, rdi; int
0x180154ab7  mov     word ptr [rsp+100h+var_E0], r14w; int
0x180154abd  call    TIFFWriteDirectoryTagData
0x180154ac2  jmp     short loc_180154B18
0x180154ac4  test    r13, r13
0x180154ac7  jnz     short loc_180154AD2
0x180154ac9  mov     [rbp+57h+var_C0], r12d
0x180154acd  mov     eax, r12d
0x180154ad0  jmp     short loc_180154B12
0x180154ad2  test    byte ptr [rdi+10h], 80h
0x180154ad6  mov     [rbp+57h+Src], eax
0x180154ad9  jz      short loc_180154AE4
0x180154adb  lea     rcx, [rbp+57h+Src]
0x180154adf  call    TIFFSwabLong
0x180154ae4  lea     rax, [rbp+57h+Src]
0x180154ae8  mov     r9d, 100h; int
0x180154aee  mov     [rsp+38h], rax; Src
0x180154af3  lea     rdx, [rbp+57h+var_C0]; int
0x180154af7  mov     dword ptr [rsp+100h+Size], r15d; Size
0x180154afc  mov     r8, r13; int
0x180154aff  mov     dword ptr [rsp+100h+var_D8], r12d; int
0x180154b04  mov     rcx, rdi; int
0x180154b07  mov     word ptr [rsp+100h+var_E0], r15w; int
0x180154b0d  call    TIFFWriteDirectoryTagData
0x180154b12  mov     r14d, 3
0x180154b18  test    eax, eax
0x180154b1a  jz      loc_180156B99
0x180154b20  mov     eax, [rdi+5Ch]
0x180154b23  cmp     eax, 0FFFFh
0x180154b28  ja      short loc_180154B64
0x180154b2a  test    r13, r13
0x180154b2d  jnz     short loc_180154B37
0x180154b2f  inc     [rbp+57h+var_C0]
0x180154b32  mov     eax, r12d
0x180154b35  jmp     short loc_180154BB1
0x180154b37  test    byte ptr [rdi+10h], 80h
0x180154b3b  mov     word ptr [rbp+57h+Src], ax
0x180154b3f  jz      short loc_180154B4A
0x180154b41  lea     rcx, [rbp+57h+Src]
0x180154b45  call    TIFFSwabShort
0x180154b4a  lea     rax, [rbp+57h+Src]
0x180154b4e  mov     [rsp+38h], rax
0x180154b53  mov     dword ptr [rsp+100h+Size], esi
0x180154b57  mov     dword ptr [rsp+100h+var_D8], r12d
0x180154b5c  mov     word ptr [rsp+100h+var_E0], r14w
0x180154b62  jmp     short loc_180154B9C
0x180154b64  test    r13, r13
0x180154b67  jnz     short loc_180154B71
0x180154b69  inc     [rbp+57h+var_C0]
0x180154b6c  mov     eax, r12d
0x180154b6f  jmp     short loc_180154BB1
0x180154b71  test    byte ptr [rdi+10h], 80h
0x180154b75  mov     [rbp+57h+Src], eax
0x180154b78  jz      short loc_180154B83
0x180154b7a  lea     rcx, [rbp+57h+Src]
0x180154b7e  call    TIFFSwabLong
0x180154b83  lea     rax, [rbp+57h+Src]
0x180154b87  mov     [rsp+38h], rax; Src
0x180154b8c  mov     dword ptr [rsp+100h+Size], r15d; Size
0x180154b91  mov     dword ptr [rsp+100h+var_D8], r12d; int
0x180154b96  mov     word ptr [rsp+100h+var_E0], r15w; int
0x180154b9c  mov     r9d, 101h; int
0x180154ba2  lea     rdx, [rbp+57h+var_C0]; int
0x180154ba6  mov     r8, r13; int
0x180154ba9  mov     rcx, rdi; int
0x180154bac  call    TIFFWriteDirectoryTagData
0x180154bb1  test    eax, eax
0x180154bb3  jz      loc_180156B99
0x180154bb9  jmp     short loc_180154BC1
0x180154bbb  mov     r14d, 3
0x180154bc1  test    byte ptr [rdi+48h], 4
0x180154bc5  jz      loc_180154CFD
0x180154bcb  mov     eax, [rdi+64h]
0x180154bce  cmp     eax, 0FFFFh
0x180154bd3  ja      short loc_180154C0F
0x180154bd5  test    r13, r13
0x180154bd8  jnz     short loc_180154BE2
0x180154bda  inc     [rbp+57h+var_C0]
0x180154bdd  mov     eax, r12d
0x180154be0  jmp     short loc_180154C5C
0x180154be2  test    byte ptr [rdi+10h], 80h
0x180154be6  mov     word ptr [rbp+57h+Src], ax
0x180154bea  jz      short loc_180154BF5
0x180154bec  lea     rcx, [rbp+57h+Src]
0x180154bf0  call    TIFFSwabShort
0x180154bf5  lea     rax, [rbp+57h+Src]
0x180154bf9  mov     [rsp+38h], rax
0x180154bfe  mov     dword ptr [rsp+100h+Size], esi
0x180154c02  mov     dword ptr [rsp+100h+var_D8], r12d
0x180154c07  mov     word ptr [rsp+100h+var_E0], r14w
0x180154c0d  jmp     short loc_180154C47
0x180154c0f  test    r13, r13
0x180154c12  jnz     short loc_180154C1C
0x180154c14  inc     [rbp+57h+var_C0]
0x180154c17  mov     eax, r12d
0x180154c1a  jmp     short loc_180154C5C
0x180154c1c  test    byte ptr [rdi+10h], 80h
0x180154c20  mov     [rbp+57h+Src], eax
0x180154c23  jz      short loc_180154C2E
0x180154c25  lea     rcx, [rbp+57h+Src]
0x180154c29  call    TIFFSwabLong
0x180154c2e  lea     rax, [rbp+57h+Src]
0x180154c32  mov     [rsp+38h], rax; Src
0x180154c37  mov     dword ptr [rsp+100h+Size], r15d; Size
0x180154c3c  mov     dword ptr [rsp+100h+var_D8], r12d; int
0x180154c41  mov     word ptr [rsp+100h+var_E0], r15w; int
0x180154c47  mov     r9d, 142h; int
0x180154c4d  lea     rdx, [rbp+57h+var_C0]; int
0x180154c51  mov     r8, r13; int
0x180154c54  mov     rcx, rdi; int
0x180154c57  call    TIFFWriteDirectoryTagData
0x180154c5c  test    eax, eax
0x180154c5e  jz      loc_180156B99
0x180154c64  mov     eax, [rdi+68h]
0x180154c67  cmp     eax, 0FFFFh
0x180154c6c  ja      short loc_180154CA8
0x180154c6e  test    r13, r13
0x180154c71  jnz     short loc_180154C7B
0x180154c73  inc     [rbp+57h+var_C0]
0x180154c76  mov     eax, r12d
0x180154c79  jmp     short loc_180154CF5
0x180154c7b  test    byte ptr [rdi+10h], 80h
0x180154c7f  mov     word ptr [rbp+57h+Src], ax
0x180154c83  jz      short loc_180154C8E
0x180154c85  lea     rcx, [rbp+57h+Src]
0x180154c89  call    TIFFSwabShort
0x180154c8e  lea     rax, [rbp+57h+Src]
0x180154c92  mov     [rsp+38h], rax
0x180154c97  mov     dword ptr [rsp+100h+Size], esi
0x180154c9b  mov     dword ptr [rsp+100h+var_D8], r12d
0x180154ca0  mov     word ptr [rsp+100h+var_E0], r14w
0x180154ca6  jmp     short loc_180154CE0
0x180154ca8  test    r13, r13
0x180154cab  jnz     short loc_180154CB5
0x180154cad  inc     [rbp+57h+var_C0]
0x180154cb0  mov     eax, r12d
0x180154cb3  jmp     short loc_180154CF5
0x180154cb5  test    byte ptr [rdi+10h], 80h
0x180154cb9  mov     [rbp+57h+Src], eax
0x180154cbc  jz      short loc_180154CC7
0x180154cbe  lea     rcx, [rbp+57h+Src]
0x180154cc2  call    TIFFSwabLong
0x180154cc7  lea     rax, [rbp+57h+Src]
0x180154ccb  mov     [rsp+38h], rax; Src
0x180154cd0  mov     dword ptr [rsp+100h+Size], r15d; Size
0x180154cd5  mov     dword ptr [rsp+100h+var_D8], r12d; int
0x180154cda  mov     word ptr [rsp+100h+var_E0], r15w; int
0x180154ce0  mov     r9d, 143h; int
0x180154ce6  lea     rdx, [rbp+57h+var_C0]; int
0x180154cea  mov     r8, r13; int
0x180154ced  mov     rcx, rdi; int
0x180154cf0  call    TIFFWriteDirectoryTagData
0x180154cf5  test    eax, eax
0x180154cf7  jz      loc_180156B99
0x180154cfd  test    byte ptr [rdi+48h], 8
0x180154d01  jz      loc_180154E46
0x180154d07  movss   xmm0, dword ptr [rdi+0A0h]
0x180154d0f  cvtps2pd xmm0, xmm0
0x180154d12  comisd  xmm6, xmm0
0x180154d16  ja      loc_180156BB4
0x180154d1c  ucomisd xmm0, xmm0
0x180154d20  jp      loc_180156B83
0x180154d26  test    r13, r13
0x180154d29  jnz     short loc_180154D4B
0x180154d2b  mov     eax, [rdi+10h]
0x180154d2e  not     eax
0x180154d30  shr     rax, 10h
0x180154d34  and     eax, 8
0x180154d37  add     rax, [rbx]
0x180154d3a  mov     ebx, 5
0x180154d3f  inc     [rbp+57h+var_C0]
0x180154d42  mov     [rdi+1A0h], rax
0x180154d49  jmp     short loc_180154DAD
0x180154d4b  lea     r8, [rbp+57h+var_94]
0x180154d4f  lea     rdx, [rbp+57h+var_98]
0x180154d53  call    DoubleToRational
0x180154d58  test    byte ptr [rdi+10h], 80h
0x180154d5c  jz      short loc_180154D70
0x180154d5e  lea     rcx, [rbp+57h+var_98]
0x180154d62  call    TIFFSwabLong
0x180154d67  lea     rcx, [rbp+57h+var_94]
0x180154d6b  call    TIFFSwabLong
0x180154d70  lea     rax, [rbp+57h+var_98]
0x180154d74  mov     ebx, 5
  ... truncated ...
```
