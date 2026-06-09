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
  __int64 v12; // r9
  const char *v13; // r8
  unsigned __int64 v15; // rbx
  _WORD *v16; // r13
  __int64 v17; // r9
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r9
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // r9
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  unsigned __int64 v47; // rax
  __int16 v48; // bx
  __int64 v49; // rax
  __int64 v50; // r9
  void *v51; // rsi
  unsigned __int16 v52; // r9
  unsigned __int16 v53; // r8
  _WORD *i; // rdx
  int v55; // ebx
  int v56; // ebx
  int v57; // eax
  unsigned __int64 v58; // rax
  __int16 v59; // bx
  __int64 v60; // rax
  void *v61; // rsi
  unsigned __int16 v62; // r9
  unsigned __int16 v63; // r8
  _WORD *j; // rdx
  int v65; // ebx
  int v66; // ebx
  unsigned __int64 v67; // rax
  __int16 v68; // bx
  __int64 v69; // rax
  void *v70; // rsi
  unsigned __int16 v71; // r9
  unsigned __int16 v72; // r8
  _WORD *k; // rdx
  int v74; // ebx
  int v75; // ebx
  __int64 v76; // r14
  unsigned __int64 v77; // rax
  char *v78; // rax
  char *v79; // rsi
  int v80; // ebx
  int v81; // ebx
  int v82; // eax
  unsigned __int64 v83; // rcx
  bool v84; // cf
  unsigned __int64 v85; // rax
  void *v86; // rsi
  unsigned __int64 v87; // rax
  __int16 v88; // bx
  __int64 v89; // rax
  void *v90; // rsi
  unsigned __int16 v91; // r9
  unsigned __int16 v92; // r8
  _WORD *m; // rdx
  int v94; // ebx
  int v95; // ebx
  __int64 v96; // rax
  __int64 v97; // rcx
  char *v98; // rsi
  __int64 v99; // rcx
  __int64 v100; // rcx
  __int64 v101; // rcx
  __int64 v102; // rcx
  __int64 v103; // rcx
  int v104; // ebx
  unsigned __int64 v105; // rcx
  unsigned __int64 v106; // rax
  unsigned __int64 v107; // rax
  __int64 n; // r14
  unsigned int *v109; // rsi
  unsigned __int16 v110; // dx
  int v111; // eax
  unsigned __int64 v112; // rax
  __int64 v113; // rax
  int v114; // eax
  __int64 v115; // rdx
  __int64 v116; // r8
  __int64 v117; // r9
  __int64 v118; // rdx
  __int64 v119; // r8
  __int64 v120; // r9
  unsigned int v121; // eax
  unsigned __int64 v122; // rcx
  __int64 v123; // rdx
  __int64 v124; // rax
  __int64 v125; // rax
  __int64 v126; // rdx
  __int64 v127; // rsi
  unsigned __int16 *v128; // r8
  unsigned __int64 v129; // kr08_8
  __int64 v130; // kr10_8
  int v131; // eax
  unsigned __int64 v132; // rax
  unsigned __int64 v133; // rax
  int v134; // eax
  unsigned __int64 v135; // rcx
  unsigned __int64 v136; // rax
  void *v137; // rsi
  unsigned __int64 v138; // rax
  unsigned __int64 v139; // rcx
  void *v140; // rsi
  void *v141; // rsi
  void *v142; // rsi
  bool v143; // zf
  int v144; // eax
  _QWORD *v145; // rsi
  unsigned int v146; // eax
  __int64 v147; // rax
  void *v148; // r14
  int v149; // r8d
  _DWORD *v150; // rcx
  signed __int64 v151; // r9
  unsigned int v152; // eax
  int v153; // eax
  __int64 *v154; // rsi
  __int64 v155; // rax
  int v156; // r8d
  _DWORD *v157; // rcx
  unsigned int v158; // edx
  __int64 v159; // r15
  __int64 v160; // rax
  __int64 v161; // rcx
  __int64 v162; // r9
  unsigned int v163; // r14d
  __int64 ii; // rsi
  unsigned __int64 v165; // rax
  unsigned __int64 v166; // rcx
  __int64 v167; // r15
  __int64 v168; // rax
  __int64 v169; // rcx
  __int64 v170; // r9
  unsigned int v171; // r14d
  __int64 jj; // rsi
  __int64 v173; // r15
  __int64 v174; // rax
  __int64 v175; // rcx
  __int64 v176; // r9
  unsigned int v177; // r14d
  __int64 kk; // rsi
  __int64 v179; // r15
  __int64 v180; // rax
  __int64 v181; // rcx
  __int64 v182; // r9
  unsigned int v183; // r14d
  __int64 mm; // rsi
  void *v185; // rsi
  void *v186; // rsi
  void *v187; // rsi
  __int64 v188; // rax
  unsigned __int64 v189; // rax
  unsigned __int64 v190; // rax
  const char *v191; // rdx
  unsigned int v192; // eax
  const char *v193; // r8
  const char *v194; // rdx
  int v195; // eax
  _WORD *v196; // rcx
  __int64 v197; // rcx
  __int64 v198; // rax
  __int64 v199; // rcx
  __int64 v200; // rdx
  __int64 v201; // r8
  _QWORD *v202; // r12
  char *v203; // rbx
  unsigned int v204; // r15d
  _WORD *v205; // rsi
  _WORD *v206; // r14
  __int64 v207; // rdx
  __int64 v208; // r8
  __int64 v209; // r9
  unsigned int v210; // r15d
  _WORD *v211; // rsi
  _WORD *v212; // r14
  __int64 v213; // r9
  __int64 v214; // rsi
  __int64 v215; // r9
  int v216; // eax
  int v217; // ebx
  int v218; // eax
  void (__fastcall *v219)(__int64); // rax
  int v220; // eax
  int v221; // [rsp+28h] [rbp-89h]
  int v222; // [rsp+30h] [rbp-81h]
  int v223; // [rsp+30h] [rbp-81h]
  size_t Size; // [rsp+38h] [rbp-79h]
  void *v225; // [rsp+40h] [rbp-71h]
  void *v226; // [rsp+40h] [rbp-71h]
  int v227; // [rsp+48h] [rbp-69h] BYREF
  int v228[2]; // [rsp+50h] [rbp-61h]
  unsigned int v229; // [rsp+58h] [rbp-59h]
  unsigned __int16 v230; // [rsp+5Ch] [rbp-55h] BYREF
  __int16 v231[2]; // [rsp+60h] [rbp-51h] BYREF
  unsigned int v232; // [rsp+64h] [rbp-4Dh]
  int v233; // [rsp+68h] [rbp-49h]
  _BYTE v234[4]; // [rsp+70h] [rbp-41h] BYREF
  _BYTE v235[4]; // [rsp+74h] [rbp-3Dh] BYREF
  _BYTE v236[4]; // [rsp+78h] [rbp-39h] BYREF
  _BYTE v237[4]; // [rsp+7Ch] [rbp-35h] BYREF
  _BYTE v238[4]; // [rsp+80h] [rbp-31h] BYREF
  _BYTE v239[4]; // [rsp+84h] [rbp-2Dh] BYREF
  _BYTE v240[4]; // [rsp+88h] [rbp-29h] BYREF
  _BYTE v241[4]; // [rsp+8Ch] [rbp-25h] BYREF
  unsigned int v242; // [rsp+90h] [rbp-21h] BYREF
  int v243; // [rsp+94h] [rbp-1Dh] BYREF
  void *v244[2]; // [rsp+98h] [rbp-19h] BYREF
  char *Str; // [rsp+A8h] [rbp-9h] BYREF
  int Src; // [rsp+118h] [rbp+67h] BYREF
  int v247; // [rsp+120h] [rbp+6Fh]
  int v248; // [rsp+128h] [rbp+77h]
  _QWORD *v249; // [rsp+130h] [rbp+7Fh]

  v249 = a4;
  v248 = a3;
  v247 = a2;
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
        v13 = "Error post-encoding before directory write";
