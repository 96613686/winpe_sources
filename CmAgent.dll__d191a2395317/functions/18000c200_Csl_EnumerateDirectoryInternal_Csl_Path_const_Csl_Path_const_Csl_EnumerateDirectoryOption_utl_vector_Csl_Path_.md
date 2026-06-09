# Csl::EnumerateDirectoryInternal(Csl::Path const &,Csl::Path const &,Csl::EnumerateDirectoryOption,utl::vector<Csl::Path,utl::allocator<Csl::Path>> &,ushort const *)

- ea: `0x18000c200`
- end: `0x18000cb4f`
- name: `?EnumerateDirectoryInternal@Csl@@YAJAEBVPath@1@0W4EnumerateDirectoryOption@1@AEAV?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@PEBG@Z`
- size: `2383`
- prototype: `__int64 __fastcall(const void **, __int64, int, __int64, _WORD *)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, loader_planting`

## callers

- `0x18000bd28`
- `0x18000c200`
- `0x1800282d4`

## callees

- `0x180002140`
- `0x180002534`
- `0x180002c48`
- `0x1800045e4`
- `0x180007b2c`
- `0x18000adb8`
- `0x18000af30`
- `0x18000b938`
- `0x18000b9b8`
- `0x18000ba80`
- `0x18000bb98`
- `0x18000bd28`
- `0x18000c200`
- `0x18000cf40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c55b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c55b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9e9`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000c76f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000c7e5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000c884`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000c76f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000c7e5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000c884`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18000c543`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18000c543`

## pseudocode

