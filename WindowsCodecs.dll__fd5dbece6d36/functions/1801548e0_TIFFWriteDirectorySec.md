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
  unsigned __int16 v50; // r8
  _WORD *i; // rdx
  int v52; // ebx
  int v53; // ebx
  int v54; // eax
  unsigned __int64 v55; // rax
  __int16 v56; // bx
  __int64 v57; // rax
  void *v58; // rsi
  unsigned __int16 v59; // r9
  unsigned __int16 v60; // r8
  _WORD *j; // rdx
  int v62; // ebx
  int v63; // ebx
  unsigned __int64 v64; // rax
  __int16 v65; // bx
  __int64 v66; // rax
  void *v67; // rsi
  unsigned __int16 v68; // r9
  unsigned __int16 v69; // r8
  _WORD *k; // rdx
  int v71; // ebx
  int v72; // ebx
  __int64 v73; // r14
  unsigned __int64 v74; // rax
  char *v75; // rax
  char *v76; // rsi
  int v77; // ebx
  int v78; // ebx
  int v79; // eax
  unsigned __int64 v80; // rcx
  bool v81; // cf
  unsigned __int64 v82; // rax
  void *v83; // rsi
  unsigned __int64 v84; // rax
  __int16 v85; // bx
  __int64 v86; // rax
  void *v87; // rsi
  unsigned __int16 v88; // r9
  unsigned __int16 v89; // r8
  _WORD *m; // rdx
  int v91; // ebx
  int v92; // ebx
  __int64 v93; // rax
  __int64 v94; // rcx
  char *v95; // rsi
  __int64 v96; // rcx
  __int64 v97; // rcx
  __int64 v98; // rcx
  __int64 v99; // rcx
  __int64 v100; // rcx
  int v101; // ebx
  unsigned __int64 v102; // rcx
  unsigned __int64 v103; // rax
  unsigned __int64 v104; // rax
  __int64 n; // r14
  unsigned int *v106; // rsi
  unsigned __int16 v107; // dx
  int v108; // eax
  unsigned __int64 v109; // rax
  __int64 v110; // rax
  int v111; // eax
  __int64 v112; // rdx
  __int64 v113; // r8
  __int64 v114; // r9
  __int64 v115; // rdx
  __int64 v116; // r8
  __int64 v117; // r9
  unsigned int v118; // eax
  unsigned __int64 v119; // rcx
  __int64 v120; // rdx
  __int64 v121; // rax
  __int64 v122; // rax
  __int64 v123; // rdx
  __int64 v124; // rsi
  unsigned __int16 *v125; // r8
  unsigned __int64 v126; // kr08_8
  __int64 v127; // kr10_8
  int v128; // eax
  unsigned __int64 v129; // rax
  unsigned __int64 v130; // rax
  int v131; // eax
  unsigned __int64 v132; // rcx
  unsigned __int64 v133; // rax
  void *v134; // rsi
  unsigned __int64 v135; // rax
  unsigned __int64 v136; // rcx
  void *v137; // rsi
  void *v138; // rsi
  void *v139; // rsi
  bool v140; // zf
  int v141; // eax
  _QWORD *v142; // rsi
  unsigned int v143; // eax
  __int64 v144; // rax
  void *v145; // r14
  int v146; // r8d
  _DWORD *v147; // rcx
  unsigned int v148; // eax
  int v149; // eax
  __int64 *v150; // rsi
  __int64 v151; // rax
  int v152; // r8d
  _DWORD *v153; // rcx
  signed __int64 v154; // r9
  int v155; // edx
  __int64 v156; // r15
  __int64 v157; // rax
  __int64 v158; // rcx
  unsigned int v159; // r14d
  __int64 ii; // rsi
  unsigned __int64 v161; // rax
  unsigned __int64 v162; // rcx
  __int64 v163; // r15
  __int64 v164; // rax
  __int64 v165; // rcx
  unsigned int v166; // r14d
  __int64 jj; // rsi
  __int64 v168; // r15
  __int64 v169; // rax
  __int64 v170; // rcx
  unsigned int v171; // r14d
  __int64 kk; // rsi
  __int64 v173; // r15
  __int64 v174; // rax
  __int64 v175; // rcx
  unsigned int v176; // r14d
  __int64 mm; // rsi
  void *v178; // rsi
  void *v179; // rsi
  void *v180; // rsi
  __int64 v181; // rax
  unsigned __int64 v182; // rax
  unsigned __int64 v183; // rax
  const char *v184; // rdx
  const char *v185; // rbx
  int v186; // eax
  const char *v187; // r8
  const char *v188; // rdx
  int v189; // eax
  _WORD *v190; // rcx
  __int64 v191; // rcx
  __int64 v192; // rax
  __int64 v193; // rcx
  __int64 v194; // rdx
  __int64 v195; // r8
  __int64 v196; // r9
  _QWORD *v197; // r12
  char *v198; // rbx
  unsigned int v199; // r15d
  _WORD *v200; // rsi
  _WORD *v201; // r14
  __int64 v202; // rdx
  __int64 v203; // r8
  __int64 v204; // r9
  unsigned int v205; // r15d
  _WORD *v206; // rsi
  _WORD *v207; // r14
  __int64 v208; // rsi
  int v209; // eax
  int v210; // ebx
  int v211; // eax
  void (__fastcall *v212)(__int64); // rax
  int v213; // eax
  int v214; // [rsp+28h] [rbp-89h]
  int v215; // [rsp+30h] [rbp-81h]
  int v216; // [rsp+30h] [rbp-81h]
  size_t Size; // [rsp+38h] [rbp-79h]
  void *v218; // [rsp+40h] [rbp-71h]
  void *v219; // [rsp+40h] [rbp-71h]
  int v220; // [rsp+48h] [rbp-69h] BYREF
  int v221[2]; // [rsp+50h] [rbp-61h]
  unsigned int v222; // [rsp+58h] [rbp-59h]
  unsigned __int16 v223; // [rsp+5Ch] [rbp-55h] BYREF
  __int16 v224[2]; // [rsp+60h] [rbp-51h] BYREF
  int v225; // [rsp+64h] [rbp-4Dh]
  int v226; // [rsp+68h] [rbp-49h]
  _BYTE v227[4]; // [rsp+70h] [rbp-41h] BYREF
  _BYTE v228[4]; // [rsp+74h] [rbp-3Dh] BYREF
  _BYTE v229[4]; // [rsp+78h] [rbp-39h] BYREF
  _BYTE v230[4]; // [rsp+7Ch] [rbp-35h] BYREF
  _BYTE v231[4]; // [rsp+80h] [rbp-31h] BYREF
  _BYTE v232[4]; // [rsp+84h] [rbp-2Dh] BYREF
  _BYTE v233[4]; // [rsp+88h] [rbp-29h] BYREF
  _BYTE v234[4]; // [rsp+8Ch] [rbp-25h] BYREF
  unsigned int v235; // [rsp+90h] [rbp-21h] BYREF
  int v236; // [rsp+94h] [rbp-1Dh] BYREF
  void *v237; // [rsp+98h] [rbp-19h]
  void *v238; // [rsp+A0h] [rbp-11h]
  char *Str; // [rsp+A8h] [rbp-9h] BYREF
  int Src; // [rsp+118h] [rbp+67h] BYREF
  int v241; // [rsp+120h] [rbp+6Fh]
  int v242; // [rsp+128h] [rbp+77h]
  _QWORD *v243; // [rsp+130h] [rbp+7Fh]

  v243 = a4;
  v242 = a3;
  v241 = a2;
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
        TIFFfreeExt(a1, v8);
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
  *(_QWORD *)v221 = 0;
  v222 = 0;
  while ( 1 )
  {
    v220 = 0;
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
          v140 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 88);
          if ( !v140 )
            TIFFSwabLong(&Src, v8, v10, 8);
          LODWORD(Size) = 4;
          LOWORD(v214) = 4;
          v16 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 256, v214, 1, Size, &Src);
        }
        else
        {
          v220 = 1;
          v16 = 1;
        }
      }
      else if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 88);
        if ( !v140 )
          TIFFSwabShort(&Src, v8, v10, 8);
        LODWORD(Size) = 2;
        LOWORD(v214) = 3;
        v16 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 256, v214, 1, Size, &Src);
      }
      else
      {
        v220 = 1;
        v16 = 1;
      }
      if ( !v16 )
        goto LABEL_522;
      if ( *(_DWORD *)(a1 + 92) > 0xFFFFu )
      {
        if ( v14 )
        {
          v140 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 92);
          if ( !v140 )
            TIFFSwabLong(&Src, v8, v10, v15);
          LODWORD(Size) = 4;
          LOWORD(v214) = 4;
          v17 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 257, v214, 1, Size, &Src);
        }
        else
        {
          ++v220;
          v17 = 1;
        }
      }
      else if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 92);
        if ( !v140 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v214) = 3;
        v17 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 257, v214, 1, Size, &Src);
      }
      else
      {
        ++v220;
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
          v140 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 100);
          if ( !v140 )
            TIFFSwabLong(&Src, v8, v10, v15);
          LODWORD(Size) = 4;
          LOWORD(v214) = 4;
          v18 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 322, v214, 1, Size, &Src);
        }
        else
        {
          ++v220;
          v18 = 1;
        }
      }
      else if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 100);
        if ( !v140 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v214) = 3;
        v18 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 322, v214, 1, Size, &Src);
      }
      else
      {
        ++v220;
        v18 = 1;
      }
      if ( !v18 )
        goto LABEL_522;
      if ( *(_DWORD *)(a1 + 104) > 0xFFFFu )
      {
        if ( v14 )
        {
          v140 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 104);
          if ( !v140 )
            TIFFSwabLong(&Src, v8, v10, v15);
          LODWORD(Size) = 4;
          LOWORD(v214) = 4;
          v19 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 323, v214, 1, Size, &Src);
        }
        else
        {
          ++v220;
          v19 = 1;
        }
      }
      else if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 104);
        if ( !v140 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v214) = 3;
        v19 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 323, v214, 1, Size, &Src);
      }
      else
      {
        ++v220;
        v19 = 1;
      }
      if ( !v19 )
      {
LABEL_522:
        if ( !v14 )
          return 0;
LABEL_523:
        TIFFfreeExt(a1, v14);
        return 0;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 8) != 0 )
    {
      if ( *(float *)(a1 + 160) < 0.0 )
        goto LABEL_524;
      if ( v14 )
      {
        DoubleToRational(v9, v227, v228);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v227, v21, v22, v23);
          TIFFSwabLong(v228, v24, v25, v26);
        }
        LODWORD(Size) = 8;
        LOWORD(v214) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 282, v214, 1, Size, v227) )
          goto LABEL_523;
      }
      else
      {
        v20 = *(_QWORD *)v13 + (((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8);
        ++v220;
        *(_QWORD *)(a1 + 416) = v20;
      }
      if ( *(float *)(a1 + 164) < 0.0 )
        goto LABEL_524;
      if ( v14 )
      {
        DoubleToRational(v9, v229, v230);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v229, v27, v28, v29);
          TIFFSwabLong(v230, v30, v31, v32);
        }
        LODWORD(Size) = 8;
        LOWORD(v214) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 283, v214, 1, Size, v229) )
          goto LABEL_523;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v220;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x10) != 0 )
    {
      if ( *(float *)(a1 + 172) < 0.0 )
        goto LABEL_524;
      if ( v14 )
      {
        DoubleToRational(v9, v231, v232);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v231, v33, v34, v35);
          TIFFSwabLong(v232, v36, v37, v38);
        }
        LODWORD(Size) = 8;
        LOWORD(v214) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 286, v214, 1, Size, v231) )
          goto LABEL_523;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v220;
      }
      if ( *(float *)(a1 + 176) < 0.0 )
      {
LABEL_524:
        TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRational", "Negative value is illegal");
        goto LABEL_522;
      }
      if ( v14 )
      {
        DoubleToRational(v9, v233, v234);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v233, v39, v40, v41);
          TIFFSwabLong(v234, v42, v43, v44);
        }
        LODWORD(Size) = 8;
        LOWORD(v214) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 287, v214, 1, Size, v233) )
          goto LABEL_523;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v220;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x20) != 0 )
    {
      if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 112);
        if ( !v140 )
          TIFFSwabLong(&Src, v8, v10, v15);
        LODWORD(Size) = 4;
        LOWORD(v214) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 254, v214, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v220;
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
        for ( i = (_WORD *)v47; v50 < v49; ++v50 )
        {
          *i++ = v46;
          v49 = *(_WORD *)(a1 + 130);
        }
        v52 = v49;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v47, v49);
        LODWORD(Size) = 2 * v52;
        LOWORD(v214) = 3;
        v53 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 258, v214, v52, Size, v48);
        TIFFfreeExt(a1, v48);
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
        ++v220;
      }
    }
    if ( *(char *)(a1 + 72) < 0 )
    {
      if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 120);
        if ( !v140 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v214) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 259, v214, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v220;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x100) != 0 )
    {
      if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 122);
        if ( !v140 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v214) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 262, v214, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v220;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x200) != 0 )
    {
      if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 124);
        if ( !v140 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v214) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 263, v214, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v220;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x400) != 0 )
    {
      if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 126);
        if ( !v140 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v214) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 266, v214, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v220;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x8000) != 0 )
    {
      if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 128);
        if ( !v140 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v214) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 274, v214, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v220;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x10000) != 0 )
    {
      if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 130);
        if ( !v140 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v214) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 277, v214, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v220;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x20000) != 0 )
    {
      if ( *(_DWORD *)(a1 + 132) > 0xFFFFu )
      {
        if ( v14 )
        {
          v140 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 132);
          if ( !v140 )
            TIFFSwabLong(&Src, v8, v10, v15);
          LODWORD(Size) = 4;
          LOWORD(v214) = 4;
          v54 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 278, v214, 1, Size, &Src);
        }
        else
        {
          ++v220;
          v54 = 1;
        }
      }
      else if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 132);
        if ( !v140 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v214) = 3;
        v54 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 278, v214, 1, Size, &Src);
      }
      else
      {
        ++v220;
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
        for ( j = (_WORD *)v57; v60 < v59; ++v60 )
        {
          *j++ = v56;
          v59 = *(_WORD *)(a1 + 130);
        }
        v62 = v59;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v57, v59);
        LODWORD(Size) = 2 * v62;
        LOWORD(v214) = 3;
        v63 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 280, v214, v62, Size, v58);
        TIFFfreeExt(a1, v58);
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
        ++v220;
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
        for ( k = (_WORD *)v66; v69 < v68; ++v69 )
        {
          *k++ = v65;
          v68 = *(_WORD *)(a1 + 130);
        }
        v71 = v68;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v66, v68);
        LODWORD(Size) = 2 * v71;
        LOWORD(v214) = 3;
        v72 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 281, v214, v71, Size, v67);
        TIFFfreeExt(a1, v67);
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
        ++v220;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x100000) != 0 )
    {
      if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 170);
        if ( !v140 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v214) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 284, v214, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v220;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x400000) != 0 )
    {
      if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 168);
        if ( !v140 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v214) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 296, v214, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v220;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x800000) != 0 )
    {
      if ( v14 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 180, 2);
        LODWORD(Size) = 4;
        LOWORD(v214) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 297, v214, 2, Size, (void *)(a1 + 180)) )
          goto LABEL_523;
      }
      else
      {
        ++v220;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x1000000) != 0
      && !(unsigned int)TIFFWriteDirectoryTagLongLong8Array(
                          a1,
                          (int)&v220,
                          (int)v14,
                          *(_DWORD *)(a1 + 228),
                          *(void **)(a1 + 240))
      || (*(_DWORD *)(a1 + 72) & 0x2000000) != 0
      && ((*(_DWORD *)(a1 + 16) & 0x400) != 0 || *(_QWORD *)(a1 + 232))
      && !(unsigned int)TIFFWriteDirectoryTagLongLong8Array(
                          a1,
                          (int)&v220,
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
          v184 = "TIFFWriteDirectoryTagColormap";
          goto LABEL_556;
        }
        TIFFmemcpy(v75, *(const void **)(a1 + 184), 2 * v73);
        TIFFmemcpy(&v76[2 * v73], *(const void **)(a1 + 192), 2 * v73);
        TIFFmemcpy(&v76[2 * (unsigned int)(2 * v73)], *(const void **)(a1 + 200), 2 * v73);
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v76, (unsigned int)(3 * v73));
        LODWORD(Size) = 6 * v73;
        LOWORD(v214) = 3;
        v77 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 320, v214, 3 * (int)v73, Size, v76);
        TIFFfreeExt(a1, v76);
        if ( !v77 )
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
        ++v220;
        v7 = 1;
      }
    }
    if ( *(int *)(a1 + 72) < 0 && *(_WORD *)(a1 + 212) )
    {
      TIFFGetFieldDefaulted(a1, 338, &v223);
      v78 = v223;
      v79 = *(_DWORD *)(a1 + 16);
      if ( v14 )
      {
        v83 = v237;
        if ( (v79 & 0x80u) != 0 )
          TIFFSwabArrayOfShort(v237, v223);
        LODWORD(Size) = 2 * v78;
        LOWORD(v214) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 338, v214, v78, Size, v83) )
          goto LABEL_523;
      }
      else
      {
        v80 = 2LL * v223;
        v81 = (v79 & 0x80000) != 0;
        v82 = 4;
        if ( v81 )
          v82 = 8;
        if ( v80 > v82 )
          *(_QWORD *)(a1 + 416) += v80;
        ++v220;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 1) != 0 )
    {
      v8 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v14 )
      {
        v85 = *(_WORD *)(a1 + 118);
        v86 = TIFFmallocExt(a1, v8);
        v87 = (void *)v86;
        if ( !v86 )
        {
LABEL_525:
          v184 = "TIFFWriteDirectoryTagShortPerSample";
          goto LABEL_556;
        }
        v88 = *(_WORD *)(a1 + 130);
        v89 = 0;
        for ( m = (_WORD *)v86; v89 < v88; ++v89 )
        {
          *m++ = v85;
          v88 = *(_WORD *)(a1 + 130);
        }
        v91 = v88;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v86, v88);
        LODWORD(Size) = 2 * v91;
        LOWORD(v214) = 3;
        v92 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 339, v214, v91, Size, v87);
        TIFFfreeExt(a1, v87);
        if ( !v92 )
          goto LABEL_523;
      }
      else
      {
        v84 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v84 = 8;
        if ( v8 > v84 )
          *(_QWORD *)(a1 + 416) += v8;
        ++v220;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 2) != 0
      && !(unsigned int)TIFFWriteDirectoryTagSampleformatArray(
                          a1,
                          (int)&v220,
                          (int)v14,
                          *(unsigned __int16 *)(a1 + 130),
                          *(void **)(a1 + 144))
      || (*(_BYTE *)(a1 + 76) & 4) != 0
      && !(unsigned int)TIFFWriteDirectoryTagSampleformatArray(
                          a1,
                          (int)&v220,
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
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 96);
        if ( !v140 )
          TIFFSwabLong(&Src, v8, v10, v15);
        LODWORD(Size) = 4;
        LOWORD(v214) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 32997, v214, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v220;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 0x10) != 0 )
    {
      if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 108);
        if ( !v140 )
          TIFFSwabLong(&Src, v8, v10, v15);
        LODWORD(Size) = 4;
        LOWORD(v214) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 32998, v214, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v220;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 0x20) != 0 )
    {
      if ( v14 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 208, 2);
        LODWORD(Size) = 4;
        v13 = 3;
        LOWORD(v214) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 321, v214, 2, Size, (void *)(a1 + 208)) )
          goto LABEL_523;
        goto LABEL_275;
      }
      ++v220;
    }
    v13 = 3;