LABEL_6:
        TIFFErrorExtR(a1, "TIFFWriteDirectorySec", v13, v12);
        return 0;
      }
    }
    (*(void (__fastcall **)(__int64))(a1 + 1032))(a1);
    if ( *(__int64 *)(a1 + 1136) > 0 && (*(_BYTE *)(a1 + 16) & 0x40) != 0 && !(unsigned int)TIFFFlushData1(a1) )
    {
      v13 = "Error flushing data before directory write";
      goto LABEL_6;
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
  v15 = a1 + 416;
  v16 = 0;
  *(_QWORD *)v228 = 0;
  v229 = 0;
  while ( 1 )
  {
    v227 = 0;
    v17 = 8;
    if ( !v16 )
      *(_QWORD *)v15 = 0;
    if ( !v5 )
      goto LABEL_359;
    if ( (*(_BYTE *)(a1 + 72) & 2) != 0 )
    {
      if ( *(_DWORD *)(a1 + 88) > 0xFFFFu )
      {
        if ( v16 )
        {
          v143 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 88);
          if ( !v143 )
            TIFFSwabLong(&Src, v8, v10, 8);
          LODWORD(Size) = 4;
          LOWORD(v221) = 4;
          v18 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 256, v221, 1, Size, &Src);
        }
        else
        {
          v227 = 1;
          v18 = 1;
        }
      }
      else if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 88);
        if ( !v143 )
          TIFFSwabShort(&Src, v8, v10, 8);
        LODWORD(Size) = 2;
        LOWORD(v221) = 3;
        v18 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 256, v221, 1, Size, &Src);
      }
      else
      {
        v227 = 1;
        v18 = 1;
      }
      if ( !v18 )
        goto LABEL_523;
      if ( *(_DWORD *)(a1 + 92) > 0xFFFFu )
      {
        if ( v16 )
        {
          v143 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 92);
          if ( !v143 )
            TIFFSwabLong(&Src, v8, v10, v17);
          LODWORD(Size) = 4;
          LOWORD(v221) = 4;
          v19 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 257, v221, 1, Size, &Src);
        }
        else
        {
          ++v227;
          v19 = 1;
        }
      }
      else if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 92);
        if ( !v143 )
          TIFFSwabShort(&Src, v8, v10, v17);
        LODWORD(Size) = 2;
        LOWORD(v221) = 3;
        v19 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 257, v221, 1, Size, &Src);
      }
      else
      {
        ++v227;
        v19 = 1;
      }
      if ( !v19 )
        goto LABEL_523;
    }
    if ( (*(_BYTE *)(a1 + 72) & 4) != 0 )
    {
      if ( *(_DWORD *)(a1 + 100) > 0xFFFFu )
      {
        if ( v16 )
        {
          v143 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 100);
          if ( !v143 )
            TIFFSwabLong(&Src, v8, v10, v17);
          LODWORD(Size) = 4;
          LOWORD(v221) = 4;
          v20 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 322, v221, 1, Size, &Src);
        }
        else
        {
          ++v227;
          v20 = 1;
        }
      }
      else if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 100);
        if ( !v143 )
          TIFFSwabShort(&Src, v8, v10, v17);
        LODWORD(Size) = 2;
        LOWORD(v221) = 3;
        v20 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 322, v221, 1, Size, &Src);
      }
      else
      {
        ++v227;
        v20 = 1;
      }
      if ( !v20 )
        goto LABEL_523;
      if ( *(_DWORD *)(a1 + 104) > 0xFFFFu )
      {
        if ( v16 )
        {
          v143 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 104);
          if ( !v143 )
            TIFFSwabLong(&Src, v8, v10, v17);
          LODWORD(Size) = 4;
          LOWORD(v221) = 4;
          v21 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 323, v221, 1, Size, &Src);
        }
        else
        {
          ++v227;
          v21 = 1;
        }
      }
      else if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 104);
        if ( !v143 )
          TIFFSwabShort(&Src, v8, v10, v17);
        LODWORD(Size) = 2;
        LOWORD(v221) = 3;
        v21 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 323, v221, 1, Size, &Src);
      }
      else
      {
        ++v227;
        v21 = 1;
      }
      if ( !v21 )
      {
LABEL_523:
        if ( !v16 )
          return 0;
LABEL_524:
        TIFFfreeExt(a1, v16);
        return 0;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 8) != 0 )
    {
      if ( *(float *)(a1 + 160) < 0.0 )
        goto LABEL_525;
      if ( v16 )
      {
        DoubleToRational(v9, v234, v235);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v234, v23, v24, v25);
          TIFFSwabLong(v235, v26, v27, v28);
        }
        LODWORD(Size) = 8;
        LOWORD(v221) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 282, v221, 1, Size, v234) )
          goto LABEL_524;
      }
      else
      {
        v22 = *(_QWORD *)v15 + (((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8);
        ++v227;
        *(_QWORD *)(a1 + 416) = v22;
      }
      if ( *(float *)(a1 + 164) < 0.0 )
        goto LABEL_525;
      if ( v16 )
      {
        DoubleToRational(v9, v236, v237);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v236, v29, v30, v31);
          TIFFSwabLong(v237, v32, v33, v34);
        }
        LODWORD(Size) = 8;
        LOWORD(v221) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 283, v221, 1, Size, v236) )
          goto LABEL_524;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v227;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x10) != 0 )
    {
      if ( *(float *)(a1 + 172) < 0.0 )
        goto LABEL_525;
      if ( v16 )
      {
        DoubleToRational(v9, v238, v239);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v238, v35, v36, v37);
          TIFFSwabLong(v239, v38, v39, v40);
        }
        LODWORD(Size) = 8;
        LOWORD(v221) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 286, v221, 1, Size, v238) )
          goto LABEL_524;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v227;
      }
      if ( *(float *)(a1 + 176) < 0.0 )
      {
LABEL_525:
        TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRational", "Negative value is illegal", v17);
        goto LABEL_523;
      }
      if ( v16 )
      {
        DoubleToRational(v9, v240, v241);
        if ( *(char *)(a1 + 16) < 0 )
        {
          TIFFSwabLong(v240, v41, v42, v43);
          TIFFSwabLong(v241, v44, v45, v46);
        }
        LODWORD(Size) = 8;
        LOWORD(v221) = 5;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 287, v221, 1, Size, v240) )
          goto LABEL_524;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += ((unsigned int)~*(_DWORD *)(a1 + 16) >> 16) & 8;
        ++v227;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x20) != 0 )
    {
      if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 112);
        if ( !v143 )
          TIFFSwabLong(&Src, v8, v10, v17);
        LODWORD(Size) = 4;
        LOWORD(v221) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 254, v221, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v227;
      }
    }
    if ( (*(_BYTE *)(a1 + 72) & 0x40) != 0 )
    {
      v8 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v16 )
      {
        v48 = *(_WORD *)(a1 + 116);
        v49 = TIFFmallocExt(a1, v8);
        v51 = (void *)v49;
        if ( !v49 )
          goto LABEL_526;
        v52 = *(_WORD *)(a1 + 130);
        v53 = 0;
        for ( i = (_WORD *)v49; v53 < v52; ++v53 )
        {
          *i++ = v48;
          v52 = *(_WORD *)(a1 + 130);
        }
        v55 = v52;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v49, v52);
        LODWORD(Size) = 2 * v55;
        LOWORD(v221) = 3;
        v56 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 258, v221, v55, Size, v51);
        TIFFfreeExt(a1, v51);
        if ( !v56 )
          goto LABEL_524;
      }
      else
      {
        v47 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v47 = 8;
        if ( v8 > v47 )
          *(_QWORD *)(a1 + 416) += v8;
        ++v227;
      }
    }
    if ( *(char *)(a1 + 72) < 0 )
    {
      if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 120);
        if ( !v143 )
          TIFFSwabShort(&Src, v8, v10, v17);
        LODWORD(Size) = 2;
        LOWORD(v221) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 259, v221, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v227;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x100) != 0 )
    {
      if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 122);
        if ( !v143 )
          TIFFSwabShort(&Src, v8, v10, v17);
        LODWORD(Size) = 2;
        LOWORD(v221) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 262, v221, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v227;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x200) != 0 )
    {
      if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 124);
        if ( !v143 )
          TIFFSwabShort(&Src, v8, v10, v17);
        LODWORD(Size) = 2;
        LOWORD(v221) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 263, v221, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v227;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x400) != 0 )
    {
      if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 126);
        if ( !v143 )
          TIFFSwabShort(&Src, v8, v10, v17);
        LODWORD(Size) = 2;
        LOWORD(v221) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 266, v221, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v227;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x8000) != 0 )
    {
      if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 128);
        if ( !v143 )
          TIFFSwabShort(&Src, v8, v10, v17);
        LODWORD(Size) = 2;
        LOWORD(v221) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 274, v221, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v227;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x10000) != 0 )
    {
      if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 130);
        if ( !v143 )
          TIFFSwabShort(&Src, v8, v10, v17);
        LODWORD(Size) = 2;
        LOWORD(v221) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 277, v221, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v227;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x20000) != 0 )
    {
      if ( *(_DWORD *)(a1 + 132) > 0xFFFFu )
      {
        if ( v16 )
        {
          v143 = *(_BYTE *)(a1 + 16) >= 0;
          Src = *(_DWORD *)(a1 + 132);
          if ( !v143 )
            TIFFSwabLong(&Src, v8, v10, v17);
          LODWORD(Size) = 4;
          LOWORD(v221) = 4;
          v57 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 278, v221, 1, Size, &Src);
        }
        else
        {
          ++v227;
          v57 = 1;
        }
      }
      else if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_DWORD *)(a1 + 132);
        if ( !v143 )
          TIFFSwabShort(&Src, v8, v10, v17);
        LODWORD(Size) = 2;
        LOWORD(v221) = 3;
        v57 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 278, v221, 1, Size, &Src);
      }
      else
      {
        ++v227;
        v57 = 1;
      }
      if ( !v57 )
        goto LABEL_523;
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x40000) != 0 )
    {
      v8 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v16 )
      {
        v59 = *(_WORD *)(a1 + 136);
        v60 = TIFFmallocExt(a1, v8);
        v61 = (void *)v60;
        if ( !v60 )
          goto LABEL_526;
        v62 = *(_WORD *)(a1 + 130);
        v63 = 0;
        for ( j = (_WORD *)v60; v63 < v62; ++v63 )
        {
          *j++ = v59;
          v62 = *(_WORD *)(a1 + 130);
        }
        v65 = v62;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v60, v62);
        LODWORD(Size) = 2 * v65;
        LOWORD(v221) = 3;
        v66 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 280, v221, v65, Size, v61);
        TIFFfreeExt(a1, v61);
        if ( !v66 )
          goto LABEL_524;
      }
      else
      {
        v58 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v58 = 8;
        if ( v8 > v58 )
          *(_QWORD *)(a1 + 416) += v8;
        ++v227;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x80000) != 0 )
    {
      v8 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v16 )
      {
        v68 = *(_WORD *)(a1 + 138);
        v69 = TIFFmallocExt(a1, v8);
        v70 = (void *)v69;
        if ( !v69 )
          goto LABEL_526;
        v71 = *(_WORD *)(a1 + 130);
        v72 = 0;
        for ( k = (_WORD *)v69; v72 < v71; ++v72 )
        {
          *k++ = v68;
          v71 = *(_WORD *)(a1 + 130);
        }
        v74 = v71;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v69, v71);
        LODWORD(Size) = 2 * v74;
        LOWORD(v221) = 3;
        v75 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 281, v221, v74, Size, v70);
        TIFFfreeExt(a1, v70);
        if ( !v75 )
          goto LABEL_524;
      }
      else
      {
        v67 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v67 = 8;
        if ( v8 > v67 )
          *(_QWORD *)(a1 + 416) += v8;
        ++v227;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x100000) != 0 )
    {
      if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 170);
        if ( !v143 )
          TIFFSwabShort(&Src, v8, v10, v17);
        LODWORD(Size) = 2;
        LOWORD(v221) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 284, v221, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v227;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x400000) != 0 )
    {
      if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 168);
        if ( !v143 )
          TIFFSwabShort(&Src, v8, v10, v17);
        LODWORD(Size) = 2;
        LOWORD(v221) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 296, v221, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v227;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x800000) != 0 )
    {
      if ( v16 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 180, 2);
        LODWORD(Size) = 4;
        LOWORD(v221) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 297, v221, 2, Size, (void *)(a1 + 180)) )
          goto LABEL_524;
      }
      else
      {
        ++v227;
      }
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x1000000) != 0
      && !(unsigned int)TIFFWriteDirectoryTagLongLong8Array(
                          a1,
                          (int)&v227,
                          (int)v16,
                          *(_DWORD *)(a1 + 228),
                          *(void **)(a1 + 240))
      || (*(_DWORD *)(a1 + 72) & 0x2000000) != 0
      && ((*(_DWORD *)(a1 + 16) & 0x400) != 0 || *(_QWORD *)(a1 + 232))
      && !(unsigned int)TIFFWriteDirectoryTagLongLong8Array(
                          a1,
                          (int)&v227,
                          (int)v16,
                          *(_DWORD *)(a1 + 228),
                          *(void **)(a1 + 232)) )
    {
      goto LABEL_523;
    }
    if ( (*(_DWORD *)(a1 + 72) & 0x4000000) != 0 )
    {
      v76 = (unsigned int)(1 << *(_BYTE *)(a1 + 116));
      v8 = 2LL * (unsigned int)(3 * v76);
      if ( v16 )
      {
        v78 = (char *)TIFFmallocExt(a1, v8);
        v79 = v78;
        if ( !v78 )
        {
          v191 = "TIFFWriteDirectoryTagColormap";
          goto LABEL_555;
        }
        TIFFmemcpy(v78, *(const void **)(a1 + 184), 2 * v76);
        TIFFmemcpy(&v79[2 * v76], *(const void **)(a1 + 192), 2 * v76);
        TIFFmemcpy(&v79[2 * (unsigned int)(2 * v76)], *(const void **)(a1 + 200), 2 * v76);
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v79, (unsigned int)(3 * v76));
        LODWORD(Size) = 6 * v76;
        LOWORD(v221) = 3;
        v80 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 320, v221, 3 * (int)v76, Size, v79);
        TIFFfreeExt(a1, v79);
        if ( !v80 )
          goto LABEL_524;
        v7 = 1;
      }
      else
      {
        v77 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v77 = 8;
        if ( v8 > v77 )
          *(_QWORD *)(a1 + 416) += v8;
        ++v227;
        v7 = 1;
      }
    }
    if ( *(int *)(a1 + 72) < 0 && *(_WORD *)(a1 + 212) )
    {
      TIFFGetFieldDefaulted(a1, 338, &v230, v244);
      v81 = v230;
      v82 = *(_DWORD *)(a1 + 16);
      if ( v16 )
      {
        v86 = v244[0];
        if ( (v82 & 0x80u) != 0 )
          TIFFSwabArrayOfShort(v244[0], v230);
        LODWORD(Size) = 2 * v81;
        LOWORD(v221) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 338, v221, v81, Size, v86) )
          goto LABEL_524;
      }
      else
      {
        v83 = 2LL * v230;
        v84 = (v82 & 0x80000) != 0;
        v85 = 4;
        if ( v84 )
          v85 = 8;
        if ( v83 > v85 )
          *(_QWORD *)(a1 + 416) += v83;
        ++v227;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 1) != 0 )
    {
      v8 = 2LL * *(unsigned __int16 *)(a1 + 130);
      if ( v16 )
      {
        v88 = *(_WORD *)(a1 + 118);
        v89 = TIFFmallocExt(a1, v8);
        v90 = (void *)v89;
        if ( !v89 )
        {
LABEL_526:
          v191 = "TIFFWriteDirectoryTagShortPerSample";
          goto LABEL_555;
        }
        v91 = *(_WORD *)(a1 + 130);
        v92 = 0;
        for ( m = (_WORD *)v89; v92 < v91; ++v92 )
        {
          *m++ = v88;
          v91 = *(_WORD *)(a1 + 130);
        }
        v94 = v91;
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(v89, v91);
        LODWORD(Size) = 2 * v94;
        LOWORD(v221) = 3;
        v95 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 339, v221, v94, Size, v90);
        TIFFfreeExt(a1, v90);
        if ( !v95 )
          goto LABEL_524;
      }
      else
      {
        v87 = 4;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v87 = 8;
        if ( v8 > v87 )
          *(_QWORD *)(a1 + 416) += v8;
        ++v227;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 2) != 0
      && !(unsigned int)TIFFWriteDirectoryTagSampleformatArray(
                          a1,
                          (int)&v227,
                          (int)v16,
                          *(unsigned __int16 *)(a1 + 130),
                          *(void **)(a1 + 144))
      || (*(_BYTE *)(a1 + 76) & 4) != 0
      && !(unsigned int)TIFFWriteDirectoryTagSampleformatArray(
                          a1,
                          (int)&v227,
                          (int)v16,
                          *(unsigned __int16 *)(a1 + 130),
                          *(void **)(a1 + 152)) )
    {
      goto LABEL_523;
    }
    if ( (*(_BYTE *)(a1 + 76) & 8) != 0 )
    {
      if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 96);
        if ( !v143 )
          TIFFSwabLong(&Src, v8, v10, v17);
        LODWORD(Size) = 4;
        LOWORD(v221) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 32997, v221, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v227;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 0x10) != 0 )
    {
      if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        Src = *(_DWORD *)(a1 + 108);
        if ( !v143 )
          TIFFSwabLong(&Src, v8, v10, v17);
        LODWORD(Size) = 4;
        LOWORD(v221) = 4;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 32998, v221, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v227;
      }
    }
    if ( (*(_BYTE *)(a1 + 76) & 0x20) != 0 )
    {
      if ( v16 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 208, 2);
        LODWORD(Size) = 4;
        v15 = 3;
        LOWORD(v221) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 321, v221, 2, Size, (void *)(a1 + 208)) )
          goto LABEL_524;
        goto LABEL_276;
      }
      ++v227;
    }
    v15 = 3;
