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
  __int64 v116; // rdx
  __int64 v117; // r8
  __int64 v118; // r9
  unsigned int v119; // eax
  unsigned __int64 v120; // rcx
  __int64 v121; // rdx
  __int64 v122; // rax
  __int64 v123; // rax
  __int64 v124; // rdx
  __int64 v125; // rsi
  unsigned __int16 *v126; // r8
  unsigned __int64 v127; // kr08_8
  __int64 v128; // kr10_8
  int v129; // eax
  unsigned __int64 v130; // rax
  unsigned __int64 v131; // rax
  int v132; // eax
  unsigned __int64 v133; // rcx
  unsigned __int64 v134; // rax
  void *v135; // rsi
  unsigned __int64 v136; // rax
  unsigned __int64 v137; // rcx
  void *v138; // rsi
  void *v139; // rsi
  void *v140; // rsi
  bool v141; // zf
  int v142; // eax
  _QWORD *v143; // rsi
  unsigned int v144; // eax
  __int64 v145; // rax
  void *v146; // r14
  int v147; // r8d
  _DWORD *v148; // rcx
  unsigned int v149; // eax
  int v150; // eax
  __int64 *v151; // rsi
  __int64 v152; // rax
  int v153; // r8d
  _DWORD *v154; // rcx
  signed __int64 v155; // r9
  int v156; // edx
  __int64 v157; // r15
  __int64 v158; // rax
  __int64 v159; // rcx
  unsigned int v160; // r14d
  __int64 ii; // rsi
  unsigned __int64 v162; // rax
  unsigned __int64 v163; // rcx
  __int64 v164; // r15
  __int64 v165; // rax
  __int64 v166; // rcx
  unsigned int v167; // r14d
  __int64 jj; // rsi
  __int64 v169; // r15
  __int64 v170; // rax
  __int64 v171; // rcx
  unsigned int v172; // r14d
  __int64 kk; // rsi
  __int64 v174; // r15
  __int64 v175; // rax
  __int64 v176; // rcx
  unsigned int v177; // r14d
  __int64 mm; // rsi
  void *v179; // rsi
  void *v180; // rsi
  void *v181; // rsi
  __int64 v182; // rax
  unsigned __int64 v183; // rax
  unsigned __int64 v184; // rax
  const char *v185; // rdx
  const char *v186; // rbx
  int v187; // eax
  const char *v188; // r8
  const char *v189; // rdx
  int v190; // eax
  _WORD *v191; // rcx
  __int64 v192; // rcx
  __int64 v193; // rax
  __int64 v194; // rcx
  __int64 v195; // rdx
  __int64 v196; // r8
  __int64 v197; // r9
  _QWORD *v198; // r12
  char *v199; // rbx
  unsigned int v200; // r15d
  _WORD *v201; // rsi
  _WORD *v202; // r14
  __int64 v203; // rdx
  __int64 v204; // r8
  __int64 v205; // r9
  unsigned int v206; // r15d
  _WORD *v207; // rsi
  _WORD *v208; // r14
  __int64 v209; // rsi
  int v210; // eax
  int v211; // ebx
  int v212; // eax
  void (__fastcall *v213)(__int64); // rax
  int v214; // eax
  int v215; // [rsp+28h] [rbp-89h]
  int v216; // [rsp+30h] [rbp-81h]
  int v217; // [rsp+30h] [rbp-81h]
  size_t Size; // [rsp+38h] [rbp-79h]
  void *v219; // [rsp+40h] [rbp-71h]
  void *v220; // [rsp+40h] [rbp-71h]
  int v221; // [rsp+48h] [rbp-69h] BYREF
  int v222[2]; // [rsp+50h] [rbp-61h]
  unsigned int v223; // [rsp+58h] [rbp-59h]
  unsigned __int16 v224; // [rsp+5Ch] [rbp-55h] BYREF
  __int16 v225[2]; // [rsp+60h] [rbp-51h] BYREF
  int v226; // [rsp+64h] [rbp-4Dh]
  int v227; // [rsp+68h] [rbp-49h]
  _BYTE v228[4]; // [rsp+70h] [rbp-41h] BYREF
  _BYTE v229[4]; // [rsp+74h] [rbp-3Dh] BYREF
  _BYTE v230[4]; // [rsp+78h] [rbp-39h] BYREF
  _BYTE v231[4]; // [rsp+7Ch] [rbp-35h] BYREF
  _BYTE v232[4]; // [rsp+80h] [rbp-31h] BYREF
  _BYTE v233[4]; // [rsp+84h] [rbp-2Dh] BYREF
  _BYTE v234[4]; // [rsp+88h] [rbp-29h] BYREF
  _BYTE v235[4]; // [rsp+8Ch] [rbp-25h] BYREF
  unsigned int v236; // [rsp+90h] [rbp-21h] BYREF
  int v237; // [rsp+94h] [rbp-1Dh] BYREF
  void *v238[2]; // [rsp+98h] [rbp-19h] BYREF
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
  *(_QWORD *)v222 = 0;
  v223 = 0;
  while ( 1 )
  {
    v221 = 0;
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
          v141 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 88);
          if ( !v141 )
            TIFFSwabLong(&Src, v8, v10, 8);
          LODWORD(Size) = 4;
          LOWORD(v215) = 4;
          v16 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 256, v215, 1, Size, &Src);
        }
        else
        {
          v221 = 1;
          v16 = 1;
        }
      }
      else if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 88);
        if ( !v141 )
          TIFFSwabShort(&Src, v8, v10, 8);
        LODWORD(Size) = 2;
        LOWORD(v215) = 3;
        v16 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 256, v215, 1, Size, &Src);
      }
      else
      {
        v221 = 1;
        v16 = 1;
      }
      if ( !v16 )
        goto LABEL_522;
      if ( *(_DWORD *)(a1 + 92) > 0xFFFFu )
      {
        if ( v14 )
        {
          v141 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 92);
          if ( !v141 )
            TIFFSwabLong(&Src, v8, v10, v15);
          LODWORD(Size) = 4;
          LOWORD(v215) = 4;
          v17 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 257, v215, 1, Size, &Src);
        }
        else
        {
          ++v221;
          v17 = 1;
        }
      }
      else if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 92);
        if ( !v141 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v215) = 3;
        v17 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 257, v215, 1, Size, &Src);
      }
      else
      {
        ++v221;
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
          v141 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 100);
          if ( !v141 )
            TIFFSwabLong(&Src, v8, v10, v15);
          LODWORD(Size) = 4;
          LOWORD(v215) = 4;
          v18 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 322, v215, 1, Size, &Src);
        }
        else
        {
          ++v221;
          v18 = 1;
        }
      }
      else if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 100);
        if ( !v141 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v215) = 3;
        v18 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 322, v215, 1, Size, &Src);
      }
      else
      {
        ++v221;
        v18 = 1;
      }
      if ( !v18 )
        goto LABEL_522;
      if ( *(_DWORD *)(a1 + 104) > 0xFFFFu )
      {
        if ( v14 )
        {
          v141 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 104);
          if ( !v141 )
            TIFFSwabLong(&Src, v8, v10, v15);
          LODWORD(Size) = 4;
          LOWORD(v215) = 4;
          v19 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 323, v215, 1, Size, &Src);
        }
        else
        {
          ++v221;
          v19 = 1;
        }
      }
      else if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 104);
        if ( !v141 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v215) = 3;
        v19 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 323, v215, 1, Size, &Src);
      }
      else
      {
        ++v221;
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
        DoubleToRational(v9, v228, v229);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v228, v21, v22, v23);
          TIFFSwabLong(v229, v24, v25, v26);
        }
        LODWORD(Size) = 8;
        LOWORD(v215) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 282, v215, 1, Size, v228) )
          goto LABEL_523;
      }
      else
      {
        v20 = *(_QWORD *)v13 + (((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8);
        ++v221;
        *(_QWORD *)(a1 + 416) = v20;
      }
      if ( *(float *)(a1 + 164) < 0.0 )
        goto LABEL_524;
      if ( v14 )
      {
        DoubleToRational(v9, v230, v231);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v230, v27, v28, v29);
          TIFFSwabLong(v231, v30, v31, v32);
        }
        LODWORD(Size) = 8;
        LOWORD(v215) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 283, v215, 1, Size, v230) )
          goto LABEL_523;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v221;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x10) != 0 )
    {
      if ( *(float *)(a1 + 172) < 0.0 )
        goto LABEL_524;
      if ( v14 )
      {
        DoubleToRational(v9, v232, v233);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v232, v33, v34, v35);
          TIFFSwabLong(v233, v36, v37, v38);
        }
        LODWORD(Size) = 8;
        LOWORD(v215) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 286, v215, 1, Size, v232) )
          goto LABEL_523;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v221;
      }
      if ( *(float *)(a1 + 176) < 0.0 )
      {
LABEL_524:
        TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRational", "Negative value is illegal");
        goto LABEL_522;
      }
      if ( v14 )
      {
        DoubleToRational(v9, v234, v235);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v234, v39, v40, v41);
          TIFFSwabLong(v235, v42, v43, v44);
        }
        LODWORD(Size) = 8;
        LOWORD(v215) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 287, v215, 1, Size, v234) )
          goto LABEL_523;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v221;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x20) != 0 )
    {
      if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 112);
        if ( !v141 )
          TIFFSwabLong(&Src, v8, v10, v15);
        LODWORD(Size) = 4;
        LOWORD(v215) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 254, v215, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v221;
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
        LOWORD(v215) = 3;
        v53 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 258, v215, v52, Size, v48);
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
        ++v221;
      }
    }
    if ( *(char *)(a1 + 72) < 0 )
    {
      if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 120);
        if ( !v141 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v215) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 259, v215, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v221;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x100) != 0 )
    {
      if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 122);
        if ( !v141 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v215) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 262, v215, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v221;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x200) != 0 )
    {
      if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 124);
        if ( !v141 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v215) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 263, v215, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v221;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x400) != 0 )
    {
      if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 126);
        if ( !v141 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v215) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 266, v215, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v221;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x8000) != 0 )
    {
      if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 128);
        if ( !v141 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v215) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 274, v215, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v221;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x10000) != 0 )
    {
      if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 130);
        if ( !v141 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v215) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 277, v215, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v221;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x20000) != 0 )
    {
      if ( *(_DWORD *)(a1 + 132) > 0xFFFFu )
      {
        if ( v14 )
        {
          v141 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 132);
          if ( !v141 )
            TIFFSwabLong(&Src, v8, v10, v15);
          LODWORD(Size) = 4;
          LOWORD(v215) = 4;
          v54 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 278, v215, 1, Size, &Src);
        }
        else
        {
          ++v221;
          v54 = 1;
        }
      }
      else if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 132);
        if ( !v141 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v215) = 3;
        v54 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 278, v215, 1, Size, &Src);
      }
      else
      {
        ++v221;
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
        LOWORD(v215) = 3;
        v63 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 280, v215, v62, Size, v58);
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
        ++v221;
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
        LOWORD(v215) = 3;
        v72 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 281, v215, v71, Size, v67);
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
        ++v221;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x100000) != 0 )
    {
      if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 170);
        if ( !v141 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v215) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 284, v215, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v221;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x400000) != 0 )
    {
      if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 168);
        if ( !v141 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v215) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 296, v215, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v221;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x800000) != 0 )
    {
      if ( v14 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 180, 2, v10);
        LODWORD(Size) = 4;
        LOWORD(v215) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 297, v215, 2, Size, (void *)(a1 + 180)) )
          goto LABEL_523;
      }
      else
      {
        ++v221;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x1000000) != 0
      && !(unsigned int)TIFFWriteDirectoryTagLongLong8Array(
                          a1,
                          (int)&v221,
                          (int)v14,
                          *(_DWORD *)(a1 + 228),
                          *(void **)(a1 + 240))
      || (*(_DWORD *)(a1 + 72) & 0x2000000) != 0
      && ((*(_DWORD *)(a1 + 16) & 0x400) != 0 || *(_QWORD *)(a1 + 232))
      && !(unsigned int)TIFFWriteDirectoryTagLongLong8Array(
                          a1,
                          (int)&v221,
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
          v185 = "TIFFWriteDirectoryTagColormap";
          goto LABEL_556;
        }
        TIFFmemcpy(v75, *(const void **)(a1 + 184), 2 * v73);
        TIFFmemcpy(&v76[2 * v73], *(const void **)(a1 + 192), 2 * v73);
        TIFFmemcpy(&v76[2 * (unsigned int)(2 * v73)], *(const void **)(a1 + 200), 2 * v73);
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v76, (unsigned int)(3 * v73), v77);
        LODWORD(Size) = 6 * v73;
        LOWORD(v215) = 3;
        v78 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 320, v215, 3 * (int)v73, Size, v76);
        TIFFfreeExt(a1, v76);
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
        ++v221;
        v7 = 1;
      }
    }
    if ( *(int *)(a1 + 72) < 0 && *(_WORD *)(a1 + 212) )
    {
      TIFFGetFieldDefaulted(a1, 338, &v224, v238);
      v79 = v224;
      v80 = *(_DWORD *)(a1 + 16);
      if ( v14 )
      {
        v84 = v238[0];
        if ( (v80 & 0x80u) != 0 )
          TIFFSwabArrayOfShort(v238[0], v224, v10);
        LODWORD(Size) = 2 * v79;
        LOWORD(v215) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 338, v215, v79, Size, v84) )
          goto LABEL_523;
      }
      else
      {
        v81 = 2LL * v224;
        v82 = (v80 & 0x80000) != 0;
        v83 = 4;
        if ( v82 )
          v83 = 8;
        if ( v81 > v83 )
          *(_QWORD *)(a1 + 416) += v81;
        ++v221;
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
          v185 = "TIFFWriteDirectoryTagShortPerSample";
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
        LOWORD(v215) = 3;
        v93 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 339, v215, v92, Size, v88);
        TIFFfreeExt(a1, v88);
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
        ++v221;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 2) != 0
      && !(unsigned int)TIFFWriteDirectoryTagSampleformatArray(
                          a1,
                          (int)&v221,
                          (int)v14,
                          *(unsigned __int16 *)(a1 + 130),
                          *(void **)(a1 + 144))
      || (*(_BYTE *)(a1 + 76) & 4) != 0
      && !(unsigned int)TIFFWriteDirectoryTagSampleformatArray(
                          a1,
                          (int)&v221,
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
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 96);
        if ( !v141 )
          TIFFSwabLong(&Src, v8, v10, v15);
        LODWORD(Size) = 4;
        LOWORD(v215) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 32997, v215, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v221;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 0x10) != 0 )
    {
      if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 108);
        if ( !v141 )
          TIFFSwabLong(&Src, v8, v10, v15);
        LODWORD(Size) = 4;
        LOWORD(v215) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 32998, v215, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v221;
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
        LOWORD(v215) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 321, v215, 2, Size, (void *)(a1 + 208)) )
          goto LABEL_523;
        goto LABEL_275;
      }
      ++v221;
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
        LOWORD(v215) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 530, v215, 2, Size, (void *)(a1 + 336)) )
          goto LABEL_523;
      }
      else
      {
        ++v221;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x100) != 0 )
    {
      if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 340);
        if ( !v141 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v215) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 531, v215, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v221;
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
          v185 = "TIFFWriteDirectoryTagCheckedRationalArray";
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
        LOWORD(v215) = 5;
        v102 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 532, v215, 6, Size, v96);
        TIFFfreeExt(a1, v96);
        if ( !v102 )
          goto LABEL_523;
        v13 = 3;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += 48LL;
        ++v221;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x1000) != 0
      && !(unsigned int)TIFFWriteDirectoryTagTransferfunction(a1, (int)&v221, (int)v14) )
    {
      goto LABEL_522;
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x4000) != 0 )
    {
      v103 = *(unsigned int *)(a1 + 376);
      if ( v14 )
      {
        LODWORD(Size) = *(_DWORD *)(a1 + 376);
        LOWORD(v215) = 2;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(
                              a1,
                              (int)&v221,
                              (int)v14,
                              333,
                              v215,
                              v103,
                              Size,
                              *(void **)(a1 + 384)) )
          goto LABEL_523;
      }
      else
      {
        v104 = 4;
        v8 = (unsigned int)v103;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v104 = 8;
        if ( v103 > v104 )
        {
          v105 = v103 + 1;
          if ( (v103 & 1) == 0 )
            v105 = *(unsigned int *)(a1 + 376);
          *(_QWORD *)(a1 + 416) += v105;
        }
        ++v221;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x40000) != 0 )
    {
      if ( v14 )
      {
        v141 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 392);
        if ( !v141 )
          TIFFSwabShort(&Src, v8, v10, v15);
        LODWORD(Size) = 2;
        LOWORD(v215) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, 334, v215, 1, Size, &Src) )
          goto LABEL_523;
      }
      else
      {
        ++v221;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x20000) != 0 && !(unsigned int)TIFFWriteDirectoryTagSubifd(a1, (int)&v221, (int)v14) )
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
              v119 = strlen_0(Str);
              if ( v14 )
              {
                LODWORD(Size) = v119;
                LOWORD(v215) = 2;
                v112 = TIFFWriteDirectoryTagData(
                         a1,
                         (int)&v221,
                         (int)v14,
                         *(unsigned __int16 *)v107,
                         v215,
                         v119,
                         Size,
                         (void *)v13);
                goto LABEL_356;
              }
              v120 = 4;
              v121 = v119;
              if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                v120 = 8;
              if ( v119 > v120 )
              {
                v141 = (v119 & 1) == 0;
                v122 = v119 + 1LL;
                if ( v141 )
                  v122 = v121;
                *(_QWORD *)(a1 + 416) += v122;
              }
              ++v221;
              break;
            case 4u:
              TIFFGetField(a1, *v107, v225);
              if ( v14 )
              {
                v141 = *(_BYTE *)(a1 + 16) >= 0;
                v13 = *(unsigned __int16 *)v107;
                LOWORD(Src) = v225[0];
                if ( !v141 )
                  TIFFSwabShort(&Src, v116, v117, v118);
                LODWORD(Size) = 2;
                LOWORD(v215) = 3;
                v112 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, (unsigned __int16)v13, v215, 1, Size, &Src);
