# TIFFWriteDirectorySec

- ea: `0x1801577e0`
- end: `0x18015a110`
- name: `TIFFWriteDirectorySec`
- size: `10544`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `35`
- tags: `broker_com_uri`

## callers

- `0x1801573a0`
- `0x1801577c0`

## callees

- `0x180150e00`
- `0x180150e40`
- `0x180151cc0`
- `0x180151e80`
- `0x1801520f0`
- `0x180152170`
- `0x180155f20`
- `0x180156870`
- `0x1801568c0`
- `0x180156b30`
- `0x180156dd0`
- `0x1801573a0`
- `0x1801577e0`
- `0x18015a210`
- `0x18015a510`
- `0x18015a6f0`
- `0x18015a9e0`
- `0x18015b410`
- `0x18015b660`
- `0x18015c7d0`
- `0x18015d110`
- `0x18015d220`
- `0x18015d440`
- `0x18015d4d0`
- `0x18015e490`
- `0x18015e4f0`
- `0x18015e530`
- `0x18015e5b0`
- `0x18015e5e0`
- `0x18015e630`
- `0x1801665f0`
- `0x180166a40`
- `0x180167290`
- `0x18017e414`
- `0x1801ce010`

## string_xrefs

- `0x18015a000`: `Starting directory %u at offset 0x%llx (%llu) might cause an IFD loop`
- `0x18015785b`: `TIFFWriteDirectorySec`
- `0x180157903`: `TIFFWriteDirectorySec`
- `0x180159b0d`: `TIFFWriteDirectorySec`
- `0x180159c41`: `TIFFWriteDirectorySec`
- `0x180159cad`: `TIFFWriteDirectorySec`
- `0x180159cff`: `TIFFWriteDirectorySec`
- `0x180159efa`: `TIFFWriteDirectorySec`
- `0x180159f43`: `TIFFWriteDirectorySec`
- `0x18015a00e`: `TIFFWriteDirectorySec`
- `0x18015a074`: `TIFFWriteDirectorySec`
- `0x180159abd`: `TIFFWriteDirectoryTagShortPerSample`
- `0x180159b25`: `TIFFWriteDirectoryTagLong8Array`
- `0x180159b2e`: `TIFFWriteDirectoryTagLong8Array`
- `0x180159b41`: `TIFFWriteDirectoryTagSlong8Array`
- `0x180159b7b`: `TIFFWriteDirectoryTagSlong8Array`
- `0x180159ac9`: `TIFFWriteDirectoryTagColormap`
- `0x180159a8a`: `TIFFWriteDirectoryTagCheckedRational`
- `0x180159ad5`: `TIFFWriteDirectoryTagCheckedRationalArray`
- `0x180159bbd`: `TIFFWriteDirectoryTagCheckedRationalArray`
- `0x180159c15`: `TIFFWriteDirectoryTagCheckedSrationalArray`
- `0x180159b91`: `TIFFWriteDirectoryTagCheckedRationalDoubleArray`
- `0x180159be9`: `TIFFWriteDirectoryTagCheckedSrationalDoubleArray`
- `0x180157854`: `Error post-encoding before directory write`
- `0x18015789b`: `Error flushing data before directory write`
- `0x1801578f9`: `Creating TIFF with legacy Deflate codec identifier, COMPRESSION_ADOBE_DEFLATE is more widely supported`
- `0x180159b03`: `Cannot write tag %u (%s)`
- `0x180159699`: `TIFFLib: _TIFFWriteDirectorySec()`
- `0x180159ef0`: `IO error writing directory at seek to offset`
- `0x180159f3c`: `IO error writing directory`
- `0x180159b1e`: `Attempt to write unsigned long value %llu larger than 0xFFFFFFFF for tag %d in Classic TIFF file. TIFF file writing aborted`
- `0x180159b72`: `Attempt to write signed long value %lli larger than 0x7FFFFFFF (2147483647) for tag %d in Classic TIFF file. TIFF writing to file aborted`
- `0x180159b3a`: `Attempt to write signed long value %lli smaller than 0x80000000 (-2147483648) for tag %d in Classic TIFF file. TIFF writing to file aborted`
- `0x180159270`: `TIFFWriteDirectoryTagCheckedLong8Array`
- `0x1801593be`: `TIFFWriteDirectoryTagCheckedSlong8Array`

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
  __int64 v13; // r13
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
  __int64 v80; // r8
  int v81; // ebx
  unsigned __int64 v82; // rcx
  unsigned __int64 v83; // rax
  unsigned __int64 v84; // rax
  __int64 n; // r14
  unsigned int *v86; // rsi
  unsigned __int16 v87; // dx
  int v88; // eax
  unsigned __int64 v89; // rax
  __int64 v90; // rax
  int v91; // eax
  unsigned int v92; // eax
  unsigned __int64 v93; // rcx
  __int64 v94; // rdx
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // rdx
  __int64 v98; // rsi
  unsigned __int16 *v99; // r8
  unsigned __int64 v100; // kr08_8
  __int64 v101; // kr10_8
  int v102; // eax
  unsigned __int64 v103; // rax
  unsigned __int64 v104; // rax
  int v105; // eax
  unsigned __int64 v106; // rcx
  unsigned __int64 v107; // rax
  void *v108; // rsi
  unsigned __int64 v109; // rax
  unsigned __int64 v110; // rcx
  void *v111; // rsi
  void *v112; // rsi
  void *v113; // rsi
  bool v114; // zf
  int v115; // eax
  _QWORD *v116; // rsi
  unsigned int v117; // eax
  __int64 v118; // rax
  void *v119; // r14
  __int64 v120; // r8
  _DWORD *v121; // rcx
  unsigned int v122; // eax
  int v123; // eax
  __int64 *v124; // rsi
  __int64 v125; // rax
  __int64 v126; // r8
  _DWORD *v127; // rcx
  signed __int64 v128; // r9
  int v129; // edx
  __int64 v130; // r15
  __int64 v131; // rax
  __int64 v132; // rcx
  __int64 v133; // r8
  unsigned int v134; // r14d
  __int64 ii; // rsi
  unsigned __int64 v136; // rax
  unsigned __int64 v137; // rcx
  __int64 v138; // r15
  __int64 v139; // rax
  __int64 v140; // rcx
  __int64 v141; // r8
  unsigned int v142; // r14d
  __int64 jj; // rsi
  __int64 v144; // r15
  __int64 v145; // rax
  __int64 v146; // rcx
  __int64 v147; // r8
  unsigned int v148; // r14d
  __int64 kk; // rsi
  __int64 v150; // r15
  __int64 v151; // rax
  __int64 v152; // rcx
  __int64 v153; // r8
  unsigned int v154; // r14d
  __int64 mm; // rsi
  void *v156; // rsi
  void *v157; // rsi
  void *v158; // rsi
  __int64 v159; // rax
  unsigned __int64 v160; // rax
  unsigned __int64 v161; // rdx
  __int64 v162; // r8
  unsigned __int64 v163; // rax
  const char *v164; // rdx
  const char *v165; // rbx
  int v166; // eax
  const char *v167; // r8
  const char *v168; // rdx
  int v169; // eax
  _WORD *v170; // rcx
  __int64 v171; // rcx
  __int64 v172; // rax
  __int64 v173; // rcx
  _QWORD *v174; // r12
  char *v175; // rbx
  unsigned int v176; // r15d
  _WORD *v177; // rsi
  __int64 v178; // r14
  unsigned int v179; // r15d
  _WORD *v180; // rsi
  _WORD *v181; // r14
  __int64 v182; // rsi
  int v183; // eax
  int v184; // ebx
  int v185; // eax
  void (__fastcall *v186)(__int64); // rax
  int v187; // eax
  int v188; // [rsp+28h] [rbp-89h]
  int v189; // [rsp+30h] [rbp-81h]
  int v190; // [rsp+30h] [rbp-81h]
  size_t Size; // [rsp+38h] [rbp-79h]
  void *v192; // [rsp+40h] [rbp-71h]
  void *v193; // [rsp+40h] [rbp-71h]
  int v194; // [rsp+48h] [rbp-69h] BYREF
  int v195[2]; // [rsp+50h] [rbp-61h]
  unsigned int v196; // [rsp+58h] [rbp-59h]
  unsigned __int16 v197; // [rsp+5Ch] [rbp-55h] BYREF
  __int16 v198[2]; // [rsp+60h] [rbp-51h] BYREF
  int v199; // [rsp+64h] [rbp-4Dh]
  int v200; // [rsp+68h] [rbp-49h]
  _BYTE v201[4]; // [rsp+70h] [rbp-41h] BYREF
  _BYTE v202[4]; // [rsp+74h] [rbp-3Dh] BYREF
  _BYTE v203[4]; // [rsp+78h] [rbp-39h] BYREF
  _BYTE v204[4]; // [rsp+7Ch] [rbp-35h] BYREF
  _BYTE v205[4]; // [rsp+80h] [rbp-31h] BYREF
  _BYTE v206[4]; // [rsp+84h] [rbp-2Dh] BYREF
  _BYTE v207[4]; // [rsp+88h] [rbp-29h] BYREF
  _BYTE v208[4]; // [rsp+8Ch] [rbp-25h] BYREF
  unsigned int v209; // [rsp+90h] [rbp-21h] BYREF
  int v210; // [rsp+94h] [rbp-1Dh] BYREF
  void *v211; // [rsp+98h] [rbp-19h]
  void *v212; // [rsp+A0h] [rbp-11h]
  char *Str; // [rsp+A8h] [rbp-9h] BYREF
  int Src; // [rsp+118h] [rbp+67h] BYREF
  int v215; // [rsp+120h] [rbp+6Fh]
  int v216; // [rsp+128h] [rbp+77h]
  _QWORD *v217; // [rsp+130h] [rbp+7Fh]

  v217 = a4;
  v216 = a3;
  v215 = a2;
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
  *(_QWORD *)v195 = 0;
  v196 = 0;
  while ( 1 )
  {
    v194 = 0;
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
          v114 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 88);
          if ( !v114 )
            TIFFSwabLong(&Src);
          LODWORD(Size) = 4;
          LOWORD(v188) = 4;
          v14 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 256, v188, 1, Size, &Src);
        }
        else
        {
          v194 = 1;
          v14 = 1;
        }
      }
      else if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 88);
        if ( !v114 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v188) = 3;
        v14 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 256, v188, 1, Size, &Src);
      }
      else
      {
        v194 = 1;
        v14 = 1;
      }
      if ( !v14 )
        goto LABEL_522;
      if ( *(_DWORD *)(a1 + 92) > 0xFFFFu )
      {
        if ( v13 )
        {
          v114 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 92);
          if ( !v114 )
            TIFFSwabLong(&Src);
          LODWORD(Size) = 4;
          LOWORD(v188) = 4;
          v15 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 257, v188, 1, Size, &Src);
        }
        else
        {
          ++v194;
          v15 = 1;
        }
      }
      else if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 92);
        if ( !v114 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v188) = 3;
        v15 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 257, v188, 1, Size, &Src);
      }
      else
      {
        ++v194;
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
          v114 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 100);
          if ( !v114 )
            TIFFSwabLong(&Src);
          LODWORD(Size) = 4;
          LOWORD(v188) = 4;
          v16 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 322, v188, 1, Size, &Src);
        }
        else
        {
          ++v194;
          v16 = 1;
        }
      }
      else if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 100);
        if ( !v114 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v188) = 3;
        v16 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 322, v188, 1, Size, &Src);
      }
      else
      {
        ++v194;
        v16 = 1;
      }
      if ( !v16 )
        goto LABEL_522;
      if ( *(_DWORD *)(a1 + 104) > 0xFFFFu )
      {
        if ( v13 )
        {
          v114 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 104);
          if ( !v114 )
            TIFFSwabLong(&Src);
          LODWORD(Size) = 4;
          LOWORD(v188) = 4;
          v17 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 323, v188, 1, Size, &Src);
        }
        else
        {
          ++v194;
          v17 = 1;
        }
      }
      else if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 104);
        if ( !v114 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v188) = 3;
        v17 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 323, v188, 1, Size, &Src);
      }
      else
      {
        ++v194;
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
        DoubleToRational(v8, v201, v202);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v201);
          TIFFSwabLong(v202);
        }
        LODWORD(Size) = 8;
        LOWORD(v188) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 282, v188, 1, Size, v201) )
          goto LABEL_523;
      }
      else
      {
        v18 = *(_QWORD *)v12 + (((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8);
        ++v194;
        *(_QWORD *)(a1 + 416) = v18;
      }
      if ( *(float *)(a1 + 164) < 0.0 )
        goto LABEL_524;
      if ( v13 )
      {
        DoubleToRational(v8, v203, v204);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v203);
          TIFFSwabLong(v204);
        }
        LODWORD(Size) = 8;
        LOWORD(v188) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 283, v188, 1, Size, v203) )
          goto LABEL_523;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v194;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x10) != 0 )
    {
      if ( *(float *)(a1 + 172) < 0.0 )
        goto LABEL_524;
      if ( v13 )
      {
        DoubleToRational(v8, v205, v206);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v205);
          TIFFSwabLong(v206);
        }
        LODWORD(Size) = 8;
        LOWORD(v188) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 286, v188, 1, Size, v205) )
          goto LABEL_523;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v194;
      }
      if ( *(float *)(a1 + 176) < 0.0 )
      {
LABEL_524:
        TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRational", "Negative value is illegal");
        goto LABEL_522;
      }
      if ( v13 )
      {
        DoubleToRational(v8, v207, v208);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v207);
          TIFFSwabLong(v208);
        }
        LODWORD(Size) = 8;
        LOWORD(v188) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 287, v188, 1, Size, v207) )
          goto LABEL_523;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v194;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x20) != 0 )
    {
      if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 112);
        if ( !v114 )
          TIFFSwabLong(&Src);
        LODWORD(Size) = 4;
        LOWORD(v188) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 254, v188, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v194;
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
        LOWORD(v188) = 3;
        v28 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 258, v188, v27, Size, v23);
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
        ++v194;
      }
    }
    if ( *(char *)(a1 + 72) < 0 )
    {
      if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 120);
        if ( !v114 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v188) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 259, v188, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v194;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x100) != 0 )
    {
      if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 122);
        if ( !v114 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v188) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 262, v188, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v194;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x200) != 0 )
    {
      if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 124);
        if ( !v114 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v188) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 263, v188, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v194;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x400) != 0 )
    {
      if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 126);
        if ( !v114 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v188) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 266, v188, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v194;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x8000) != 0 )
    {
      if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 128);
        if ( !v114 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v188) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 274, v188, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v194;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x10000) != 0 )
    {
      if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 130);
        if ( !v114 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v188) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 277, v188, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v194;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x20000) != 0 )
    {
      if ( *(_DWORD *)(a1 + 132) > 0xFFFFu )
      {
        if ( v13 )
        {
          v114 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 132);
          if ( !v114 )
            TIFFSwabLong(&Src);
          LODWORD(Size) = 4;
          LOWORD(v188) = 4;
          v29 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 278, v188, 1, Size, &Src);
        }
        else
        {
          ++v194;
          v29 = 1;
        }
      }
      else if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 132);
        if ( !v114 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v188) = 3;
        v29 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 278, v188, 1, Size, &Src);
      }
      else
      {
        ++v194;
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
        LOWORD(v188) = 3;
        v39 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 280, v188, v38, Size, v34);
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
        ++v194;
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
        LOWORD(v188) = 3;
        v49 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 281, v188, v48, Size, v44);
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
        ++v194;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x100000) != 0 )
    {
      if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 170);
        if ( !v114 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v188) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 284, v188, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v194;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x400000) != 0 )
    {
      if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 168);
        if ( !v114 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v188) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 296, v188, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v194;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x800000) != 0 )
    {
      if ( v13 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 180, 2);
        LODWORD(Size) = 4;
        LOWORD(v188) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 297, v188, 2, Size, (void *)(a1 + 180)) )
          goto LABEL_523;
      }
      else
      {
        ++v194;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x1000000) != 0
      && !(unsigned int)TIFFWriteDirectoryTagLongLong8Array(
                          a1,
                          (int)&v194,
                          v13,
                          *(_DWORD *)(a1 + 228),
                          *(void **)(a1 + 240))
      || (*(_DWORD *)(a1 + 72) & 0x2000000) != 0
      && ((*(_DWORD *)(a1 + 16) & 0x400) != 0 || *(_QWORD *)(a1 + 232))
      && !(unsigned int)TIFFWriteDirectoryTagLongLong8Array(
                          a1,
                          (int)&v194,
                          v13,
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
          v164 = "TIFFWriteDirectoryTagColormap";
          goto LABEL_556;
        }
        TIFFmemcpy(v53, *(const void **)(a1 + 184), 2 * v50);
        TIFFmemcpy(&v54[2 * v50], *(const void **)(a1 + 192), 2 * v50);
        TIFFmemcpy(&v54[2 * (unsigned int)(2 * v50)], *(const void **)(a1 + 200), 2 * v50);
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v54, (unsigned int)(3 * v50));
        LODWORD(Size) = 6 * v50;
        LOWORD(v188) = 3;
        v55 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 320, v188, 3 * (int)v50, Size, v54);
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
        ++v194;
        v7 = 1;
      }
    }
    if ( *(int *)(a1 + 72) < 0 && *(_WORD *)(a1 + 212) )
    {
      TIFFGetFieldDefaulted(a1, 338, &v197);
      v56 = v197;
      v57 = *(_DWORD *)(a1 + 16);
      if ( v13 )
      {
        v61 = v211;
        if ( (v57 & 0x80u) != 0 )
          TIFFSwabArrayOfShort(v211, v197);
        LODWORD(Size) = 2 * v56;
        LOWORD(v188) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 338, v188, v56, Size, v61) )
          goto LABEL_523;
      }
      else
      {
        v58 = 2LL * v197;
        v59 = (v57 & 0x80000) != 0;
        v60 = 4;
        if ( v59 )
          v60 = 8;
        if ( v58 > v60 )
          *(_QWORD *)(a1 + 416) += v58;
        ++v194;
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
          v164 = "TIFFWriteDirectoryTagShortPerSample";
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
        LOWORD(v188) = 3;
        v71 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 339, v188, v70, Size, v66);
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
        ++v194;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 2) != 0
      && !(unsigned int)TIFFWriteDirectoryTagSampleformatArray(
                          a1,
                          (int)&v194,
                          v13,
                          *(unsigned __int16 *)(a1 + 130),
                          *(void **)(a1 + 144))
      || (*(_BYTE *)(a1 + 76) & 4) != 0
      && !(unsigned int)TIFFWriteDirectoryTagSampleformatArray(
                          a1,
                          (int)&v194,
                          v13,
                          *(unsigned __int16 *)(a1 + 130),
                          *(void **)(a1 + 152)) )
    {
      goto LABEL_522;
    }
    if ( (*(_BYTE *)(a1 + 76) & 8) != 0 )
    {
      if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 96);
        if ( !v114 )
          TIFFSwabLong(&Src);
        LODWORD(Size) = 4;
        LOWORD(v188) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 32997, v188, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v194;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 0x10) != 0 )
    {
      if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 108);
        if ( !v114 )
          TIFFSwabLong(&Src);
        LODWORD(Size) = 4;
        LOWORD(v188) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 32998, v188, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v194;
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
        LOWORD(v188) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 321, v188, 2, Size, (void *)(a1 + 208)) )
          goto LABEL_523;
        goto LABEL_275;
      }
      ++v194;
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
        LOWORD(v188) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 530, v188, 2, Size, (void *)(a1 + 336)) )
          goto LABEL_523;
      }
      else
      {
        ++v194;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x100) != 0 )
    {
      if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 340);
        if ( !v114 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v188) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 531, v188, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v194;
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
          v164 = "TIFFWriteDirectoryTagCheckedRationalArray";
          goto LABEL_556;
        }
        DoubleToRational(v73, v72, v72 + 4);
        DoubleToRational(v75, v74 + 8, v74 + 12);
        DoubleToRational(v76, v74 + 16, v74 + 20);
        DoubleToRational(v77, v74 + 24, v74 + 28);
        DoubleToRational(v78, v74 + 32, v74 + 36);
        DoubleToRational(v79, v74 + 40, v74 + 44);
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfFloat(v74, 12, v80);
        LODWORD(Size) = 48;
        LOWORD(v188) = 5;
        v81 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 532, v188, 6, Size, v74);
        TIFFfreeExt(a1, v74);
        if ( !v81 )
          goto LABEL_523;
        v12 = 3;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += 48LL;
        ++v194;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x1000) != 0
      && !(unsigned int)TIFFWriteDirectoryTagTransferfunction(a1, (int)&v194, v13) )
    {
      goto LABEL_522;
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x4000) != 0 )
    {
      v82 = *(unsigned int *)(a1 + 376);
      if ( v13 )
      {
        LODWORD(Size) = *(_DWORD *)(a1 + 376);
        LOWORD(v188) = 2;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 333, v188, v82, Size, *(void **)(a1 + 384)) )
          goto LABEL_523;
      }
      else
      {
        v83 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v83 = 8;
        if ( v82 > v83 )
        {
          v84 = v82 + 1;
          if ( (v82 & 1) == 0 )
            v84 = *(unsigned int *)(a1 + 376);
          *(_QWORD *)(a1 + 416) += v84;
        }
        ++v194;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x40000) != 0 )
    {
      if ( v13 )
      {
        v114 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 392);
        if ( !v114 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v188) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v194, v13, 334, v188, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v194;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x20000) != 0 && !(unsigned int)TIFFWriteDirectoryTagSubifd(a1, (int)&v194, v13) )
      goto LABEL_522;
    for ( n = 0; (unsigned __int64)(unsigned int)n < *(_QWORD *)(a1 + 1240); n = (unsigned int)(n + 1) )
    {
      v86 = *(unsigned int **)(*(_QWORD *)(a1 + 1232) + 8 * n);
      v87 = *((_WORD *)v86 + 12);
      if ( v87 >= 0x42u )
      {
        v88 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)v87 >> 5) + 72);
        if ( _bittest(&v88, v87 & 0x1F) )
        {
          switch ( v86[4] )
          {
            case 1u:
              TIFFGetField(a1, *v86, &Str);
              v12 = (unsigned __int64)Str;
              v92 = strlen_0(Str);
              if ( v13 )
              {
                LODWORD(Size) = v92;
                LOWORD(v188) = 2;
                v91 = TIFFWriteDirectoryTagData(
                        a1,
                        (int)&v194,
                        v13,
                        *(unsigned __int16 *)v86,
                        v188,
                        v92,
                        Size,
                        (void *)v12);
                goto LABEL_356;
              }
              v93 = 4;
              v94 = v92;
              if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                v93 = 8;
              if ( v92 > v93 )
              {
                v114 = (v92 & 1) == 0;
                v95 = v92 + 1LL;
                if ( v114 )
                  v95 = v94;
                *(_QWORD *)(a1 + 416) += v95;
              }
              ++v194;
              break;
            case 4u:
              TIFFGetField(a1, *v86, v198);
              if ( v13 )
              {
                v114 = *(_BYTE *)(a1 + 16) >= 0;
                v12 = *(unsigned __int16 *)v86;
                LOWORD(Src) = v198[0];
                if ( !v114 )
                  TIFFSwabShort(&Src);
                LODWORD(Size) = 2;
                LOWORD(v188) = 3;
                v91 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, (unsigned __int16)v12, v188, 1, Size, &Src);
LABEL_356:
                if ( !v91 )
                  goto LABEL_523;
                continue;
              }
              ++v194;
              break;
            case 6u:
              TIFFGetField(a1, *v86, &v210);
              if ( v13 )
              {
                v114 = *(_BYTE *)(a1 + 16) >= 0;
                v12 = *(unsigned __int16 *)v86;
                Src = v210;
                if ( !v114 )
                  TIFFSwabLong(&Src);
                LODWORD(Size) = 4;
                LOWORD(v188) = 4;
                v91 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, (unsigned __int16)v12, v188, 1, Size, &Src);
                goto LABEL_356;
              }
              ++v194;
              break;
            case 0x28u:
              TIFFGetField(a1, *v86, &v209);
              if ( v13 )
              {
                LODWORD(Size) = v209;
                LOWORD(v188) = 7;
                v91 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, *(unsigned __int16 *)v86, v188, v209, Size, v212);
                goto LABEL_356;
              }
              v89 = 4;
              if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                v89 = 8;
              if ( v209 > v89 )
              {
                v90 = v209 + 1LL;
                if ( (v209 & 1) == 0 )
                  v90 = v209;
                *(_QWORD *)(a1 + 416) += v90;
              }
              ++v194;
              break;
            default:
              v165 = "unknown";
              if ( *((_QWORD *)v86 + 4) )
                v165 = (const char *)*((_QWORD *)v86 + 4);
              v166 = TIFFFieldTag(v86);
              TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Cannot write tag %u (%s)", v166, v165);
              goto LABEL_522;
          }
        }
      }
    }