LABEL_276:
    if ( *(char *)(a1 + 76) < 0 )
    {
      if ( v16 )
      {
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfShort(a1 + 336, 2);
        LODWORD(Size) = 4;
        v15 = 3;
        LOWORD(v221) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 530, v221, 2, Size, (void *)(a1 + 336)) )
          goto LABEL_524;
      }
      else
      {
        ++v227;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x100) != 0 )
    {
      if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 340);
        if ( !v143 )
          TIFFSwabShort(&Src, v8, v10, v17);
        LODWORD(Size) = 2;
        LOWORD(v221) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 531, v221, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v227;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x200) != 0 )
    {
      if ( v16 )
      {
        v96 = TIFFmallocExt(a1, 48);
        v98 = (char *)v96;
        if ( !v96 )
        {
          v191 = "TIFFWriteDirectoryTagCheckedRationalArray";
          goto LABEL_555;
        }
        DoubleToRational(v97, v96, v96 + 4);
        DoubleToRational(v99, v98 + 8, v98 + 12);
        DoubleToRational(v100, v98 + 16, v98 + 20);
        DoubleToRational(v101, v98 + 24, v98 + 28);
        DoubleToRational(v102, v98 + 32, v98 + 36);
        DoubleToRational(v103, v98 + 40, v98 + 44);
        if ( *(char *)(a1 + 16) < 0 )
          TIFFSwabArrayOfFloat(v98, 12);
        LODWORD(Size) = 48;
        LOWORD(v221) = 5;
        v104 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 532, v221, 6, Size, v98);
        TIFFfreeExt(a1, v98);
        if ( !v104 )
          goto LABEL_524;
        v15 = 3;
      }
      else
      {
        *(_QWORD *)(a1 + 416) += 48LL;
        ++v227;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x1000) != 0
      && !(unsigned int)TIFFWriteDirectoryTagTransferfunction(a1, (int)&v227, (int)v16) )
    {
      goto LABEL_523;
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x4000) != 0 )
    {
      v105 = *(unsigned int *)(a1 + 376);
      if ( v16 )
      {
        LODWORD(Size) = *(_DWORD *)(a1 + 376);
        LOWORD(v221) = 2;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(
                              a1,
                              (int)&v227,
                              (int)v16,
                              333,
                              v221,
                              v105,
                              Size,
                              *(void **)(a1 + 384)) )
          goto LABEL_524;
      }
      else
      {
        v106 = 4;
        v8 = (unsigned int)v105;
        if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
          v106 = 8;
        if ( v105 > v106 )
        {
          v107 = v105 + 1;
          if ( (v105 & 1) == 0 )
            v107 = *(unsigned int *)(a1 + 376);
          *(_QWORD *)(a1 + 416) += v107;
        }
        ++v227;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x40000) != 0 )
    {
      if ( v16 )
      {
        v143 = *(_BYTE *)(a1 + 16) >= 0;
        LOWORD(Src) = *(_WORD *)(a1 + 392);
        if ( !v143 )
          TIFFSwabShort(&Src, v8, v10, v17);
        LODWORD(Size) = 2;
        LOWORD(v221) = 3;
        if ( !(unsigned int)TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, 334, v221, 1, Size, &Src) )
          goto LABEL_524;
      }
      else
      {
        ++v227;
      }
    }
    if ( (*(_DWORD *)(a1 + 76) & 0x20000) != 0 && !(unsigned int)TIFFWriteDirectoryTagSubifd(a1, (int)&v227, (int)v16) )
      goto LABEL_523;
    for ( n = 0; (unsigned __int64)(unsigned int)n < *(_QWORD *)(a1 + 1240); n = (unsigned int)(n + 1) )
    {
      v109 = *(unsigned int **)(*(_QWORD *)(a1 + 1232) + 8 * n);
      v110 = *((_WORD *)v109 + 12);
      if ( v110 >= 0x42u )
      {
        v111 = *(_DWORD *)(a1 + 4 * ((unsigned __int64)v110 >> 5) + 72);
        if ( _bittest(&v111, v110 & 0x1F) )
        {
          switch ( v109[4] )
          {
            case 1u:
              TIFFGetField(a1, *v109, &Str);
              v15 = (unsigned __int64)Str;
              v121 = strlen_0(Str);
              if ( v16 )
              {
                LODWORD(Size) = v121;
                LOWORD(v221) = 2;
                v114 = TIFFWriteDirectoryTagData(
                         a1,
                         (int)&v227,
                         (int)v16,
                         *(unsigned __int16 *)v109,
                         v221,
                         v121,
                         Size,
                         (void *)v15);
                goto LABEL_357;
              }
              v122 = 4;
              v123 = v121;
              if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                v122 = 8;
              if ( v121 > v122 )
              {
                v143 = (v121 & 1) == 0;
                v124 = v121 + 1LL;
                if ( v143 )
                  v124 = v123;
                *(_QWORD *)(a1 + 416) += v124;
              }
              ++v227;
              break;
            case 4u:
              TIFFGetField(a1, *v109, v231);
              if ( v16 )
              {
                v143 = *(_BYTE *)(a1 + 16) >= 0;
                v15 = *(unsigned __int16 *)v109;
                LOWORD(Src) = v231[0];
                if ( !v143 )
                  TIFFSwabShort(&Src, v118, v119, v120);
                LODWORD(Size) = 2;
                LOWORD(v221) = 3;
                v114 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, (unsigned __int16)v15, v221, 1, Size, &Src);
LABEL_357:
                if ( !v114 )
                  goto LABEL_524;
                continue;
              }
              ++v227;
              break;
            case 6u:
              TIFFGetField(a1, *v109, &v243);
              if ( v16 )
              {
                v143 = *(_BYTE *)(a1 + 16) >= 0;
                v15 = *(unsigned __int16 *)v109;
                Src = v243;
                if ( !v143 )
                  TIFFSwabLong(&Src, v115, v116, v117);
                LODWORD(Size) = 4;
                LOWORD(v221) = 4;
                v114 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, (unsigned __int16)v15, v221, 1, Size, &Src);
                goto LABEL_357;
              }
              ++v227;
              break;
            case 0x28u:
              TIFFGetField(a1, *v109, &v242);
              if ( v16 )
              {
                LODWORD(Size) = v242;
                LOWORD(v221) = 7;
                v114 = TIFFWriteDirectoryTagData(
                         a1,
                         (int)&v227,
                         (int)v16,
                         *(unsigned __int16 *)v109,
                         v221,
                         v242,
                         Size,
                         v244[1]);
                goto LABEL_357;
              }
              v112 = 4;
              if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                v112 = 8;
              if ( v242 > v112 )
              {
                v113 = v242 + 1LL;
                if ( (v242 & 1) == 0 )
                  v113 = v242;
                *(_QWORD *)(a1 + 416) += v113;
              }
              ++v227;
              break;
            default:
              v192 = TIFFFieldTag(v109);
              TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Cannot write tag %u (%s)", v192);
              goto LABEL_523;
          }
        }
      }
    }