LABEL_356:
                if ( !v112 )
                  goto LABEL_523;
                continue;
              }
              ++v221;
              break;
            case 6u:
              TIFFGetField(a1, *v107, &v237);
              if ( v14 )
              {
                v141 = *(_BYTE *)(a1 + 16) >= 0;
                v13 = *(unsigned __int16 *)v107;
                Src = v237;
                if ( !v141 )
                  TIFFSwabLong(&Src, v113, v114, v115);
                LODWORD(Size) = 4;
                LOWORD(v215) = 4;
                v112 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, (unsigned __int16)v13, v215, 1, Size, &Src);
                goto LABEL_356;
              }
              ++v221;
              break;
            case 0x28u:
              TIFFGetField(a1, *v107, &v236);
              if ( v14 )
              {
                LODWORD(Size) = v236;
                LOWORD(v215) = 7;
                v112 = TIFFWriteDirectoryTagData(
                         a1,
                         (int)&v221,
                         (int)v14,
                         *(unsigned __int16 *)v107,
                         v215,
                         v236,
                         Size,
                         v238[1]);
                goto LABEL_356;
              }
              v110 = 4;
              if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                v110 = 8;
              if ( v236 > v110 )
              {
                v111 = v236 + 1LL;
                if ( (v236 & 1) == 0 )
                  v111 = v236;
                *(_QWORD *)(a1 + 416) += v111;
              }
              ++v221;
              break;
            default:
              v186 = "unknown";
              if ( *((_QWORD *)v107 + 4) )
                v186 = (const char *)*((_QWORD *)v107 + 4);
              v187 = TIFFFieldTag(v107);
              TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Cannot write tag %u (%s)", v187, v186);
              goto LABEL_522;
          }
        }
      }
    }