LABEL_275:
    if ( *(char *)(a1 + 76) < 0 )
    {
      if ( v14 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 336, 2);
        LODWORD(Size) = 4;
        v13 = 3;
        LOWORD(v214) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 530, v214, 2, Size, (void *)(a1 + 336)) )
          goto LABEL_523;
      }
      else
      {
        ++v220;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x100) != 0 )
    {
      if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 340);
        if ( !v140 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v214) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 531, v214, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v220;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x200) != 0 )
    {
      if ( v14 )
      {
        v93 = TIFFmallocExt(a1, 48);
        v95 = (char *)v93;
        if ( !v93 )
        {
          v184 = "TIFFWriteDirectoryTagCheckedRationalArray";
          goto LABEL_556;
        }
        DoubleToRational(v94, v93, v93 + 4);
        DoubleToRational(v96, v95 + 8, v95 + 12);
        DoubleToRational(v97, v95 + 16, v95 + 20);
        DoubleToRational(v98, v95 + 24, v95 + 28);
        DoubleToRational(v99, v95 + 32, v95 + 36);
        DoubleToRational(v100, v95 + 40, v95 + 44);
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfFloat(v95, 12);
        LODWORD(Size) = 48;
        LOWORD(v214) = 5;
        v101 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 532, v214, 6, Size, v95);
        TIFFfreeExt(a1, v95);
        if ( !v101 )
          goto LABEL_523;
        v13 = 3;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += 48LL;
        ++v220;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x1000) != 0
      && !(unsigned int)TIFFWriteDirectoryTagTransferfunction(a1, (int)&v220, (int)v14) )
    {
      goto LABEL_522;
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x4000) != 0 )
    {
      v102 = *(unsigned int *)(a1 + 376);
      if ( v14 )
      {
        LODWORD(Size) = *(_DWORD *)(a1 + 376);
        LOWORD(v214) = 2;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(
                              a1,
                              (int)&v220,
                              (int)v14,
                              333,
                              v214,
                              v102,
                              Size,
                              *(void **)(a1 + 384)) )
          goto LABEL_523;
      }
      else
      {
        v103 = 4;
        v8 = (unsigned int)v102;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v103 = 8;
        if ( v102 > v103 )
        {
          v104 = v102 + 1;
          if ( (v102 & 1) == 0 )
            v104 = *(unsigned int *)(a1 + 376);
          *(_QWORD *)(a1 + 416) += v104;
        }
        ++v220;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x40000) != 0 )
    {
      if ( v14 )
      {
        v140 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 392);
        if ( !v140 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v214) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, 334, v214, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v220;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x20000) != 0 && !(unsigned int)TIFFWriteDirectoryTagSubifd(a1, (int)&v220, (int)v14) )
      goto LABEL_522;
    for ( n = 0; (unsigned __int64)(unsigned int)n < *(_QWORD *)(a1 + 1240); n = (unsigned int)(n + 1) )
    {
      v106 = *(unsigned int **)(*(_QWORD *)(a1 + 1232) + 8 * n);
      v107 = *((_WORD *)v106 + 12);
      if ( v107 >= 0x42u )
      {
        v108 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)v107 >> 5) + 72);
        if ( _bittest(&v108, v107 & 0x1F) )
        {
          switch ( v106[4] )
          {
            case 1u:
              TIFFGetField(a1, *v106, &Str);
              v13 = (unsigned __int64)Str;
              v118 = strlen_0(Str);
              if ( v14 )
              {
                LODWORD(Size) = v118;
                LOWORD(v214) = 2;
                v111 = TIFFWriteDirectoryTagData(
                         a1,
                         (int)&v220,
                         (int)v14,
                         *(unsigned __int16 *)v106,
                         v214,
                         v118,
                         Size,
                         (void *)v13);
                goto LABEL_356;
              }
              v119 = 4;
              v120 = v118;
              if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                v119 = 8;
              if ( v118 > v119 )
              {
                v140 = (v118 & 1) == 0;
                v121 = v118 + 1LL;
                if ( v140 )
                  v121 = v120;
                *(_QWORD *)(a1 + 416) += v121;
              }
              ++v220;
              break;
            case 4u:
              TIFFGetField(a1, *v106, v224);
              if ( v14 )
              {
                v140 = *(_BYTE *)(a1 + 16) >= 0;
                v13 = *(unsigned __int16 *)v106;
                LOWORD(Src) = v224[0];
                if ( !v140 )
                  TIFFSwabShort(&Src, v115, v116, v117);
                LODWORD(Size) = 2;
                LOWORD(v214) = 3;
                v111 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, (unsigned __int16)v13, v214, 1, Size, &Src);
LABEL_356:
                if ( !v111 )
                  goto LABEL_523;
                continue;
              }
              ++v220;
              break;
            case 6u:
              TIFFGetField(a1, *v106, &v236);
              if ( v14 )
              {
                v140 = *(_BYTE *)(a1 + 16) >= 0;
                v13 = *(unsigned __int16 *)v106;
                Src = v236;
                if ( !v140 )
                  TIFFSwabLong(&Src, v112, v113, v114);
                LODWORD(Size) = 4;
                LOWORD(v214) = 4;
                v111 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, (unsigned __int16)v13, v214, 1, Size, &Src);
                goto LABEL_356;
              }
              ++v220;
              break;
            case 0x28u:
              TIFFGetField(a1, *v106, &v235);
              if ( v14 )
              {
                LODWORD(Size) = v235;
                LOWORD(v214) = 7;
                v111 = TIFFWriteDirectoryTagData(
                         a1,
                         (int)&v220,
                         (int)v14,
                         *(unsigned __int16 *)v106,
                         v214,
                         v235,
                         Size,
                         v238);
                goto LABEL_356;
              }
              v109 = 4;
              if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                v109 = 8;
              if ( v235 > v109 )
              {
                v110 = v235 + 1LL;
                if ( (v235 & 1) == 0 )
                  v110 = v235;
                *(_QWORD *)(a1 + 416) += v110;
              }
              ++v220;
              break;
            default:
              v185 = "unknown";
              if ( *((_QWORD *)v106 + 4) )
                v185 = (const char *)*((_QWORD *)v106 + 4);
              v186 = TIFFFieldTag(v106);
              TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Cannot write tag %u (%s)", v186, v185);
              goto LABEL_522;
          }
        }
      }
    }