LABEL_358:
    v96 = 0;
    v200 = 0;
    if ( *(_DWORD *)(a1 + 396) )
    {
      while ( 1 )
      {
        v97 = *(_QWORD *)(a1 + 400);
        v98 = 3 * v96;
        v99 = *(unsigned __int16 **)(v97 + 24 * v96);
        v100 = v12;
        v101 = v7;
        v7 = *v99;
        v12 = *(unsigned int *)(v97 + 24 * v96 + 8);
        v102 = *((_DWORD *)v99 + 2) - 1;
        LOWORD(Src) = *v99;
        switch ( v102 )
        {
          case 0:
            if ( !v13 )
              goto LABEL_361;
            LODWORD(Size) = v12;
            LOWORD(v188) = 1;
            v105 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v194,
                     v13,
                     (unsigned __int16)v7,
                     v188,
                     v12,
                     Size,
                     *(void **)(v97 + 8 * v98 + 16));
            goto LABEL_369;
          case 1:
            if ( !v13 )
              goto LABEL_361;
            LODWORD(Size) = v12;
            LOWORD(v188) = 2;
            v105 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v194,
                     v13,
                     (unsigned __int16)v7,
                     v188,
                     v12,
                     Size,
                     *(void **)(v97 + 8 * v98 + 16));
            goto LABEL_369;
          case 2:
            if ( !v13 )
            {
              v106 = 2 * v12;
              goto LABEL_379;
            }
            v108 = *(void **)(v97 + 8 * v98 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfShort(v108, v12);
            LODWORD(Size) = 2 * v12;
            LOWORD(v188) = 3;
            v105 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, (unsigned __int16)v7, v188, v12, Size, v108);
            goto LABEL_369;
          case 3:
            if ( !v13 )
            {
              v106 = 4 * v12;
              goto LABEL_379;
            }
            v112 = *(void **)(v97 + 8 * v98 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v112, v12, v99);
            LODWORD(Size) = 4 * v12;
            LOWORD(v188) = 4;
            v105 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, (unsigned __int16)v7, v188, v12, Size, v112);
            goto LABEL_369;
          case 4:
            v199 = TIFFFieldSetGetSize(v99);
            v129 = v199;
            if ( v199 == 8 )
            {
              if ( !v13 )
                goto LABEL_440;
              v130 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v98 + 16);
              v131 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v12));
              v7 = v131;
              if ( !v131 )
              {
                TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRationalDoubleArray", "Out of memory");
                TIFFfreeExt(a1, *(_QWORD *)v195);
                return 0;
              }
              v134 = 0;
              for ( ii = v131; v134 < (unsigned int)v12; ++v134 )
              {
                DoubleToRational(v132, ii, ii + 4);
                ii += 8;
                v130 += 8;
              }
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v12), v133);
              v192 = (void *)v7;
              LODWORD(Size) = 8 * v12;
              v189 = v12;
              LOWORD(v188) = 5;
              goto LABEL_447;
            }
            if ( !v13 )
              goto LABEL_450;
            v138 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v98 + 16);
            v139 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v12));
            v7 = v139;
            if ( !v139 )
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRationalArray", "Out of memory");
              TIFFfreeExt(a1, *(_QWORD *)v195);
              return 0;
            }
            v142 = 0;
            for ( jj = v139; v142 < (unsigned int)v12; ++v142 )
            {
              DoubleToRational(v140, jj, jj + 4);
              jj += 8;
              v138 += 4;
            }
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v12), v141);
            v193 = (void *)v7;
            LODWORD(Size) = 8 * v12;
            v190 = v12;
            LOWORD(v188) = 5;
            goto LABEL_461;
          case 5:
            if ( !v13 )
              goto LABEL_361;
            LODWORD(Size) = v12;
            LOWORD(v188) = 6;
            v105 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v194,
                     v13,
                     (unsigned __int16)v7,
                     v188,
                     v12,
                     Size,
                     *(void **)(v97 + 8 * v98 + 16));
            goto LABEL_369;
          case 6:
            if ( v13 )
            {
              LODWORD(Size) = v12;
              LOWORD(v188) = 7;
              v105 = TIFFWriteDirectoryTagData(
                       a1,
                       (int)&v194,
                       v13,
                       (unsigned __int16)v7,
                       v188,
                       v12,
                       Size,
                       *(void **)(v97 + 8 * v98 + 16));
              goto LABEL_369;
            }
