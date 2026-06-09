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
  __int64 v8; // rcx
  int v9; // eax
  __int64 v11; // rdx
  unsigned __int64 v12; // rbx
  _WORD *v13; // r13
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int64 v18; // rax
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rax
  __int16 v21; // bx
  __int64 v22; // rax
  void *v23; // rsi
  unsigned __int16 v24; // r9
  unsigned __int16 v25; // r8
  _WORD *i; // rdx
  int v27; // ebx
  int v28; // ebx
  int v29; // eax
  unsigned __int64 v30; // rdx
  unsigned __int64 v31; // rax
  __int16 v32; // bx
  __int64 v33; // rax
  void *v34; // rsi
  unsigned __int16 v35; // r9
  unsigned __int16 v36; // r8
  _WORD *j; // rdx
  int v38; // ebx
  int v39; // ebx
  unsigned __int64 v40; // rdx
  unsigned __int64 v41; // rax
  __int16 v42; // bx
  __int64 v43; // rax
  void *v44; // rsi
  unsigned __int16 v45; // r9
  unsigned __int16 v46; // r8
  _WORD *k; // rdx
  int v48; // ebx
  int v49; // ebx
  __int64 v50; // r14
  unsigned __int64 v51; // rdx
  unsigned __int64 v52; // rax
  char *v53; // rax
  char *v54; // rsi
  int v55; // ebx
  int v56; // ebx
  int v57; // eax
  unsigned __int64 v58; // rcx
  bool v59; // cf
  unsigned __int64 v60; // rax
  void *v61; // rsi
  unsigned __int64 v62; // rdx
  unsigned __int64 v63; // rax
  __int16 v64; // bx
  __int64 v65; // rax
  void *v66; // rsi
  unsigned __int16 v67; // r9
  unsigned __int16 v68; // r8
  _WORD *m; // rdx
  int v70; // ebx
  int v71; // ebx
  __int64 v72; // rax
  __int64 v73; // rcx
  char *v74; // rsi
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  int v80; // ebx
  unsigned __int64 v81; // rcx
  unsigned __int64 v82; // rax
  unsigned __int64 v83; // rax
  __int64 n; // r14
  unsigned int *v85; // rsi
  unsigned __int16 v86; // dx
  int v87; // eax
  unsigned __int64 v88; // rax
  __int64 v89; // rax
  int v90; // eax
  unsigned int v91; // eax
  unsigned __int64 v92; // rcx
  __int64 v93; // rdx
  __int64 v94; // rax
  __int64 v95; // rax
  __int64 v96; // rdx
  __int64 v97; // rsi
  unsigned __int16 *v98; // r8
  unsigned __int64 v99; // kr08_8
  __int64 v100; // kr10_8
  int v101; // eax
  unsigned __int64 v102; // rax
  unsigned __int64 v103; // rax
  int v104; // eax
  unsigned __int64 v105; // rcx
  unsigned __int64 v106; // rax
  void *v107; // rsi
  unsigned __int64 v108; // rax
  unsigned __int64 v109; // rcx
  void *v110; // rsi
  void *v111; // rsi
  void *v112; // rsi
  bool v113; // zf
  int v114; // eax
  _QWORD *v115; // rsi
  unsigned int v116; // eax
  __int64 v117; // rax
  void *v118; // r14
  int v119; // r8d
  _DWORD *v120; // rcx
  unsigned int v121; // eax
  int v122; // eax
  __int64 *v123; // rsi
  __int64 v124; // rax
  int v125; // r8d
  _DWORD *v126; // rcx
  signed __int64 v127; // r9
  int v128; // edx
  __int64 v129; // r15
  __int64 v130; // rax
  __int64 v131; // rcx
  unsigned int v132; // r14d
  __int64 ii; // rsi
  unsigned __int64 v134; // rax
  unsigned __int64 v135; // rcx
  __int64 v136; // r15
  __int64 v137; // rax
  __int64 v138; // rcx
  unsigned int v139; // r14d
  __int64 jj; // rsi
  __int64 v141; // r15
  __int64 v142; // rax
  __int64 v143; // rcx
  unsigned int v144; // r14d
  __int64 kk; // rsi
  __int64 v146; // r15
  __int64 v147; // rax
  __int64 v148; // rcx
  unsigned int v149; // r14d
  __int64 mm; // rsi
  void *v151; // rsi
  void *v152; // rsi
  void *v153; // rsi
  __int64 v154; // rax
  unsigned __int64 v155; // rax
  unsigned __int64 v156; // rdx
  __int64 v157; // r8
  unsigned __int64 v158; // rax
  const char *v159; // rdx
  const char *v160; // rbx
  int v161; // eax
  const char *v162; // r8
  const char *v163; // rdx
  int v164; // eax
  _WORD *v165; // rcx
  __int64 v166; // rcx
  __int64 v167; // rax
  __int64 v168; // rcx
  _QWORD *v169; // r12
  char *v170; // rbx
  unsigned int v171; // r15d
  _WORD *v172; // rsi
  _WORD *v173; // r14
  unsigned int v174; // r15d
  _WORD *v175; // rsi
  _WORD *v176; // r14
  __int64 v177; // rsi
  int v178; // eax
  int v179; // ebx
  int v180; // eax
  void (__fastcall *v181)(__int64); // rax
  int v182; // eax
  int v183; // [rsp+28h] [rbp-89h]
  int v184; // [rsp+30h] [rbp-81h]
  int v185; // [rsp+30h] [rbp-81h]
  size_t Size; // [rsp+38h] [rbp-79h]
  void *v187; // [rsp+40h] [rbp-71h]
  void *v188; // [rsp+40h] [rbp-71h]
  int v189; // [rsp+48h] [rbp-69h] BYREF
  int v190[2]; // [rsp+50h] [rbp-61h]
  unsigned int v191; // [rsp+58h] [rbp-59h]
  unsigned __int16 v192; // [rsp+5Ch] [rbp-55h] BYREF
  __int16 v193[2]; // [rsp+60h] [rbp-51h] BYREF
  int v194; // [rsp+64h] [rbp-4Dh]
  int v195; // [rsp+68h] [rbp-49h]
  _BYTE v196[4]; // [rsp+70h] [rbp-41h] BYREF
  _BYTE v197[4]; // [rsp+74h] [rbp-3Dh] BYREF
  _BYTE v198[4]; // [rsp+78h] [rbp-39h] BYREF
  _BYTE v199[4]; // [rsp+7Ch] [rbp-35h] BYREF
  _BYTE v200[4]; // [rsp+80h] [rbp-31h] BYREF
  _BYTE v201[4]; // [rsp+84h] [rbp-2Dh] BYREF
  _BYTE v202[4]; // [rsp+88h] [rbp-29h] BYREF
  _BYTE v203[4]; // [rsp+8Ch] [rbp-25h] BYREF
  unsigned int v204; // [rsp+90h] [rbp-21h] BYREF
  int v205; // [rsp+94h] [rbp-1Dh] BYREF
  void *v206; // [rsp+98h] [rbp-19h]
  void *v207; // [rsp+A0h] [rbp-11h]
  char *Str; // [rsp+A8h] [rbp-9h] BYREF
  int Src; // [rsp+118h] [rbp+67h] BYREF
  int v210; // [rsp+120h] [rbp+6Fh]
  int v211; // [rsp+128h] [rbp+77h]
  _QWORD *v212; // [rsp+130h] [rbp+7Fh]

  v212 = a4;
  v211 = a3;
  v210 = a2;
  v5 = a2;
  v7 = 1;
  if ( !*(_DWORD *)(a1 + 12) )
    return 1;
  TIFFFillStriles();
  if ( a3 )
  {
    v9 = *(_DWORD *)(a1 + 16);
    if ( (v9 & 0x1000) != 0 )
    {
      *(_DWORD *)(a1 + 16) = v9 & 0xFFFFEFFF;
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
      v11 = *(_QWORD *)(a1 + 1096);
      if ( v11 )
      {
        TIFFfreeExt(a1, v11);
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
  v12 = a1 + 416;
  v13 = 0;
  *(_QWORD *)v190 = 0;
  v191 = 0;
  while ( 1 )
  {
    v189 = 0;
    if ( !v13 )
      *(_QWORD *)v12 = 0;
    if ( !v5 )
      goto LABEL_358;
    if ( (*(_BYTE *)(a1 + 72) & 2) != 0 )
    {
      if ( *(_DWORD *)(a1 + 88) > 0xFFFFu )
      {
        if ( v13 )
        {
          v113 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 88);
          if ( !v113 )
            TIFFSwabLong(&Src);
          LODWORD(Size) = 4;
          LOWORD(v183) = 4;
          v14 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 256, v183, 1, Size, &Src);
        }
        else
        {
          v189 = 1;
          v14 = 1;
        }
      }
      else if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 88);
        if ( !v113 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v183) = 3;
        v14 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 256, v183, 1, Size, &Src);
      }
      else
      {
        v189 = 1;
        v14 = 1;
      }
      if ( !v14 )
        goto LABEL_522;
      if ( *(_DWORD *)(a1 + 92) > 0xFFFFu )
      {
        if ( v13 )
        {
          v113 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 92);
          if ( !v113 )
            TIFFSwabLong(&Src);
          LODWORD(Size) = 4;
          LOWORD(v183) = 4;
          v15 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 257, v183, 1, Size, &Src);
        }
        else
        {
          ++v189;
          v15 = 1;
        }
      }
      else if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 92);
        if ( !v113 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v183) = 3;
        v15 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 257, v183, 1, Size, &Src);
      }
      else
      {
        ++v189;
        v15 = 1;
      }
      if ( !v15 )
        goto LABEL_522;
    }
    if ( (*(_BYTE *)(a1 + 72) & 4) != 0 )
    {
      if ( *(_DWORD *)(a1 + 100) > 0xFFFFu )
      {
        if ( v13 )
        {
          v113 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 100);
          if ( !v113 )
            TIFFSwabLong(&Src);
          LODWORD(Size) = 4;
          LOWORD(v183) = 4;
          v16 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 322, v183, 1, Size, &Src);
        }
        else
        {
          ++v189;
          v16 = 1;
        }
      }
      else if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 100);
        if ( !v113 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v183) = 3;
        v16 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 322, v183, 1, Size, &Src);
      }
      else
      {
        ++v189;
        v16 = 1;
      }
      if ( !v16 )
        goto LABEL_522;
      if ( *(_DWORD *)(a1 + 104) > 0xFFFFu )
      {
        if ( v13 )
        {
          v113 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 104);
          if ( !v113 )
            TIFFSwabLong(&Src);
          LODWORD(Size) = 4;
          LOWORD(v183) = 4;
          v17 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 323, v183, 1, Size, &Src);
        }
        else
        {
          ++v189;
          v17 = 1;
        }
      }
      else if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 104);
        if ( !v113 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v183) = 3;
        v17 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 323, v183, 1, Size, &Src);
      }
      else
      {
        ++v189;
        v17 = 1;
      }
      if ( !v17 )
      {
LABEL_522:
        if ( !v13 )
          return 0;
LABEL_523:
        TIFFfreeExt(a1, v13);
        return 0;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 8) != 0 )
    {
      if ( *(float *)(a1 + 160) < 0.0 )
        goto LABEL_524;
      if ( v13 )
      {
        DoubleToRational(v8, v196, v197);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v196);
          TIFFSwabLong(v197);
        }
        LODWORD(Size) = 8;
        LOWORD(v183) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 282, v183, 1, Size, v196) )
          goto LABEL_523;
      }
      else
      {
        v18 = *(_QWORD *)v12 + (((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8);
        ++v189;
        *(_QWORD *)(a1 + 416) = v18;
      }
      if ( *(float *)(a1 + 164) < 0.0 )
        goto LABEL_524;
      if ( v13 )
      {
        DoubleToRational(v8, v198, v199);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v198);
          TIFFSwabLong(v199);
        }
        LODWORD(Size) = 8;
        LOWORD(v183) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 283, v183, 1, Size, v198) )
          goto LABEL_523;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v189;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x10) != 0 )
    {
      if ( *(float *)(a1 + 172) < 0.0 )
        goto LABEL_524;
      if ( v13 )
      {
        DoubleToRational(v8, v200, v201);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v200);
          TIFFSwabLong(v201);
        }
        LODWORD(Size) = 8;
        LOWORD(v183) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 286, v183, 1, Size, v200) )
          goto LABEL_523;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v189;
      }
      if ( *(float *)(a1 + 176) < 0.0 )
      {
LABEL_524:
        TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRational", "Negative value is illegal");
        goto LABEL_522;
      }
      if ( v13 )
      {
        DoubleToRational(v8, v202, v203);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v202);
          TIFFSwabLong(v203);
        }
        LODWORD(Size) = 8;
        LOWORD(v183) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 287, v183, 1, Size, v202) )
          goto LABEL_523;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v189;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x20) != 0 )
    {
      if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 112);
        if ( !v113 )
          TIFFSwabLong(&Src);
        LODWORD(Size) = 4;
        LOWORD(v183) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 254, v183, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v189;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x40) != 0 )
    {
      v19 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v13 )
      {
        v21 = *(_WORD *)(a1 + 116);
        v22 = TIFFmallocExt(a1, v19);
        v23 = (void *)v22;
        if ( !v22 )
          goto LABEL_525;
        v24 = *(_WORD *)(a1 + 130);
        v25 = 0;
        for ( i = (_WORD *)v22; v25 < v24; ++v25 )
        {
          *i++ = v21;
          v24 = *(_WORD *)(a1 + 130);
        }
        v27 = v24;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v22, v24);
        LODWORD(Size) = 2 * v27;
        LOWORD(v183) = 3;
        v28 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 258, v183, v27, Size, v23);
        TIFFfreeExt(a1, v23);
        if ( !v28 )
          goto LABEL_523;
      }
      else
      {
        v20 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v20 = 8;
        if ( v19 > v20 )
          *(_QWORD *)(a1 + 416) += v19;
        ++v189;
      }
    }
    if ( *(char *)(a1 + 72) < 0 )
    {
      if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 120);
        if ( !v113 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v183) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 259, v183, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v189;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x100) != 0 )
    {
      if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 122);
        if ( !v113 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v183) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 262, v183, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v189;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x200) != 0 )
    {
      if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 124);
        if ( !v113 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v183) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 263, v183, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v189;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x400) != 0 )
    {
      if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 126);
        if ( !v113 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v183) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 266, v183, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v189;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x8000) != 0 )
    {
      if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 128);
        if ( !v113 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v183) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 274, v183, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v189;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x10000) != 0 )
    {
      if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 130);
        if ( !v113 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v183) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 277, v183, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v189;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x20000) != 0 )
    {
      if ( *(_DWORD *)(a1 + 132) > 0xFFFFu )
      {
        if ( v13 )
        {
          v113 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 132);
          if ( !v113 )
            TIFFSwabLong(&Src);
          LODWORD(Size) = 4;
          LOWORD(v183) = 4;
          v29 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 278, v183, 1, Size, &Src);
        }
        else
        {
          ++v189;
          v29 = 1;
        }
      }
      else if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 132);
        if ( !v113 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v183) = 3;
        v29 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 278, v183, 1, Size, &Src);
      }
      else
      {
        ++v189;
        v29 = 1;
      }
      if ( !v29 )
        goto LABEL_522;
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x40000) != 0 )
    {
      v30 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v13 )
      {
        v32 = *(_WORD *)(a1 + 136);
        v33 = TIFFmallocExt(a1, v30);
        v34 = (void *)v33;
        if ( !v33 )
          goto LABEL_525;
        v35 = *(_WORD *)(a1 + 130);
        v36 = 0;
        for ( j = (_WORD *)v33; v36 < v35; ++v36 )
        {
          *j++ = v32;
          v35 = *(_WORD *)(a1 + 130);
        }
        v38 = v35;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v33, v35);
        LODWORD(Size) = 2 * v38;
        LOWORD(v183) = 3;
        v39 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 280, v183, v38, Size, v34);
        TIFFfreeExt(a1, v34);
        if ( !v39 )
          goto LABEL_523;
      }
      else
      {
        v31 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v31 = 8;
        if ( v30 > v31 )
          *(_QWORD *)(a1 + 416) += v30;
        ++v189;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x80000) != 0 )
    {
      v40 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v13 )
      {
        v42 = *(_WORD *)(a1 + 138);
        v43 = TIFFmallocExt(a1, v40);
        v44 = (void *)v43;
        if ( !v43 )
          goto LABEL_525;
        v45 = *(_WORD *)(a1 + 130);
        v46 = 0;
        for ( k = (_WORD *)v43; v46 < v45; ++v46 )
        {
          *k++ = v42;
          v45 = *(_WORD *)(a1 + 130);
        }
        v48 = v45;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v43, v45);
        LODWORD(Size) = 2 * v48;
        LOWORD(v183) = 3;
        v49 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 281, v183, v48, Size, v44);
        TIFFfreeExt(a1, v44);
        if ( !v49 )
          goto LABEL_523;
      }
      else
      {
        v41 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v41 = 8;
        if ( v40 > v41 )
          *(_QWORD *)(a1 + 416) += v40;
        ++v189;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x100000) != 0 )
    {
      if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 170);
        if ( !v113 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v183) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 284, v183, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v189;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x400000) != 0 )
    {
      if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 168);
        if ( !v113 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v183) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 296, v183, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v189;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x800000) != 0 )
    {
      if ( v13 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 180, 2);
        LODWORD(Size) = 4;
        LOWORD(v183) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 297, v183, 2, Size, (void *)(a1 + 180)) )
          goto LABEL_523;
      }
      else
      {
        ++v189;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x1000000) != 0
      && !(unsigned int)TIFFWriteDirectoryTagLongLong8Array(
                          a1,
                          (int)&v189,
                          (int)v13,
                          *(_DWORD *)(a1 + 228),
                          *(void **)(a1 + 240))
      || (*(_DWORD *)(a1 + 72) & 0x2000000) != 0
      && ((*(_DWORD *)(a1 + 16) & 0x400) != 0 || *(_QWORD *)(a1 + 232))
      && !(unsigned int)TIFFWriteDirectoryTagLongLong8Array(
                          a1,
                          (int)&v189,
                          (int)v13,
                          *(_DWORD *)(a1 + 228),
                          *(void **)(a1 + 232)) )
    {
      goto LABEL_522;
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x4000000) != 0 )
    {
      v50 = (unsigned int)(1 << *(_BYTE *)(a1 + 116));
      v51 = 2LL * (unsigned int)(3 * v50);
      if ( v13 )
      {
        v53 = (char *)TIFFmallocExt(a1, v51);
        v54 = v53;
        if ( !v53 )
        {
          v159 = "TIFFWriteDirectoryTagColormap";
          goto LABEL_556;
        }
        TIFFmemcpy(v53, *(const void **)(a1 + 184), 2 * v50);
        TIFFmemcpy(&v54[2 * v50], *(const void **)(a1 + 192), 2 * v50);
        TIFFmemcpy(&v54[2 * (unsigned int)(2 * v50)], *(const void **)(a1 + 200), 2 * v50);
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v54, (unsigned int)(3 * v50));
        LODWORD(Size) = 6 * v50;
        LOWORD(v183) = 3;
        v55 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 320, v183, 3 * (int)v50, Size, v54);
        TIFFfreeExt(a1, v54);
        if ( !v55 )
          goto LABEL_523;
        v7 = 1;
      }
      else
      {
        v52 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v52 = 8;
        if ( v51 > v52 )
          *(_QWORD *)(a1 + 416) += v51;
        ++v189;
        v7 = 1;
      }
    }
    if ( *(int *)(a1 + 72) < 0 && *(_WORD *)(a1 + 212) )
    {
      TIFFGetFieldDefaulted(a1, 338, &v192);
      v56 = v192;
      v57 = *(_DWORD *)(a1 + 16);
      if ( v13 )
      {
        v61 = v206;
        if ( (v57 & 0x80u) != 0 )
          TIFFSwabArrayOfShort(v206, v192);
        LODWORD(Size) = 2 * v56;
        LOWORD(v183) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 338, v183, v56, Size, v61) )
          goto LABEL_523;
      }
      else
      {
        v58 = 2LL * v192;
        v59 = (v57 & 0x80000) != 0;
        v60 = 4;
        if ( v59 )
          v60 = 8;
        if ( v58 > v60 )
          *(_QWORD *)(a1 + 416) += v58;
        ++v189;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 1) != 0 )
    {
      v62 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v13 )
      {
        v64 = *(_WORD *)(a1 + 118);
        v65 = TIFFmallocExt(a1, v62);
        v66 = (void *)v65;
        if ( !v65 )
        {
LABEL_525:
          v159 = "TIFFWriteDirectoryTagShortPerSample";
          goto LABEL_556;
        }
        v67 = *(_WORD *)(a1 + 130);
        v68 = 0;
        for ( m = (_WORD *)v65; v68 < v67; ++v68 )
        {
          *m++ = v64;
          v67 = *(_WORD *)(a1 + 130);
        }
        v70 = v67;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v65, v67);
        LODWORD(Size) = 2 * v70;
        LOWORD(v183) = 3;
        v71 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 339, v183, v70, Size, v66);
        TIFFfreeExt(a1, v66);
        if ( !v71 )
          goto LABEL_523;
      }
      else
      {
        v63 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v63 = 8;
        if ( v62 > v63 )
          *(_QWORD *)(a1 + 416) += v62;
        ++v189;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 2) != 0
      && !(unsigned int)TIFFWriteDirectoryTagSampleformatArray(
                          a1,
                          (int)&v189,
                          (int)v13,
                          *(unsigned __int16 *)(a1 + 130),
                          *(void **)(a1 + 144))
      || (*(_BYTE *)(a1 + 76) & 4) != 0
      && !(unsigned int)TIFFWriteDirectoryTagSampleformatArray(
                          a1,
                          (int)&v189,
                          (int)v13,
                          *(unsigned __int16 *)(a1 + 130),
                          *(void **)(a1 + 152)) )
    {
      goto LABEL_522;
    }
    if ( (*(_BYTE *)(a1 + 76) & 8) != 0 )
    {
      if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 96);
        if ( !v113 )
          TIFFSwabLong(&Src);
        LODWORD(Size) = 4;
        LOWORD(v183) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 32997, v183, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v189;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 0x10) != 0 )
    {
      if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 108);
        if ( !v113 )
          TIFFSwabLong(&Src);
        LODWORD(Size) = 4;
        LOWORD(v183) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 32998, v183, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v189;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 0x20) != 0 )
    {
      if ( v13 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 208, 2);
        LODWORD(Size) = 4;
        v12 = 3;
        LOWORD(v183) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 321, v183, 2, Size, (void *)(a1 + 208)) )
          goto LABEL_523;
        goto LABEL_275;
      }
      ++v189;
    }
    v12 = 3;