LABEL_358:
    v122 = 0;
    v226 = 0;
    if ( *(_DWORD *)(a1 + 396) )
    {
      while ( 1 )
      {
        v123 = *(_QWORD *)(a1 + 400);
        v124 = 3 * v122;
        v125 = *(unsigned __int16 **)(v123 + 24 * v122);
        v126 = v13;
        v127 = v7;
        v7 = *v125;
        v13 = *(unsigned int *)(v123 + 24 * v122 + 8);
        v128 = *((_DWORD *)v125 + 2) - 1;
        LOWORD(Src) = *v125;
        switch ( v128 )
        {
          case 0:
            if ( !v14 )
              goto LABEL_361;
            LODWORD(Size) = v13;
            LOWORD(v214) = 1;
            v131 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v220,
                     (int)v14,
                     (unsigned __int16)v7,
                     v214,
                     v13,
                     Size,
                     *(void **)(v123 + 8 * v124 + 16));
            goto LABEL_369;
          case 1:
            if ( !v14 )
              goto LABEL_361;
            LODWORD(Size) = v13;
            LOWORD(v214) = 2;
            v131 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v220,
                     (int)v14,
                     (unsigned __int16)v7,
                     v214,
                     v13,
                     Size,
                     *(void **)(v123 + 8 * v124 + 16));
            goto LABEL_369;
          case 2:
            if ( !v14 )
            {
              v132 = 2 * v13;
              goto LABEL_379;
            }
            v134 = *(void **)(v123 + 8 * v124 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfShort(v134, v13);
            LODWORD(Size) = 2 * v13;
            LOWORD(v214) = 3;
            v131 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, (unsigned __int16)v7, v214, v13, Size, v134);
            goto LABEL_369;
          case 3:
            if ( !v14 )
            {
              v132 = 4 * v13;
              goto LABEL_379;
            }
            v138 = *(void **)(v123 + 8 * v124 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v138, v13);
            LODWORD(Size) = 4 * v13;
            LOWORD(v214) = 4;
            v131 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, (unsigned __int16)v7, v214, v13, Size, v138);
            goto LABEL_369;
          case 4:
            v225 = TIFFFieldSetGetSize(v125);
            v155 = v225;
            if ( v225 == 8 )
            {
              if ( !v14 )
                goto LABEL_440;
              v156 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v124 + 16);
              v157 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v13));
              v7 = v157;
              if ( !v157 )
              {
                TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRationalDoubleArray", "Out of memory");
                TIFFfreeExt(a1, *(_QWORD *)v221);
                return 0;
              }
              v159 = 0;
              for ( ii = v157; v159 < (unsigned int)v13; ++v159 )
              {
                DoubleToRational(v158, ii, ii + 4);
                ii += 8;
                v156 += 8;
              }
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v13));
              v218 = (void *)v7;
              LODWORD(Size) = 8 * v13;
              v215 = v13;
              LOWORD(v214) = 5;
              goto LABEL_447;
            }
            if ( !v14 )
              goto LABEL_450;
            v163 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v124 + 16);
            v164 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v13));
            v7 = v164;
            if ( !v164 )
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRationalArray", "Out of memory");
              TIFFfreeExt(a1, *(_QWORD *)v221);
              return 0;
            }
            v166 = 0;
            for ( jj = v164; v166 < (unsigned int)v13; ++v166 )
            {
              DoubleToRational(v165, jj, jj + 4);
              jj += 8;
              v163 += 4;
            }
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v13));
            v219 = (void *)v7;
            LODWORD(Size) = 8 * v13;
            v216 = v13;
            LOWORD(v214) = 5;
            goto LABEL_461;
          case 5:
            if ( !v14 )
              goto LABEL_361;
            LODWORD(Size) = v13;
            LOWORD(v214) = 6;
            v131 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v220,
                     (int)v14,
                     (unsigned __int16)v7,
                     v214,
                     v13,
                     Size,
                     *(void **)(v123 + 8 * v124 + 16));
            goto LABEL_369;
          case 6:
            if ( v14 )
            {
              LODWORD(Size) = v13;
              LOWORD(v214) = 7;
              v131 = TIFFWriteDirectoryTagData(
                       a1,
                       (int)&v220,
                       (int)v14,
                       (unsigned __int16)v7,
                       v214,
                       v13,
                       Size,
                       *(void **)(v123 + 8 * v124 + 16));
              goto LABEL_369;
            }