LABEL_361:
            v103 = 4;
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
              v103 = 8;
            if ( v12 > v103 )
            {
              v104 = v12 + 1;
              if ( (v12 & 1) == 0 )
                v104 = v12;
              *(_QWORD *)(a1 + 416) += v104;
            }
            goto LABEL_367;
          case 7:
            if ( v13 )
            {
              v111 = *(void **)(v97 + 8 * v98 + 16);
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfShort(v111, v12);
              LODWORD(Size) = 2 * v12;
              LOWORD(v188) = 8;
              v105 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, (unsigned __int16)v7, v188, v12, Size, v111);
              goto LABEL_369;
            }
            v109 = 4;
            v110 = 2 * v12;
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
              v109 = 8;
            if ( v110 > v109 )
            {
              *(_QWORD *)(a1 + 416) += v110;
              ++v194;
              goto LABEL_497;
            }
            goto LABEL_367;
          case 8:
            if ( !v13 )
            {
              v106 = 4 * v12;
              goto LABEL_379;
            }
            v113 = *(void **)(v97 + 8 * v98 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v113, v12, v99);
            LODWORD(Size) = 4 * v12;
            LOWORD(v188) = 9;
            v105 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, (unsigned __int16)v7, v188, v12, Size, v113);
            goto LABEL_369;
          case 9:
            v199 = TIFFFieldSetGetSize(v99);
            v129 = v199;
            if ( v199 == 8 )
            {
              if ( v13 )
              {
                v144 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v98 + 16);
                v145 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v12));
                v7 = v145;
                if ( !v145 )
                {
                  TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSrationalDoubleArray", "Out of memory");
                  TIFFfreeExt(a1, *(_QWORD *)v195);
                  return 0;
                }
                v148 = 0;
                for ( kk = v145; v148 < (unsigned int)v12; ++v148 )
                {
                  DoubleToSrational(v146, kk, kk + 4);
                  kk += 8;
                  v144 += 8;
                }
                if ( *(char *)(a1 + 16) < 0 )
                  TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v12), v147);
                v192 = (void *)v7;
                LODWORD(Size) = 8 * v12;
                v189 = v12;
                LOWORD(v188) = 10;
