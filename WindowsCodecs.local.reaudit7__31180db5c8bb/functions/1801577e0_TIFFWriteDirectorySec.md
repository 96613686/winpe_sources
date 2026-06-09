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
  __int64 v10; // r9
  const char *v11; // r8
  __int64 v13; // rdx
  unsigned __int64 v14; // rbx
  _WORD *v15; // r13
  __int64 v16; // r9
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rax
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rax
  __int16 v24; // bx
  __int64 v25; // rax
  __int64 v26; // r9
  void *v27; // rsi
  unsigned __int16 v28; // r9
  unsigned __int16 v29; // r8
  _WORD *i; // rdx
  int v31; // ebx
  int v32; // ebx
  int v33; // eax
  unsigned __int64 v34; // rdx
  unsigned __int64 v35; // rax
  __int16 v36; // bx
  __int64 v37; // rax
  void *v38; // rsi
  unsigned __int16 v39; // r9
  unsigned __int16 v40; // r8
  _WORD *j; // rdx
  int v42; // ebx
  int v43; // ebx
  unsigned __int64 v44; // rdx
  unsigned __int64 v45; // rax
  __int16 v46; // bx
  __int64 v47; // rax
  void *v48; // rsi
  unsigned __int16 v49; // r9
  unsigned __int16 v50; // r8
  _WORD *k; // rdx
  int v52; // ebx
  int v53; // ebx
  __int64 v54; // r14
  unsigned __int64 v55; // rdx
  unsigned __int64 v56; // rax
  char *v57; // rax
  char *v58; // rsi
  int v59; // ebx
  int v60; // ebx
  int v61; // eax
  unsigned __int64 v62; // rcx
  bool v63; // cf
  unsigned __int64 v64; // rax
  void *v65; // rsi
  unsigned __int64 v66; // rdx
  unsigned __int64 v67; // rax
  __int16 v68; // bx
  __int64 v69; // rax
  void *v70; // rsi
  unsigned __int16 v71; // r9
  unsigned __int16 v72; // r8
  _WORD *m; // rdx
  int v74; // ebx
  int v75; // ebx
  __int64 v76; // rax
  __int64 v77; // rcx
  char *v78; // rsi
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  int v84; // ebx
  unsigned __int64 v85; // rcx
  unsigned __int64 v86; // rax
  unsigned __int64 v87; // rax
  __int64 n; // r14
  unsigned int *v89; // rsi
  unsigned __int16 v90; // dx
  int v91; // eax
  unsigned __int64 v92; // rax
  __int64 v93; // rax
  int v94; // eax
  unsigned int v95; // eax
  unsigned __int64 v96; // rcx
  __int64 v97; // rdx
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rdx
  __int64 v101; // rsi
  unsigned __int16 *v102; // r8
  unsigned __int64 v103; // kr08_8
  __int64 v104; // kr10_8
  int v105; // eax
  unsigned __int64 v106; // rax
  unsigned __int64 v107; // rax
  int v108; // eax
  unsigned __int64 v109; // rcx
  unsigned __int64 v110; // rax
  void *v111; // rsi
  unsigned __int64 v112; // rax
  unsigned __int64 v113; // rcx
  void *v114; // rsi
  void *v115; // rsi
  void *v116; // rsi
  bool v117; // zf
  int v118; // eax
  _QWORD *v119; // rsi
  unsigned int v120; // eax
  __int64 v121; // rax
  void *v122; // r14
  int v123; // r8d
  _DWORD *v124; // rcx
  signed __int64 v125; // r9
  unsigned int v126; // eax
  int v127; // eax
  __int64 *v128; // rsi
  __int64 v129; // rax
  int v130; // r8d
  _DWORD *v131; // rcx
  unsigned int v132; // edx
  __int64 v133; // r15
  __int64 v134; // rax
  __int64 v135; // rcx
  __int64 v136; // r9
  unsigned int v137; // r14d
  __int64 ii; // rsi
  unsigned __int64 v139; // rax
  unsigned __int64 v140; // rcx
  __int64 v141; // r15
  __int64 v142; // rax
  __int64 v143; // rcx
  __int64 v144; // r9
  unsigned int v145; // r14d
  __int64 jj; // rsi
  __int64 v147; // r15
  __int64 v148; // rax
  __int64 v149; // rcx
  __int64 v150; // r9
  unsigned int v151; // r14d
  __int64 kk; // rsi
  __int64 v153; // r15
  __int64 v154; // rax
  __int64 v155; // rcx
  __int64 v156; // r9
  unsigned int v157; // r14d
  __int64 mm; // rsi
  void *v159; // rsi
  void *v160; // rsi
  void *v161; // rsi
  __int64 v162; // rax
  unsigned __int64 v163; // rax
  unsigned __int64 v164; // rdx
  __int64 v165; // r8
  unsigned __int64 v166; // rax
  const char *v167; // rdx
  unsigned int v168; // eax
  const char *v169; // r8
  const char *v170; // rdx
  int v171; // eax
  _WORD *v172; // rcx
  __int64 v173; // rcx
  __int64 v174; // rax
  __int64 v175; // rcx
  _QWORD *v176; // r12
  char *v177; // rbx
  unsigned int v178; // r15d
  _WORD *v179; // rsi
  _WORD *v180; // r14
  unsigned int v181; // r15d
  _WORD *v182; // rsi
  _WORD *v183; // r14
  __int64 v184; // r9
  __int64 v185; // rsi
  __int64 v186; // r9
  int v187; // eax
  int v188; // ebx
  int v189; // eax
  void (__fastcall *v190)(__int64); // rax
  int v191; // eax
  int v192; // [rsp+28h] [rbp-89h]
  int v193; // [rsp+30h] [rbp-81h]
  int v194; // [rsp+30h] [rbp-81h]
  size_t Size; // [rsp+38h] [rbp-79h]
  void *v196; // [rsp+40h] [rbp-71h]
  void *v197; // [rsp+40h] [rbp-71h]
  int v198; // [rsp+48h] [rbp-69h] BYREF
  int v199[2]; // [rsp+50h] [rbp-61h]
  unsigned int v200; // [rsp+58h] [rbp-59h]
  unsigned __int16 v201; // [rsp+5Ch] [rbp-55h] BYREF
  __int16 v202[2]; // [rsp+60h] [rbp-51h] BYREF
  unsigned int v203; // [rsp+64h] [rbp-4Dh]
  int v204; // [rsp+68h] [rbp-49h]
  _BYTE v205[4]; // [rsp+70h] [rbp-41h] BYREF
  _BYTE v206[4]; // [rsp+74h] [rbp-3Dh] BYREF
  _BYTE v207[4]; // [rsp+78h] [rbp-39h] BYREF
  _BYTE v208[4]; // [rsp+7Ch] [rbp-35h] BYREF
  _BYTE v209[4]; // [rsp+80h] [rbp-31h] BYREF
  _BYTE v210[4]; // [rsp+84h] [rbp-2Dh] BYREF
  _BYTE v211[4]; // [rsp+88h] [rbp-29h] BYREF
  _BYTE v212[4]; // [rsp+8Ch] [rbp-25h] BYREF
  unsigned int v213; // [rsp+90h] [rbp-21h] BYREF
  int v214; // [rsp+94h] [rbp-1Dh] BYREF
  void *v215[2]; // [rsp+98h] [rbp-19h] BYREF
  char *Str; // [rsp+A8h] [rbp-9h] BYREF
  int Src; // [rsp+118h] [rbp+67h] BYREF
  int v218; // [rsp+120h] [rbp+6Fh]
  int v219; // [rsp+128h] [rbp+77h]
  _QWORD *v220; // [rsp+130h] [rbp+7Fh]

  v220 = a4;
  v219 = a3;
  v218 = a2;
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
        v11 = "Error post-encoding before directory write";