LABEL_361:
            v129 = 4;
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
              v129 = 8;
            if ( v13 > v129 )
            {
              v130 = v13 + 1;
              if ( (v13 & 1) == 0 )
                v130 = v13;
              *(_QWORD *)(a1 + 416) += v130;
            }
            goto LABEL_367;
          case 7:
            if ( v14 )
            {
              v137 = *(void **)(v123 + 8 * v124 + 16);
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfShort(v137, v13);
              LODWORD(Size) = 2 * v13;
              LOWORD(v214) = 8;
              v131 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, (unsigned __int16)v7, v214, v13, Size, v137);
              goto LABEL_369;
            }
            v135 = 4;
            v136 = 2 * v13;
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
              v135 = 8;
            if ( v136 > v135 )
            {
              *(_QWORD *)(a1 + 416) += v136;
              ++v220;
              goto LABEL_497;
            }
            goto LABEL_367;
          case 8:
            if ( !v14 )
            {
              v132 = 4 * v13;
              goto LABEL_379;
            }
            v139 = *(void **)(v123 + 8 * v124 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v139, v13);
            LODWORD(Size) = 4 * v13;
            LOWORD(v214) = 9;
            v131 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, (unsigned __int16)v7, v214, v13, Size, v139);
            goto LABEL_369;
          case 9:
            v225 = TIFFFieldSetGetSize(v125);
            v155 = v225;
            if ( v225 == 8 )
            {
              if ( v14 )
              {
                v168 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v124 + 16);
                v169 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v13));
                v7 = v169;
                if ( !v169 )
                {
                  TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSrationalDoubleArray", "Out of memory");
                  TIFFfreeExt(a1, *(_QWORD *)v221);
                  return 0;
                }
                v171 = 0;
                for ( kk = v169; v171 < (unsigned int)v13; ++v171 )
                {
                  DoubleToSrational(v170, kk, kk + 4);
                  kk += 8;
                  v168 += 8;
                }
                if ( *(char *)(a1 + 16) < 0 )
                  TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v13));
                v218 = (void *)v7;
                LODWORD(Size) = 8 * v13;
                v215 = v13;
                LOWORD(v214) = 10;