LABEL_359:
    v125 = 0;
    v233 = 0;
    if ( *(_DWORD *)(a1 + 396) )
    {
      while ( 1 )
      {
        v126 = *(_QWORD *)(a1 + 400);
        v127 = 3 * v125;
        v128 = *(unsigned __int16 **)(v126 + 24 * v125);
        v129 = v15;
        v130 = v7;
        v7 = *v128;
        v15 = *(unsigned int *)(v126 + 24 * v125 + 8);
        v131 = *((_DWORD *)v128 + 2) - 1;
        LOWORD(Src) = *v128;
        switch ( v131 )
        {
          case 0:
            if ( !v16 )
              goto LABEL_362;
            LODWORD(Size) = v15;
            LOWORD(v221) = 1;
            v134 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v227,
                     (int)v16,
                     (unsigned __int16)v7,
                     v221,
                     v15,
                     Size,
                     *(void **)(v126 + 8 * v127 + 16));
            goto LABEL_370;
          case 1:
            if ( !v16 )
              goto LABEL_362;
            LODWORD(Size) = v15;
            LOWORD(v221) = 2;
            v134 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v227,
                     (int)v16,
                     (unsigned __int16)v7,
                     v221,
                     v15,
                     Size,
                     *(void **)(v126 + 8 * v127 + 16));
            goto LABEL_370;
          case 2:
            if ( !v16 )
            {
              v135 = 2 * v15;
              goto LABEL_380;
            }
            v137 = *(void **)(v126 + 8 * v127 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfShort(v137, v15);
            LODWORD(Size) = 2 * v15;
            LOWORD(v221) = 3;
            v134 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, (unsigned __int16)v7, v221, v15, Size, v137);
            goto LABEL_370;
          case 3:
            if ( !v16 )
            {
              v135 = 4 * v15;
              goto LABEL_380;
            }
            v141 = *(void **)(v126 + 8 * v127 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v141, v15);
            LODWORD(Size) = 4 * v15;
            LOWORD(v221) = 4;
            v134 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, (unsigned __int16)v7, v221, v15, Size, v141);
            goto LABEL_370;
          case 4:
            v232 = TIFFFieldSetGetSize(v128);
            v158 = v232;
            if ( v232 == 8 )
            {
              if ( !v16 )
                goto LABEL_441;
              v159 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v127 + 16);
              v160 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v15));
              v7 = v160;
              if ( !v160 )
              {
                TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRationalDoubleArray", "Out of memory", v162);
                TIFFfreeExt(a1, *(_QWORD *)v228);
                return 0;
              }
              v163 = 0;
              for ( ii = v160; v163 < (unsigned int)v15; ++v163 )
              {
                DoubleToRational(v161, ii, ii + 4);
                ii += 8;
                v159 += 8;
              }
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v15));
              v225 = (void *)v7;
              LODWORD(Size) = 8 * v15;
              v222 = v15;
              LOWORD(v221) = 5;
              goto LABEL_448;
            }
            if ( !v16 )
              goto LABEL_451;
            v167 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v127 + 16);
            v168 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v15));
            v7 = v168;
            if ( !v168 )
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedRationalArray", "Out of memory", v170);
              TIFFfreeExt(a1, *(_QWORD *)v228);
              return 0;
            }
            v171 = 0;
            for ( jj = v168; v171 < (unsigned int)v15; ++v171 )
            {
              DoubleToRational(v169, jj, jj + 4);
              jj += 8;
              v167 += 4;
            }
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v15));
            v226 = (void *)v7;
            LODWORD(Size) = 8 * v15;
            v223 = v15;
            LOWORD(v221) = 5;
            goto LABEL_462;
          case 5:
            if ( !v16 )
              goto LABEL_362;
            LODWORD(Size) = v15;
            LOWORD(v221) = 6;
            v134 = TIFFWriteDirectoryTagData(
                     a1,
                     (int)&v227,
                     (int)v16,
                     (unsigned __int16)v7,
                     v221,
                     v15,
                     Size,
                     *(void **)(v126 + 8 * v127 + 16));
            goto LABEL_370;
          case 6:
            if ( v16 )
            {
              LODWORD(Size) = v15;
              LOWORD(v221) = 7;
              v134 = TIFFWriteDirectoryTagData(
                       a1,
                       (int)&v227,
                       (int)v16,
                       (unsigned __int16)v7,
                       v221,
                       v15,
                       Size,
                       *(void **)(v126 + 8 * v127 + 16));
              goto LABEL_370;
            }