LABEL_275:
    if ( *(char *)(a1 + 76) < 0 )
    {
      if ( v13 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 336, 2);
        LODWORD(Size) = 4;
        v12 = 3;
        LOWORD(v183) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 530, v183, 2, Size, (void *)(a1 + 336)) )
          goto LABEL_523;
      }
      else
      {
        ++v189;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x100) != 0 )
    {
      if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 340);
        if ( !v113 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v183) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 531, v183, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v189;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x200) != 0 )
    {
      if ( v13 )
      {
        v72 = TIFFmallocExt(a1, 48);
        v74 = (char *)v72;
        if ( !v72 )
        {
          v159 = "TIFFWriteDirectoryTagCheckedRationalArray";
          goto LABEL_556;
        }
        DoubleToRational(v73, v72, v72 + 4);
        DoubleToRational(v75, v74 + 8, v74 + 12);
        DoubleToRational(v76, v74 + 16, v74 + 20);
        DoubleToRational(v77, v74 + 24, v74 + 28);
        DoubleToRational(v78, v74 + 32, v74 + 36);
        DoubleToRational(v79, v74 + 40, v74 + 44);
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfFloat(v74, 12);
        LODWORD(Size) = 48;
        LOWORD(v183) = 5;
        v80 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 532, v183, 6, Size, v74);
        TIFFfreeExt(a1, v74);
        if ( !v80 )
          goto LABEL_523;
        v12 = 3;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += 48LL;
        ++v189;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x1000) != 0
      && !(unsigned int)TIFFWriteDirectoryTagTransferfunction(a1, (int)&v189, (int)v13) )
    {
      goto LABEL_522;
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x4000) != 0 )
    {
      v81 = *(unsigned int *)(a1 + 376);
      if ( v13 )
      {
        LODWORD(Size) = *(_DWORD *)(a1 + 376);
        LOWORD(v183) = 2;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(
                              a1,
                              (int)&v189,
                              (int)v13,
                              333,
                              v183,
                              v81,
                              Size,
                              *(void **)(a1 + 384)) )
          goto LABEL_523;
      }
      else
      {
        v82 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v82 = 8;
        if ( v81 > v82 )
        {
          v83 = v81 + 1;
          if ( (v81 & 1) == 0 )
            v83 = *(unsigned int *)(a1 + 376);
          *(_QWORD *)(a1 + 416) += v83;
        }
        ++v189;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x40000) != 0 )
    {
      if ( v13 )
      {
        v113 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 392);
        if ( !v113 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v183) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, 334, v183, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v189;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x20000) != 0 && !(unsigned int)TIFFWriteDirectoryTagSubifd(a1, (int)&v189, (int)v13) )
      goto LABEL_522;
    for ( n = 0; (unsigned __int64)(unsigned int)n < *(_QWORD *)(a1 + 1240); n = (unsigned int)(n + 1) )
    {
      v85 = *(unsigned int **)(*(_QWORD *)(a1 + 1232) + 8 * n);
      v86 = *((_WORD *)v85 + 12);
      if ( v86 >= 0x42u )
      {
        v87 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)v86 >> 5) + 72);
        if ( _bittest(&v87, v86 & 0x1F) )
        {
          switch ( v85[4] )
          {
            case 1u:
              TIFFGetField(a1, *v85, &Str);
              v12 = (unsigned __int64)Str;
              v91 = strlen_0(Str);
              if ( v13 )
              {
                LODWORD(Size) = v91;
                LOWORD(v183) = 2;
                v90 = TIFFWriteDirectoryTagData(
                        a1,
                        (int)&v189,
                        (int)v13,
                        *(unsigned __int16 *)v85,
                        v183,
                        v91,
                        Size,
                        (void *)v12);
                goto LABEL_356;
              }
              v92 = 4;
              v93 = v91;
              if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                v92 = 8;
              if ( v91 > v92 )
              {
                v113 = (v91 & 1) == 0;
                v94 = v91 + 1LL;
                if ( v113 )
                  v94 = v93;
                *(_QWORD *)(a1 + 416) += v94;
              }
              ++v189;
              break;
            case 4u:
              TIFFGetField(a1, *v85, v193);
              if ( v13 )
              {
                v113 = *(_BYTE *)(a1 + 16) >= 0;
                v12 = *(unsigned __int16 *)v85;
                LOWORD(Src) = v193[0];
                if ( !v113 )
                  TIFFSwabShort(&Src);
                LODWORD(Size) = 2;
                LOWORD(v183) = 3;
                v90 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, (unsigned __int16)v12, v183, 1, Size, &Src);
LABEL_356:
                if ( !v90 )
                  goto LABEL_523;
                continue;
              }
              ++v189;
              break;
            case 6u:
              TIFFGetField(a1, *v85, &v205);
              if ( v13 )
              {
                v113 = *(_BYTE *)(a1 + 16) >= 0;
                v12 = *(unsigned __int16 *)v85;
                Src = v205;
                if ( !v113 )
                  TIFFSwabLong(&Src);
                LODWORD(Size) = 4;
                LOWORD(v183) = 4;
                v90 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, (unsigned __int16)v12, v183, 1, Size, &Src);
                goto LABEL_356;
              }
              ++v189;
              break;
            case 0x28u:
              TIFFGetField(a1, *v85, &v204);
              if ( v13 )
              {
                LODWORD(Size) = v204;
                LOWORD(v183) = 7;
                v90 = TIFFWriteDirectoryTagData(
                        a1,
                        (int)&v189,
                        (int)v13,
                        *(unsigned __int16 *)v85,
                        v183,
                        v204,
                        Size,
                        v207);
                goto LABEL_356;
              }
              v88 = 4;
              if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                v88 = 8;
              if ( v204 > v88 )
              {
                v89 = v204 + 1LL;
                if ( (v204 & 1) == 0 )
                  v89 = v204;
                *(_QWORD *)(a1 + 416) += v89;
              }
              ++v189;
              break;
            default:
              v160 = "unknown";
              if ( *((_QWORD *)v85 + 4) )
                v160 = (const char *)*((_QWORD *)v85 + 4);
              v161 = TIFFFieldTag(v85);
              TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Cannot write tag %u (%s)", v161, v160);
              goto LABEL_522;
          }
        }
      }
    }