```c
__int64 __fastcall Csl::EnumerateDirectoryInternal(const void **a1, __int64 a2, int a3, __int64 a4, _WORD *a5)
{
  int v6; // ebx
  __int64 v7; // r8
  const void *v8; // rdx
  void *v9; // rcx
  __m128i si128; // xmm6
  LPCWSTR v11; // rcx
  int v12; // ebx
  void *v13; // rcx
  bool v14; // zf
  _QWORD *i; // rbx
  _QWORD *v17; // rdi
  const void **v18; // rdi
  __int64 v19; // r14
  __int64 v20; // rbx
  __int64 v21; // r8
  const void *v22; // rdx
  __int64 v23; // rax
  HANDLE FirstFile; // rax
  const char *v25; // r9
  unsigned int LastError; // eax
  LPCWSTR v27; // rcx
  unsigned int v28; // esi
  void *v29; // rdi
  _OWORD *v30; // rcx
  __int64 v31; // rdx
  char *v32; // rax
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm1
  __int64 v41; // r8
  const void *v42; // rdx
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  void *v46; // rsi
  unsigned __int64 v47; // r14
  unsigned __int64 v48; // rdx
  char v49; // al
  LPCWSTR v50; // rcx
  void *v51; // rcx
  __int64 v52; // rdx
  LPCWSTR v53; // rcx
  void *v54; // rdi
  void *v55; // r12
  __int64 v56; // rdi
  int v57; // esi
  __int64 v58; // r14
  const char *v59; // r9
  unsigned int v60; // edi
  __int64 v61; // rcx
  __int64 v62; // r13
  __m128i v63; // rdi
  __int64 v64; // r14
  __int64 v65; // rcx
  int lpSearchFilter; // [rsp+28h] [rbp-E0h]
  __m128i dwAdditionalFlags_8; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v68; // [rsp+48h] [rbp-C0h]
  void *v69[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int16 v70; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v71[4]; // [rsp+70h] [rbp-98h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+90h] [rbp-78h] BYREF
  _WORD v73[8]; // [rsp+A0h] [rbp-68h] BYREF
  void *v74[2]; // [rsp+B0h] [rbp-58h] BYREF
  __int16 v75; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v76; // [rsp+C2h] [rbp-46h]
  int v77; // [rsp+CAh] [rbp-3Eh]
  __int16 v78; // [rsp+CEh] [rbp-3Ah]
  __int64 v79; // [rsp+D0h] [rbp-38h]
  __int64 v80; // [rsp+D8h] [rbp-30h]
  _QWORD v81[3]; // [rsp+E0h] [rbp-28h] BYREF
  HANDLE hFindFile; // [rsp+F8h] [rbp-10h] BYREF
  char v83; // [rsp+100h] [rbp-8h] BYREF
  void *v84[2]; // [rsp+350h] [rbp+248h] BYREF
  _WORD v85[12]; // [rsp+360h] [rbp+258h] BYREF
  _BYTE FindFileData[592]; // [rsp+378h] [rbp+270h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+630h] [rbp+528h]

  LODWORD(v71[0]) = a3;
  v6 = (int)a1;
  v7 = (_BYTE *)a1[1] - (_BYTE *)*a1;
  v79 = a2;
  v8 = *a1;
  v69[0] = &v70;
  v80 = a4;
  v69[1] = &v70;
  v70 = 0;
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)v69,
          v8,
          v7 >> 1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)0x8007000ELL,
      lpSearchFilter);
    goto LABEL_3;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *(__m128i *)&v71[1] = si128;
  v71[3] = -1;
  if ( !utl::vector<Csl::Path,utl::allocator<Csl::Path>>::emplace_back<Csl::Path,0>(&v71[1], v69) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3AB,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)0x8007000ELL,
      lpSearchFilter);
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v71[1]);
LABEL_3:
    v9 = v69[0];
    if ( v69[0] == &v70 )
      return 2147942414LL;
LABEL_77:
    operator delete(v9, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  if ( (a3 & 4) != 0 && *a5 == 42 && a5[1] )
  {
    v68 = -1;
    v74[0] = &v75;
    v76 = 0;
    v74[1] = &v75;
    v77 = 0;
    v78 = 0;
    dwAdditionalFlags_8 = si128;
    v75 = 0;
    v12 = Csl::EnumerateDirectoryInternal(v6, (unsigned int)v74, 7, (unsigned int)&dwAdditionalFlags_8, (__int64)L"*");
    if ( v74[0] != &v75 )
      operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v12 == -2147024894 )
    {
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&dwAdditionalFlags_8);
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v71[1]);
      v13 = v69[0];
      v14 = v69[0] == &v70;
LABEL_83:
      if ( !v14 )
        operator delete(v13, (const struct std::nothrow_t *)&std::nothrow);
      return 2147942402LL;
    }
    else
    {
      if ( v12 >= 0 )
      {
        v17 = (_QWORD *)dwAdditionalFlags_8.m128i_i64[1];
        for ( i = (_QWORD *)dwAdditionalFlags_8.m128i_i64[0]; ; i += 4 )
        {
          if ( i == v17 )
          {
            LODWORD(v71[0]) = a3 & 0xFFFFFFFB;
            utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&dwAdditionalFlags_8);
            si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
            goto LABEL_24;
          }
          if ( !utl::vector<Csl::Path,utl::allocator<Csl::Path>>::emplace_back<Csl::Path,0>(&v71[1], i) )
            break;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3CC,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
          (const char *)0x8007000ELL,
          lpSearchFilter);
        utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&dwAdditionalFlags_8);
LABEL_76:
        utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v71[1]);
        v9 = v69[0];
        if ( v69[0] == &v70 )
          return 2147942414LL;
        goto LABEL_77;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3C6,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
        (const char *)(unsigned int)v12,
        lpSearchFilter);
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&dwAdditionalFlags_8);
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v71[1]);
      if ( v69[0] != &v70 )
        operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
      return (unsigned int)v12;
    }
  }
  else
  {
LABEL_24:
    v18 = (const void **)v71[1];
    v19 = -1;
    dwAdditionalFlags_8 = si128;
    v20 = si128.m128i_i64[1];
    v68 = -1;
    while ( v18 != (const void **)v71[2] )
    {
      memset_0(FindFileData, 0, sizeof(FindFileData));
      v21 = (_BYTE *)v18[1] - (_BYTE *)*v18;
      v22 = *v18;
      lpFileName[0] = v73;
      lpFileName[1] = v73;
      v73[0] = 0;
      if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
              (__int64)lpFileName,
              v22,
              v21 >> 1) )
      {
        v52 = 988;
LABEL_70:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v52,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
          (const char *)0x8007000ELL,
          lpSearchFilter);
LABEL_71:
        v53 = lpFileName[0];
        if ( lpFileName[0] != v73 )
          operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
        v54 = (void *)dwAdditionalFlags_8.m128i_i64[0];
        if ( dwAdditionalFlags_8.m128i_i64[0] != -1 )
        {
          utl::_RangeDestroyApc<utl::allocator<Csl::FindFirstFileInformation>>(
            v53,
            dwAdditionalFlags_8.m128i_i64[0],
            (v20 - dwAdditionalFlags_8.m128i_i64[0]) / 632);
          v51 = v54;
          goto LABEL_75;
        }
        goto LABEL_76;
      }
      v81[0] = a5;
      v23 = -1;
      do
        ++v23;
      while ( a5[v23] );
      v81[1] = v23;
      if ( !Csl::Path::Append((Csl::Path *)lpFileName, (__int64)v81) )
      {
        v52 = 989;
        goto LABEL_70;
      }
      FirstFile = FindFirstFileExW(lpFileName[0], FindExInfoBasic, FindFileData, FindExSearchNameMatch, 0, 2u);
      if ( FirstFile == (HANDLE)-1LL )
      {
        if ( GetLastError() != 2 )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x3EE,
                        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
                        v25);
          v27 = lpFileName[0];
          v28 = LastError;
          if ( lpFileName[0] != v73 )
            operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
          v29 = (void *)dwAdditionalFlags_8.m128i_i64[0];
          if ( dwAdditionalFlags_8.m128i_i64[0] != -1 )
          {
            utl::_RangeDestroyApc<utl::allocator<Csl::FindFirstFileInformation>>(
              v27,
              dwAdditionalFlags_8.m128i_i64[0],
              (v20 - dwAdditionalFlags_8.m128i_i64[0]) / 632);
            operator delete(v29, (const struct std::nothrow_t *)&std::nothrow);
          }
          utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v71[1]);
          if ( v69[0] != &v70 )
            operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
          return v28;
        }
      }
      else
      {
        hFindFile = FirstFile;
        v84[0] = v85;
        v30 = FindFileData;
        v85[0] = 0;
        v31 = 4;
        v84[1] = v85;
        v32 = &v83;
        do
        {
          v33 = v30[1];
          *(_OWORD *)v32 = *v30;
          v34 = v30[2];
          *((_OWORD *)v32 + 1) = v33;
          v35 = v30[3];
          *((_OWORD *)v32 + 2) = v34;
          v36 = v30[4];
          *((_OWORD *)v32 + 3) = v35;
          v37 = v30[5];
          *((_OWORD *)v32 + 4) = v36;
          v38 = v30[6];
          *((_OWORD *)v32 + 5) = v37;
          v39 = v30[7];
          v30 += 8;
          *((_OWORD *)v32 + 6) = v38;
          *((_OWORD *)v32 + 7) = v39;
          v32 += 128;
          --v31;
        }
        while ( v31 );
        v40 = v30[1];
        v41 = (_BYTE *)v18[1] - (_BYTE *)*v18;
        v42 = *v18;
        *(_OWORD *)v32 = *v30;
        v43 = v30[2];
        *((_OWORD *)v32 + 1) = v40;
        v44 = v30[3];
        *((_OWORD *)v32 + 2) = v43;
        v45 = v30[4];
        *((_OWORD *)v32 + 3) = v44;
        *((_OWORD *)v32 + 4) = v45;
        if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                (__int64)v84,
                v42,
                v41 >> 1) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3F5,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
            (const char *)0x8007000ELL,
            lpSearchFilter);
          if ( v84[0] != v85 )
            operator delete(v84[0], (const struct std::nothrow_t *)&std::nothrow);
          if ( (char *)hFindFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            FindClose(hFindFile);
          goto LABEL_71;
        }
        if ( v20 == v19 )
        {
          v46 = (void *)dwAdditionalFlags_8.m128i_i64[0];
          v47 = 0x9B8B577E613716AFuLL * ((v19 - dwAdditionalFlags_8.m128i_i64[0]) >> 3);
          v48 = 7 * (v47 >> 2) + 8;
          if ( v48 > 0x33D91D2A2067B2LL )
            v48 = 0x33D91D2A2067B2LL;
          if ( v47 >= v48 )
            goto LABEL_56;
          v49 = utl::vector<Csl::FindFirstFileInformation,utl::allocator<Csl::FindFirstFileInformation>>::_SetCapacity(&dwAdditionalFlags_8);
          v20 = dwAdditionalFlags_8.m128i_i64[1];
          if ( !v49 )
          {
            v46 = (void *)dwAdditionalFlags_8.m128i_i64[0];
LABEL_56:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3F7,
              (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
              (const char *)0x8007000ELL,
              lpSearchFilter);
            if ( v84[0] != v85 )
              operator delete(v84[0], (const struct std::nothrow_t *)&std::nothrow);
            if ( (char *)hFindFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
              FindClose(hFindFile);
            v50 = lpFileName[0];
            if ( lpFileName[0] != v73 )
              operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
            if ( v46 != (void *)-1LL )
            {
              utl::_RangeDestroyApc<utl::allocator<Csl::FindFirstFileInformation>>(v50, v46, (v20 - (__int64)v46) / 632);
              v51 = v46;
LABEL_75:
              operator delete(v51, (const struct std::nothrow_t *)&std::nothrow);
              goto LABEL_76;
            }
            goto LABEL_76;
          }
          v19 = v68;
        }
        Csl::FindFirstFileInformation::FindFirstFileInformation(v20, &hFindFile);
        v20 += 632;
        dwAdditionalFlags_8.m128i_i64[1] = v20;
        if ( v84[0] != v85 )
          operator delete(v84[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( (char *)hFindFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          FindClose(hFindFile);
      }
      v11 = lpFileName[0];
      if ( lpFileName[0] != v73 )
        operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
      v18 += 4;
    }
    v55 = (void *)dwAdditionalFlags_8.m128i_i64[0];
    if ( dwAdditionalFlags_8.m128i_i64[0] == v20 )
    {
      if ( dwAdditionalFlags_8.m128i_i64[0] != -1 )
      {
        utl::_RangeDestroyApc<utl::allocator<Csl::FindFirstFileInformation>>(
          v11,
          dwAdditionalFlags_8.m128i_i64[0],
          (v20 - dwAdditionalFlags_8.m128i_i64[0]) / 632);
        operator delete(v55, (const struct std::nothrow_t *)&std::nothrow);
      }
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v71[1]);
      v13 = v69[0];
      v14 = v69[0] == &v70;
      goto LABEL_83;
    }
    v56 = dwAdditionalFlags_8.m128i_i64[0];
    v57 = v71[0];
    v58 = v79;
    dwAdditionalFlags_8 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v68 = -1;
    while ( v56 != v20 )
    {
      Csl::EnumerateDirectoryInternal(v56, v58, v57, (__int64)a5, dwAdditionalFlags_8.m128i_i64);
      v56 += 632;
    }
    if ( GetLastError() == 18 )
    {
      v62 = v80;
      v63 = dwAdditionalFlags_8;
      v64 = v68;
      dwAdditionalFlags_8 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
      v68 = -1;
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(v80);
      *(__m128i *)v62 = v63;
      *(_QWORD *)(v62 + 16) = v64;
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&dwAdditionalFlags_8);
      if ( v55 != (void *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<Csl::FindFirstFileInformation>>(v65, v55, (v20 - (__int64)v55) / 632);
        operator delete(v55, (const struct std::nothrow_t *)&std::nothrow);
      }
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v71[1]);
      if ( v69[0] != &v70 )
        operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
      return 0;
    }
    else
    {
      v60 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x415,
              (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
              v59);
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&dwAdditionalFlags_8);
      if ( v55 != (void *)-1LL )
      {
        utl::_RangeDestroyApc<utl::allocator<Csl::FindFirstFileInformation>>(v61, v55, (v20 - (__int64)v55) / 632);
        operator delete(v55, (const struct std::nothrow_t *)&std::nothrow);
      }
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&v71[1]);
      if ( v69[0] != &v70 )
        operator delete(v69[0], (const struct std::nothrow_t *)&std::nothrow);
      return v60;
    }
  }
}

```