LABEL_447:
                v14 = *(_WORD **)v221;
                v13 = (unsigned int)TIFFWriteDirectoryTagData(
                                      a1,
                                      (int)&v220,
                                      v221[0],
                                      (unsigned __int16)Src,
                                      v214,
                                      v215,
                                      Size,
                                      v218);
                TIFFfreeExt(a1, v7);
                if ( !(_DWORD)v13 )
                  goto LABEL_523;
              }
              else
              {
LABEL_440:
                v132 = 4LL * (unsigned int)(2 * v13);
LABEL_379:
                v133 = 4;
                if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                  v133 = 8;
                if ( v132 <= v133 )
                {
LABEL_367:
                  ++v220;
                }
                else
                {
                  *(_QWORD *)(a1 + 416) += v132;
                  ++v220;
                }
              }
            }
            else
            {
              if ( v14 )
              {
                v173 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v124 + 16);
                v174 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v13));
                v7 = v174;
                if ( !v174 )
                {
                  TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSrationalArray", "Out of memory");
                  TIFFfreeExt(a1, *(_QWORD *)v221);
                  return 0;
                }
                v176 = 0;
                for ( mm = v174; v176 < (unsigned int)v13; ++v176 )
                {
                  DoubleToSrational(v175, mm, mm + 4);
                  mm += 8;
                  v173 += 4;
                }
                if ( *(char *)(a1 + 16) < 0 )
                  TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v13));
                v219 = (void *)v7;
                LODWORD(Size) = 8 * v13;
                v216 = v13;
                LOWORD(v214) = 10;