LABEL_358:
    v95 = 0;
    v195 = 0;
    if ( *(_DWORD *)(a1 + 396) )
    {
      while ( 1 )
      {
        v96 = *(_QWORD *)(a1 + 400);
        v97 = 3 * v95;
        v98 = *(unsigned __int16 **)(v96 + 24 * v95);
        v99 = v12;
        v100 = v7;
        v7 = *v98;
        v12 = *(unsigned int *)(v96 + 24 * v95 + 8);
        v101 = *((_DWORD *)v98 + 2) - 1;
        LOWORD(Src) = *v98;
        switch ( v101 )
        {
          case 0:
            if ( !v13 )
              goto LABEL_361;
            LODWORD(Size) = v12;
            LOWORD(v183) = 1;
            v104 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v189,
                     (int)v13,
                     (unsigned __int16)v7,
                     v183,
                     v12,
                     Size,
                     *(void **)(v96 + 8 * v97 + 16));
            goto LABEL_369;
          case 1:
            if ( !v13 )
              goto LABEL_361;
            LODWORD(Size) = v12;
            LOWORD(v183) = 2;
            v104 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v189,
                     (int)v13,
                     (unsigned __int16)v7,
                     v183,
                     v12,
                     Size,
                     *(void **)(v96 + 8 * v97 + 16));
            goto LABEL_369;
          case 2:
            if ( !v13 )
            {
              v105 = 2 * v12;
              goto LABEL_379;
            }
            v107 = *(void **)(v96 + 8 * v97 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfShort(v107, v12);
            LODWORD(Size) = 2 * v12;
            LOWORD(v183) = 3;
            v104 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, (unsigned __int16)v7, v183, v12, Size, v107);
            goto LABEL_369;
          case 3:
            if ( !v13 )
            {
              v105 = 4 * v12;
              goto LABEL_379;
            }
            v111 = *(void **)(v96 + 8 * v97 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v111, v12);
            LODWORD(Size) = 4 * v12;
            LOWORD(v183) = 4;
            v104 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, (unsigned __int16)v7, v183, v12, Size, v111);
            goto LABEL_369;
          case 4:
            v194 = TIFFFieldSetGetSize(v98);
            v128 = v194;
            if ( v194 == 8 )
            {
              if ( !v13 )
                goto LABEL_440;
              v129 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v97 + 16);
              v130 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v12));
              v7 = v130;
              if ( !v130 )
              {
                TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRationalDoubleArray", "Out of memory");
                TIFFfreeExt(a1, *(_QWORD *)v190);
                return 0;
              }
              v132 = 0;
              for ( ii = v130; v132 < (unsigned int)v12; ++v132 )
              {
                DoubleToRational(v131, ii, ii + 4);
                ii += 8;
                v129 += 8;
              }
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v12));
              v187 = (void *)v7;
              LODWORD(Size) = 8 * v12;
              v184 = v12;
              LOWORD(v183) = 5;
              goto LABEL_447;
            }
            if ( !v13 )
              goto LABEL_450;
            v136 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v97 + 16);
            v137 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v12));
            v7 = v137;
            if ( !v137 )
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRationalArray", "Out of memory");
              TIFFfreeExt(a1, *(_QWORD *)v190);
              return 0;
            }
            v139 = 0;
            for ( jj = v137; v139 < (unsigned int)v12; ++v139 )
            {
              DoubleToRational(v138, jj, jj + 4);
              jj += 8;
              v136 += 4;
            }
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v12));
            v188 = (void *)v7;
            LODWORD(Size) = 8 * v12;
            v185 = v12;
            LOWORD(v183) = 5;
            goto LABEL_461;
          case 5:
            if ( !v13 )
              goto LABEL_361;
            LODWORD(Size) = v12;
            LOWORD(v183) = 6;
            v104 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v189,
                     (int)v13,
                     (unsigned __int16)v7,
                     v183,
                     v12,
                     Size,
                     *(void **)(v96 + 8 * v97 + 16));
            goto LABEL_369;
          case 6:
            if ( v13 )
            {
              LODWORD(Size) = v12;
              LOWORD(v183) = 7;
              v104 = TIFFWriteDirectoryTagData(
                       a1,
                       (int)&v189,
                       (int)v13,
                       (unsigned __int16)v7,
                       v183,
                       v12,
                       Size,
                       *(void **)(v96 + 8 * v97 + 16));
              goto LABEL_369;
            }