LABEL_6:
        TIFFErrorExtR(a1, "TIFFWriteDirectorySec", v11, v10);
        return 0;
      }
    }
    (*(void (__fastcall **)(__int64))(a1 + 1032))(a1);
    if ( *(__int64 *)(a1 + 1136) > 0 && (*(_BYTE *)(a1 + 16) & 0x40) != 0 && !(unsigned int)TIFFFlushData1(a1) )
    {
      v11 = "Error flushing data before directory write";
      goto LABEL_6;
    }
    if ( (*(_DWORD *)(a1 + 16) & 0x200) != 0 )
    {
      v13 = *(_QWORD *)(a1 + 1096);
      if ( v13 )
      {
        TIFFfreeExt(a1, v13);
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
  v14 = a1 + 416;
  v15 = 0;
  *(_QWORD *)v199 = 0;
  v200 = 0;
  while ( 1 )
  {
    v198 = 0;
    v16 = 8;
    if ( !v15 )
      *(_QWORD *)v14 = 0;
    if ( !v5 )
      goto LABEL_359;
    if ( (*(_BYTE *)(a1 + 72) & 2) != 0 )
    {
      if ( *(_DWORD *)(a1 + 88) > 0xFFFFu )
      {
        if ( v15 )
        {
          v117 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 88);
          if ( !v117 )
            TIFFSwabLong(&Src);
          LODWORD(Size) = 4;
          LOWORD(v192) = 4;
          v17 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 256, v192, 1, Size, &Src);
        }
        else
        {
          v198 = 1;
          v17 = 1;
        }
      }
      else if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 88);
        if ( !v117 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v192) = 3;
        v17 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 256, v192, 1, Size, &Src);
      }
      else
      {
        v198 = 1;
        v17 = 1;
      }
      if ( !v17 )
        goto LABEL_523;
      if ( *(_DWORD *)(a1 + 92) > 0xFFFFu )
      {
        if ( v15 )
        {
          v117 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 92);
          if ( !v117 )
            TIFFSwabLong(&Src);
          LODWORD(Size) = 4;
          LOWORD(v192) = 4;
          v18 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 257, v192, 1, Size, &Src);
        }
        else
        {
          ++v198;
          v18 = 1;
        }
      }
      else if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 92);
        if ( !v117 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v192) = 3;
        v18 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 257, v192, 1, Size, &Src);
      }
      else
      {
        ++v198;
        v18 = 1;
      }
      if ( !v18 )
        goto LABEL_523;
    }
    if ( (*(_BYTE *)(a1 + 72) & 4) != 0 )
    {
      if ( *(_DWORD *)(a1 + 100) > 0xFFFFu )
      {
        if ( v15 )
        {
          v117 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 100);
          if ( !v117 )
            TIFFSwabLong(&Src);
          LODWORD(Size) = 4;
          LOWORD(v192) = 4;
          v19 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 322, v192, 1, Size, &Src);
        }
        else
        {
          ++v198;
          v19 = 1;
        }
      }
      else if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 100);
        if ( !v117 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v192) = 3;
        v19 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 322, v192, 1, Size, &Src);
      }
      else
      {
        ++v198;
        v19 = 1;
      }
      if ( !v19 )
        goto LABEL_523;
      if ( *(_DWORD *)(a1 + 104) > 0xFFFFu )
      {
        if ( v15 )
        {
          v117 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 104);
          if ( !v117 )
            TIFFSwabLong(&Src);
          LODWORD(Size) = 4;
          LOWORD(v192) = 4;
          v20 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 323, v192, 1, Size, &Src);
        }
        else
        {
          ++v198;
          v20 = 1;
        }
      }
      else if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 104);
        if ( !v117 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v192) = 3;
        v20 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 323, v192, 1, Size, &Src);
      }
      else
      {
        ++v198;
        v20 = 1;
      }
      if ( !v20 )
      {
LABEL_523:
        if ( !v15 )
          return 0;
LABEL_524:
        TIFFfreeExt(a1, v15);
        return 0;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 8) != 0 )
    {
      if ( *(float *)(a1 + 160) < 0.0 )
        goto LABEL_525;
      if ( v15 )
      {
        DoubleToRational(v8, v205, v206);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v205);
          TIFFSwabLong(v206);
        }
        LODWORD(Size) = 8;
        LOWORD(v192) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 282, v192, 1, Size, v205) )
          goto LABEL_524;
      }
      else
      {
        v21 = *(_QWORD *)v14 + (((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8);
        ++v198;
        *(_QWORD *)(a1 + 416) = v21;
      }
      if ( *(float *)(a1 + 164) < 0.0 )
        goto LABEL_525;
      if ( v15 )
      {
        DoubleToRational(v8, v207, v208);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v207);
          TIFFSwabLong(v208);
        }
        LODWORD(Size) = 8;
        LOWORD(v192) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 283, v192, 1, Size, v207) )
          goto LABEL_524;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v198;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x10) != 0 )
    {
      if ( *(float *)(a1 + 172) < 0.0 )
        goto LABEL_525;
      if ( v15 )
      {
        DoubleToRational(v8, v209, v210);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v209);
          TIFFSwabLong(v210);
        }
        LODWORD(Size) = 8;
        LOWORD(v192) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 286, v192, 1, Size, v209) )
          goto LABEL_524;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v198;
      }
      if ( *(float *)(a1 + 176) < 0.0 )
      {
LABEL_525:
        TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRational", "Negative value is illegal", v16);
        goto LABEL_523;
      }
      if ( v15 )
      {
        DoubleToRational(v8, v211, v212);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v211);
          TIFFSwabLong(v212);
        }
        LODWORD(Size) = 8;
        LOWORD(v192) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 287, v192, 1, Size, v211) )
          goto LABEL_524;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v198;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x20) != 0 )
    {
      if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 112);
        if ( !v117 )
          TIFFSwabLong(&Src);
        LODWORD(Size) = 4;
        LOWORD(v192) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 254, v192, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v198;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x40) != 0 )
    {
      v22 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v15 )
      {
        v24 = *(_WORD *)(a1 + 116);
        v25 = TIFFmallocExt(a1, v22);
        v27 = (void *)v25;
        if ( !v25 )
          goto LABEL_526;
        v28 = *(_WORD *)(a1 + 130);
        v29 = 0;
        for ( i = (_WORD *)v25; v29 < v28; ++v29 )
        {
          *i++ = v24;
          v28 = *(_WORD *)(a1 + 130);
        }
        v31 = v28;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v25, v28);
        LODWORD(Size) = 2 * v31;
        LOWORD(v192) = 3;
        v32 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 258, v192, v31, Size, v27);
        TIFFfreeExt(a1, v27);
        if ( !v32 )
          goto LABEL_524;
      }
      else
      {
        v23 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v23 = 8;
        if ( v22 > v23 )
          *(_QWORD *)(a1 + 416) += v22;
        ++v198;
      }
    }
    if ( *(char *)(a1 + 72) < 0 )
    {
      if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 120);
        if ( !v117 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v192) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 259, v192, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v198;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x100) != 0 )
    {
      if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 122);
        if ( !v117 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v192) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 262, v192, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v198;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x200) != 0 )
    {
      if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 124);
        if ( !v117 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v192) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 263, v192, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v198;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x400) != 0 )
    {
      if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 126);
        if ( !v117 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v192) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 266, v192, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v198;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x8000) != 0 )
    {
      if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 128);
        if ( !v117 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v192) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 274, v192, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v198;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x10000) != 0 )
    {
      if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 130);
        if ( !v117 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v192) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 277, v192, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v198;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x20000) != 0 )
    {
      if ( *(_DWORD *)(a1 + 132) > 0xFFFFu )
      {
        if ( v15 )
        {
          v117 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 132);
          if ( !v117 )
            TIFFSwabLong(&Src);
          LODWORD(Size) = 4;
          LOWORD(v192) = 4;
          v33 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 278, v192, 1, Size, &Src);
        }
        else
        {
          ++v198;
          v33 = 1;
        }
      }
      else if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 132);
        if ( !v117 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v192) = 3;
        v33 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 278, v192, 1, Size, &Src);
      }
      else
      {
        ++v198;
        v33 = 1;
      }
      if ( !v33 )
        goto LABEL_523;
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x40000) != 0 )
    {
      v34 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v15 )
      {
        v36 = *(_WORD *)(a1 + 136);
        v37 = TIFFmallocExt(a1, v34);
        v38 = (void *)v37;
        if ( !v37 )
          goto LABEL_526;
        v39 = *(_WORD *)(a1 + 130);
        v40 = 0;
        for ( j = (_WORD *)v37; v40 < v39; ++v40 )
        {
          *j++ = v36;
          v39 = *(_WORD *)(a1 + 130);
        }
        v42 = v39;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v37, v39);
        LODWORD(Size) = 2 * v42;
        LOWORD(v192) = 3;
        v43 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 280, v192, v42, Size, v38);
        TIFFfreeExt(a1, v38);
        if ( !v43 )
          goto LABEL_524;
      }
      else
      {
        v35 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v35 = 8;
        if ( v34 > v35 )
          *(_QWORD *)(a1 + 416) += v34;
        ++v198;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x80000) != 0 )
    {
      v44 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v15 )
      {
        v46 = *(_WORD *)(a1 + 138);
        v47 = TIFFmallocExt(a1, v44);
        v48 = (void *)v47;
        if ( !v47 )
          goto LABEL_526;
        v49 = *(_WORD *)(a1 + 130);
        v50 = 0;
        for ( k = (_WORD *)v47; v50 < v49; ++v50 )
        {
          *k++ = v46;
          v49 = *(_WORD *)(a1 + 130);
        }
        v52 = v49;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v47, v49);
        LODWORD(Size) = 2 * v52;
        LOWORD(v192) = 3;
        v53 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 281, v192, v52, Size, v48);
        TIFFfreeExt(a1, v48);
        if ( !v53 )
          goto LABEL_524;
      }
      else
      {
        v45 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v45 = 8;
        if ( v44 > v45 )
          *(_QWORD *)(a1 + 416) += v44;
        ++v198;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x100000) != 0 )
    {
      if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 170);
        if ( !v117 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v192) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 284, v192, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v198;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x400000) != 0 )
    {
      if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 168);
        if ( !v117 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v192) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 296, v192, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v198;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x800000) != 0 )
    {
      if ( v15 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 180, 2);
        LODWORD(Size) = 4;
        LOWORD(v192) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 297, v192, 2, Size, (void *)(a1 + 180)) )
          goto LABEL_524;
      }
      else
      {
        ++v198;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x1000000) != 0
      && !(unsigned int)TIFFWriteDirectoryTagLongLong8Array(
                          a1,
                          (int)&v198,
                          (int)v15,
                          *(_DWORD *)(a1 + 228),
                          *(void **)(a1 + 240))
      || (*(_DWORD *)(a1 + 72) & 0x2000000) != 0
      && ((*(_DWORD *)(a1 + 16) & 0x400) != 0 || *(_QWORD *)(a1 + 232))
      && !(unsigned int)TIFFWriteDirectoryTagLongLong8Array(
                          a1,
                          (int)&v198,
                          (int)v15,
                          *(_DWORD *)(a1 + 228),
                          *(void **)(a1 + 232)) )
    {
      goto LABEL_523;
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x4000000) != 0 )
    {
      v54 = (unsigned int)(1 << *(_BYTE *)(a1 + 116));
      v55 = 2LL * (unsigned int)(3 * v54);
      if ( v15 )
      {
        v57 = (char *)TIFFmallocExt(a1, v55);
        v58 = v57;
        if ( !v57 )
        {
          v167 = "TIFFWriteDirectoryTagColormap";
          goto LABEL_555;
        }
        TIFFmemcpy(v57, *(const void **)(a1 + 184), 2 * v54);
        TIFFmemcpy(&v58[2 * v54], *(const void **)(a1 + 192), 2 * v54);
        TIFFmemcpy(&v58[2 * (unsigned int)(2 * v54)], *(const void **)(a1 + 200), 2 * v54);
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v58, (unsigned int)(3 * v54));
        LODWORD(Size) = 6 * v54;
        LOWORD(v192) = 3;
        v59 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 320, v192, 3 * (int)v54, Size, v58);
        TIFFfreeExt(a1, v58);
        if ( !v59 )
          goto LABEL_524;
        v7 = 1;
      }
      else
      {
        v56 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v56 = 8;
        if ( v55 > v56 )
          *(_QWORD *)(a1 + 416) += v55;
        ++v198;
        v7 = 1;
      }
    }
    if ( *(int *)(a1 + 72) < 0 && *(_WORD *)(a1 + 212) )
    {
      TIFFGetFieldDefaulted(a1, 338, &v201, v215);
      v60 = v201;
      v61 = *(_DWORD *)(a1 + 16);
      if ( v15 )
      {
        v65 = v215[0];
        if ( (v61 & 0x80u) != 0 )
          TIFFSwabArrayOfShort(v215[0], v201);
        LODWORD(Size) = 2 * v60;
        LOWORD(v192) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 338, v192, v60, Size, v65) )
          goto LABEL_524;
      }
      else
      {
        v62 = 2LL * v201;
        v63 = (v61 & 0x80000) != 0;
        v64 = 4;
        if ( v63 )
          v64 = 8;
        if ( v62 > v64 )
          *(_QWORD *)(a1 + 416) += v62;
        ++v198;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 1) != 0 )
    {
      v66 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v15 )
      {
        v68 = *(_WORD *)(a1 + 118);
        v69 = TIFFmallocExt(a1, v66);
        v70 = (void *)v69;
        if ( !v69 )
        {
LABEL_526:
          v167 = "TIFFWriteDirectoryTagShortPerSample";
          goto LABEL_555;
        }
        v71 = *(_WORD *)(a1 + 130);
        v72 = 0;
        for ( m = (_WORD *)v69; v72 < v71; ++v72 )
        {
          *m++ = v68;
          v71 = *(_WORD *)(a1 + 130);
        }
        v74 = v71;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v69, v71);
        LODWORD(Size) = 2 * v74;
        LOWORD(v192) = 3;
        v75 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 339, v192, v74, Size, v70);
        TIFFfreeExt(a1, v70);
        if ( !v75 )
          goto LABEL_524;
      }
      else
      {
        v67 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v67 = 8;
        if ( v66 > v67 )
          *(_QWORD *)(a1 + 416) += v66;
        ++v198;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 2) != 0
      && !(unsigned int)TIFFWriteDirectoryTagSampleformatArray(
                          a1,
                          (int)&v198,
                          (int)v15,
                          *(unsigned __int16 *)(a1 + 130),
                          *(void **)(a1 + 144))
      || (*(_BYTE *)(a1 + 76) & 4) != 0
      && !(unsigned int)TIFFWriteDirectoryTagSampleformatArray(
                          a1,
                          (int)&v198,
                          (int)v15,
                          *(unsigned __int16 *)(a1 + 130),
                          *(void **)(a1 + 152)) )
    {
      goto LABEL_523;
    }
    if ( (*(_BYTE *)(a1 + 76) & 8) != 0 )
    {
      if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 96);
        if ( !v117 )
          TIFFSwabLong(&Src);
        LODWORD(Size) = 4;
        LOWORD(v192) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 32997, v192, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v198;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 0x10) != 0 )
    {
      if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 108);
        if ( !v117 )
          TIFFSwabLong(&Src);
        LODWORD(Size) = 4;
        LOWORD(v192) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 32998, v192, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v198;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 0x20) != 0 )
    {
      if ( v15 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 208, 2);
        LODWORD(Size) = 4;
        v14 = 3;
        LOWORD(v192) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 321, v192, 2, Size, (void *)(a1 + 208)) )
          goto LABEL_524;
        goto LABEL_276;
      }
      ++v198;
    }
    v14 = 3;