LABEL_358:
    v123 = 0;
    v227 = 0;
    if ( *(_DWORD *)(a1 + 396) )
    {
      while ( 1 )
      {
        v124 = *(_QWORD *)(a1 + 400);
        v125 = 3 * v123;
        v126 = *(unsigned __int16 **)(v124 + 24 * v123);
        v127 = v13;
        v128 = v7;
        v7 = *v126;
        v13 = *(unsigned int *)(v124 + 24 * v123 + 8);
        v129 = *((_DWORD *)v126 + 2) - 1;
        LOWORD(Src) = *v126;
        switch ( v129 )
        {
          case 0:
            if ( !v14 )
              goto LABEL_361;
            LODWORD(Size) = v13;
            LOWORD(v215) = 1;
            v132 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v221,
                     (int)v14,
                     (unsigned __int16)v7,
                     v215,
                     v13,
                     Size,
                     *(void **)(v124 + 8 * v125 + 16));
            goto LABEL_369;
          case 1:
            if ( !v14 )
              goto LABEL_361;
            LODWORD(Size) = v13;
            LOWORD(v215) = 2;
            v132 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v221,
                     (int)v14,
                     (unsigned __int16)v7,
                     v215,
                     v13,
                     Size,
                     *(void **)(v124 + 8 * v125 + 16));
            goto LABEL_369;
          case 2:
            if ( !v14 )
            {
              v133 = 2 * v13;
              goto LABEL_379;
            }
            v135 = *(void **)(v124 + 8 * v125 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfShort(v135, v13, v126);
            LODWORD(Size) = 2 * v13;
            LOWORD(v215) = 3;
            v132 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, (unsigned __int16)v7, v215, v13, Size, v135);
            goto LABEL_369;
          case 3:
            if ( !v14 )
            {
              v133 = 4 * v13;
              goto LABEL_379;
            }
            v139 = *(void **)(v124 + 8 * v125 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v139, v13);
            LODWORD(Size) = 4 * v13;
            LOWORD(v215) = 4;
            v132 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, (unsigned __int16)v7, v215, v13, Size, v139);
            goto LABEL_369;
          case 4:
            v226 = TIFFFieldSetGetSize(v126);
            v156 = v226;
            if ( v226 == 8 )
            {
              if ( !v14 )
                goto LABEL_440;
              v157 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v125 + 16);
              v158 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v13));
              v7 = v158;
              if ( !v158 )
              {
                TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRationalDoubleArray", "Out of memory");
                TIFFfreeExt(a1, *(_QWORD *)v222);
                return 0;
              }
              v160 = 0;
              for ( ii = v158; v160 < (unsigned int)v13; ++v160 )
              {
                DoubleToRational(v159, ii, ii + 4);
                ii += 8;
                v157 += 8;
              }
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v13));
              v219 = (void *)v7;
              LODWORD(Size) = 8 * v13;
              v216 = v13;
              LOWORD(v215) = 5;
              goto LABEL_447;
            }
            if ( !v14 )
              goto LABEL_450;
            v164 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v125 + 16);
            v165 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v13));
            v7 = v165;
            if ( !v165 )
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRationalArray", "Out of memory");
              TIFFfreeExt(a1, *(_QWORD *)v222);
              return 0;
            }
            v167 = 0;
            for ( jj = v165; v167 < (unsigned int)v13; ++v167 )
            {
              DoubleToRational(v166, jj, jj + 4);
              jj += 8;
              v164 += 4;
            }
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v13));
            v220 = (void *)v7;
            LODWORD(Size) = 8 * v13;
            v217 = v13;
            LOWORD(v215) = 5;
            goto LABEL_461;
          case 5:
            if ( !v14 )
              goto LABEL_361;
            LODWORD(Size) = v13;
            LOWORD(v215) = 6;
            v132 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v221,
                     (int)v14,
                     (unsigned __int16)v7,
                     v215,
                     v13,
                     Size,
                     *(void **)(v124 + 8 * v125 + 16));
            goto LABEL_369;
          case 6:
            if ( v14 )
            {
              LODWORD(Size) = v13;
              LOWORD(v215) = 7;
              v132 = TIFFWriteDirectoryTagData(
                       a1,
                       (int)&v221,
                       (int)v14,
                       (unsigned __int16)v7,
                       v215,
                       v13,
                       Size,
                       *(void **)(v124 + 8 * v125 + 16));
              goto LABEL_369;
            }