LABEL_361:
            v102 = 4;
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
              v102 = 8;
            if ( v12 > v102 )
            {
              v103 = v12 + 1;
              if ( (v12 & 1) == 0 )
                v103 = v12;
              *(_QWORD *)(a1 + 416) += v103;
            }
            goto LABEL_367;
          case 7:
            if ( v13 )
            {
              v110 = *(void **)(v96 + 8 * v97 + 16);
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfShort(v110, v12);
              LODWORD(Size) = 2 * v12;
              LOWORD(v183) = 8;
              v104 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, (unsigned __int16)v7, v183, v12, Size, v110);
              goto LABEL_369;
            }
            v108 = 4;
            v109 = 2 * v12;
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
              v108 = 8;
            if ( v109 > v108 )
            {
              *(_QWORD *)(a1 + 416) += v109;
              ++v189;
              goto LABEL_497;
            }
            goto LABEL_367;
          case 8:
            if ( !v13 )
            {
              v105 = 4 * v12;
              goto LABEL_379;
            }
            v112 = *(void **)(v96 + 8 * v97 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v112, v12);
            LODWORD(Size) = 4 * v12;
            LOWORD(v183) = 9;
            v104 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, (unsigned __int16)v7, v183, v12, Size, v112);
            goto LABEL_369;
          case 9:
            v194 = TIFFFieldSetGetSize(v98);
            v128 = v194;
            if ( v194 == 8 )
            {
              if ( v13 )
              {
                v141 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v97 + 16);
                v142 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v12));
                v7 = v142;
                if ( !v142 )
                {
                  TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSrationalDoubleArray", "Out of memory");
                  TIFFfreeExt(a1, *(_QWORD *)v190);
                  return 0;
                }
                v144 = 0;
                for ( kk = v142; v144 < (unsigned int)v12; ++v144 )
                {
                  DoubleToSrational(v143, kk, kk + 4);
                  kk += 8;
                  v141 += 8;
                }
                if ( *(char *)(a1 + 16) < 0 )
                  TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v12));
                v187 = (void *)v7;
                LODWORD(Size) = 8 * v12;
                v184 = v12;
                LOWORD(v183) = 10;
