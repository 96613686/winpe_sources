# mkl_aa_fw_reserve_threads

- ea: `0x18012bf20`
- end: `0x18012d1a0`
- name: `mkl_aa_fw_reserve_threads`
- size: `4736`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x180060de0`

## callees

- `0x180038b70`
- `0x180056020`
- `0x18012b460`
- `0x18012bf20`
- `0x18012d430`
- `0x180453270`
- `0x1804537f0`
- `0x180453810`
- `0x180453860`
- `0x180453d40`
- `0x180453e40`
- `0x1832ce3b0`
- `0x1832ceb40`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18012bfc4`
- `KERNEL32!GetCurrentProcessId` at `0x18012bfc4`

## pseudocode

```c
__int64 __fastcall mkl_aa_fw_reserve_threads(int a1, signed int a2)
{
  __int128 v2; // xmm6
  __int128 v3; // xmm7
  void *v4; // rsp
  int v6; // esi
  signed int v7; // r13d
  unsigned int v8; // ebx
  int phy_device_count; // edi
  unsigned __int64 v10; // rcx
  int v11; // r15d
  __int64 v12; // rdx
  __int64 v13; // rbp
  __int64 v14; // r14
  DWORD CurrentProcessId; // r8d
  unsigned int v17; // ebx
  __int64 v18; // rdi
  int v19; // r12d
  __int64 v20; // rdx
  int v21; // r8d
  int v22; // edi
  signed int v23; // r12d
  double v24; // xmm0_8
  int v25; // eax
  int v26; // r9d
  unsigned __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rdi
  unsigned __int64 v30; // rdx
  unsigned __int64 v31; // rcx
  __int64 v32; // r11
  __int64 v33; // rax
  int v34; // r12d
  __int64 v35; // rsi
  __int64 v36; // rdi
  int v37; // ecx
  __int64 v38; // r9
  __int64 v39; // r13
  int v40; // esi
  __int64 v41; // r14
  int v42; // r15d
  int v43; // eax
  unsigned __int64 v44; // rbx
  int v45; // ebp
  _DWORD *v46; // rax
  int v47; // esi
  int v48; // ebp
  __int64 v49; // rdx
  int v50; // r9d
  int v51; // ecx
  int v52; // esi
  int v53; // r15d
  int v54; // r10d
  int v55; // r15d
  signed int v56; // r12d
  int v57; // edi
  unsigned __int64 v58; // rcx
  int v59; // r11d
  int v60; // r14d
  int v61; // r11d
  int v62; // r14d
  int v63; // edx
  int v64; // ecx
  int v65; // edx
  int *v66; // rsi
  _DWORD *v67; // rdi
  unsigned __int64 i; // rcx
  __int64 v69; // rcx
  __int64 v70; // r11
  __int64 v71; // rdi
  int v72; // r14d
  unsigned int v73; // edi
  unsigned __int64 v74; // rsi
  __int64 v75; // r11
  int v76; // ebp
  char *v77; // rdx
  __int64 v78; // r13
  bool v79; // cc
  int v80; // r13d
  int v81; // edi
  int v82; // esi
  __int64 v83; // rcx
  unsigned int v84; // edi
  int v85; // eax
  int v86; // esi
  unsigned __int64 v87; // rdx
  unsigned __int64 v88; // rcx
  __int64 v89; // rdi
  int v90; // r11d
  __int64 v91; // r15
  int v92; // r13d
  int v93; // esi
  int v94; // r12d
  int v95; // r10d
  __int64 v96; // rcx
  __int64 v97; // rcx
  __int64 v98; // r15
  int v99; // edx
  __int64 v100; // r11
  __int64 v101; // rsi
  __int64 v102; // r12
  int v103; // eax
  _DWORD *v104; // r15
  __int64 v105; // rsi
  __int64 v106; // rdi
  __int64 v107; // r12
  int v108; // r14d
  DWORD v109; // ebp
  __int64 v110; // r9
  unsigned int v111; // esi
  int v112; // r12d
  __int64 v113; // rdi
  __int64 v114; // rcx
  double workdivision; // xmm6_8
  __int64 v116; // rdi
  __int64 v117; // rsi
  unsigned int v118; // ebx
  __int64 v119; // r8
  int v120; // eax
  unsigned __int64 v121; // rcx
  unsigned __int64 v122; // rdx
  __m128i v123; // xmm11
  __m128i v124; // xmm14
  __m128i v125; // xmm10
  __m128i v126; // xmm13
  __m128i v127; // xmm9
  __m128i v128; // xmm15
  __m128i v129; // xmm3
  __m128i v130; // xmm12
  __m128i v131; // xmm4
  __m128i v132; // xmm5
  __m128i v133; // xmm6
  __m128i v134; // xmm7
  __m128i v135; // xmm8
  __m128i v136; // xmm1
  __m128i v137; // xmm2
  __m128i v138; // xmm0
  char v139; // r9
  __m128i v140; // xmm3
  char v141; // dl
  __m128i si128; // xmm5
  unsigned __int64 v143; // r15
  char v144; // cl
  __m128i v145; // xmm4
  char v146; // r13
  char v147; // r11
  char v148; // r10
  char v149; // al
  __m128i v150; // xmm6
  char v151; // r14
  char v152; // r12
  char v153; // r8
  char v154; // di
  char v155; // si
  char v156; // bp
  unsigned __int64 v157; // rbx
  __m128i v158; // xmm2
  __m128i v159; // xmm4
  __m128i v160; // xmm3
  __m128i v161; // xmm5
  __m128i v162; // xmm14
  __m128i v163; // xmm14
  unsigned __int64 j; // r15
  unsigned int v165; // ecx
  int v166; // r11d
  unsigned __int64 v167; // rdx
  unsigned __int64 v168; // rsi
  __int64 v169; // r11
  __int64 v170; // r12
  unsigned __int64 v171; // rdx
  unsigned __int64 v172; // r15
  _DWORD v173[929]; // [rsp+0h] [rbp-227ECh] BYREF
  int v174; // [rsp+E84h] [rbp-21968h]
  char *v175; // [rsp+E8Ch] [rbp-21960h]
  unsigned int v176; // [rsp+E94h] [rbp-21958h]
  __int64 v177; // [rsp+E9Ch] [rbp-21950h]
  __int64 v178; // [rsp+EA4h] [rbp-21948h]
  signed int v179; // [rsp+EACh] [rbp-21940h]
  int v180; // [rsp+EB4h] [rbp-21938h]
  int v181; // [rsp+EBCh] [rbp-21930h]
  __int64 v182; // [rsp+EC4h] [rbp-21928h]
  signed int v183; // [rsp+ECCh] [rbp-21920h]
  __m128i v184; // [rsp+ED4h] [rbp-21918h] BYREF
  __m128i v185; // [rsp+EE4h] [rbp-21908h] BYREF
  __m128i v186; // [rsp+EF4h] [rbp-218F8h] BYREF
  __int128 v187; // [rsp+F44h] [rbp-218A8h]
  __int128 v188; // [rsp+F94h] [rbp-21858h]
  unsigned int v189; // [rsp+FA4h] [rbp-21848h]
  int v190; // [rsp+FACh] [rbp-21840h] BYREF
  int v191; // [rsp+FB0h] [rbp-2183Ch] BYREF
  DWORD v192; // [rsp+FB4h] [rbp-21838h]
  unsigned __int64 v193; // [rsp+FBCh] [rbp-21830h]
  __int64 v194; // [rsp+FC4h] [rbp-21828h]
  __int64 v195; // [rsp+FCCh] [rbp-21820h]
  __int64 v196; // [rsp+FD4h] [rbp-21818h]
  unsigned __int64 v197; // [rsp+FDCh] [rbp-21810h]
  int v198; // [rsp+FE4h] [rbp-21808h]
  int v199; // [rsp+FECh] [rbp-21800h]
  int v200; // [rsp+FF4h] [rbp-217F8h]
  _DWORD v201[33830]; // [rsp+FFCh] [rbp-217F0h] BYREF
  _OWORD v202[27]; // [rsp+22094h] [rbp-758h] BYREF
  int v203[34]; // [rsp+22244h] [rbp-5A8h] BYREF
  char v204[20]; // [rsp+222CCh] [rbp-520h] BYREF
  int v205; // [rsp+222E0h] [rbp-50Ch]
  _DWORD v206[293]; // [rsp+22308h] [rbp-4E4h]
  int v207; // [rsp+2279Ch] [rbp-50h]
  unsigned int v208; // [rsp+227A0h] [rbp-4Ch]

  v4 = alloca(137544);
  v180 = a1;
  mkl_serv_dsecnd();
  v6 = 0;
  v7 = 0;
  v190 = 0;
  v8 = 0;
  phy_device_count = mkl_ueaa_get_phy_device_count();
  v10 = 0;
  v11 = 0;
  v12 = 0;
  LODWORD(v13) = phy_device_count - 1;
  v14 = 0;
  do
  {
    v206[2 * v10 + 1] = 0;
    v206[2 * v10++ + 2] = 0;
    v201[v12 + 2] = 0;
    v201[v12 + 1027] = 0;
    v12 += 2050;
  }
  while ( v10 < 0x10 );
  v206[33] = 0;
  v201[32802] = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( *(double *)&mkl_aa_fraction > 0.0 )
  {
    if ( (int)v13 <= 0 )
      return 0xFFFFFFFFLL;
    v188 = v2;
    v189 = 0;
    v17 = 0;
    v192 = CurrentProcessId;
    v174 = phy_device_count;
    v18 = 1;
    v183 = 0;
    v179 = a2;
    v19 = 1;
    do
    {
      v201[v18 + 33829] = 0;
      mkl_ueaa_get_phy_device_mask((unsigned int)v19, &v191);
      if ( v191 )
      {
        if ( (unsigned int)mkl_ueaa_get_device_info(v204, ++v17) )
        {
          v2 = v188;
          v8 = -1;
          CurrentProcessId = v192;
          v7 = v183;
LABEL_165:
          v192 = CurrentProcessId;
          mkl_aa_fw_unlock_sharing_mask(v201, v20);
          CurrentProcessId = v192;
          goto LABEL_166;
        }
        v201[v18 + 33829] = v205 - 4;
        if ( mkl_aa_fw_get_workdivision(v17) != 0.0 )
        {
          v21 = v201[v18 + 33829];
          v203[v14] = v19;
          if ( v21 < 0 )
            v21 = 0;
          ++v14;
          v6 += v21;
          ++v11;
        }
      }
      ++v19;
      ++v18;
    }
    while ( v19 <= (int)v13 );
    v2 = v188;
    v8 = v189;
    CurrentProcessId = v192;
    v22 = v174;
    v7 = v183;
    v23 = v179;
    if ( !v6 )
    {
LABEL_15:
      v8 = -1;
      goto LABEL_166;
    }
    v24 = (double)v6 * *(double *)&mkl_aa_fraction;
    if ( (int)(((int)v24 + ((unsigned int)((int)v24 >> 1) >> 30)) & 0xFFFFFFFC) >= v179 )
    {
      v176 = ((int)v24 + ((unsigned int)((int)v24 >> 1) >> 30)) & 0xFFFFFFFC;
      v25 = mkl_aa_fw_lock_sharing_mask(v201, &v190);
      CurrentProcessId = v192;
      if ( v25 )
        goto LABEL_15;
      v26 = 1;
      v27 = 0;
      v28 = 0;
      if ( (int)(v174 + ((unsigned int)v13 >> 31) - 1) >> 1 )
      {
        do
        {
          ++v27;
          dword_1836FE2E8[v28] = 0;
          dword_1836FF2EC[v28] = 0;
          v28 += 2050;
        }
        while ( v27 < (int)(v22 + ((unsigned int)v13 >> 31) - 1) >> 1 );
        v26 = 2 * v27 + 1;
      }
      if ( (unsigned int)v13 > v26 - 1 )
        dword_1836FD2E4[1025 * v26] = 0;
      v29 = v22 - 1LL;
      if ( v29 < 4 )
      {
        v31 = 0;
      }
      else
      {
        v30 = 0;
        v31 = (int)(v29 & 0xFFFFFFFC);
        do
        {
          v202[v30 / 4 + 9] = 0;
          v202[v30 / 4 + 18] = 0;
          v30 += 4LL;
        }
        while ( v30 < v31 );
      }
      for ( ; v31 < v29; ++v31 )
      {
        *((_DWORD *)&v202[9] + v31) = 0;
        *((_DWORD *)&v202[18] + v31) = 0;
      }
      if ( v190 )
      {
        v201[1] = v13;
        v32 = 1;
        v201[0] = 1;
        v33 = 1025;
        v179 = v23;
        do
        {
          v34 = v201[v32 + 33829];
          v35 = 0;
          v173[v33] = v34;
          v36 = v33 * 4;
          if ( v34 > 0 )
          {
            do
            {
              v201[v33 - 1022 + v35++] = 0;
              *(int *)((char *)dword_1836FD2E8 + v36) = 0;
              v36 += 4;
            }
            while ( v35 < (int)v173[v33] );
          }
          ++v32;
          v33 += 1025;
        }
        while ( v32 <= (int)v13 );
        v23 = v179;
      }
      v37 = 0;
      v20 = 0;
      if ( v11 > 0 )
      {
        v38 = v11;
        v189 = v8;
        v176 = ((int)v24 + ((unsigned int)((int)v24 >> 1) >> 30)) & 0xFFFFFFFC;
        LODWORD(v175) = v11;
        v174 = v13;
        v183 = v7;
        v179 = v23;
        do
        {
          v39 = v203[v20];
          v40 = 0;
          v41 = 1025 * v39;
          v42 = v173[1025 * v39];
          if ( v42 > 0 )
          {
            v43 = 1;
            v44 = 0;
            if ( v42 / 2 )
            {
              v45 = *((_DWORD *)&v202[17] + v39 + 3);
              v46 = &v201[v41 + 3];
              v178 = v38;
              v177 = v20;
              do
              {
                v47 = v46[2 * v44 - 1025];
                v48 = (v47 == 0) + v45;
                v49 = v41 * 4 + 8 * v44;
                if ( CurrentProcessId == *(int *)((char *)dword_1836FD2E8 + v49) )
                {
                  if ( v47 )
                    v206[v39] = 1;
                  ++dword_1836FD2E4[1025 * v39];
                }
                v50 = v46[2 * v44 - 1024];
                v51 = v48 + v37;
                v45 = (v50 == 0) + v48;
                if ( CurrentProcessId == *(int *)((char *)&dword_1836FD2EC + v49) )
                {
                  if ( v50 )
                    v206[v39] = 1;
                  ++dword_1836FD2E4[1025 * v39];
                }
                v37 = v45 + v51;
                v40 = 2 * v44++ + 2;
              }
              while ( v44 < v42 / 2 );
              v38 = v178;
              v43 = 2 * v44 + 1;
              v20 = v177;
              *((_DWORD *)&v202[17] + v39 + 3) = v45;
            }
            if ( v42 > (unsigned int)(v43 - 1) )
            {
              v52 = v201[v41 - 1023 + v43];
              v53 = *((_DWORD *)&v202[17] + v39 + 3) + (v52 == 0);
              *((_DWORD *)&v202[17] + v39 + 3) = v53;
              if ( CurrentProcessId == dword_1836FD2E4[v43 + v41] )
              {
                if ( v52 )
                  v206[v39] = 1;
                ++dword_1836FD2E4[1025 * v39];
              }
              v37 += v53;
              v40 = v43;
            }
          }
          ++v20;
        }
        while ( v20 < (unsigned __int64)v38 );
        v8 = v189;
        v54 = v176;
        v55 = (int)v175;
        LODWORD(v13) = v174;
        v7 = v183;
        v56 = v179;
        if ( v37 )
        {
          v57 = 1;
          v58 = 0;
          if ( (int)v175 / 2 )
          {
            do
            {
              v59 = v203[2 * v58];
              v60 = *((_DWORD *)&v202[17] + v59 + 3);
              if ( v60 >= v54 )
                v60 = v54;
              if ( v60 >= v56 && v60 > 0 )
              {
                if ( v60 <= v7 )
                {
                  if ( v60 == v7 && v7 == dword_1836FD2E4[1025 * v59] && !v206[v59] )
                  {
                    v206[v40] = 0;
                    v40 = v59;
                  }
                }
                else
                {
                  v7 = v60;
                  v40 = v203[2 * v58];
                }
              }
              v61 = v203[2 * v58 + 1];
              v62 = *((_DWORD *)&v202[17] + v61 + 3);
              if ( v62 >= v54 )
                v62 = v54;
              if ( v62 >= v56 && v62 > 0 )
              {
                if ( v62 <= v7 )
                {
                  if ( v62 == v7 && v7 == dword_1836FD2E4[1025 * v61] && !v206[v61] )
                  {
                    v206[v40] = 0;
                    v40 = v61;
                  }
                }
                else
                {
                  v7 = v62;
                  v40 = v203[2 * v58 + 1];
                }
              }
              ++v58;
            }
            while ( v58 < v55 / 2 );
            v57 = 2 * v58 + 1;
          }
          if ( v55 > (unsigned int)(v57 - 1) )
          {
            v63 = *((_DWORD *)&v202[26] + v57 + 3);
            v64 = *((_DWORD *)&v202[17] + v63 + 3);
            if ( v64 >= v54 )
              v64 = v54;
            if ( v64 >= v56 && v64 > 0 )
            {
              if ( v64 <= v7 )
              {
                if ( v64 == v7 && v7 == dword_1836FD2E4[1025 * v63] && !v206[v63] )
                {
                  v206[v40] = 0;
                  v40 = v63;
                }
              }
              else
              {
                v7 = v64;
                v40 = *((_DWORD *)&v202[26] + v57 + 3);
              }
            }
          }
          if ( v7 )
            *((_DWORD *)&v202[8] + v40 + 3) = v7;
          if ( v7 >= v54 )
            goto LABEL_138;
          v65 = v180;
          if ( v55 < v180 )
            v65 = v55;
          v180 = v65;
          if ( v65 <= 1 )
            goto LABEL_138;
          if ( v55 > 24 && (v66 = v203, (char *)v203 - (char *)v202 > 4 * v38 || (char *)v202 - (char *)v203 > 4 * v38) )
          {
            v67 = v202;
            for ( i = (unsigned __int64)(4 * v38) >> 2; i; --i )
              *v67++ = *v66++;
          }
          else
          {
            if ( v38 < 4 )
            {
              v172 = 0;
            }
            else
            {
              v171 = 0;
              v172 = (int)(v55 & 0xFFFFFFFC);
              do
              {
                v202[v171 / 4] = _mm_load_si128((const __m128i *)&v203[v171]);
                v171 += 4LL;
              }
              while ( v171 < v172 );
            }
            for ( ; v172 < v38; ++v172 )
              *((_DWORD *)v202 + v172) = v203[v172];
          }
          v20 = v38 - 1;
          if ( v38 > 1 )
          {
            do
            {
              v69 = 0;
              do
              {
                v70 = *((int *)v202 + v69);
                v71 = *((int *)v202 + v69 + 1);
                if ( *((_DWORD *)&v202[17] + v70 + 3) < *((_DWORD *)&v202[17] + v71 + 3) )
                {
                  *((_DWORD *)v202 + v69) = v71;
                  *((_DWORD *)v202 + v69 + 1) = v70;
                }
                ++v69;
              }
              while ( v69 < v20 );
              --v20;
            }
            while ( v20 > 0 );
          }
          v72 = v180 - 1;
          if ( v180 - 1 >= 0 )
          {
            v73 = v180;
            v20 = 1;
            v74 = 0;
            v75 = 0;
            if ( v180 / 2 )
            {
              v174 = v13;
              v192 = CurrentProcessId;
              v183 = v7;
              v76 = v180;
              v77 = (char *)v202 + 4 * v72;
              do
              {
                ++v74;
                v78 = *(int *)&v77[v75 - 4];
                if ( v56 > *((_DWORD *)&v202[17] + *(int *)&v77[v75] + 3) )
                  --v76;
                v75 -= 8;
                v79 = v56 <= *((_DWORD *)&v202[17] + v78 + 3);
                v80 = 0;
                if ( !v79 )
                  v80 = -1;
                v76 += v80;
              }
              while ( v74 < v180 / 2 );
              v180 = v76;
              v20 = (unsigned int)(2 * v74 + 1);
              CurrentProcessId = v192;
              LODWORD(v13) = v174;
              v7 = v183;
            }
            if ( v73 > (int)v20 - 1 )
            {
              v20 = (int)v20;
              v81 = v180;
              if ( v56 > *((_DWORD *)&v202[17] + *((int *)v202 + v72 - (__int64)(int)v20 + 1) + 3) )
                v81 = v180 - 1;
              v180 = v81;
            }
          }
          v82 = 0;
          v83 = 0;
          if ( v180 > 0 )
          {
            while ( 1 )
            {
              v84 = v82 + 1;
              v20 = (unsigned int)(v54 >> 31);
              LODWORD(v20) = v54 % (v82 + 1);
              v85 = v54 / (v82 + 1);
              if ( v85 <= *((_DWORD *)&v202[17] + *((int *)v202 + v83) + 3) )
                break;
              ++v83;
              ++v82;
              if ( (int)v84 >= v180 )
                goto LABEL_124;
            }
            v165 = (v85 + ((unsigned int)(v85 >> 1) >> 30)) & 0xFFFFFFFC;
            v7 = v165 + v165 * v82;
            if ( v82 >= 0 )
            {
              v166 = 1;
              v167 = 0;
              v168 = (int)(v82 + (v84 >> 31) + 1) >> 1;
              if ( v168 )
              {
                do
                {
                  v169 = *((int *)v202 + 2 * v167);
                  v170 = *((int *)v202 + 2 * v167++ + 1);
                  *((_DWORD *)&v202[8] + v169 + 3) = v165;
                  *((_DWORD *)&v202[8] + v170 + 3) = v165;
                }
                while ( v167 < v168 );
                v166 = 2 * v167 + 1;
              }
              v20 = (unsigned int)(v166 - 1);
              if ( v84 > (unsigned int)v20 )
              {
                v20 = (int)v201[v166 + 33829];
                *((_DWORD *)&v202[8] + v20 + 3) = v165;
              }
            }
          }
LABEL_124:
          if ( v7 )
            goto LABEL_138;
          if ( v180 > 0 )
          {
            v86 = 1;
            v87 = 0;
            v88 = v180 / 2;
            if ( v180 / 2 )
            {
              do
              {
                v89 = *((int *)v202 + 2 * v87);
                v90 = v54 - v7;
                v91 = *((int *)v202 + 2 * v87++ + 1);
                if ( *((_DWORD *)&v202[17] + v89 + 3) < v54 - v7 )
                  v90 = *((_DWORD *)&v202[17] + v89 + 3);
                v92 = v90 + v7;
                v93 = v54 - v92;
                v94 = *((_DWORD *)&v202[17] + v91 + 3);
                *((_DWORD *)&v202[8] + v89 + 3) = v90;
                if ( v94 < v54 - v92 )
                  v93 = v94;
                v7 = v93 + v92;
                *((_DWORD *)&v202[8] + v91 + 3) = v93;
              }
              while ( v87 < v88 );
              v86 = 2 * v87 + 1;
            }
            v20 = (unsigned int)(v86 - 1);
            if ( (unsigned int)v20 < v180 )
            {
              v95 = v54 - v7;
              v96 = (int)v201[v86 + 33829];
              v20 = *((unsigned int *)&v202[17] + v96 + 3);
              if ( (int)v20 < v95 )
                v95 = *((_DWORD *)&v202[17] + v96 + 3);
              *((_DWORD *)&v202[8] + v96 + 3) = v95;
              v7 += v95;
            }
            if ( v7 )
            {
LABEL_138:
              v97 = 0;
              do
              {
                v98 = v203[v97];
                v99 = *((_DWORD *)&v202[8] + v98 + 3);
                v100 = 1025 * v98;
                if ( v99 != dword_1836FD2E4[1025 * v98] )
                  v206[v98] = 1;
                if ( v99 > 0 )
                {
                  v101 = (int)v173[1025 * v98];
                  v102 = 0;
                  if ( v206[v98] )
                  {
                    v103 = 0;
                    if ( v101 > 0 )
                    {
                      v104 = &v201[v100 + 3];
                      do
                      {
                        if ( v103 >= v99 )
                          break;
                        if ( !v104[v102 - 1025] )
                        {
                          v104[v102 - 1025] = CurrentProcessId;
                          ++v103;
                          v101 = (int)v173[v100];
                        }
                        ++v102;
                      }
                      while ( v102 < v101 );
                    }
                  }
                  else if ( v101 > 0 )
                  {
                    do
                    {
                      if ( CurrentProcessId == dword_1836FE2E0[v100 - 1022 + v102] )
                      {
                        v201[v100 - 1022 + v102] = CurrentProcessId;
                        v101 = (int)v173[1025 * v98];
                      }
                      ++v102;
                    }
                    while ( v102 < v101 );
                  }
                }
                ++v97;
              }
              while ( v97 < v38 );
              v105 = (int)v13;
              v106 = 1;
              v188 = v2;
              v107 = 1025;
              v108 = v13;
              v109 = CurrentProcessId;
              do
              {
                v110 = 4LL * (int)v173[v107];
                dword_1836FD2E8[v107 - 1] = v173[v107];
                mkl_serv_memcpy_s(&dword_1836FD2E8[v107], v110, &v173[v107 + 1], v110);
                ++v106;
                v107 += 1025;
              }
              while ( v106 <= v105 );
              v111 = 0;
              v112 = 1;
              v187 = v3;
              v113 = 0x1FFFFFFFFFFFFFFFLL;
              do
              {
                mkl_ueaa_get_phy_device_mask((unsigned int)v112, &v191);
                if ( v191 )
                {
                  ++v111;
                  ++v113;
                  workdivision = mkl_aa_fw_get_workdivision(v111);
                  if ( workdivision != 0.0 && !*((_DWORD *)&v202[8] + v112 + 3) )
                    mkl_aa_fw_set_workdivision(v114, v111);
                  *(double *)&mkl_aa_offload_factors_save[v113] = workdivision;
                }
                ++v112;
              }
              while ( v112 <= v108 );
              v2 = v188;
              CurrentProcessId = v109;
              v3 = v187;
              LODWORD(v13) = v108;
            }
          }
        }
      }
      goto LABEL_165;
    }
  }
LABEL_166:
  v116 = 1;
  v117 = 4100;
  if ( (int)v13 <= 0 )
    goto LABEL_218;
  v13 = (int)v13;
  v188 = v2;
  v187 = v3;
  v189 = v8;
  v118 = CurrentProcessId;
  v183 = v7;
  do
  {
    v119 = *(int *)((char *)v173 + v117);
    v120 = 0;
    if ( v119 <= 0 )
      goto LABEL_213;
    if ( v119 < 16 )
    {
      v122 = 0;
    }
    else
    {
      v121 = 0;
      v122 = (int)(v119 & 0xFFFFFFF0);
      do
      {
        *(_OWORD *)&v206[v121 / 4 + 35] = 0;
        v121 += 16LL;
      }
      while ( v121 < v122 );
    }
    for ( ; v122 < v119; ++v122 )
      *((_BYTE *)&v206[35] + v122) = 0;
    if ( v119 < 16 )
    {
      for ( j = 0; j < v119; ++j )
      {
LABEL_210:
        if ( v118 == *(_DWORD *)((char *)&v201[j - 1022] + v117) )
        {
          *((_BYTE *)&v206[35] + j) = 1;
          ++v120;
        }
      }
      goto LABEL_213;
    }
    v123 = _mm_srli_si128(_mm_load_si128(&xmmword_18340A2C0), 1);
    v124 = 0;
    v125 = _mm_srli_si128(v123, 1);
    v126 = 0;
    v127 = _mm_srli_si128(v125, 1);
    v128 = 0;
    v129 = _mm_srli_si128(v127, 1);
    v130 = 0;
    v131 = _mm_srli_si128(v129, 1);
    v132 = _mm_srli_si128(v131, 1);
    v133 = _mm_srli_si128(v132, 1);
    v134 = _mm_srli_si128(v133, 1);
    v135 = _mm_srli_si128(v134, 1);
    v185 = _mm_srli_si128(v135, 1);
    v136 = _mm_srli_si128(v185, 1);
    v184 = _mm_shuffle_epi32(_mm_cvtsi32_si128(v118), 0);
    v137 = _mm_srli_si128(v136, 1);
    v186 = _mm_srli_si128(v137, 1);
    v138 = _mm_srli_si128(v186, 1);
    v139 = _mm_cvtsi128_si32(v129);
    v140 = _mm_load_si128(&v185);
    LODWORD(v178) = _mm_cvtsi128_si32(v138);
    v141 = _mm_cvtsi128_si32(v132);
    si128 = _mm_load_si128(&xmmword_18340A2C0);
    v143 = (int)(v119 & 0xFFFFFFF0);
    v182 = 0;
    v144 = _mm_cvtsi128_si32(v131);
    v181 = _mm_cvtsi128_si32(v135);
    v180 = _mm_cvtsi128_si32(v140);
    v179 = _mm_cvtsi128_si32(v137);
    v145 = _mm_load_si128(&v186);
    LODWORD(v177) = _mm_cvtsi128_si32(_mm_srli_si128(v138, 1));
    v176 = _mm_cvtsi128_si32(si128);
    v175 = (char *)&v201[3] + v117;
    v193 = v119;
    v194 = v13;
    v195 = v117;
    v196 = v116;
    v192 = v118;
    v146 = _mm_cvtsi128_si32(v123);
    v200 = _mm_cvtsi128_si32(v134);
    v199 = _mm_cvtsi128_si32(v136);
    v147 = _mm_cvtsi128_si32(v125);
    v198 = _mm_cvtsi128_si32(v145);
    v148 = _mm_cvtsi128_si32(v127);
    v149 = _mm_cvtsi128_si32(v133);
    v150 = _mm_load_si128(&v184);
    v151 = v176;
    v152 = v177;
    v153 = v178;
    v154 = v179;
    v155 = v180;
    v156 = v181;
    v157 = 0;
    v197 = v143;
    do
    {
      v158 = _mm_cmpeq_epi32(_mm_loadu_si128((const __m128i *)&v175[4 * v157 - 4100]), v150);
      v159 = _mm_cmpeq_epi32(_mm_loadu_si128((const __m128i *)&v175[4 * v157 - 4068]), v150);
      v160 = _mm_cmpeq_epi32(_mm_loadu_si128((const __m128i *)&v175[4 * v157 - 4084]), v150);
      v161 = _mm_cmpeq_epi32(_mm_loadu_si128((const __m128i *)&v175[4 * v157 - 4052]), v150);
      v174 = _mm_movemask_epi8(_mm_packs_epi16(_mm_packs_epi32(v158, v160), _mm_packs_epi32(v159, v161)));
      if ( (v174 & 1) != 0 )
        LOBYTE(v206[v157 / 4 + 35]) = v151;
      if ( (v174 & 2) != 0 )
        BYTE1(v206[v157 / 4 + 35]) = v146;
      if ( (v174 & 4) != 0 )
        BYTE2(v206[v157 / 4 + 35]) = v147;
      if ( (v174 & 8) != 0 )
        HIBYTE(v206[v157 / 4 + 35]) = v148;
      if ( (v174 & 0x10) != 0 )
        LOBYTE(v206[v157 / 4 + 36]) = v139;
      if ( (v174 & 0x20) != 0 )
        BYTE1(v206[v157 / 4 + 36]) = v144;
      if ( (v174 & 0x40) != 0 )
        BYTE2(v206[v157 / 4 + 36]) = v141;
      if ( (v174 & 0x80) != 0 )
        HIBYTE(v206[v157 / 4 + 36]) = v149;
      if ( (v174 & 0x100) != 0 )
        LOBYTE(v206[v157 / 4 + 37]) = v200;
      if ( (v174 & 0x200) != 0 )
        BYTE1(v206[v157 / 4 + 37]) = v156;
      if ( (v174 & 0x400) != 0 )
        BYTE2(v206[v157 / 4 + 37]) = v155;
      if ( (v174 & 0x800) != 0 )
        HIBYTE(v206[v157 / 4 + 37]) = v199;
      if ( (v174 & 0x1000) != 0 )
        LOBYTE(v206[v157 / 4 + 38]) = v154;
      if ( (v174 & 0x2000) != 0 )
        BYTE1(v206[v157 / 4 + 38]) = v198;
      if ( (v174 & 0x4000) != 0 )
        BYTE2(v206[v157 / 4 + 38]) = v153;
      if ( (v174 & 0x8000) != 0 )
        HIBYTE(v206[v157 / 4 + 38]) = v152;
      v157 += 16LL;
      v124 = _mm_sub_epi32(v124, v158);
      v126 = _mm_sub_epi32(v126, v160);
      v128 = _mm_sub_epi32(v128, v159);
      v130 = _mm_sub_epi32(v130, v161);
    }
    while ( v157 < v197 );
    v162 = _mm_add_epi32(_mm_add_epi32(_mm_add_epi32(v124, v126), v128), v130);
    v163 = _mm_add_epi32(v162, _mm_srli_si128(v162, 8));
    j = v197;
    v119 = v193;
    v13 = v194;
    v117 = v195;
    v116 = v196;
    v118 = v192;
    v120 = _mm_cvtsi128_si32(_mm_add_epi32(v163, _mm_srli_epi64(v163, 0x20u)));
    if ( v197 < v193 )
      goto LABEL_210;
LABEL_213:
    v206[291] = v119;
    v206[292] = v120;
    if ( v120 )
      v207 = v206[v116];
    else
      v207 = 0;
    v208 = v118;
    mkl_ueaa_set_phy_affinity_params((unsigned int)v116++);
    v117 += 4100;
  }
  while ( v116 <= v13 );
  v8 = v189;
  v7 = v183;
LABEL_218:
  if ( !v8 )
    return (unsigned int)v7;
  return v8;
}

```

