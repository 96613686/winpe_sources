# AslpFileMakeStringVersionAttributes

- ea: `0x180014550`
- end: `0x180015773`
- name: `AslpFileMakeStringVersionAttributes`
- size: `4643`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001445c`

## callees

- `0x18000f114`
- `0x180014550`
- `0x18001577c`
- `0x1800159e0`
- `0x180039a5a`
- `0x180059270`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001477a`
- `ntdll!RtlFreeHeap` at `0x180014b8b`
- `ntdll!RtlFreeHeap` at `0x180014fde`
- `ntdll!RtlFreeHeap` at `0x18001477a`
- `ntdll!RtlFreeHeap` at `0x180014b8b`
- `ntdll!RtlFreeHeap` at `0x180014fde`

## string_xrefs

- `0x180014c17`: `RtlStringCchCopyW failed [%x]`
- `0x180015743`: `AslStringXmlSanitize failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileMakeStringVersionAttributes(_DWORD *a1, unsigned __int16 *a2)
{
  unsigned __int16 *i; // rdi
  _DWORD *v3; // r12
  unsigned __int64 v4; // r13
  unsigned __int64 v5; // rbp
  int v6; // eax
  int v7; // ebx
  __int64 v8; // rax
  const wchar_t *v9; // rbx
  char *v10; // r14
  __int16 v11; // r15
  unsigned __int16 *v12; // rbp
  const WCHAR *v13; // rcx
  const wchar_t *v14; // r9
  const WCHAR *v15; // rcx
  WCHAR v16; // dx
  const wchar_t *v17; // rsi
  __int64 v18; // rcx
  unsigned __int64 v19; // r8
  _WORD *v20; // rax
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rdx
  int v24; // eax
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rax
  unsigned __int16 *v29; // rsi
  _WORD *v30; // rax
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rdx
  int v33; // eax
  unsigned __int64 v34; // rax
  unsigned int v35; // ebp
  unsigned __int64 v36; // rax
  unsigned __int64 v37; // rbp
  __int64 v38; // rax
  unsigned __int16 *v39; // rdi
  unsigned __int64 v40; // r12
  wchar_t *v41; // r10
  wchar_t *v42; // rdx
  _WORD *v43; // r9
  __int64 v44; // rcx
  __int64 v45; // r8
  _WORD *v46; // rax
  int v47; // ebx
  __int64 v48; // rcx
  _WORD *v49; // rax
  __int64 v50; // r8
  const char *v51; // r9
  int v52; // eax
  __int64 v53; // rdx
  wchar_t *v54; // r8
  _WORD *v55; // r9
  _WORD *v56; // rax
  unsigned __int16 *v57; // rsi
  unsigned __int16 *k; // r14
  int v59; // eax
  __int64 v60; // rax
  const wchar_t *v61; // rdi
  char *v62; // rbp
  __int16 v63; // r15
  unsigned __int16 *v64; // rsi
  const WCHAR *v65; // rcx
  const wchar_t *v66; // r9
  const WCHAR *v67; // rdx
  WCHAR v68; // r8
  const wchar_t *v69; // rbx
  const wchar_t *m; // rdx
  __int64 v71; // rcx
  unsigned __int64 v72; // r8
  _WORD *v73; // rax
  unsigned __int64 v74; // rcx
  unsigned __int64 v75; // rdx
  unsigned __int64 v76; // rdx
  int v77; // eax
  unsigned __int64 v78; // rax
  unsigned __int64 v79; // rdx
  unsigned __int64 v80; // rdx
  unsigned __int64 v81; // rax
  unsigned __int64 v82; // rsi
  WCHAR v83; // dx
  unsigned int v84; // edi
  const WCHAR *v86; // rcx
  const wchar_t *v87; // r10
  const WCHAR *v88; // r9
  WCHAR v89; // r8
  WCHAR v90; // r8
  _WORD *v91; // rax
  unsigned __int64 v92; // rcx
  unsigned __int64 v93; // rdx
  int v94; // eax
  unsigned __int16 *v95; // r12
  unsigned __int16 *v96; // rdi
  unsigned __int16 *n; // rsi
  int v98; // eax
  __int64 v99; // rax
  __int16 v100; // r15
  char *v101; // r14
  const wchar_t *v102; // rdi
  const wchar_t *v103; // rbx
  unsigned __int16 *v104; // rbp
  const WCHAR *v105; // rcx
  const wchar_t *v106; // r9
  const WCHAR *v107; // rdx
  WCHAR v108; // cx
  const wchar_t *ii; // r9
  __int64 v110; // rcx
  unsigned __int64 v111; // r8
  _WORD *v112; // rax
  unsigned __int64 v113; // rcx
  unsigned __int64 v114; // rdx
  unsigned __int64 v115; // rdx
  int v116; // eax
  unsigned __int64 v117; // rax
  unsigned __int64 v118; // rdx
  unsigned __int64 v119; // rdx
  unsigned __int64 v120; // rax
  unsigned __int16 *v121; // rdi
  unsigned __int64 v122; // rbp
  _WORD *v123; // rax
  unsigned __int64 v124; // rcx
  int v125; // eax
  unsigned __int64 v126; // rdx
  unsigned __int64 v127; // rax
  unsigned __int64 jj; // rcx
  unsigned __int64 kk; // r9
  unsigned __int16 v130; // r8
  __int64 v131; // rax
  _DWORD *v132; // rcx
  WCHAR v133; // dx
  unsigned __int64 v134; // rax
  _WORD *v135; // rdx
  unsigned __int64 v136; // rsi
  unsigned __int64 v137; // rcx
  _WORD *v138; // rax
  int v139; // r8d
  const char *v140; // r9
  __int64 v141; // r8
  unsigned __int64 v142; // rax
  unsigned __int64 v143; // rbp
  unsigned __int64 v144; // rcx
  _WORD *v145; // rax
  int v146; // r8d
  unsigned __int64 v147; // rax
  const WCHAR *v148; // rcx
  const wchar_t *v149; // r10
  const WCHAR *v150; // rdx
  WCHAR v151; // cx
  WCHAR v152; // dx
  const char *v153; // r9
  __int64 v154; // r8
  WCHAR v155; // dx
  __int64 v156; // rax
  const wchar_t *j; // rcx
  const WCHAR *v158; // rdx
  const wchar_t *v159; // r10
  const WCHAR *v160; // rdx
  WCHAR v161; // r8
  WCHAR v162; // r8
  const char *v163; // r9
  __int64 v164; // r8
  __int64 v165; // r8
  __int64 v166; // [rsp+20h] [rbp-1A8h]
  wchar_t *v167; // [rsp+30h] [rbp-198h]
  PVOID P; // [rsp+38h] [rbp-190h] BYREF
  PVOID v169; // [rsp+40h] [rbp-188h] BYREF
  int v170; // [rsp+48h] [rbp-180h]
  unsigned __int16 *v171; // [rsp+50h] [rbp-178h]
  unsigned __int64 v172; // [rsp+58h] [rbp-170h]
  unsigned __int16 *v173; // [rsp+60h] [rbp-168h]
  _DWORD *v174; // [rsp+68h] [rbp-160h]
  unsigned __int64 v175; // [rsp+70h] [rbp-158h]
  _WORD v176[128]; // [rsp+80h] [rbp-148h] BYREF
  __int64 v177; // [rsp+180h] [rbp-48h] BYREF

  v173 = a2;
  i = a2;
  v174 = a1;
  v3 = a1;
  if ( !a2 )
  {
    a1[46] |= 2u;
    a1[54] |= 2u;
    a1[62] |= 2u;
    a1[70] |= 2u;
    a1[78] |= 2u;
    a1[86] |= 2u;
    a1[94] |= 2u;
    a1[102] |= 2u;
    a1[198] |= 2u;
    return 0;
  }
  v4 = 0;
  v5 = 0;
  v172 = (unsigned __int64)a2;
  P = 0;
  if ( a2[2] )
  {
    v163 = "Version block invalid";
    v164 = 2787;
LABEL_350:
    v7 = -1073741811;
    AslLogCallPrintf(1, "AslpFileVerQueryBlock", v164, v163);
LABEL_41:
    i = 0;
    goto LABEL_42;
  }
  v6 = AslStringDuplicate(&P, L"\\VarFileInfo\\Translation");
  v7 = v6;
  if ( v6 < 0 )
  {
    AslLogCallPrintf(1, "AslpFileVerQueryBlock", 2793, "AslStringDuplicate failed [%x]", v6);
    goto LABEL_41;
  }
  v8 = *i;
  if ( (unsigned __int16)v8 > 0x7FFFu )
  {
    v163 = "VersionBlock is too long";
    v164 = 2805;
    goto LABEL_350;
  }
  if ( (unsigned int)v8 < 8 )
  {
    v163 = "VersionBlock not long enough";
    v164 = 2810;
    goto LABEL_350;
  }
  v9 = (const wchar_t *)P;
  v10 = (char *)i + v8;
  v11 = *(unsigned __int16 *)((char *)i + v8 - 2);
  v12 = (unsigned __int16 *)v10;
  *((_WORD *)v10 - 1) = 0;
  if ( v9 )
  {
    for ( ; *v9; ++v9 )
    {
      v13 = L"\\";
      if ( pszSrc[0] )
      {
        v155 = pszSrc[0];
        while ( v155 != *v9 )
        {
          v155 = v13[1];
          ++v13;
          if ( !v155 )
            goto LABEL_10;
        }
      }
      if ( !*v13 )
        break;
    }
LABEL_10:
    v14 = v9;
    while ( *v9 )
    {
      v15 = L"\\";
      if ( pszSrc[0] )
      {
        v16 = pszSrc[0];
        do
        {
          if ( v16 == *v9 )
            break;
          v16 = v15[1];
          ++v15;
        }
        while ( v16 );
      }
      if ( *v15 )
      {
        *v9++ = 0;
        break;
      }
      ++v9;
    }
    v17 = 0;
    if ( v9 != v14 )
      v17 = v14;
  }
  else
  {
    v9 = 0;
    v17 = 0;
  }
LABEL_22:
  if ( v17 )
  {
    v18 = (unsigned int)((_DWORD)v10 - (_DWORD)i);
    if ( (unsigned int)v18 >= 8 )
    {
      v19 = *i;
      if ( (unsigned int)v19 <= (unsigned int)v18 && (unsigned int)v18 <= 0x7FFF )
      {
        v20 = i + 3;
        if ( i != (unsigned __int16 *)-6LL )
        {
          v21 = (unsigned __int64)(v18 - 6) >> 1;
          if ( v21 <= 0x7FFFFFFF )
          {
            v22 = v21;
            if ( v21 )
            {
              while ( *v20 )
              {
                ++v20;
                if ( !--v21 )
                  goto LABEL_31;
              }
              v23 = v22 - v21;
              v24 = 0;
            }
            else
            {
LABEL_31:
              v23 = 0;
              v24 = -1073741811;
            }
            if ( v24 >= 0 )
            {
              v25 = 2 * v23;
              v26 = 2 * v23 + 8;
              if ( v26 >= v25 )
              {
                v27 = ((i[1] + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + ((v26 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
                if ( v27 <= v19 )
                {
                  v12 = (unsigned __int16 *)((char *)i + v19);
                  for ( i = (unsigned __int16 *)((char *)i + v27);
                        i < v12;
                        i = (unsigned __int16 *)((char *)i + ((*i + 3LL) & 0xFFFFFFFFFFFFFFFCuLL)) )
                  {
                    v28 = *i;
                    if ( (unsigned int)v28 <= 8 || v28 > (char *)v12 - (char *)i )
                      break;
                    if ( !wcsicmp_0(v17, i + 3) )
                    {
                      if ( v9 )
                      {
                        for ( j = v9; *j; ++j )
                        {
                          v158 = L"\\";
                          if ( pszSrc[0] )
                          {
                            v162 = pszSrc[0];
                            while ( v162 != *j )
                            {
                              v162 = v158[1];
                              ++v158;
                              if ( !v162 )
                                goto LABEL_328;
                            }
                          }
                          if ( !*v158 )
                            break;
                        }
LABEL_328:
                        v159 = j;
                        while ( *j )
                        {
                          v160 = L"\\";
                          if ( pszSrc[0] )
                          {
                            v161 = pszSrc[0];
                            do
                            {
                              if ( v161 == *j )
                                break;
                              v161 = v160[1];
                              ++v160;
                            }
                            while ( v161 );
                          }
                          if ( *v160 )
                          {
                            *j++ = 0;
                            break;
                          }
                          ++j;
                        }
                        v17 = 0;
                        v9 = j;
                        if ( j != v159 )
                          v17 = v159;
                      }
                      else
                      {
                        v17 = 0;
                      }
                      goto LABEL_22;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    *((_WORD *)v10 - 1) = v11;
    v7 = -1073741275;
    v5 = 0;
    goto LABEL_41;
  }
  v5 = (char *)v12 - (char *)i;
  *((_WORD *)v10 - 1) = v11;
  v7 = 0;
LABEL_42:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v7 == -1073741275 )
  {
    v29 = 0;
    P = 0;
LABEL_314:
    v35 = 0;
    goto LABEL_60;
  }
  if ( v7 < 0 )
  {
    AslLogCallPrintf(1, "AslpFileMakeStringVersionAttributes", 2561, "AslpFileVerQueryBlock failed [%x]", v7);
    return (unsigned int)v7;
  }
  P = 0;
  v29 = 0;
  if ( v5 - 8 > 0x7FF7 )
    goto LABEL_314;
  v30 = i + 3;
  if ( i == (unsigned __int16 *)-6LL )
    goto LABEL_314;
  v31 = (v5 - 6) >> 1;
  if ( v31 > 0x7FFFFFFF )
    goto LABEL_314;
  if ( v31 )
  {
    while ( *v30 )
    {
      ++v30;
      if ( !--v31 )
        goto LABEL_52;
    }
    v32 = ((v5 - 6) >> 1) - v31;
    v33 = 0;
  }
  else
  {
LABEL_52:
    v32 = 0;
    v33 = -1073741811;
  }
  if ( v33 < 0 )
    goto LABEL_314;
  if ( 2 * v32 + 8 < 2 * v32 )
    goto LABEL_314;
  v34 = (2 * v32 + 11) & 0xFFFFFFFFFFFFFFFCuLL;
  if ( v34 >= v5 )
    goto LABEL_314;
  v29 = (unsigned __int16 *)((char *)i + v34);
  v35 = v5 - v34;
  P = (char *)i + v34;
LABEL_60:
  v36 = 0;
  v37 = v35 >> 2;
  v172 = (unsigned int)v37;
  while ( 1 )
  {
    v175 = v36;
    if ( v36 >= 8 )
      break;
    v38 = 2 * v36;
    v176[0] = 0;
    v39 = 0;
    v171 = 0;
    v40 = 0;
    v41 = (&off_18005BBF8)[v38];
    v167 = v41;
    v170 = dword_18005BBF0[2 * v38];
    while ( 1 )
    {
      if ( v40 >= 4 )
        goto LABEL_175;
      v42 = off_18005BAB0[v40];
      v43 = v176;
      v44 = 2147483646;
      v45 = 128;
      do
      {
        if ( !v44 )
          break;
        if ( !*v42 )
          break;
        *v43++ = *v42++;
        --v44;
        --v45;
      }
      while ( v45 );
      v46 = v43 - 1;
      v47 = -2147483643;
      if ( v45 )
      {
        v46 = v43;
        v47 = 0;
      }
      *v46 = 0;
      if ( !v45 )
      {
        v51 = "RtlStringCchCopyW failed [%x]";
        v50 = 3104;
        v52 = v47;
LABEL_141:
        LODWORD(v166) = v52;
        AslLogCallPrintf(1, "AslpFileQueryVersionString", v50, v51, v166);
        v84 = v47;
        if ( v47 != -1073741275 )
        {
LABEL_142:
          AslLogCallPrintf(
            1,
            "AslpFileMakeStringVersionAttributes",
            2616,
            "AslpFileQueryVersionString failed [%x]",
            v47);
          return v84;
        }
LABEL_238:
        v3 = v174;
        v174[8 * v170 + 6] |= 2u;
        goto LABEL_253;
      }
      v48 = 128;
      v49 = v176;
      while ( *v49 )
      {
        ++v49;
        if ( !--v48 )
        {
          v47 = -1073741811;
          goto LABEL_75;
        }
      }
      v53 = 2147483646;
      v54 = v41;
      v55 = (_WORD *)&v177 - v48;
      do
      {
        if ( !v53 )
          break;
        if ( !*v54 )
          break;
        *v55++ = *v54++;
        --v53;
        --v48;
      }
      while ( v48 );
      v56 = v55 - 1;
      v47 = -2147483643;
      if ( v48 )
      {
        v56 = v55;
        v47 = 0;
      }
      *v56 = 0;
      if ( !v48 )
      {
LABEL_75:
        v50 = 3110;
        v51 = "RtlStringCchCatW failed [%x]";
        v52 = v47;
        goto LABEL_141;
      }
      v57 = v173;
      k = v173;
      v169 = 0;
      if ( v173[2] )
      {
        v140 = "Version block invalid";
        v141 = 2787;
        goto LABEL_267;
      }
      v59 = AslStringDuplicate(&v169, v176);
      v47 = v59;
      if ( v59 < 0 )
      {
        AslLogCallPrintf(1, "AslpFileVerQueryBlock", 2793, "AslStringDuplicate failed [%x]", v59);
        goto LABEL_126;
      }
      v60 = *v57;
      if ( (unsigned __int16)v60 > 0x7FFFu )
      {
        v140 = "VersionBlock is too long";
        v141 = 2805;
LABEL_267:
        v47 = -1073741811;
        AslLogCallPrintf(1, "AslpFileVerQueryBlock", v141, v140);
LABEL_126:
        v82 = 0;
        goto LABEL_127;
      }
      if ( (unsigned int)v60 < 8 )
      {
        v140 = "VersionBlock not long enough";
        v141 = 2810;
        goto LABEL_267;
      }
      v61 = (const wchar_t *)v169;
      v62 = (char *)v57 + v60;
      v63 = *(unsigned __int16 *)((char *)v57 + v60 - 2);
      v64 = (unsigned __int16 *)v62;
      *((_WORD *)v62 - 1) = 0;
      if ( v61 )
      {
        for ( ; *v61; ++v61 )
        {
          v65 = L"\\";
          if ( pszSrc[0] )
          {
            v83 = pszSrc[0];
            while ( v83 != *v61 )
            {
              v83 = v65[1];
              ++v65;
              if ( !v83 )
                goto LABEL_91;
            }
          }
          if ( !*v65 )
            break;
        }
LABEL_91:
        v66 = v61;
        while ( *v61 )
        {
          v67 = L"\\";
          if ( pszSrc[0] )
          {
            v68 = pszSrc[0];
            do
            {
              if ( v68 == *v61 )
                break;
              v68 = v67[1];
              ++v67;
            }
            while ( v68 );
          }
          if ( *v67 )
          {
            *v61++ = 0;
            break;
          }
          ++v61;
        }
        v69 = 0;
        if ( v61 != v66 )
          v69 = v66;
      }
      else
      {
        v61 = 0;
        v69 = 0;
      }
LABEL_107:
      if ( v69 )
      {
        v71 = (unsigned int)((_DWORD)v62 - (_DWORD)k);
        if ( (unsigned int)v71 >= 8 )
        {
          v72 = *k;
          if ( (unsigned int)v72 <= (unsigned int)v71 && (unsigned int)v71 <= 0x7FFF )
          {
            v73 = k + 3;
            if ( k != (unsigned __int16 *)-6LL )
            {
              v74 = (unsigned __int64)(v71 - 6) >> 1;
              if ( v74 <= 0x7FFFFFFF )
              {
                v75 = v74;
                if ( v74 )
                {
                  while ( *v73 )
                  {
                    ++v73;
                    if ( !--v74 )
                      goto LABEL_116;
                  }
                  v76 = v75 - v74;
                  v77 = 0;
                }
                else
                {
LABEL_116:
                  v76 = 0;
                  v77 = -1073741811;
                }
                if ( v77 >= 0 )
                {
                  v78 = 2 * v76;
                  v79 = 2 * v76 + 8;
                  if ( v79 >= v78 )
                  {
                    v80 = ((k[1] + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + ((v79 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
                    if ( v80 <= v72 )
                    {
                      v64 = (unsigned __int16 *)((char *)k + v72);
                      for ( k = (unsigned __int16 *)((char *)k + v80);
                            k < v64;
                            k = (unsigned __int16 *)((char *)k + ((*k + 3LL) & 0xFFFFFFFFFFFFFFFCuLL)) )
                      {
                        v81 = *k;
                        if ( (unsigned int)v81 <= 8 || v81 > (char *)v64 - (char *)k )
                          break;
                        if ( !wcsicmp_0(v69, k + 3) )
                        {
                          if ( v61 )
                          {
                            for ( m = v61; *m; ++m )
                            {
                              v86 = L"\\";
                              if ( pszSrc[0] )
                              {
                                v90 = pszSrc[0];
                                while ( v90 != *m )
                                {
                                  v90 = v86[1];
                                  ++v86;
                                  if ( !v90 )
                                    goto LABEL_147;
                                }
                              }
                              if ( !*v86 )
                                break;
                            }
LABEL_147:
                            v87 = m;
                            while ( *m )
                            {
                              v88 = L"\\";
                              if ( pszSrc[0] )
                              {
                                v89 = pszSrc[0];
                                do
                                {
                                  if ( v89 == *m )
                                    break;
                                  v89 = v88[1];
                                  ++v88;
                                }
                                while ( v89 );
                              }
                              if ( *v88 )
                              {
                                *m++ = 0;
                                break;
                              }
                              ++m;
                            }
                            v69 = 0;
                            v61 = m;
                            if ( m != v87 )
                              v69 = v87;
                          }
                          else
                          {
                            v69 = 0;
                          }
                          goto LABEL_107;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
        v39 = v171;
        v47 = -1073741275;
        *((_WORD *)v62 - 1) = v63;
        goto LABEL_126;
      }
      v82 = (char *)v64 - (char *)k;
      v171 = k;
      v39 = k;
      *((_WORD *)v62 - 1) = v63;
      v47 = 0;
LABEL_127:
      if ( v169 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v169);
      if ( v47 >= 0 )
        break;
      if ( v47 != -1073741275 )
      {
        v165 = 3140;
LABEL_369:
        AslLogCallPrintf(1, "AslpFileQueryVersionString", v165, "AslpFileVerQueryBlock failed [%x]", v47);
        v84 = v47;
        goto LABEL_142;
      }
      v41 = v167;
      ++v40;
    }
    if ( v82 - 8 > 0x7FF7 )
      goto LABEL_174;
    v91 = v39 + 3;
    if ( v39 == (unsigned __int16 *)-6LL )
      goto LABEL_174;
    v92 = (v82 - 6) >> 1;
    if ( v92 > 0x7FFFFFFF )
      goto LABEL_174;
    if ( v92 )
    {
      while ( *v91 )
      {
        ++v91;
        if ( !--v92 )
          goto LABEL_168;
      }
      v93 = ((v82 - 6) >> 1) - v92;
      v94 = 0;
    }
    else
    {
LABEL_168:
      v93 = 0;
      v94 = -1073741811;
    }
    if ( v94 < 0 || 2 * v93 + 8 < 2 * v93 || (v134 = (2 * v93 + 11) & 0xFFFFFFFFFFFFFFFCuLL, v134 > v82) )
    {
LABEL_174:
      v41 = v167;
LABEL_175:
      if ( !P )
        goto LABEL_238;
      v95 = (unsigned __int16 *)P;
      while ( 2 )
      {
        if ( v4 >= v172 )
          goto LABEL_238;
        LODWORD(v166) = v95[1];
        v52 = RtlStringCchPrintfW(v176, 128, L"\\StringFileInfo\\%04X%04X\\%s", *v95, v166, v41);
        v47 = v52;
        if ( v52 < 0 )
        {
          v51 = "RtlStringCchPrintfW failed [%x]";
          v50 = 3158;
          goto LABEL_141;
        }
        v96 = v173;
        n = v173;
        v169 = 0;
        if ( v173[2] )
        {
          v153 = "Version block invalid";
          v154 = 2787;
        }
        else
        {
          v98 = AslStringDuplicate(&v169, v176);
          v47 = v98;
          if ( v98 < 0 )
          {
            AslLogCallPrintf(1, "AslpFileVerQueryBlock", 2793, "AslStringDuplicate failed [%x]", v98);
            goto LABEL_222;
          }
          v99 = *v96;
          if ( (unsigned __int16)v99 > 0x7FFFu )
          {
            v153 = "VersionBlock is too long";
            v154 = 2805;
          }
          else
          {
            if ( (unsigned int)v99 >= 8 )
            {
              v100 = *(unsigned __int16 *)((char *)v96 + v99 - 2);
              v101 = (char *)v96 + v99;
              v102 = (const wchar_t *)v169;
              v103 = 0;
              *((_WORD *)v101 - 1) = 0;
              v104 = (unsigned __int16 *)v101;
              if ( v102 )
              {
                for ( ; *v102; ++v102 )
                {
                  v105 = L"\\";
                  if ( pszSrc[0] )
                  {
                    v133 = pszSrc[0];
                    while ( v133 != *v102 )
                    {
                      v133 = v105[1];
                      ++v105;
                      if ( !v133 )
                        goto LABEL_187;
                    }
                  }
                  if ( !*v105 )
                    break;
                }
LABEL_187:
                v106 = v102;
                while ( *v102 )
                {
                  v107 = L"\\";
                  if ( pszSrc[0] )
                  {
                    v108 = pszSrc[0];
                    do
                    {
                      if ( v108 == *v102 )
                        break;
                      v108 = v107[1];
                      ++v107;
                    }
                    while ( v108 );
                  }
                  if ( *v107 )
                  {
                    *v102++ = 0;
                    break;
                  }
                  ++v102;
                }
                if ( v102 != v106 )
                  v103 = v106;
              }
              else
              {
                v102 = 0;
              }
LABEL_203:
              if ( v103 )
              {
                v110 = (unsigned int)((_DWORD)v101 - (_DWORD)n);
                if ( (unsigned int)v110 >= 8 )
                {
                  v111 = *n;
                  if ( (unsigned int)v111 <= (unsigned int)v110 && (unsigned int)v110 <= 0x7FFF )
                  {
                    v112 = n + 3;
                    if ( n != (unsigned __int16 *)-6LL )
                    {
                      v113 = (unsigned __int64)(v110 - 6) >> 1;
                      if ( v113 <= 0x7FFFFFFF )
                      {
                        v114 = v113;
                        if ( v113 )
                        {
                          while ( *v112 )
                          {
                            ++v112;
                            if ( !--v113 )
                              goto LABEL_212;
                          }
                          v115 = v114 - v113;
                          v116 = 0;
                        }
                        else
                        {
LABEL_212:
                          v115 = 0;
                          v116 = -1073741811;
                        }
                        if ( v116 >= 0 )
                        {
                          v117 = 2 * v115;
                          v118 = 2 * v115 + 8;
                          if ( v118 >= v117 )
                          {
                            v119 = ((n[1] + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + ((v118 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
                            if ( v119 <= v111 )
                            {
                              v104 = (unsigned __int16 *)((char *)n + v111);
                              for ( n = (unsigned __int16 *)((char *)n + v119);
                                    n < v104;
                                    n = (unsigned __int16 *)((char *)n + ((*n + 3LL) & 0xFFFFFFFFFFFFFFFCuLL)) )
                              {
                                v120 = *n;
                                if ( (unsigned int)v120 <= 8 || v120 > (char *)v104 - (char *)n )
                                  break;
                                if ( !wcsicmp_0(v103, n + 3) )
                                {
                                  if ( v102 )
                                  {
                                    for ( ii = v102; *ii; ++ii )
                                    {
                                      v148 = L"\\";
                                      if ( pszSrc[0] )
                                      {
                                        v152 = pszSrc[0];
                                        while ( v152 != *ii )
                                        {
                                          v152 = v148[1];
                                          ++v148;
                                          if ( !v152 )
                                            goto LABEL_286;
                                        }
                                      }
                                      if ( !*v148 )
                                        break;
                                    }
LABEL_286:
                                    v149 = ii;
                                    while ( *ii )
                                    {
                                      v150 = L"\\";
                                      if ( pszSrc[0] )
                                      {
                                        v151 = pszSrc[0];
                                        do
                                        {
                                          if ( v151 == *ii )
                                            break;
                                          v151 = v150[1];
                                          ++v150;
                                        }
                                        while ( v151 );
                                      }
                                      if ( *v150 )
                                      {
                                        *ii++ = 0;
                                        break;
                                      }
                                      ++ii;
                                    }
                                    v103 = 0;
                                    v102 = ii;
                                    if ( ii != v149 )
                                      v103 = v149;
                                  }
                                  else
                                  {
                                    v103 = 0;
                                  }
                                  goto LABEL_203;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
                *((_WORD *)v101 - 1) = v100;
                v47 = -1073741275;
LABEL_222:
                v121 = v171;
                v122 = 0;
              }
              else
              {
                v122 = (char *)v104 - (char *)n;
                v171 = n;
                v47 = 0;
                *((_WORD *)v101 - 1) = v100;
                v121 = n;
              }
              if ( v169 )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v169);
              if ( v47 >= 0 )
              {
                if ( v122 - 8 > 0x7FF7 )
                  goto LABEL_238;
                v123 = v121 + 3;
                if ( v121 == (unsigned __int16 *)-6LL )
                  goto LABEL_238;
                v124 = (v122 - 6) >> 1;
                if ( v124 > 0x7FFFFFFF )
                  goto LABEL_238;
                if ( v124 )
                {
                  while ( *v123 )
                  {
                    ++v123;
                    if ( !--v124 )
                      goto LABEL_232;
                  }
                  v126 = ((v122 - 6) >> 1) - v124;
                  v125 = 0;
                }
                else
                {
LABEL_232:
                  v125 = -1073741811;
                  v126 = 0;
                }
                if ( v125 < 0 )
                  goto LABEL_238;
                if ( 2 * v126 + 8 < 2 * v126 )
                  goto LABEL_238;
                v142 = (2 * v126 + 11) & 0xFFFFFFFFFFFFFFFCuLL;
                if ( v142 > v122 )
                  goto LABEL_238;
                v135 = (unsigned __int16 *)((char *)v121 + v142);
                if ( v142 == v122 )
                {
                  --v135;
                }
                else
                {
                  v143 = v122 - v142;
                  if ( !v135 )
                    goto LABEL_279;
                  v144 = v143 >> 1;
                  if ( v143 >> 1 > 0x7FFFFFFF )
                    goto LABEL_279;
                  v145 = (unsigned __int16 *)((char *)v121 + v142);
                  v146 = 0;
                  if ( v144 )
                  {
                    while ( *v145 )
                    {
                      ++v145;
                      if ( !--v144 )
                        goto LABEL_277;
                    }
                  }
                  else
                  {
LABEL_277:
                    v146 = -1073741811;
                  }
                  if ( v146 < 0 )
                  {
LABEL_279:
                    v147 = v143 - 2;
                    goto LABEL_281;
                  }
                }
                goto LABEL_240;
              }
              if ( v47 != -1073741275 )
              {
                v165 = 3188;
                goto LABEL_369;
              }
              v41 = v167;
              ++v4;
              v95 += 2;
              continue;
            }
            v153 = "VersionBlock not long enough";
            v154 = 2810;
          }
        }
        break;
      }
      v47 = -1073741811;
      AslLogCallPrintf(1, "AslpFileVerQueryBlock", v154, v153);
      goto LABEL_222;
    }
    v135 = (unsigned __int16 *)((char *)v39 + v134);
    if ( v134 == v82 )
    {
      --v135;
    }
    else
    {
      v136 = v82 - v134;
      if ( !v135 )
        goto LABEL_280;
      v137 = v136 >> 1;
      if ( v136 >> 1 > 0x7FFFFFFF )
        goto LABEL_280;
      v138 = (unsigned __int16 *)((char *)v39 + v134);
      v139 = 0;
      if ( v137 )
      {
        while ( *v138 )
        {
          ++v138;
          if ( !--v137 )
            goto LABEL_265;
        }
      }
      else
      {
LABEL_265:
        v139 = -1073741811;
      }
      if ( v139 < 0 )
      {
LABEL_280:
        v147 = v136 - 2;
LABEL_281:
        v135[v147 >> 1] = 0;
      }
    }
LABEL_240:
    if ( !v135 )
    {
      AslLogCallPrintf(1, "AslpFileMakeStringVersionAttributes", 2603, "AslStringXmlSanitize failed [%x]", -1073741811);
      return 3221225485LL;
    }
    if ( *v135 )
    {
      v127 = -1;
      do
        ++v127;
      while ( v135[v127] );
      for ( jj = 0; jj < v127; ++jj )
      {
        for ( kk = 0; kk < 5; ++kk )
        {
          v130 = v135[jj];
          if ( v130 >= *(_WORD *)&asc_180060420[4 * kk] && v130 <= (unsigned __int16)word_180060422[2 * kk] )
            goto LABEL_249;
        }
        v135[jj] = 64;
LABEL_249:
        ;
      }
    }
    v131 = -1;
    v3 = v174;
    v132 = &v174[8 * v170];
    *v132 = 4;
    do
      ++v131;
    while ( v135[v131] );
    v132[6] |= 1u;
    *((_QWORD *)v132 + 1) = v131;
    *((_QWORD *)v132 + 2) = v135;
LABEL_253:
    v29 = (unsigned __int16 *)P;
    v36 = v175 + 1;
    v37 = v172;
    v4 = 0;
  }
  if ( v29 && v37 == 1 )
  {
    v3[192] = 2;
    *((_QWORD *)v3 + 97) = 4;
    v156 = *v29;
    v3[198] |= 1u;
    *((_QWORD *)v3 + 98) = v156;
  }
  else
  {
    v3[198] |= 2u;
  }
  return 0;
}

```