LABEL_276:
    if ( *(char *)(a1 + 76) < 0 )
    {
      if ( v15 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 336, 2);
        LODWORD(Size) = 4;
        v14 = 3;
        LOWORD(v192) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 530, v192, 2, Size, (void *)(a1 + 336)) )
          goto LABEL_524;
      }
      else
      {
        ++v198;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x100) != 0 )
    {
      if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 340);
        if ( !v117 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v192) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 531, v192, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v198;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x200) != 0 )
    {
      if ( v15 )
      {
        v76 = TIFFmallocExt(a1, 48);
        v78 = (char *)v76;
        if ( !v76 )
        {
          v167 = "TIFFWriteDirectoryTagCheckedRationalArray";
          goto LABEL_555;
        }
        DoubleToRational(v77, v76, v76 + 4);
        DoubleToRational(v79, v78 + 8, v78 + 12);
        DoubleToRational(v80, v78 + 16, v78 + 20);
        DoubleToRational(v81, v78 + 24, v78 + 28);
        DoubleToRational(v82, v78 + 32, v78 + 36);
        DoubleToRational(v83, v78 + 40, v78 + 44);
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfFloat(v78, 12);
        LODWORD(Size) = 48;
        LOWORD(v192) = 5;
        v84 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 532, v192, 6, Size, v78);
        TIFFfreeExt(a1, v78);
        if ( !v84 )
          goto LABEL_524;
        v14 = 3;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += 48LL;
        ++v198;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x1000) != 0
      && !(unsigned int)TIFFWriteDirectoryTagTransferfunction(a1, (int)&v198, (int)v15) )
    {
      goto LABEL_523;
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x4000) != 0 )
    {
      v85 = *(unsigned int *)(a1 + 376);
      if ( v15 )
      {
        LODWORD(Size) = *(_DWORD *)(a1 + 376);
        LOWORD(v192) = 2;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(
                              a1,
                              (int)&v198,
                              (int)v15,
                              333,
                              v192,
                              v85,
                              Size,
                              *(void **)(a1 + 384)) )
          goto LABEL_524;
      }
      else
      {
        v86 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v86 = 8;
        if ( v85 > v86 )
        {
          v87 = v85 + 1;
          if ( (v85 & 1) == 0 )
            v87 = *(unsigned int *)(a1 + 376);
          *(_QWORD *)(a1 + 416) += v87;
        }
        ++v198;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x40000) != 0 )
    {
      if ( v15 )
      {
        v117 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 392);
        if ( !v117 )
          TIFFSwabShort(&Src);
        LODWORD(Size) = 2;
        LOWORD(v192) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, 334, v192, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v198;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x20000) != 0 && !(unsigned int)TIFFWriteDirectoryTagSubifd(a1, (int)&v198, (int)v15) )
      goto LABEL_523;
    for ( n = 0; (unsigned __int64)(unsigned int)n < *(_QWORD *)(a1 + 1240); n = (unsigned int)(n + 1) )
    {
      v89 = *(unsigned int **)(*(_QWORD *)(a1 + 1232) + 8 * n);
      v90 = *((_WORD *)v89 + 12);
      if ( v90 >= 0x42u )
      {
        v91 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)v90 >> 5) + 72);
        if ( _bittest(&v91, v90 & 0x1F) )
        {
          switch ( v89[4] )
          {
            case 1u:
              TIFFGetField(a1, *v89, &Str);
              v14 = (unsigned __int64)Str;
              v95 = strlen_0(Str);
              if ( v15 )
              {
                LODWORD(Size) = v95;
                LOWORD(v192) = 2;
                v94 = TIFFWriteDirectoryTagData(
                        a1,
                        (int)&v198,
                        (int)v15,
                        *(unsigned __int16 *)v89,
                        v192,
                        v95,
                        Size,
                        (void *)v14);
                goto LABEL_357;
              }
              v96 = 4;
              v97 = v95;
              if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                v96 = 8;
              if ( v95 > v96 )
              {
                v117 = (v95 & 1) == 0;
                v98 = v95 + 1LL;
                if ( v117 )
                  v98 = v97;
                *(_QWORD *)(a1 + 416) += v98;
              }
              ++v198;
              break;
            case 4u:
              TIFFGetField(a1, *v89, v202);
              if ( v15 )
              {
                v117 = *(_BYTE *)(a1 + 16) >= 0;
                v14 = *(unsigned __int16 *)v89;
                LOWORD(Src) = v202[0];
                if ( !v117 )
                  TIFFSwabShort(&Src);
                LODWORD(Size) = 2;
                LOWORD(v192) = 3;
                v94 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, (unsigned __int16)v14, v192, 1, Size, &Src);
LABEL_357:
                if ( !v94 )
                  goto LABEL_524;
                continue;
              }
              ++v198;
              break;
            case 6u:
              TIFFGetField(a1, *v89, &v214);
              if ( v15 )
              {
                v117 = *(_BYTE *)(a1 + 16) >= 0;
                v14 = *(unsigned __int16 *)v89;
                Src = v214;
                if ( !v117 )
                  TIFFSwabLong(&Src);
                LODWORD(Size) = 4;
                LOWORD(v192) = 4;
                v94 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, (unsigned __int16)v14, v192, 1, Size, &Src);
                goto LABEL_357;
              }
              ++v198;
              break;
            case 0x28u:
              TIFFGetField(a1, *v89, &v213);
              if ( v15 )
              {
                LODWORD(Size) = v213;
                LOWORD(v192) = 7;
                v94 = TIFFWriteDirectoryTagData(
                        a1,
                        (int)&v198,
                        (int)v15,
                        *(unsigned __int16 *)v89,
                        v192,
                        v213,
                        Size,
                        v215[1]);
                goto LABEL_357;
              }
              v92 = 4;
              if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                v92 = 8;
              if ( v213 > v92 )
              {
                v93 = v213 + 1LL;
                if ( (v213 & 1) == 0 )
                  v93 = v213;
                *(_QWORD *)(a1 + 416) += v93;
              }
              ++v198;
              break;
            default:
              v168 = TIFFFieldTag(v89);
              TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Cannot write tag %u (%s)", v168);
              goto LABEL_523;
          }
        }
      }
    }