LABEL_461:
                v14 = *(_WORD **)v221;
                v13 = (unsigned int)TIFFWriteDirectoryTagData(
                                      a1,
                                      (int)&v220,
                                      v221[0],
                                      (unsigned __int16)Src,
                                      v214,
                                      v216,
                                      Size,
                                      v219);
                TIFFfreeExt(a1, v7);
                if ( !(_DWORD)v13 )
                  goto LABEL_523;
                v155 = v225;
              }
              else
              {
LABEL_450:
                v161 = 4;
                v162 = 4LL * (unsigned int)(2 * v13);
                if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                  v161 = 8;
                if ( v162 > v161 )
                  *(_QWORD *)(a1 + 416) += v162;
                ++v220;
              }
              if ( v155 != 4 )
                TIFFErrorExtR(
                  a1,
                  "TIFFLib: _TIFFWriteDirectorySec()",
                  "Rational2Double: .set_field_type is not 4 but %d",
                  v155);
            }
            goto LABEL_497;
          case 10:
            if ( !v14 )
            {
              v132 = 4 * v13;
              goto LABEL_379;
            }
            v178 = *(void **)(v123 + 8 * v124 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v178, v13);
            LODWORD(Size) = 4 * v13;
            LOWORD(v214) = 11;
            v131 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, (unsigned __int16)v7, v214, v13, Size, v178);
            goto LABEL_369;
          case 11:
            if ( !v14 )
            {
              v132 = 8 * v13;
              goto LABEL_379;
            }
            v179 = *(void **)(v123 + 8 * v124 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfDouble(v179, v13, v125, 8);
            LODWORD(Size) = 8 * v13;
            LOWORD(v214) = 12;
            v131 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, (unsigned __int16)v7, v214, v13, Size, v179);
            goto LABEL_369;
          case 12:
            if ( !v14 )
            {
              v132 = 4 * v13;
              goto LABEL_379;
            }
            v180 = *(void **)(v123 + 8 * v124 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v180, v13);
            LODWORD(Size) = 4 * v13;
            LOWORD(v214) = 13;
            v131 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, (unsigned __int16)v7, v214, v13, Size, v180);
LABEL_369:
            if ( !v131 )
              goto LABEL_523;
            goto LABEL_497;
          case 15:
            if ( v14 )
            {
              v141 = *(_DWORD *)(a1 + 16);
              v142 = *(_QWORD **)(v123 + 8 * v124 + 16);
              if ( (v141 & 0x80000) != 0 )
              {
                if ( (v141 & 0x80u) != 0 )
                  TIFFSwabArrayOfDouble(v142, v13, v125, 8);
                LODWORD(Size) = 8 * v13;
                LOWORD(v214) = 16;
                v143 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, (unsigned __int16)v7, v214, v13, Size, v142);
LABEL_414:
                v13 = v143;
                v140 = v143 == 0;
                goto LABEL_496;
              }
              v144 = TIFFmallocExt(a1, 4 * v13);
              v145 = (void *)v144;
              if ( !v144 )
              {
                v184 = "TIFFWriteDirectoryTagLong8Array";
                goto LABEL_556;
              }
              v146 = 0;
              v147 = (_DWORD *)v144;
              if ( (_DWORD)v13 )
              {
                while ( *v142 <= 0xFFFFFFFF )
                {
                  *v147++ = *v142++;
                  if ( ++v146 >= (unsigned int)v13 )
                    goto LABEL_419;
                }
                v187 = "Attempt to write unsigned long value %llu larger than 0xFFFFFFFF for tag %d in Classic TIFF file."
                       " TIFF file writing aborted";
                v188 = "TIFFWriteDirectoryTagLong8Array";
LABEL_535:
                TIFFErrorExtR(a1, v188, v187);
                TIFFfreeExt(a1, v145);
                TIFFfreeExt(a1, v14);
                return 0;
              }
