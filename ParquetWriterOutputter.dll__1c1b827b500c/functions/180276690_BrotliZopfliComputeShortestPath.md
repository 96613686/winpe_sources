# BrotliZopfliComputeShortestPath

- ea: `0x180276690`
- end: `0x180277481`
- name: `BrotliZopfliComputeShortestPath`
- size: `3569`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180264000`
- `0x180276500`

## callees

- `0x180268010`
- `0x1802680b0`
- `0x180276690`
- `0x180277800`
- `0x1802779d0`
- `0x180277a50`
- `0x180277b10`
- `0x180277fa0`
- `0x180277fb0`
- `0x180278a60`
- `0x1802919f0`
- `0x18030c3f0`
- `0x18030cf60`

## pseudocode

```c
__int64 __fastcall BrotliZopfliComputeShortestPath(
        __int64 a1,
        int a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        unsigned __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // rdi
  __int64 v13; // rsi
  __int64 v14; // rax
  unsigned __int64 v15; // rax
  _DWORD *v16; // rdx
  __int64 v17; // r9
  __int64 v18; // rbp
  __int64 v19; // rcx
  __int64 v20; // r8
  unsigned __int64 v21; // rdx
  __int64 v22; // r11
  unsigned __int64 v23; // r10
  char *v24; // r15
  unsigned __int64 v25; // r14
  __int64 v26; // r9
  unsigned __int64 v27; // r12
  __int64 v28; // r13
  unsigned __int64 v29; // rbx
  unsigned __int64 v30; // rcx
  unsigned __int64 v31; // rbp
  unsigned __int64 v32; // r8
  __int64 v33; // rdx
  _BYTE *v34; // rsi
  _BYTE *v35; // r11
  _BYTE *v36; // r10
  unsigned __int64 v37; // rdx
  unsigned __int64 v38; // r9
  _DWORD *v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // r9
  unsigned __int64 v43; // r10
  __int64 v44; // r11
  __int64 v45; // rbx
  __int64 v46; // r13
  __int64 v47; // rbp
  unsigned __int64 v48; // rdx
  unsigned __int64 v49; // r8
  __int64 v50; // r12
  unsigned __int64 v51; // rdi
  __int64 v52; // r14
  unsigned __int64 v53; // rsi
  __int64 v54; // rdx
  char *v55; // rcx
  __int64 v56; // r11
  char *v57; // r10
  __int64 v58; // r8
  __int64 v59; // rax
  unsigned int v60; // eax
  _QWORD *v61; // rax
  __int64 v62; // rcx
  __int64 v63; // rbp
  unsigned __int64 v64; // rbx
  unsigned int v65; // eax
  __int64 v66; // rdx
  int v67; // eax
  __int64 v68; // r15
  __int64 v69; // rax
  __int64 v70; // rbx
  unsigned __int64 updated; // rax
  unsigned __int64 v72; // rcx
  unsigned __int64 v73; // rcx
  unsigned __int64 v74; // r8
  __int64 v75; // r13
  unsigned __int64 v76; // rax
  unsigned __int64 v77; // rdi
  unsigned __int64 v78; // rsi
  unsigned int v79; // eax
  unsigned __int64 v80; // r8
  __int64 v81; // r11
  __int64 v82; // rdx
  __int64 v83; // rdx
  unsigned __int64 v84; // r9
  __int64 v85; // rbx
  unsigned __int64 v86; // r10
  __int64 v87; // rbp
  __int64 v88; // r12
  unsigned __int64 v89; // rdi
  __int64 v90; // r14
  unsigned __int64 v91; // rsi
  unsigned __int64 v92; // r11
  _DWORD *v93; // rcx
  __int64 v94; // rdx
  unsigned __int64 v95; // r10
  unsigned __int64 v96; // r9
  unsigned __int64 v97; // r8
  unsigned __int64 v98; // r8
  __int64 v99; // rax
  unsigned int v100; // eax
  int v101; // eax
  __int64 v102; // r14
  unsigned __int64 v103; // rbx
  unsigned int v104; // eax
  unsigned __int64 v105; // r10
  __int64 v106; // rdx
  unsigned __int64 v107; // r8
  unsigned __int64 v108; // r9
  __int64 v109; // r12
  __int64 v110; // r11
  __int64 v111; // r13
  __int64 v112; // rdx
  __int64 v113; // rsi
  unsigned __int64 v114; // rdi
  __int64 v115; // rbp
  unsigned __int64 v116; // r14
  __int64 v117; // rdx
  unsigned __int64 v118; // rbx
  _DWORD *v119; // rcx
  unsigned __int64 v120; // r10
  unsigned __int64 v121; // r9
  unsigned __int64 v122; // r8
  __int64 v123; // r11
  unsigned int v124; // eax
  int v125; // eax
  __int64 v126; // rbp
  unsigned __int64 v127; // rdi
  __int64 v128; // rbx
  unsigned __int64 v130; // [rsp+80h] [rbp-19E8h]
  __int64 v131; // [rsp+80h] [rbp-19E8h]
  unsigned __int64 v132; // [rsp+88h] [rbp-19E0h]
  unsigned __int64 v133; // [rsp+88h] [rbp-19E0h]
  unsigned __int64 v134; // [rsp+90h] [rbp-19D8h]
  unsigned __int64 v135; // [rsp+90h] [rbp-19D8h]
  unsigned __int64 v136; // [rsp+98h] [rbp-19D0h]
  unsigned __int64 v137; // [rsp+98h] [rbp-19D0h]
  unsigned __int64 v138; // [rsp+98h] [rbp-19D0h]
  __int64 v139; // [rsp+A0h] [rbp-19C8h]
  unsigned __int64 v140; // [rsp+A0h] [rbp-19C8h]
  unsigned __int64 v141; // [rsp+A0h] [rbp-19C8h]
  __int64 v142; // [rsp+A8h] [rbp-19C0h]
  unsigned __int64 v143; // [rsp+B0h] [rbp-19B8h]
  unsigned __int64 v144; // [rsp+B0h] [rbp-19B8h]
  unsigned __int64 v145; // [rsp+B8h] [rbp-19B0h]
  unsigned __int64 v146; // [rsp+B8h] [rbp-19B0h]
  unsigned __int64 v147; // [rsp+C0h] [rbp-19A8h]
  __int64 v148; // [rsp+C0h] [rbp-19A8h]
  unsigned __int64 v149; // [rsp+C0h] [rbp-19A8h]
  unsigned __int64 v152; // [rsp+E0h] [rbp-1988h]
  unsigned __int64 v153; // [rsp+E0h] [rbp-1988h]
  unsigned __int64 v154; // [rsp+E8h] [rbp-1980h]
  unsigned __int64 v155; // [rsp+F8h] [rbp-1970h]
  __int64 v156; // [rsp+108h] [rbp-1960h]
  _BYTE v159[256]; // [rsp+120h] [rbp-1948h] BYREF
  __int64 v160; // [rsp+220h] [rbp-1848h]
  _BYTE v161[4928]; // [rsp+230h] [rbp-1838h] BYREF
  _DWORD v162[40]; // [rsp+1570h] [rbp-4F8h] BYREF
  _QWORD v163[128]; // [rsp+1610h] [rbp-458h] BYREF

  v11 = a4;
  v12 = a3;
  v13 = a10;
  v14 = 325;
  if ( *(int *)(a7 + 4) <= 10 )
    v14 = 150;
  v154 = v14;
  v15 = StoreLookaheadH10(a7, a11);
  if ( v12 < v15 )
    v155 = v11;
  else
    v155 = v11 - v15 + v12 + 1;
  *v16 = 0;
  v16[3] = 0;
  InitZopfliCostModel(v17, v161, v12);
  ZopfliCostModelSetFromLiteralCosts(v161, v11, a5, a6);
  v160 = 0;
  v18 = 0;
  v142 = 0;
  v156 = HashTypeLengthH10(v19, 0, v20);
  if ( v156 - 1 < v12 )
  {
    v22 = (unsigned int)(v21 + 16);
    do
    {
      v23 = a8;
      v24 = (char *)v163;
      v25 = v18 + v11;
      v26 = a6;
      v136 = v25;
      if ( v25 < a8 )
        v23 = v25;
      v27 = v12 - v18;
      v134 = v23;
      v28 = a6 & v25;
      v130 = v12 - v18;
      v29 = v25 - 1;
      v30 = 64;
      v139 = a6 & v25;
      if ( *(_DWORD *)(a7 + 4) != 11 )
        v30 = v22;
      v31 = v21;
      v32 = 1;
      v132 = 1;
      if ( v25 >= v30 )
        v31 = v25 - v30;
      if ( v29 > v31 )
      {
        v33 = a5;
        v34 = (_BYTE *)(a5 + v28);
        do
        {
          if ( v32 > 2 || v25 - v29 > v23 )
            break;
          v35 = (_BYTE *)(v33 + (v26 & v29));
          if ( *v34 == *v35 && *(_BYTE *)(v33 + v28 + 1) == *(_BYTE *)(v33 + (v26 & v29) + 1) )
          {
            v36 = &v34[v27];
            v37 = 0;
            v38 = (unsigned __int64)&v34[v27 - 4];
            v39 = (_DWORD *)(a5 + v28);
            if ( (unsigned __int64)v34 <= v38 )
            {
              do
              {
                if ( *v39 != *(_DWORD *)((char *)v39 + v35 - v34) )
                  break;
                ++v39;
                v37 += 4LL;
              }
              while ( (unsigned __int64)v39 <= v38 );
              v32 = v132;
            }
            for ( ; v39 < (_DWORD *)v36; ++v37 )
            {
              if ( v35[v37] != *(_BYTE *)v39 )
                break;
              v39 = (_DWORD *)((char *)v39 + 1);
            }
            v23 = v134;
            v26 = a6;
            if ( v37 > v32 )
            {
              v32 = v37;
              v132 = v37;
              *((_DWORD *)v24 + 1) = 32 * v37;
              *(_DWORD *)v24 = v25 - v29;
              v24 += 8;
            }
            v33 = a5;
          }
          --v29;
        }
        while ( v29 > v31 );
        v13 = a10;
      }
      if ( v32 < v27 )
      {
        v40 = 128;
        if ( v27 < 0x80 )
          v40 = v27;
        v147 = v40;
        v41 = (unsigned int)HashBytesH10(a5 + v28);
        v45 = *(unsigned int *)(v13 + 4 * v41 + 48);
        v46 = 2 * (v25 & *(_QWORD *)(v13 + 40));
        v145 = 0;
        v47 = v46 + 1;
        v143 = 0;
        v48 = 0;
        v49 = 0;
        if ( v27 >= 0x80 )
          *(_DWORD *)(v13 + 4 * v41 + 48) = v25;
        v50 = 64;
        v51 = v25 - v45;
        if ( v25 != v45 )
        {
          do
          {
            v52 = a6 & v45;
            if ( v51 > v43 || !v50 )
              break;
            v53 = v49;
            if ( v48 < v49 )
              v53 = v48;
            v54 = 0;
            v55 = (char *)(v52 + v44 + v53);
            v56 = v42 + v53;
            v57 = &v55[v130 - v53];
            if ( v55 <= v57 - 4 )
            {
              v58 = v56 - (_QWORD)v55;
              do
              {
                if ( *(_DWORD *)v55 != *(_DWORD *)&v55[v58] )
                  break;
                v55 += 4;
                v54 += 4;
              }
              while ( v55 <= v57 - 4 );
            }
            for ( ; v55 < v57; ++v54 )
            {
              if ( *(_BYTE *)(v54 + v56) != *v55 )
                break;
              ++v55;
            }
            v49 = v54 + v53;
            if ( v24 && v49 > v132 )
            {
              *(_DWORD *)v24 = v51;
              *((_DWORD *)v24 + 1) = 32 * v49;
              v24 += 8;
              v132 = v54 + v53;
            }
            if ( v49 >= v147 )
            {
              v27 = v130;
              if ( v130 >= 0x80 )
              {
                *(_DWORD *)(a10 + 4 * v46 + 524344) = *(_DWORD *)(a10 + 8 * (v45 & *(_QWORD *)(a10 + 40)) + 524344);
                *(_DWORD *)(a10 + 4 * v47 + 524344) = *(_DWORD *)(a10 + 8 * (v45 & *(_QWORD *)(a10 + 40)) + 524348);
              }
              goto LABEL_63;
            }
            v44 = a5;
            v13 = a10;
            v42 = a5 + v139;
            if ( *(_BYTE *)(a5 + v139 + v49) <= *(_BYTE *)(a5 + v49 + v52) )
            {
              v143 = v49;
              if ( v130 >= 0x80 )
                *(_DWORD *)(a10 + 4 * v47 + 524344) = v45;
              v48 = v145;
              v47 = 2 * (v45 & *(_QWORD *)(a10 + 40));
              v60 = *(_DWORD *)(a10 + 8 * (v45 & *(_QWORD *)(a10 + 40)) + 524344);
            }
            else
            {
              v48 = v49;
              v145 = v49;
              if ( v130 >= 0x80 )
                *(_DWORD *)(a10 + 4 * v46 + 524344) = v45;
              v49 = v143;
              v59 = v45 & *(_QWORD *)(a10 + 40);
              v46 = 2 * v59 + 1;
              v60 = *(_DWORD *)(a10 + 8 * v59 + 524348);
            }
            --v50;
            v43 = v134;
            v45 = v60;
            v51 = v136 - v60;
          }
          while ( v136 != v60 );
        }
        v27 = v130;
        if ( v130 >= 0x80 )
        {
          *(_DWORD *)(v13 + 4 * v46 + 524344) = *(_DWORD *)(v13 + 524336);
          *(_DWORD *)(v13 + 4 * v47 + 524344) = *(_DWORD *)(v13 + 524336);
        }
LABEL_63:
        v32 = v132;
        v25 = v136;
        LODWORD(v28) = v139;
      }
      v61 = v162;
      v62 = 2;
      do
      {
        *v61 = 0xFFFFFFF0FFFFFFFLL;
        v61[1] = 0xFFFFFFF0FFFFFFFLL;
        v61[2] = 0xFFFFFFF0FFFFFFFLL;
        v61 += 8;
        *(v61 - 5) = 0xFFFFFFF0FFFFFFFLL;
        *(v61 - 4) = 0xFFFFFFF0FFFFFFFLL;
        *(v61 - 3) = 0xFFFFFFF0FFFFFFFLL;
        *(v61 - 2) = 0xFFFFFFF0FFFFFFFLL;
        *(v61 - 1) = 0xFFFFFFF0FFFFFFFLL;
        --v62;
      }
      while ( v62 );
      v63 = a5;
      v64 = v32 + 1;
      *v61 = 0xFFFFFFF0FFFFFFFLL;
      v61[1] = 0xFFFFFFF0FFFFFFFLL;
      v61[2] = 0xFFFFFFF0FFFFFFFLL;
      if ( v32 + 1 < 4 )
        v64 = 4;
      if ( (unsigned int)BrotliFindAllStaticDictionaryMatches(a2, (int)a5 + (int)v28, v64, v27, (__int64)v162) )
      {
        if ( v27 > 0x25 )
          v27 = 37;
        for ( ; v64 <= v27; ++v64 )
        {
          v65 = v162[v64];
          if ( v65 < 0xFFFFFFF )
          {
            v66 = v65 & 0x1F;
            *(_DWORD *)v24 = v134 + (v65 >> 5) + 1;
            v67 = v66 | (32 * v64);
            if ( v64 == v66 )
              v67 = 32 * v64;
            *((_DWORD *)v24 + 1) = v67;
            v24 += 8;
          }
        }
      }
      v68 = (v24 - (char *)v163) >> 3;
      if ( v68 && (unsigned __int64)(unsigned int)v162[2 * v68 + 39] >> 5 > v154 )
      {
        v69 = *(_QWORD *)&v162[2 * v68 + 38];
        v68 = 1;
        v163[0] = v69;
      }
      v12 = a3;
      v70 = a6;
      updated = UpdateNodes(a3, a4, v142, a5, a6, a7, a8, a9, v68, (__int64)v163, (__int64)v161, (__int64)v159, a11);
      if ( updated < 0x4000 )
        updated = 0;
      v144 = updated;
      if ( v68 == 1 )
      {
        v72 = (unsigned __int64)HIDWORD(v163[0]) >> 5;
        if ( v72 > v154 )
        {
          if ( v72 > updated )
            updated = (unsigned __int64)HIDWORD(v163[0]) >> 5;
          v144 = updated;
        }
      }
      if ( updated <= 1 )
      {
        v126 = v142;
      }
      else
      {
        v73 = v155;
        v74 = v25 + 1;
        v75 = a10;
        v76 = v25 + updated;
        v133 = v25 + 1;
        if ( v76 < v155 )
          v73 = v76;
        v146 = v73;
        v77 = v73 - 63;
        if ( v25 + 64 > v73 )
          v77 = v25 + 1;
        v135 = v77;
        if ( v25 + 513 <= v77 && v74 < v77 )
        {
          do
          {
            v148 = v63 + (v70 & v74);
            v78 = *(_QWORD *)(a10 + 40) - 15LL;
            v152 = v78;
            v79 = HashBytesH10(v148);
            v83 = 2 * (v80 & v82);
            v137 = 0;
            v140 = 0;
            v84 = 0;
            v131 = v83;
            v85 = *(unsigned int *)(a10 + 4LL * v79 + 48);
            v86 = 0;
            *(_DWORD *)(a10 + 4LL * v79 + 48) = v80;
            v87 = v83 + 1;
            v88 = 64;
            v89 = v80 - v85;
            if ( v80 != v85 )
            {
              while ( 1 )
              {
                v90 = a6 & v85;
                if ( v89 > v78 || !v88 )
                  break;
                v91 = v86;
                if ( v84 < v86 )
                  v91 = v84;
                v92 = v91 + v81;
                v93 = (_DWORD *)(v90 + v91 + a5);
                v94 = 0;
                v95 = v90 + a5 + 128;
                v96 = v90 + a5 + 124;
                if ( (unsigned __int64)v93 <= v96 )
                {
                  v97 = v92 - (_QWORD)v93;
                  do
                  {
                    if ( *v93 != *(_DWORD *)((char *)v93 + v97) )
                      break;
                    ++v93;
                    v94 += 4;
                  }
                  while ( (unsigned __int64)v93 <= v96 );
                }
                for ( ; (unsigned __int64)v93 < v95; ++v94 )
                {
                  if ( *(_BYTE *)(v94 + v92) != *(_BYTE *)v93 )
                    break;
                  v93 = (_DWORD *)((char *)v93 + 1);
                }
                v98 = v94 + v91;
                if ( v94 + v91 >= 0x80 )
                {
                  v80 = v133;
                  *(_DWORD *)(a10 + 4 * v131 + 524344) = *(_DWORD *)(a10 + 8 * (v85 & *(_QWORD *)(a10 + 40)) + 524344);
                  v101 = *(_DWORD *)(a10 + 8 * (v85 & *(_QWORD *)(a10 + 40)) + 524348);
                  goto LABEL_117;
                }
                v81 = v148;
                if ( *(_BYTE *)(v148 + v98) <= *(_BYTE *)(v98 + a5 + v90) )
                {
                  v83 = v131;
                  v86 = v98;
                  v84 = v137;
                  *(_DWORD *)(a10 + 4 * v87 + 524344) = v85;
                  v140 = v98;
                  v87 = 2 * (v85 & *(_QWORD *)(a10 + 40));
                  v100 = *(_DWORD *)(a10 + 8 * (v85 & *(_QWORD *)(a10 + 40)) + 524344);
                }
                else
                {
                  v84 = v94 + v91;
                  v86 = v140;
                  v137 = v94 + v91;
                  *(_DWORD *)(a10 + 4 * v131 + 524344) = v85;
                  v99 = v85 & *(_QWORD *)(a10 + 40);
                  v83 = 2 * v99 + 1;
                  v100 = *(_DWORD *)(a10 + 8 * v99 + 524348);
                  v131 = v83;
                }
                v80 = v133;
                --v88;
                v78 = v152;
                v85 = v100;
                v89 = v133 - v100;
                if ( v133 == v100 )
                  goto LABEL_116;
              }
              v83 = v131;
            }
LABEL_116:
            *(_DWORD *)(a10 + 4 * v83 + 524344) = *(_DWORD *)(a10 + 524336);
            v101 = *(_DWORD *)(a10 + 524336);
LABEL_117:
            v77 = v135;
            v74 = v80 + 8;
            v70 = a6;
            *(_DWORD *)(a10 + 4 * v87 + 524344) = v101;
            v63 = a5;
            v133 = v74;
          }
          while ( v74 < v135 );
          v73 = v146;
        }
        if ( v77 < v73 )
        {
          while ( 1 )
          {
            v102 = a6;
            v103 = *(_QWORD *)(v75 + 40) - 15LL;
            v153 = v63 + (a6 & v77);
            v149 = v103;
            v104 = HashBytesH10(v153);
            v107 = 0;
            v138 = 0;
            v108 = 0;
            v141 = 0;
            v109 = 64;
            v110 = *(unsigned int *)(v75 + 4LL * v104 + 48);
            v111 = 2 * (v77 & v106);
            v112 = a10;
            v113 = v111 + 1;
            *(_DWORD *)(a10 + 4LL * v104 + 48) = v77;
            v114 = v77 - v110;
            if ( v114 )
            {
              do
              {
                v115 = v102 & v110;
                if ( v114 > v103 || !v109 )
                  break;
                v116 = v108;
                if ( v107 < v108 )
                  v116 = v107;
                v117 = 0;
                v118 = v105 + v116;
                v119 = (_DWORD *)(a5 + v116 + v115);
                v120 = a5 + v115 + 128;
                v121 = a5 + v115 + 124;
                if ( (unsigned __int64)v119 <= v121 )
                {
                  v122 = v118 - (_QWORD)v119;
                  do
                  {
                    if ( *v119 != *(_DWORD *)((char *)v119 + v122) )
                      break;
                    ++v119;
                    v117 += 4;
                  }
                  while ( (unsigned __int64)v119 <= v121 );
                }
                for ( ; (unsigned __int64)v119 < v120; ++v117 )
                {
                  if ( *(_BYTE *)(v117 + v118) != *(_BYTE *)v119 )
                    break;
                  v119 = (_DWORD *)((char *)v119 + 1);
                }
                v107 = v117 + v116;
                if ( v117 + v116 >= 0x80 )
                {
                  *(_DWORD *)(a10 + 4 * v111 + 524344) = *(_DWORD *)(a10 + 8 * (*(_QWORD *)(a10 + 40) & v110) + 524344);
                  v75 = a10;
                  v125 = *(_DWORD *)(a10 + 8 * (*(_QWORD *)(a10 + 40) & v110) + 524348);
                  goto LABEL_140;
                }
                v105 = v153;
                v112 = a10;
                if ( *(_BYTE *)(v153 + v107) <= *(_BYTE *)(v107 + v115 + a5) )
                {
                  *(_DWORD *)(a10 + 4 * v113 + 524344) = v110;
                  v108 = v107;
                  v141 = v107;
                  v107 = v138;
                  v113 = 2 * (*(_QWORD *)(a10 + 40) & v110);
                  v124 = *(_DWORD *)(a10 + 8 * (*(_QWORD *)(a10 + 40) & v110) + 524344);
                }
                else
                {
                  v108 = v141;
                  *(_DWORD *)(a10 + 4 * v111 + 524344) = v110;
                  v123 = *(_QWORD *)(a10 + 40) & v110;
                  v124 = *(_DWORD *)(a10 + 8 * v123 + 524348);
                  v111 = 2 * v123 + 1;
                  v138 = v107;
                }
                --v109;
                v103 = v149;
                v102 = a6;
                v110 = v124;
                v114 = v135 - v124;
              }
              while ( v135 != v124 );
            }
            *(_DWORD *)(v112 + 4 * v111 + 524344) = *(_DWORD *)(v112 + 524336);
            v75 = a10;
            v125 = *(_DWORD *)(a10 + 524336);
LABEL_140:
            v77 = v135 + 1;
            *(_DWORD *)(v75 + 4 * v113 + 524344) = v125;
            v135 = v77;
            if ( v77 >= v146 )
              break;
            v63 = a5;
          }
        }
        v126 = v142;
        v127 = v144 - 1;
        if ( v144 == 1 )
        {
          v12 = a3;
        }
        else
        {
          v128 = v156 + v142 - 1;
          do
          {
            ++v126;
            if ( ++v128 >= a3 )
              break;
            EvaluateNode(a4, v126, a8, a9, (__int64)v161, (__int64)v159, a11);
            --v127;
          }
          while ( v127 );
          v12 = a3;
        }
      }
      v18 = v126 + 1;
      v13 = a10;
      v11 = a4;
      v21 = 0;
      v142 = v18;
      v22 = 16;
    }
    while ( v18 + v156 - 1 < v12 );
  }
  CleanupZopfliCostModel(a1, v161);
  return ComputeShortestPathFromNodes(v12, a11);
}