LABEL_447:
                v13 = *(_QWORD *)v195;
                v12 = (unsigned int)TIFFWriteDirectoryTagData(
                                      a1,
                                      (int)&v194,
                                      v195[0],
                                      (unsigned __int16)Src,
                                      v188,
                                      v189,
                                      Size,
                                      v192);
                TIFFfreeExt(a1, v7);
                if ( !(_DWORD)v12 )
                  goto LABEL_523;
              }
              else
              {
LABEL_440:
                v106 = 4LL * (unsigned int)(2 * v12);
LABEL_379:
                v107 = 4;
                if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                  v107 = 8;
                if ( v106 <= v107 )
                {
LABEL_367:
                  ++v194;
                }
                else
                {
                  *(_QWORD *)(a1 + 416) += v106;
                  ++v194;
                }
              }
            }
            else
            {
              if ( v13 )
              {
                v150 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v98 + 16);
                v151 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v12));
                v7 = v151;
                if ( !v151 )
                {
                  TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSrationalArray", "Out of memory");
                  TIFFfreeExt(a1, *(_QWORD *)v195);
                  return 0;
                }
                v154 = 0;
                for ( mm = v151; v154 < (unsigned int)v12; ++v154 )
                {
                  DoubleToSrational(v152, mm, mm + 4);
                  mm += 8;
                  v150 += 4;
                }
                if ( *(char *)(a1 + 16) < 0 )
                  TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v12), v153);
                v193 = (void *)v7;
                LODWORD(Size) = 8 * v12;
                v190 = v12;
                LOWORD(v188) = 10;