LABEL_361:
            v130 = 4;
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
              v130 = 8;
            if ( v13 > v130 )
            {
              v131 = v13 + 1;
              if ( (v13 & 1) == 0 )
                v131 = v13;
              *(_QWORD *)(a1 + 416) += v131;
            }
            goto LABEL_367;
          case 7:
            if ( v14 )
            {
              v138 = *(void **)(v124 + 8 * v125 + 16);
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfShort(v138, v13, v126);
              LODWORD(Size) = 2 * v13;
              LOWORD(v215) = 8;
              v132 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, (unsigned __int16)v7, v215, v13, Size, v138);
              goto LABEL_369;
            }
            v136 = 4;
            v137 = 2 * v13;
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
              v136 = 8;
            if ( v137 > v136 )
            {
              *(_QWORD *)(a1 + 416) += v137;
              ++v221;
              goto LABEL_497;
            }
            goto LABEL_367;
          case 8:
            if ( !v14 )
            {
              v133 = 4 * v13;
              goto LABEL_379;
            }
            v140 = *(void **)(v124 + 8 * v125 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v140, v13);
            LODWORD(Size) = 4 * v13;
            LOWORD(v215) = 9;
            v132 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, (unsigned __int16)v7, v215, v13, Size, v140);
            goto LABEL_369;
          case 9:
            v226 = TIFFFieldSetGetSize(v126);
            v156 = v226;
            if ( v226 == 8 )
            {
              if ( v14 )
              {
                v169 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v125 + 16);
                v170 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v13));
                v7 = v170;
                if ( !v170 )
                {
                  TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSrationalDoubleArray", "Out of memory");
                  TIFFfreeExt(a1, *(_QWORD *)v222);
                  return 0;
                }
                v172 = 0;
                for ( kk = v170; v172 < (unsigned int)v13; ++v172 )
                {
                  DoubleToSrational(v171, kk, kk + 4);
                  kk += 8;
                  v169 += 8;
                }
                if ( *(char *)(a1 + 16) < 0 )
                  TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v13));
                v219 = (void *)v7;
                LODWORD(Size) = 8 * v13;
                v216 = v13;
                LOWORD(v215) = 10;