LABEL_362:
            v132 = 4;
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
              v132 = 8;
            if ( v15 > v132 )
            {
              v133 = v15 + 1;
              if ( (v15 & 1) == 0 )
                v133 = v15;
              *(_QWORD *)(a1 + 416) += v133;
            }
            goto LABEL_368;
          case 7:
            if ( v16 )
            {
              v140 = *(void **)(v126 + 8 * v127 + 16);
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfShort(v140, v15);
              LODWORD(Size) = 2 * v15;
              LOWORD(v221) = 8;
              v134 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, (unsigned __int16)v7, v221, v15, Size, v140);
              goto LABEL_370;
            }
            v138 = 4;
            v139 = 2 * v15;
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
              v138 = 8;
            if ( v139 > v138 )
            {
              *(_QWORD *)(a1 + 416) += v139;
              ++v227;
              goto LABEL_498;
            }
            goto LABEL_368;
          case 8:
            if ( !v16 )
            {
              v135 = 4 * v15;
              goto LABEL_380;
            }
            v142 = *(void **)(v126 + 8 * v127 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v142, v15);
            LODWORD(Size) = 4 * v15;
            LOWORD(v221) = 9;
            v134 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, (unsigned __int16)v7, v221, v15, Size, v142);
            goto LABEL_370;
          case 9:
            v232 = TIFFFieldSetGetSize(v128);
            v158 = v232;
            if ( v232 == 8 )
            {
              if ( v16 )
              {
                v173 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v127 + 16);
                v174 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v15));
                v7 = v174;
                if ( !v174 )
                {
                  TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSrationalDoubleArray", "Out of memory", v176);
                  TIFFfreeExt(a1, *(_QWORD *)v228);
                  return 0;
                }
                v177 = 0;
                for ( kk = v174; v177 < (unsigned int)v15; ++v177 )
                {
                  DoubleToSrational(v175, kk, kk + 4);
                  kk += 8;
                  v173 += 8;
                }
                if ( *(char *)(a1 + 16) < 0 )
                  TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v15));
                v225 = (void *)v7;
                LODWORD(Size) = 8 * v15;
                v222 = v15;
                LOWORD(v221) = 10;