LABEL_461:
                v13 = *(_QWORD *)v195;
                v12 = (unsigned int)TIFFWriteDirectoryTagData(
                                      a1,
                                      (int)&v194,
                                      v195[0],
                                      (unsigned __int16)Src,
                                      v188,
                                      v190,
                                      Size,
                                      v193);
                TIFFfreeExt(a1, v7);
                if ( !(_DWORD)v12 )
                  goto LABEL_523;
                v129 = v199;
              }
              else
              {
LABEL_450:
                v136 = 4;
                v137 = 4LL * (unsigned int)(2 * v12);
                if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                  v136 = 8;
                if ( v137 > v136 )
                  *(_QWORD *)(a1 + 416) += v137;
                ++v194;
              }
              if ( v129 != 4 )
                TIFFErrorExtR(
                  a1,
                  "TIFFLib: _TIFFWriteDirectorySec()",
                  "Rational2Double: .set_field_type is not 4 but %d",
                  v129);
            }
            goto LABEL_497;
          case 10:
            if ( !v13 )
            {
              v106 = 4 * v12;
              goto LABEL_379;
            }
            v156 = *(void **)(v97 + 8 * v98 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v156, v12, v99);
            LODWORD(Size) = 4 * v12;
            LOWORD(v188) = 11;
            v105 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, (unsigned __int16)v7, v188, v12, Size, v156);
            goto LABEL_369;
          case 11:
            if ( !v13 )
            {
              v106 = 8 * v12;
              goto LABEL_379;
            }
            v157 = *(void **)(v97 + 8 * v98 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfDouble(v157, v12);
            LODWORD(Size) = 8 * v12;
            LOWORD(v188) = 12;
            v105 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, (unsigned __int16)v7, v188, v12, Size, v157);
            goto LABEL_369;
          case 12:
            if ( !v13 )
            {
              v106 = 4 * v12;
              goto LABEL_379;
            }
            v158 = *(void **)(v97 + 8 * v98 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v158, v12, v99);
            LODWORD(Size) = 4 * v12;
            LOWORD(v188) = 13;
            v105 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, (unsigned __int16)v7, v188, v12, Size, v158);
LABEL_369:
            if ( !v105 )
              goto LABEL_523;
            goto LABEL_497;
          case 15:
            if ( v13 )
            {
              v115 = *(_DWORD *)(a1 + 16);
              v116 = *(_QWORD **)(v97 + 8 * v98 + 16);
              if ( (v115 & 0x80000) != 0 )
              {
                if ( (v115 & 0x80u) != 0 )
                  TIFFSwabArrayOfDouble(v116, v12);
                LODWORD(Size) = 8 * v12;
                LOWORD(v188) = 16;
                v117 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, (unsigned __int16)v7, v188, v12, Size, v116);
LABEL_414:
                v12 = v117;
                v114 = v117 == 0;
                goto LABEL_496;
              }
              v118 = TIFFmallocExt(a1, 4 * v12);
              v119 = (void *)v118;
              if ( !v118 )
              {
                v164 = "TIFFWriteDirectoryTagLong8Array";
                goto LABEL_556;
              }
              v120 = 0;
              v121 = (_DWORD *)v118;
              if ( (_DWORD)v12 )
              {
                while ( *v116 <= 0xFFFFFFFF )
                {
                  *v121++ = *v116++;
                  v120 = (unsigned int)(v120 + 1);
                  if ( (unsigned int)v120 >= (unsigned int)v12 )
                    goto LABEL_419;
                }
                v167 = "Attempt to write unsigned long value %llu larger than 0xFFFFFFFF for tag %d in Classic TIFF file."
                       " TIFF file writing aborted";
                v168 = "TIFFWriteDirectoryTagLong8Array";
LABEL_535:
                TIFFErrorExtR(a1, v168, v167);
                TIFFfreeExt(a1, v119);
                TIFFfreeExt(a1, v13);
                return 0;
              }
LABEL_419:
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v118, v12, v120);
              LODWORD(Size) = 4 * v12;
              LOWORD(v188) = 4;
              v122 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, (unsigned __int16)v7, v188, v12, Size, v119);
LABEL_422:
              v12 = v122;
              TIFFfreeExt(a1, v119);
              v114 = (_DWORD)v12 == 0;
              goto LABEL_496;
            }
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) == 0 )
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedLong8Array", "LONG8 not allowed for ClassicTIFF", 8);
              v12 = 0;
              v114 = 1;
              goto LABEL_496;
            }
            goto LABEL_407;
          case 16:
            if ( v13 )
            {
              v123 = *(_DWORD *)(a1 + 16);
              v124 = *(__int64 **)(v97 + 8 * v98 + 16);
              if ( (v123 & 0x80000) != 0 )
              {
                if ( (v123 & 0x80u) != 0 )
                  TIFFSwabArrayOfDouble(v124, v12);
                LODWORD(Size) = 8 * v12;
                LOWORD(v188) = 17;
                v117 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, (unsigned __int16)v7, v188, v12, Size, v124);
                goto LABEL_414;
              }
              v125 = TIFFmallocExt(a1, 4 * v12);
              v119 = (void *)v125;
              if ( !v125 )
              {
                v164 = "TIFFWriteDirectoryTagSlong8Array";
                goto LABEL_556;
              }
              v126 = 0;
              v127 = (_DWORD *)v125;
              if ( (_DWORD)v12 )
              {
                while ( 1 )
                {
                  v128 = *v124;
                  if ( *v124 > 0x7FFFFFFF )
                    break;
                  if ( v128 < (__int64)0xFFFFFFFF80000000uLL )
                  {
                    v167 = "Attempt to write signed long value %lli smaller than 0x80000000 (-2147483648) for tag %d in C"
                           "lassic TIFF file. TIFF writing to file aborted";
                    goto LABEL_534;
                  }
                  *v127 = v128;
                  ++v124;
                  ++v127;
                  v126 = (unsigned int)(v126 + 1);
                  if ( (unsigned int)v126 >= (unsigned int)v12 )
                    goto LABEL_435;
                }
                v167 = "Attempt to write signed long value %lli larger than 0x7FFFFFFF (2147483647) for tag %d in Classic"
                       " TIFF file. TIFF writing to file aborted";
LABEL_534:
                v168 = "TIFFWriteDirectoryTagSlong8Array";
                goto LABEL_535;
              }
LABEL_435:
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v125, v12, v126);
              LODWORD(Size) = 4 * v12;
              LOWORD(v188) = 9;
              v122 = TIFFWriteDirectoryTagData(a1, (int)&v194, v13, (unsigned __int16)v7, v188, v12, Size, v119);
              goto LABEL_422;
            }
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
            {
LABEL_407:
              if ( 8 * v12 > 8 )
                *(_QWORD *)(a1 + 416) += 8 * v12;
              ++v194;
              v12 = 1;
              v114 = 0;
            }
            else
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSlong8Array", "SLONG8 not allowed for ClassicTIFF", 8);
              v12 = 0;
              v114 = 1;
            }
LABEL_496:
            if ( v114 )
              goto LABEL_522;
LABEL_497:
            v96 = (unsigned int)(v200 + 1);
            v200 = v96;
            if ( (unsigned int)v96 >= *(_DWORD *)(a1 + 396) )
              goto LABEL_498;
            break;
          case 17:
            v114 = (unsigned int)TIFFWriteDirectoryTagIfdIfd8Array(
                                   a1,
                                   &v194,
                                   v13,
                                   v7,
                                   v12,
                                   *(void **)(v97 + 8 * v98 + 16)) == 0;
            goto LABEL_496;
          default:
            v7 = v101;
            v12 = v100;
            goto LABEL_497;
        }
      }
    }