LABEL_419:
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v144, v13);
              LODWORD(Size) = 4 * v13;
              LOWORD(v214) = 4;
              v148 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, (unsigned __int16)v7, v214, v13, Size, v145);
LABEL_422:
              v13 = v148;
              TIFFfreeExt(a1, v145);
              v140 = (_DWORD)v13 == 0;
              goto LABEL_496;
            }
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) == 0 )
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedLong8Array", "LONG8 not allowed for ClassicTIFF", 8);
              v13 = 0;
              v140 = 1;
              goto LABEL_496;
            }
            goto LABEL_407;
          case 16:
            if ( v14 )
            {
              v149 = *(_DWORD *)(a1 + 16);
              v150 = *(__int64 **)(v123 + 8 * v124 + 16);
              if ( (v149 & 0x80000) != 0 )
              {
                if ( (v149 & 0x80u) != 0 )
                  TIFFSwabArrayOfDouble(v150, v13, v125, 8);
                LODWORD(Size) = 8 * v13;
                LOWORD(v214) = 17;
                v143 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, (unsigned __int16)v7, v214, v13, Size, v150);
                goto LABEL_414;
              }
              v151 = TIFFmallocExt(a1, 4 * v13);
              v145 = (void *)v151;
              if ( !v151 )
              {
                v184 = "TIFFWriteDirectoryTagSlong8Array";
                goto LABEL_556;
              }
              v152 = 0;
              v153 = (_DWORD *)v151;
              if ( (_DWORD)v13 )
              {
                while ( 1 )
                {
                  v154 = *v150;
                  if ( *v150 > 0x7FFFFFFF )
                    break;
                  if ( v154 < (__int64)0xFFFFFFFF80000000uLL )
                  {
                    v187 = "Attempt to write signed long value %lli smaller than 0x80000000 (-2147483648) for tag %d in C"
                           "lassic TIFF file. TIFF writing to file aborted";
                    goto LABEL_534;
                  }
                  *v153 = v154;
                  ++v150;
                  ++v153;
                  if ( ++v152 >= (unsigned int)v13 )
                    goto LABEL_435;
                }
                v187 = "Attempt to write signed long value %lli larger than 0x7FFFFFFF (2147483647) for tag %d in Classic"
                       " TIFF file. TIFF writing to file aborted";
LABEL_534:
                v188 = "TIFFWriteDirectoryTagSlong8Array";
                goto LABEL_535;
              }
LABEL_435:
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v151, v13);
              LODWORD(Size) = 4 * v13;
              LOWORD(v214) = 9;
              v148 = TIFFWriteDirectoryTagData(a1, (int)&v220, (int)v14, (unsigned __int16)v7, v214, v13, Size, v145);
              goto LABEL_422;
            }
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
            {
LABEL_407:
              if ( 8 * v13 > 8 )
                *(_QWORD *)(a1 + 416) += 8 * v13;
              ++v220;
              v13 = 1;
              v140 = 0;
            }
            else
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSlong8Array", "SLONG8 not allowed for ClassicTIFF", 8);
              v13 = 0;
              v140 = 1;
            }
LABEL_496:
            if ( v140 )
              goto LABEL_522;
LABEL_497:
            v122 = (unsigned int)(v226 + 1);
            v226 = v122;
            if ( (unsigned int)v122 >= *(_DWORD *)(a1 + 396) )
              goto LABEL_498;
            break;
          case 17:
            v140 = (unsigned int)TIFFWriteDirectoryTagIfdIfd8Array(
                                   a1,
                                   (int)&v220,
                                   (int)v14,
                                   v13,
                                   *(void **)(v123 + 8 * v124 + 16)) == 0;
            goto LABEL_496;
          default:
            v7 = v127;
            v13 = v126;
            goto LABEL_497;
        }
      }
    }
LABEL_498:
    if ( v14 )
      break;
    v13 = a1 + 416;
    if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
      v181 = (unsigned int)(20 * v220 + 16);
    else
      v181 = (unsigned int)(12 * v220 + 6);
    *(_QWORD *)v13 = *(_QWORD *)(a1 + 416) + v181;
    *(_QWORD *)v221 = TIFFmallocExt(a1, 32LL * (unsigned int)v220);
    v14 = *(_WORD **)v221;
    if ( !*(_QWORD *)v221 )
    {
      TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Out of memory");
      return 0;
    }
    v5 = v241;
    if ( v241 )
    {
      if ( *(_QWORD *)(a1 + 24) )
      {
        if ( *(_QWORD *)v13 > *(_QWORD *)(a1 + 424) )
        {
          TIFFfreeExt(a1, *(_QWORD *)v221);
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
      v182 = *(_QWORD *)(a1 + 424);
      if ( !v182 || *(_QWORD *)v13 > v182 )
        *(_QWORD *)(a1 + 24) = ((*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 1200))(
                                  *(_QWORD *)(a1 + 1176),
                                  0,
                                  2)
                              + 1)
                             & 0xFFFFFFFFFFFFFFFEuLL;
    }
    if ( v243 )
      *v243 = *(_QWORD *)(a1 + 24);
    v8 = *(_QWORD *)(a1 + 24);
    if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
    {
      v10 = (unsigned int)(20 * v220 + 16);
      v183 = v10 + v8;
    }
    else
    {
      v10 = (unsigned int)(12 * v220 + 6);
      v183 = (unsigned int)(v8 + v10);
    }
    *(_QWORD *)(a1 + 880) = v183;
    v9 = (unsigned int)v10;
    v222 = v10;
    if ( v183 < v8 || v183 < (unsigned int)v10 )
    {
      TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Maximum TIFF file size exceeded");
      TIFFfreeExt(a1, v14);
      return 0;
    }
    if ( (v183 & 1) != 0 )
      *(_QWORD *)(a1 + 880) = v183 + 1;
    v7 = 1;
  }
  if ( !v241 || (*(_DWORD *)(a1 + 76) & 0x20000) == 0 || *(_QWORD *)(a1 + 896) )
    goto LABEL_554;
  v189 = 0;
  v190 = v14;
  if ( !v220 )
  {
LABEL_550:
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Cannot find SubIFD tag", 8);
    TIFFfreeExt(a1, v14);
    return 0;
  }
  while ( *v190 != 330 )
  {
    ++v189;
    v190 += 16;
    if ( v189 == v220 )
      goto LABEL_550;
  }
  v191 = *(_QWORD *)(a1 + 24);
  if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
  {
    v192 = (unsigned int)(20 * v189);
    v193 = v191 + 20;
  }
  else
  {
    v192 = (unsigned int)(12 * v189);
    v193 = v191 + 10;
  }
  *(_QWORD *)(a1 + 896) = v192 + v193;
