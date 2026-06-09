# AslpFileMakeStringVersionAttributes

- ea: `0x14003c980`
- end: `0x14003d80e`
- name: `AslpFileMakeStringVersionAttributes`
- size: `3726`
- prototype: `__int64 __fastcall(_DWORD *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140025b04`

## callees

- `0x140001ec4`
- `0x14000436d`
- `0x1400044f9`
- `0x1400079f0`
- `0x14003c980`
- `0x14003e364`
- `0x14003e3a0`
- `0x14003e76c`

## string_xrefs

- `0x14003ccf1`: `RtlStringCchCopyW failed [%x]`
- `0x14003d7de`: `AslStringXmlSanitize failed [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileMakeStringVersionAttributes(_DWORD *a1, unsigned __int16 *a2)
{
  unsigned __int16 *i; // rsi
  unsigned __int64 v3; // r13
  const wchar_t *v4; // rdi
  int v5; // eax
  int v6; // ebx
  __int64 v7; // rax
  __int16 v8; // r12
  char *v9; // r15
  unsigned __int16 *v10; // r14
  const wchar_t *v11; // rbx
  const wchar_t *v12; // rcx
  const wchar_t *v13; // r9
  const wchar_t *v14; // rcx
  wchar_t v15; // dx
  __int64 v16; // rcx
  unsigned __int64 v17; // r8
  _WORD *v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  unsigned __int16 *v25; // r15
  _WORD *v26; // rax
  unsigned __int64 v27; // rcx
  unsigned __int64 v28; // rdx
  unsigned __int64 v29; // rax
  unsigned int v30; // edi
  unsigned __int64 v31; // r14
  unsigned __int16 *v32; // rsi
  unsigned __int64 v33; // rdi
  wchar_t *v34; // r10
  wchar_t *v35; // rdx
  wchar_t *v36; // r9
  __int64 v37; // rcx
  __int64 v38; // r8
  wchar_t *v39; // rax
  int v40; // ebx
  const char *v41; // r9
  __int64 v42; // r8
  NTSTATUS v43; // eax
  unsigned int v44; // edi
  wchar_t v45; // dx
  __int64 v46; // rcx
  wchar_t *v47; // rax
  __int64 v48; // rdx
  wchar_t *v49; // r8
  _WORD *v50; // r9
  _WORD *v51; // rax
  unsigned __int16 *v52; // r12
  unsigned __int16 *k; // r15
  int v54; // eax
  __int64 v55; // rax
  char *v56; // r14
  __int16 v57; // r12
  unsigned __int16 *v58; // rsi
  const wchar_t *v59; // rdi
  const wchar_t *v60; // rcx
  const wchar_t *v61; // r9
  const wchar_t *v62; // rdx
  wchar_t v63; // cx
  const wchar_t *v64; // rbx
  unsigned int v65; // ecx
  unsigned __int64 v66; // r8
  _WORD *v67; // rax
  unsigned __int64 v68; // rdx
  unsigned __int64 v69; // rcx
  unsigned __int64 v70; // rcx
  unsigned __int64 v71; // rdx
  wchar_t v72; // dx
  _WORD *v73; // rax
  unsigned __int64 v74; // rcx
  unsigned __int64 v75; // rdx
  unsigned __int16 *v76; // r12
  unsigned __int16 *v77; // rdi
  unsigned __int64 n; // rsi
  _WORD *v79; // rcx
  unsigned __int64 v80; // rax
  unsigned __int64 v81; // rdx
  unsigned __int64 v82; // rax
  const wchar_t *m; // r9
  const wchar_t *v84; // rdx
  const wchar_t *v85; // r10
  const wchar_t *v86; // rcx
  wchar_t v87; // dx
  wchar_t v88; // cx
  const char *v89; // r9
  __int64 v90; // r8
  unsigned __int64 v91; // rax
  _WORD *v92; // rcx
  unsigned __int64 v93; // r13
  unsigned __int64 v94; // rdx
  _WORD *v95; // rax
  unsigned __int64 v96; // rax
  unsigned __int64 v97; // rax
  unsigned __int64 ii; // rdx
  unsigned __int64 jj; // r9
  unsigned __int16 v100; // r8
  _DWORD *v101; // rdx
  __int64 v102; // rax
  _DWORD *v103; // rcx
  __int64 v104; // rax
  unsigned __int64 v106; // rax
  const wchar_t *j; // rcx
  const wchar_t *v108; // rdx
  const wchar_t *v109; // r10
  const wchar_t *v110; // rdx
  wchar_t v111; // r9
  wchar_t v112; // r8
  unsigned __int64 v113; // rax
  unsigned __int64 v114; // r8
  unsigned __int64 v115; // rdx
  _WORD *v116; // rax
  const char *v117; // r9
  __int64 v118; // r8
  __int64 v119; // r8
  __int64 v120; // [rsp+28h] [rbp-E0h]
  wchar_t *v121; // [rsp+38h] [rbp-D0h]
  int v122; // [rsp+40h] [rbp-C8h]
  unsigned __int64 v123; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int16 *v124; // [rsp+50h] [rbp-B8h] BYREF
  unsigned __int16 *v125; // [rsp+58h] [rbp-B0h]
  _DWORD *v126; // [rsp+60h] [rbp-A8h]
  PVOID P; // [rsp+68h] [rbp-A0h] BYREF
  PVOID v128; // [rsp+70h] [rbp-98h] BYREF
  unsigned __int64 v129; // [rsp+78h] [rbp-90h]
  unsigned __int64 v130; // [rsp+80h] [rbp-88h]
  unsigned __int16 *v131; // [rsp+88h] [rbp-80h]
  __int64 v132; // [rsp+90h] [rbp-78h]
  wchar_t pszDest[128]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v134; // [rsp+198h] [rbp+90h] BYREF

  v131 = a2;
  i = a2;
  v126 = a1;
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
  v3 = 0;
  v4 = 0;
  v130 = (unsigned __int64)a2;
  P = 0;
  if ( a2[2] )
  {
    v117 = "Version block invalid";
    v118 = 2787;
LABEL_268:
    v6 = -1073741811;
    AslLogCallPrintf(1, "AslpFileVerQueryBlock", v118, v117);
    i = 0;
    goto LABEL_40;
  }
  v5 = AslStringDuplicate(&P, L"\\VarFileInfo\\Translation");
  v6 = v5;
  if ( v5 < 0 )
  {
    AslLogCallPrintf(1, "AslpFileVerQueryBlock", 2793, "AslStringDuplicate failed [%x]", v5);
    i = 0;
    goto LABEL_40;
  }
  v7 = *i;
  if ( (unsigned __int16)v7 > 0x7FFFu )
  {
    v117 = "VersionBlock is too long";
    v118 = 2805;
    goto LABEL_268;
  }
  if ( (unsigned int)v7 < 8 )
  {
    v117 = "VersionBlock not long enough";
    v118 = 2810;
    goto LABEL_268;
  }
  v8 = *(unsigned __int16 *)((char *)i + v7 - 2);
  v9 = (char *)i + v7;
  *(unsigned __int16 *)((char *)i + v7 - 2) = 0;
  v10 = (unsigned __int16 *)((char *)i + v7);
  v11 = (const wchar_t *)P;
  if ( P )
  {
    if ( *(_WORD *)P )
    {
      do
      {
        v12 = L"\\";
        if ( asc_14000AF88[0] )
        {
          v45 = asc_14000AF88[0];
          while ( v45 != *v11 )
          {
            v45 = v12[1];
            ++v12;
            if ( !v45 )
              goto LABEL_10;
          }
        }
        if ( !*v12 )
          break;
        ++v11;
      }
      while ( *v11 );
    }
LABEL_10:
    v13 = v11;
    while ( *v11 )
    {
      v14 = L"\\";
      if ( asc_14000AF88[0] )
      {
        v15 = asc_14000AF88[0];
        do
        {
          if ( v15 == *v11 )
            break;
          v15 = v14[1];
          ++v14;
        }
        while ( v15 );
      }
      if ( *v14 )
      {
        *v11++ = 0;
        break;
      }
      ++v11;
    }
    if ( v11 != v13 )
      v4 = v13;
  }
  else
  {
    v11 = 0;
  }
LABEL_22:
  if ( v4 )
  {
    v16 = (unsigned int)((_DWORD)v9 - (_DWORD)i);
    if ( (unsigned int)v16 >= 8 )
    {
      v17 = *i;
      if ( (unsigned int)v17 <= (unsigned int)v16 && (unsigned int)v16 <= 0x7FFF )
      {
        v18 = i + 3;
        if ( i != (unsigned __int16 *)-6LL )
        {
          v19 = (unsigned __int64)(v16 - 6) >> 1;
          if ( v19 <= 0x7FFFFFFF )
          {
            v20 = v19;
            if ( v19 )
            {
              while ( *v18 )
              {
                ++v18;
                if ( !--v19 )
                  goto LABEL_31;
              }
              v21 = v20 - v19;
            }
            else
            {
LABEL_31:
              v21 = 0;
            }
            if ( v19 )
            {
              v22 = 2 * v21;
              v23 = 2 * v21 + 8;
              if ( v23 >= v22 )
              {
                v24 = ((i[1] + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + ((v23 + 3) & 0xFFFFFFFFFFFFFFFCuLL);
                if ( v24 <= v17 )
                {
                  v10 = (unsigned __int16 *)((char *)i + v17);
                  for ( i = (unsigned __int16 *)((char *)i + v24);
                        i < v10;
                        i = (unsigned __int16 *)((char *)i + ((*i + 3LL) & 0xFFFFFFFFFFFFFFFCuLL)) )
                  {
                    v106 = *i;
                    if ( (unsigned int)v106 <= 8 || v106 > (char *)v10 - (char *)i )
                      break;
                    if ( !wcsicmp_0(v4, i + 3) )
                    {
                      if ( v11 )
                      {
                        for ( j = v11; *j; ++j )
                        {
                          v108 = L"\\";
                          if ( asc_14000AF88[0] )
                          {
                            v112 = asc_14000AF88[0];
                            while ( v112 != *j )
                            {
                              v112 = v108[1];
                              ++v108;
                              if ( !v112 )
                                goto LABEL_238;
                            }
                          }
                          if ( !*v108 )
                            break;
                        }
LABEL_238:
                        v109 = j;
                        while ( *j )
                        {
                          v110 = L"\\";
                          if ( asc_14000AF88[0] )
                          {
                            v111 = asc_14000AF88[0];
                            do
                            {
                              if ( v111 == *j )
                                break;
                              v111 = v110[1];
                              ++v110;
                            }
                            while ( v111 );
                          }
                          if ( *v110 )
                          {
                            *j++ = 0;
                            break;
                          }
                          ++j;
                        }
                        v4 = 0;
                        v11 = j;
                        if ( j != v109 )
                          v4 = v109;
                      }
                      else
                      {
                        v4 = 0;
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
    *((_WORD *)v9 - 1) = v8;
    v6 = -1073741275;
    v4 = 0;
    i = 0;
  }
  else
  {
    *((_WORD *)v9 - 1) = v8;
    v4 = (const wchar_t *)((char *)v10 - (char *)i);
    v6 = 0;
  }
LABEL_40:
  if ( P )
    ExFreePoolWithTag_0(P, 0x74705041u);
  if ( v6 == -1073741275 )
  {
    v25 = 0;
    v125 = 0;
  }
  else
  {
    if ( v6 < 0 )
    {
      AslLogCallPrintf(1, "AslpFileMakeStringVersionAttributes", 2561, "AslpFileVerQueryBlock failed [%x]", v6);
      return (unsigned int)v6;
    }
    v125 = 0;
    v25 = 0;
    if ( (unsigned __int64)(v4 - 4) <= 0x7FF7 )
    {
      v26 = i + 3;
      if ( i != (unsigned __int16 *)-6LL )
      {
        v27 = (unsigned __int64)(v4 - 3) >> 1;
        if ( v27 <= 0x7FFFFFFF )
        {
          if ( v27 )
          {
            while ( *v26 )
            {
              ++v26;
              if ( !--v27 )
                goto LABEL_50;
            }
            v28 = ((unsigned __int64)(v4 - 3) >> 1) - v27;
          }
          else
          {
LABEL_50:
            v28 = 0;
          }
          if ( v27 )
          {
            if ( 2 * v28 + 8 >= 2 * v28 )
            {
              v29 = (2 * v28 + 11) & 0xFFFFFFFFFFFFFFFCuLL;
              if ( v29 < (unsigned __int64)v4 )
              {
                v25 = (unsigned __int16 *)((char *)i + v29);
                v30 = (_DWORD)v4 - v29;
                v125 = (unsigned __int16 *)((char *)i + v29);
                goto LABEL_56;
              }
            }
          }
        }
      }
    }
  }
  v30 = 0;
LABEL_56:
  v31 = 0;
  v132 = 0;
  v130 = v30 >> 2;
LABEL_57:
  if ( v31 >= 8 )
  {
    if ( v25 && v130 == 1 )
    {
      v103 = v126;
      v126[192] = 2;
      *((_QWORD *)v103 + 97) = 4;
      v104 = *v25;
      v103[198] |= 1u;
      *((_QWORD *)v103 + 98) = v104;
    }
    else
    {
      v126[198] |= 2u;
    }
    return 0;
  }
  pszDest[0] = 0;
  v124 = 0;
  v32 = 0;
  v123 = 0;
  v33 = 0;
  v34 = (&off_14000AC28)[2 * v31];
  v121 = v34;
  v122 = dword_14000AC20[4 * v31];
  while ( 1 )
  {
    v129 = v33;
    if ( v33 >= 4 )
      goto LABEL_148;
    v35 = off_14000ACA0[v33];
    v36 = pszDest;
    v37 = 2147483646;
    v38 = 128;
    do
    {
      if ( !v37 )
        break;
      if ( !*v35 )
        break;
      *v36++ = *v35++;
      --v37;
      --v38;
    }
    while ( v38 );
    v39 = v36 - 1;
    v40 = -2147483643;
    if ( v38 )
    {
      v39 = v36;
      v40 = 0;
    }
    *v39 = 0;
    if ( !v38 )
    {
      v41 = "RtlStringCchCopyW failed [%x]";
      v42 = 3104;
      v43 = v40;
      goto LABEL_68;
    }
    v46 = 128;
    v47 = pszDest;
    do
    {
      if ( !*v47 )
        break;
      ++v47;
      --v46;
    }
    while ( v46 );
    v40 = -1073741811;
    if ( !v46 )
      goto LABEL_272;
    v48 = 2147483646;
    v49 = v34;
    v50 = (_WORD *)&v134 - v46;
    do
    {
      if ( !v48 )
        break;
      if ( !*v49 )
        break;
      *v50++ = *v49++;
      --v48;
      --v46;
    }
    while ( v46 );
    v51 = v50 - 1;
    v40 = -2147483643;
    if ( v46 )
    {
      v51 = v50;
      v40 = 0;
    }
    *v51 = 0;
    if ( !v46 )
    {
LABEL_272:
      v42 = 3110;
      v41 = "RtlStringCchCatW failed [%x]";
      v43 = v40;
LABEL_68:
      LODWORD(v120) = v43;
      AslLogCallPrintf(1, "AslpFileQueryVersionString", v42, v41, v120);
      v44 = v40;
      if ( v40 != -1073741275 )
        goto LABEL_275;
LABEL_227:
      v126[8 * v122 + 6] |= 2u;
LABEL_214:
      v25 = v125;
      v31 = ++v132;
      goto LABEL_57;
    }
    v52 = v131;
    k = v131;
    v128 = 0;
    v123 = 0;
    if ( v131[2] )
    {
      v89 = "Version block invalid";
      v90 = 2787;
LABEL_189:
      v40 = -1073741811;
      AslLogCallPrintf(1, "AslpFileVerQueryBlock", v90, v89);
      goto LABEL_125;
    }
    v54 = AslStringDuplicate(&v128, pszDest);
    v40 = v54;
    if ( v54 < 0 )
    {
      AslLogCallPrintf(1, "AslpFileVerQueryBlock", 2793, "AslStringDuplicate failed [%x]", v54);
      goto LABEL_125;
    }
    v55 = *v52;
    if ( (unsigned __int16)v55 > 0x7FFFu )
    {
      v89 = "VersionBlock is too long";
      v90 = 2805;
      goto LABEL_189;
    }
    if ( (unsigned int)v55 < 8 )
    {
      v89 = "VersionBlock not long enough";
      v90 = 2810;
      goto LABEL_189;
    }
    v56 = (char *)v52 + v55;
    v57 = *(unsigned __int16 *)((char *)v52 + v55 - 2);
    v58 = (unsigned __int16 *)v56;
    *((_WORD *)v56 - 1) = 0;
    v59 = (const wchar_t *)v128;
    if ( v128 )
    {
      if ( *(_WORD *)v128 )
      {
        do
        {
          v60 = L"\\";
          if ( asc_14000AF88[0] )
          {
            v72 = asc_14000AF88[0];
            while ( v72 != *v59 )
            {
              v72 = v60[1];
              ++v60;
              if ( !v72 )
                goto LABEL_95;
            }
          }
          if ( !*v60 )
            break;
          ++v59;
        }
        while ( *v59 );
      }
LABEL_95:
      v61 = v59;
      while ( *v59 )
      {
        v62 = L"\\";
        if ( asc_14000AF88[0] )
        {
          v63 = asc_14000AF88[0];
          do
          {
            if ( v63 == *v59 )
              break;
            v63 = v62[1];
            ++v62;
          }
          while ( v63 );
        }
        if ( *v62 )
        {
          *v59++ = 0;
          break;
        }
        ++v59;
      }
      v64 = 0;
      if ( v59 != v61 )
        v64 = v61;
    }
    else
    {
      v59 = 0;
      v64 = 0;
    }
LABEL_107:
    if ( v64 )
    {
      v65 = (_DWORD)v56 - (_DWORD)k;
      if ( (unsigned int)((_DWORD)v56 - (_DWORD)k) >= 8 )
      {
        v66 = *k;
        if ( (unsigned int)v66 <= v65 && v65 <= 0x7FFF )
        {
          v67 = k + 3;
          if ( k != (unsigned __int16 *)-6LL )
          {
            v68 = ((unsigned __int64)v65 - 6) >> 1;
            if ( v68 <= 0x7FFFFFFF )
            {
              v69 = ((unsigned __int64)v65 - 6) >> 1;
              if ( v68 )
              {
                while ( *v67 )
                {
                  ++v67;
                  if ( !--v68 )
                    goto LABEL_116;
                }
                v70 = v69 - v68;
              }
              else
              {
LABEL_116:
                v70 = 0;
              }
              if ( v68 )
              {
                if ( 2 * v70 + 8 >= 2 * v70 )
                {
                  v71 = ((k[1] + 3LL) & 0xFFFFFFFFFFFFFFFCuLL) + ((2 * v70 + 11) & 0xFFFFFFFFFFFFFFFCuLL);
                  if ( v71 <= v66 )
                  {
                    v58 = (unsigned __int16 *)((char *)k + v66);
                    for ( k = (unsigned __int16 *)((char *)k + v71);
                          k < v58;
                          k = (unsigned __int16 *)((char *)k + ((*k + 3LL) & 0xFFFFFFFFFFFFFFFCuLL)) )
                    {
                      v82 = *k;
                      if ( (unsigned int)v82 <= 8 || v82 > (char *)v58 - (char *)k )
                        break;
                      if ( !wcsicmp_0(v64, k + 3) )
                      {
                        if ( v59 )
                        {
                          for ( m = v59; *m; ++m )
                          {
                            v84 = L"\\";
                            if ( asc_14000AF88[0] )
                            {
                              v88 = asc_14000AF88[0];
                              while ( v88 != *m )
                              {
                                v88 = v84[1];
                                ++v84;
                                if ( !v88 )
                                  goto LABEL_167;
                              }
                            }
                            if ( !*v84 )
                              break;
                          }
LABEL_167:
                          v85 = m;
                          while ( *m )
                          {
                            v86 = L"\\";
                            if ( asc_14000AF88[0] )
                            {
                              v87 = asc_14000AF88[0];
                              do
                              {
                                if ( v87 == *m )
                                  break;
                                v87 = v86[1];
                                ++v86;
                              }
                              while ( v87 );
                            }
                            if ( *v86 )
                            {
                              *m++ = 0;
                              break;
                            }
                            ++m;
                          }
                          v64 = 0;
                          v59 = m;
                          if ( m != v85 )
                            v64 = v85;
                        }
                        else
                        {
                          v64 = 0;
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
      v32 = v124;
      v40 = -1073741275;
    }
    else
    {
      v124 = k;
      v3 = (char *)v58 - (char *)k;
      v32 = k;
      v123 = v3;
      v40 = 0;
    }
    v33 = v129;
    *((_WORD *)v56 - 1) = v57;
LABEL_125:
    if ( v128 )
      ExFreePoolWithTag_0(v128, 0x74705041u);
    if ( v40 >= 0 )
      break;
    if ( v40 != -1073741275 )
    {
      v119 = 3140;
LABEL_274:
      AslLogCallPrintf(1, "AslpFileQueryVersionString", v119, "AslpFileVerQueryBlock failed [%x]", v40);
      v44 = v40;
LABEL_275:
      AslLogCallPrintf(1, "AslpFileMakeStringVersionAttributes", 2616, "AslpFileQueryVersionString failed [%x]", v40);
      return v44;
    }
    v34 = v121;
    ++v33;
    v3 = 0;
  }
  if ( v3 - 8 > 0x7FF7 )
    goto LABEL_147;
  v73 = v32 + 3;
  if ( v32 == (unsigned __int16 *)-6LL )
    goto LABEL_147;
  v74 = (v3 - 6) >> 1;
  if ( v74 > 0x7FFFFFFF )
    goto LABEL_147;
  if ( v74 )
  {
    while ( *v73 )
    {
      ++v73;
      if ( !--v74 )
        goto LABEL_143;
    }
    v75 = ((v3 - 6) >> 1) - v74;
  }
  else
  {
LABEL_143:
    v75 = 0;
  }
  if ( !v74 || 2 * v75 + 8 < 2 * v75 || (v91 = (2 * v75 + 11) & 0xFFFFFFFFFFFFFFFCuLL, v91 > v3) )
  {
LABEL_147:
    v34 = v121;
    v3 = 0;
LABEL_148:
    if ( v125 )
    {
      v76 = v131;
      v77 = v125;
      for ( n = 0; n < v130; ++n )
      {
        LODWORD(v120) = v77[1];
        v43 = RtlStringCchPrintfW(pszDest, 0x80u, L"\\StringFileInfo\\%04X%04X\\%s", *v77, v120, v34);
        v40 = v43;
        if ( v43 < 0 )
        {
          v41 = "RtlStringCchPrintfW failed [%x]";
          v42 = 3158;
          goto LABEL_68;
        }
        v40 = AslpFileVerQueryBlock(v76, pszDest, &v124, &v123);
        if ( v40 >= 0 )
        {
          if ( v123 - 8 > 0x7FF7 )
            goto LABEL_227;
          v79 = v124 + 3;
          if ( v124 == (unsigned __int16 *)-6LL )
            goto LABEL_227;
          v80 = (v123 - 6) >> 1;
          if ( v80 > 0x7FFFFFFF )
            goto LABEL_227;
          if ( v80 )
          {
            while ( *v79 )
            {
              ++v79;
              if ( !--v80 )
                goto LABEL_159;
            }
            v81 = ((v123 - 6) >> 1) - v80;
          }
          else
          {
LABEL_159:
            v81 = 0;
          }
          if ( !v80 )
            goto LABEL_227;
          if ( 2 * v81 + 8 < 2 * v81 )
            goto LABEL_227;
          v113 = (2 * v81 + 11) & 0xFFFFFFFFFFFFFFFCuLL;
          if ( v113 > v123 )
            goto LABEL_227;
          v92 = (unsigned __int16 *)((char *)v124 + v113);
          if ( v113 == v123 )
          {
            --v92;
          }
          else
          {
            v114 = v123 - v113;
            if ( !v92 )
              goto LABEL_266;
            v115 = v114 >> 1;
            if ( v114 >> 1 > 0x7FFFFFFF )
              goto LABEL_266;
            v116 = (unsigned __int16 *)((char *)v124 + v113);
            if ( !v115 )
              goto LABEL_266;
            do
            {
              if ( !*v116 )
                break;
              ++v116;
              --v115;
            }
            while ( v115 );
            if ( !v115 )
            {
LABEL_266:
              v96 = (v114 - 2) >> 1;
              goto LABEL_200;
            }
          }
          goto LABEL_201;
        }
        if ( v40 != -1073741275 )
        {
          v119 = 3188;
          goto LABEL_274;
        }
        v34 = v121;
        v77 += 2;
      }
    }
    goto LABEL_227;
  }
  v92 = (unsigned __int16 *)((char *)v32 + v91);
  if ( v91 == v3 )
  {
    --v92;
    goto LABEL_198;
  }
  v93 = v3 - v91;
  if ( !v92 )
    goto LABEL_199;
  v94 = v93 >> 1;
  if ( v93 >> 1 > 0x7FFFFFFF )
    goto LABEL_199;
  v95 = (unsigned __int16 *)((char *)v32 + v91);
  if ( !v94 )
    goto LABEL_199;
  do
  {
    if ( !*v95 )
      break;
    ++v95;
    --v94;
  }
  while ( v94 );
  if ( v94 )
  {
LABEL_198:
    v3 = 0;
  }
  else
  {
LABEL_199:
    v96 = (v93 - 2) >> 1;
    v3 = 0;
LABEL_200:
    v92[v96] = 0;
  }
LABEL_201:
  if ( v92 )
  {
    if ( *v92 )
    {
      v97 = -1;
      do
        ++v97;
      while ( v92[v97] );
      for ( ii = 0; ii < v97; ++ii )
      {
        for ( jj = 0; jj < 5; ++jj )
        {
          v100 = v92[ii];
          if ( v100 >= (unsigned __int16)word_14000C108[2 * jj] && v100 <= (unsigned __int16)word_14000C10A[2 * jj] )
            goto LABEL_210;
        }
        v92[ii] = 64;
LABEL_210:
        ;
      }
    }
    v101 = &v126[8 * v122];
    v102 = -1;
    *v101 = 4;
    do
      ++v102;
    while ( v92[v102] );
    v101[6] |= 1u;
    *((_QWORD *)v101 + 1) = v102;
    *((_QWORD *)v101 + 2) = v92;
    goto LABEL_214;
  }
  AslLogCallPrintf(1, "AslpFileMakeStringVersionAttributes", 2603, "AslStringXmlSanitize failed [%x]", -1073741811);
  return 3221225485LL;
}

```