LABEL_498:
    if ( v13 )
      break;
    v12 = a1 + 416;
    if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
      v159 = (unsigned int)(20 * v194 + 16);
    else
      v159 = (unsigned int)(12 * v194 + 6);
    *(_QWORD *)v12 = *(_QWORD *)(a1 + 416) + v159;
    *(_QWORD *)v195 = TIFFmallocExt(a1, 32LL * (unsigned int)v194);
    v13 = *(_QWORD *)v195;
    if ( !*(_QWORD *)v195 )
    {
      TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Out of memory");
      return 0;
    }
    v5 = v215;
    if ( v215 )
    {
      if ( *(_QWORD *)(a1 + 24) )
      {
        if ( *(_QWORD *)v12 > *(_QWORD *)(a1 + 424) )
        {
          TIFFfreeExt(a1, *(_QWORD *)v195);
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
      v160 = *(_QWORD *)(a1 + 424);
      if ( !v160 || *(_QWORD *)v12 > v160 )
        *(_QWORD *)(a1 + 24) = ((*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 1200))(
                                  *(_QWORD *)(a1 + 1176),
                                  0,
                                  2)
                              + 1)
                             & 0xFFFFFFFFFFFFFFFEuLL;
    }
    if ( v217 )
      *v217 = *(_QWORD *)(a1 + 24);
    v161 = *(_QWORD *)(a1 + 24);
    if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
    {
      v162 = (unsigned int)(20 * v194 + 16);
      v163 = v162 + v161;
    }
    else
    {
      LODWORD(v162) = 12 * v194 + 6;
      v163 = (unsigned int)(v161 + v162);
    }
    *(_QWORD *)(a1 + 880) = v163;
    v8 = (unsigned int)v162;
    v196 = v162;
    if ( v163 < v161 || v163 < (unsigned int)v162 )
    {
      TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Maximum TIFF file size exceeded");
      TIFFfreeExt(a1, v13);
      return 0;
    }
    if ( (v163 & 1) != 0 )
      *(_QWORD *)(a1 + 880) = v163 + 1;
    v7 = 1;
  }
  if ( !v215 || (*(_DWORD *)(a1 + 76) & 0x20000) == 0 || *(_QWORD *)(a1 + 896) )
    goto LABEL_554;
  v169 = 0;
  v170 = (_WORD *)v13;
  if ( !v194 )
  {
LABEL_550:
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Cannot find SubIFD tag", 8);
    TIFFfreeExt(a1, v13);
    return 0;
  }
  while ( *v170 != 330 )
  {
    ++v169;
    v170 += 16;
    if ( v169 == v194 )
      goto LABEL_550;
  }
  v171 = *(_QWORD *)(a1 + 24);
  if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
  {
    v172 = (unsigned int)(20 * v169);
    v173 = v171 + 20;
  }
  else
  {
    v172 = (unsigned int)(12 * v169);
    v173 = v171 + 10;
  }
  *(_QWORD *)(a1 + 896) = v172 + v173;
LABEL_554:
  v174 = (_QWORD *)TIFFmallocExt(a1, v196);
  if ( !v174 )
  {
    v164 = "TIFFWriteDirectorySec";
LABEL_556:
    TIFFErrorExtR(a1, v164, "Out of memory");
    goto LABEL_523;
  }
  v175 = (char *)(a1 + 16);
  if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
  {
    *v174 = (unsigned int)v194;
    if ( *v175 < 0 )
      TIFFSwabLong8(v174);
    v179 = 0;
    v180 = v174 + 1;
    v181 = (_WORD *)v13;
    if ( v194 )
    {
      do
      {
        *v180 = *v181;
        if ( *v175 < 0 )
          TIFFSwabShort(v180);
        v180[1] = v181[1];
        if ( *v175 < 0 )
          TIFFSwabShort(v180 + 1);
        TIFFmemcpy(v180 + 2, v181 + 4, 8u);
        if ( *v175 < 0 )
          TIFFSwabLong8(v180 + 2);
        TIFFmemcpy(v180 + 6, v181 + 8, 8u);
        v180 += 10;
        v181 += 16;
        ++v179;
      }
      while ( v179 < v194 );
      v13 = *(_QWORD *)v195;
      v175 = (char *)(a1 + 16);
    }
    TIFFmemcpy(v180, (const void *)(a1 + 32), 8u);
    if ( *v175 < 0 )
      TIFFSwabLong8(v180);
  }
  else
  {
    *(_WORD *)v174 = v194;
    if ( *v175 < 0 )
      TIFFSwabShort(v174);
    v176 = 0;
    v177 = (_WORD *)v174 + 1;
    v178 = v13;
    if ( v194 )
    {
      do
      {
        *v177 = *(_WORD *)v178;
        if ( *v175 < 0 )
          TIFFSwabShort(v177);
        v177[1] = *(_WORD *)(v178 + 2);
        if ( *v175 < 0 )
          TIFFSwabShort(v177 + 1);
        Src = *(_DWORD *)(v178 + 8);
        TIFFmemcpy(v177 + 2, &Src, 4u);
        if ( *v175 < 0 )
          TIFFSwabLong(v177 + 2);
        TIFFmemcpy(v177 + 4, (const void *)(v178 + 16), 4u);
        v177 += 6;
        v178 += 32;
        ++v176;
      }
      while ( v176 < v194 );
      v13 = *(_QWORD *)v195;
      v175 = (char *)(a1 + 16);
    }
    v114 = *v175 >= 0;
    Src = *(_DWORD *)(a1 + 32);
    if ( !v114 )
      TIFFSwabLong(&Src);
    TIFFmemcpy(v177, &Src, 4u);
    v175 = (char *)(a1 + 16);
  }
  TIFFfreeExt(a1, v13);
  if ( !(unsigned int)TIFFSeekOK(a1, *(_QWORD *)(a1 + 24)) )
  {
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "IO error writing directory at seek to offset");
    TIFFfreeExt(a1, v174);
    return 0;
  }
  v182 = v196;
  if ( (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD))(a1 + 1192))(*(_QWORD *)(a1 + 1176), v174, v196) != v182 )
  {
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "IO error writing directory");
    TIFFfreeExt(a1, v174);
    return 0;
  }
  TIFFfreeExt(a1, v174);
  if ( !v215 || *(_BYTE *)(a1 + 409) )
  {
LABEL_600:
    v184 = v216;
    *(_BYTE *)(a1 + 409) = 1;
    if ( v184 )
    {
      v185 = *(_DWORD *)(a1 + 16);
      if ( (v185 & 0x2000) != 0 && !*(_WORD *)(a1 + 888) )
        *(_DWORD *)(a1 + 16) = v185 & 0xFFFFDFFF;
    }
    if ( !(unsigned int)TIFFCheckDirNumberAndOffset(a1, *(unsigned int *)(a1 + 848), *(_QWORD *)(a1 + 24)) )
      TIFFErrorExtR(
        a1,
        "TIFFWriteDirectorySec",
        "Starting directory %u at offset 0x%llx (%llu) might cause an IFD loop",
        *(_DWORD *)(a1 + 848),
        *(_QWORD *)(a1 + 24),
        *(_QWORD *)(a1 + 24));
    if ( v184 )
    {
      TIFFFreeDirectory(a1);
      v186 = *(void (__fastcall **)(__int64))(a1 + 1048);
      *(_DWORD *)(a1 + 16) &= 0xFFDFFFF7;
      v186(a1);
      TIFFCreateDirectory(a1);
    }
    else
    {
      *(_QWORD *)(a1 + 424) = *(_QWORD *)(a1 + 416);
    }
    return 1;
  }
  if ( (*(_DWORD *)v175 & 0x2000) != 0 && (*(_DWORD *)(a1 + 76) & 0x20000) == 0 )
  {
    v183 = 0;
    goto LABEL_597;
  }
  v183 = *(_DWORD *)(a1 + 852);
  if ( v183 != -1 )
  {
LABEL_597:
    *(_DWORD *)(a1 + 848) = v183;
    if ( (*(_DWORD *)(a1 + 16) & 0x2000) == 0 || (*(_DWORD *)(a1 + 76) & 0x20000) != 0 )
      ++*(_DWORD *)(a1 + 852);
    goto LABEL_600;
  }
  v187 = TIFFNumberOfDirectories(a1);
  *(_DWORD *)(a1 + 852) = v187;
  *(_DWORD *)(a1 + 848) = v187;
  TIFFErrorExtR(
    a1,
    "TIFFWriteDirectorySec",
    "tif_curdircount is TIFF_NON_EXISTENT_DIR_NUMBER, not expected !! Line %d",
    1330);
  TIFFfreeExt(a1, v174);
  return 0;
}