LABEL_554:
  v197 = (_QWORD *)TIFFmallocExt(a1, v222);
  if ( !v197 )
  {
    v184 = "TIFFWriteDirectorySec";
LABEL_556:
    TIFFErrorExtR(a1, v184, "Out of memory");
    goto LABEL_523;
  }
  v198 = (char *)(a1 + 16);
  if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
  {
    *v197 = (unsigned int)v220;
    if ( *v198 < 0 )
      TIFFSwabLong8(v197);
    v205 = 0;
    v206 = v197 + 1;
    v207 = v14;
    if ( v220 )
    {
      do
      {
        *v206 = *v207;
        if ( *v198 < 0 )
          TIFFSwabShort(v206, v194, v195, v196);
        v206[1] = v207[1];
        if ( *v198 < 0 )
          TIFFSwabShort(v206 + 1, v194, v195, v196);
        TIFFmemcpy(v206 + 2, v207 + 4, 8u);
        if ( *v198 < 0 )
          TIFFSwabLong8(v206 + 2);
        TIFFmemcpy(v206 + 6, v207 + 8, 8u);
        v206 += 10;
        v207 += 16;
        ++v205;
      }
      while ( v205 < v220 );
      v14 = *(_WORD **)v221;
      v198 = (char *)(a1 + 16);
    }
    TIFFmemcpy(v206, (const void *)(a1 + 32), 8u);
    if ( *v198 < 0 )
      TIFFSwabLong8(v206);
  }
  else
  {
    *(_WORD *)v197 = v220;
    if ( *v198 < 0 )
      TIFFSwabShort(v197, v194, v195, v196);
    v199 = 0;
    v200 = (_WORD *)v197 + 1;
    v201 = v14;
    if ( v220 )
    {
      do
      {
        *v200 = *v201;
        if ( *v198 < 0 )
          TIFFSwabShort(v200, v194, v195, v196);
        v200[1] = v201[1];
        if ( *v198 < 0 )
          TIFFSwabShort(v200 + 1, v194, v195, v196);
        Src = *((_DWORD *)v201 + 2);
        TIFFmemcpy(v200 + 2, &Src, 4u);
        if ( *v198 < 0 )
          TIFFSwabLong(v200 + 2, v202, v203, v204);
        TIFFmemcpy(v200 + 4, v201 + 8, 4u);
        v200 += 6;
        v201 += 16;
        ++v199;
      }
      while ( v199 < v220 );
      v14 = *(_WORD **)v221;
      v198 = (char *)(a1 + 16);
    }
    v140 = *v198 >= 0;
    Src = *(_DWORD *)(a1 + 32);
    if ( !v140 )
      TIFFSwabLong(&Src, v194, v195, v196);
    TIFFmemcpy(v200, &Src, 4u);
    v198 = (char *)(a1 + 16);
  }
  TIFFfreeExt(a1, v14);
  if ( !(unsigned int)TIFFSeekOK(a1, *(_QWORD *)(a1 + 24)) )
  {
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "IO error writing directory at seek to offset");
    TIFFfreeExt(a1, v197);
    return 0;
  }
  v208 = v222;
  if ( (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD))(a1 + 1192))(*(_QWORD *)(a1 + 1176), v197, v222) != v208 )
  {
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "IO error writing directory");
    TIFFfreeExt(a1, v197);
    return 0;
  }
  TIFFfreeExt(a1, v197);
  if ( !v241 || *(_BYTE *)(a1 + 409) )
  {
LABEL_600:
    v210 = v242;
    *(_BYTE *)(a1 + 409) = 1;
    if ( v210 )
    {
      v211 = *(_DWORD *)(a1 + 16);
      if ( (v211 & 0x2000) != 0 && !*(_WORD *)(a1 + 888) )
        *(_DWORD *)(a1 + 16) = v211 & 0xFFFFDFFF;
    }
    if ( !(unsigned int)TIFFCheckDirNumberAndOffset(a1, *(unsigned int *)(a1 + 848), *(_QWORD *)(a1 + 24)) )
      TIFFErrorExtR(
        a1,
        "TIFFWriteDirectorySec",
        "Starting directory %u at offset 0x%llx (%llu) might cause an IFD loop",
        *(_DWORD *)(a1 + 848),
        *(_QWORD *)(a1 + 24),
        *(_QWORD *)(a1 + 24));
    if ( v210 )
    {
      TIFFFreeDirectory(a1);
      v212 = *(void (__fastcall **)(__int64))(a1 + 1048);
      *(_DWORD *)(a1 + 16) &= 0xFFDFFFF7;
      v212(a1);
      TIFFCreateDirectory(a1);
    }
    else
    {
      *(_QWORD *)(a1 + 424) = *(_QWORD *)(a1 + 416);
    }
    return 1;
  }
  if ( (*(_DWORD *)v198 & 0x2000) != 0 && (*(_DWORD *)(a1 + 76) & 0x20000) == 0 )
  {
    v209 = 0;
    goto LABEL_597;
  }
  v209 = *(_DWORD *)(a1 + 852);
  if ( v209 != -1 )
  {
LABEL_597:
    *(_DWORD *)(a1 + 848) = v209;
    if ( (*(_DWORD *)(a1 + 16) & 0x2000) == 0 || (*(_DWORD *)(a1 + 76) & 0x20000) != 0 )
      ++*(_DWORD *)(a1 + 852);
    goto LABEL_600;
  }
  v213 = TIFFNumberOfDirectories(a1);
  *(_DWORD *)(a1 + 852) = v213;
  *(_DWORD *)(a1 + 848) = v213;
  TIFFErrorExtR(
    a1,
    "TIFFWriteDirectorySec",
    "tif_curdircount is TIFF_NON_EXISTENT_DIR_NUMBER, not expected !! Line %d",
    1330);
  TIFFfreeExt(a1, v197);
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