LABEL_359:
    v99 = 0;
    v204 = 0;
    if ( *(_DWORD *)(a1 + 396) )
    {
      while ( 1 )
      {
        v100 = *(_QWORD *)(a1 + 400);
        v101 = 3 * v99;
        v102 = *(unsigned __int16 **)(v100 + 24 * v99);
        v103 = v14;
        v104 = v7;
        v7 = *v102;
        v14 = *(unsigned int *)(v100 + 24 * v99 + 8);
        v105 = *((_DWORD *)v102 + 2) - 1;
        LOWORD(Src) = *v102;
        switch ( v105 )
        {
          case 0:
            if ( !v15 )
              goto LABEL_362;
            LODWORD(Size) = v14;
            LOWORD(v192) = 1;
            v108 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v198,
                     (int)v15,
                     (unsigned __int16)v7,
                     v192,
                     v14,
                     Size,
                     *(void **)(v100 + 8 * v101 + 16));
            goto LABEL_370;
          case 1:
            if ( !v15 )
              goto LABEL_362;
            LODWORD(Size) = v14;
            LOWORD(v192) = 2;
            v108 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v198,
                     (int)v15,
                     (unsigned __int16)v7,
                     v192,
                     v14,
                     Size,
                     *(void **)(v100 + 8 * v101 + 16));
            goto LABEL_370;
          case 2:
            if ( !v15 )
            {
              v109 = 2 * v14;
              goto LABEL_380;
            }
            v111 = *(void **)(v100 + 8 * v101 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfShort(v111, v14);
            LODWORD(Size) = 2 * v14;
            LOWORD(v192) = 3;
            v108 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, (unsigned __int16)v7, v192, v14, Size, v111);
            goto LABEL_370;
          case 3:
            if ( !v15 )
            {
              v109 = 4 * v14;
              goto LABEL_380;
            }
            v115 = *(void **)(v100 + 8 * v101 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v115, v14);
            LODWORD(Size) = 4 * v14;
            LOWORD(v192) = 4;
            v108 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, (unsigned __int16)v7, v192, v14, Size, v115);
            goto LABEL_370;
          case 4:
            v203 = TIFFFieldSetGetSize(v102);
            v132 = v203;
            if ( v203 == 8 )
            {
              if ( !v15 )
                goto LABEL_441;
              v133 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v101 + 16);
              v134 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v14));
              v7 = v134;
              if ( !v134 )
              {
                TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRationalDoubleArray", "Out of memory", v136);
                TIFFfreeExt(a1, *(_QWORD *)v199);
                return 0;
              }
              v137 = 0;
              for ( ii = v134; v137 < (unsigned int)v14; ++v137 )
              {
                DoubleToRational(v135, ii, ii + 4);
                ii += 8;
                v133 += 8;
              }
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v14));
              v196 = (void *)v7;
              LODWORD(Size) = 8 * v14;
              v193 = v14;
              LOWORD(v192) = 5;
              goto LABEL_448;
            }
            if ( !v15 )
              goto LABEL_451;
            v141 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v101 + 16);
            v142 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v14));
            v7 = v142;
            if ( !v142 )
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRationalArray", "Out of memory", v144);
              TIFFfreeExt(a1, *(_QWORD *)v199);
              return 0;
            }
            v145 = 0;
            for ( jj = v142; v145 < (unsigned int)v14; ++v145 )
            {
              DoubleToRational(v143, jj, jj + 4);
              jj += 8;
              v141 += 4;
            }
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v14));
            v197 = (void *)v7;
            LODWORD(Size) = 8 * v14;
            v194 = v14;
            LOWORD(v192) = 5;
            goto LABEL_462;
          case 5:
            if ( !v15 )
              goto LABEL_362;
            LODWORD(Size) = v14;
            LOWORD(v192) = 6;
            v108 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v198,
                     (int)v15,
                     (unsigned __int16)v7,
                     v192,
                     v14,
                     Size,
                     *(void **)(v100 + 8 * v101 + 16));
            goto LABEL_370;
          case 6:
            if ( v15 )
            {
              LODWORD(Size) = v14;
              LOWORD(v192) = 7;
              v108 = TIFFWriteDirectoryTagData(
                       a1,
                       (int)&v198,
                       (int)v15,
                       (unsigned __int16)v7,
                       v192,
                       v14,
                       Size,
                       *(void **)(v100 + 8 * v101 + 16));
              goto LABEL_370;
            }
