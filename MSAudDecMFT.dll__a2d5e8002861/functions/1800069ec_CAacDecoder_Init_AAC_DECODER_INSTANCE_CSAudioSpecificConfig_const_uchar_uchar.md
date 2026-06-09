# CAacDecoder_Init(AAC_DECODER_INSTANCE *,CSAudioSpecificConfig const *,uchar,uchar *)

- ea: `0x1800069ec`
- end: `0x180008312`
- name: `?CAacDecoder_Init@@YA?AW4AAC_DECODER_ERROR@@PEAUAAC_DECODER_INSTANCE@@PEBUCSAudioSpecificConfig@@EPEAE@Z`
- size: `6438`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008320`

## callees

- `0x180006368`
- `0x180006754`
- `0x180006798`
- `0x180006914`
- `0x1800069ec`
- `0x180038a44`
- `0x18003c2cc`
- `0x1800405b8`
- `0x1800420c4`
- `0x180046ebc`
- `0x180048018`
- `0x18004b854`
- `0x18004d320`
- `0x18004dd14`
- `0x1800725f0`
- `0x18007334c`
- `0x180073f04`
- `0x180073f38`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800073f6`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800075e4`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180007fbb`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180008056`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800080ad`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180008150`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000821d`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800073f6`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800075e4`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180007fbb`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180008056`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800080ad`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180008150`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18000821d`

## pseudocode

```c
__int64 __fastcall CAacDecoder_Init(int *a1, __int64 a2, char a3, _BYTE *a4)
{
  BOOL v4; // r14d
  __int64 v5; // rdi
  int v7; // eax
  _OWORD *v8; // rsi
  char *v9; // r15
  int v10; // r13d
  int v11; // esi
  int v12; // r9d
  __int64 v13; // rsi
  int v14; // ecx
  int v15; // esi
  unsigned int v16; // eax
  char v17; // r11
  unsigned __int8 v18; // r9
  int v19; // r10d
  int v20; // r15d
  signed int v21; // edx
  int v22; // r8d
  int v23; // r10d
  int v24; // r9d
  int v25; // r8d
  char v26; // r10
  int v27; // ecx
  __int64 v28; // rdx
  unsigned int v29; // r12d
  int *v30; // rsi
  int v31; // r9d
  char v32; // al
  char v33; // r11
  _BYTE *v34; // r15
  __int64 v35; // rax
  signed int v36; // esi
  unsigned int v37; // r13d
  unsigned int *v38; // r14
  unsigned int v39; // eax
  int v40; // eax
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 jj; // rdx
  __int64 v44; // rcx
  __int64 v45; // r8
  unsigned int v46; // ecx
  __int64 v47; // rdx
  bool v48; // zf
  __int64 result; // rax
  __int64 v50; // rax
  _BYTE *v51; // rcx
  unsigned __int8 *v52; // rax
  char v53; // r8
  unsigned __int8 *v54; // rdx
  _BYTE *v55; // rcx
  int v56; // eax
  __int128 v57; // xmm1
  unsigned int v58; // eax
  __int128 v59; // xmm0
  __int128 v60; // xmm1
  __int128 v61; // xmm0
  __int128 v62; // xmm1
  __int128 v63; // xmm0
  __int128 v64; // xmm1
  __int128 v65; // xmm0
  __int128 v66; // xmm1
  __int128 v67; // xmm0
  __int128 v68; // xmm1
  __int128 v69; // xmm0
  __int128 v70; // xmm1
  __int128 v71; // xmm0
  unsigned int v72; // r8d
  int v73; // ecx
  __int128 v74; // xmm1
  unsigned int v75; // eax
  __int128 v76; // xmm0
  __int128 v77; // xmm1
  __int128 v78; // xmm0
  __int128 v79; // xmm1
  __int128 v80; // xmm0
  __int128 v81; // xmm1
  __int128 v82; // xmm0
  __int128 v83; // xmm1
  __int128 v84; // xmm0
  __int128 v85; // xmm1
  __int128 v86; // xmm0
  __int128 v87; // xmm1
  __int128 v88; // xmm0
  int j; // esi
  __int64 v90; // rax
  int v91; // r14d
  int v92; // eax
  int k; // r15d
  unsigned int v94; // r8d
  size_t v95; // r10
  __int64 v96; // rcx
  __int64 v97; // rdx
  int v98; // r9d
  __int64 v99; // rdx
  unsigned int v100; // eax
  int v101; // r8d
  int m; // esi
  void *v103; // rax
  _QWORD *v104; // r8
  _QWORD *v105; // rdx
  __int64 v106; // rcx
  int v107; // r13d
  int v108; // r13d
  int v109; // r13d
  int v110; // r13d
  unsigned __int8 v111; // r14
  _OWORD *v112; // rax
  __int64 v113; // rdx
  __int128 v114; // xmm1
  int ElementTable; // eax
  __int64 v116; // r9
  int v117; // r9d
  int v118; // r10d
  int v119; // eax
  int v120; // edx
  unsigned int i; // ecx
  char v122; // al
  int v123; // r10d
  int v124; // esi
  __int64 v125; // rax
  char v126; // r15
  unsigned int v127; // ecx
  char v128; // r10
  int v129; // r8d
  int v130; // ecx
  int v131; // edx
  int v132; // ecx
  __int64 v133; // r11
  char v134; // r15
  int v135; // r9d
  int v136; // ecx
  int v137; // r8d
  int v138; // ecx
  int v139; // r8d
  __int64 v140; // rcx
  unsigned int v141; // r8d
  char v142; // al
  int v143; // r12d
  int v144; // ecx
  int v145; // r8d
  char v146; // al
  __int64 v147; // rax
  char v148; // cl
  char v149; // al
  char v150; // al
  _BOOL8 v151; // rdx
  _QWORD *v152; // rdx
  __int64 v153; // rcx
  __int64 v154; // rdx
  int n; // r14d
  void *v156; // rax
  int v157; // r11d
  int ii; // r14d
  unsigned int v159; // eax
  bool v160; // cc
  int v161; // r15d
  int v162; // ecx
  void *v163; // rax
  __int64 v164; // r8
  __int64 v165; // rax
  __int64 v166; // rdx
  void *v167; // rax
  __int64 v168; // rcx
  __int64 v169; // rax
  char v170; // [rsp+20h] [rbp-E0h]
  char v171; // [rsp+21h] [rbp-DFh]
  int v173; // [rsp+24h] [rbp-DCh]
  int v174; // [rsp+24h] [rbp-DCh]
  char v175; // [rsp+28h] [rbp-D8h]
  unsigned int v176; // [rsp+28h] [rbp-D8h]
  unsigned __int16 v177[2]; // [rsp+2Ch] [rbp-D4h] BYREF
  unsigned __int8 v178; // [rsp+30h] [rbp-D0h]
  unsigned __int8 v179; // [rsp+31h] [rbp-CFh]
  char v180; // [rsp+33h] [rbp-CDh]
  int v181; // [rsp+34h] [rbp-CCh]
  int v182; // [rsp+38h] [rbp-C8h]
  char *v183; // [rsp+40h] [rbp-C0h]
  _BYTE *v184; // [rsp+48h] [rbp-B8h]
  int ELChannels; // [rsp+50h] [rbp-B0h]
  __int64 v186; // [rsp+58h] [rbp-A8h]
  __int128 v187; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v188; // [rsp+70h] [rbp-90h]
  __int128 v189; // [rsp+80h] [rbp-80h]
  __int128 v190; // [rsp+90h] [rbp-70h]
  __int128 v191; // [rsp+A0h] [rbp-60h]
  __int128 v192; // [rsp+B0h] [rbp-50h]
  __int128 v193; // [rsp+C0h] [rbp-40h]
  __int128 v194; // [rsp+D0h] [rbp-30h]
  __int128 v195; // [rsp+E0h] [rbp-20h]
  __int128 v196; // [rsp+F0h] [rbp-10h]
  __int128 v197; // [rsp+100h] [rbp+0h]
  __int128 v198; // [rsp+110h] [rbp+10h]
  __int128 v199; // [rsp+120h] [rbp+20h]
  __int128 v200; // [rsp+130h] [rbp+30h]
  __int128 v201; // [rsp+140h] [rbp+40h]
  unsigned int v202; // [rsp+150h] [rbp+50h]

  v4 = 0;
  v184 = a4;
  v5 = a2;
  v186 = a2;
  if ( !a1 )
    return 8193;
  v7 = *(_DWORD *)(a2 + 1200);
  if ( v7 == 2 )
  {
    a1[351] = 1;
LABEL_4:
    v182 = 1;
    goto LABEL_5;
  }
  if ( v7 == 23 || v7 == 5 || v7 == 17 || v7 == 29 )
    goto LABEL_4;
  if ( v7 != 39 )
  {
    if ( v7 != 42 )
      return 8194;
    goto LABEL_4;
  }
  v182 = 2;
LABEL_5:
  v8 = (_OWORD *)((char *)a1 + 881);
  v9 = (char *)(a2 + 1224);
  v179 = *((_BYTE *)a1 + 2576);
  v171 = *((_BYTE *)a1 + 4361);
  v178 = *((_BYTE *)a1 + 2564);
  v175 = *((_BYTE *)a1 + 2565);
  v183 = (char *)(a2 + 1224);
  if ( !*((_BYTE *)a1 + 1342) )
  {
LABEL_6:
    memset_0((char *)a1 + 881, 0, 0x1D1u);
    *((_BYTE *)a1 + 883) = 15;
    goto LABEL_7;
  }
  if ( *v9 <= 0 )
  {
    v183 = (char *)(a2 + 1224);
    goto LABEL_6;
  }
  CProgramConfig_GetDefault((struct CProgramConfig *)&v187, *v9);
  if ( (unsigned int)CProgramConfig_Compare(
                       (const struct CProgramConfig *const)((char *)a1 + 881),
                       (const struct CProgramConfig *const)&v187) > 1 )
    goto LABEL_6;
LABEL_7:
  v10 = *v9;
  if ( v10 <= 6 )
  {
    if ( v10 == 6 )
      goto LABEL_9;
    if ( *v9 )
    {
      if ( v10 != 1 && v10 != 2 && v10 != 3 && (unsigned int)(v10 - 4) > 1 )
        return 8199;
      goto LABEL_9;
    }
    if ( *(_DWORD *)(v5 + 1200) == 42 )
    {
      *((_BYTE *)a1 + 880) = 0;
      v111 = *(_BYTE *)(v5 + 3);
LABEL_190:
      v10 = v111;
      v4 = 0;
      goto LABEL_9;
    }
    if ( *(_BYTE *)(v5 + 1193) )
    {
      v111 = *(_BYTE *)(v5 + 1194);
      if ( v111 )
      {
        v112 = (_OWORD *)(v5 + 732);
        v113 = 3;
        do
        {
          *v8 = *v112;
          v8[1] = v112[1];
          v8[2] = v112[2];
          v8[3] = v112[3];
          v8[4] = v112[4];
          v8[5] = v112[5];
          v8[6] = v112[6];
          v114 = v112[7];
          v112 += 8;
          v8[7] = v114;
          v8 += 8;
          --v113;
        }
        while ( v113 );
        *v8 = *v112;
        v8[1] = v112[1];
        v8[2] = v112[2];
        v8[3] = v112[3];
        v8[4] = v112[4];
        *((_BYTE *)v8 + 80) = *((_BYTE *)v112 + 80);
        ElementTable = CProgramConfig_GetElementTable(
                         (const struct CProgramConfig *)(v5 + 732),
                         (enum MP4_ELEMENT_ID *const)(a1 + 79),
                         128,
                         (unsigned __int8 *)a1 + 880);
        if ( ElementTable < 61 )
          memset_0(&a1[ElementTable + 79], -1, 4LL * (61 - ElementTable));
        goto LABEL_190;
      }
    }
    else
    {
      *((_BYTE *)a1 + 880) = 0;
    }
    return 8199;
  }
  v107 = v10 - 7;
  if ( v107 )
  {
    v108 = v107 - 4;
    if ( !v108 )
    {
      v10 = 7;
      goto LABEL_9;
    }
    v109 = v108 - 1;
    if ( v109 )
    {
      v110 = v109 - 2;
      if ( v110 )
      {
        if ( v110 != 17 )
          return 8199;
      }
    }
  }
  v10 = 8;
LABEL_9:
  v11 = *(_DWORD *)(v5 + 1200);
  *(_DWORD *)v177 = 0;
  if ( v11 == 42 )
  {
    v116 = 8;
    if ( v10 < 8 )
      v116 = (unsigned int)v10;
    if ( (unsigned int)pcmDmx_GetParam(*((_QWORD *)a1 + 553), 32, v177, v116) )
      return 5;
    v119 = v118;
    if ( *(int *)v177 > v117 )
      v117 = *(_DWORD *)v177;
    *(_DWORD *)v177 = 0;
    if ( v117 < v118 )
      v119 = v117;
    v12 = 0;
    v173 = v119;
  }
  else
  {
    v173 = 0;
    v12 = 0;
    if ( v11 != 150 )
      goto LABEL_11;
  }
  v120 = *(_DWORD *)(v5 + 8);
  if ( (unsigned int)v120 > 0x3D )
    goto LABEL_77;
  if ( v120 > 0 )
  {
    for ( i = 0; (int)i < v120; ++i )
    {
      v122 = *(_BYTE *)(v5 + 20LL * i + 20);
      if ( v122 == 1 )
      {
        --v10;
      }
      else if ( v122 == 2 )
      {
        if ( *(_BYTE *)(v5 + 20LL * i + 17) )
          v12 += *(_DWORD *)(v5 + 1208);
        if ( *(_BYTE *)(v5 + 1) == 4 )
          v12 += 96;
      }
    }
    *(_DWORD *)v177 = v12;
  }
LABEL_11:
  if ( *v9 != 31 && ((unsigned int)(v10 - 1) > 7 || *v9 > 14) )
    return 8199;
  memset_0(&v187, 0, 0xF4u);
  if ( *v9 > 0 )
  {
    if ( v11 != 42 && v11 != 150 )
    {
      v13 = 0;
      if ( *v9 == 31 )
      {
        *(_OWORD *)(a1 + 79) = 0;
        *(_OWORD *)(a1 + 83) = 0;
        do
          LODWORD(v13) = v13 + 1;
        while ( (int)v13 < 8 );
        memset_0(&a1[(int)v13 + 79], -1, 4LL * (61 - (int)v13));
        do
          LODWORD(v13) = v13 + 1;
        while ( (int)v13 < 61 );
      }
      else
      {
        do
        {
          a1[v13 + 79] = *((_DWORD *)&elementsTab + 7 * *v9 + (unsigned int)v13 - 7);
          v13 = (unsigned int)(v13 + 1);
        }
        while ( (int)v13 < 7 );
        memset_0(&a1[(int)v13 + 79], -1, 4LL * (61 - (int)v13));
        do
          LODWORD(v13) = v13 + 1;
        while ( (int)v13 < 61 );
      }
LABEL_21:
      v14 = 0;
      if ( v10 <= 0 )
        goto LABEL_85;
      do
      {
        *((_BYTE *)a1 + (unsigned int)v14 + 560) = v14;
        ++v14;
      }
      while ( v14 < v10 );
      while ( v14 < 8 )
      {
LABEL_85:
        v50 = v14++;
        *((_BYTE *)a1 + v50 + 560) = -1;
      }
      *((_BYTE *)a1 + 880) = *v9;
      goto LABEL_25;
    }
LABEL_221:
    *((_QWORD *)a1 + 313) = v5;
    v123 = *(_DWORD *)(v5 + 8);
    v171 = 0;
    v4 = a1[609] != v123;
    if ( (a3 & 2) != 0 )
    {
      a1[609] = v123;
      if ( *(int *)(v5 + 8) > 0 )
      {
        v124 = 0;
        v125 = v5;
        v126 = 0;
        do
        {
          v127 = *(_DWORD *)(v125 + 20LL * v124 + 12);
          if ( a1[v124 + 79] != v127 )
            v4 = 1;
          v48 = *((_BYTE *)a1 + v124 + 2440) == *(_BYTE *)(v5 + 20LL * v124 + 20);
          a1[v124 + 79] = v127;
          v128 = *(_BYTE *)(v5 + 20LL * v124 + 20);
          if ( !v48 )
            v4 = 1;
          *((_BYTE *)a1 + v124 + 2440) = v128;
          if ( a1[v124 + 79] == 17 )
            v126 |= v128 != 0;
          v129 = *(_DWORD *)(v5 + 20LL * v124 + 12);
          v130 = 0x2000;
          if ( v129 != 18 )
            v130 = 0;
          v131 = v130
               | (*(_BYTE *)(v5 + 20LL * v124 + 16) != 0 ? 2 : 0)
               | (*(_BYTE *)(v5 + 20LL * v124 + 18) != 0 ? 4 : 0)
               | (*(_BYTE *)(v5 + 20LL * v124 + 19) != 0 ? 8 : 0);
          v132 = 32;
          if ( v129 != 18 )
            v132 = 0;
          *((_DWORD *)&v187 + v124) |= (*(_BYTE *)(v5 + 20LL * v124 + 20) != 0 ? 0x10 : 0) | v132 | v131;
          if ( v129 == 17 && !v128 )
            *((_DWORD *)&v187 + v124) |= 0x40u;
          v125 = *((_QWORD *)a1 + 313);
          ++v124;
        }
        while ( v124 < *(_DWORD *)(v125 + 8) );
        v171 = v126;
LABEL_253:
        v9 = v183;
      }
    }
    else if ( v123 > 0 )
    {
      v133 = 0;
      do
      {
        v134 = *((_BYTE *)a1 + v133 + 2440);
        v135 = *(_DWORD *)(v5 + 20 * v133 + 12);
        if ( a1[v133 + 79] != v135 )
          v4 = 1;
        if ( v134 != *(_BYTE *)(v5 + 20 * v133 + 20) )
          v4 = 1;
        v136 = 0x2000;
        if ( v135 != 18 )
          v136 = 0;
        v137 = v136
             | (*(_BYTE *)(v5 + 20 * v133 + 16) != 0 ? 2 : 0)
             | (*(_BYTE *)(v5 + 20 * v133 + 18) != 0 ? 4 : 0)
             | (*(_BYTE *)(v5 + 20 * v133 + 19) != 0 ? 8 : 0);
        v138 = 32;
        v139 = (*(_BYTE *)(v5 + 20 * v133 + 20) != 0 ? 0x10 : 0) | v137;
        if ( v135 != 18 )
          v138 = 0;
        *((_DWORD *)&v187 + v133) |= v138 | v139;
        if ( v135 == 17 && !v134 )
          *((_DWORD *)&v187 + v133) |= 0x40u;
        v133 = (unsigned int)(v133 + 1);
      }
      while ( (int)v133 < v123 );
      goto LABEL_253;
    }
    *((_BYTE *)a1 + 4604) = 0;
    v140 = *((_QWORD *)a1 + 313);
    if ( *(_DWORD *)(v140 + 8) )
      *((_BYTE *)a1 + 4604) = *(_BYTE *)(v5 + 31);
    if ( (a3 & 2) != 0 )
      a1[*(unsigned int *)(v140 + 8) + 79] = 7;
    goto LABEL_21;
  }
  if ( v11 == 150 || v11 == 42 )
    goto LABEL_221;
  v51 = (_BYTE *)(v5 + 745);
  if ( *(_BYTE *)(v5 + 1193) && *v51 )
  {
    v54 = (unsigned __int8 *)(v5 + 746);
    *((_BYTE *)a1 + 1470) = *(_BYTE *)(v5 + 746);
    v52 = (unsigned __int8 *)(v5 + 747);
    v53 = *(_BYTE *)(v5 + 747);
  }
  else
  {
    *((_BYTE *)a1 + 1470) = -1;
    v52 = (unsigned __int8 *)(v5 + 747);
    v53 = -1;
    v54 = (unsigned __int8 *)(v5 + 746);
  }
  *((_BYTE *)a1 + 1471) = v53;
  if ( *(_BYTE *)(v5 + 1193) )
    pcmDmx_SetMatrixMixdownFromPce(*((_QWORD *)a1 + 553), (unsigned __int8)*v51, *v54, *v52);
LABEL_25:
  v15 = 0x10000000;
  a1[353] = *v9;
  v16 = *(_DWORD *)(v5 + 1200);
  if ( *v9 != 31 )
    v15 = 0;
  v17 = a3 & 2;
  if ( a1[352] != v16 )
  {
    if ( v17 )
    {
      a1[352] = v16;
      v16 = *(_DWORD *)(v5 + 1200);
    }
    v4 = 1;
  }
  if ( v16 != 39 )
    goto LABEL_29;
  v141 = *(_DWORD *)(v5 + 8);
  if ( !v141 )
    goto LABEL_29;
  if ( a1[14] == v141 && a1[14] * *((unsigned __int8 *)a1 + 2564) == *(_DWORD *)(v5 + 1204) )
  {
    LOBYTE(v19) = v175;
    v18 = v178;
    goto LABEL_30;
  }
  if ( (v19 = *(_DWORD *)(v5 + 1204) / v141, (unsigned __int8)(v19 - 1) > 1u)
    && ((_BYTE)v19 != 3 || !*(_BYTE *)v5)
    && (_BYTE)v19 != 4
    || *(_DWORD *)(v5 + 1204) % v141 )
  {
LABEL_29:
    v18 = 1;
    LOBYTE(v19) = 1;
    goto LABEL_30;
  }
  v18 = v19;
LABEL_30:
  if ( *((_BYTE *)a1 + 2565) != (_BYTE)v19 )
  {
    if ( v17 )
    {
      *((_BYTE *)a1 + 2565) = v19;
      *((_BYTE *)a1 + 2564) = v18;
    }
    v4 = 1;
  }
  v20 = v18;
  if ( *(_DWORD *)(v5 + 1208) % (int)v18 )
    return 8200;
  a1[354] = 0;
  if ( *(_DWORD *)(v5 + 1200) == 39 )
  {
    v142 = *(_BYTE *)(v5 + 2);
    if ( *((_BYTE *)a1 + 2516) != v142 )
      v4 = 1;
    if ( v17 )
      *((_BYTE *)a1 + 2516) = v142;
    if ( v179 != *(char *)(v5 + 1229) )
      v4 = 1;
  }
  a1[357] = *(_DWORD *)(v5 + 1216);
  v21 = *(_DWORD *)(v5 + 1220);
  if ( a1[358] != v21 )
    v4 = 1;
  if ( v17 )
    a1[358] = v21;
  else
    v21 = a1[358];
  v22 = *(_BYTE *)(v5 + 1229) != 0 ? 0x8000 : 0;
  v23 = *(_BYTE *)(v5 + 1230) != 0 ? 0x20000 : 0;
  if ( *(_BYTE *)(v5 + 1229) )
  {
    v170 = 1;
    if ( *(_DWORD *)(v5 + 1220) )
    {
      if ( v18 != 1 && (v18 & 1) != 0 )
        return 8200;
      if ( v17 )
        a1[358] = v21 / *((unsigned __int8 *)a1 + 2564);
    }
  }
  else
  {
    v170 = 0;
  }
  v24 = *(_DWORD *)(v5 + 1200);
  if ( v24 == 2 && *(_BYTE *)(v5 + 1229) == 1 && *(_DWORD *)(v5 + 1220) > (unsigned int)(2 * *(_DWORD *)(v5 + 1204)) )
    return 8200;
  if ( v24 == 39 )
  {
    v171 = 0;
    v25 = v15
        | v23
        | v22
        | (*(_BYTE *)(v5 + 1226) != 0)
        | (*(_BYTE *)(v5 + 1227) != 0 ? 2 : 0)
        | (*(_BYTE *)(v5 + 1228) != 0 ? 4 : 0)
        | (*(_BYTE *)(v5 + 1229) != 0 ? 32784 : 16)
        | (*(_BYTE *)(v5 + 2) != 0 ? 0x40000 : 0)
        | (*(_BYTE *)(v5 + 4) != 0 ? 0x10000 : 0);
    if ( *((_BYTE *)a1 + 4362) )
      v171 = *(_BYTE *)(v5 + 2);
  }
  else
  {
    v25 = v15
        | v23
        | v22
        | (*(_BYTE *)(v5 + 1226) != 0)
        | (*(_BYTE *)(v5 + 1227) != 0 ? 2 : 0)
        | (*(_BYTE *)(v5 + 1228) != 0 ? 4 : 0);
  }
  v26 = *(_BYTE *)(v5 + 1225);
  v27 = 32;
  if ( v24 != 23 )
    v27 = 0;
  v28 = v25 | v27 | (((*(char *)(v5 + 1225) >> 7) & 0xFFFFFFC0) + 64);
  if ( v24 == 42 )
  {
    v143 = 262400;
    if ( !*(_BYTE *)(v5 + 20) )
      v143 = 256;
    v29 = v28 | v143;
  }
  else
  {
    v29 = v25 | v27 | (((*(char *)(v5 + 1225) >> 7) & 0xFFFFFFC0) + 64);
  }
  v176 = v29;
  if ( v26 >= 0 && *v183 <= 0 )
    return 8196;
  *((_BYTE *)a1 + 1444) = v26;
  if ( *(char *)(v5 + 1225) > 1 )
    return 8196;
  v30 = a1 + 355;
  if ( a1[14] != *(_DWORD *)(v5 + 1204)
    || (v28 = (unsigned int)(*(int *)(v5 + 1208) >> 31),
        LODWORD(v28) = *(_DWORD *)(v5 + 1208) % v20,
        *v30 != *(_DWORD *)(v5 + 1208) / v20) )
  {
    v4 = 1;
    if ( v17 )
    {
      result = getSamplingRateInfo(a1 + 8, *(unsigned int *)(v5 + 1208), *(unsigned __int8 *)(v5 + 1231));
      if ( (_DWORD)result )
        return result;
      v72 = *((unsigned __int8 *)a1 + 2564);
      HIDWORD(v28) = 0;
      v73 = a1[14] / v72;
      a1[350] = v73;
      LODWORD(v28) = *(_DWORD *)(v5 + 1208) % v72;
      *v30 = *(_DWORD *)(v5 + 1208) / v72;
      if ( v73 <= 0 )
        return 8200;
    }
  }
  if ( a1[1] != v10 )
    v4 = 1;
  if ( (a3 & 1) != 0 )
  {
    if ( v4 )
      *v184 = 1;
    v74 = v188;
    v75 = v202;
    *(_OWORD *)(a1 + 18) = v187;
    v76 = v189;
    *(_OWORD *)(a1 + 22) = v74;
    v77 = v190;
    *(_OWORD *)(a1 + 26) = v76;
    v78 = v191;
    *(_OWORD *)(a1 + 30) = v77;
    v79 = v192;
    *(_OWORD *)(a1 + 34) = v78;
    v80 = v193;
    *(_OWORD *)(a1 + 38) = v79;
    v81 = v194;
    *(_OWORD *)(a1 + 42) = v80;
    v82 = v195;
    *(_OWORD *)(a1 + 46) = v81;
    v83 = v196;
    *(_OWORD *)(a1 + 50) = v82;
    v84 = v197;
    *(_OWORD *)(a1 + 54) = v83;
    v85 = v198;
    *(_OWORD *)(a1 + 58) = v84;
    v86 = v199;
    *(_OWORD *)(a1 + 62) = v85;
    v87 = v200;
    *(_OWORD *)(a1 + 66) = v86;
    v88 = v201;
    *(_OWORD *)(a1 + 70) = v87;
    *(_OWORD *)(a1 + 74) = v88;
    a1[78] = v75;
    a1[17] = v29;
    return 0;
  }
  v31 = *(_DWORD *)(v5 + 1200);
  v32 = v170;
  if ( v31 == 42 && v170 )
  {
    v144 = 0;
    v33 = -1;
    while ( v144 < *(_DWORD *)(*((_QWORD *)a1 + 313) + 8LL) )
    {
      v28 = v144;
      if ( (unsigned int)(a1[v144 + 79] - 16) <= 2 )
      {
        if ( v33 >= 0 )
        {
          v145 = *((unsigned __int8 *)a1 + v144 + 2440);
          if ( v33 != v145 || (_BYTE)v145 )
            goto LABEL_77;
        }
        else
        {
          v33 = *((_BYTE *)a1 + v144 + 2440);
        }
      }
      ++v144;
    }
    if ( v33 < 0 )
      goto LABEL_77;
    v32 = v170;
    if ( v33 == 3 )
    {
      v29 |= 0x8000000u;
      v176 = v29;
    }
  }
  else
  {
    v33 = -1;
  }
  v34 = v184;
  if ( !*v184 )
    goto LABEL_57;
  if ( v31 == 39 )
  {
    if ( !v171 || !*(_BYTE *)(v5 + 2) )
      goto LABEL_113;
    v151 = !v32 || !*((_QWORD *)a1 + 321);
    mpegSurroundDecoder_ConfigureQmfDomain(*((_QWORD *)a1 + 544), v151, (unsigned int)a1[350], 39);
    goto LABEL_317;
  }
  if ( v31 == 42 )
  {
    if ( !v32 )
      goto LABEL_113;
    v28 = 32;
    *((_BYTE *)a1 + 2602) = v10;
    a1[663] = 0;
    v146 = v10;
    LOWORD(v181) = 6160;
    BYTE2(v181) = 32;
    if ( v33 == 1 )
      v146 = 2;
    *((_BYTE *)a1 + 2604) = v146;
    v147 = *(unsigned __int8 *)(v5 + 2);
    *((_WORD *)a1 + 1330) = 64;
    v148 = *(&v180 + v147);
    v149 = 64;
    *((_BYTE *)a1 + 2657) = v148;
    if ( *(_BYTE *)(v5 + 2) != 1 )
      v149 = 32;
    *((_BYTE *)a1 + 2663) = v149;
    v150 = 12;
    v48 = *(_BYTE *)(v5 + 2) == 1;
    *((_BYTE *)a1 + 2667) = 64;
    if ( !v48 )
      v150 = 6;
    *((_BYTE *)a1 + 2669) = 1;
    *((_BYTE *)a1 + 2665) = v150;
    *((_BYTE *)a1 + 2605) = v33 == 3;
    *((_BYTE *)a1 + 2606) = v33 == 3;
LABEL_317:
    *((_BYTE *)a1 + 2600) = 1;
    goto LABEL_113;
  }
  *((_BYTE *)a1 + 2600) = 0;
LABEL_113:
  for ( j = 0; j < v10; ++j )
  {
    if ( j >= 8 )
      goto LABEL_77;
    v90 = CDKaalloc_L(1728);
    *(_QWORD *)&a1[2 * j + 370] = v90;
    if ( !v90 )
      goto LABEL_77;
  }
  v91 = 0;
  LODWORD(v183) = v29 & 0x300;
  v92 = 16;
  v181 = 16;
  if ( (v29 & 0x300) != 0 )
  {
    v92 = *(_DWORD *)(v5 + 8);
    v181 = v92;
  }
  for ( k = 0; k < v92 && ((v29 & 0x4370) == 0 || v91 < v10); ++k )
  {
    v94 = a1[k + 79];
    if ( v94 < 2 || v94 == 3 || v94 == 16 || v94 - 17 <= 1 )
    {
      LOBYTE(v28) = *((_BYTE *)a1 + k + 2440);
      ELChannels = CAacDecoder_GetELChannels(v94, v28);
      if ( v91 >= 8 )
        goto LABEL_77;
      if ( !*(_QWORD *)&a1[2 * v91 + 370] )
        goto LABEL_77;
      *(_QWORD *)(*(_QWORD *)&a1[2 * v91 + 370] + 1720LL) = calloc(v95, 0x10u);
      if ( !*(_QWORD *)(*(_QWORD *)&a1[2 * v91 + 370] + 1720LL) )
        goto LABEL_77;
      if ( v91 )
      {
        *(_QWORD *)(*(_QWORD *)&a1[2 * v91 + 370] + 1712LL) = CDKaalloc_L(17288);
        **(_QWORD **)(*(_QWORD *)&a1[2 * v91 + 370] + 1720LL) = **(_QWORD **)(*((_QWORD *)a1 + 185) + 1720LL);
      }
      else
      {
        *(_QWORD *)(*((_QWORD *)a1 + 185) + 1712LL) = CDKaalloc_L(17292);
        **(_QWORD **)(*((_QWORD *)a1 + 185) + 1720LL) = CDKaalloc_L(0x2000);
      }
      v96 = *(_QWORD *)&a1[2 * v91 + 370];
      v97 = *(_QWORD *)(v96 + 1712);
      if ( !v97 || !**(_QWORD **)(v96 + 1720) )
        goto LABEL_77;
      v98 = ELChannels;
      *(_QWORD *)(v96 + 1704) = v97;
      v28 = *((_QWORD *)a1 + 202) + 4LL * (v91 << 10);
      *(_QWORD *)(*(_QWORD *)&a1[2 * v91 + 370] + 1664LL) = v28;
      if ( v98 == 2 )
      {
        if ( v91 >= 7 )
          goto LABEL_77;
        v99 = *(_QWORD *)&a1[2 * v91 + 372];
        if ( !v99 )
          goto LABEL_77;
        *(_QWORD *)(v99 + 1712) = *(_QWORD *)(*(_QWORD *)&a1[2 * v91 + 370] + 1712LL);
        *(_QWORD *)(*(_QWORD *)&a1[2 * v91 + 372] + 1720LL) = *(_QWORD *)(*(_QWORD *)&a1[2 * v91 + 370] + 1720LL);
        **(_QWORD **)(*(_QWORD *)&a1[2 * v91 + 372] + 1720LL) = **(_QWORD **)(*(_QWORD *)&a1[2 * v91 + 370] + 1720LL);
        *(_QWORD *)(*(_QWORD *)&a1[2 * v91 + 372] + 1704LL) = *(_QWORD *)(*(_QWORD *)&a1[2 * v91 + 370] + 1712LL)
                                                            + 2168LL;
        v28 = *((_QWORD *)a1 + 202) + 4LL * ((v91 << 10) + 1024);
        *(_QWORD *)(*(_QWORD *)&a1[2 * v91 + 372] + 1664LL) = v28;
      }
      v91 += v98;
    }
    v29 = v176;
    if ( a1[k + 79] == 7 )
      break;
    v92 = v181;
  }
  v100 = *(_DWORD *)(v5 + 1200);
  if ( v100 <= 0x1D )
  {
    v101 = 536870948;
    if ( _bittest(&v101, v100) )
    {
      if ( v91 > 2 )
      {
        *((_QWORD *)a1 + 201) = CDKaalloc_L(1728);
        *(_QWORD *)(*((_QWORD *)a1 + 201) + 1720LL) = calloc(1u, 0x10u);
        v152 = *(_QWORD **)(*((_QWORD *)a1 + 201) + 1720LL);
        if ( !v152 )
          goto LABEL_77;
        *v152 = **(_QWORD **)(*((_QWORD *)a1 + 185) + 1720LL);
        *(_QWORD *)(*((_QWORD *)a1 + 201) + 1712LL) = CDKaalloc_L(17288);
        v153 = *((_QWORD *)a1 + 201);
        v154 = *(_QWORD *)(v153 + 1712);
        if ( !v154 || !**(_QWORD **)(v153 + 1720) )
          goto LABEL_77;
        *(_QWORD *)(v153 + 1704) = v154;
      }
    }
  }
  for ( m = 0; m < v10; ++m )
  {
    v103 = calloc(1u, 0x12A8u);
    *(_QWORD *)&a1[2 * m + 386] = v103;
    if ( !v103 )
      goto LABEL_77;
    *(_QWORD *)(*(_QWORD *)&a1[2 * m + 386] + 4184LL) = CDKaalloc_L(4096);
    if ( !*(_QWORD *)(*(_QWORD *)&a1[2 * m + 386] + 4184LL) )
      goto LABEL_77;
    **(_QWORD **)&a1[2 * m + 386] = CDKaalloc_L(3072);
    v104 = *(_QWORD **)&a1[2 * m + 386];
    if ( !*v104 )
      goto LABEL_77;
    if ( (v29 & 0x4300) != 0 )
    {
      *(_QWORD *)(*(_QWORD *)&a1[2 * m + 386] + 64LL) = calloc(1u, 0x206u);
      v104 = *(_QWORD **)&a1[2 * m + 386];
      if ( !v104[8] )
        goto LABEL_77;
    }
    if ( (v29 & 0x300) == 0 )
    {
      v105 = *(_QWORD **)&a1[2 * m + 370];
      v106 = v105[214];
      v105[18] = v104 + 9;
      v105[19] = v106 + 4464;
    }
  }
  if ( (v29 & 0x100) != 0 )
  {
    for ( n = 0; n < v173; ++n )
    {
      if ( !*(_QWORD *)&a1[2 * n + 1118] )
      {
        v156 = calloc(0x80u, 4u);
        *(_QWORD *)&a1[2 * n + 1118] = v156;
        if ( !v156 )
          goto LABEL_77;
      }
      m = n;
    }
  }
  if ( !(_DWORD)v183 )
    goto LABEL_155;
  v157 = 0;
  m = 0;
  v174 = 0;
  for ( ii = 0; ii < *(_DWORD *)(v5 + 8); ++ii )
  {
    v159 = a1[ii + 79];
    v160 = v159 <= 0x11;
    if ( v159 == 17 )
    {
      if ( *((_BYTE *)a1 + ii + 2440) != 1 )
      {
        v161 = 2;
        goto LABEL_341;
      }
      v160 = 1;
    }
    if ( v160 && (v162 = 196619, _bittest(&v162, v159)) || (v161 = 0, v159 == 18) )
      v161 = 1;
LABEL_341:
    if ( (*((_BYTE *)&v187 + 4 * ii) & 0x40) != 0 )
    {
      v157 = 1;
      v174 = 1;
      if ( !*(_QWORD *)&a1[2 * ii + 410] )
      {
        v163 = calloc(1u, 0x828u);
        *(_QWORD *)&a1[2 * ii + 410] = v163;
        if ( !v163 )
          goto LABEL_77;
        v157 = 1;
      }
    }
    v164 = 0;
    if ( v161 )
    {
      do
      {
        *(_QWORD *)(*(_QWORD *)&a1[2 * m + 386] + 4768LL) = *(_QWORD *)&a1[2 * ii + 410];
        v165 = *(_QWORD *)&a1[2 * m + 386];
        v166 = *(_QWORD *)(v165 + 4768);
        if ( v166 )
        {
          *(_QWORD *)(v166 + 8 * v164 + 16) = *(_QWORD *)(v165 + 4184);
          *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&a1[2 * m + 386] + 4768LL) + 8LL) = **(_QWORD **)(*(_QWORD *)&a1[2 * m + 370]
                                                                                             + 1720LL);
        }
        ++m;
        v164 = (unsigned int)(v164 + 1);
      }
      while ( (int)v164 < v161 );
      v157 = v174;
    }
    if ( v157 && v161 == 2 )
    {
      if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&a1[2 * m + 368] + 1720LL) + 8LL) )
      {
        v167 = calloc(1u, 0x804u);
        v157 = v174;
        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&a1[2 * m + 368] + 1720LL) + 8LL) = v167;
      }
      if ( !*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&a1[2 * m + 368] + 1720LL) + 8LL) )
        goto LABEL_77;
    }
    if ( v161 )
    {
      v168 = m - v161;
      *(_DWORD *)(*(_QWORD *)&a1[2 * v168 + 386] + 4108LL) = 12345;
      if ( a1[ii + 79] == 17 && *(_BYTE *)(v5 + 20 * (ii + 1LL)) != 1 )
        *(_DWORD *)(*(_QWORD *)&a1[2 * v168 + 388] + 4108LL) = 67890;
    }
  }
  v29 = v176;