LABEL_448:
                v16 = *(_WORD **)v228;
                v15 = (unsigned int)TIFFWriteDirectoryTagData(
                                      a1,
                                      (int)&v227,
                                      v228[0],
                                      (unsigned __int16)Src,
                                      v221,
                                      v222,
                                      Size,
                                      v225);
                TIFFfreeExt(a1, v7);
                if ( !(_DWORD)v15 )
                  goto LABEL_524;
              }
              else
              {
LABEL_441:
                v135 = 4LL * (unsigned int)(2 * v15);
LABEL_380:
                v136 = 4;
                if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                  v136 = 8;
                if ( v135 <= v136 )
                {
LABEL_368:
                  ++v227;
                }
                else
                {
                  *(_QWORD *)(a1 + 416) += v135;
                  ++v227;
                }
              }
            }
            else
            {
              if ( v16 )
              {
                v179 = *(_QWORD *)(*(_QWORD *)(a1 + 400) + 8 * v127 + 16);
                v180 = TIFFmallocExt(a1, 4LL * (unsigned int)(2 * v15));
                v7 = v180;
                if ( !v180 )
                {
                  TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSrationalArray", "Out of memory", v182);
                  TIFFfreeExt(a1, *(_QWORD *)v228);
                  return 0;
                }
                v183 = 0;
                for ( mm = v180; v183 < (unsigned int)v15; ++v183 )
                {
                  DoubleToSrational(v181, mm, mm + 4);
                  mm += 8;
                  v179 += 4;
                }
                if ( *(char *)(a1 + 16) < 0 )
                  TIFFSwabArrayOfFloat(v7, (unsigned int)(2 * v15));
                v226 = (void *)v7;
                LODWORD(Size) = 8 * v15;
                v223 = v15;
                LOWORD(v221) = 10;
LABEL_462:
                v16 = *(_WORD **)v228;
                v15 = (unsigned int)TIFFWriteDirectoryTagData(
                                      a1,
                                      (int)&v227,
                                      v228[0],
                                      (unsigned __int16)Src,
                                      v221,
                                      v223,
                                      Size,
                                      v226);
                TIFFfreeExt(a1, v7);
                if ( !(_DWORD)v15 )
                  goto LABEL_524;
                v158 = v232;
              }
              else
              {
LABEL_451:
                v165 = 4;
                v166 = 4LL * (unsigned int)(2 * v15);
                if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
                  v165 = 8;
                if ( v166 > v165 )
                  *(_QWORD *)(a1 + 416) += v166;
                ++v227;
              }
              if ( v158 != 4 )
                TIFFErrorExtR(
                  a1,
                  "TIFFLib: _TIFFWriteDirectorySec()",
                  "Rational2Double: .set_field_type is not 4 but %d",
                  v158);
            }
            goto LABEL_498;
          case 10:
            if ( !v16 )
            {
              v135 = 4 * v15;
              goto LABEL_380;
            }
            v185 = *(void **)(v126 + 8 * v127 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v185, v15);
            LODWORD(Size) = 4 * v15;
            LOWORD(v221) = 11;
            v134 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, (unsigned __int16)v7, v221, v15, Size, v185);
            goto LABEL_370;
          case 11:
            if ( !v16 )
            {
              v135 = 8 * v15;
              goto LABEL_380;
            }
            v186 = *(void **)(v126 + 8 * v127 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfDouble(v186, v15, v128, 8);
            LODWORD(Size) = 8 * v15;
            LOWORD(v221) = 12;
            v134 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, (unsigned __int16)v7, v221, v15, Size, v186);
            goto LABEL_370;
          case 12:
            if ( !v16 )
            {
              v135 = 4 * v15;
              goto LABEL_380;
            }
            v187 = *(void **)(v126 + 8 * v127 + 16);
            if ( *(char *)(a1 + 16) < 0 )
              TIFFSwabArrayOfFloat(v187, v15);
            LODWORD(Size) = 4 * v15;
            LOWORD(v221) = 13;
            v134 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, (unsigned __int16)v7, v221, v15, Size, v187);
