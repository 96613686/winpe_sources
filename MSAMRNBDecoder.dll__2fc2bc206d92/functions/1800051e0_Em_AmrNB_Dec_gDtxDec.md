# Em_AmrNB_Dec_gDtxDec

- ea: `0x1800051e0`
- end: `0x180005f97`
- name: `Em_AmrNB_Dec_gDtxDec`
- size: `3511`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x180003800`

## callees

- `0x180001400`
- `0x180004b5c`
- `0x180004bb4`
- `0x180004d24`
- `0x1800051e0`
- `0x18000671c`
- `0x1800067ac`
- `0x18000688c`
- `0x18000694c`
- `0x180007b6c`
- `0x180007e64`
- `0x180007eb4`
- `0x180008048`
- `0x180008078`
- `0x1800085b4`
- `0x180009ea0`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_gDtxDec(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  __int16 v4; // si
  __int64 v5; // rdi
  __int16 v6; // cx
  __int64 v7; // rdi
  int v8; // edx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned __int16 v12; // r8
  __int16 v13; // r9
  __int16 v14; // ax
  int v15; // eax
  unsigned __int16 i; // dx
  __int64 v17; // r10
  int v18; // edi
  int v19; // eax
  unsigned int v20; // ecx
  __int64 j; // rcx
  int v22; // ecx
  int k; // edx
  __int64 v24; // rcx
  unsigned __int16 v25; // r9
  int v26; // edi
  int m; // r8d
  int v28; // ecx
  int v29; // edx
  int v30; // r11d
  int v31; // edi
  int v32; // r14d
  __int64 v33; // r8
  int v34; // eax
  int v35; // edx
  __int16 v36; // ax
  int v37; // eax
  int v38; // ecx
  int v39; // eax
  int n; // edx
  __int64 v41; // rcx
  int v42; // eax
  __int16 v43; // dx
  __int16 v44; // ax
  __int64 v45; // r8
  int ii; // edi
  __int64 v47; // rdx
  __int16 v48; // dx
  __int16 v49; // ax
  int jj; // edx
  __int64 v51; // rcx
  int v52; // eax
  __int16 v53; // cx
  int v54; // eax
  __int16 v55; // ax
  int v56; // ecx
  int v57; // ecx
  int v58; // eax
  __int16 v59; // dx
  __int16 v60; // ax
  int v61; // ecx
  __int64 v62; // rax
  int v63; // edx
  unsigned int v64; // r9d
  __int64 v65; // rcx
  __int16 v66; // di
  __int64 v67; // r10
  __int64 v68; // rcx
  int v69; // r8d
  __int64 v70; // rdi
  int v71; // edx
  int v72; // ecx
  int v73; // eax
  int v74; // ecx
  __int16 v75; // dx
  __int16 v76; // r15
  __int16 v77; // di
  int v78; // r12d
  __int64 kk; // r14
  int v80; // edx
  int v81; // ecx
  __int16 v82; // ax
  int v83; // eax
  int v84; // edx
  int v85; // edx
  __int16 v86; // ax
  int v87; // eax
  __int64 v88; // rbx
  int mm; // edx
  __int64 v90; // rcx
  unsigned __int16 nn; // dx
  __int64 v92; // r8
  int v93; // eax
  __int64 v94; // r10
  int v95; // edx
  __int64 v96; // rcx
  int v97; // r11d
  int v98; // r11d
  int v99; // r11d
  __int64 i1; // rdi
  unsigned __int16 v101; // r9
  unsigned int v102; // r9d
  int v103; // edx
  int v104; // edi
  int v105; // ecx
  int v106; // eax
  int v107; // eax
  unsigned int v108; // edi
  int v109; // eax
  int v110; // r14d
  int v111; // eax
  int v112; // edi
  int v113; // eax
  int v114; // ecx
  __int64 v115; // rdx
  _WORD *v116; // rdi
  __int64 i2; // rcx
  int i3; // edi
  int v119; // eax
  __int64 v120; // r14
  int v121; // r9d
  int v122; // r15d
  int v123; // r12d
  __int64 i4; // rcx
  int i5; // edx
  __int64 v126; // rcx
  int v127; // eax
  int v128; // eax
  int v130; // [rsp+20h] [rbp-99h]
  int v131; // [rsp+30h] [rbp-89h]
  int v132; // [rsp+30h] [rbp-89h]
  __int64 v134; // [rsp+40h] [rbp-79h] BYREF
  __int64 v135; // [rsp+48h] [rbp-71h]
  _WORD v136[12]; // [rsp+50h] [rbp-69h] BYREF
  __int16 v137; // [rsp+68h] [rbp-51h] BYREF
  char v138[22]; // [rsp+6Ah] [rbp-4Fh] BYREF
  _OWORD v139[2]; // [rsp+80h] [rbp-39h] BYREF
  __int64 v140; // [rsp+A0h] [rbp-19h]

  v135 = a1;
  v2 = a2;
  v4 = 0x7FFF;
  if ( *(_WORD *)(a1 + 1036) && *(_WORD *)(a1 + 1032) )
  {
    v5 = *(__int16 *)(a1 + 1020);
    *(_WORD *)(a1 + 1026) = Em_AmrNB_Dec_dtx_log_en_adjust[*(__int16 *)(a2 + 1306)];
    v6 = v5 + 10;
    if ( (unsigned int)((__int16)(v5 + 10) - 80 + 0x8000) <= 0xFFFF && (_WORD)v5 == 70 )
      v6 = 0;
    v7 = a1 + 2 * v5;
    v8 = 1;
    v9 = a1 + 2LL * v6;
    do
    {
      v10 = 10LL - (unsigned int)v8++;
      *(_WORD *)(v9 + 2 * v10 + 672) = *(_WORD *)(v7 + 2 * v10 + 672);
    }
    while ( v8 <= 10 );
    v11 = *(__int16 *)(a1 + 1024);
    v12 = 0;
    memset(v139, 0, sizeof(v139));
    v13 = 0;
    v14 = 0;
    if ( (_WORD)v11 != 7 )
      v14 = v11 + 1;
    *(_WORD *)(a1 + 2LL * v14 + 992) = *(_WORD *)(a1 + 2 * v11 + 992);
    v140 = 0;
    *(_WORD *)(a1 + 1012) = 0;
    do
    {
      v15 = (*(__int16 *)(a1 + 2LL * v12 + 992) >> 3) + v13;
      if ( v15 <= 0x7FFF )
      {
        if ( v15 < -32768 )
          LOWORD(v15) = 0x8000;
      }
      else
      {
        LOWORD(v15) = 0x7FFF;
      }
      *(_WORD *)(a1 + 1012) = v15;
      for ( i = 0; (__int16)i < 10; ++i )
      {
        v13 = v15;
        v17 = i;
        v18 = *((_DWORD *)v139 + i);
        v19 = *(__int16 *)(a1 + 2 * (i + 10LL * v12) + 672);
        v20 = v19 + v18;
        if ( (v18 ^ v19) >= 0 && ((v18 ^ v20) & 0x80000000) != 0 )
        {
          v20 = 0x7FFFFFFF;
          if ( v18 < 0 )
            v20 = 0x80000000;
        }
        *((_DWORD *)v139 + v17) = v20;
        LOWORD(v15) = v13;
      }
      ++v12;
      v4 = 0x7FFF;
    }
    while ( (__int16)v12 < 8 );
    for ( j = 0; j != 10; ++j )
      v136[j] = *((int *)v139 + j) >> 3;
    Em_AmrNB_Dec_LsfToLsp(v136, a1 + 632);
    v22 = *(__int16 *)(a1 + 1012) - *(__int16 *)(a1 + 1026);
    if ( v22 <= 0x7FFF )
    {
      if ( v22 < -32768 )
        LOWORD(v22) = 0x8000;
    }
    else
    {
      LOWORD(v22) = 0x7FFF;
    }
    *(_WORD *)(a1 + 1012) = v22;
    for ( k = 1; k <= 80; ++k )
    {
      v24 = 80LL - (unsigned int)k;
      *(_WORD *)(a1 + 2 * v24 + 832) = *(_WORD *)(a1 + 2 * v24 + 672);
    }
    v25 = 0;
    while ( 1 )
    {
      v26 = 0;
      for ( m = 0; m != 8; ++m )
      {
        v28 = *(__int16 *)(a1 + 2LL * (v25 + 10 * m) + 832);
        v29 = v28 + v26;
        if ( (v26 ^ v28) >= 0 && (v26 ^ v29) < 0 )
        {
          v29 = 0x7FFFFFFF;
          if ( v26 < 0 )
            v29 = 0x80000000;
        }
        v26 = v29;
      }
      v30 = Em_AmrNB_Dec_lsf_hist_mean_scale[v25];
      v31 = 0;
      v32 = (__int16)(v29 >> 3);
      do
      {
        v33 = v25 + 10 * v31;
        v34 = *(__int16 *)(a1 + 2 * v33 + 832) - v32;
        if ( v34 <= 0x7FFF )
        {
          if ( v34 < -32768 )
            LOWORD(v34) = 0x8000;
        }
        else
        {
          LOWORD(v34) = 0x7FFF;
        }
        v35 = (v30 * (__int16)v34) >> 15;
        if ( (_WORD)v35 == 0x8000 )
        {
          v36 = 0x7FFF;
        }
        else
        {
          v36 = -(__int16)v35;
          if ( (__int16)v35 > 0 )
            v36 = v35;
          if ( v36 <= 655 )
          {
            LOWORD(v38) = v36;
            goto LABEL_56;
          }
        }
        v37 = (unsigned __int16)v36 - 655;
        if ( v37 <= 0x7FFF )
        {
          if ( v37 < -32768 )
            LOWORD(v37) = 0x8000;
        }
        else
        {
          LOWORD(v37) = 0x7FFF;
        }
        v38 = ((__int16)v37 >> 2) + 655;
        if ( v38 <= 0x7FFF )
        {
          if ( v38 < -32768 )
            LOWORD(v38) = 0x8000;
        }
        else
        {
          LOWORD(v38) = 0x7FFF;
        }
LABEL_56:
        v39 = (__int16)v38 - 1310;
        if ( v39 > 0x7FFF || v39 >= -32768 && (__int16)v39 > 0 )
          LOWORD(v38) = 1310;
        *(_WORD *)(a1 + 2 * v33 + 832) = v38;
        if ( (v35 & 0x8000u) != 0 )
          *(_WORD *)(a1 + 2 * v33 + 832) = -(__int16)v38;
        ++v31;
      }
      while ( v31 != 8 );
      if ( (__int16)++v25 >= 10 )
      {
        v2 = a2;
        break;
      }
    }
  }
  if ( *(_WORD *)(a1 + 1032) )
  {
    for ( n = 1; n <= 10; ++n )
    {
      v41 = 10LL - (unsigned int)n;
      *(_WORD *)(a1 + 2 * v41 + 652) = *(_WORD *)(a1 + 2 * v41 + 632);
    }
    LOWORD(v42) = *(_WORD *)(a1 + 1012);
    *(_WORD *)(a1 + 1014) = v42;
    if ( *(_WORD *)(a1 + 1034) )
    {
      v43 = *(_WORD *)(a1 + 1008);
      *(_WORD *)(a1 + 1008) = 0;
      if ( v43 < 2 )
        v44 = 0x4000;
      else
        v44 = Em_AmrNB_Dec_div_s(1024);
      *(_WORD *)(a1 + 1010) = v44;
      v45 = 0x180000000LL + 20LL * **(unsigned __int16 **)(v2 + 1320) + 91280;
      for ( ii = 1; ii <= 10; ++ii )
      {
        v47 = 10LL - (unsigned int)ii;
        *(_WORD *)(a1 + 2 * v47 + 60) = *(_WORD *)(v45 + 2 * v47);
      }
      v134 = *(_QWORD *)(v2 + 1320) + 2LL;
      Em_AmrNB_Dec_gGetLPC(8, a1, &v134, a1 + 632);
      *(_OWORD *)(a1 + 60) = 0;
      *(_DWORD *)(a1 + 76) = 0;
      v48 = *(_WORD *)(*(_QWORD *)(v2 + 1320) + 8LL);
      if ( v48 << 9 == (__int16)(v48 << 9) )
      {
        v49 = v48 << 9;
      }
      else
      {
        v49 = 0x7FFF;
        if ( v48 <= 0 )
          v49 = 0x8000;
      }
      v42 = v49 - 5120;
      if ( v42 <= 0x7FFF )
      {
        if ( v42 < -32768 )
          LOWORD(v42) = 0x8000;
      }
      else
      {
        LOWORD(v42) = 0x7FFF;
      }
      *(_WORD *)(a1 + 1012) = v42;
      if ( !v48 )
      {
        *(_WORD *)(a1 + 1012) = 0x8000;
        LOWORD(v42) = 0x8000;
      }
      if ( !*(_WORD *)(a1 + 1044) || !*(_DWORD *)(a1 + 1040) )
      {
        for ( jj = 1; jj <= 10; ++jj )
        {
          v51 = 10LL - (unsigned int)jj;
          *(_WORD *)(a1 + 2 * v51 + 652) = *(_WORD *)(a1 + 2 * v51 + 632);
        }
        LOWORD(v42) = *(_WORD *)(a1 + 1012);
        *(_WORD *)(a1 + 1014) = v42;
      }
    }
    v52 = ((__int16)v42 >> 1) - 9000;
    if ( v52 <= 0x7FFF )
    {
      if ( v52 < -32768 )
        LOWORD(v52) = 0x8000;
    }
    else
    {
      LOWORD(v52) = 0x7FFF;
    }
    v53 = 0;
    if ( (__int16)v52 <= 0 )
      v53 = v52;
    v54 = v53 + 14436;
    if ( v54 > 0x7FFF || v54 >= -32768 && (v54 & 0x8000u) == 0 )
      v55 = v53;
    else
      v55 = -14436;
    *(_WORD *)(a1 + 424) = v55;
    *(_WORD *)(a1 + 426) = v55;
    *(_WORD *)(a1 + 428) = v55;
    *(_WORD *)(a1 + 430) = v55;
    v56 = (5443 * v55) >> 15;
    *(_WORD *)(a1 + 432) = v56;
    *(_WORD *)(a1 + 434) = v56;
    *(_WORD *)(a1 + 436) = v56;
    *(_WORD *)(a1 + 438) = v56;
  }
  v57 = 32 * Em_AmrNB_Dec_dtx_log_en_adjust[*(__int16 *)(v2 + 1306)];
  if ( v57 != (__int16)(32 * Em_AmrNB_Dec_dtx_log_en_adjust[*(__int16 *)(v2 + 1306)]) )
  {
    LOWORD(v57) = 0x7FFF;
    if ( Em_AmrNB_Dec_dtx_log_en_adjust[*(__int16 *)(v2 + 1306)] <= 0 )
      LOWORD(v57) = 0x8000;
  }
  v58 = ((__int16)((unsigned int)(3277 * (__int16)v57) >> 16) >> 4) + (__int16)((29491 * *(__int16 *)(a1 + 1026)) >> 15);
  if ( v58 <= 0x7FFF )
  {
    if ( v58 < -32768 )
      LOWORD(v58) = 0x8000;
  }
  else
  {
    LOWORD(v58) = 0x7FFF;
  }
  v59 = *(_WORD *)(a1 + 1008) + 1;
  *(_WORD *)(a1 + 1026) = v58;
  if ( v59 << 10 == (__int16)(v59 << 10) )
  {
    v60 = v59 << 10;
  }
  else
  {
    v60 = 0x7FFF;
    if ( v59 <= 0 )
      v60 = 0x8000;
  }
  v61 = (v60 * *(__int16 *)(a1 + 1010)) >> 15;
  if ( (__int16)v61 > 1024 )
    LOWORD(v61) = 1024;
  v62 = 0;
  v63 = (__int16)(16 * v61);
  v64 = 2 * v63 * *(__int16 *)(a1 + 1012);
  do
  {
    v65 = v62 + 1;
    *((_WORD *)v139 + v65) = (v63 * *(__int16 *)(a1 + 2 * v62++ + 632)) >> 15;
  }
  while ( v65 != 10 );
  if ( 0x4000 - v63 <= 0x7FFF )
  {
    if ( 0x4000 - v63 >= -32768 )
      v66 = 0x4000 - v63;
    else
      v66 = 0x8000;
  }
  else
  {
    v66 = 0x7FFF;
  }
  v131 = Em_AmrNB_Dec_L_mac(v64, (unsigned __int16)v66, *(unsigned __int16 *)(a1 + 1014));
  v68 = 0;
  v69 = v66;
  do
  {
    v70 = v68 + 1;
    v71 = *((__int16 *)v139 + v68 + 1) + (__int16)((v69 * *(__int16 *)(a1 + 2 * v68 + 652)) >> 15);
    if ( v71 <= 0x7FFF )
    {
      if ( v71 < -32768 )
        LOWORD(v71) = 0x8000;
    }
    else
    {
      LOWORD(v71) = 0x7FFF;
    }
    v72 = 2 * (__int16)v71;
    if ( v72 != (__int16)(2 * v71) )
    {
      LOWORD(v72) = 0x7FFF;
      if ( (__int16)v71 <= 0 )
        LOWORD(v72) = 0x8000;
    }
    *((_WORD *)v139 + v70) = v72;
    v68 = v70;
  }
  while ( v70 != v67 );
  v73 = *(__int16 *)(a1 + 1022) - 2457;
  if ( v73 <= 0x7FFF )
  {
    if ( v73 < -32768 )
      LOWORD(v73) = 0x8000;
  }
  else
  {
    LOWORD(v73) = 0x7FFF;
  }
  v74 = 4096 - (__int16)((9830 * (__int16)v73) >> 15);
  if ( v74 > 0x7FFF )
    goto LABEL_140;
  if ( v74 < -32768 )
  {
    LOWORD(v74) = 0x8000;
    goto LABEL_141;
  }
  if ( (__int16)v74 > 4096 )
LABEL_140:
    LOWORD(v74) = 4096;
LABEL_141:
  v75 = 0;
  if ( (v74 & 0x8000u) == 0 )
    v75 = v74;
  if ( 8 * v75 == (__int16)(8 * v75) )
  {
    v76 = 8 * v75;
  }
  else
  {
    v76 = 0x7FFF;
    if ( v75 <= 0 )
      v76 = 0x8000;
  }
  v77 = 63;
  v78 = (__int16)Em_AmrNB_Dec_pseudonoise(a1 + 1016, 3);
  for ( kk = 9; kk != -1; --kk )
  {
    v80 = *((__int16 *)v139 + kk + 1);
    if ( Em_AmrNB_Dec_LsfToLspTable[v77] < *((__int16 *)v139 + kk + 1) )
    {
      do
        --v77;
      while ( Em_AmrNB_Dec_LsfToLspTable[v77] < (__int16)v80 );
    }
    v81 = v80 - Em_AmrNB_Dec_LsfToLspTable[v77];
    if ( v81 <= 0x7FFF )
    {
      if ( v81 >= -32768 )
        v82 = v80 - Em_AmrNB_Dec_LsfToLspTable[v77];
      else
        v82 = 0x8000;
    }
    else
    {
      v82 = 0x7FFF;
    }
    v83 = Em_AmrNB_Dec_L_shl((unsigned int)(2 * v82 * Em_AmrNB_Dec_slope[v77]), 3);
    v84 = v83 + 0x8000;
    if ( v83 >= 0 && (v84 ^ v83) < 0 )
      v84 = 0x7FFFFFFF;
    v85 = v84 >> 16;
    if ( v77 << 8 == (__int16)(v77 << 8) )
    {
      v86 = v77 << 8;
    }
    else
    {
      v86 = 0x7FFF;
      if ( v77 <= 0 )
        v86 = 0x8000;
    }
    v87 = v86 + (__int16)v85;
    if ( v87 <= 0x7FFF )
    {
      if ( v87 < -32768 )
        LOWORD(v87) = 0x8000;
    }
    else
    {
      LOWORD(v87) = 0x7FFF;
    }
    *(_WORD *)&v138[2 * kk - 2] = v87;
  }
  v88 = v135;
  for ( mm = 1; mm <= 10; ++mm )
  {
    v90 = 10LL - (unsigned int)mm;
    v136[v90] = *(_WORD *)&v138[2 * v90 - 2];
  }
  for ( nn = 0; (__int16)nn < 10; ++nn )
  {
    v92 = nn;
    v93 = (__int16)((v76 * *(__int16 *)(v88 + 2LL * (10 * v78 + nn) + 832)) >> 15) + (__int16)v136[nn];
    if ( v93 <= 0x7FFF )
    {
      if ( v93 < -32768 )
        LOWORD(v93) = 0x8000;
    }
    else
    {
      LOWORD(v93) = 0x7FFF;
    }
    v136[v92] = v93;
  }
  Em_AmrNB_Dec_ReorderLsf(&v137);
  Em_AmrNB_Dec_ReorderLsf(v136);
  v95 = 1;
  do
  {
    v96 = v94 - (unsigned int)v95++;
    *(_WORD *)(v88 + 2 * v96) = *(_WORD *)&v138[2 * v96 - 2];
  }
  while ( v95 <= (int)v94 );
  Em_AmrNB_Dec_LsfToLsp(&v137, (char *)v139 + 2);
  Em_AmrNB_Dec_LsfToLsp(v136, v138);
  Em_AmrNB_Dec_LspToLpc(v139);
  Em_AmrNB_Dec_LspToLpc(&v137);
  Em_AmrNB_Dec_gCopy((__int64)v139, a2, 22);
  Em_AmrNB_Dec_gCopy((__int64)v139, a2 + 22, v97);
  Em_AmrNB_Dec_gCopy((__int64)v139, a2 + 44, v98);
  Em_AmrNB_Dec_gCopy((__int64)v139, a2 + 66, v99);
  Em_AmrNB_Dec_gLpcToRefl((char *)v139 + 2, v136);
  for ( i1 = 0; i1 != 10; ++i1 )
  {
    Em_AmrNB_Dec_mult((unsigned __int16)v136[i1]);
    v102 = (__int16)Em_AmrNB_Dec_mult(v101);
  }
  v103 = Em_AmrNB_Dec_gLog2(v102);
  v104 = SHIWORD(v103) - 15;
  if ( v104 <= 0x7FFF )
  {
    if ( v104 < -32768 )
      LOWORD(v104) = 0x8000;
  }
  else
  {
    LOWORD(v104) = 0x7FFF;
  }
  v105 = (__int16)v104 << 12;
  if ( v105 != (__int16)((_WORD)v104 << 12) )
  {
    LOWORD(v105) = 0x7FFF;
    if ( (__int16)v104 <= 0 )
      LOWORD(v105) = 0x8000;
  }
  v106 = ((v103 >> 4) & 0xFFF) + (__int16)v105;
  if ( v106 <= 0x7FFF )
  {
    if ( v106 < -32768 )
      LOWORD(v106) = 0x8000;
  }
  else
  {
    LOWORD(v106) = 0x7FFF;
  }
  v107 = -(__int16)v106;
  if ( v107 <= 0x7FFF )
  {
    if ( v107 < -32768 )
      LOWORD(v107) = 0x8000;
  }
  else
  {
    LOWORD(v107) = 0x7FFF;
  }
  v108 = (__int16)v107 >> 1;
  v109 = (__int16)((29491 * *(__int16 *)(v88 + 1022)) >> 15) + (__int16)((int)(3277 * v108) >> 15);
  if ( v109 <= 0x7FFF )
  {
    if ( v109 < -32768 )
      LOWORD(v109) = 0x8000;
  }
  else
  {
    LOWORD(v109) = 0x7FFF;
  }
  *(_WORD *)(v88 + 1022) = v109;
  v110 = (v131 >> 10) + 0x40000;
  if ( v131 >> 10 >= 0 && ((v131 >> 10) ^ v110) < 0 )
    v110 = 0x7FFFFFFF;
  v111 = Em_AmrNB_Dec_L_shl(v108, 4);
  v112 = v110 - v111;
  if ( (v111 ^ v110) < 0 && (v112 ^ v110) < 0 )
  {
    v112 = 0x7FFFFFFF;
    if ( v110 < 0 )
      v112 = 0x80000000;
  }
  v113 = Em_AmrNB_Dec_L_shl((unsigned int)*(__int16 *)(v88 + 1026), 5);
  v114 = v113 + v112;
  if ( (v112 ^ v113) >= 0 && (v114 ^ v112) < 0 )
  {
    v114 = 0x7FFFFFFF;
    if ( v112 < 0 )
      v114 = 0x80000000;
  }
  v115 = (unsigned int)(v114 >> 1);
  LOWORD(v115) = v115 & 0x7FFF;
  LODWORD(v134) = (__int16)Em_AmrNB_Dec_gPow2((unsigned int)(v114 >> 16), v115);
  v132 = 0;
  do
  {
    v116 = v139;
    for ( i2 = 40; i2; --i2 )
      *v116++ = 0;
    for ( i3 = 0; i3 != 10; ++i3 )
    {
      v119 = i3 + ((__int16)(20 * Em_AmrNB_Dec_pseudonoise(v88 + 1016, 2)) >> 1);
      if ( v119 <= 0x7FFF )
      {
        if ( v119 < -32768 )
          LOWORD(v119) = 0x8000;
      }
      else
      {
        LOWORD(v119) = 0x7FFF;
      }
      v120 = (__int16)v119;
      *((_WORD *)v139 + (__int16)v119) = 4096;
      if ( (__int16)Em_AmrNB_Dec_pseudonoise(v88 + 1016, 1) <= 0 )
        *((_WORD *)v139 + v120) = -4096;
    }
    v122 = v132;
    v123 = v134;
    for ( i4 = 0; i4 != 40; ++i4 )
      *((_WORD *)v139 + i4) = (v123 * *((__int16 *)v139 + i4)) >> 15;
    Em_AmrNB_Dec_gIIRFilter(
      (unsigned int)&v137,
      (unsigned int)v139,
      v88 + 20,
      v121,
      v130,
      *(_QWORD *)(a2 + 1336) + 80LL * v132++);
  }
  while ( v122 != 3 );
  *(_DWORD *)(v88 + 468) = 20;
  if ( *(_DWORD *)(a2 + 1312) == 2 )
  {
    *(_WORD *)(v88 + 1010) = Em_AmrNB_Dec_div_s(1024);
    *(_WORD *)(v88 + 1008) = 0;
    for ( i5 = 1; i5 <= 10; ++i5 )
    {
      v126 = 10LL - (unsigned int)i5;
      *(_WORD *)(v88 + 2 * v126 + 652) = *(_WORD *)(v88 + 2 * v126 + 632);
    }
    v127 = *(__int16 *)(v88 + 1012);
    *(_WORD *)(v88 + 1014) = v127;
    v128 = v127 - 256;
    if ( v128 <= 0x7FFF )
    {
      v4 = 0x8000;
      if ( v128 >= -32768 )
        v4 = v128;
    }
    *(_WORD *)(v88 + 1012) = v4;
  }
  if ( *(_WORD *)(v88 + 1032) && (*(_WORD *)(v88 + 1034) || *(_WORD *)(v88 + 1036)) )
  {
    *(_WORD *)(v88 + 1008) = 0;
    *(_WORD *)(v88 + 1044) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x1800051e0  mov     [rsp-8+arg_10], rbx
0x1800051e5  push    rbp
0x1800051e6  push    rsi
0x1800051e7  push    rdi
0x1800051e8  push    r12
0x1800051ea  push    r13
0x1800051ec  push    r14
0x1800051ee  push    r15
0x1800051f0  lea     rbp, [rsp-27h]
0x1800051f5  sub     rsp, 0E0h
0x1800051fc  mov     rax, cs:__security_cookie
0x180005203  xor     rax, rsp
0x180005206  mov     [rbp+57h+var_40], rax
0x18000520a  mov     r10d, 0Ah
0x180005210  mov     [rsp+110h+var_D8], rdx
0x180005215  xor     r13d, r13d
0x180005218  mov     [rbp+57h+var_C8], rcx
0x18000521c  lea     rdi, cs:180000000h
0x180005223  mov     r15, rdx
0x180005226  mov     rbx, rcx
0x180005229  mov     esi, 7FFFh
0x18000522e  lea     r11d, [r10-9]
0x180005232  mov     r12d, 0FFFF8000h
0x180005238  lea     r14d, [r10-2]
0x18000523c  cmp     [rcx+40Ch], r13w
0x180005244  jz      loc_18000558C
0x18000524a  cmp     [rcx+408h], r13w
0x180005252  jz      loc_18000558C
0x180005258  movsx   rax, word ptr [rdx+51Ah]
0x180005260  movzx   eax, ds:rva Em_AmrNB_Dec_dtx_log_en_adjust[rdi+rax*2]
0x180005268  movsx   rdi, word ptr [rcx+3FCh]
0x180005270  mov     [rcx+402h], ax
0x180005277  lea     ecx, [r10+rdi]
0x18000527b  movsx   edx, cx
0x18000527e  add     edx, 0FFFFFFB0h
0x180005281  lea     eax, [rdx+8000h]
0x180005287  cmp     eax, 0FFFFh
0x18000528c  ja      short loc_180005296
0x18000528e  test    dx, dx
0x180005291  jnz     short loc_180005296
0x180005293  mov     ecx, r13d
0x180005296  movsx   rax, cx
0x18000529a  lea     rdi, [rbx+rdi*2]
0x18000529e  mov     edx, r11d
0x1800052a1  lea     r8, [rbx+rax*2]
0x1800052a5  mov     eax, edx
0x1800052a7  mov     rcx, r10
0x1800052aa  sub     rcx, rax
0x1800052ad  add     edx, r11d
0x1800052b0  movzx   eax, word ptr [rdi+rcx*2+2A0h]
0x1800052b8  mov     [r8+rcx*2+2A0h], ax
0x1800052c1  cmp     edx, r10d
0x1800052c4  jle     short loc_1800052A5
0x1800052c6  movsx   rax, word ptr [rbx+400h]
0x1800052ce  xorps   xmm0, xmm0
0x1800052d1  mov     rdx, rax
0x1800052d4  mov     r8d, r13d
0x1800052d7  movups  [rbp+57h+var_90], xmm0
0x1800052db  movzx   r9d, r13w
0x1800052df  mov     r15, r10
0x1800052e2  lea     ecx, [r11+rax]
0x1800052e6  mov     eax, r13d
0x1800052e9  cmp     cx, r14w
0x1800052ed  movups  [rbp+57h+var_80], xmm0
0x1800052f1  cmovnz  ax, cx
0x1800052f5  movsx   rcx, ax
0x1800052f9  movzx   eax, word ptr [rbx+rdx*2+3E0h]
0x180005301  mov     [rbx+rcx*2+3E0h], ax
0x180005309  xor     eax, eax
0x18000530b  mov     [rbp+57h+var_70], rax
0x18000530f  mov     [rbx+3F4h], r13w
0x180005317  movzx   r11d, r8w
0x18000531b  movsx   eax, r9w
0x18000531f  movsx   ecx, word ptr [rbx+r11*2+3E0h]
0x180005328  sar     ecx, 3
0x18000532b  add     eax, ecx
0x18000532d  cmp     eax, esi
0x18000532f  jle     short loc_180005336
0x180005331  movzx   eax, si
0x180005334  jmp     short loc_18000533E
0x180005336  cmp     eax, r12d
0x180005339  jge     short loc_18000533E
0x18000533b  mov     eax, r12d
0x18000533e  mov     [rbx+3F4h], ax
0x180005345  mov     edx, r13d
0x180005348  mov     esi, 80000000h
0x18000534d  mov     r12d, 1
0x180005353  movzx   r9d, ax
0x180005357  movzx   r10d, dx
0x18000535b  movzx   eax, dx
0x18000535e  lea     rcx, [r11+r11*4]
0x180005362  mov     edi, dword ptr [rbp+r10*4+57h+var_90]
0x180005367  lea     rcx, [rax+rcx*2]
0x18000536b  movsx   eax, word ptr [rbx+rcx*2+2A0h]
0x180005373  lea     ecx, [rax+rdi]
0x180005376  xor     eax, edi
0x180005378  jl      short loc_18000538A
0x18000537a  mov     eax, ecx
0x18000537c  xor     eax, edi
0x18000537e  jge     short loc_18000538A
0x180005380  test    edi, edi
0x180005382  mov     ecx, 7FFFFFFFh
0x180005387  cmovs   ecx, esi
0x18000538a  add     dx, r12w
0x18000538e  mov     dword ptr [rbp+r10*4+57h+var_90], ecx
0x180005393  movzx   eax, r9w
0x180005397  cmp     dx, r15w
0x18000539b  jl      short loc_180005353
0x18000539d  add     r8w, r12w
0x1800053a1  mov     esi, 7FFFh
0x1800053a6  mov     r12d, 0FFFF8000h
0x1800053ac  cmp     r8w, r14w
0x1800053b0  jl      loc_180005317
0x1800053b6  mov     rcx, r13
0x1800053b9  mov     eax, dword ptr [rbp+rcx*4+57h+var_90]
0x1800053bd  sar     eax, 3
0x1800053c0  mov     [rbp+rcx*2+57h+var_C0], ax
0x1800053c5  inc     rcx
0x1800053c8  cmp     rcx, r15
0x1800053cb  jnz     short loc_1800053B9
0x1800053cd  lea     rdx, [rbx+278h]
0x1800053d4  lea     rcx, [rbp+57h+var_C0]
0x1800053d8  call    Em_AmrNB_Dec_LsfToLsp
0x1800053dd  movsx   eax, word ptr [rbx+402h]
0x1800053e4  movsx   ecx, word ptr [rbx+3F4h]
0x1800053eb  sub     ecx, eax
0x1800053ed  cmp     ecx, esi
0x1800053ef  jle     short loc_1800053F6
0x1800053f1  movzx   ecx, si
0x1800053f4  jmp     short loc_1800053FE
0x1800053f6  cmp     ecx, r12d
0x1800053f9  jge     short loc_1800053FE
0x1800053fb  mov     ecx, r12d
0x1800053fe  mov     r11d, 1
0x180005404  mov     [rbx+3F4h], cx
0x18000540b  mov     edx, r11d
0x18000540e  mov     eax, edx
0x180005410  mov     ecx, 50h ; 'P'
0x180005415  sub     rcx, rax
0x180005418  add     edx, r11d
0x18000541b  movzx   eax, word ptr [rbx+rcx*2+2A0h]
0x180005423  mov     [rbx+rcx*2+340h], ax
0x18000542b  cmp     edx, 50h ; 'P'
0x18000542e  jle     short loc_18000540E
0x180005430  mov     r9d, r13d
0x180005433  lea     r15, cs:180000000h
0x18000543a  jmp     short loc_180005442
0x18000543c  mov     r14d, 8
0x180005442  movzx   r10d, r9w
0x180005446  mov     edi, r13d
0x180005449  mov     r8d, r13d
0x18000544c  mov     r12d, 80000000h
0x180005452  lea     eax, [r8+r8*4]
0x180005456  lea     eax, [r10+rax*2]
0x18000545a  cdqe
0x18000545c  movsx   ecx, word ptr [rbx+rax*2+340h]
0x180005464  lea     edx, [rcx+rdi]
0x180005467  xor     ecx, edi
0x180005469  jl      short loc_18000547C
0x18000546b  mov     eax, edx
0x18000546d  xor     eax, edi
0x18000546f  jge     short loc_18000547C
0x180005471  test    edi, edi
0x180005473  mov     edx, 7FFFFFFFh
0x180005478  cmovs   edx, r12d
0x18000547c  add     r8d, r11d
0x18000547f  mov     edi, edx
0x180005481  cmp     r8d, r14d
0x180005484  jnz     short loc_180005452
0x180005486  movsx   r11d, ds:rva Em_AmrNB_Dec_lsf_hist_mean_scale[r15+r10*2]
0x18000548f  mov     edi, r13d
0x180005492  sar     edx, 3
0x180005495  mov     r12d, 0FFFF8000h
0x18000549b  movsx   r14d, dx
0x18000549f  lea     eax, [rdi+rdi*4]
0x1800054a2  lea     ecx, [r10+rax*2]
0x1800054a6  movsxd  r8, ecx
0x1800054a9  movsx   eax, word ptr [rbx+r8*2+340h]
0x1800054b2  sub     eax, r14d
0x1800054b5  cmp     eax, esi
0x1800054b7  jle     short loc_1800054BE
0x1800054b9  movzx   eax, si
0x1800054bc  jmp     short loc_1800054C6
0x1800054be  cmp     eax, r12d
0x1800054c1  jge     short loc_1800054C6
0x1800054c3  mov     eax, r12d
0x1800054c6  movsx   edx, ax
0x1800054c9  imul    edx, r11d
0x1800054cd  sar     edx, 0Fh
0x1800054d0  cmp     dx, r12w
0x1800054d4  jnz     short loc_1800054DB
0x1800054d6  movzx   eax, si
0x1800054d9  jmp     short loc_1800054EF
0x1800054db  movzx   eax, dx
0x1800054de  mov     ecx, 28Fh
0x1800054e3  neg     ax
0x1800054e6  cmovs   ax, dx
0x1800054ea  cmp     ax, cx
0x1800054ed  jle     short loc_180005527
0x1800054ef  movzx   eax, ax
0x1800054f2  add     eax, 0FFFFFD71h
0x1800054f7  cmp     eax, esi
0x1800054f9  jle     short loc_180005500
0x1800054fb  movzx   eax, si
0x1800054fe  jmp     short loc_180005508
0x180005500  cmp     eax, r12d
0x180005503  jge     short loc_180005508
0x180005505  mov     eax, r12d
0x180005508  movsx   ecx, ax
0x18000550b  sar     ecx, 2
0x18000550e  add     ecx, 28Fh
0x180005514  cmp     ecx, esi
0x180005516  jle     short loc_18000551D
0x180005518  movzx   ecx, si
0x18000551b  jmp     short loc_18000552A
0x18000551d  cmp     ecx, r12d
0x180005520  jge     short loc_18000552A
0x180005522  mov     ecx, r12d
0x180005525  jmp     short loc_18000552A
0x180005527  movzx   ecx, ax
0x18000552a  movsx   eax, cx
0x18000552d  add     eax, 0FFFFFAE2h
0x180005532  cmp     eax, esi
0x180005534  jg      short loc_180005540
0x180005536  cmp     eax, r12d
0x180005539  jl      short loc_180005545
0x18000553b  test    ax, ax
0x18000553e  jle     short loc_180005545
0x180005540  mov     ecx, 51Eh
0x180005545  mov     [rbx+r8*2+340h], cx
0x18000554e  test    dx, dx
0x180005551  jns     short loc_18000555F
0x180005553  neg     cx
0x180005556  mov     [rbx+r8*2+340h], cx
0x18000555f  inc     edi
0x180005561  cmp     edi, 8
0x180005564  jnz     loc_18000549F
0x18000556a  lea     r11d, [rdi-7]
0x18000556e  add     r9w, r11w
0x180005572  lea     r10d, [rdi+2]
0x180005576  cmp     r9w, r10w
0x18000557a  jl      loc_18000543C
0x180005580  mov     r15, [rsp+110h+var_D8]
0x180005585  lea     rdi, cs:180000000h
0x18000558c  mov     r9d, 2
0x180005592  mov     r8d, 400h
0x180005598  mov     r14d, 4000h
0x18000559e  cmp     [rbx+408h], r13w
0x1800055a6  jz      loc_1800057D7
0x1800055ac  mov     edx, r11d
0x1800055af  mov     eax, edx
0x1800055b1  mov     rcx, r10
0x1800055b4  sub     rcx, rax
0x1800055b7  add     edx, r11d
0x1800055ba  movzx   eax, word ptr [rbx+rcx*2+278h]
0x1800055c2  mov     [rbx+rcx*2+28Ch], ax
0x1800055ca  cmp     edx, r10d
0x1800055cd  jle     short loc_1800055AF
0x1800055cf  movzx   eax, word ptr [rbx+3F4h]
0x1800055d6  mov     [rbx+3F6h], ax
0x1800055dd  cmp     [rbx+40Ah], r13w
0x1800055e5  jz      loc_180005752
0x1800055eb  movzx   edx, word ptr [rbx+3F0h]
0x1800055f2  mov     eax, 20h ; ' '
0x1800055f7  mov     [rbx+3F0h], r13w
0x1800055ff  cmp     dx, ax
0x180005602  jle     short loc_180005609
0x180005604  movzx   edx, ax
0x180005607  jmp     short loc_18000560F
0x180005609  cmp     dx, r9w
0x18000560d  jl      short loc_18000562B
0x18000560f  shl     dx, 0Ah
0x180005613  mov     ecx, r8d
0x180005616  call    Em_AmrNB_Dec_div_s
0x18000561b  mov     r11d, 1
0x180005621  lea     r10d, [r11+9]
0x180005625  lea     r9d, [r11+1]
0x180005629  jmp     short loc_18000562E
0x18000562b  mov     eax, r14d
0x18000562e  mov     [rbx+3F2h], ax
0x180005635  mov     rax, [r15+528h]
0x18000563c  movzx   ecx, word ptr [rax]
0x18000563f  lea     rax, [rcx+rcx*4]
0x180005643  lea     r8, ds:16490h[rax*4]
0x18000564b  add     r8, rdi
0x18000564e  mov     edi, r11d
0x180005651  mov     eax, edi
0x180005653  mov     rdx, r10
0x180005656  sub     rdx, rax
0x180005659  add     edi, r11d
0x18000565c  movzx   eax, word ptr [r8+rdx*2]
0x180005661  mov     [rbx+rdx*2+3Ch], ax
0x180005666  cmp     edi, r10d
0x180005669  jle     short loc_180005651
0x18000566b  mov     rax, [r15+528h]
0x180005672  lea     r8, [rbp+57h+var_D0]
0x180005676  add     rax, r9
0x180005679  mov     rdx, rbx
0x18000567c  lea     r9, [rbx+278h]
0x180005683  mov     [rbp+57h+var_D0], rax
  ... truncated ...
```