## disassembly

```asm
0x180014550  mov     r11, rsp
0x180014553  push    rdi
0x180014554  push    r12
0x180014556  sub     rsp, 1B8h
0x18001455d  mov     rax, cs:__security_cookie
0x180014564  xor     rax, rsp
0x180014567  mov     [rsp+1C8h+var_48], rax
0x18001456f  mov     [rsp+1C8h+var_168], rdx
0x180014574  mov     rdi, rdx
0x180014577  mov     [rsp+1C8h+var_160], rcx
0x18001457c  mov     r12, rcx
0x18001457f  test    rdx, rdx
0x180014582  jz      loc_180015492
0x180014588  mov     [r11+18h], rbx
0x18001458c  mov     [r11-18h], rbp
0x180014590  mov     [r11-20h], rsi
0x180014594  mov     esi, 7FFFh
0x180014599  mov     [r11-28h], r13
0x18001459d  xor     r13d, r13d
0x1800145a0  mov     ebp, r13d
0x1800145a3  mov     [r11-30h], r14
0x1800145a7  mov     [r11-38h], r15
0x1800145ab  mov     [rsp+1C8h+var_170], rdx
0x1800145b0  mov     [rsp+1C8h+P], r13
0x1800145b5  cmp     [rdx+4], bp
0x1800145b9  jnz     loc_18001559E
0x1800145bf  lea     rdx, aVarfileinfoTra; "\\VarFileInfo\\Translation"
0x1800145c6  lea     rcx, [rsp+1C8h+P]
0x1800145cb  call    AslStringDuplicate
0x1800145d0  mov     ebx, eax
0x1800145d2  test    eax, eax
0x1800145d4  js      loc_180015613
0x1800145da  movzx   eax, word ptr [rdi]
0x1800145dd  cmp     ax, si
0x1800145e0  ja      loc_18001563A
0x1800145e6  cmp     eax, 8
0x1800145e9  jb      loc_18001564C
0x1800145ef  mov     rbx, [rsp+1C8h+P]
0x1800145f4  lea     r14, [rdi+rax]
0x1800145f8  movzx   r15d, word ptr [r14-2]
0x1800145fd  mov     rbp, r14
0x180014600  mov     [r14-2], r13w
0x180014605  test    rbx, rbx
0x180014608  jz      loc_18001565E
0x18001460e  mov     eax, dword ptr cs:pszSrc; "\\"
0x180014614  cmp     [rbx], r13w
0x180014618  jz      short loc_180014634
0x18001461a  lea     rcx, pszSrc; "\\"
0x180014621  test    ax, ax
0x180014624  jnz     loc_180015427
0x18001462a  cmp     [rcx], r13w
0x18001462e  jnz     loc_18001547F
0x180014634  mov     r9, rbx
0x180014637  nop     word ptr [rax+rax+00000000h]
0x180014640  movzx   r8d, word ptr [rbx]
0x180014644  test    r8w, r8w
0x180014648  jz      short loc_180014682
0x18001464a  lea     rcx, pszSrc; "\\"
0x180014651  test    ax, ax
0x180014654  jnz     short loc_180014662
0x180014656  cmp     [rcx], r13w
0x18001465a  jnz     short loc_18001467A
0x18001465c  add     rbx, 2
0x180014660  jmp     short loc_180014640
0x180014662  movzx   edx, ax
0x180014665  cmp     dx, r8w
0x180014669  jz      short loc_180014656
0x18001466b  movzx   edx, word ptr [rcx+2]
0x18001466f  add     rcx, 2
0x180014673  test    dx, dx
0x180014676  jnz     short loc_180014665
0x180014678  jmp     short loc_180014656
0x18001467a  mov     [rbx], r13w
0x18001467e  add     rbx, 2
0x180014682  cmp     rbx, r9
0x180014685  mov     rsi, r13
0x180014688  cmovnz  rsi, r9
0x18001468c  test    rsi, rsi
0x18001468f  jz      loc_18001558E
0x180014695  mov     ecx, r14d
0x180014698  sub     ecx, edi
0x18001469a  cmp     ecx, 8
0x18001469d  jb      loc_180014751
0x1800146a3  movzx   r8d, word ptr [rdi]
0x1800146a7  cmp     r8d, ecx
0x1800146aa  ja      loc_180014751
0x1800146b0  cmp     ecx, 7FFFh
0x1800146b6  ja      loc_180014751
0x1800146bc  lea     rax, [rdi+6]
0x1800146c0  test    rax, rax
0x1800146c3  jz      loc_180014751
0x1800146c9  sub     rcx, 6
0x1800146cd  shr     rcx, 1
0x1800146d0  cmp     rcx, 7FFFFFFFh
0x1800146d7  ja      short loc_180014751
0x1800146d9  mov     rdx, rcx
0x1800146dc  test    rcx, rcx
0x1800146df  jz      short loc_1800146F1
0x1800146e1  cmp     [rax], r13w
0x1800146e5  jz      short loc_1800146FB
0x1800146e7  add     rax, 2
0x1800146eb  sub     rcx, 1
0x1800146ef  jnz     short loc_1800146E1
0x1800146f1  mov     rdx, r13
0x1800146f4  mov     eax, 0C000000Dh
0x1800146f9  jmp     short loc_180014701
0x1800146fb  sub     rdx, rcx
0x1800146fe  mov     eax, r13d
0x180014701  test    eax, eax
0x180014703  js      short loc_180014751
0x180014705  lea     rax, [rdx+rdx]
0x180014709  lea     rdx, [rax+8]
0x18001470d  cmp     rdx, rax
0x180014710  jb      short loc_180014751
0x180014712  movzx   ecx, word ptr [rdi+2]
0x180014716  add     rdx, 3
0x18001471a  add     rcx, 3
0x18001471e  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180014722  and     rcx, 0FFFFFFFFFFFFFFFCh
0x180014726  add     rdx, rcx
0x180014729  cmp     rdx, r8
0x18001472c  ja      short loc_180014751
0x18001472e  lea     rbp, [r8+rdi]
0x180014732  add     rdi, rdx
0x180014735  cmp     rdi, rbp
0x180014738  jnb     short loc_180014751
0x18001473a  movzx   eax, word ptr [rdi]
0x18001473d  cmp     eax, 8
0x180014740  jbe     short loc_180014751
0x180014742  mov     rcx, rbp
0x180014745  sub     rcx, rdi
0x180014748  cmp     rax, rcx
0x18001474b  jbe     loc_1800147EE
0x180014751  mov     [r14-2], r15w
0x180014756  mov     ebx, 0C0000225h
0x18001475b  mov     rbp, r13
0x18001475e  mov     rdi, r13
0x180014761  mov     r8, [rsp+1C8h+P]; P
0x180014766  test    r8, r8
0x180014769  jz      short loc_180014780
0x18001476b  mov     rcx, gs:60h
0x180014774  xor     edx, edx; Flags
0x180014776  mov     rcx, [rcx+30h]; HeapHandle
0x18001477a  call    cs:__imp_RtlFreeHeap
0x180014780  cmp     ebx, 0C0000225h
0x180014786  jz      loc_180015417
0x18001478c  test    ebx, ebx
0x18001478e  js      loc_1800155D8
0x180014794  lea     rax, [rbp-8]
0x180014798  mov     [rsp+1C8h+P], r13
0x18001479d  mov     rsi, r13
0x1800147a0  cmp     rax, 7FF7h
0x1800147a6  ja      loc_18001541F
0x1800147ac  lea     rax, [rdi+6]
0x1800147b0  test    rax, rax
0x1800147b3  jz      loc_18001541F
0x1800147b9  lea     rcx, [rbp-6]
0x1800147bd  shr     rcx, 1
0x1800147c0  cmp     rcx, 7FFFFFFFh
0x1800147c7  ja      loc_18001541F
0x1800147cd  mov     rdx, rcx
0x1800147d0  test    rcx, rcx
0x1800147d3  jz      short loc_1800147E4
0x1800147d5  cmp     [rax], si
0x1800147d8  jz      short loc_180014815
0x1800147da  add     rax, 2
0x1800147de  sub     rcx, 1
0x1800147e2  jnz     short loc_1800147D5
0x1800147e4  mov     rdx, r13
0x1800147e7  mov     eax, 0C000000Dh
0x1800147ec  jmp     short loc_18001481B
0x1800147ee  lea     rdx, [rdi+6]; String2
0x1800147f2  mov     rcx, rsi; String1
0x1800147f5  call    _wcsicmp_0
0x1800147fa  test    eax, eax
0x1800147fc  jz      loc_1800154D8
0x180014802  movzx   eax, word ptr [rdi]
0x180014805  add     rax, 3
0x180014809  and     rax, 0FFFFFFFFFFFFFFFCh
0x18001480d  add     rdi, rax
0x180014810  jmp     loc_180014735
0x180014815  sub     rdx, rcx
0x180014818  mov     eax, r13d
0x18001481b  test    eax, eax
0x18001481d  js      loc_18001541F
0x180014823  lea     rax, [rdx+rdx]
0x180014827  lea     rcx, [rax+8]
0x18001482b  cmp     rcx, rax
0x18001482e  jb      loc_18001541F
0x180014834  lea     rax, [rcx+3]
0x180014838  and     rax, 0FFFFFFFFFFFFFFFCh
0x18001483c  cmp     rax, rbp
0x18001483f  jnb     loc_18001541F
0x180014845  lea     rsi, [rax+rdi]
0x180014849  sub     rbp, rax
0x18001484c  mov     [rsp+1C8h+P], rsi
0x180014851  shr     rbp, 2
0x180014855  mov     rax, r13
0x180014858  and     ebp, 3FFFFFFFh
0x18001485e  mov     [rsp+1C8h+var_170], rbp
0x180014863  mov     [rsp+1C8h+var_158], rax
0x180014868  lea     rdx, __ImageBase
0x18001486f  cmp     rax, 8
0x180014873  jnb     loc_1800153B7
0x180014879  add     rax, rax
0x18001487c  mov     [rsp+1C8h+var_148], r13w
0x180014885  mov     rdi, r13
0x180014888  mov     [rsp+1C8h+var_178], r13
0x18001488d  mov     r12, r13
0x180014890  mov     r10, ds:rva off_18005BBF8[rdx+rax*8]; "ProductVersion" ...
0x180014898  mov     ecx, ds:rva dword_18005BBF0[rdx+rax*8]
0x18001489f  mov     [rsp+1C8h+var_198], r10
0x1800148a4  mov     [rsp+1C8h+var_180], ecx
0x1800148a8  cmp     r12, 4
0x1800148ac  jnb     loc_180014D9A
0x1800148b2  mov     rdx, ds:rva off_18005BAB0[rdx+r12*8]; "\\StringFileInfo\\000004B0\\" ...
0x1800148ba  lea     r9, [rsp+1C8h+var_148]
0x1800148c2  mov     ecx, 7FFFFFFEh
0x1800148c7  mov     r8d, 80h
0x1800148cd  nop     dword ptr [rax]
0x1800148d0  test    rcx, rcx
0x1800148d3  jz      short loc_1800148F2
0x1800148d5  movzx   eax, word ptr [rdx]
0x1800148d8  test    ax, ax
0x1800148db  jz      short loc_1800148F2
0x1800148dd  mov     [r9], ax
0x1800148e1  add     rdx, 2
0x1800148e5  add     r9, 2
0x1800148e9  dec     rcx
0x1800148ec  sub     r8, 1
0x1800148f0  jnz     short loc_1800148D0
0x1800148f2  test    r8, r8
0x1800148f5  lea     rax, [r9-2]
0x1800148f9  mov     ebx, 80000005h
0x1800148fe  cmovnz  rax, r9
0x180014902  cmovnz  ebx, r13d
0x180014906  mov     [rax], r13w
0x18001490a  jz      loc_180014C17
0x180014910  mov     ecx, 80h
0x180014915  lea     rax, [rsp+1C8h+var_148]
0x18001491d  nop     dword ptr [rax]
0x180014920  cmp     word ptr [rax], 0
0x180014924  jz      short loc_180014949
0x180014926  add     rax, 2
0x18001492a  sub     rcx, 1
0x18001492e  jnz     short loc_180014920
0x180014930  mov     ebx, 0C000000Dh
0x180014935  mov     r8d, 0C26h
0x18001493b  lea     r9, aRtlstringcchca; "RtlStringCchCatW failed [%x]"
0x180014942  mov     eax, ebx
0x180014944  jmp     loc_180014C26
0x180014949  lea     rax, [rcx+rcx]
0x18001494d  mov     edx, 7FFFFFFEh
0x180014952  lea     r9, [rsp+1C8h+var_48]
0x18001495a  mov     r8, r10
0x18001495d  sub     r9, rax
0x180014960  test    rcx, rcx
0x180014963  jz      short loc_180014988
0x180014965  test    rdx, rdx
0x180014968  jz      short loc_180014988
0x18001496a  movzx   eax, word ptr [r8]
0x18001496e  test    ax, ax
0x180014971  jz      short loc_180014988
0x180014973  mov     [r9], ax
0x180014977  add     r8, 2
0x18001497b  add     r9, 2
0x18001497f  dec     rdx
0x180014982  sub     rcx, 1
0x180014986  jnz     short loc_180014965
0x180014988  test    rcx, rcx
0x18001498b  lea     rax, [r9-2]
0x18001498f  mov     ebx, 80000005h
0x180014994  cmovnz  rax, r9
0x180014998  cmovnz  ebx, r13d
0x18001499c  mov     [rax], r13w
0x1800149a0  jz      short loc_180014935
0x1800149a2  mov     rsi, [rsp+1C8h+var_168]
0x1800149a7  mov     r14, rsi
0x1800149aa  mov     [rsp+1C8h+var_188], r13
0x1800149af  cmp     word ptr [rsi+4], 0
0x1800149b4  jnz     loc_1800151EF
0x1800149ba  lea     rdx, [rsp+1C8h+var_148]
0x1800149c2  lea     rcx, [rsp+1C8h+var_188]
0x1800149c7  call    AslStringDuplicate
0x1800149cc  mov     ebx, eax
0x1800149ce  test    eax, eax
0x1800149d0  js      loc_180015669
0x1800149d6  movzx   eax, word ptr [rsi]
0x1800149d9  mov     edx, 7FFFh
0x1800149de  cmp     ax, dx
0x1800149e1  ja      loc_180015690
0x1800149e7  cmp     eax, 8
0x1800149ea  jb      loc_1800156A2
0x1800149f0  mov     rdi, [rsp+1C8h+var_188]
0x1800149f5  lea     rbp, [rsi+rax]
0x1800149f9  movzx   r15d, word ptr [rbp-2]
0x1800149fe  mov     rsi, rbp
0x180014a01  mov     [rbp-2], r13w
0x180014a06  test    rdi, rdi
0x180014a09  jz      loc_1800156B4
  ... truncated ...
```
