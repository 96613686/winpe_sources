# Appx::Packaging::FileNameHelper::ValidateFileName(ushort const *,bool *)

- ea: `0x180011d60`
- end: `0x1800133f3`
- name: `?ValidateFileName@FileNameHelper@Packaging@Appx@@SAJPEBGPEA_N@Z`
- size: `5779`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180025d00`
- `0x180069820`

## callees

- `0x180011d60`
- `0x1800133fc`
- `0x180029dc0`
- `0x180071f50`
- `0x1800992c4`
- `0x18009d3d0`
- `0x18009d729`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800122d2`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180012517`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180012751`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180012974`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800122d2`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180012517`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180012751`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180012974`

## string_xrefs

- `0x180012457`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012bc3`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012be3`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012c1a`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012c3b`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012c5a`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012c77`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012c90`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012ca9`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012cc8`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012e3f`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012e5a`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012e7f`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012e9a`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012ebf`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012eda`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012f12`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012f34`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012f5b`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180012f76`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180013108`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18001316f`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800131c0`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180013227`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180013269`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800132d0`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18001330f`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180013336`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800133b1`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Appx::Packaging::FileNameHelper::ValidateFileName(unsigned __int16 *a1, bool *a2)
{
  unsigned __int64 v2; // rdx
  __int64 v3; // r8
  const unsigned __int16 *v4; // rax
  int v5; // ebx
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rsi
  int v8; // ebx
  unsigned __int64 v9; // rdi
  __int16 v10; // cx
  unsigned int v11; // r9d
  unsigned __int16 *v12; // r8
  __int64 v13; // r11
  wchar_t *v14; // r14
  unsigned int v15; // r15d
  unsigned int i; // r10d
  int v17; // ecx
  unsigned __int16 v18; // cx
  __int64 v19; // rdx
  int v21; // r10d
  unsigned __int16 v22; // cx
  unsigned __int16 v23; // cx
  unsigned int v24; // r13d
  __int64 v25; // rcx
  const unsigned __int16 *v26; // rax
  unsigned int v27; // edi
  wil::details::in1diag3 *v28; // rcx
  unsigned int j; // ebx
  __int16 *v30; // r15
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // rdx
  __int16 *v33; // r14
  unsigned int v34; // eax
  size_t v35; // r8
  const unsigned __int16 *v36; // rdi
  unsigned __int64 v37; // rdx
  __int16 *v38; // rcx
  __int16 k; // ax
  __int64 v40; // rax
  bool v41; // bl
  unsigned __int64 v42; // rdx
  unsigned int v43; // r13d
  __int64 v44; // rcx
  const unsigned __int16 *v45; // rax
  unsigned int v46; // edi
  wil::details::in1diag3 *v47; // rcx
  unsigned int n; // ebx
  __int16 *v49; // r15
  unsigned __int64 v50; // rax
  unsigned __int64 v51; // rdx
  __int16 *v52; // r14
  unsigned int v53; // eax
  size_t v54; // r8
  const unsigned __int16 *v55; // rdi
  unsigned __int64 v56; // rdx
  __int64 v57; // rdx
  __int16 *v58; // rcx
  __int16 ii; // ax
  __int64 v60; // rax
  unsigned __int64 v61; // r14
  unsigned __int64 v62; // rdx
  unsigned int v63; // r13d
  __int64 v64; // rcx
  const unsigned __int16 *v65; // rax
  unsigned int v66; // edi
  wil::details::in1diag3 *v67; // rcx
  unsigned int kk; // ebx
  __int16 *v69; // r15
  unsigned __int64 v70; // rax
  unsigned __int64 v71; // rdx
  __int16 *v72; // r14
  unsigned int v73; // eax
  size_t v74; // r8
  const unsigned __int16 *v75; // rdi
  unsigned __int64 v76; // rdx
  __int16 *v77; // rcx
  __int16 v78; // ax
  __int64 v79; // r13
  __int64 v80; // rax
  bool v81; // r12
  unsigned __int64 v82; // rdx
  unsigned int v83; // r14d
  __int64 v84; // rcx
  const unsigned __int16 *v85; // rax
  unsigned int v86; // esi
  unsigned int nn; // r15d
  __int16 *v88; // rdi
  unsigned __int64 v89; // rax
  unsigned __int64 v90; // rdx
  __int16 *v91; // rsi
  unsigned int v92; // eax
  unsigned __int64 v93; // rdx
  __int16 *v94; // rcx
  __int16 v95; // ax
  bool v96; // bl
  unsigned __int64 v97; // rdx
  unsigned __int64 v98; // rdx
  unsigned __int64 v99; // rdx
  unsigned __int64 v100; // rdx
  unsigned __int64 v101; // rdx
  unsigned __int64 v102; // rdx
  unsigned __int64 v103; // rdx
  unsigned __int64 v104; // rdx
  __int16 *m; // rcx
  __int16 *jj; // rcx
  __int16 *mm; // rcx
  __int16 *i1; // rcx
  __int64 v109; // rdx
  unsigned __int64 v110; // rdx
  unsigned __int64 v111; // rdx
  unsigned __int64 v112; // rdx
  unsigned __int64 v113; // rdx
  __int64 v114; // rdx
  int v115; // eax
  int v116; // eax
  int v117; // eax
  int v118; // eax
  __int16 *v119; // xmm0_8
  __int16 *v120; // xmm0_8
  __int16 *v121; // xmm0_8
  __int16 *v122; // xmm0_8
  int lpString2; // [rsp+20h] [rbp-49h]
  int lpString2a; // [rsp+20h] [rbp-49h]
  int lpString2b; // [rsp+20h] [rbp-49h]
  int lpString2c; // [rsp+20h] [rbp-49h]
  int lpString2d; // [rsp+20h] [rbp-49h]
  int lpString2e; // [rsp+20h] [rbp-49h]
  int lpString2f; // [rsp+20h] [rbp-49h]
  int lpString2g; // [rsp+20h] [rbp-49h]
  int lpString2h; // [rsp+20h] [rbp-49h]
  int lpString2i; // [rsp+20h] [rbp-49h]
  unsigned int v133; // [rsp+50h] [rbp-19h]
  __int128 v134; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v135; // [rsp+70h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  bool v139; // [rsp+E0h] [rbp+77h]
  unsigned __int64 v140; // [rsp+E8h] [rbp+7Fh]

  v2 = (unsigned __int64)a1;
  if ( !a1 )
  {
    v5 = -2147024809;
LABEL_382:
    v19 = 319;
    goto LABEL_31;
  }
  v3 = 0x7FFFFFFF;
  v4 = a1;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  v5 = -2147024809;
  if ( v3 )
  {
    v5 = 0;
    v6 = 0x7FFFFFFF - v3;
  }
  else
  {
    v6 = 0;
  }
  v140 = v6;
  if ( !v3 )
    goto LABEL_382;
  if ( v6 - 1 > 0x7FFE || *(_WORD *)v2 == 92 )
  {
    v5 = -2147024773;
    v19 = 325;
    goto LABEL_31;
  }
  v7 = 0;
  v8 = 0;
  v9 = v2 + 2 * v6;
  v10 = 0;
  v11 = 0;
  v12 = (unsigned __int16 *)v2;
  v13 = 0x1000000000004001LL;
  v14 = a1;
  v15 = (unsigned int)a1;
  while ( (unsigned __int64)v12 < v9 )
  {
    v2 = *v12;
    if ( (unsigned int)v2 >= 0x7D )
    {
      if ( (unsigned __int16)v2 > 0xFFFDu )
      {
        v5 = -2147024773;
        v19 = 345;
        goto LABEL_31;
      }
      v23 = v10 + 10240;
      if ( (unsigned __int16)(v2 + 9216) > 0x3FFu )
      {
        if ( v23 <= 0x3FFu )
        {
          v5 = -2147024773;
          v19 = 355;
          goto LABEL_31;
        }
      }
      else if ( v23 > 0x3FFu )
      {
        v5 = -2147024773;
        v19 = 350;
        goto LABEL_31;
      }
LABEL_15:
      if ( v8 == 1 )
      {
LABEL_16:
        ++v11;
        goto LABEL_17;
      }
      if ( !v7 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= 5 )
          {
            v8 = 1;
            v13 = 0x1000000000004001LL;
            goto LABEL_16;
          }
          v17 = *(&off_180109B18)[2 * (int)i];
          if ( (_WORD)v2 == (_WORD)v17 || (_DWORD)v2 == v17 + 32 )
            break;
        }
        v15 = *((_DWORD *)&Appx::Packaging::FileNameHelper::DeviceNameChecker::DeviceNameTable + 4 * (int)i);
        v14 = (&off_180109B18)[2 * (int)i];
        v7 = 1;
        v13 = 0x1000000000004001LL;
        goto LABEL_16;
      }
      if ( v7 >= v15 )
      {
        if ( (_DWORD)v2 == 46 )
        {
          v8 = (v8 != 2) + 1;
        }
        else if ( !v8 )
        {
          goto LABEL_37;
        }
      }
      else
      {
        v21 = v14[v7];
        if ( (_WORD)v2 != (_WORD)v21 && (_DWORD)v2 != v21 + 32 )
        {
          if ( v21 == 63 )
          {
            if ( (((_WORD)v2 - 78) & 0xFFDF) == 0 )
            {
              --v15;
              ++v7;
              goto LABEL_16;
            }
            if ( (((_WORD)v2 - 77) & 0xFFDF) == 0 )
            {
              ++v7;
              goto LABEL_16;
            }
LABEL_37:
            v8 = 1;
          }
          else if ( v21 != 49 || (unsigned __int16)(v2 - 49) > 8u )
          {
            goto LABEL_37;
          }
        }
      }
      ++v7;
      goto LABEL_16;
    }
    if ( *((_BYTE *)&Appx::Packaging::FileNameHelper::IsReservedFileNameChar + v2) )
    {
      v5 = -2147024773;
      v19 = 339;
      goto LABEL_31;
    }
    if ( (_DWORD)v2 != 92 )
      goto LABEL_15;
    if ( (unsigned __int16)(v10 + 10240) <= 0x3FFu
      || (v18 = v10 - 32, v18 <= 0x3Cu) && _bittest64(&v13, v18)
      || v11 > 0xFF )
    {
LABEL_30:
      v5 = -2147024773;
      v19 = 364;
      goto LABEL_31;
    }
    if ( v8 )
    {
      if ( v8 == 2 )
        goto LABEL_30;
    }
    else if ( v7 == v15 )
    {
      goto LABEL_30;
    }
    v7 = 0;
    v8 = 0;
    v11 = 0;
LABEL_17:
    v10 = *v12++;
  }
  if ( (unsigned __int16)(v10 + 10240) <= 0x3FFu )
    goto LABEL_45;
  v22 = v10 - 32;
  if ( v22 <= 0x3Cu )
  {
    if ( _bittest64(&v13, v22) )
      goto LABEL_45;
  }
  if ( v11 > 0xFF )
    goto LABEL_45;
  if ( v8 )
  {
    if ( v8 == 2 )
    {
LABEL_45:
      v5 = -2147024773;
      v19 = 383;
      goto LABEL_31;
    }
  }
  else if ( v7 == v15 )
  {
    goto LABEL_45;
  }
  v134 = 0;
  v24 = 0;
  v135 = 0;
  v25 = 1073741822;
  v26 = a1;
  do
  {
    if ( !*v26 )
      break;
    ++v26;
    --v25;
  }
  while ( v25 );
  v5 = -2147024809;
  if ( v25 )
  {
    v5 = 0;
    v27 = 1073741822 - v25;
  }
  else
  {
    v27 = 0;
  }
  if ( !v25 )
  {
    v114 = 585;
    v28 = retaddr;
    goto LABEL_323;
  }
  v5 = -2147024362;
  if ( v27 <= 0x7FFFFFFF )
    v5 = 0;
  v28 = retaddr;
  if ( v27 > 0x7FFFFFFF )
  {
    v114 = 559;
LABEL_323:
    wil::details::in1diag3::_Log_Hr(
      v28,
      (void *)v114,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v5,
      lpString2);
    v30 = (__int16 *)*((_QWORD *)&v134 + 1);
    v36 = a1;
    goto LABEL_101;
  }
  if ( !v27 )
  {
    v30 = (__int16 *)*((_QWORD *)&v134 + 1);
    goto LABEL_94;
  }
  if ( v27 <= 0x20 )
  {
    for ( j = 8; j < v27; j *= 2 )
      ;
  }
  else
  {
    j = v27;
  }
  if ( j > 0x3FFFFFFF )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070503LL,
      lpString2);
    v5 = -2147023613;
    v30 = (__int16 *)*((_QWORD *)&v134 + 1);
  }
  else if ( j )
  {
    v30 = (__int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    v31 = 2LL * (j + 1);
    if ( !is_mul_ok(j + 1, 2u) )
      v31 = -1;
    v33 = (__int16 *)operator new[](v31, (const struct std::nothrow_t *)&std::nothrow);
    if ( v33 )
    {
      operator delete(v30, v32);
      v30 = v33;
      v24 = j + 1;
      v135 = j + 1;
      *((_QWORD *)&v134 + 1) = v33;
      if ( (unsigned int)v134 > j )
      {
        LODWORD(v134) = j;
        v33[j] = 0;
      }
      else if ( (unsigned int)v134 < j && !(_DWORD)v134 )
      {
        *v33 = 0;
      }
      goto LABEL_86;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x8007000ELL,
      lpString2);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x8007000ELL,
      lpString2i);
    v5 = -2147024882;
  }
  else
  {
    v119 = (__int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    v30 = v119;
    if ( v119 )
    {
      operator delete(v119, v2);
      v30 = 0;
      *((_QWORD *)&v134 + 1) = 0;
      LODWORD(v134) = 0;
    }
    v135 = 0;
LABEL_86:
    v5 = 0;
  }
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v5,
      lpString2);
    v36 = a1;
  }
  else
  {
    if ( v24 )
    {
      v34 = v24 - 1;
      goto LABEL_95;
    }
LABEL_94:
    v34 = 0;
LABEL_95:
    if ( v27 > v34 )
    {
      v115 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)&v134, v27);
      v5 = v115;
      if ( v115 >= 0 )
      {
        v30 = (__int16 *)*((_QWORD *)&v134 + 1);
        goto LABEL_96;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x20C,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v115,
        lpString2);
      v30 = (__int16 *)*((_QWORD *)&v134 + 1);
    }
    else
    {
LABEL_96:
      LODWORD(v134) = v27;
      if ( v27 )
        v30[v27] = 0;
      v5 = 0;
    }
    if ( v5 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x235,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v5,
        lpString2);
      v36 = a1;
    }
    else
    {
      v35 = 2 * v27;
      v36 = a1;
      memcpy_0(v30, a1, v35);
      v5 = 0;
    }
  }
LABEL_101:
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\stringhelper.cpp",
      (const char *)(unsigned int)v5,
      lpString2);
    if ( !v30 )
    {
LABEL_256:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BC,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filenamehelper.cpp",
        (const char *)(unsigned int)v5,
        lpString2b);
      operator delete(0, v98);
      v19 = 391;
      goto LABEL_31;
    }
LABEL_255:
    operator delete(v30, v97);
    goto LABEL_256;
  }
  if ( v30 )
  {
    v38 = v30;
    for ( k = *v30; *v38; k = *v38 )
    {
      if ( k == 47 )
        *v38 = 92;
      ++v38;
    }
    v40 = -1;
    do
      ++v40;
    while ( v30[v40] );
    if ( v40 )
    {
      for ( m = &v30[v40 - 1]; m >= v30; --m )
      {
        if ( *m != 92 )
          break;
        *m = 0;
      }
    }
  }
  if ( !(_DWORD)v134 )
  {
    v5 = -2147024773;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\stringhelper.cpp",
      (const char *)0x8007007BLL,
      lpString2);
    if ( !v30 )
      goto LABEL_256;
    goto LABEL_255;
  }
  v41 = 0;
  if ( v140 >= 0x21
    && CompareStringEx(&LocaleName, 1u, (LPCWCH)v30, 33, L"microsoft.system.package.metadata", 33, 0, 0, 0) == 2 )
  {
    if ( v140 == 33 )
    {
      v5 = -2147024773;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D0,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filenamehelper.cpp",
        (const char *)0x8007007BLL,
        lpString2);
      operator delete(v30, v113);
      v19 = 391;
      goto LABEL_31;
    }
    v41 = v30[33] == 92;
  }
  operator delete(v30, v37);
  if ( v41 )
  {
    v5 = -2147024773;
    v19 = 394;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filenamehelper.cpp",
      (const char *)(unsigned int)v5,
      lpString2);
    return (unsigned int)v5;
  }
  v134 = 0;
  v43 = 0;
  v135 = 0;
  v44 = 1073741822;
  v45 = v36;
  do
  {
    if ( !*v45 )
      break;
    ++v45;
    --v44;
  }
  while ( v44 );
  v5 = -2147024809;
  if ( v44 )
  {
    v5 = 0;
    v46 = 1073741822 - v44;
  }
  else
  {
    v46 = 0;
  }
  if ( !v44 )
  {
    v57 = 585;
    v47 = retaddr;
    goto LABEL_148;
  }
  v5 = -2147024362;
  if ( v46 <= 0x7FFFFFFF )
    v5 = 0;
  v47 = retaddr;
  if ( v46 > 0x7FFFFFFF )
  {
    v57 = 559;
LABEL_148:
    wil::details::in1diag3::_Log_Hr(
      v47,
      (void *)v57,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v5,
      lpString2);
    v49 = (__int16 *)*((_QWORD *)&v134 + 1);
    goto LABEL_149;
  }
  if ( !v46 )
  {
    v49 = (__int16 *)*((_QWORD *)&v134 + 1);
    goto LABEL_140;
  }
  if ( v46 <= 0x20 )
  {
    for ( n = 8; n < v46; n *= 2 )
      ;
  }
  else
  {
    n = v46;
  }
  if ( n > 0x3FFFFFFF )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070503LL,
      lpString2);
    v5 = -2147023613;
    v49 = (__int16 *)*((_QWORD *)&v134 + 1);
  }
  else if ( n )
  {
    v49 = (__int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    v50 = 2LL * (n + 1);
    if ( !is_mul_ok(n + 1, 2u) )
      v50 = -1;
    v52 = (__int16 *)operator new[](v50, (const struct std::nothrow_t *)&std::nothrow);
    if ( v52 )
    {
      operator delete(v49, v51);
      v49 = v52;
      v43 = n + 1;
      v135 = n + 1;
      *((_QWORD *)&v134 + 1) = v52;
      if ( (unsigned int)v134 > n )
      {
        LODWORD(v134) = n;
        v52[n] = 0;
      }
      else if ( (unsigned int)v134 < n && !(_DWORD)v134 )
      {
        *v52 = 0;
      }
      goto LABEL_135;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x8007000ELL,
      lpString2);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x8007000ELL,
      lpString2f);
    v5 = -2147024882;
  }
  else
  {
    v120 = (__int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    v49 = v120;
    if ( v120 )
    {
      operator delete(v120, v42);
      v49 = 0;
      *((_QWORD *)&v134 + 1) = 0;
      LODWORD(v134) = 0;
    }
    v135 = 0;
LABEL_135:
    v5 = 0;
  }
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v5,
      lpString2);
  }
  else
  {
    if ( v43 )
    {
      v53 = v43 - 1;
      goto LABEL_141;
    }
LABEL_140:
    v53 = 0;
LABEL_141:
    if ( v46 > v53 )
    {
      v116 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)&v134, v46);
      v5 = v116;
      if ( v116 >= 0 )
      {
        v49 = (__int16 *)*((_QWORD *)&v134 + 1);
        goto LABEL_142;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x20C,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v116,
        lpString2);
      v49 = (__int16 *)*((_QWORD *)&v134 + 1);
    }
    else
    {
LABEL_142:
      LODWORD(v134) = v46;
      if ( v46 )
        v49[v46] = 0;
      v5 = 0;
    }
    if ( v5 >= 0 )
    {
      v54 = 2 * v46;
      v55 = a1;
      memcpy_0(v49, a1, v54);
      v5 = 0;
      goto LABEL_150;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x235,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v5,
      lpString2);
  }
LABEL_149:
  v55 = a1;
LABEL_150:
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\stringhelper.cpp",
      (const char *)(unsigned int)v5,
      lpString2);
    if ( !v49 )
    {
LABEL_259:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BC,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filenamehelper.cpp",
        (const char *)(unsigned int)v5,
        lpString2c);
      operator delete(0, v100);
      v19 = 401;
      goto LABEL_31;
    }
LABEL_258:
    operator delete(v49, v99);
    goto LABEL_259;
  }
  if ( v49 )
  {
    v58 = v49;
    for ( ii = *v49; *v58; ii = *v58 )
    {
      if ( ii == 47 )
        *v58 = 92;
      ++v58;
    }
    v60 = -1;
    do
      ++v60;
    while ( v49[v60] );
    if ( v60 )
    {
      for ( jj = &v49[v60 - 1]; jj >= v49; --jj )
      {
        if ( *jj != 92 )
          break;
        *jj = 0;
      }
    }
  }
  if ( !(_DWORD)v134 )
  {
    v5 = -2147024773;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\stringhelper.cpp",
      (const char *)0x8007007BLL,
      lpString2);
    if ( !v49 )
      goto LABEL_259;
    goto LABEL_258;
  }
  v139 = 0;
  v61 = v140;
  if ( v140 >= 0xC && CompareStringEx(&LocaleName, 1u, (LPCWCH)v49, 12, L"appxmetadata", 12, 0, 0, 0) == 2 )
  {
    if ( v140 == 12 )
    {
      v5 = -2147024773;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D0,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filenamehelper.cpp",
        (const char *)0x8007007BLL,
        lpString2);
      operator delete(v49, v110);
      v19 = 401;
      goto LABEL_31;
    }
    v139 = v49[12] == 92;
  }
  operator delete(v49, v56);
  v134 = 0;
  v63 = 0;
  v135 = 0;
  v64 = 1073741822;
  v65 = v55;
  do
  {
    if ( !*v65 )
      break;
    ++v65;
    --v64;
  }
  while ( v64 );
  v5 = -2147024809;
  if ( v64 )
  {
    v5 = 0;
    v66 = 1073741822 - v64;
  }
  else
  {
    v66 = 0;
  }
  if ( !v64 )
  {
    v109 = 585;
    v67 = retaddr;
    goto LABEL_294;
  }
  v5 = -2147024362;
  if ( v66 <= 0x7FFFFFFF )
    v5 = 0;
  v67 = retaddr;
  if ( v66 > 0x7FFFFFFF )
  {
    v109 = 559;
LABEL_294:
    wil::details::in1diag3::_Log_Hr(
      v67,
      (void *)v109,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v5,
      lpString2);
    v69 = (__int16 *)*((_QWORD *)&v134 + 1);
    v75 = a1;
    v76 = 0;
    goto LABEL_196;
  }
  if ( !v66 )
  {
    v69 = (__int16 *)*((_QWORD *)&v134 + 1);
    goto LABEL_188;
  }
  if ( v66 <= 0x20 )
  {
    for ( kk = 8; kk < v66; kk *= 2 )
      ;
  }
  else
  {
    kk = v66;
  }
  if ( kk > 0x3FFFFFFF )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070503LL,
      lpString2);
    v5 = -2147023613;
    v69 = (__int16 *)*((_QWORD *)&v134 + 1);
  }
  else if ( kk )
  {
    v69 = (__int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    v70 = 2LL * (kk + 1);
    if ( !is_mul_ok(kk + 1, 2u) )
      v70 = -1;
    v72 = (__int16 *)operator new[](v70, (const struct std::nothrow_t *)&std::nothrow);
    if ( v72 )
    {
      operator delete(v69, v71);
      v69 = v72;
      v63 = kk + 1;
      v135 = kk + 1;
      *((_QWORD *)&v134 + 1) = v72;
      if ( (unsigned int)v134 > kk )
      {
        LODWORD(v134) = kk;
        v72[kk] = 0;
      }
      else if ( (unsigned int)v134 < kk && !(_DWORD)v134 )
      {
        *v72 = 0;
      }
      goto LABEL_183;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x8007000ELL,
      lpString2);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x8007000ELL,
      lpString2g);
    v5 = -2147024882;
  }
  else
  {
    v121 = (__int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    v69 = v121;
    if ( v121 )
    {
      operator delete(v121, v62);
      v69 = 0;
      *((_QWORD *)&v134 + 1) = 0;
      LODWORD(v134) = 0;
    }
    v135 = 0;
LABEL_183:
    v5 = 0;
  }
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v5,
      lpString2);
    v75 = a1;
    v76 = 0;
  }
  else
  {
    if ( v63 )
    {
      v73 = v63 - 1;
      goto LABEL_189;
    }
LABEL_188:
    v73 = 0;
LABEL_189:
    if ( v66 > v73 )
    {
      v117 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)&v134, v66);
      v5 = v117;
      if ( v117 >= 0 )
      {
        v69 = (__int16 *)*((_QWORD *)&v134 + 1);
        goto LABEL_190;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x20C,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v117,
        lpString2);
      v69 = (__int16 *)*((_QWORD *)&v134 + 1);
    }
    else
    {
LABEL_190:
      LODWORD(v134) = v66;
      if ( v66 )
        v69[v66] = 0;
      v5 = 0;
    }
    if ( v5 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x235,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v5,
        lpString2);
      v75 = a1;
      v76 = 0;
    }
    else
    {
      v74 = 2 * v66;
      v75 = a1;
      memcpy_0(v69, a1, v74);
      v76 = 0;
      v5 = 0;
    }
  }
  v61 = v140;
LABEL_196:
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\stringhelper.cpp",
      (const char *)(unsigned int)v5,
      lpString2);
    if ( !v69 )
    {
LABEL_262:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BC,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filenamehelper.cpp",
        (const char *)(unsigned int)v5,
        lpString2d);
      operator delete(0, v102);
      v19 = 408;
      goto LABEL_31;
    }
LABEL_261:
    operator delete(v69, v101);
    goto LABEL_262;
  }
  if ( v69 )
  {
    v77 = v69;
    v78 = *v69;
    if ( *v69 )
    {
      do
      {
        if ( v78 == 47 )
          *v77 = 92;
        v78 = *++v77;
      }
      while ( *v77 );
      v75 = a1;
    }
    v79 = -1;
    v80 = -1;
    do
      ++v80;
    while ( v69[v80] );
    if ( v80 )
    {
      for ( mm = &v69[v80 - 1]; mm >= v69; --mm )
      {
        if ( *mm != 92 )
          break;
        *mm = 0;
      }
    }
  }
  else
  {
    v79 = -1;
  }
  if ( !(_DWORD)v134 )
  {
    v5 = -2147024773;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\stringhelper.cpp",
      (const char *)0x8007007BLL,
      lpString2);
    if ( !v69 )
      goto LABEL_262;
    goto LABEL_261;
  }
  v81 = 0;
  if ( v61 >= 0x11 && CompareStringEx(&LocaleName, 1u, (LPCWCH)v69, 17, L"appxmetadata\\stub", 17, 0, 0, 0) == 2 )
  {
    if ( v61 == 17 )
    {
      v5 = -2147024773;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D0,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filenamehelper.cpp",
        (const char *)0x8007007BLL,
        lpString2);
      operator delete(v69, v111);
      v19 = 408;
      goto LABEL_31;
    }
    v81 = v69[17] == 92;
  }
  operator delete(v69, v76);
  v134 = 0;
  v83 = 0;
  v135 = 0;
  v84 = 1073741822;
  v85 = v75;
  do
  {
    if ( !*v85 )
      break;
    ++v85;
    --v84;
  }
  while ( v84 );
  v5 = -2147024809;
  if ( v84 )
  {
    v5 = 0;
    v86 = 1073741822 - v84;
    v133 = 1073741822 - v84;
  }
  else
  {
    v86 = 0;
    v133 = 0;
  }
  if ( v84 )
  {
    v5 = -2147024362;
    if ( v86 > 0x7FFFFFFF )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x22F,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)0x80070216LL,
        lpString2);
      v88 = (__int16 *)*((_QWORD *)&v134 + 1);
    }
    else
    {
      if ( !v86 )
      {
        v88 = (__int16 *)*((_QWORD *)&v134 + 1);
        goto LABEL_233;
      }
      if ( v86 <= 0x20 )
      {
        for ( nn = 8; nn < v86; nn *= 2 )
          ;
      }
      else
      {
        nn = v86;
      }
      if ( nn > 0x3FFFFFFF )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A9,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)0x80070503LL,
          lpString2);
        v5 = -2147023613;
        v88 = (__int16 *)*((_QWORD *)&v134 + 1);
      }
      else if ( nn )
      {
        v88 = (__int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        v89 = 2LL * (nn + 1);
        if ( !is_mul_ok(nn + 1, 2u) )
          v89 = -1;
        v91 = (__int16 *)operator new[](v89, (const struct std::nothrow_t *)&std::nothrow);
        if ( v91 )
        {
          operator delete(v88, v90);
          v88 = v91;
          v83 = nn + 1;
          v135 = nn + 1;
          *((_QWORD *)&v134 + 1) = v91;
          if ( (unsigned int)v134 > nn )
          {
            LODWORD(v134) = nn;
            v91[nn] = 0;
          }
          else if ( (unsigned int)v134 < nn && !(_DWORD)v134 )
          {
            *v91 = 0;
          }
          goto LABEL_228;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x193,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)0x8007000ELL,
          lpString2);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C4,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)0x8007000ELL,
          lpString2h);
        v5 = -2147024882;
      }
      else
      {
        v122 = (__int16 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
        v88 = v122;
        if ( v122 )
        {
          operator delete(v122, v82);
          v88 = 0;
          *((_QWORD *)&v134 + 1) = 0;
          LODWORD(v134) = 0;
        }
        v83 = 0;
        v135 = 0;
LABEL_228:
        v5 = 0;
      }
      if ( v5 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x232,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)(unsigned int)v5,
          lpString2);
      }
      else
      {
        v86 = v133;
        if ( v83 )
        {
          v92 = v83 - 1;
          goto LABEL_234;
        }
LABEL_233:
        v92 = 0;
LABEL_234:
        if ( v86 > v92 )
        {
          v118 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)&v134, v86);
          v5 = v118;
          if ( v118 >= 0 )
          {
            v88 = (__int16 *)*((_QWORD *)&v134 + 1);
            goto LABEL_235;
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x20C,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)(unsigned int)v118,
            lpString2);
          v88 = (__int16 *)*((_QWORD *)&v134 + 1);
        }
        else
        {
LABEL_235:
          LODWORD(v134) = v86;
          if ( v86 )
            v88[v86] = 0;
          v5 = 0;
        }
        if ( v5 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x235,
            (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
            (const char *)(unsigned int)v5,
            lpString2);
        }
        else
        {
          memcpy_0(v88, a1, 2 * v86);
          v5 = 0;
        }
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v5,
      lpString2);
    v88 = (__int16 *)*((_QWORD *)&v134 + 1);
  }
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\stringhelper.cpp",
      (const char *)(unsigned int)v5,
      lpString2);
    if ( !v88 )
    {
LABEL_265:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BC,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filenamehelper.cpp",
        (const char *)(unsigned int)v5,
        lpString2e);
      operator delete(0, v104);
      v19 = 415;
      goto LABEL_31;
    }
LABEL_264:
    operator delete(v88, v103);
    goto LABEL_265;
  }
  if ( v88 )
  {
    v94 = v88;
    v95 = *v88;
    if ( *v88 )
    {
      do
      {
        if ( v95 == 47 )
          *v94 = 92;
        v95 = *++v94;
      }
      while ( *v94 );
      v79 = -1;
    }
    do
      ++v79;
    while ( v88[v79] );
    if ( v79 )
    {
      for ( i1 = &v88[v79 - 1]; i1 >= v88; --i1 )
      {
        if ( *i1 != 92 )
          break;
        *i1 = 0;
      }
    }
  }
  if ( !(_DWORD)v134 )
  {
    v5 = -2147024773;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\stringhelper.cpp",
      (const char *)0x8007007BLL,
      lpString2);
    if ( !v88 )
      goto LABEL_265;
    goto LABEL_264;
  }
  v96 = 0;
  if ( v140 >= 0x1E
    && CompareStringEx(&LocaleName, 1u, (LPCWCH)v88, 30, L"AppxMetadata\\PublisherBridging", 30, 0, 0, 0) == 2 )
  {
    if ( v140 == 30 )
    {
      v5 = -2147024773;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D0,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\filenamehelper.cpp",
        (const char *)0x8007007BLL,
        lpString2a);
      operator delete(v88, v112);
      v19 = 415;
      goto LABEL_31;
    }
    v96 = v88[30] == 92;
  }
  operator delete(v88, v93);
  if ( !v139 || v81 || v96 )
  {
    *a2 = 0;
    return 0;
  }
  else
  {
    *a2 = 1;
    return 0;
  }
}

```