LABEL_447:
                v13 = *(_WORD **)v190;
                v12 = (unsigned int)TIFFWriteDirectoryTagData(
                                      a1,
                                      (int)&v189,
                                      v190[0],
                                      (unsigned __int16)Src,
                                      v183,
                                      v184,
                                      Size,
                                      v187);
                TIFFfreeExt(a1, v7);
                if ( !(_DWORD)v12 )
                  goto LABEL_523;
              }
              else
              {
LABEL_440:
                v105 = 4LL * (unsigned int)(2 * v12);
LABEL_379:
                v106 = 4;
                if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                  v106 = 8;
                if ( v105 <= v106 )
                {
LABEL_367:
                  ++v189;
                }
                else
                {
                  *(_QWORD *)(a1 + 416) += v105;
                  ++v189;
                }
              }
            }
            else
            {
              if ( v13 )
              {
                v146 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v97 + 16);
                v147 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v12));
                v7 = v147;
                if ( !v147 )
                {
                  TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSrationalArray", "Out of memory");
                  TIFFfreeExt(a1, *(_QWORD *)v190);
                  return 0;
                }
                v149 = 0;
                for ( mm = v147; v149 < (unsigned int)v12; ++v149 )
                {
                  DoubleToSrational(v148, mm, mm + 4);
                  mm += 8;
                  v146 += 4;
                }
                if ( *(char *)(a1 + 16) < 0 )
                  TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v12));
                v188 = (void *)v7;
                LODWORD(Size) = 8 * v12;
                v185 = v12;
                LOWORD(v183) = 10;