## disassembly

```asm
0x14003c980  mov     r11, rsp
0x14003c983  push    rbp
0x14003c984  push    rsi
0x14003c985  lea     rbp, [r11-0D8h]
0x14003c98c  sub     rsp, 1C8h
0x14003c993  mov     rax, cs:__security_cookie
0x14003c99a  xor     rax, rsp
0x14003c99d  mov     [rbp+0D0h+var_40], rax
0x14003c9a4  mov     [rbp+0D0h+var_150], rdx
0x14003c9a8  mov     rsi, rdx
0x14003c9ab  mov     [rsp+1D0h+var_178], rcx
0x14003c9b0  test    rdx, rdx
0x14003c9b3  jz      loc_14003D477
0x14003c9b9  mov     [r11+18h], rbx
0x14003c9bd  mov     [r11-18h], rdi
0x14003c9c1  mov     [r11-20h], r12
0x14003c9c5  mov     [r11-28h], r13
0x14003c9c9  xor     r13d, r13d
0x14003c9cc  mov     [r11-30h], r14
0x14003c9d0  mov     edi, r13d
0x14003c9d3  mov     r14d, 7FFFh
0x14003c9d9  mov     [r11-38h], r15
0x14003c9dd  mov     [rsp+1D0h+var_158], rdx
0x14003c9e2  mov     [rsp+1D0h+P], r13
0x14003c9e7  cmp     [rdx+4], di
0x14003c9eb  jnz     loc_14003D635
0x14003c9f1  lea     rdx, aVarfileinfoTra; "\\VarFileInfo\\Translation"
0x14003c9f8  lea     rcx, [rsp+1D0h+P]
0x14003c9fd  call    AslStringDuplicate
0x14003ca02  mov     ebx, eax
0x14003ca04  test    eax, eax
0x14003ca06  js      loc_14003D725
0x14003ca0c  movzx   eax, word ptr [rsi]
0x14003ca0f  cmp     ax, r14w
0x14003ca13  ja      loc_14003D761
0x14003ca19  cmp     eax, 8
0x14003ca1c  jb      loc_14003D773
0x14003ca22  movzx   r12d, word ptr [rsi+rax-2]
0x14003ca28  lea     r15, [rsi+rax]
0x14003ca2c  mov     [r15-2], r13w
0x14003ca31  mov     r14, r15
0x14003ca34  mov     rbx, [rsp+1D0h+P]
0x14003ca39  test    rbx, rbx
0x14003ca3c  jz      loc_14003D671
0x14003ca42  mov     eax, dword ptr cs:asc_14000AF88; "\\"
0x14003ca48  cmp     [rbx], di
0x14003ca4b  jz      short loc_14003CA66
0x14003ca4d  lea     rcx, asc_14000AF88; "\\"
0x14003ca54  test    ax, ax
0x14003ca57  jnz     loc_14003CD28
0x14003ca5d  cmp     [rcx], di
0x14003ca60  jnz     loc_14003D434
0x14003ca66  mov     r9, rbx
0x14003ca69  nop     dword ptr [rax+00000000h]
0x14003ca70  movzx   r8d, word ptr [rbx]
0x14003ca74  test    r8w, r8w
0x14003ca78  jz      short loc_14003CAB1
0x14003ca7a  lea     rcx, asc_14000AF88; "\\"
0x14003ca81  test    ax, ax
0x14003ca84  jnz     short loc_14003CA91
0x14003ca86  cmp     [rcx], di
0x14003ca89  jnz     short loc_14003CAA9
0x14003ca8b  add     rbx, 2
0x14003ca8f  jmp     short loc_14003CA70
0x14003ca91  movzx   edx, ax
0x14003ca94  cmp     dx, r8w
0x14003ca98  jz      short loc_14003CA86
0x14003ca9a  movzx   edx, word ptr [rcx+2]
0x14003ca9e  add     rcx, 2
0x14003caa2  test    dx, dx
0x14003caa5  jnz     short loc_14003CA94
0x14003caa7  jmp     short loc_14003CA86
0x14003caa9  mov     [rbx], r13w
0x14003caad  add     rbx, 2
0x14003cab1  cmp     rbx, r9
0x14003cab4  cmovnz  rdi, r9
0x14003cab8  test    rdi, rdi
0x14003cabb  jz      loc_14003CB6D
0x14003cac1  mov     ecx, r15d
0x14003cac4  sub     ecx, esi
0x14003cac6  cmp     ecx, 8
0x14003cac9  jb      loc_14003CB5B
0x14003cacf  movzx   r8d, word ptr [rsi]
0x14003cad3  cmp     r8d, ecx
0x14003cad6  ja      loc_14003CB5B
0x14003cadc  cmp     ecx, 7FFFh
0x14003cae2  ja      short loc_14003CB5B
0x14003cae4  lea     rax, [rsi+6]
0x14003cae8  test    rax, rax
0x14003caeb  jz      short loc_14003CB5B
0x14003caed  sub     rcx, 6
0x14003caf1  shr     rcx, 1
0x14003caf4  cmp     rcx, 7FFFFFFFh
0x14003cafb  ja      short loc_14003CB5B
0x14003cafd  mov     rdx, rcx
0x14003cb00  test    rcx, rcx
0x14003cb03  jz      short loc_14003CB15
0x14003cb05  cmp     [rax], r13w
0x14003cb09  jz      short loc_14003CB1A
0x14003cb0b  add     rax, 2
0x14003cb0f  sub     rcx, 1
0x14003cb13  jnz     short loc_14003CB05
0x14003cb15  mov     rdx, r13
0x14003cb18  jmp     short loc_14003CB1D
0x14003cb1a  sub     rdx, rcx
0x14003cb1d  test    rcx, rcx
0x14003cb20  jz      short loc_14003CB5B
0x14003cb22  lea     rax, [rdx+rdx]
0x14003cb26  lea     rdx, [rax+8]
0x14003cb2a  cmp     rdx, rax
0x14003cb2d  jb      short loc_14003CB5B
0x14003cb2f  movzx   ecx, word ptr [rsi+2]
0x14003cb33  add     rdx, 3
0x14003cb37  add     rcx, 3
0x14003cb3b  and     rdx, 0FFFFFFFFFFFFFFFCh
0x14003cb3f  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14003cb43  add     rdx, rcx
0x14003cb46  cmp     rdx, r8
0x14003cb49  ja      short loc_14003CB5B
0x14003cb4b  lea     r14, [r8+rsi]
0x14003cb4f  add     rsi, rdx
0x14003cb52  cmp     rsi, r14
0x14003cb55  jb      loc_14003D4DA
0x14003cb5b  mov     [r15-2], r12w
0x14003cb60  mov     ebx, 0C0000225h
0x14003cb65  mov     rdi, r13
0x14003cb68  mov     rsi, r13
0x14003cb6b  jmp     short loc_14003CB7B
0x14003cb6d  mov     rdi, r14
0x14003cb70  mov     [r15-2], r12w
0x14003cb75  sub     rdi, rsi
0x14003cb78  mov     ebx, r13d
0x14003cb7b  mov     rcx, [rsp+1D0h+P]; P
0x14003cb80  test    rcx, rcx
0x14003cb83  jz      short loc_14003CB8F
0x14003cb85  mov     edx, 74705041h; Tag
0x14003cb8a  call    ExFreePoolWithTag_0
0x14003cb8f  cmp     ebx, 0C0000225h
0x14003cb95  jz      loc_14003CD4B
0x14003cb9b  test    ebx, ebx
0x14003cb9d  js      loc_14003D785
0x14003cba3  lea     rax, [rdi-8]
0x14003cba7  mov     [rsp+1D0h+var_180], r13
0x14003cbac  mov     r15, r13
0x14003cbaf  cmp     rax, 7FF7h
0x14003cbb5  ja      loc_14003CD53
0x14003cbbb  lea     rax, [rsi+6]
0x14003cbbf  test    rax, rax
0x14003cbc2  jz      loc_14003CD53
0x14003cbc8  lea     rcx, [rdi-6]
0x14003cbcc  shr     rcx, 1
0x14003cbcf  cmp     rcx, 7FFFFFFFh
0x14003cbd6  ja      loc_14003CD53
0x14003cbdc  mov     rdx, rcx
0x14003cbdf  test    rcx, rcx
0x14003cbe2  jz      short loc_14003CBF4
0x14003cbe4  cmp     [rax], r13w
0x14003cbe8  jz      short loc_14003CBF9
0x14003cbea  add     rax, 2
0x14003cbee  sub     rcx, 1
0x14003cbf2  jnz     short loc_14003CBE4
0x14003cbf4  mov     rdx, r13
0x14003cbf7  jmp     short loc_14003CBFC
0x14003cbf9  sub     rdx, rcx
0x14003cbfc  test    rcx, rcx
0x14003cbff  jz      loc_14003CD53
0x14003cc05  lea     rax, [rdx+rdx]
0x14003cc09  lea     rcx, [rax+8]
0x14003cc0d  cmp     rcx, rax
0x14003cc10  jb      loc_14003CD53
0x14003cc16  lea     rax, [rcx+3]
0x14003cc1a  and     rax, 0FFFFFFFFFFFFFFFCh
0x14003cc1e  cmp     rax, rdi
0x14003cc21  jnb     loc_14003CD53
0x14003cc27  lea     r15, [rax+rsi]
0x14003cc2b  sub     rdi, rax
0x14003cc2e  mov     [rsp+1D0h+var_180], r15
0x14003cc33  shr     rdi, 2
0x14003cc37  mov     r14, r13
0x14003cc3a  and     edi, 3FFFFFFFh
0x14003cc40  mov     [rbp+0D0h+var_148], r13
0x14003cc44  mov     [rsp+1D0h+var_158], rdi
0x14003cc49  lea     rdx, cs:140000000h
0x14003cc50  cmp     r14, 8
0x14003cc54  jnb     loc_14003D39B
0x14003cc5a  mov     rax, r14
0x14003cc5d  mov     [rbp+0D0h+pszDest], r13w
0x14003cc62  add     rax, rax
0x14003cc65  mov     [rsp+1D0h+var_188], r13
0x14003cc6a  mov     rsi, r13
0x14003cc6d  mov     [rsp+1D0h+var_190], r13
0x14003cc72  mov     rdi, r13
0x14003cc75  mov     r10, ds:rva off_14000AC28[rdx+rax*8]; "ProductVersion" ...
0x14003cc7d  mov     r14d, ds:rva dword_14000AC20[rdx+rax*8]
0x14003cc85  mov     [rsp+1D0h+var_1A0], r10
0x14003cc8a  mov     dword ptr [rsp+1D0h+var_198], r14d
0x14003cc8f  mov     [rsp+1D0h+var_160], rdi
0x14003cc94  cmp     rdi, 4
0x14003cc98  jnb     loc_14003D079
0x14003cc9e  mov     rdx, ds:rva off_14000ACA0[rdx+rdi*8]; "\\StringFileInfo\\000004B0\\" ...
0x14003cca6  lea     r9, [rbp+0D0h+pszDest]
0x14003ccaa  mov     ecx, 7FFFFFFEh
0x14003ccaf  mov     r8d, 80h
0x14003ccb5  test    rcx, rcx
0x14003ccb8  jz      short loc_14003CCD7
0x14003ccba  movzx   eax, word ptr [rdx]
0x14003ccbd  test    ax, ax
0x14003ccc0  jz      short loc_14003CCD7
0x14003ccc2  mov     [r9], ax
0x14003ccc6  add     rdx, 2
0x14003ccca  add     r9, 2
0x14003ccce  dec     rcx
0x14003ccd1  sub     r8, 1
0x14003ccd5  jnz     short loc_14003CCB5
0x14003ccd7  test    r8, r8
0x14003ccda  lea     rax, [r9-2]
0x14003ccde  mov     ebx, 80000005h
0x14003cce3  cmovnz  rax, r9
0x14003cce7  cmovnz  ebx, r13d
0x14003cceb  mov     [rax], r13w
0x14003ccef  jnz     short loc_14003CD5B
0x14003ccf1  lea     r9, aRtlstringcchco_0; "RtlStringCchCopyW failed [%x]"
0x14003ccf8  mov     r8d, 0C20h
0x14003ccfe  mov     eax, ebx
0x14003cd00  lea     rdx, aAslpfilequeryv; "AslpFileQueryVersionString"
0x14003cd07  mov     dword ptr [rsp+1D0h+var_1B0], eax
0x14003cd0b  mov     ecx, 1
0x14003cd10  call    AslLogCallPrintf
0x14003cd15  mov     edi, ebx
0x14003cd17  cmp     ebx, 0C0000225h
0x14003cd1d  jnz     loc_14003D6D8
0x14003cd23  jmp     loc_14003D45F
0x14003cd28  movzx   r8d, word ptr [rbx]
0x14003cd2c  movzx   edx, ax
0x14003cd2f  cmp     dx, r8w
0x14003cd33  jz      loc_14003CA5D
0x14003cd39  movzx   edx, word ptr [rcx+2]
0x14003cd3d  add     rcx, 2
0x14003cd41  test    dx, dx
0x14003cd44  jnz     short loc_14003CD2F
0x14003cd46  jmp     loc_14003CA66
0x14003cd4b  mov     r15, r13
0x14003cd4e  mov     [rsp+1D0h+var_180], r13
0x14003cd53  mov     rdi, r13
0x14003cd56  jmp     loc_14003CC33
0x14003cd5b  mov     ecx, 80h
0x14003cd60  lea     rax, [rbp+0D0h+pszDest]
0x14003cd64  cmp     word ptr [rax], 0
0x14003cd68  jz      short loc_14003CD74
0x14003cd6a  add     rax, 2
0x14003cd6e  sub     rcx, 1
0x14003cd72  jnz     short loc_14003CD64
0x14003cd74  test    rcx, rcx
0x14003cd77  mov     ebx, 0C000000Dh
0x14003cd7c  cmovnz  ebx, r13d
0x14003cd80  jz      loc_14003D6A0
0x14003cd86  lea     rax, [rcx+rcx]
0x14003cd8a  mov     edx, 7FFFFFFEh
0x14003cd8f  lea     r9, [rbp+0D0h+var_40]
0x14003cd96  mov     r8, r10
0x14003cd99  sub     r9, rax
0x14003cd9c  nop     dword ptr [rax+00h]
0x14003cda0  test    rdx, rdx
0x14003cda3  jz      short loc_14003CDC3
0x14003cda5  movzx   eax, word ptr [r8]
0x14003cda9  test    ax, ax
0x14003cdac  jz      short loc_14003CDC3
0x14003cdae  mov     [r9], ax
0x14003cdb2  add     r8, 2
0x14003cdb6  add     r9, 2
0x14003cdba  dec     rdx
0x14003cdbd  sub     rcx, 1
0x14003cdc1  jnz     short loc_14003CDA0
0x14003cdc3  test    rcx, rcx
0x14003cdc6  lea     rax, [r9-2]
0x14003cdca  mov     ebx, 80000005h
0x14003cdcf  cmovnz  rax, r9
0x14003cdd3  cmovnz  ebx, r13d
0x14003cdd7  mov     [rax], r13w
0x14003cddb  jz      loc_14003D6A0
0x14003cde1  mov     r12, [rbp+0D0h+var_150]
0x14003cde5  mov     r15, r12
0x14003cde8  mov     [rsp+1D0h+var_168], r13
0x14003cded  mov     [rsp+1D0h+var_190], r13
0x14003cdf2  cmp     word ptr [r12+4], 0
0x14003cdf9  jnz     loc_14003D254
0x14003cdff  lea     rdx, [rbp+0D0h+pszDest]
0x14003ce03  lea     rcx, [rsp+1D0h+var_168]
0x14003ce08  call    AslStringDuplicate
0x14003ce0d  mov     ebx, eax
0x14003ce0f  test    eax, eax
0x14003ce11  js      loc_14003D679
0x14003ce17  movzx   eax, word ptr [r12]
0x14003ce1c  mov     edx, 7FFFh
0x14003ce21  cmp     ax, dx
0x14003ce24  ja      loc_14003D701
0x14003ce2a  cmp     eax, 8
0x14003ce2d  jb      loc_14003D713
0x14003ce33  lea     r14, [r12+rax]
0x14003ce37  xor     r10d, r10d
  ... truncated ...
```