## disassembly

```asm
0x18012bf20  push    rbx
0x18012bf21  push    rsi
0x18012bf22  push    rdi
0x18012bf23  push    r12
0x18012bf25  push    r13
0x18012bf27  push    r14
0x18012bf29  push    r15
0x18012bf2b  push    rbp
0x18012bf2c  mov     eax, 21948h
0x18012bf31  call    _alloca_probe
0x18012bf36  sub     rsp, 21948h
0x18012bf3d  mov     r12d, edx
0x18012bf40  mov     [rsp+21988h+var_21938], ecx
0x18012bf44  mov     rax, cs:__security_cookie
0x18012bf4b  xor     rax, rsp
0x18012bf4e  mov     [rsp+21988h+var_48], rax
0x18012bf56  call    mkl_serv_dsecnd
0x18012bf5b  xor     esi, esi
0x18012bf5d  xor     r13d, r13d
0x18012bf60  mov     [rsp+21988h+var_21840], 0
0x18012bf6b  xor     ebx, ebx
0x18012bf6d  call    mkl_ueaa_get_phy_device_count
0x18012bf72  mov     edi, eax
0x18012bf74  xor     ecx, ecx
0x18012bf76  xor     r15d, r15d
0x18012bf79  xor     edx, edx
0x18012bf7b  lea     ebp, [rdi-1]
0x18012bf7e  xor     r14d, r14d
0x18012bf81  xor     r8d, r8d
0x18012bf84  mov     [rsp+rcx*8+21988h+var_4E0], r8d
0x18012bf8c  mov     [rsp+rcx*8+21988h+var_4DC], r8d
0x18012bf94  inc     rcx
0x18012bf97  mov     [rsp+rdx+21988h+var_217E8], r8d
0x18012bf9f  mov     [rsp+rdx+21988h+var_207E4], r8d
0x18012bfa7  add     rdx, 2008h
0x18012bfae  cmp     rcx, 10h
0x18012bfb2  jb      short loc_18012BF84
0x18012bfb4  xor     edx, edx
0x18012bfb6  mov     [rsp+21988h+var_460], edx
0x18012bfbd  mov     [rsp+21988h+var_1768], edx
0x18012bfc4  call    cs:__imp_GetCurrentProcessId
0x18012bfca  mov     r8d, eax
0x18012bfcd  pxor    xmm0, xmm0
0x18012bfd1  comisd  xmm0, cs:mkl_aa_fraction
0x18012bfd9  jnb     loc_18012CABE
0x18012bfdf  test    ebp, ebp
0x18012bfe1  jg      short loc_18012C00C
0x18012bfe3  mov     rcx, [rsp+21988h+var_48]
0x18012bfeb  xor     rcx, rsp; StackCookie
0x18012bfee  call    __security_check_cookie
0x18012bff3  mov     eax, 0FFFFFFFFh
0x18012bff8  add     rsp, 21948h
0x18012bfff  pop     rbp
0x18012c000  pop     r15
0x18012c002  pop     r14
0x18012c004  pop     r13
0x18012c006  pop     r12
0x18012c008  pop     rdi
0x18012c009  pop     rsi
0x18012c00a  pop     rbx
0x18012c00b  retn
0x18012c00c  xor     ecx, ecx
0x18012c00e  mov     edx, 1
0x18012c013  mov     eax, 1
0x18012c018  movaps  [rsp+21988h+var_21858], xmm6
0x18012c020  mov     [rsp+21988h+var_21848], ebx
0x18012c027  mov     ebx, ecx
0x18012c029  mov     [rsp+21988h+var_21838], r8d
0x18012c031  pxor    xmm6, xmm6
0x18012c035  mov     [rsp+21988h+var_21968], edi
0x18012c039  mov     rdi, rax
0x18012c03c  mov     [rsp+21988h+var_21920], r13d
0x18012c041  mov     r13d, ecx
0x18012c044  mov     [rsp+21988h+var_21940], r12d
0x18012c049  mov     r12d, edx
0x18012c04c  mov     ecx, r12d
0x18012c04f  lea     rdx, [rsp+21988h+var_2183C]
0x18012c057  mov     [rsp+rdi*4+21988h+var_75C], 0
0x18012c062  call    mkl_ueaa_get_phy_device_mask
0x18012c067  cmp     [rsp+21988h+var_2183C], 0
0x18012c06f  jz      short loc_18012C0CD
0x18012c071  inc     ebx
0x18012c073  lea     rcx, [rsp+21988h+var_520]
0x18012c07b  mov     edx, ebx
0x18012c07d  call    mkl_ueaa_get_device_info
0x18012c082  test    eax, eax
0x18012c084  jnz     loc_18012D17D
0x18012c08a  mov     ecx, ebx
0x18012c08c  mov     r8d, [rsp+21988h+var_50C]
0x18012c094  add     r8d, 0FFFFFFFCh
0x18012c098  mov     [rsp+rdi*4+21988h+var_75C], r8d
0x18012c0a0  call    mkl_aa_fw_get_workdivision
0x18012c0a5  ucomisd xmm0, xmm6
0x18012c0a9  jp      short loc_18012C0AD
0x18012c0ab  jz      short loc_18012C0CD
0x18012c0ad  mov     r8d, [rsp+rdi*4+21988h+var_75C]
0x18012c0b5  test    r8d, r8d
0x18012c0b8  mov     [rsp+r14*4+21988h+var_5A8], r12d
0x18012c0c0  cmovl   r8d, r13d
0x18012c0c4  inc     r14
0x18012c0c7  add     esi, r8d
0x18012c0ca  inc     r15d
0x18012c0cd  inc     r12d
0x18012c0d0  inc     rdi
0x18012c0d3  cmp     r12d, ebp
0x18012c0d6  jle     loc_18012C04C
0x18012c0dc  movaps  xmm6, [rsp+21988h+var_21858]
0x18012c0e4  test    esi, esi
0x18012c0e6  mov     ebx, [rsp+21988h+var_21848]
0x18012c0ed  mov     r8d, [rsp+21988h+var_21838]
0x18012c0f5  mov     edi, [rsp+21988h+var_21968]
0x18012c0f9  mov     r13d, [rsp+21988h+var_21920]
0x18012c0fe  mov     r12d, [rsp+21988h+var_21940]
0x18012c103  jnz     short loc_18012C10F
0x18012c105  mov     ebx, 0FFFFFFFFh
0x18012c10a  jmp     loc_18012CABE
0x18012c10f  pxor    xmm0, xmm0
0x18012c113  cvtsi2sd xmm0, esi
0x18012c117  mulsd   xmm0, cs:mkl_aa_fraction
0x18012c11f  cvttsd2si edx, xmm0
0x18012c123  mov     r10d, edx
0x18012c126  sar     r10d, 1
0x18012c129  shr     r10d, 1Eh
0x18012c12d  add     r10d, edx
0x18012c130  and     r10d, 0FFFFFFFCh
0x18012c134  cmp     r10d, r12d
0x18012c137  jl      loc_18012CABE
0x18012c13d  mov     [rsp+21988h+var_21958], r10d
0x18012c142  lea     rcx, [rsp+21988h+var_217F0]
0x18012c14a  mov     [rcx-48h], r8d
0x18012c14e  lea     rdx, [rsp+21988h+var_21840]
0x18012c156  call    mkl_aa_fw_lock_sharing_mask
0x18012c15b  mov     r8d, [rsp+21988h+var_21838]
0x18012c163  mov     r10d, [rsp+21988h+var_21958]
0x18012c168  test    eax, eax
0x18012c16a  jnz     short loc_18012C105
0x18012c16c  mov     ecx, ebp
0x18012c16e  mov     r9d, 1
0x18012c174  shr     ecx, 1Fh
0x18012c177  xor     edx, edx
0x18012c179  lea     esi, [rdi+rcx-1]
0x18012c17d  xor     ecx, ecx
0x18012c17f  sar     esi, 1
0x18012c181  movsxd  rsi, esi
0x18012c184  test    rsi, rsi
0x18012c187  jbe     short loc_18012C1B7
0x18012c189  xor     r9d, r9d
0x18012c18c  lea     r11, cs:180000000h
0x18012c193  inc     rdx
0x18012c196  mov     rva dword_1836FE2E8[r11+rcx], r9d
0x18012c19e  mov     rva dword_1836FF2EC[r11+rcx], r9d
0x18012c1a6  add     rcx, 2008h
0x18012c1ad  cmp     rdx, rsi
0x18012c1b0  jb      short loc_18012C193
0x18012c1b2  lea     r9d, [rdx+rdx+1]
0x18012c1b7  lea     edx, [r9-1]
0x18012c1bb  cmp     ebp, edx
0x18012c1bd  jbe     short loc_18012C1DF
0x18012c1bf  movsxd  r9, r9d
0x18012c1c2  lea     rcx, cs:180000000h
0x18012c1c9  mov     rdx, r9
0x18012c1cc  shl     rdx, 0Ch
0x18012c1d0  lea     rsi, [rdx+r9*4]
0x18012c1d4  mov     rva dword_1836FD2E4[rcx+rsi], 0
0x18012c1df  movsxd  rdi, edi
0x18012c1e2  dec     rdi
0x18012c1e5  cmp     rdi, 4
0x18012c1e9  jl      loc_18012D176
0x18012c1ef  mov     ecx, edi
0x18012c1f1  xor     edx, edx
0x18012c1f3  and     ecx, 0FFFFFFFCh
0x18012c1f6  pxor    xmm0, xmm0
0x18012c1fa  movsxd  rcx, ecx
0x18012c1fd  movdqa  [rsp+rdx*4+21988h+var_6C8], xmm0
0x18012c206  movdqa  [rsp+rdx*4+21988h+var_638], xmm0
0x18012c20f  add     rdx, 4
0x18012c213  cmp     rdx, rcx
0x18012c216  jb      short loc_18012C1FD
0x18012c218  cmp     rcx, rdi
0x18012c21b  jnb     short loc_18012C235
0x18012c21d  xor     edx, edx
0x18012c21f  mov     dword ptr [rsp+rcx*4+21988h+var_6C8], edx
0x18012c226  mov     dword ptr [rsp+rcx*4+21988h+var_638], edx
0x18012c22d  inc     rcx
0x18012c230  cmp     rcx, rdi
0x18012c233  jb      short loc_18012C21F
0x18012c235  cmp     [rsp+21988h+var_21840], 0
0x18012c23d  jz      loc_18012C2C9
0x18012c243  mov     [rsp+21988h+var_217EC], ebp
0x18012c24a  mov     r11d, 1
0x18012c250  mov     [rsp+21988h+var_217F0], 1
0x18012c25b  mov     eax, 1004h
0x18012c260  movsxd  r9, ebp
0x18012c263  xor     edx, edx
0x18012c265  mov     [rsp+21988h+var_21940], r12d
0x18012c26a  lea     rcx, cs:180000000h
0x18012c271  mov     r12d, [rsp+r11*4+21988h+var_75C]
0x18012c279  xor     esi, esi
0x18012c27b  mov     [rsp+rax+21988h+var_227EC], r12d
0x18012c283  mov     rdi, rax
0x18012c286  test    r12d, r12d
0x18012c289  jle     short loc_18012C2B6
0x18012c28b  lea     r12, [rsp+rax+21988h+var_217E4]
0x18012c293  mov     [r12+rsi*4-1004h], edx
0x18012c29b  inc     rsi
0x18012c29e  mov     rva dword_1836FD2E8[rcx+rdi], edx
0x18012c2a5  add     rdi, 4
0x18012c2a9  movsxd  r14, [rsp+rax+21988h+var_227EC]
0x18012c2b1  cmp     rsi, r14
0x18012c2b4  jl      short loc_18012C293
0x18012c2b6  inc     r11
0x18012c2b9  add     rax, 1004h
0x18012c2bf  cmp     r11, r9
0x18012c2c2  jle     short loc_18012C271
0x18012c2c4  mov     r12d, [rsp+21988h+var_21940]
0x18012c2c9  xor     ecx, ecx
0x18012c2cb  xor     edx, edx
0x18012c2cd  test    r15d, r15d
0x18012c2d0  jle     loc_18012CAA1
0x18012c2d6  movsxd  r9, r15d
0x18012c2d9  xor     edi, edi
0x18012c2db  mov     [rsp+21988h+var_21848], ebx
0x18012c2e2  mov     [rsp+21988h+var_21958], r10d
0x18012c2e7  lea     r10, cs:180000000h
0x18012c2ee  mov     dword ptr [rsp+21988h+var_21960], r15d
0x18012c2f3  mov     [rsp+21988h+var_21968], ebp
0x18012c2f7  mov     [rsp+21988h+var_21920], r13d
0x18012c2fc  mov     [rsp+21988h+var_21940], r12d
0x18012c301  mov     r12d, 1
0x18012c307  movsxd  r13, [rsp+rdx*4+21988h+var_5A8]
0x18012c30f  mov     esi, edi
0x18012c311  mov     rax, r13
0x18012c314  shl     rax, 0Ch
0x18012c318  lea     r14, [rax+r13*4]
0x18012c31c  mov     r15d, [rsp+r14+21988h+var_227EC]
0x18012c324  test    r15d, r15d
0x18012c327  jle     loc_18012C457
0x18012c32d  mov     r11d, r15d
0x18012c330  mov     eax, r12d
0x18012c333  shr     r11d, 1Fh
0x18012c337  xor     ebx, ebx
0x18012c339  add     r11d, r15d
0x18012c33c  sar     r11d, 1
0x18012c33f  movsxd  r11, r11d
0x18012c342  test    r11, r11
0x18012c345  jbe     loc_18012C3F8
0x18012c34b  mov     ebp, [rsp+r13*4+21988h+var_63C]
0x18012c353  lea     rax, [rsp+r14+21988h+var_217E4]
0x18012c35b  mov     [rsp+21988h+var_21948], r9
0x18012c360  mov     [rsp+21988h+var_21950], rdx
0x18012c365  mov     esi, [rax+rbx*8-1004h]
0x18012c36c  test    esi, esi
0x18012c36e  mov     edx, edi
0x18012c370  cmovz   edx, r12d
0x18012c374  add     ebp, edx
0x18012c376  lea     rdx, [r14+rbx*8]
0x18012c37a  cmp     r8d, rva dword_1836FD2E8[r10+rdx]
0x18012c382  jnz     short loc_18012C39C
0x18012c384  test    esi, esi
0x18012c386  jz      short loc_18012C394
0x18012c388  mov     [rsp+r13*4+21988h+var_4E4], 1
0x18012c394  inc     rva dword_1836FD2E4[r10+r14]
0x18012c39c  mov     r9d, [rax+rbx*8-1000h]
0x18012c3a4  test    r9d, r9d
0x18012c3a7  mov     esi, edi
0x18012c3a9  cmovz   esi, r12d
0x18012c3ad  add     ecx, ebp
0x18012c3af  add     ebp, esi
0x18012c3b1  cmp     r8d, rva dword_1836FD2EC[r10+rdx]
0x18012c3b9  jnz     short loc_18012C3D4
0x18012c3bb  test    r9d, r9d
0x18012c3be  jz      short loc_18012C3CC
0x18012c3c0  mov     [rsp+r13*4+21988h+var_4E4], 1
0x18012c3cc  inc     rva dword_1836FD2E4[r10+r14]
0x18012c3d4  add     ecx, ebp
0x18012c3d6  lea     esi, [rbx+rbx+2]
0x18012c3da  inc     rbx
0x18012c3dd  cmp     rbx, r11
0x18012c3e0  jb      short loc_18012C365
0x18012c3e2  mov     r9, [rsp+21988h+var_21948]
0x18012c3e7  lea     eax, [rbx+rbx+1]
0x18012c3eb  mov     rdx, [rsp+21988h+var_21950]
0x18012c3f0  mov     [rsp+r13*4+21988h+var_63C], ebp
0x18012c3f8  lea     r11d, [rax-1]
0x18012c3fc  cmp     r15d, r11d
0x18012c3ff  jbe     short loc_18012C457
0x18012c401  movsxd  rax, eax
0x18012c404  lea     rsi, [rsp+r14+21988h+var_217E4]
0x18012c40c  mov     r15d, edi
0x18012c40f  mov     esi, [rsi+rax*4-1008h]
0x18012c416  test    esi, esi
0x18012c418  lea     r11, [r14+rax*4]
0x18012c41c  cmovz   r15d, r12d
0x18012c420  add     r15d, [rsp+r13*4+21988h+var_63C]
0x18012c428  mov     [rsp+r13*4+21988h+var_63C], r15d
0x18012c430  cmp     r8d, rva dword_1836FD2E4[r10+r11]
0x18012c438  jnz     short loc_18012C452
0x18012c43a  test    esi, esi
0x18012c43c  jz      short loc_18012C44A
0x18012c43e  mov     [rsp+r13*4+21988h+var_4E4], 1
  ... truncated ...
```