LABEL_461:
                v13 = *(_WORD **)v190;
                v12 = (unsigned int)TIFFWriteDirectoryTagData(
                                      a1,
                                      (int)&v189,
                                      v190[0],
                                      (unsigned __int16)Src,
                                      v183,
                                      v185,
                                      Size,
                                      v188);
                TIFFfreeExt(a1, v7);
                if ( !(_DWORD)v12 )
                  goto LABEL_523;
                v128 = v194;
              }
              else
              {
LABEL_450:
                v134 = 4;
                v135 = 4LL * (unsigned int)(2 * v12);
                if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                  v134 = 8;
                if ( v135 > v134 )
                  *(_QWORD *)(a1 + 416) += v135;
                ++v189;
              }
              if ( v128 != 4 )
                TIFFErrorExtR(
                  a1,
                  "TIFFLib: _TIFFWriteDirectorySec()",
                  "Rational2Double: .set_field_type is not 4 but %d",
                  v128);
            }
            goto LABEL_497;
          case 10:
            if ( !v13 )
            {
              v105 = 4 * v12;
              goto LABEL_379;
            }
            v151 = *(void **)(v96 + 8 * v97 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v151, v12);
            LODWORD(Size) = 4 * v12;
            LOWORD(v183) = 11;
            v104 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, (unsigned __int16)v7, v183, v12, Size, v151);
            goto LABEL_369;
          case 11:
            if ( !v13 )
            {
              v105 = 8 * v12;
              goto LABEL_379;
            }
            v152 = *(void **)(v96 + 8 * v97 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfDouble(v152, v12);
            LODWORD(Size) = 8 * v12;
            LOWORD(v183) = 12;
            v104 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, (unsigned __int16)v7, v183, v12, Size, v152);
            goto LABEL_369;
          case 12:
            if ( !v13 )
            {
              v105 = 4 * v12;
              goto LABEL_379;
            }
            v153 = *(void **)(v96 + 8 * v97 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v153, v12);
            LODWORD(Size) = 4 * v12;
            LOWORD(v183) = 13;
            v104 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, (unsigned __int16)v7, v183, v12, Size, v153);