LABEL_447:
                v14 = *(_WORD **)v222;
                v13 = (unsigned int)TIFFWriteDirectoryTagData(
                                      a1,
                                      (int)&v221,
                                      v222[0],
                                      (unsigned __int16)Src,
                                      v215,
                                      v216,
                                      Size,
                                      v219);
                TIFFfreeExt(a1, v7);
                if ( !(_DWORD)v13 )
                  goto LABEL_523;
              }
              else
              {
LABEL_440:
                v133 = 4LL * (unsigned int)(2 * v13);
LABEL_379:
                v134 = 4;
                if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                  v134 = 8;
                if ( v133 <= v134 )
                {
LABEL_367:
                  ++v221;
                }
                else
                {
                  *(_QWORD *)(a1 + 416) += v133;
                  ++v221;
                }
              }
            }
            else
            {
              if ( v14 )
              {
                v174 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v125 + 16);
                v175 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v13));
                v7 = v175;
                if ( !v175 )
                {
                  TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSrationalArray", "Out of memory");
                  TIFFfreeExt(a1, *(_QWORD *)v222);
                  return 0;
                }
                v177 = 0;
                for ( mm = v175; v177 < (unsigned int)v13; ++v177 )
                {
                  DoubleToSrational(v176, mm, mm + 4);
                  mm += 8;
                  v174 += 4;
                }
                if ( *(char *)(a1 + 16) < 0 )
                  TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v13));
                v220 = (void *)v7;
                LODWORD(Size) = 8 * v13;
                v217 = v13;
                LOWORD(v215) = 10;