```

## disassembly

```asm
0x180276690  push    rbx
0x180276692  push    rbp
0x180276693  push    rsi
0x180276694  push    rdi
0x180276695  push    r14
0x180276697  mov     eax, 1A40h
0x18027669c  call    _alloca_probe
0x1802766a1  sub     rsp, rax
0x1802766a4  mov     rax, cs:__security_cookie
0x1802766ab  xor     rax, rsp
0x1802766ae  mov     [rsp+1A68h+var_58], rax
0x1802766b6  mov     rax, [rsp+1A68h+arg_40]
0x1802766be  mov     r14, r9
0x1802766c1  mov     rbx, [rsp+1A68h+arg_20]
0x1802766c9  mov     rdi, r8
0x1802766cc  mov     rsi, [rsp+1A68h+arg_48]
0x1802766d4  mov     [rsp+1A68h+var_1968], rax
0x1802766dc  mov     eax, 145h
0x1802766e1  mov     [rsp+1A68h+var_1998], r9
0x1802766e9  mov     r9, rcx
0x1802766ec  mov     [rsp+1A68h+var_1950], rcx
0x1802766f4  mov     rcx, [rsp+1A68h+arg_30]
0x1802766fc  mov     [rsp+1A68h+var_19A0], r8
0x180276704  mov     r8d, 96h
0x18027670a  mov     [rsp+1A68h+var_1958], rdx
0x180276712  mov     rdx, [rsp+1A68h+arg_50]
0x18027671a  cmp     dword ptr [rcx+4], 0Ah
0x18027671e  mov     [rsp+1A68h+var_19F0], rbx
0x180276723  cmovle  eax, r8d
0x180276727  mov     [rsp+1A68h+var_1978], rcx
0x18027672f  mov     [rsp+1A68h+var_1980], rax
0x180276737  mov     [rsp+1A68h+var_19F8], rsi
0x18027673c  mov     [rsp+1A68h+var_1990], rdx
0x180276744  call    StoreLookaheadH10
0x180276749  cmp     rdi, rax
0x18027674c  jb      short loc_180276765
0x18027674e  mov     rcx, r14
0x180276751  sub     rcx, rax
0x180276754  lea     rax, [rdi+1]
0x180276758  add     rax, rcx
0x18027675b  mov     [rsp+1A68h+var_1970], rax
0x180276763  jmp     short loc_18027676D
0x180276765  mov     [rsp+1A68h+var_1970], r14
0x18027676d  xor     eax, eax
0x18027676f  mov     r8, rdi
0x180276772  mov     [rdx], eax
0x180276774  mov     rcx, r9
0x180276777  mov     [rdx+0Ch], eax
0x18027677a  lea     rdx, [rsp+1A68h+var_1838]
0x180276782  call    InitZopfliCostModel
0x180276787  mov     r9, [rsp+1A68h+arg_28]
0x18027678f  lea     rcx, [rsp+1A68h+var_1838]
0x180276797  mov     r8, rbx
0x18027679a  mov     rdx, r14
0x18027679d  call    ZopfliCostModelSetFromLiteralCosts
0x1802767a2  xor     edx, edx
0x1802767a4  mov     [rsp+1A68h+var_1848], rdx
0x1802767ac  mov     ebp, edx
0x1802767ae  mov     [rsp+1A68h+var_19C0], rdx
0x1802767b6  call    HashTypeLengthH10
0x1802767bb  mov     [rsp+1A68h+var_1960], rax
0x1802767c3  dec     rax
0x1802767c6  cmp     rax, rdi
0x1802767c9  jnb     loc_18027743E
0x1802767cf  mov     [rsp+1A68h+var_30], r12
0x1802767d7  lea     r11d, [rdx+10h]
0x1802767db  mov     [rsp+1A68h+var_38], r13
0x1802767e3  mov     [rsp+1A68h+var_40], r15
0x1802767eb  nop     dword ptr [rax+rax+00h]
0x1802767f0  mov     r10, [rsp+1A68h+arg_38]
0x1802767f8  lea     r15, [rsp+1A68h+var_458]
0x180276800  mov     rax, [rsp+1A68h+var_1978]
0x180276808  add     r14, rbp
0x18027680b  mov     r9, [rsp+1A68h+arg_28]
0x180276813  cmp     r14, r10
0x180276816  mov     r12, rdi
0x180276819  mov     [rsp+1A68h+var_19D0], r14
0x180276821  cmovb   r10, r14
0x180276825  mov     r13, r14
0x180276828  sub     r12, rbp
0x18027682b  mov     [rsp+1A68h+var_19D8], r10
0x180276833  and     r13, r9
0x180276836  mov     [rsp+1A68h+var_19E8], r12
0x18027683e  cmp     dword ptr [rax+4], 0Bh
0x180276842  lea     rbx, [r14-1]
0x180276846  mov     ecx, 40h ; '@'
0x18027684b  mov     [rsp+1A68h+var_19C8], r13
0x180276853  cmovnz  rcx, r11
0x180276857  mov     rax, r14
0x18027685a  sub     rax, rcx
0x18027685d  mov     rbp, rdx
0x180276860  cmp     r14, rcx
0x180276863  mov     r8d, 1
0x180276869  mov     [rsp+1A68h+var_19E0], r8
0x180276871  cmovnb  rbp, rax
0x180276875  cmp     rbx, rbp
0x180276878  jbe     loc_180276969
0x18027687e  mov     rdx, [rsp+1A68h+var_19F0]
0x180276883  lea     rsi, [rdx+r13]
0x180276887  nop     word ptr [rax+rax+00000000h]
0x180276890  cmp     r8, 2
0x180276894  ja      loc_180276964
0x18027689a  mov     rdi, r14
0x18027689d  sub     rdi, rbx
0x1802768a0  cmp     rdi, r10
0x1802768a3  ja      loc_180276964
0x1802768a9  mov     rcx, rbx
0x1802768ac  and     rcx, r9
0x1802768af  movzx   eax, byte ptr [rdx+rcx]
0x1802768b3  lea     r11, [rdx+rcx]
0x1802768b7  cmp     [rsi], al
0x1802768b9  jnz     loc_180276958
0x1802768bf  movzx   eax, byte ptr [rdx+rcx+1]
0x1802768c4  cmp     [rdx+r13+1], al
0x1802768c9  jnz     loc_180276958
0x1802768cf  lea     r10, [rsi+r12]
0x1802768d3  xor     edx, edx
0x1802768d5  lea     r9, [r10-4]
0x1802768d9  mov     rcx, rsi
0x1802768dc  cmp     rsi, r9
0x1802768df  ja      short loc_180276904
0x1802768e1  mov     r8, r11
0x1802768e4  sub     r8, rsi
0x1802768e7  mov     eax, [r8+rcx]
0x1802768eb  cmp     [rcx], eax
0x1802768ed  jnz     short loc_1802768FC
0x1802768ef  add     rcx, 4
0x1802768f3  add     rdx, 4
0x1802768f7  cmp     rcx, r9
0x1802768fa  jbe     short loc_1802768E7
0x1802768fc  mov     r8, [rsp+1A68h+var_19E0]
0x180276904  cmp     rcx, r10
0x180276907  jnb     short loc_180276924
0x180276909  nop     dword ptr [rax+00000000h]
0x180276910  movzx   eax, byte ptr [rcx]
0x180276913  cmp     [rdx+r11], al
0x180276917  jnz     short loc_180276924
0x180276919  inc     rcx
0x18027691c  inc     rdx
0x18027691f  cmp     rcx, r10
0x180276922  jb      short loc_180276910
0x180276924  mov     r10, [rsp+1A68h+var_19D8]
0x18027692c  mov     r9, [rsp+1A68h+arg_28]
0x180276934  cmp     rdx, r8
0x180276937  jbe     short loc_180276953
0x180276939  mov     r8, rdx
0x18027693c  mov     [rsp+1A68h+var_19E0], rdx
0x180276944  shl     rdx, 5
0x180276948  mov     [r15+4], edx
0x18027694c  mov     [r15], edi
0x18027694f  add     r15, 8
0x180276953  mov     rdx, [rsp+1A68h+var_19F0]
0x180276958  dec     rbx
0x18027695b  cmp     rbx, rbp
0x18027695e  ja      loc_180276890
0x180276964  mov     rsi, [rsp+1A68h+var_19F8]
0x180276969  cmp     r8, r12
0x18027696c  jnb     loc_180276BB1
0x180276972  mov     r11, [rsp+1A68h+var_19F0]
0x180276977  mov     eax, 80h
0x18027697c  cmp     r12, rax
0x18027697f  cmovb   rax, r12
0x180276983  lea     r9, [r11+r13]
0x180276987  mov     [rsp+1A68h+var_19A8], rax
0x18027698f  mov     rcx, r9
0x180276992  call    HashBytesH10
0x180276997  mov     ecx, eax
0x180276999  mov     rax, [rsi+28h]
0x18027699d  and     rax, r14
0x1802769a0  mov     ebx, [rsi+rcx*4+30h]
0x1802769a4  lea     r13, [rax+rax]
0x1802769a8  xor     eax, eax
0x1802769aa  mov     [rsp+1A68h+var_19B0], rax
0x1802769b2  lea     rbp, [r13+1]
0x1802769b6  mov     [rsp+1A68h+var_19B8], rax
0x1802769be  mov     edx, eax
0x1802769c0  mov     r8d, eax
0x1802769c3  cmp     r12, 80h
0x1802769ca  jb      short loc_1802769D1
0x1802769cc  mov     [rsi+rcx*4+30h], r14d
0x1802769d1  mov     rdi, r14
0x1802769d4  mov     r12d, 40h ; '@'
0x1802769da  sub     rdi, rbx
0x1802769dd  jz      loc_180276B6D
0x1802769e3  nop     dword ptr [rax+00h]
0x1802769e7  nop     word ptr [rax+rax+00000000h]
0x1802769f0  mov     r14, rbx
0x1802769f3  and     r14, [rsp+1A68h+arg_28]
0x1802769fb  cmp     rdi, r10
0x1802769fe  ja      loc_180276B6D
0x180276a04  test    r12, r12
0x180276a07  jz      loc_180276B6D
0x180276a0d  cmp     rdx, r8
0x180276a10  mov     rsi, r8
0x180276a13  cmovb   rsi, rdx
0x180276a17  mov     rdx, rax
0x180276a1a  lea     rcx, [r11+rsi]
0x180276a1e  add     rcx, r14
0x180276a21  lea     r11, [r9+rsi]
0x180276a25  mov     r10, rcx
0x180276a28  sub     r10, rsi
0x180276a2b  add     r10, [rsp+1A68h+var_19E8]
0x180276a33  lea     r9, [r10-4]
0x180276a37  cmp     rcx, r9
0x180276a3a  ja      short loc_180276A57
0x180276a3c  mov     r8, r11
0x180276a3f  sub     r8, rcx
0x180276a42  mov     eax, [r8+rcx]
0x180276a46  cmp     [rcx], eax
0x180276a48  jnz     short loc_180276A57
0x180276a4a  add     rcx, 4
0x180276a4e  add     rdx, 4
0x180276a52  cmp     rcx, r9
0x180276a55  jbe     short loc_180276A42
0x180276a57  cmp     rcx, r10
0x180276a5a  jnb     short loc_180276A74
0x180276a5c  nop     dword ptr [rax+00h]
0x180276a60  movzx   eax, byte ptr [rcx]
0x180276a63  cmp     [rdx+r11], al
0x180276a67  jnz     short loc_180276A74
0x180276a69  inc     rcx
0x180276a6c  inc     rdx
0x180276a6f  cmp     rcx, r10
0x180276a72  jb      short loc_180276A60
0x180276a74  lea     r8, [rdx+rsi]
0x180276a78  test    r15, r15
0x180276a7b  jz      short loc_180276AA1
0x180276a7d  cmp     r8, [rsp+1A68h+var_19E0]
0x180276a85  jbe     short loc_180276AA1
0x180276a87  mov     rax, r8
0x180276a8a  mov     [r15], edi
0x180276a8d  shl     rax, 5
0x180276a91  mov     [r15+4], eax
0x180276a95  add     r15, 8
0x180276a99  mov     [rsp+1A68h+var_19E0], r8
0x180276aa1  cmp     r8, [rsp+1A68h+var_19A8]
0x180276aa9  jnb     loc_180276FB1
0x180276aaf  mov     r11, [rsp+1A68h+var_19F0]
0x180276ab4  mov     r9, [rsp+1A68h+var_19C8]
0x180276abc  mov     rsi, [rsp+1A68h+var_19F8]
0x180276ac1  add     r9, r11
0x180276ac4  lea     rax, [r11+r8]
0x180276ac8  movzx   ecx, byte ptr [rax+r14]
0x180276acd  cmp     [r9+r8], cl
0x180276ad1  jbe     short loc_180276B14
0x180276ad3  cmp     [rsp+1A68h+var_19E8], 80h
0x180276adf  mov     rdx, r8
0x180276ae2  mov     [rsp+1A68h+var_19B0], rdx
0x180276aea  jb      short loc_180276AF4
0x180276aec  mov     [rsi+r13*4+80038h], ebx
0x180276af4  mov     rax, [rsi+28h]
0x180276af8  mov     r8, [rsp+1A68h+var_19B8]
0x180276b00  and     rax, rbx
0x180276b03  lea     r13, ds:1[rax*2]
0x180276b0b  mov     eax, [rsi+rax*8+8003Ch]
0x180276b12  jmp     short loc_180276B4A
0x180276b14  cmp     [rsp+1A68h+var_19E8], 80h
0x180276b20  mov     [rsp+1A68h+var_19B8], r8
0x180276b28  jb      short loc_180276B31
0x180276b2a  mov     [rsi+rbp*4+80038h], ebx
0x180276b31  mov     rbp, [rsi+28h]
0x180276b35  mov     rdx, [rsp+1A68h+var_19B0]
0x180276b3d  and     rbp, rbx
0x180276b40  add     rbp, rbp
0x180276b43  mov     eax, [rsi+rbp*4+80038h]
0x180276b4a  mov     rdi, [rsp+1A68h+var_19D0]
0x180276b52  dec     r12
0x180276b55  mov     r10, [rsp+1A68h+var_19D8]
0x180276b5d  mov     ebx, eax
0x180276b5f  mov     eax, 0
0x180276b64  sub     rdi, rbx
0x180276b67  jnz     loc_1802769F0
0x180276b6d  mov     r12, [rsp+1A68h+var_19E8]
0x180276b75  cmp     r12, 80h
0x180276b7c  jb      short loc_180276B99
0x180276b7e  mov     eax, [rsi+80030h]
0x180276b84  mov     [rsi+r13*4+80038h], eax
0x180276b8c  mov     eax, [rsi+80030h]
0x180276b92  mov     [rsi+rbp*4+80038h], eax
0x180276b99  mov     r8, [rsp+1A68h+var_19E0]
0x180276ba1  mov     r14, [rsp+1A68h+var_19D0]
0x180276ba9  mov     r13, [rsp+1A68h+var_19C8]
0x180276bb1  lea     rax, [rsp+1A68h+var_4F8]
0x180276bb9  mov     ecx, 2
0x180276bbe  mov     rdx, 0FFFFFFF0FFFFFFFh
0x180276bc8  nop     dword ptr [rax+rax+00000000h]
0x180276bd0  mov     [rax], rdx
0x180276bd3  mov     [rax+8], rdx
0x180276bd7  mov     [rax+10h], rdx
0x180276bdb  lea     rax, [rax+40h]
0x180276bdf  mov     [rax-28h], rdx
0x180276be3  mov     [rax-20h], rdx
0x180276be7  mov     [rax-18h], rdx
0x180276beb  mov     [rax-10h], rdx
0x180276bef  mov     [rax-8], rdx
0x180276bf3  sub     rcx, 1
0x180276bf7  jnz     short loc_180276BD0
0x180276bf9  mov     rbp, [rsp+1A68h+var_19F0]
0x180276bfe  lea     rbx, [r8+1]
0x180276c02  mov     rcx, [rsp+1A68h+var_1958]
  ... truncated ...
```