LABEL_369:
            if ( !v104 )
              goto LABEL_523;
            goto LABEL_497;
          case 15:
            if ( v13 )
            {
              v114 = *(_DWORD *)(a1 + 16);
              v115 = *(_QWORD **)(v96 + 8 * v97 + 16);
              if ( (v114 & 0x80000) != 0 )
              {
                if ( (v114 & 0x80u) != 0 )
                  TIFFSwabArrayOfDouble(v115, v12);
                LODWORD(Size) = 8 * v12;
                LOWORD(v183) = 16;
                v116 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, (unsigned __int16)v7, v183, v12, Size, v115);
LABEL_414:
                v12 = v116;
                v113 = v116 == 0;
                goto LABEL_496;
              }
              v117 = TIFFmallocExt(a1, 4 * v12);
              v118 = (void *)v117;
              if ( !v117 )
              {
                v159 = "TIFFWriteDirectoryTagLong8Array";
                goto LABEL_556;
              }
              v119 = 0;
              v120 = (_DWORD *)v117;
              if ( (_DWORD)v12 )
              {
                while ( *v115 <= 0xFFFFFFFF )
                {
                  *v120++ = *v115++;
                  if ( ++v119 >= (unsigned int)v12 )
                    goto LABEL_419;
                }
                v162 = "Attempt to write unsigned long value %llu larger than 0xFFFFFFFF for tag %d in Classic TIFF file."
                       " TIFF file writing aborted";
                v163 = "TIFFWriteDirectoryTagLong8Array";
LABEL_535:
                TIFFErrorExtR(a1, v163, v162);
                TIFFfreeExt(a1, v118);
                TIFFfreeExt(a1, v13);
                return 0;
              }
LABEL_419:
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v117, v12);
              LODWORD(Size) = 4 * v12;
              LOWORD(v183) = 4;
              v121 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, (unsigned __int16)v7, v183, v12, Size, v118);
LABEL_422:
              v12 = v121;
              TIFFfreeExt(a1, v118);
              v113 = (_DWORD)v12 == 0;
              goto LABEL_496;
            }
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) == 0 )
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedLong8Array", "LONG8 not allowed for ClassicTIFF", 8);
              v12 = 0;
              v113 = 1;
              goto LABEL_496;
            }
            goto LABEL_407;
          case 16:
            if ( v13 )
            {
              v122 = *(_DWORD *)(a1 + 16);
              v123 = *(__int64 **)(v96 + 8 * v97 + 16);
              if ( (v122 & 0x80000) != 0 )
              {
                if ( (v122 & 0x80u) != 0 )
                  TIFFSwabArrayOfDouble(v123, v12);
                LODWORD(Size) = 8 * v12;
                LOWORD(v183) = 17;
                v116 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, (unsigned __int16)v7, v183, v12, Size, v123);
                goto LABEL_414;
              }
              v124 = TIFFmallocExt(a1, 4 * v12);
              v118 = (void *)v124;
              if ( !v124 )
              {
                v159 = "TIFFWriteDirectoryTagSlong8Array";
                goto LABEL_556;
              }
              v125 = 0;
              v126 = (_DWORD *)v124;
              if ( (_DWORD)v12 )
              {
                while ( 1 )
                {
                  v127 = *v123;
                  if ( *v123 > 0x7FFFFFFF )
                    break;
                  if ( v127 < (__int64)0xFFFFFFFF80000000uLL )
                  {
                    v162 = "Attempt to write signed long value %lli smaller than 0x80000000 (-2147483648) for tag %d in C"
                           "lassic TIFF file. TIFF writing to file aborted";
                    goto LABEL_534;
                  }
                  *v126 = v127;
                  ++v123;
                  ++v126;
                  if ( ++v125 >= (unsigned int)v12 )
                    goto LABEL_435;
                }
                v162 = "Attempt to write signed long value %lli larger than 0x7FFFFFFF (2147483647) for tag %d in Classic"
                       " TIFF file. TIFF writing to file aborted";
LABEL_534:
                v163 = "TIFFWriteDirectoryTagSlong8Array";
                goto LABEL_535;
              }
LABEL_435:
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v124, v12);
              LODWORD(Size) = 4 * v12;
              LOWORD(v183) = 9;
              v121 = TIFFWriteDirectoryTagData(a1, (int)&v189, (int)v13, (unsigned __int16)v7, v183, v12, Size, v118);
              goto LABEL_422;
            }
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
            {
LABEL_407:
              if ( 8 * v12 > 8 )
                *(_QWORD *)(a1 + 416) += 8 * v12;
              ++v189;
              v12 = 1;
              v113 = 0;
            }
            else
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSlong8Array", "SLONG8 not allowed for ClassicTIFF", 8);
              v12 = 0;
              v113 = 1;
            }
LABEL_496:
            if ( v113 )
              goto LABEL_522;
LABEL_497:
            v95 = (unsigned int)(v195 + 1);
            v195 = v95;
            if ( (unsigned int)v95 >= *(_DWORD *)(a1 + 396) )
              goto LABEL_498;
            break;
          case 17:
            v113 = (unsigned int)TIFFWriteDirectoryTagIfdIfd8Array(
                                   a1,
                                   (int)&v189,
                                   (int)v13,
                                   v12,
                                   *(void **)(v96 + 8 * v97 + 16)) == 0;
            goto LABEL_496;
          default:
            v7 = v100;
            v12 = v99;
            goto LABEL_497;
        }
      }
    }
LABEL_498:
    if ( v13 )
      break;
    v12 = a1 + 416;
    if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
      v154 = (unsigned int)(20 * v189 + 16);
    else
      v154 = (unsigned int)(12 * v189 + 6);
    *(_QWORD *)v12 = *(_QWORD *)(a1 + 416) + v154;
    *(_QWORD *)v190 = TIFFmallocExt(a1, 32LL * (unsigned int)v189);
    v13 = *(_WORD **)v190;
    if ( !*(_QWORD *)v190 )
    {
      TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Out of memory");
      return 0;
    }
    v5 = v210;
    if ( v210 )
    {
      if ( *(_QWORD *)(a1 + 24) )
      {
        if ( *(_QWORD *)v12 > *(_QWORD *)(a1 + 424) )
        {
          TIFFfreeExt(a1, *(_QWORD *)v190);
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
      v155 = *(_QWORD *)(a1 + 424);
      if ( !v155 || *(_QWORD *)v12 > v155 )
        *(_QWORD *)(a1 + 24) = ((*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 1200))(
                                  *(_QWORD *)(a1 + 1176),
                                  0,
                                  2)
                              + 1)
                             & 0xFFFFFFFFFFFFFFFEuLL;
    }
    if ( v212 )
      *v212 = *(_QWORD *)(a1 + 24);
    v156 = *(_QWORD *)(a1 + 24);
    if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
    {
      v157 = (unsigned int)(20 * v189 + 16);
      v158 = v157 + v156;
    }
    else
    {
      LODWORD(v157) = 12 * v189 + 6;
      v158 = (unsigned int)(v156 + v157);
    }
    *(_QWORD *)(a1 + 880) = v158;
    v8 = (unsigned int)v157;
    v191 = v157;
    if ( v158 < v156 || v158 < (unsigned int)v157 )
    {
      TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Maximum TIFF file size exceeded");
      TIFFfreeExt(a1, v13);
      return 0;
    }
    if ( (v158 & 1) != 0 )
      *(_QWORD *)(a1 + 880) = v158 + 1;
    v7 = 1;
  }
  if ( !v210 || (*(_DWORD *)(a1 + 76) & 0x20000) == 0 || *(_QWORD *)(a1 + 896) )
    goto LABEL_554;
  v164 = 0;
  v165 = v13;
  if ( !v189 )
  {
LABEL_550:
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Cannot find SubIFD tag", 8);
    TIFFfreeExt(a1, v13);
    return 0;
  }
  while ( *v165 != 330 )
  {
    ++v164;
    v165 += 16;
    if ( v164 == v189 )
      goto LABEL_550;
  }
  v166 = *(_QWORD *)(a1 + 24);
  if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
  {
    v167 = (unsigned int)(20 * v164);
    v168 = v166 + 20;
  }
  else
  {
    v167 = (unsigned int)(12 * v164);
    v168 = v166 + 10;
  }
  *(_QWORD *)(a1 + 896) = v167 + v168;