LABEL_362:
            v106 = 4;
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
              v106 = 8;
            if ( v14 > v106 )
            {
              v107 = v14 + 1;
              if ( (v14 & 1) == 0 )
                v107 = v14;
              *(_QWORD *)(a1 + 416) += v107;
            }
            goto LABEL_368;
          case 7:
            if ( v15 )
            {
              v114 = *(void **)(v100 + 8 * v101 + 16);
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfShort(v114, v14);
              LODWORD(Size) = 2 * v14;
              LOWORD(v192) = 8;
              v108 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, (unsigned __int16)v7, v192, v14, Size, v114);
              goto LABEL_370;
            }
            v112 = 4;
            v113 = 2 * v14;
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
              v112 = 8;
            if ( v113 > v112 )
            {
              *(_QWORD *)(a1 + 416) += v113;
              ++v198;
              goto LABEL_498;
            }
            goto LABEL_368;
          case 8:
            if ( !v15 )
            {
              v109 = 4 * v14;
              goto LABEL_380;
            }
            v116 = *(void **)(v100 + 8 * v101 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v116, v14);
            LODWORD(Size) = 4 * v14;
            LOWORD(v192) = 9;
            v108 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, (unsigned __int16)v7, v192, v14, Size, v116);
            goto LABEL_370;
          case 9:
            v203 = TIFFFieldSetGetSize(v102);
            v132 = v203;
            if ( v203 == 8 )
            {
              if ( v15 )
              {
                v147 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v101 + 16);
                v148 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v14));
                v7 = v148;
                if ( !v148 )
                {
                  TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSrationalDoubleArray", "Out of memory", v150);
                  TIFFfreeExt(a1, *(_QWORD *)v199);
                  return 0;
                }
                v151 = 0;
                for ( kk = v148; v151 < (unsigned int)v14; ++v151 )
                {
                  DoubleToSrational(v149, kk, kk + 4);
                  kk += 8;
                  v147 += 8;
                }
                if ( *(char *)(a1 + 16) < 0 )
                  TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v14));
                v196 = (void *)v7;
                LODWORD(Size) = 8 * v14;
                v193 = v14;
                LOWORD(v192) = 10;