LABEL_461:
                v14 = *(_WORD **)v222;
                v13 = (unsigned int)TIFFWriteDirectoryTagData(
                                      a1,
                                      (int)&v221,
                                      v222[0],
                                      (unsigned __int16)Src,
                                      v215,
                                      v217,
                                      Size,
                                      v220);
                TIFFfreeExt(a1, v7);
                if ( !(_DWORD)v13 )
                  goto LABEL_523;
                v156 = v226;
              }
              else
              {
LABEL_450:
                v162 = 4;
                v163 = 4LL * (unsigned int)(2 * v13);
                if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                  v162 = 8;
                if ( v163 > v162 )
                  *(_QWORD *)(a1 + 416) += v163;
                ++v221;
              }
              if ( v156 != 4 )
                TIFFErrorExtR(
                  a1,
                  "TIFFLib: _TIFFWriteDirectorySec()",
                  "Rational2Double: .set_field_type is not 4 but %d",
                  v156);
            }
            goto LABEL_497;
          case 10:
            if ( !v14 )
            {
              v133 = 4 * v13;
              goto LABEL_379;
            }
            v179 = *(void **)(v124 + 8 * v125 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v179, v13);
            LODWORD(Size) = 4 * v13;
            LOWORD(v215) = 11;
            v132 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, (unsigned __int16)v7, v215, v13, Size, v179);
            goto LABEL_369;
          case 11:
            if ( !v14 )
            {
              v133 = 8 * v13;
              goto LABEL_379;
            }
            v180 = *(void **)(v124 + 8 * v125 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfDouble(v180, v13, v126, 8);
            LODWORD(Size) = 8 * v13;
            LOWORD(v215) = 12;
            v132 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, (unsigned __int16)v7, v215, v13, Size, v180);
            goto LABEL_369;
          case 12:
            if ( !v14 )
            {
              v133 = 4 * v13;
              goto LABEL_379;
            }
            v181 = *(void **)(v124 + 8 * v125 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v181, v13);
            LODWORD(Size) = 4 * v13;
            LOWORD(v215) = 13;
            v132 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, (unsigned __int16)v7, v215, v13, Size, v181);
LABEL_369:
            if ( !v132 )
              goto LABEL_523;
            goto LABEL_497;
          case 15:
            if ( v14 )
            {
              v142 = *(_DWORD *)(a1 + 16);
              v143 = *(_QWORD **)(v124 + 8 * v125 + 16);
              if ( (v142 & 0x80000) != 0 )
              {
                if ( (v142 & 0x80u) != 0 )
                  TIFFSwabArrayOfDouble(v143, v13, v126, 8);
                LODWORD(Size) = 8 * v13;
                LOWORD(v215) = 16;
                v144 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, (unsigned __int16)v7, v215, v13, Size, v143);
LABEL_414:
                v13 = v144;
                v141 = v144 == 0;
                goto LABEL_496;
              }
              v145 = TIFFmallocExt(a1, 4 * v13);
              v146 = (void *)v145;
              if ( !v145 )
              {
                v185 = "TIFFWriteDirectoryTagLong8Array";
                goto LABEL_556;
              }
              v147 = 0;
              v148 = (_DWORD *)v145;
              if ( (_DWORD)v13 )
              {
                while ( *v143 <= 0xFFFFFFFF )
                {
                  *v148++ = *v143++;
                  if ( ++v147 >= (unsigned int)v13 )
                    goto LABEL_419;
                }
                v188 = "Attempt to write unsigned long value %llu larger than 0xFFFFFFFF for tag %d in Classic TIFF file."
                       " TIFF file writing aborted";
                v189 = "TIFFWriteDirectoryTagLong8Array";
LABEL_535:
                TIFFErrorExtR(a1, v189, v188);
                TIFFfreeExt(a1, v146);
                TIFFfreeExt(a1, v14);
                return 0;
              }
LABEL_419:
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v145, v13);
              LODWORD(Size) = 4 * v13;
              LOWORD(v215) = 4;
              v149 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, (unsigned __int16)v7, v215, v13, Size, v146);