## disassembly

```asm
0x18000c200  mov     rax, rsp
0x18000c203  push    rbp
0x18000c204  push    rbx
0x18000c205  push    rsi
0x18000c206  push    rdi
0x18000c207  push    r12
0x18000c209  push    r13
0x18000c20b  push    r14
0x18000c20d  push    r15
0x18000c20f  lea     rbp, [rax-528h]
0x18000c216  sub     rsp, 5E8h
0x18000c21d  movaps  xmmword ptr [rax-58h], xmm6
0x18000c221  mov     rax, cs:__security_cookie
0x18000c228  xor     rax, rsp
0x18000c22b  mov     [rbp+520h+var_60], rax
0x18000c232  mov     r13, [rbp+520h+arg_20]
0x18000c239  lea     rax, [rsp+620h+var_5C8]
0x18000c23e  mov     esi, r8d
0x18000c241  mov     dword ptr [rsp+620h+var_5B8], r8d
0x18000c246  mov     r8, [rcx+8]
0x18000c24a  mov     rbx, rcx
0x18000c24d  sub     r8, [rcx]
0x18000c250  xor     r14d, r14d
0x18000c253  mov     [rbp+520h+var_558], rdx
0x18000c257  mov     rdx, [rcx]
0x18000c25a  lea     rcx, [rsp+620h+var_5D8]
0x18000c25f  mov     [rsp+620h+var_5D8], rax
0x18000c264  lea     rax, [rsp+620h+var_5C8]
0x18000c269  sar     r8, 1
0x18000c26c  mov     [rbp+520h+var_550], r9
0x18000c270  mov     qword ptr [rsp+620h+var_5D0], rax
0x18000c275  mov     [rsp+620h+var_5C8], r14w
0x18000c27b  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000c280  test    al, al
0x18000c282  jnz     short loc_18000C2C1
0x18000c284  mov     rcx, [rbp+528h]; this
0x18000c28b  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000c292  mov     r9d, 8007000Eh; char *
0x18000c298  mov     edx, 3A8h; void *
0x18000c29d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c2a2  mov     rcx, [rsp+620h+var_5D8]
0x18000c2a7  lea     rax, [rsp+620h+var_5C8]
0x18000c2ac  cmp     rcx, rax
0x18000c2af  jz      loc_18000C928
0x18000c2b5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000c2bc  jmp     loc_18000C923
0x18000c2c1  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000c2c9  lea     rdx, [rsp+620h+var_5D8]
0x18000c2ce  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000c2d2  lea     rcx, [rsp+620h+var_5B8+8]
0x18000c2d7  movdqu  xmmword ptr [rsp+620h+var_5B8+8], xmm6
0x18000c2dd  mov     [rbp+520h+var_5A0], r12
0x18000c2e1  call    ??$emplace_back@VPath@Csl@@$0A@@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@QEAA_N$$QEAVPath@Csl@@@Z; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::emplace_back<Csl::Path,0>(Csl::Path &&)
0x18000c2e6  test    al, al
0x18000c2e8  jnz     short loc_18000C314
0x18000c2ea  mov     rcx, [rbp+528h]; this
0x18000c2f1  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000c2f8  mov     r9d, 8007000Eh; char *
0x18000c2fe  mov     edx, 3ABh; void *
0x18000c303  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c308  lea     rcx, [rsp+620h+var_5B8+8]
0x18000c30d  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18000c312  jmp     short loc_18000C2A2
0x18000c314  lea     r15, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000c31b  test    sil, 4
0x18000c31f  jz      loc_18000C48E
0x18000c325  cmp     word ptr [r13+0], 2Ah ; '*'
0x18000c32b  jnz     loc_18000C48E
0x18000c331  cmp     [r13+2], r14w
0x18000c336  jz      loc_18000C48E
0x18000c33c  lea     rax, [rbp+520h+var_568]
0x18000c340  mov     [rsp+620h+var_5E0], r12
0x18000c345  mov     [rbp+520h+var_578], rax
0x18000c349  lea     r9, [rsp+620h+dwAdditionalFlags+8]
0x18000c34e  lea     rax, [rbp+520h+var_568]
0x18000c352  mov     [rbp+520h+var_566], r14
0x18000c356  mov     [rbp+520h+var_570], rax
0x18000c35a  lea     rdx, [rbp+520h+var_578]
0x18000c35e  lea     rax, asc_18003FBC4; "*"
0x18000c365  mov     [rbp+520h+var_55E], r14d
0x18000c369  mov     r8d, 7
0x18000c36f  mov     [rsp+620h+lpSearchFilter], rax; int
0x18000c374  mov     rcx, rbx
0x18000c377  mov     [rbp+520h+var_55A], r14w
0x18000c37c  movdqu  xmmword ptr [rsp+620h+dwAdditionalFlags+8], xmm6
0x18000c382  mov     [rbp+520h+var_568], r14w
0x18000c387  call    ?EnumerateDirectoryInternal@Csl@@YAJAEBVPath@1@0W4EnumerateDirectoryOption@1@AEAV?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@PEBG@Z; Csl::EnumerateDirectoryInternal(Csl::Path const &,Csl::Path const &,Csl::EnumerateDirectoryOption,utl::vector<Csl::Path,utl::allocator<Csl::Path>> &,ushort const *)
0x18000c38c  mov     rcx, [rbp+520h+var_578]; void *
0x18000c390  mov     ebx, eax
0x18000c392  lea     rax, [rbp+520h+var_568]
0x18000c396  cmp     rcx, rax
0x18000c399  jz      short loc_18000C3A3
0x18000c39b  mov     rdx, r15; struct std::nothrow_t *
0x18000c39e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c3a3  cmp     ebx, 80070002h
0x18000c3a9  jnz     short loc_18000C3D1
0x18000c3ab  lea     rcx, [rsp+620h+dwAdditionalFlags+8]
0x18000c3b0  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18000c3b5  lea     rcx, [rsp+620h+var_5B8+8]
0x18000c3ba  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18000c3bf  mov     rcx, [rsp+620h+var_5D8]
0x18000c3c4  lea     rax, [rsp+620h+var_5C8]
0x18000c3c9  cmp     rcx, rax
0x18000c3cc  jmp     loc_18000C98A
0x18000c3d1  test    ebx, ebx
0x18000c3d3  jns     short loc_18000C422
0x18000c3d5  mov     rcx, [rbp+528h]; this
0x18000c3dc  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000c3e3  mov     r9d, ebx; char *
0x18000c3e6  mov     edx, 3C6h; void *
0x18000c3eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c3f0  lea     rcx, [rsp+620h+dwAdditionalFlags+8]
0x18000c3f5  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18000c3fa  lea     rcx, [rsp+620h+var_5B8+8]
0x18000c3ff  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18000c404  mov     rcx, [rsp+620h+var_5D8]; void *
0x18000c409  lea     rax, [rsp+620h+var_5C8]
0x18000c40e  cmp     rcx, rax
0x18000c411  jz      short loc_18000C41B
0x18000c413  mov     rdx, r15; struct std::nothrow_t *
0x18000c416  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c41b  mov     eax, ebx
0x18000c41d  jmp     loc_18000CB23
0x18000c422  mov     rbx, qword ptr [rsp+620h+dwAdditionalFlags+8]
0x18000c427  mov     rdi, [rsp+620h+var_5E8]
0x18000c42c  cmp     rbx, rdi
0x18000c42f  jz      short loc_18000C475
0x18000c431  mov     rdx, rbx
0x18000c434  lea     rcx, [rsp+620h+var_5B8+8]
0x18000c439  call    ??$emplace_back@VPath@Csl@@$0A@@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@QEAA_N$$QEAVPath@Csl@@@Z; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::emplace_back<Csl::Path,0>(Csl::Path &&)
0x18000c43e  test    al, al
0x18000c440  jz      short loc_18000C448
0x18000c442  add     rbx, 20h ; ' '
0x18000c446  jmp     short loc_18000C42C
0x18000c448  mov     rcx, [rbp+528h]; this
0x18000c44f  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000c456  mov     r9d, 8007000Eh; char *
0x18000c45c  mov     edx, 3CCh; void *
0x18000c461  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c466  lea     rcx, [rsp+620h+dwAdditionalFlags+8]
0x18000c46b  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18000c470  jmp     loc_18000C907
0x18000c475  and     esi, 0FFFFFFFBh
0x18000c478  lea     rcx, [rsp+620h+dwAdditionalFlags+8]
0x18000c47d  mov     dword ptr [rsp+620h+var_5B8], esi
0x18000c481  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18000c486  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18000c48e  mov     rdi, qword ptr [rsp+620h+var_5B8+8]
0x18000c493  mov     r14, r12
0x18000c496  movdqu  xmmword ptr [rsp+620h+dwAdditionalFlags+8], xmm6
0x18000c49c  mov     rbx, [rsp+620h+var_5E8]
0x18000c4a1  mov     [rsp+620h+var_5E0], r12
0x18000c4a6  cmp     rdi, qword ptr [rsp+620h+var_5B8+10h]
0x18000c4ab  jz      loc_18000C932
0x18000c4b1  xor     edx, edx; Val
0x18000c4b3  lea     rcx, [rbp+520h+FindFileData]; void *
0x18000c4ba  mov     r8d, 250h; Size
0x18000c4c0  call    memset_0
0x18000c4c5  mov     r8, [rdi+8]
0x18000c4c9  lea     rax, [rbp+520h+var_588]
0x18000c4cd  sub     r8, [rdi]
0x18000c4d0  lea     rcx, [rbp+520h+lpFileName]
0x18000c4d4  mov     rdx, [rdi]
0x18000c4d7  xor     esi, esi
0x18000c4d9  mov     [rbp+520h+lpFileName], rax
0x18000c4dd  lea     rax, [rbp+520h+var_588]
0x18000c4e1  sar     r8, 1
0x18000c4e4  mov     [rbp+520h+var_590], rax
0x18000c4e8  mov     [rbp+520h+var_588], si
0x18000c4ec  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000c4f1  test    al, al
0x18000c4f3  jz      loc_18000C899
0x18000c4f9  mov     [rbp+520h+var_548], r13
0x18000c4fd  mov     rax, r12
0x18000c500  inc     rax
0x18000c503  cmp     [r13+rax*2+0], si
0x18000c509  jnz     short loc_18000C500
0x18000c50b  lea     rdx, [rbp+520h+var_548]
0x18000c50f  mov     [rbp+520h+var_540], rax
0x18000c513  lea     rcx, [rbp+520h+lpFileName]; this
0x18000c517  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18000c51c  test    al, al
0x18000c51e  jz      loc_18000C892
0x18000c524  mov     rcx, [rbp+520h+lpFileName]; lpFileName
0x18000c528  lea     r8, [rbp+520h+FindFileData]; lpFindFileData
0x18000c52f  xor     r9d, r9d; fSearchOp
0x18000c532  mov     [rsp+620h+dwAdditionalFlags], 2; dwAdditionalFlags
0x18000c53a  mov     [rsp+620h+lpSearchFilter], rsi; int
0x18000c53f  lea     edx, [r9+1]; fInfoLevelId
0x18000c543  call    cs:__imp_FindFirstFileExW
0x18000c54a  nop     dword ptr [rax+rax+00h]
0x18000c54f  mov     rcx, rax
0x18000c552  cmp     rax, r12
0x18000c555  jnz     loc_18000C602
0x18000c55b  call    cs:__imp_GetLastError
0x18000c562  nop     dword ptr [rax+rax+00h]
0x18000c567  cmp     eax, 2
0x18000c56a  jz      loc_18000C77B
0x18000c570  mov     rcx, [rbp+528h]; this
0x18000c577  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000c57e  mov     edx, 3EEh; void *
0x18000c583  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c588  mov     rcx, [rbp+520h+lpFileName]; void *
0x18000c58c  mov     esi, eax
0x18000c58e  lea     rax, [rbp+520h+var_588]
0x18000c592  cmp     rcx, rax
0x18000c595  jz      short loc_18000C59F
0x18000c597  mov     rdx, r15; struct std::nothrow_t *
0x18000c59a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c59f  mov     rdi, qword ptr [rsp+620h+dwAdditionalFlags+8]
0x18000c5a4  cmp     rdi, r12
0x18000c5a7  jz      short loc_18000C5DA
0x18000c5a9  sub     rbx, rdi
0x18000c5ac  mov     rax, 67B23A5440CF6475h
0x18000c5b6  imul    rbx
0x18000c5b9  sar     rdx, 8
0x18000c5bd  mov     r8, rdx
0x18000c5c0  shr     r8, 3Fh
0x18000c5c4  add     r8, rdx
0x18000c5c7  mov     rdx, rdi
0x18000c5ca  call    ??$_RangeDestroyApc@V?$allocator@UFindFirstFileInformation@Csl@@@utl@@@utl@@YAXAEAV?$allocator@UFindFirstFileInformation@Csl@@@0@PEAUFindFirstFileInformation@Csl@@_K@Z; utl::_RangeDestroyApc<utl::allocator<Csl::FindFirstFileInformation>>(utl::allocator<Csl::FindFirstFileInformation> &,Csl::FindFirstFileInformation *,unsigned __int64)
0x18000c5cf  mov     rdx, r15; struct std::nothrow_t *
0x18000c5d2  mov     rcx, rdi; void *
0x18000c5d5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c5da  lea     rcx, [rsp+620h+var_5B8+8]
0x18000c5df  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x18000c5e4  mov     rcx, [rsp+620h+var_5D8]; void *
0x18000c5e9  lea     rax, [rsp+620h+var_5C8]
0x18000c5ee  cmp     rcx, rax
0x18000c5f1  jz      short loc_18000C5FB
0x18000c5f3  mov     rdx, r15; struct std::nothrow_t *
0x18000c5f6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c5fb  mov     eax, esi
0x18000c5fd  jmp     loc_18000CB23
0x18000c602  lea     rax, [rbp+520h+var_2C8]
0x18000c609  mov     [rbp+520h+hFindFile], rcx
0x18000c60d  mov     [rbp+520h+var_2D8], rax
0x18000c614  lea     rcx, [rbp+520h+FindFileData]
0x18000c61b  lea     rax, [rbp+520h+var_2C8]
0x18000c622  mov     [rbp+520h+var_2C8], si
0x18000c629  mov     edx, 4
0x18000c62e  mov     [rbp+520h+var_2D0], rax
0x18000c635  lea     rax, [rbp+520h+var_528]
0x18000c639  lea     r8d, [rdx+7Ch]
0x18000c63d  movups  xmm0, xmmword ptr [rcx]
0x18000c640  movups  xmm1, xmmword ptr [rcx+10h]
0x18000c644  movups  xmmword ptr [rax], xmm0
0x18000c647  movups  xmm0, xmmword ptr [rcx+20h]
0x18000c64b  movups  xmmword ptr [rax+10h], xmm1
0x18000c64f  movups  xmm1, xmmword ptr [rcx+30h]
0x18000c653  movups  xmmword ptr [rax+20h], xmm0
0x18000c657  movups  xmm0, xmmword ptr [rcx+40h]
0x18000c65b  movups  xmmword ptr [rax+30h], xmm1
0x18000c65f  movups  xmm1, xmmword ptr [rcx+50h]
0x18000c663  movups  xmmword ptr [rax+40h], xmm0
0x18000c667  movups  xmm0, xmmword ptr [rcx+60h]
0x18000c66b  movups  xmmword ptr [rax+50h], xmm1
0x18000c66f  movups  xmm1, xmmword ptr [rcx+70h]
0x18000c673  add     rcx, r8
0x18000c676  movups  xmmword ptr [rax+60h], xmm0
0x18000c67a  movups  xmmword ptr [rax+70h], xmm1
0x18000c67e  add     rax, r8
0x18000c681  sub     rdx, 1
0x18000c685  jnz     short loc_18000C63D
0x18000c687  movups  xmm0, xmmword ptr [rcx]
0x18000c68a  mov     r8, [rdi+8]
0x18000c68e  movups  xmm1, xmmword ptr [rcx+10h]
0x18000c692  sub     r8, [rdi]
0x18000c695  mov     rdx, [rdi]
0x18000c698  movups  xmmword ptr [rax], xmm0
0x18000c69b  sar     r8, 1
0x18000c69e  movups  xmm0, xmmword ptr [rcx+20h]
0x18000c6a2  movups  xmmword ptr [rax+10h], xmm1
0x18000c6a6  movups  xmm1, xmmword ptr [rcx+30h]
0x18000c6aa  movups  xmmword ptr [rax+20h], xmm0
0x18000c6ae  movups  xmm0, xmmword ptr [rcx+40h]
0x18000c6b2  lea     rcx, [rbp+520h+var_2D8]
0x18000c6b9  movups  xmmword ptr [rax+30h], xmm1
0x18000c6bd  movups  xmmword ptr [rax+40h], xmm0
0x18000c6c1  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000c6c6  test    al, al
0x18000c6c8  jz      loc_18000C83D
0x18000c6ce  cmp     rbx, r14
0x18000c6d1  jnz     short loc_18000C72E
0x18000c6d3  mov     rsi, qword ptr [rsp+620h+dwAdditionalFlags+8]
0x18000c6d8  mov     rax, 9B8B577E613716AFh
0x18000c6e2  sub     r14, rsi
0x18000c6e5  sar     r14, 3
0x18000c6e9  imul    r14, rax
0x18000c6ed  mov     rax, r14
0x18000c6f0  shr     rax, 2
0x18000c6f4  imul    rdx, rax, 7
0x18000c6f8  mov     rax, 33D91D2A2067B2h
0x18000c702  add     rdx, 8
0x18000c706  cmp     rdx, rax
0x18000c709  cmova   rdx, rax
0x18000c70d  cmp     r14, rdx
0x18000c710  jnb     loc_18000C79E
0x18000c716  lea     rcx, [rsp+620h+dwAdditionalFlags+8]
0x18000c71b  call    ?_SetCapacity@?$vector@UFindFirstFileInformation@Csl@@V?$allocator@UFindFirstFileInformation@Csl@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Csl::FindFirstFileInformation,utl::allocator<Csl::FindFirstFileInformation>>::_SetCapacity(unsigned __int64)
  ... truncated ...
```