LABEL_448:
                v15 = *(_WORD **)v199;
                v14 = (unsigned int)TIFFWriteDirectoryTagData(
                                      a1,
                                      (int)&v198,
                                      v199[0],
                                      (unsigned __int16)Src,
                                      v192,
                                      v193,
                                      Size,
                                      v196);
                TIFFfreeExt(a1, v7);
                if ( !(_DWORD)v14 )
                  goto LABEL_524;
              }
              else
              {
LABEL_441:
                v109 = 4LL * (unsigned int)(2 * v14);
LABEL_380:
                v110 = 4;
                if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                  v110 = 8;
                if ( v109 <= v110 )
                {
LABEL_368:
                  ++v198;
                }
                else
                {
                  *(_QWORD *)(a1 + 416) += v109;
                  ++v198;
                }
              }
            }
            else
            {
              if ( v15 )
              {
                v153 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v101 + 16);
                v154 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v14));
                v7 = v154;
                if ( !v154 )
                {
                  TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSrationalArray", "Out of memory", v156);
                  TIFFfreeExt(a1, *(_QWORD *)v199);
                  return 0;
                }
                v157 = 0;
                for ( mm = v154; v157 < (unsigned int)v14; ++v157 )
                {
                  DoubleToSrational(v155, mm, mm + 4);
                  mm += 8;
                  v153 += 4;
                }
                if ( *(char *)(a1 + 16) < 0 )
                  TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v14));
                v197 = (void *)v7;
                LODWORD(Size) = 8 * v14;
                v194 = v14;
                LOWORD(v192) = 10;
LABEL_462:
                v15 = *(_WORD **)v199;
                v14 = (unsigned int)TIFFWriteDirectoryTagData(
                                      a1,
                                      (int)&v198,
                                      v199[0],
                                      (unsigned __int16)Src,
                                      v192,
                                      v194,
                                      Size,
                                      v197);
                TIFFfreeExt(a1, v7);
                if ( !(_DWORD)v14 )
                  goto LABEL_524;
                v132 = v203;
              }
              else
              {
LABEL_451:
                v139 = 4;
                v140 = 4LL * (unsigned int)(2 * v14);
                if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                  v139 = 8;
                if ( v140 > v139 )
                  *(_QWORD *)(a1 + 416) += v140;
                ++v198;
              }
              if ( v132 != 4 )
                TIFFErrorExtR(
                  a1,
                  "TIFFLib: _TIFFWriteDirectorySec()",
                  "Rational2Double: .set_field_type is not 4 but %d",
                  v132);
            }
            goto LABEL_498;
          case 10:
            if ( !v15 )
            {
              v109 = 4 * v14;
              goto LABEL_380;
            }
            v159 = *(void **)(v100 + 8 * v101 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v159, v14);
            LODWORD(Size) = 4 * v14;
            LOWORD(v192) = 11;
            v108 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, (unsigned __int16)v7, v192, v14, Size, v159);
            goto LABEL_370;
          case 11:
            if ( !v15 )
            {
              v109 = 8 * v14;
              goto LABEL_380;
            }
            v160 = *(void **)(v100 + 8 * v101 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfDouble(v160, v14, v102, 8);
            LODWORD(Size) = 8 * v14;
            LOWORD(v192) = 12;
            v108 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, (unsigned __int16)v7, v192, v14, Size, v160);
            goto LABEL_370;
          case 12:
            if ( !v15 )
            {
              v109 = 4 * v14;
              goto LABEL_380;
            }
            v161 = *(void **)(v100 + 8 * v101 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v161, v14);
            LODWORD(Size) = 4 * v14;
            LOWORD(v192) = 13;
            v108 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, (unsigned __int16)v7, v192, v14, Size, v161);