LABEL_554:
  v169 = (_QWORD *)TIFFmallocExt(a1, v191);
  if ( !v169 )
  {
    v159 = "TIFFWriteDirectorySec";
LABEL_556:
    TIFFErrorExtR(a1, v159, "Out of memory");
    goto LABEL_523;
  }
  v170 = (char *)(a1 + 16);
  if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
  {
    *v169 = (unsigned int)v189;
    if ( *v170 < 0 )
      TIFFSwabLong8(v169);
    v174 = 0;
    v175 = v169 + 1;
    v176 = v13;
    if ( v189 )
    {
      do
      {
        *v175 = *v176;
        if ( *v170 < 0 )
          TIFFSwabShort(v175);
        v175[1] = v176[1];
        if ( *v170 < 0 )
          TIFFSwabShort(v175 + 1);
        TIFFmemcpy(v175 + 2, v176 + 4, 8u);
        if ( *v170 < 0 )
          TIFFSwabLong8(v175 + 2);
        TIFFmemcpy(v175 + 6, v176 + 8, 8u);
        v175 += 10;
        v176 += 16;
        ++v174;
      }
      while ( v174 < v189 );
      v13 = *(_WORD **)v190;
      v170 = (char *)(a1 + 16);
    }
    TIFFmemcpy(v175, (const void *)(a1 + 32), 8u);
    if ( *v170 < 0 )
      TIFFSwabLong8(v175);
  }
  else
  {
    *(_WORD *)v169 = v189;
    if ( *v170 < 0 )
      TIFFSwabShort(v169);
    v171 = 0;
    v172 = (_WORD *)v169 + 1;
    v173 = v13;
    if ( v189 )
    {
      do
      {
        *v172 = *v173;
        if ( *v170 < 0 )
          TIFFSwabShort(v172);
        v172[1] = v173[1];
        if ( *v170 < 0 )
          TIFFSwabShort(v172 + 1);
        Src = *((_DWORD *)v173 + 2);
        TIFFmemcpy(v172 + 2, &Src, 4u);
        if ( *v170 < 0 )
          TIFFSwabLong(v172 + 2);
        TIFFmemcpy(v172 + 4, v173 + 8, 4u);
        v172 += 6;
        v173 += 16;
        ++v171;
      }
      while ( v171 < v189 );
      v13 = *(_WORD **)v190;
      v170 = (char *)(a1 + 16);
    }
    v113 = *v170 >= 0;
    Src = *(_DWORD *)(a1 + 32);
    if ( !v113 )
      TIFFSwabLong(&Src);
    TIFFmemcpy(v172, &Src, 4u);
    v170 = (char *)(a1 + 16);
  }
  TIFFfreeExt(a1, v13);
  if ( !(unsigned int)TIFFSeekOK(a1) )
  {
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "IO error writing directory at seek to offset");
    TIFFfreeExt(a1, v169);
    return 0;
  }
  v177 = v191;
  if ( (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD))(a1 + 1192))(*(_QWORD *)(a1 + 1176), v169, v191) != v177 )
  {
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "IO error writing directory");
    TIFFfreeExt(a1, v169);
    return 0;
  }
  TIFFfreeExt(a1, v169);
  if ( !v210 || *(_BYTE *)(a1 + 409) )
  {
LABEL_600:
    v179 = v211;
    *(_BYTE *)(a1 + 409) = 1;
    if ( v179 )
    {
      v180 = *(_DWORD *)(a1 + 16);
      if ( (v180 & 0x2000) != 0 && !*(_WORD *)(a1 + 888) )
        *(_DWORD *)(a1 + 16) = v180 & 0xFFFFDFFF;
    }
    if ( !(unsigned int)TIFFCheckDirNumberAndOffset(a1, *(unsigned int *)(a1 + 848), *(_QWORD *)(a1 + 24)) )
      TIFFErrorExtR(
        a1,
        "TIFFWriteDirectorySec",
        "Starting directory %u at offset 0x%llx (%llu) might cause an IFD loop",
        *(_DWORD *)(a1 + 848),
        *(_QWORD *)(a1 + 24),
        *(_QWORD *)(a1 + 24));
    if ( v179 )
    {
      TIFFFreeDirectory(a1);
      v181 = *(void (__fastcall **)(__int64))(a1 + 1048);
      *(_DWORD *)(a1 + 16) &= 0xFFDFFFF7;
      v181(a1);
      TIFFCreateDirectory(a1);
    }
    else
    {
      *(_QWORD *)(a1 + 424) = *(_QWORD *)(a1 + 416);
    }
    return 1;
  }
  if ( (*(_DWORD *)v170 & 0x2000) != 0 && (*(_DWORD *)(a1 + 76) & 0x20000) == 0 )
  {
    v178 = 0;
    goto LABEL_597;
  }
  v178 = *(_DWORD *)(a1 + 852);
  if ( v178 != -1 )
  {
LABEL_597:
    *(_DWORD *)(a1 + 848) = v178;
    if ( (*(_DWORD *)(a1 + 16) & 0x2000) == 0 || (*(_DWORD *)(a1 + 76) & 0x20000) != 0 )
      ++*(_DWORD *)(a1 + 852);
    goto LABEL_600;
  }
  v182 = TIFFNumberOfDirectories(a1);
  *(_DWORD *)(a1 + 852) = v182;
  *(_DWORD *)(a1 + 848) = v182;
  TIFFErrorExtR(
    a1,
    "TIFFWriteDirectorySec",
    "tif_curdircount is TIFF_NON_EXISTENT_DIR_NUMBER, not expected !! Line %d",
    1330);
  TIFFfreeExt(a1, v169);
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