LABEL_422:
              v13 = v149;
              TIFFfreeExt(a1, v146);
              v141 = (_DWORD)v13 == 0;
              goto LABEL_496;
            }
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) == 0 )
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedLong8Array", "LONG8 not allowed for ClassicTIFF", 8);
              v13 = 0;
              v141 = 1;
              goto LABEL_496;
            }
            goto LABEL_407;
          case 16:
            if ( v14 )
            {
              v150 = *(_DWORD *)(a1 + 16);
              v151 = *(__int64 **)(v124 + 8 * v125 + 16);
              if ( (v150 & 0x80000) != 0 )
              {
                if ( (v150 & 0x80u) != 0 )
                  TIFFSwabArrayOfDouble(v151, v13, v126, 8);
                LODWORD(Size) = 8 * v13;
                LOWORD(v215) = 17;
                v144 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, (unsigned __int16)v7, v215, v13, Size, v151);
                goto LABEL_414;
              }
              v152 = TIFFmallocExt(a1, 4 * v13);
              v146 = (void *)v152;
              if ( !v152 )
              {
                v185 = "TIFFWriteDirectoryTagSlong8Array";
                goto LABEL_556;
              }
              v153 = 0;
              v154 = (_DWORD *)v152;
              if ( (_DWORD)v13 )
              {
                while ( 1 )
                {
                  v155 = *v151;
                  if ( *v151 > 0x7FFFFFFF )
                    break;
                  if ( v155 < (__int64)0xFFFFFFFF80000000uLL )
                  {
                    v188 = "Attempt to write signed long value %lli smaller than 0x80000000 (-2147483648) for tag %d in C"
                           "lassic TIFF file. TIFF writing to file aborted";
                    goto LABEL_534;
                  }
                  *v154 = v155;
                  ++v151;
                  ++v154;
                  if ( ++v153 >= (unsigned int)v13 )
                    goto LABEL_435;
                }
                v188 = "Attempt to write signed long value %lli larger than 0x7FFFFFFF (2147483647) for tag %d in Classic"
                       " TIFF file. TIFF writing to file aborted";
LABEL_534:
                v189 = "TIFFWriteDirectoryTagSlong8Array";
                goto LABEL_535;
              }
LABEL_435:
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v152, v13);
              LODWORD(Size) = 4 * v13;
              LOWORD(v215) = 9;
              v149 = TIFFWriteDirectoryTagData(a1, (int)&v221, (int)v14, (unsigned __int16)v7, v215, v13, Size, v146);
              goto LABEL_422;
            }
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
            {
LABEL_407:
              if ( 8 * v13 > 8 )
                *(_QWORD *)(a1 + 416) += 8 * v13;
              ++v221;
              v13 = 1;
              v141 = 0;
            }
            else
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSlong8Array", "SLONG8 not allowed for ClassicTIFF", 8);
              v13 = 0;
              v141 = 1;
            }
LABEL_496:
            if ( v141 )
              goto LABEL_522;
LABEL_497:
            v123 = (unsigned int)(v227 + 1);
            v227 = v123;
            if ( (unsigned int)v123 >= *(_DWORD *)(a1 + 396) )
              goto LABEL_498;
            break;
          case 17:
            v141 = (unsigned int)TIFFWriteDirectoryTagIfdIfd8Array(
                                   a1,
                                   (int)&v221,
                                   (int)v14,
                                   v13,
                                   *(void **)(v124 + 8 * v125 + 16)) == 0;
            goto LABEL_496;
          default:
            v7 = v128;
            v13 = v127;
            goto LABEL_497;
        }
      }
    }
LABEL_498:
    if ( v14 )
      break;
    v13 = a1 + 416;
    if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
      v182 = (unsigned int)(20 * v221 + 16);
    else
      v182 = (unsigned int)(12 * v221 + 6);
    *(_QWORD *)v13 = *(_QWORD *)(a1 + 416) + v182;
    *(_QWORD *)v222 = TIFFmallocExt(a1, 32LL * (unsigned int)v221);
    v14 = *(_WORD **)v222;
    if ( !*(_QWORD *)v222 )
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
          TIFFfreeExt(a1, *(_QWORD *)v222);
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
      v183 = *(_QWORD *)(a1 + 424);
      if ( !v183 || *(_QWORD *)v13 > v183 )
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
      v10 = (unsigned int)(20 * v221 + 16);
      v184 = v10 + v8;
    }
    else
    {
      v10 = (unsigned int)(12 * v221 + 6);
      v184 = (unsigned int)(v8 + v10);
    }
    *(_QWORD *)(a1 + 880) = v184;
    v9 = (unsigned int)v10;
    v223 = v10;
    if ( v184 < v8 || v184 < (unsigned int)v10 )
    {
      TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Maximum TIFF file size exceeded");
      TIFFfreeExt(a1, v14);
      return 0;
    }
    if ( (v184 & 1) != 0 )
      *(_QWORD *)(a1 + 880) = v184 + 1;
    v7 = 1;
  }
  if ( !v241 || (*(_DWORD *)(a1 + 76) & 0x20000) == 0 || *(_QWORD *)(a1 + 896) )
    goto LABEL_554;
  v190 = 0;
  v191 = v14;
  if ( !v221 )
  {
LABEL_550:
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Cannot find SubIFD tag", 8);
    TIFFfreeExt(a1, v14);
    return 0;
  }
  while ( *v191 != 330 )
  {
    ++v190;
    v191 += 16;
    if ( v190 == v221 )
      goto LABEL_550;
  }
  v192 = *(_QWORD *)(a1 + 24);
  if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
  {
    v193 = (unsigned int)(20 * v190);
    v194 = v192 + 20;
  }
  else
  {
    v193 = (unsigned int)(12 * v190);
    v194 = v192 + 10;
  }
  *(_QWORD *)(a1 + 896) = v193 + v194;