```

## disassembly

```asm
0x1801577e0  mov     rax, rsp
0x1801577e3  mov     [rax+20h], r9
0x1801577e7  mov     [rax+18h], r8d
0x1801577eb  mov     [rax+10h], edx
0x1801577ee  push    rbp
0x1801577ef  push    rbx
0x1801577f0  push    rsi
0x1801577f1  push    rdi
0x1801577f2  push    r12
0x1801577f4  push    r13
0x1801577f6  push    r14
0x1801577f8  push    r15
0x1801577fa  lea     rbp, [rax-5Fh]
0x1801577fe  sub     rsp, 0C8h
0x180157805  cmp     dword ptr [rcx+0Ch], 0
0x180157809  mov     ebx, r8d
0x18015780c  movaps  xmmword ptr [rax-58h], xmm6
0x180157810  mov     r14d, edx
0x180157813  mov     rdi, rcx
0x180157816  mov     r12d, 1
0x18015781c  jz      loc_18015A0A6
0x180157822  call    _TIFFFillStriles
0x180157827  xor     esi, esi
0x180157829  test    ebx, ebx
0x18015782b  jz      loc_1801578E8
0x180157831  mov     eax, [rdi+10h]
0x180157834  bt      eax, 0Ch
0x180157838  jnb     short loc_180157871
0x18015783a  btr     eax, 0Ch
0x18015783e  mov     rcx, rdi
0x180157841  mov     [rdi+10h], eax
0x180157844  mov     rax, [rdi+3D0h]
0x18015784b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180157850  test    eax, eax
0x180157852  jnz     short loc_180157871
0x180157854  lea     r8, aErrorPostEncod; "Error post-encoding before directory wr"...
0x18015785b  lea     rdx, aTiffwritedirec_1; "TIFFWriteDirectorySec"
0x180157862  mov     rcx, rdi
0x180157865  call    TIFFErrorExtR
0x18015786a  xor     eax, eax
0x18015786c  jmp     loc_18015A0A9
0x180157871  mov     rax, [rdi+408h]
0x180157878  mov     rcx, rdi
0x18015787b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180157880  cmp     [rdi+470h], rsi
0x180157887  jle     short loc_1801578A4
0x180157889  test    byte ptr [rdi+10h], 40h
0x18015788d  jz      short loc_1801578A4
0x18015788f  mov     rcx, rdi
0x180157892  call    TIFFFlushData1
0x180157897  test    eax, eax
0x180157899  jnz     short loc_1801578A4
0x18015789b  lea     r8, aErrorFlushingD; "Error flushing data before directory wr"...
0x1801578a2  jmp     short loc_18015785B
0x1801578a4  test    dword ptr [rdi+10h], 200h
0x1801578ab  jz      short loc_1801578E4
0x1801578ad  mov     rdx, [rdi+448h]
0x1801578b4  test    rdx, rdx
0x1801578b7  jz      short loc_1801578E4
0x1801578b9  mov     rcx, rdi
0x1801578bc  call    _TIFFfreeExt
0x1801578c1  mov     [rdi+448h], rsi
0x1801578c8  mov     [rdi+470h], rsi
0x1801578cf  mov     [rdi+450h], rsi
0x1801578d6  mov     [rdi+458h], rsi
0x1801578dd  mov     [rdi+460h], rsi
0x1801578e4  and     dword ptr [rdi+10h], 0FFFFFFAFh
0x1801578e8  test    byte ptr [rdi+48h], 80h
0x1801578ec  jz      short loc_18015790F
0x1801578ee  mov     eax, 80B2h
0x1801578f3  cmp     [rdi+78h], ax
0x1801578f7  jnz     short loc_18015790F
0x1801578f9  lea     r8, aCreatingTiffWi; "Creating TIFF with legacy Deflate codec"...
0x180157900  mov     rcx, rdi
0x180157903  lea     rdx, aTiffwritedirec_1; "TIFFWriteDirectorySec"
0x18015790a  call    TIFFWarningExtR
0x18015790f  xor     eax, eax
0x180157911  lea     rbx, [rdi+1A0h]
0x180157918  mov     r13d, eax
0x18015791b  mov     qword ptr [rbp+57h+var_B8], rax
0x18015791f  mov     [rbp+57h+var_B0], eax
0x180157922  xorps   xmm6, xmm6
0x180157925  mov     [rbp+57h+var_C0], eax
0x180157928  lea     r10, __ImageBase
0x18015792f  mov     r11d, 7
0x180157935  mov     r9d, 8
0x18015793b  mov     r15d, 4
0x180157941  mov     esi, 2
0x180157946  test    r13, r13
0x180157949  jnz     short loc_18015794E
0x18015794b  mov     [rbx], rax
0x18015794e  test    r14d, r14d
0x180157951  jz      loc_180158FDB
0x180157957  test    byte ptr [rdi+48h], 2
0x18015795b  jz      loc_180157ABB
0x180157961  mov     eax, [rdi+58h]
0x180157964  cmp     eax, 0FFFFh
0x180157969  ja      short loc_1801579C4
0x18015796b  test    r13, r13
0x18015796e  jnz     short loc_18015797C
0x180157970  mov     [rbp+57h+var_C0], r12d
0x180157974  mov     eax, r12d
0x180157977  jmp     loc_180157A12
0x18015797c  test    byte ptr [rdi+10h], 80h
0x180157980  mov     word ptr [rbp+57h+Src], ax
0x180157984  jz      short loc_18015798F
0x180157986  lea     rcx, [rbp+57h+Src]
0x18015798a  call    TIFFSwabShort
0x18015798f  lea     rax, [rbp+57h+Src]
0x180157993  mov     r14d, 3
0x180157999  mov     [rsp+38h], rax; Src
0x18015799e  lea     rdx, [rbp+57h+var_C0]; int
0x1801579a2  mov     dword ptr [rsp+100h+Size], esi; Size
0x1801579a6  mov     r9d, 100h; int
0x1801579ac  mov     dword ptr [rsp+100h+var_D8], r12d; int
0x1801579b1  mov     r8, r13; int
0x1801579b4  mov     rcx, rdi; int
0x1801579b7  mov     word ptr [rsp+100h+var_E0], r14w; int
0x1801579bd  call    TIFFWriteDirectoryTagData
0x1801579c2  jmp     short loc_180157A18
0x1801579c4  test    r13, r13
0x1801579c7  jnz     short loc_1801579D2
0x1801579c9  mov     [rbp+57h+var_C0], r12d
0x1801579cd  mov     eax, r12d
0x1801579d0  jmp     short loc_180157A12
0x1801579d2  test    byte ptr [rdi+10h], 80h
0x1801579d6  mov     [rbp+57h+Src], eax
0x1801579d9  jz      short loc_1801579E4
0x1801579db  lea     rcx, [rbp+57h+Src]
0x1801579df  call    TIFFSwabLong
0x1801579e4  lea     rax, [rbp+57h+Src]
0x1801579e8  mov     r9d, 100h; int
0x1801579ee  mov     [rsp+38h], rax; Src
0x1801579f3  lea     rdx, [rbp+57h+var_C0]; int
0x1801579f7  mov     dword ptr [rsp+100h+Size], r15d; Size
0x1801579fc  mov     r8, r13; int
0x1801579ff  mov     dword ptr [rsp+100h+var_D8], r12d; int
0x180157a04  mov     rcx, rdi; int
0x180157a07  mov     word ptr [rsp+100h+var_E0], r15w; int
0x180157a0d  call    TIFFWriteDirectoryTagData
0x180157a12  mov     r14d, 3
0x180157a18  test    eax, eax
0x180157a1a  jz      loc_180159A99
0x180157a20  mov     eax, [rdi+5Ch]
0x180157a23  cmp     eax, 0FFFFh
0x180157a28  ja      short loc_180157A64
0x180157a2a  test    r13, r13
0x180157a2d  jnz     short loc_180157A37
0x180157a2f  inc     [rbp+57h+var_C0]
0x180157a32  mov     eax, r12d
0x180157a35  jmp     short loc_180157AB1
0x180157a37  test    byte ptr [rdi+10h], 80h
0x180157a3b  mov     word ptr [rbp+57h+Src], ax
0x180157a3f  jz      short loc_180157A4A
0x180157a41  lea     rcx, [rbp+57h+Src]
0x180157a45  call    TIFFSwabShort
0x180157a4a  lea     rax, [rbp+57h+Src]
0x180157a4e  mov     [rsp+38h], rax
0x180157a53  mov     dword ptr [rsp+100h+Size], esi
0x180157a57  mov     dword ptr [rsp+100h+var_D8], r12d
0x180157a5c  mov     word ptr [rsp+100h+var_E0], r14w
0x180157a62  jmp     short loc_180157A9C
0x180157a64  test    r13, r13
0x180157a67  jnz     short loc_180157A71
0x180157a69  inc     [rbp+57h+var_C0]
0x180157a6c  mov     eax, r12d
0x180157a6f  jmp     short loc_180157AB1
0x180157a71  test    byte ptr [rdi+10h], 80h
0x180157a75  mov     [rbp+57h+Src], eax
0x180157a78  jz      short loc_180157A83
0x180157a7a  lea     rcx, [rbp+57h+Src]
0x180157a7e  call    TIFFSwabLong
0x180157a83  lea     rax, [rbp+57h+Src]
0x180157a87  mov     [rsp+38h], rax; Src
0x180157a8c  mov     dword ptr [rsp+100h+Size], r15d; Size
0x180157a91  mov     dword ptr [rsp+100h+var_D8], r12d; int
0x180157a96  mov     word ptr [rsp+100h+var_E0], r15w; int
0x180157a9c  mov     r9d, 101h; int
0x180157aa2  lea     rdx, [rbp+57h+var_C0]; int
0x180157aa6  mov     r8, r13; int
0x180157aa9  mov     rcx, rdi; int
0x180157aac  call    TIFFWriteDirectoryTagData
0x180157ab1  test    eax, eax
0x180157ab3  jz      loc_180159A99
0x180157ab9  jmp     short loc_180157AC1
0x180157abb  mov     r14d, 3
0x180157ac1  test    byte ptr [rdi+48h], 4
0x180157ac5  jz      loc_180157BFD
0x180157acb  mov     eax, [rdi+64h]
0x180157ace  cmp     eax, 0FFFFh
0x180157ad3  ja      short loc_180157B0F
0x180157ad5  test    r13, r13
0x180157ad8  jnz     short loc_180157AE2
0x180157ada  inc     [rbp+57h+var_C0]
0x180157add  mov     eax, r12d
0x180157ae0  jmp     short loc_180157B5C
0x180157ae2  test    byte ptr [rdi+10h], 80h
0x180157ae6  mov     word ptr [rbp+57h+Src], ax
0x180157aea  jz      short loc_180157AF5
0x180157aec  lea     rcx, [rbp+57h+Src]
0x180157af0  call    TIFFSwabShort
0x180157af5  lea     rax, [rbp+57h+Src]
0x180157af9  mov     [rsp+38h], rax
0x180157afe  mov     dword ptr [rsp+100h+Size], esi
0x180157b02  mov     dword ptr [rsp+100h+var_D8], r12d
0x180157b07  mov     word ptr [rsp+100h+var_E0], r14w
0x180157b0d  jmp     short loc_180157B47
0x180157b0f  test    r13, r13
0x180157b12  jnz     short loc_180157B1C
0x180157b14  inc     [rbp+57h+var_C0]
0x180157b17  mov     eax, r12d
0x180157b1a  jmp     short loc_180157B5C
0x180157b1c  test    byte ptr [rdi+10h], 80h
0x180157b20  mov     [rbp+57h+Src], eax
0x180157b23  jz      short loc_180157B2E
0x180157b25  lea     rcx, [rbp+57h+Src]
0x180157b29  call    TIFFSwabLong
0x180157b2e  lea     rax, [rbp+57h+Src]
0x180157b32  mov     [rsp+38h], rax; Src
0x180157b37  mov     dword ptr [rsp+100h+Size], r15d; Size
0x180157b3c  mov     dword ptr [rsp+100h+var_D8], r12d; int
0x180157b41  mov     word ptr [rsp+100h+var_E0], r15w; int
0x180157b47  mov     r9d, 142h; int
0x180157b4d  lea     rdx, [rbp+57h+var_C0]; int
0x180157b51  mov     r8, r13; int
0x180157b54  mov     rcx, rdi; int
0x180157b57  call    TIFFWriteDirectoryTagData
0x180157b5c  test    eax, eax
0x180157b5e  jz      loc_180159A99
0x180157b64  mov     eax, [rdi+68h]
0x180157b67  cmp     eax, 0FFFFh
0x180157b6c  ja      short loc_180157BA8
0x180157b6e  test    r13, r13
0x180157b71  jnz     short loc_180157B7B
0x180157b73  inc     [rbp+57h+var_C0]
0x180157b76  mov     eax, r12d
0x180157b79  jmp     short loc_180157BF5
0x180157b7b  test    byte ptr [rdi+10h], 80h
0x180157b7f  mov     word ptr [rbp+57h+Src], ax
0x180157b83  jz      short loc_180157B8E
0x180157b85  lea     rcx, [rbp+57h+Src]
0x180157b89  call    TIFFSwabShort
0x180157b8e  lea     rax, [rbp+57h+Src]
0x180157b92  mov     [rsp+38h], rax
0x180157b97  mov     dword ptr [rsp+100h+Size], esi
0x180157b9b  mov     dword ptr [rsp+100h+var_D8], r12d
0x180157ba0  mov     word ptr [rsp+100h+var_E0], r14w
0x180157ba6  jmp     short loc_180157BE0
0x180157ba8  test    r13, r13
0x180157bab  jnz     short loc_180157BB5
0x180157bad  inc     [rbp+57h+var_C0]
0x180157bb0  mov     eax, r12d
0x180157bb3  jmp     short loc_180157BF5
0x180157bb5  test    byte ptr [rdi+10h], 80h
0x180157bb9  mov     [rbp+57h+Src], eax
0x180157bbc  jz      short loc_180157BC7
0x180157bbe  lea     rcx, [rbp+57h+Src]
0x180157bc2  call    TIFFSwabLong
0x180157bc7  lea     rax, [rbp+57h+Src]
0x180157bcb  mov     [rsp+38h], rax; Src
0x180157bd0  mov     dword ptr [rsp+100h+Size], r15d; Size
0x180157bd5  mov     dword ptr [rsp+100h+var_D8], r12d; int
0x180157bda  mov     word ptr [rsp+100h+var_E0], r15w; int
0x180157be0  mov     r9d, 143h; int
0x180157be6  lea     rdx, [rbp+57h+var_C0]; int
0x180157bea  mov     r8, r13; int
0x180157bed  mov     rcx, rdi; int
0x180157bf0  call    TIFFWriteDirectoryTagData
0x180157bf5  test    eax, eax
0x180157bf7  jz      loc_180159A99
0x180157bfd  test    byte ptr [rdi+48h], 8
0x180157c01  jz      loc_180157D46
0x180157c07  movss   xmm0, dword ptr [rdi+0A0h]
0x180157c0f  cvtps2pd xmm0, xmm0
0x180157c12  comisd  xmm6, xmm0
0x180157c16  ja      loc_180159AB4
0x180157c1c  ucomisd xmm0, xmm0
0x180157c20  jp      loc_180159A83
0x180157c26  test    r13, r13
0x180157c29  jnz     short loc_180157C4B
0x180157c2b  mov     eax, [rdi+10h]
0x180157c2e  not     eax
0x180157c30  shr     rax, 10h
0x180157c34  and     eax, 8
0x180157c37  add     rax, [rbx]
0x180157c3a  mov     ebx, 5
0x180157c3f  inc     [rbp+57h+var_C0]
0x180157c42  mov     [rdi+1A0h], rax
0x180157c49  jmp     short loc_180157CAD
0x180157c4b  lea     r8, [rbp+57h+var_94]
0x180157c4f  lea     rdx, [rbp+57h+var_98]
0x180157c53  call    DoubleToRational
0x180157c58  test    byte ptr [rdi+10h], 80h
0x180157c5c  jz      short loc_180157C70
0x180157c5e  lea     rcx, [rbp+57h+var_98]
0x180157c62  call    TIFFSwabLong
0x180157c67  lea     rcx, [rbp+57h+var_94]
0x180157c6b  call    TIFFSwabLong
0x180157c70  lea     rax, [rbp+57h+var_98]
0x180157c74  mov     ebx, 5
  ... truncated ...
```