LABEL_155:
  if ( v10 != *a1 )
  {
    *a1 = m;
    a1[2] = m;
  }
  if ( *(_DWORD *)v177 && (unsigned int)CDK_Delay_Create((struct CDK_SignalDelay *)(a1 + 1160), v177[0], 1u) )
  {
LABEL_77:
    CAacDecoder_DeInit(a1, 0);
    return 2;
  }
  else
  {
    v34 = v184;
    a1[1] = v10;
    a1[630] = 0;
LABEL_57:
    v35 = *((_QWORD *)a1 + 185);
    if ( v35 )
    {
      *((_QWORD *)a1 + 323) = **(_QWORD **)(v35 + 1720);
      *((_WORD *)a1 + 1296) = 512;
    }
    if ( *v34 )
    {
      v36 = 0;
      if ( a1[1] > 0 )
      {
        v37 = v182;
        v38 = (unsigned int *)(a1 + 532);
        do
        {
          v39 = a1[352];
          if ( v39 == 23 || v39 == 39 )
            v40 = a1[355];
          else
            v40 = a1[355] / 8;
          *(_DWORD *)(*(_QWORD *)&a1[2 * v36 + 370] + 1692LL) = v40;
          *(_DWORD *)(*(_QWORD *)&a1[2 * v36 + 370] + 1700LL) = v37;
          v41 = *(_QWORD *)&a1[2 * v36 + 386];
          *(_QWORD *)(v41 + 8) = *(_QWORD *)v41;
          *(_QWORD *)(v41 + 28) = 0;
          *(_DWORD *)(v41 + 24) = 0;
          *(_DWORD *)(v41 + 40) = 768;
          *(_QWORD *)(v41 + 48) = 0;
          *(_QWORD *)(v41 + 56) = 0;
          *(_DWORD *)(*(_QWORD *)&a1[2 * v36 + 386] + 1828LL) = 0;
          *(_BYTE *)(*(_QWORD *)&a1[2 * v36 + 386] + 1832LL) = -1;
          *(_WORD *)(*(_QWORD *)&a1[2 * v36 + 386] + 2232LL) = 256;
          aacDecoder_drcInitChannelData((struct CDrcChannelData *)(*(_QWORD *)&a1[2 * v36 + 386] + 4112LL));
          v42 = *((_QWORD *)a1 + 553);
          if ( v42 )
          {
            for ( jj = 0; jj != 2; ++jj )
            {
              v44 = 5 * jj;
              *(_OWORD *)(v42 + 4 * v44) = xmmword_1800B0B90;
              *(_DWORD *)(v42 + 4 * v44 + 16) = 0;
            }
            v38 = (unsigned int *)(a1 + 532);
          }
          CConcealment_InitChannelData(*(_QWORD *)&a1[2 * v36++ + 386] + 4176LL, v38, v37);
        }
        while ( v36 < a1[1] );
        v5 = v186;
        v29 = v176;
        v34 = v184;
      }
      if ( *v34 )
      {
        v45 = (unsigned int)a1[358];
        v46 = a1[350];
        v47 = (unsigned int)a1[355];
        v48 = (_DWORD)v45 == 0;
        if ( (_DWORD)v45 )
        {
          v48 = 0;
          v47 = (unsigned int)((int)v47 * (int)v45 / (int)v46);
        }
        if ( v48 )
          v45 = v46;
        if ( (unsigned int)CDK_drcDec_Init(*((_QWORD *)a1 + 556), v47, v45, (unsigned int)*a1) )
          goto LABEL_77;
        if ( *v34 )
        {
          v55 = (_BYTE *)*((_QWORD *)a1 + 542);
          v55[56] = v55[20];
          v55[40] = 0;
          v55[57] = 0;
        }
      }
    }
    v56 = *(_DWORD *)(v5 + 1200);
    if ( v56 == 150 || v56 == 42 )
    {
      pcmLimiter_SetAttack(*((_QWORD *)a1 + 554), 5);
      v169 = *((_QWORD *)a1 + 554);
      if ( v169 )
        *(_DWORD *)(v169 + 24) = 1063528710;
    }
    v57 = v188;
    v58 = v202;
    *(_OWORD *)(a1 + 18) = v187;
    v59 = v189;
    *(_OWORD *)(a1 + 22) = v57;
    v60 = v190;
    *(_OWORD *)(a1 + 26) = v59;
    v61 = v191;
    *(_OWORD *)(a1 + 30) = v60;
    v62 = v192;
    *(_OWORD *)(a1 + 34) = v61;
    v63 = v193;
    *(_OWORD *)(a1 + 38) = v62;
    v64 = v194;
    *(_OWORD *)(a1 + 42) = v63;
    v65 = v195;
    *(_OWORD *)(a1 + 46) = v64;
    v66 = v196;
    *(_OWORD *)(a1 + 50) = v65;
    v67 = v197;
    *(_OWORD *)(a1 + 54) = v66;
    v68 = v198;
    *(_OWORD *)(a1 + 58) = v67;
    v69 = v199;
    *(_OWORD *)(a1 + 62) = v68;
    v70 = v200;
    *(_OWORD *)(a1 + 66) = v69;
    v71 = v201;
    *(_OWORD *)(a1 + 70) = v70;
    *(_OWORD *)(a1 + 74) = v71;
    a1[78] = v58;
    a1[17] = v29;
    *((_BYTE *)a1 + 2576) = v170;
    *((_BYTE *)a1 + 2577) = v170;
    *((_BYTE *)a1 + 4361) = v171;
    a1[360] = v29;
    return 0;
  }
}