LABEL_554:
  v198 = (_QWORD *)TIFFmallocExt(a1, v223);
  if ( !v198 )
  {
    v185 = "TIFFWriteDirectorySec";
LABEL_556:
    TIFFErrorExtR(a1, v185, "Out of memory");
    goto LABEL_523;
  }
  v199 = (char *)(a1 + 16);
  if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
  {
    *v198 = (unsigned int)v221;
    if ( *v199 < 0 )
      TIFFSwabLong8(v198);
    v206 = 0;
    v207 = v198 + 1;
    v208 = v14;
    if ( v221 )
    {
      do
      {
        *v207 = *v208;
        if ( *v199 < 0 )
          TIFFSwabShort(v207, v195, v196, v197);
        v207[1] = v208[1];
        if ( *v199 < 0 )
          TIFFSwabShort(v207 + 1, v195, v196, v197);
        TIFFmemcpy(v207 + 2, v208 + 4, 8u);
        if ( *v199 < 0 )
          TIFFSwabLong8(v207 + 2);
        TIFFmemcpy(v207 + 6, v208 + 8, 8u);
        v207 += 10;
        v208 += 16;
        ++v206;
      }
      while ( v206 < v221 );
      v14 = *(_WORD **)v222;
      v199 = (char *)(a1 + 16);
    }
    TIFFmemcpy(v207, (const void *)(a1 + 32), 8u);
    if ( *v199 < 0 )
      TIFFSwabLong8(v207);
  }
  else
  {
    *(_WORD *)v198 = v221;
    if ( *v199 < 0 )
      TIFFSwabShort(v198, v195, v196, v197);
    v200 = 0;
    v201 = (_WORD *)v198 + 1;
    v202 = v14;
    if ( v221 )
    {
      do
      {
        *v201 = *v202;
        if ( *v199 < 0 )
          TIFFSwabShort(v201, v195, v196, v197);
        v201[1] = v202[1];
        if ( *v199 < 0 )
          TIFFSwabShort(v201 + 1, v195, v196, v197);
        Src = *((_DWORD *)v202 + 2);
        TIFFmemcpy(v201 + 2, &Src, 4u);
        if ( *v199 < 0 )
          TIFFSwabLong(v201 + 2, v203, v204, v205);
        TIFFmemcpy(v201 + 4, v202 + 8, 4u);
        v201 += 6;
        v202 += 16;
        ++v200;
      }
      while ( v200 < v221 );
      v14 = *(_WORD **)v222;
      v199 = (char *)(a1 + 16);
    }
    v141 = *v199 >= 0;
    Src = *(_DWORD *)(a1 + 32);
    if ( !v141 )
      TIFFSwabLong(&Src, v195, v196, v197);
    TIFFmemcpy(v201, &Src, 4u);
    v199 = (char *)(a1 + 16);
  }
  TIFFfreeExt(a1, v14);
  if ( !(unsigned int)TIFFSeekOK(a1, *(_QWORD *)(a1 + 24)) )
  {
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "IO error writing directory at seek to offset");
    TIFFfreeExt(a1, v198);
    return 0;
  }
  v209 = v223;
  if ( (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD))(a1 + 1192))(*(_QWORD *)(a1 + 1176), v198, v223) != v209 )
  {
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "IO error writing directory");
    TIFFfreeExt(a1, v198);
    return 0;
  }
  TIFFfreeExt(a1, v198);
  if ( !v241 || *(_BYTE *)(a1 + 409) )
  {
LABEL_600:
    v211 = v242;
    *(_BYTE *)(a1 + 409) = 1;
    if ( v211 )
    {
      v212 = *(_DWORD *)(a1 + 16);
      if ( (v212 & 0x2000) != 0 && !*(_WORD *)(a1 + 888) )
        *(_DWORD *)(a1 + 16) = v212 & 0xFFFFDFFF;
    }
    if ( !(unsigned int)TIFFCheckDirNumberAndOffset(a1, *(unsigned int *)(a1 + 848), *(_QWORD *)(a1 + 24)) )
      TIFFErrorExtR(
        a1,
        "TIFFWriteDirectorySec",
        "Starting directory %u at offset 0x%llx (%llu) might cause an IFD loop",
        *(_DWORD *)(a1 + 848),
        *(_QWORD *)(a1 + 24),
        *(_QWORD *)(a1 + 24));
    if ( v211 )
    {
      TIFFFreeDirectory(a1);
      v213 = *(void (__fastcall **)(__int64))(a1 + 1048);
      *(_DWORD *)(a1 + 16) &= 0xFFDFFFF7;
      v213(a1);
      TIFFCreateDirectory(a1);
    }
    else
    {
      *(_QWORD *)(a1 + 424) = *(_QWORD *)(a1 + 416);
    }
    return 1;
  }
  if ( (*(_DWORD *)v199 & 0x2000) != 0 && (*(_DWORD *)(a1 + 76) & 0x20000) == 0 )
  {
    v210 = 0;
    goto LABEL_597;
  }
  v210 = *(_DWORD *)(a1 + 852);
  if ( v210 != -1 )
  {
LABEL_597:
    *(_DWORD *)(a1 + 848) = v210;
    if ( (*(_DWORD *)(a1 + 16) & 0x2000) == 0 || (*(_DWORD *)(a1 + 76) & 0x20000) != 0 )
      ++*(_DWORD *)(a1 + 852);
    goto LABEL_600;
  }
  v214 = TIFFNumberOfDirectories(a1);
  *(_DWORD *)(a1 + 852) = v214;
  *(_DWORD *)(a1 + 848) = v214;
  TIFFErrorExtR(
    a1,
    "TIFFWriteDirectorySec",
    "tif_curdircount is TIFF_NON_EXISTENT_DIR_NUMBER, not expected !! Line %d",
    1330);
  TIFFfreeExt(a1, v198);
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