LABEL_370:
            if ( !v134 )
              goto LABEL_524;
            goto LABEL_498;
          case 15:
            if ( v16 )
            {
              v144 = *(_DWORD *)(a1 + 16);
              v145 = *(_QWORD **)(v126 + 8 * v127 + 16);
              if ( (v144 & 0x80000) != 0 )
              {
                if ( (v144 & 0x80u) != 0 )
                  TIFFSwabArrayOfDouble(v145, v15, v128, 8);
                LODWORD(Size) = 8 * v15;
                LOWORD(v221) = 16;
                v146 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, (unsigned __int16)v7, v221, v15, Size, v145);
LABEL_415:
                v15 = v146;
                v143 = v146 == 0;
                goto LABEL_497;
              }
              v147 = TIFFmallocExt(a1, 4 * v15);
              v148 = (void *)v147;
              if ( !v147 )
              {
                v191 = "TIFFWriteDirectoryTagLong8Array";
                goto LABEL_555;
              }
              v149 = 0;
              v150 = (_DWORD *)v147;
              if ( (_DWORD)v15 )
              {
                while ( 1 )
                {
                  v151 = *v145;
                  if ( *v145 > 0xFFFFFFFF )
                    break;
                  *v150 = v151;
                  ++v145;
                  ++v150;
                  if ( ++v149 >= (unsigned int)v15 )
                    goto LABEL_420;
                }
                v193 = "Attempt to write unsigned long value %llu larger than 0xFFFFFFFF for tag %d in Classic TIFF file."
                       " TIFF file writing aborted";
                v194 = "TIFFWriteDirectoryTagLong8Array";
LABEL_534:
                TIFFErrorExtR(a1, v194, v193, v151);
                TIFFfreeExt(a1, v148);
                TIFFfreeExt(a1, v16);
                return 0;
              }
LABEL_420:
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v147, v15);
              LODWORD(Size) = 4 * v15;
              LOWORD(v221) = 4;
              v152 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, (unsigned __int16)v7, v221, v15, Size, v148);
LABEL_423:
              v15 = v152;
              TIFFfreeExt(a1, v148);
              v143 = (_DWORD)v15 == 0;
              goto LABEL_497;
            }
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) == 0 )
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedLong8Array", "LONG8 not allowed for ClassicTIFF", 8);
              v15 = 0;
              v143 = 1;
              goto LABEL_497;
            }
            goto LABEL_408;
          case 16:
            if ( v16 )
            {
              v153 = *(_DWORD *)(a1 + 16);
              v154 = *(__int64 **)(v126 + 8 * v127 + 16);
              if ( (v153 & 0x80000) != 0 )
              {
                if ( (v153 & 0x80u) != 0 )
                  TIFFSwabArrayOfDouble(v154, v15, v128, 8);
                LODWORD(Size) = 8 * v15;
                LOWORD(v221) = 17;
                v146 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, (unsigned __int16)v7, v221, v15, Size, v154);
                goto LABEL_415;
              }
              v155 = TIFFmallocExt(a1, 4 * v15);
              v148 = (void *)v155;
              if ( !v155 )
              {
                v191 = "TIFFWriteDirectoryTagSlong8Array";
                goto LABEL_555;
              }
              v156 = 0;
              v157 = (_DWORD *)v155;
              if ( (_DWORD)v15 )
              {
                while ( 1 )
                {
                  v151 = *v154;
                  if ( *v154 > 0x7FFFFFFF )
                    break;
                  if ( v151 < (__int64)0xFFFFFFFF80000000uLL )
                  {
                    v193 = "Attempt to write signed long value %lli smaller than 0x80000000 (-2147483648) for tag %d in C"
                           "lassic TIFF file. TIFF writing to file aborted";
                    goto LABEL_533;
                  }
                  *v157 = v151;
                  ++v154;
                  ++v157;
                  if ( ++v156 >= (unsigned int)v15 )
                    goto LABEL_436;
                }
                v193 = "Attempt to write signed long value %lli larger than 0x7FFFFFFF (2147483647) for tag %d in Classic"
                       " TIFF file. TIFF writing to file aborted";
LABEL_533:
                v194 = "TIFFWriteDirectoryTagSlong8Array";
                goto LABEL_534;
              }
LABEL_436:
              if ( *(char *)(a1 + 16) < 0 )
                TIFFSwabArrayOfFloat(v155, v15);
              LODWORD(Size) = 4 * v15;
              LOWORD(v221) = 9;
              v152 = TIFFWriteDirectoryTagData(a1, (int)&v227, (int)v16, (unsigned __int16)v7, v221, v15, Size, v148);
              goto LABEL_423;
            }
            if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
            {
LABEL_408:
              if ( 8 * v15 > 8 )
                *(_QWORD *)(a1 + 416) += 8 * v15;
              ++v227;
              v15 = 1;
              v143 = 0;
            }
            else
            {
              TIFFErrorExtR(a1, "TIFFWriteDirectoryTagCheckedSlong8Array", "SLONG8 not allowed for ClassicTIFF", 8);
              v15 = 0;
              v143 = 1;
            }
LABEL_497:
            if ( v143 )
              goto LABEL_523;
LABEL_498:
            v125 = (unsigned int)(v233 + 1);
            v233 = v125;
            if ( (unsigned int)v125 >= *(_DWORD *)(a1 + 396) )
              goto LABEL_499;
            break;
          case 17:
            v143 = (unsigned int)TIFFWriteDirectoryTagIfdIfd8Array(
                                   a1,
                                   (int)&v227,
                                   (int)v16,
                                   v15,
                                   *(void **)(v126 + 8 * v127 + 16)) == 0;
            goto LABEL_497;
          default:
            v7 = v130;
            v15 = v129;
            goto LABEL_498;
        }
      }
    }
LABEL_499:
    if ( v16 )
      break;
    v15 = a1 + 416;
    if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
      v188 = (unsigned int)(20 * v227 + 16);
    else
      v188 = (unsigned int)(12 * v227 + 6);
    *(_QWORD *)v15 = *(_QWORD *)(a1 + 416) + v188;
    *(_QWORD *)v228 = TIFFmallocExt(a1, 32LL * (unsigned int)v227);
    v16 = *(_WORD **)v228;
    if ( !*(_QWORD *)v228 )
    {
      v13 = "Out of memory";
      goto LABEL_6;
    }
    v5 = v247;
    if ( v247 )
    {
      if ( *(_QWORD *)(a1 + 24) )
      {
        if ( *(_QWORD *)v15 > *(_QWORD *)(a1 + 424) )
        {
          TIFFfreeExt(a1, *(_QWORD *)v228);
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
      v189 = *(_QWORD *)(a1 + 424);
      if ( !v189 || *(_QWORD *)v15 > v189 )
        *(_QWORD *)(a1 + 24) = ((*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 1200))(
                                  *(_QWORD *)(a1 + 1176),
                                  0,
                                  2)
                              + 1)
                             & 0xFFFFFFFFFFFFFFFEuLL;
    }
    if ( v249 )
      *v249 = *(_QWORD *)(a1 + 24);
    v8 = *(_QWORD *)(a1 + 24);
    if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
    {
      v10 = (unsigned int)(20 * v227 + 16);
      v190 = v10 + v8;
    }
    else
    {
      v10 = (unsigned int)(12 * v227 + 6);
      v190 = (unsigned int)(v8 + v10);
    }
    *(_QWORD *)(a1 + 880) = v190;
    v9 = (unsigned int)v10;
    v229 = v10;
    if ( v190 < v8 || v190 < (unsigned int)v10 )
    {
      TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Maximum TIFF file size exceeded", v12);
      TIFFfreeExt(a1, v16);
      return 0;
    }
    if ( (v190 & 1) != 0 )
      *(_QWORD *)(a1 + 880) = v190 + 1;
    v7 = 1;
  }
  if ( !v247 || (*(_DWORD *)(a1 + 76) & 0x20000) == 0 || *(_QWORD *)(a1 + 896) )
    goto LABEL_553;
  v195 = 0;
  v196 = v16;
  if ( !v227 )
  {
LABEL_549:
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "Cannot find SubIFD tag", 8);
    TIFFfreeExt(a1, v16);
    return 0;
  }
  while ( *v196 != 330 )
  {
    ++v195;
    v196 += 16;
    if ( v195 == v227 )
      goto LABEL_549;
  }
  v197 = *(_QWORD *)(a1 + 24);
  if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
  {
    v198 = (unsigned int)(20 * v195);
    v199 = v197 + 20;
  }
  else
  {
    v198 = (unsigned int)(12 * v195);
    v199 = v197 + 10;
  }
  *(_QWORD *)(a1 + 896) = v198 + v199;