## disassembly

```asm
0x180011d60  mov     [rsp-8+arg_8], rdx
0x180011d65  mov     [rsp-8+Src], rcx
0x180011d6a  push    rbp
0x180011d6b  push    rbx
0x180011d6c  push    rsi
0x180011d6d  push    rdi
0x180011d6e  push    r12
0x180011d70  push    r13
0x180011d72  push    r14
0x180011d74  push    r15
0x180011d76  lea     rbp, [rsp-1Fh]
0x180011d7b  sub     rsp, 88h
0x180011d82  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x180011d8a  mov     rdx, rcx; unsigned __int64
0x180011d8d  test    rcx, rcx
0x180011d90  jz      loc_1800133E4
0x180011d96  mov     r8d, 7FFFFFFFh
0x180011d9c  mov     rax, rcx
0x180011d9f  nop
0x180011da0  cmp     word ptr [rax], 0
0x180011da4  jz      short loc_180011DB0
0x180011da6  add     rax, 2
0x180011daa  sub     r8, 1
0x180011dae  jnz     short loc_180011DA0
0x180011db0  mov     ebx, 80070057h
0x180011db5  xor     eax, eax
0x180011db7  test    r8, r8
0x180011dba  cmovnz  ebx, eax
0x180011dbd  jz      loc_1800130C5
0x180011dc3  mov     ecx, 7FFFFFFFh
0x180011dc8  sub     rcx, r8
0x180011dcb  mov     [rbp+57h+arg_18], rcx
0x180011dcf  test    r8, r8
0x180011dd2  jz      loc_1800133E9
0x180011dd8  lea     rax, [rcx-1]
0x180011ddc  cmp     rax, 7FFEh
0x180011de2  ja      loc_1800133D5
0x180011de8  cmp     word ptr [rdx], 5Ch ; '\'
0x180011dec  jz      loc_1800133D5
0x180011df2  xor     esi, esi
0x180011df4  xor     ebx, ebx
0x180011df6  lea     rdi, [rdx+rcx*2]
0x180011dfa  xor     ecx, ecx
0x180011dfc  xor     r9d, r9d
0x180011dff  mov     r8, rdx
0x180011e02  lea     r12, __ImageBase
0x180011e09  mov     r10d, 2800h
0x180011e0f  mov     r13d, 3FFh
0x180011e15  mov     r11, 1000000000004001h
0x180011e1f  mov     [rbp+57h+arg_10], 2400h
0x180011e26  mov     r14, [rbp+57h+Src]
0x180011e2a  mov     r15d, dword ptr [rbp+57h+Src]
0x180011e2e  mov     eax, 0FFFDh
0x180011e33  cmp     r8, rdi
0x180011e36  jnb     loc_180011F67
0x180011e3c  movzx   edx, word ptr [r8]
0x180011e40  cmp     edx, 7Dh ; '}'
0x180011e43  jnb     loc_18001204C
0x180011e49  cmp     byte ptr [rdx+r12+14CF20h], 0
0x180011e52  jnz     loc_1800130DB
0x180011e58  cmp     edx, 5Ch ; '\'
0x180011e5b  jz      short loc_180011EC1
0x180011e5d  cmp     ebx, 1
0x180011e60  jnz     short loc_180011E74
0x180011e62  inc     r9d
0x180011e65  mov     r10d, 2800h
0x180011e6b  movzx   ecx, dx
0x180011e6e  add     r8, 2
0x180011e72  jmp     short loc_180011E2E
0x180011e74  test    rsi, rsi
0x180011e77  jnz     loc_180011F27
0x180011e7d  xor     r10d, r10d
0x180011e80  cmp     r10d, 5
0x180011e84  jnb     short loc_180011EB0
0x180011e86  movsxd  r11, r10d
0x180011e89  add     r11, r11
0x180011e8c  mov     rax, ds:rva off_180109B18[r12+r11*8]; "AUX" ...
0x180011e94  movzx   ecx, word ptr [rax]
0x180011e97  cmp     dx, cx
0x180011e9a  jz      loc_180011FAD
0x180011ea0  add     ecx, 20h ; ' '
0x180011ea3  cmp     edx, ecx
0x180011ea5  jz      loc_180011FAD
0x180011eab  inc     r10d
0x180011eae  jmp     short loc_180011E80
0x180011eb0  mov     ebx, 1
0x180011eb5  mov     r11, 1000000000004001h
0x180011ebf  jmp     short loc_180011E62
0x180011ec1  lea     eax, [r10+rcx]
0x180011ec5  cmp     ax, r13w
0x180011ec9  jbe     short loc_180011EF3
0x180011ecb  sub     cx, 20h ; ' '
0x180011ecf  cmp     cx, 3Ch ; '<'
0x180011ed3  jbe     loc_180011FCC
0x180011ed9  cmp     r9d, 0FFh
0x180011ee0  ja      short loc_180011EF3
0x180011ee2  test    ebx, ebx
0x180011ee4  jz      loc_180012034
0x180011eea  cmp     ebx, 2
0x180011eed  jnz     loc_180012040
0x180011ef3  mov     ebx, 8007007Bh
0x180011ef8  mov     edx, 16Ch; void *
0x180011efd  mov     r9d, ebx; char *
0x180011f00  lea     r8, aOnecorePrintsc_38; "onecore\\printscan\\appxpackaging\\lib"...
0x180011f07  mov     rcx, [rbp+5Fh]; this
0x180011f0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011f10  mov     eax, ebx
0x180011f12  add     rsp, 88h
0x180011f19  pop     r15
0x180011f1b  pop     r14
0x180011f1d  pop     r13
0x180011f1f  pop     r12
0x180011f21  pop     rdi
0x180011f22  pop     rsi
0x180011f23  pop     rbx
0x180011f24  pop     rbp
0x180011f25  retn
0x180011f27  mov     eax, r15d
0x180011f2a  cmp     rsi, rax
0x180011f2d  jnb     loc_180011FF6
0x180011f33  movzx   r10d, word ptr [r14+rsi*2]
0x180011f38  cmp     dx, r10w
0x180011f3c  jz      short loc_180011F5F
0x180011f3e  lea     ecx, [r10+20h]
0x180011f42  cmp     edx, ecx
0x180011f44  jz      short loc_180011F5F
0x180011f46  cmp     r10d, 3Fh ; '?'
0x180011f4a  jz      loc_180011FDE
0x180011f50  cmp     r10d, 31h ; '1'
0x180011f54  jz      loc_180012022
0x180011f5a  mov     ebx, 1
0x180011f5f  inc     rsi
0x180011f62  jmp     loc_180011E62
0x180011f67  lea     eax, [r10+rcx]
0x180011f6b  cmp     ax, r13w
0x180011f6f  jbe     short loc_180011F9E
0x180011f71  sub     cx, 20h ; ' '
0x180011f75  cmp     cx, 3Ch ; '<'
0x180011f79  ja      short loc_180011F84
0x180011f7b  movzx   eax, cx
0x180011f7e  bt      r11, rax
0x180011f82  jb      short loc_180011F9E
0x180011f84  cmp     r9d, 0FFh
0x180011f8b  ja      short loc_180011F9E
0x180011f8d  test    ebx, ebx
0x180011f8f  jz      loc_180012083
0x180011f95  cmp     ebx, 2
0x180011f98  jnz     loc_18001208F
0x180011f9e  mov     ebx, 8007007Bh
0x180011fa3  mov     edx, 17Fh
0x180011fa8  jmp     loc_180011EFD
0x180011fad  mov     r15d, ds:rva ?DeviceNameTable@DeviceNameChecker@FileNameHelper@Packaging@Appx@@0QBUCOMMON_STRING@Common@@B[r12+r11*8]; Common::COMMON_STRING const near * const Appx::Packaging::FileNameHelper::DeviceNameChecker::DeviceNameTable ...
0x180011fb5  mov     r14, rax
0x180011fb8  mov     esi, 1
0x180011fbd  mov     r11, 1000000000004001h
0x180011fc7  jmp     loc_180011E62
0x180011fcc  movzx   eax, cx
0x180011fcf  bt      r11, rax
0x180011fd3  jnb     loc_180011ED9
0x180011fd9  jmp     loc_180011EF3
0x180011fde  lea     eax, [rdx-4Eh]
0x180011fe1  mov     ecx, 0FFDFh
0x180011fe6  test    cx, ax
0x180011fe9  jnz     short loc_18001200E
0x180011feb  dec     r15d
0x180011fee  inc     rsi
0x180011ff1  jmp     loc_180011E62
0x180011ff6  mov     eax, ebx
0x180011ff8  cmp     edx, 2Eh ; '.'
0x180011ffb  jz      loc_1800130CC
0x180012001  test    ebx, ebx
0x180012003  jz      loc_180011F5A
0x180012009  jmp     loc_180011F5F
0x18001200e  lea     eax, [rdx-4Dh]
0x180012011  test    cx, ax
0x180012014  jnz     loc_180011F5A
0x18001201a  inc     rsi
0x18001201d  jmp     loc_180011E62
0x180012022  lea     eax, [rdx-31h]
0x180012025  cmp     ax, 8
0x180012029  jbe     loc_180011F5F
0x18001202f  jmp     loc_180011F5A
0x180012034  mov     eax, r15d
0x180012037  cmp     rsi, rax
0x18001203a  jz      loc_180011EF3
0x180012040  xor     esi, esi
0x180012042  xor     ebx, ebx
0x180012044  xor     r9d, r9d
0x180012047  jmp     loc_180011E6B
0x18001204c  cmp     dx, ax
0x18001204f  ja      loc_1800121D0
0x180012055  movzx   eax, dx
0x180012058  add     ax, word ptr [rbp+57h+arg_10]
0x18001205c  add     cx, r10w
0x180012060  cmp     ax, r13w
0x180012064  ja      loc_1800121B7
0x18001206a  cmp     cx, r13w
0x18001206e  jbe     loc_180011E5D
0x180012074  mov     ebx, 8007007Bh
0x180012079  mov     edx, 15Eh
0x18001207e  jmp     loc_180011EFD
0x180012083  mov     eax, r15d
0x180012086  cmp     rsi, rax
0x180012089  jz      loc_180011F9E
0x18001208f  xorps   xmm0, xmm0
0x180012092  movups  [rbp+57h+var_60], xmm0
0x180012096  xor     r13d, r13d
0x180012099  mov     [rbp+57h+var_50], r13d
0x18001209d  mov     r14d, 3FFFFFFEh
0x1800120a3  mov     ecx, r14d
0x1800120a6  mov     rax, [rbp+57h+Src]
0x1800120aa  nop     word ptr [rax+rax+00h]
0x1800120b0  cmp     [rax], r13w
0x1800120b4  jz      short loc_1800120C0
0x1800120b6  add     rax, 2
0x1800120ba  sub     rcx, 1
0x1800120be  jnz     short loc_1800120B0
0x1800120c0  mov     ebx, 80070057h
0x1800120c5  xor     eax, eax
0x1800120c7  test    rcx, rcx
0x1800120ca  cmovnz  ebx, eax
0x1800120cd  jz      loc_1800130EA
0x1800120d3  mov     rdi, r14
0x1800120d6  sub     rdi, rcx
0x1800120d9  mov     rax, [rbp+5Fh]
0x1800120dd  mov     esi, 8
0x1800120e2  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1800120e9  test    rcx, rcx
0x1800120ec  jz      loc_1800130F1
0x1800120f2  mov     ebx, 80070216h
0x1800120f7  xor     eax, eax
0x1800120f9  cmp     edi, 7FFFFFFFh
0x1800120ff  cmovbe  ebx, eax
0x180012102  mov     rcx, [rbp+5Fh]; this
0x180012106  ja      loc_180012F0D
0x18001210c  test    edi, edi
0x18001210e  jz      loc_1800121DF
0x180012114  cmp     edi, 20h ; ' '
0x180012117  jbe     loc_180012EF8
0x18001211d  mov     ebx, edi
0x18001211f  cmp     ebx, 3FFFFFFFh
0x180012125  ja      loc_1800130FE
0x18001212b  test    ebx, ebx
0x18001212d  jz      loc_180013127
0x180012133  lea     esi, [rbx+1]
0x180012136  test    esi, esi
0x180012138  jz      loc_180013163
0x18001213e  psrldq  xmm0, 8
0x180012143  movq    r15, xmm0
0x180012148  mov     ecx, esi
0x18001214a  mov     eax, 2
0x18001214f  mul     rcx
0x180012152  cmovb   rax, r12
0x180012156  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001215d  mov     rcx, rax; unsigned __int64
0x180012160  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180012165  mov     r14, rax
0x180012168  test    rax, rax
0x18001216b  jz      loc_180012F51
0x180012171  mov     rcx, r15; void *
0x180012174  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012179  mov     r15, r14
0x18001217c  mov     r13d, esi
0x18001217f  mov     [rbp+57h+var_50], esi
0x180012182  mov     qword ptr [rbp+57h+var_60+8], r14
0x180012186  cmp     dword ptr [rbp+57h+var_60], ebx
0x180012189  ja      loc_180013152
0x18001218f  mov     eax, dword ptr [rbp+57h+var_60]
0x180012192  cmp     eax, ebx
0x180012194  jnb     short loc_18001219E
0x180012196  test    eax, eax
0x180012198  jnz     short loc_18001219E
0x18001219a  mov     [r14], ax
0x18001219e  xor     ebx, ebx
0x1800121a0  mov     rcx, [rbp+5Fh]; this
0x1800121a4  test    ebx, ebx
0x1800121a6  js      loc_180012F31
0x1800121ac  test    r13d, r13d
0x1800121af  jz      short loc_1800121E3
0x1800121b1  lea     eax, [r13-1]
0x1800121b5  jmp     short loc_1800121E5
0x1800121b7  cmp     cx, r13w
0x1800121bb  ja      loc_180011E5D
0x1800121c1  mov     ebx, 8007007Bh
0x1800121c6  mov     edx, 163h
0x1800121cb  jmp     loc_180011EFD
0x1800121d0  mov     ebx, 8007007Bh
0x1800121d5  mov     edx, 159h
0x1800121da  jmp     loc_180011EFD
0x1800121df  mov     r15, qword ptr [rbp+57h+var_60+8]
0x1800121e3  xor     eax, eax
0x1800121e5  cmp     edi, eax
0x1800121e7  ja      loc_180012F91
0x1800121ed  mov     dword ptr [rbp+57h+var_60], edi
0x1800121f0  test    edi, edi
0x1800121f2  jz      short loc_1800121FD
0x1800121f4  mov     ecx, edi
0x1800121f6  xor     eax, eax
0x1800121f8  mov     [r15+rcx*2], ax
0x1800121fd  xor     ebx, ebx
  ... truncated ...
```