```

## disassembly

```asm
0x1800069ec  mov     [rsp-8+arg_10], rbx
0x1800069f1  push    rbp
0x1800069f2  push    rsi
0x1800069f3  push    rdi
0x1800069f4  push    r12
0x1800069f6  push    r13
0x1800069f8  push    r14
0x1800069fa  push    r15
0x1800069fc  lea     rbp, [rsp-150h]
0x180006a04  sub     rsp, 250h
0x180006a0b  mov     rax, cs:__security_cookie
0x180006a12  xor     rax, rsp
0x180006a15  mov     [rbp+180h+var_40], rax
0x180006a1c  xor     r14d, r14d
0x180006a1f  mov     [rsp+280h+var_238], r9
0x180006a24  mov     [rsp+280h+var_25E], r8b
0x180006a29  mov     rdi, rdx
0x180006a2c  mov     [rsp+280h+var_228], rdx
0x180006a31  mov     rbx, rcx
0x180006a34  test    rcx, rcx
0x180006a37  jz      loc_1800077BC
0x180006a3d  mov     eax, [rdx+4B0h]
0x180006a43  lea     ecx, [r14+2]
0x180006a47  lea     r12d, [r14+1]
0x180006a4b  cmp     eax, ecx
0x180006a4d  jnz     loc_180006FCB
0x180006a53  mov     [rbx+57Ch], r12d
0x180006a5a  mov     [rsp+280h+var_248], r12d
0x180006a5f  mov     al, [rbx+0A10h]
0x180006a65  lea     rsi, [rbx+371h]
0x180006a6c  lea     r15, [rdx+4C8h]
0x180006a73  mov     [rsp+280h+var_24F], al
0x180006a77  mov     al, [rbx+1109h]
0x180006a7d  mov     [rsp+280h+var_25F], al
0x180006a81  mov     al, [rbx+0A04h]
0x180006a87  mov     [rsp+280h+var_250], al
0x180006a8b  mov     al, [rbx+0A05h]
0x180006a91  mov     [rsp+280h+var_258], eax
0x180006a95  mov     [rsp+280h+var_240], r15
0x180006a9a  cmp     [rsi+1CDh], r14b
0x180006aa1  jnz     loc_1800077F2
0x180006aa7  mov     r8d, 1D1h; Size
0x180006aad  xor     edx, edx; Val
0x180006aaf  mov     rcx, rsi; void *
0x180006ab2  call    memset_0
0x180006ab7  mov     byte ptr [rsi+2], 0Fh
0x180006abb  movsx   r13d, byte ptr [r15]
0x180006abf  mov     r10d, 8
0x180006ac5  or      r12d, 0FFFFFFFFh
0x180006ac9  lea     eax, [r10-2]
0x180006acd  lea     r8d, [r10+78h]; int
0x180006ad1  cmp     r13d, eax
0x180006ad4  jg      loc_1800076ED
0x180006ada  jnz     loc_180007729
0x180006ae0  mov     esi, [rdi+4B0h]
0x180006ae6  mov     dword ptr [rsp+280h+var_254], r14d
0x180006aeb  cmp     esi, 2Ah ; '*'
0x180006aee  jz      loc_18000792E
0x180006af4  mov     [rsp+280h+var_25C], r14d
0x180006af9  mov     r9d, r14d
0x180006afc  cmp     esi, 96h
0x180006b02  jz      loc_18000797D
0x180006b08  cmp     byte ptr [r15], 1Fh
0x180006b0c  jz      short loc_180006B25
0x180006b0e  lea     eax, [r13-1]
0x180006b12  cmp     eax, 7
0x180006b15  ja      loc_18000771F
0x180006b1b  cmp     byte ptr [r15], 0Eh
0x180006b1f  jg      loc_18000771F
0x180006b25  xor     edx, edx; Val
0x180006b27  lea     rcx, [rsp+280h+var_220]; void *
0x180006b2c  mov     r8d, 0F4h; Size
0x180006b32  call    memset_0
0x180006b37  cmp     byte ptr [r15], 0
0x180006b3b  jle     loc_18000701E
0x180006b41  cmp     esi, 2Ah ; '*'
0x180006b44  jz      loc_180007A57
0x180006b4a  cmp     esi, 96h
0x180006b50  jz      loc_180007A57
0x180006b56  xor     esi, esi
0x180006b58  cmp     byte ptr [r15], 1Fh
0x180006b5c  jz      loc_180007A03
0x180006b62  movsx   rax, byte ptr [r15]
0x180006b66  lea     rdx, ?elementsTab@@3QAY06$$CBW4MP4_ELEMENT_ID@@A; MP4_ELEMENT_ID const (near * elementsTab)[7]
0x180006b6d  imul    rax, 7
0x180006b71  mov     ecx, esi
0x180006b73  add     rax, rcx
0x180006b76  mov     eax, [rdx+rax*4-1Ch]
0x180006b7a  mov     [rbx+rsi*4+13Ch], eax
0x180006b81  inc     esi
0x180006b83  cmp     esi, 7
0x180006b86  jl      short loc_180006B62
0x180006b88  mov     eax, 3Dh ; '='
0x180006b8d  mov     edx, r12d; Val
0x180006b90  sub     eax, esi
0x180006b92  movsxd  r8, eax
0x180006b95  movsxd  rax, esi
0x180006b98  add     rax, 4Fh ; 'O'
0x180006b9c  shl     r8, 2; Size
0x180006ba0  lea     rcx, [rbx+rax*4]; void *
0x180006ba4  call    memset_0
0x180006ba9  mov     r8d, 1
0x180006baf  add     esi, r8d
0x180006bb2  cmp     esi, 3Dh ; '='
0x180006bb5  jl      short loc_180006BAF
0x180006bb7  xor     r12d, r12d
0x180006bba  mov     ecx, r12d
0x180006bbd  test    r13d, r13d
0x180006bc0  jle     loc_18000700B
0x180006bc6  mov     eax, ecx
0x180006bc8  mov     [rax+rbx+230h], cl
0x180006bcf  add     ecx, r8d
0x180006bd2  cmp     ecx, r13d
0x180006bd5  jl      short loc_180006BC6
0x180006bd7  cmp     ecx, 8
0x180006bda  jl      loc_18000700B
0x180006be0  mov     al, [r15]
0x180006be3  mov     [rbx+370h], al
0x180006be9  movsx   eax, byte ptr [r15]
0x180006bed  mov     esi, 10000000h
0x180006bf2  mov     r11b, [rsp+280h+var_25E]
0x180006bf7  mov     [rbx+584h], eax
0x180006bfd  cmp     byte ptr [r15], 1Fh
0x180006c01  mov     eax, [rdi+4B0h]
0x180006c07  cmovnz  esi, r12d
0x180006c0b  and     r11b, 2
0x180006c0f  cmp     [rbx+580h], eax
0x180006c15  jnz     loc_1800072E0
0x180006c1b  mov     r15d, 1
0x180006c21  cmp     eax, 27h ; '''
0x180006c24  jz      loc_180007C72
0x180006c2a  mov     r9b, r15b
0x180006c2d  mov     r10b, r15b
0x180006c30  cmp     [rbx+0A05h], r10b
0x180006c37  jnz     loc_180007CF0
0x180006c3d  mov     eax, [rdi+4B8h]
0x180006c43  cdq
0x180006c44  movzx   r15d, r9b
0x180006c48  idiv    r15d
0x180006c4b  test    edx, edx
0x180006c4d  jnz     loc_180007092
0x180006c53  mov     [rbx+588h], r12d
0x180006c5a  cmp     dword ptr [rdi+4B0h], 27h ; '''
0x180006c61  jz      loc_180007D0B
0x180006c67  mov     eax, [rdi+4C0h]
0x180006c6d  mov     ecx, 1
0x180006c72  mov     [rbx+594h], eax
0x180006c78  mov     edx, [rdi+4C4h]
0x180006c7e  mov     eax, [rbx+598h]
0x180006c84  cmp     eax, edx
0x180006c86  cmovnz  r14d, ecx
0x180006c8a  test    r11b, r11b
0x180006c8d  jz      loc_1800077C6
0x180006c93  mov     [rbx+598h], edx
0x180006c99  mov     cl, [rdi+4CDh]
0x180006c9f  mov     al, cl
0x180006ca1  neg     al
0x180006ca3  mov     al, [rdi+4CEh]
0x180006ca9  sbb     r8d, r8d
0x180006cac  and     r8d, 8000h
0x180006cb3  neg     al
0x180006cb5  sbb     r10d, r10d
0x180006cb8  and     r10d, 20000h
0x180006cbf  test    cl, cl
0x180006cc1  mov     ecx, 1
0x180006cc6  jnz     loc_180007D3F
0x180006ccc  mov     [rsp+280h+var_260], r12b
0x180006cd1  mov     r9d, [rdi+4B0h]
0x180006cd8  cmp     r9d, 2
0x180006cdc  jnz     short loc_180006CEA
0x180006cde  cmp     [rdi+4CDh], cl
0x180006ce4  jz      loc_180007D83
0x180006cea  mov     al, [rdi+4CCh]
0x180006cf0  neg     al
0x180006cf2  mov     al, [rdi+4CBh]
0x180006cf8  sbb     edx, edx
0x180006cfa  and     edx, 4
0x180006cfd  neg     al
0x180006cff  mov     eax, r12d
0x180006d02  sbb     ecx, ecx
0x180006d04  and     ecx, 2
0x180006d07  or      edx, ecx
0x180006d09  cmp     [rdi+4CAh], r12b
0x180006d10  setnz   al
0x180006d13  or      edx, eax
0x180006d15  or      edx, r8d
0x180006d18  or      edx, r10d
0x180006d1b  or      edx, esi
0x180006d1d  cmp     r9d, 27h ; '''
0x180006d21  jz      loc_180007D9C
0x180006d27  mov     r8d, edx
0x180006d2a  mov     r10b, [rdi+4C9h]
0x180006d31  mov     ecx, 20h ; ' '
0x180006d36  mov     al, r10b
0x180006d39  sar     al, 7
0x180006d3c  movsx   edx, al
0x180006d3f  mov     eax, 100h
0x180006d44  and     edx, 0FFFFFFC0h
0x180006d47  add     edx, 40h ; '@'
0x180006d4a  cmp     r9d, 17h
0x180006d4e  cmovnz  ecx, r12d
0x180006d52  or      edx, ecx
0x180006d54  or      edx, r8d
0x180006d57  cmp     r9d, 2Ah ; '*'
0x180006d5b  jz      loc_180007DF2
0x180006d61  mov     r12d, edx
0x180006d64  mov     [rsp+280h+var_258], r12d
0x180006d69  test    r10b, r10b
0x180006d6c  jns     loc_1800077A4
0x180006d72  mov     [rbx+5A4h], r10b
0x180006d79  mov     r10d, 1
0x180006d7f  cmp     [rdi+4C9h], r10b
0x180006d86  jg      loc_1800077B2
0x180006d8c  mov     r9d, [rdi+4B4h]
0x180006d93  lea     rsi, [rbx+58Ch]
0x180006d9a  cmp     [rbx+38h], r9d
0x180006d9e  jnz     loc_1800071C7
0x180006da4  mov     eax, [rdi+4B8h]
0x180006daa  cdq
0x180006dab  idiv    r15d
0x180006dae  cmp     [rsi], eax
0x180006db0  jnz     loc_1800071C7
0x180006db6  cmp     [rbx+4], r13d
0x180006dba  cmovnz  r14d, r10d
0x180006dbe  test    [rsp+280h+var_25E], r10b
0x180006dc3  jnz     loc_180007226
0x180006dc9  mov     r9d, [rdi+4B0h]
0x180006dd0  mov     al, [rsp+280h+var_260]
0x180006dd4  cmp     r9d, 2Ah ; '*'
0x180006dd8  jz      loc_180007E08
0x180006dde  or      r11d, 0FFFFFFFFh
0x180006de2  mov     r15, [rsp+280h+var_238]
0x180006de7  cmp     byte ptr [r15], 0
0x180006deb  jnz     loc_1800072FF
0x180006df1  mov     rax, [rbx+5C8h]
0x180006df8  test    rax, rax
0x180006dfb  jz      short loc_180006E17
0x180006dfd  mov     rax, [rax+6B8h]
0x180006e04  mov     rcx, [rax]
0x180006e07  mov     [rbx+0A18h], rcx
0x180006e0e  mov     word ptr [rbx+0A20h], 200h
0x180006e17  cmp     byte ptr [r15], 0
0x180006e1b  jz      loc_1800070B7
0x180006e21  xor     esi, esi
0x180006e23  cmp     [rbx+4], esi
0x180006e26  jle     loc_180006F6C
0x180006e2c  mov     r13d, [rsp+280h+var_248]
0x180006e31  lea     r14, [rbx+850h]
0x180006e38  lea     edi, [rsi+8]
0x180006e3b  lea     r12d, [rsi+1]
0x180006e3f  mov     eax, [rbx+580h]
0x180006e45  cmp     eax, 17h
0x180006e48  jz      loc_1800082DA
0x180006e4e  cmp     eax, 27h ; '''
0x180006e51  jz      loc_1800082DA
0x180006e57  mov     eax, [rbx+58Ch]
0x180006e5d  cdq
0x180006e5e  idiv    edi
0x180006e60  movsxd  r8, esi
0x180006e63  mov     rcx, [rbx+r8*8+5C8h]
0x180006e6b  mov     [rcx+69Ch], eax
0x180006e71  mov     rax, [rbx+r8*8+5C8h]
0x180006e79  mov     [rax+6A4h], r13d
0x180006e80  mov     rcx, [rbx+r8*8+608h]
0x180006e88  mov     rax, [rcx]
0x180006e8b  mov     [rcx+8], rax
0x180006e8f  mov     qword ptr [rcx+1Ch], 0
0x180006e97  mov     dword ptr [rcx+18h], 0
0x180006e9e  mov     dword ptr [rcx+28h], 300h
0x180006ea5  mov     qword ptr [rcx+30h], 0
0x180006ead  mov     qword ptr [rcx+38h], 0
0x180006eb5  mov     rax, [rbx+r8*8+608h]
0x180006ebd  mov     dword ptr [rax+724h], 0
0x180006ec7  mov     rax, [rbx+r8*8+608h]
0x180006ecf  mov     byte ptr [rax+728h], 0FFh
0x180006ed6  mov     rax, [rbx+r8*8+608h]
0x180006ede  mov     word ptr [rax+8B8h], 100h
0x180006ee7  mov     rcx, [rbx+r8*8+608h]
0x180006eef  add     rcx, 1010h; struct CDrcChannelData *
0x180006ef6  call    ?aacDecoder_drcInitChannelData@@YAXPEAUCDrcChannelData@@@Z; aacDecoder_drcInitChannelData(CDrcChannelData *)
0x180006efb  mov     r8, [rbx+1148h]
0x180006f02  test    r8, r8
0x180006f05  jz      short loc_180006F34
0x180006f07  xor     edx, edx
0x180006f09  movups  xmm0, cs:xmmword_1800B0B90
0x180006f10  lea     rcx, [rdx+rdx*4]
0x180006f14  add     rdx, r12
0x180006f17  movups  xmmword ptr [r8+rcx*4], xmm0
0x180006f1c  mov     eax, cs:dword_1800B0BA0
0x180006f22  mov     [r8+rcx*4+10h], eax
0x180006f27  cmp     rdx, 2
0x180006f2b  jnz     short loc_180006F09
0x180006f2d  lea     r14, [rbx+850h]
0x180006f34  movsxd  rax, esi
0x180006f37  mov     r8d, r13d
0x180006f3a  mov     rdx, r14
0x180006f3d  mov     rcx, [rbx+rax*8+608h]
0x180006f45  add     rcx, 1050h
0x180006f4c  call    ?CConcealment_InitChannelData@@YAXPEAUCConcealmentInfo@@PEAUCConcealParams_fl@@W4AACDEC_RENDER_MODE@@H@Z; CConcealment_InitChannelData(CConcealmentInfo *,CConcealParams_fl *,AACDEC_RENDER_MODE,int)
0x180006f51  add     esi, r12d
  ... truncated ...
```