LABEL_553:
  v202 = (_QWORD *)TIFFmallocExt(a1, v229);
  if ( !v202 )
  {
    v191 = "TIFFWriteDirectorySec";
LABEL_555:
    TIFFErrorExtR(a1, v191, "Out of memory", v50);
    goto LABEL_524;
  }
  v203 = (char *)(a1 + 16);
  if ( (*(_DWORD *)(a1 + 16) & 0x80000) != 0 )
  {
    *v202 = (unsigned int)v227;
    if ( *v203 < 0 )
      TIFFSwabLong8(v202);
    v210 = 0;
    v211 = v202 + 1;
    v212 = v16;
    if ( v227 )
    {
      do
      {
        *v211 = *v212;
        if ( *v203 < 0 )
          TIFFSwabShort(v211, v200, v201, v50);
        v211[1] = v212[1];
        if ( *v203 < 0 )
          TIFFSwabShort(v211 + 1, v200, v201, v50);
        TIFFmemcpy(v211 + 2, v212 + 4, 8u);
        if ( *v203 < 0 )
          TIFFSwabLong8(v211 + 2);
        TIFFmemcpy(v211 + 6, v212 + 8, 8u);
        v211 += 10;
        v212 += 16;
        ++v210;
      }
      while ( v210 < v227 );
      v16 = *(_WORD **)v228;
      v203 = (char *)(a1 + 16);
    }
    TIFFmemcpy(v211, (const void *)(a1 + 32), 8u);
    if ( *v203 < 0 )
      TIFFSwabLong8(v211);
  }
  else
  {
    *(_WORD *)v202 = v227;
    if ( *v203 < 0 )
      TIFFSwabShort(v202, v200, v201, v50);
    v204 = 0;
    v205 = (_WORD *)v202 + 1;
    v206 = v16;
    if ( v227 )
    {
      do
      {
        *v205 = *v206;
        if ( *v203 < 0 )
          TIFFSwabShort(v205, v200, v201, v50);
        v205[1] = v206[1];
        if ( *v203 < 0 )
          TIFFSwabShort(v205 + 1, v200, v201, v50);
        Src = *((_DWORD *)v206 + 2);
        TIFFmemcpy(v205 + 2, &Src, 4u);
        if ( *v203 < 0 )
          TIFFSwabLong(v205 + 2, v207, v208, v209);
        TIFFmemcpy(v205 + 4, v206 + 8, 4u);
        v205 += 6;
        v206 += 16;
        ++v204;
      }
      while ( v204 < v227 );
      v16 = *(_WORD **)v228;
      v203 = (char *)(a1 + 16);
    }
    v143 = *v203 >= 0;
    Src = *(_DWORD *)(a1 + 32);
    if ( !v143 )
      TIFFSwabLong(&Src, v200, v201, v50);
    TIFFmemcpy(v205, &Src, 4u);
    v203 = (char *)(a1 + 16);
  }
  TIFFfreeExt(a1, v16);
  if ( !(unsigned int)TIFFSeekOK(a1, *(_QWORD *)(a1 + 24)) )
  {
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "IO error writing directory at seek to offset", v213);
    TIFFfreeExt(a1, v202);
    return 0;
  }
  v214 = v229;
  if ( (*(__int64 (__fastcall **)(_QWORD, _QWORD *, _QWORD))(a1 + 1192))(*(_QWORD *)(a1 + 1176), v202, v229) != v214 )
  {
    TIFFErrorExtR(a1, "TIFFWriteDirectorySec", "IO error writing directory", v215);
    TIFFfreeExt(a1, v202);
    return 0;
  }
  TIFFfreeExt(a1, v202);
  if ( !v247 || *(_BYTE *)(a1 + 409) )
  {
LABEL_599:
    v217 = v248;
    *(_BYTE *)(a1 + 409) = 1;
    if ( v217 )
    {
      v218 = *(_DWORD *)(a1 + 16);
      if ( (v218 & 0x2000) != 0 && !*(_WORD *)(a1 + 888) )
        *(_DWORD *)(a1 + 16) = v218 & 0xFFFFDFFF;
    }
    if ( !(unsigned int)TIFFCheckDirNumberAndOffset(a1, *(unsigned int *)(a1 + 848), *(_QWORD *)(a1 + 24)) )
      TIFFErrorExtR(
        a1,
        "TIFFWriteDirectorySec",
        "Starting directory %u at offset 0x%llx (%llu) might cause an IFD loop",
        *(unsigned int *)(a1 + 848));
    if ( v217 )
    {
      TIFFFreeDirectory(a1);
      v219 = *(void (__fastcall **)(__int64))(a1 + 1048);
      *(_DWORD *)(a1 + 16) &= 0xFFDFFFF7;
      v219(a1);
      TIFFCreateDirectory(a1);
    }
    else
    {
      *(_QWORD *)(a1 + 424) = *(_QWORD *)(a1 + 416);
    }
    return 1;
  }
  if ( (*(_DWORD *)v203 & 0x2000) != 0 && (*(_DWORD *)(a1 + 76) & 0x20000) == 0 )
  {
    v216 = 0;
    goto LABEL_596;
  }
  v216 = *(_DWORD *)(a1 + 852);
  if ( v216 != -1 )
  {
LABEL_596:
    *(_DWORD *)(a1 + 848) = v216;
    if ( (*(_DWORD *)(a1 + 16) & 0x2000) == 0 || (*(_DWORD *)(a1 + 76) & 0x20000) != 0 )
      ++*(_DWORD *)(a1 + 852);
    goto LABEL_599;
  }
  v220 = TIFFNumberOfDirectories(a1);
  *(_DWORD *)(a1 + 852) = v220;
  *(_DWORD *)(a1 + 848) = v220;
  TIFFErrorExtR(
    a1,
    "TIFFWriteDirectorySec",
    "tif_curdircount is TIFF_NON_EXISTENT_DIR_NUMBER, not expected !! Line %d",
    1330);
  TIFFfreeExt(a1, v202);
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