LABEL_370:
            if ( !v108 )
              goto LABEL_524;
            goto LABEL_498;
          case 15:
            if ( v15 )
            {
              v118 = *(_DWORD *)(a1 + 16);
              v119 = *(_QWORD **)(v100 + 8 * v101 + 16);
              if ( (v118 & 0x80000) != 0 )
              {
                if ( (v118 & 0x80u) != 0 )
                  TIFFSwabArrayOfDouble(v119, v14, v102, 8);
                LODWORD(Size) = 8 * v14;
                LOWORD(v192) = 16;
                v120 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, (unsigned __int16)v7, v192, v14, Size, v119);
LABEL_415:
                v14 = v120;
                v117 = v120 == 0;
                goto LABEL_497;
              }
              v121 = TIFFmallocExt(a1, 4 * v14);
              v122 = (void *)v121;
              if ( !v121 )
              {
                v167 = "TIFFWriteDirectoryTagLong8Array";
                goto LABEL_555;
              }
              v123 = 0;
              v124 = (_DWORD *)v121;
              if ( (_DWORD)v14 )
              {
                while ( 1 )
                {
                  v125 = *v119;
                  if ( *v119 > 0xFFFFFFFF )
                    break;
                  *v124 = v125;
                  ++v119;
                  ++v124;
                  if ( ++v123 >= (unsigned int)v14 )
                    goto LABEL_420;
                }
                v169 = "Attempt to write unsigned long value %llu larger than 0xFFFFFFFF for tag %d in Classic TIFF file."
                       " TIFF file writing aborted";
                v170 = "TIFFWriteDirectoryTagLong8Array";
LABEL_534:
                TIFFErrorExtR(a1, v170, v169, v125);
                TIFFfreeExt(a1, v122);
                TIFFfreeExt(a1, v15);
                return 0;
              }
LABEL_420:
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v121, v14);
              LODWORD(Size) = 4 * v14;
              LOWORD(v192) = 4;
              v126 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, (unsigned __int16)v7, v192, v14, Size, v122);
LABEL_423:
              v14 = v126;
              TIFFfreeExt(a1, v122);
              v117 = (_DWORD)v14 == 0;
              goto LABEL_497;
            }
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) == 0 )
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedLong8Array", "LONG8 not allowed for ClassicTIFF", 8);
              v14 = 0;
              v117 = 1;
              goto LABEL_497;
            }
            goto LABEL_408;
          case 16:
            if ( v15 )
            {
              v127 = *(_DWORD *)(a1 + 16);
              v128 = *(__int64 **)(v100 + 8 * v101 + 16);
              if ( (v127 & 0x80000) != 0 )
              {
                if ( (v127 & 0x80u) != 0 )
                  TIFFSwabArrayOfDouble(v128, v14, v102, 8);
                LODWORD(Size) = 8 * v14;
                LOWORD(v192) = 17;
                v120 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, (unsigned __int16)v7, v192, v14, Size, v128);
                goto LABEL_415;
              }
              v129 = TIFFmallocExt(a1, 4 * v14);
              v122 = (void *)v129;
              if ( !v129 )
              {
                v167 = "TIFFWriteDirectoryTagSlong8Array";
                goto LABEL_555;
              }
              v130 = 0;
              v131 = (_DWORD *)v129;
              if ( (_DWORD)v14 )
              {
                while ( 1 )
                {
                  v125 = *v128;
                  if ( *v128 > 0x7FFFFFFF )
                    break;
                  if ( v125 < (__int64)0xFFFFFFFF80000000uLL )
                  {
                    v169 = "Attempt to write signed long value %lli smaller than 0x80000000 (-2147483648) for tag %d in C"
                           "lassic TIFF file. TIFF writing to file aborted";
                    goto LABEL_533;
                  }
                  *v131 = v125;
                  ++v128;
                  ++v131;
                  if ( ++v130 >= (unsigned int)v14 )
                    goto LABEL_436;
                }
                v169 = "Attempt to write signed long value %lli larger than 0x7FFFFFFF (2147483647) for tag %d in Classic"
                       " TIFF file. TIFF writing to file aborted";
LABEL_533:
                v170 = "TIFFWriteDirectoryTagSlong8Array";
                goto LABEL_534;
              }
LABEL_436:
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v129, v14);
              LODWORD(Size) = 4 * v14;
              LOWORD(v192) = 9;
              v126 = TIFFWriteDirectoryTagData(a1, (int)&v198, (int)v15, (unsigned __int16)v7, v192, v14, Size, v122);
              goto LABEL_423;
            }
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
            {
LABEL_408:
              if ( 8 * v14 > 8 )
                *(_QWORD *)(a1 + 416) += 8 * v14;
              ++v198;
              v14 = 1;
              v117 = 0;
            }
            else
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSlong8Array", "SLONG8 not allowed for ClassicTIFF", 8);
              v14 = 0;
              v117 = 1;
            }
LABEL_497:
            if ( v117 )
              goto LABEL_523;
LABEL_498:
            v99 = (unsigned int)(v204 + 1);
            v204 = v99;
            if ( (unsigned int)v99 >= *(_DWORD *)(a1 + 396) )
              goto LABEL_499;
            break;
          case 17:
            v117 = (unsigned int)TIFFWriteDirectoryTagIfdIfd8Array(
                                   a1,
                                   (int)&v198,
                                   (int)v15,
                                   v14,
                                   *(void **)(v100 + 8 * v101 + 16)) == 0;
            goto LABEL_497;
          default:
            v7 = v104;
            v14 = v103;
            goto LABEL_498;
        }
      }
    }
LABEL_499:
    if ( v15 )
      break;
    v14 = a1 + 416;
    if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
      v162 = (unsigned int)(20 * v198 + 16);
    else
      v162 = (unsigned int)(12 * v198 + 6);
    *(_QWORD *)v14 = *(_QWORD *)(a1 + 416) + v162;
    *(_QWORD *)v199 = TIFFmallocExt(a1, 32LL * (unsigned int)v198);
    v15 = *(_WORD **)v199;
    if ( !*(_QWORD *)v199 )
    {
      v11 = "Out of memory";
      goto LABEL_6;
    }
    v5 = v218;
    if ( v218 )
    {
      if ( *(_QWORD *)(a1 + 24) )
      {
        if ( *(_QWORD *)v14 > *(_QWORD *)(a1 + 424) )
        {
          TIFFfreeExt(a1, *(_QWORD *)v199);
          return (unsigned int)TIFFRewriteDirectorySec(a1) != 0;
        }
      }
      else if ( !(unsigned int)TIFFLinkDirectory(a1) )
      {
        goto LABEL_524;
      }
    }
    else
    {
      v163 = *(_QWORD *)(a1 + 424);
      if ( !v163 || *(_QWORD *)v14 > v163 )
        *(_QWORD *)(a1 + 24) = ((*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 1200))(
                                  *(_QWORD *)(a1 + 1176),
                                  0,
                                  2)
                              + 1)
                             & 0xFFFFFFFFFFFFFFFEuLL;
    }
    if ( v220 )
      *v220 = *(_QWORD *)(a1 + 24);
    v164 = *(_QWORD *)(a1 + 24);
    if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
    {
      v165 = (unsigned int)(20 * v198 + 16);
      v166 = v165 + v164;
    }
    else
    {
      LODWORD(v165) = 12 * v198 + 6;
      v166 = (unsigned int)(v164 + v165);
    }
    *(_QWORD *)(a1 + 880) = v166;
    v8 = (unsigned int)v165;
    v200 = v165;
    if ( v166 < v164 || v166 < (unsigned int)v165 )
    {
      TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Maximum TIFF file size exceeded", v10);
      TIFFfreeExt(a1, v15);
      return 0;
    }
    if ( (v166 & 1) != 0 )
      *(_QWORD *)(a1 + 880) = v166 + 1;
    v7 = 1;
  }
  if ( !v218 || (*(_DWORD *)(a1 + 76) & 0x20000) == 0 || *(_QWORD *)(a1 + 896) )
    goto LABEL_553;
  v171 = 0;
  v172 = v15;
  if ( !v198 )
  {
LABEL_549:
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Cannot find SubIFD tag", 8);
    TIFFfreeExt(a1, v15);
    return 0;
  }
  while ( *v172 != 330 )
  {
    ++v171;
    v172 += 16;
    if ( v171 == v198 )
      goto LABEL_549;
  }
  v173 = *(_QWORD *)(a1 + 24);
  if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
  {
    v174 = (unsigned int)(20 * v171);
    v175 = v173 + 20;
  }
  else
  {
    v174 = (unsigned int)(12 * v171);
    v175 = v173 + 10;
  }
  *(_QWORD *)(a1 + 896) = v174 + v175;
LABEL_553:
  v176 = (_QWORD *)TIFFmallocExt(a1, v200);
  if ( !v176 )
  {
    v167 = "TIFFWriteDirectorySec";
LABEL_555:
    TIFFErrorExtR(a1, v167, "Out of memory", v26);
    goto LABEL_524;
  }
  v177 = (char *)(a1 + 16);
  if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
  {
    *v176 = (unsigned int)v198;
    if ( *v177 < 0 )
      TIFFSwabLong8(v176);
    v181 = 0;
    v182 = v176 + 1;
    v183 = v15;
    if ( v198 )
    {
      do
      {
        *v182 = *v183;
        if ( *v177 < 0 )
          TIFFSwabShort(v182);
        v182[1] = v183[1];
        if ( *v177 < 0 )
          TIFFSwabShort(v182 + 1);
        TIFFmemcpy(v182 + 2, v183 + 4, 8u);
        if ( *v177 < 0 )
          TIFFSwabLong8(v182 + 2);
        TIFFmemcpy(v182 + 6, v183 + 8, 8u);
        v182 += 10;
        v183 += 16;
        ++v181;
      }
      while ( v181 < v198 );
      v15 = *(_WORD **)v199;
      v177 = (char *)(a1 + 16);
    }
    TIFFmemcpy(v182, (const void *)(a1 + 32), 8u);
    if ( *v177 < 0 )
      TIFFSwabLong8(v182);
  }
  else
  {
    *(_WORD *)v176 = v198;
    if ( *v177 < 0 )
      TIFFSwabShort(v176);
    v178 = 0;
    v179 = (_WORD *)v176 + 1;
    v180 = v15;
    if ( v198 )
    {
      do
      {
        *v179 = *v180;
        if ( *v177 < 0 )
          TIFFSwabShort(v179);
        v179[1] = v180[1];
        if ( *v177 < 0 )
          TIFFSwabShort(v179 + 1);
        Src = *((_DWORD *)v180 + 2);
        TIFFmemcpy(v179 + 2, &Src, 4u);
        if ( *v177 < 0 )
          TIFFSwabLong(v179 + 2);
        TIFFmemcpy(v179 + 4, v180 + 8, 4u);
        v179 += 6;
        v180 += 16;
        ++v178;
      }
      while ( v178 < v198 );
      v15 = *(_WORD **)v199;
      v177 = (char *)(a1 + 16);
    }
    v117 = *v177 >= 0;
    Src = *(_DWORD *)(a1 + 32);
    if ( !v117 )
      TIFFSwabLong(&Src);
    TIFFmemcpy(v179, &Src, 4u);
    v177 = (char *)(a1 + 16);
  }
  TIFFfreeExt(a1, v15);
  if ( !(unsigned int)TIFFSeekOK(a1, *(_QWORD *)(a1 + 24)) )
  {
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "IO error writing directory at seek to offset", v184);
    TIFFfreeExt(a1, v176);
    return 0;
  }
  v185 = v200;
  if ( (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD))(a1 + 1192))(*(_QWORD *)(a1 + 1176), v176, v200) != v185 )
  {
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "IO error writing directory", v186);
    TIFFfreeExt(a1, v176);
    return 0;
  }
  TIFFfreeExt(a1, v176);
  if ( !v218 || *(_BYTE *)(a1 + 409) )
  {
LABEL_599:
    v188 = v219;
    *(_BYTE *)(a1 + 409) = 1;
    if ( v188 )
    {
      v189 = *(_DWORD *)(a1 + 16);
      if ( (v189 & 0x2000) != 0 && !*(_WORD *)(a1 + 888) )
        *(_DWORD *)(a1 + 16) = v189 & 0xFFFFDFFF;
    }
    if ( !(unsigned int)TIFFCheckDirNumberAndOffset(a1, *(unsigned int *)(a1 + 848), *(_QWORD *)(a1 + 24)) )
      TIFFErrorExtR(
        a1,
        "TIFFWriteDirectorySec",
        "Starting directory %u at offset 0x%llx (%llu) might cause an IFD loop",
        *(unsigned int *)(a1 + 848));
    if ( v188 )
    {
      TIFFFreeDirectory(a1);
      v190 = *(void (__fastcall **)(__int64))(a1 + 1048);
      *(_DWORD *)(a1 + 16) &= 0xFFDFFFF7;
      v190(a1);
      TIFFCreateDirectory(a1);
    }
    else
    {
      *(_QWORD *)(a1 + 424) = *(_QWORD *)(a1 + 416);
    }
    return 1;
  }
  if ( (*(_DWORD *)v177 & 0x2000) != 0 && (*(_DWORD *)(a1 + 76) & 0x20000) == 0 )
  {
    v187 = 0;
    goto LABEL_596;
  }
  v187 = *(_DWORD *)(a1 + 852);
  if ( v187 != -1 )
  {
LABEL_596:
    *(_DWORD *)(a1 + 848) = v187;
    if ( (*(_DWORD *)(a1 + 16) & 0x2000) == 0 || (*(_DWORD *)(a1 + 76) & 0x20000) != 0 )
      ++*(_DWORD *)(a1 + 852);
    goto LABEL_599;
  }
  v191 = TIFFNumberOfDirectories(a1);
  *(_DWORD *)(a1 + 852) = v191;
  *(_DWORD *)(a1 + 848) = v191;
  TIFFErrorExtR(
    a1,
    "TIFFWriteDirectorySec",
    "tif_curdircount is TIFF_NON_EXISTENT_DIR_NUMBER, not expected !! Line %d",
    1330);
  TIFFfreeExt(a1, v176);
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
