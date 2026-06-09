# Utility::VerifyAndNormalizeFilePath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,long &)

- ea: `0x1800ceeb4`
- end: `0x1800cf998`
- name: `?VerifyAndNormalizeFilePath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@AEAJ@Z`
- size: `2788`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800c8770`
- `0x1800cee84`

## callees

- `0x180005890`
- `0x18000eac8`
- `0x18000edf0`
- `0x18000faf0`
- `0x1800108a8`
- `0x18001c5f0`
- `0x18001c6d8`
- `0x1800295dc`
- `0x1800c3478`
- `0x1800c9aac`
- `0x1800ca3fc`
- `0x1800ca464`
- `0x1800cd0f8`
- `0x1800cea08`
- `0x1800cebfc`
- `0x1800cec18`
- `0x1800ceeb4`
- `0x1800cfedc`
- `0x1800d00c0`
- `0x1800e1a18`
- `0x1800e4d80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800cf1da`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800cf45c`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800cf630`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800cf6f1`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800cf1da`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800cf45c`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800cf630`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800cf6f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf5e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf5e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf857`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cf878`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cf878`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800cf7bc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800cf835`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800cf7bc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800cf835`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800cf527`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x1800cf527`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1800cef4b`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1800cef4b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800cf5c3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800cf5c3`
- `api-ms-win-core-commandlinetoargv-l1-1-0!CommandLineToArgvW` at `0x1800cf7f1`
- `api-ms-win-core-commandlinetoargv-l1-1-0!CommandLineToArgvW` at `0x1800cf7f1`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1800cf73a`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x1800cf73a`

## string_xrefs

- `0x1800cefea`: `PathCchCanonicalizeEx failed: [0x%08x]`
- `0x1800cf762`: `Unsupported network path: %ws`
- `0x1800ceff7`: `Utility::VerifyAndNormalizeFilePath`
- `0x1800cf76f`: `Utility::VerifyAndNormalizeFilePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall Utility::VerifyAndNormalizeFilePath(__int64 a1, __int64 a2, signed int *a3)
{
  const WCHAR *v6; // r8
  WCHAR *v7; // rcx
  HRESULT v8; // r14d
  size_t v9; // rdx
  LPCWSTR *v10; // rax
  __int64 v11; // r14
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  unsigned __int16 **v18; // rcx
  unsigned __int16 *v19; // rdx
  wchar_t *v20; // rcx
  unsigned __int16 **v21; // rax
  __int64 v22; // rdx
  unsigned __int16 **v23; // rcx
  unsigned __int16 **v24; // rax
  unsigned __int16 **v25; // rax
  LPCWSTR *v26; // rax
  LPCWSTR v27; // rdx
  unsigned __int16 *v28; // rdx
  wchar_t *v29; // rcx
  unsigned __int16 **v30; // rax
  __int64 v31; // rdx
  unsigned __int16 **v32; // rcx
  unsigned __int16 **v33; // rax
  unsigned __int16 **v34; // rax
  LPCWSTR *v35; // rax
  LPCWSTR *v36; // rax
  __int64 v37; // rax
  const WCHAR *v38; // rcx
  signed int LastError; // eax
  LPCWSTR *v40; // rcx
  int v41; // eax
  LPCWSTR *v42; // rax
  LPCWSTR *v43; // rax
  LPCWSTR *v44; // rax
  LPCWSTR *v45; // rax
  LPCWSTR *v46; // rax
  LPCWSTR *v47; // rcx
  LPCWSTR *v48; // rax
  LPCWSTR *v49; // rcx
  LPCWSTR *v50; // rax
  const WCHAR *v51; // rcx
  DWORD FileAttributesW; // eax
  const WCHAR *v53; // rcx
  LPWSTR *v54; // rbx
  LPWSTR v55; // rdx
  const WCHAR *v56; // rcx
  signed int v57; // eax
  __int64 LongPath; // rax
  int pNumArgs; // [rsp+30h] [rbp-1438h] BYREF
  __int64 v61; // [rsp+38h] [rbp-1430h]
  LPWSTR *v62; // [rsp+40h] [rbp-1428h]
  LPCWSTR pszPath[2]; // [rsp+130h] [rbp-1338h] BYREF
  unsigned __int64 v64; // [rsp+140h] [rbp-1328h]
  unsigned __int64 v65; // [rsp+148h] [rbp-1320h]
  unsigned __int16 *v66[2]; // [rsp+150h] [rbp-1318h] BYREF
  __m128i v67; // [rsp+160h] [rbp-1308h]
  unsigned __int16 *v68[2]; // [rsp+170h] [rbp-12F8h] BYREF
  __m128i si128; // [rsp+180h] [rbp-12E8h]
  _BYTE v70[32]; // [rsp+190h] [rbp-12D8h] BYREF
  _BYTE v71[32]; // [rsp+1B0h] [rbp-12B8h] BYREF
  PWSTR pszPathOut[3]; // [rsp+1D0h] [rbp-1298h] BYREF
  size_t cchPathOut; // [rsp+1E8h] [rbp-1280h]
  _BYTE v74[32]; // [rsp+1F0h] [rbp-1278h] BYREF
  WCHAR Buffer[2312]; // [rsp+210h] [rbp-1258h] BYREF

  v61 = a1;
  std::wstring::wstring(pszPath, 0);
  std::wstring::wstring(pszPathOut, 261);
  while ( 1 )
  {
    if ( *(_QWORD *)(a2 + 24) <= 7u )
      v6 = (const WCHAR *)a2;
    else
      v6 = *(const WCHAR **)a2;
    v7 = (WCHAR *)pszPathOut;
    if ( cchPathOut > 7 )
      v7 = pszPathOut[0];
    v8 = PathCchCanonicalizeEx(v7, cchPathOut, v6, 1u);
    if ( (_WORD)v8 != 122 || cchPathOut >= 0x8000 )
      break;
    v9 = 2 * cchPathOut;
    if ( 2 * cchPathOut > 0x8000 )
      v9 = 0x8000;
    std::wstring::resize(pszPathOut, v9);
  }
  std::wstring::operator=(pszPath, pszPathOut);
  if ( v8 < 0 )
  {
    std::wstring::operator=(pszPath, a2);
    AslLogCallPrintf(1, "Utility::VerifyAndNormalizeFilePath", 1703, "PathCchCanonicalizeEx failed: [0x%08x]", v8);
    v11 = -1;
  }
  else
  {
    v10 = pszPath;
    if ( v65 > 7 )
      v10 = (LPCWSTR *)pszPath[0];
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)v10 + v12) );
    std::wstring::resize(pszPath, v12 + 1);
  }
  v13 = Utility::TrimSpace(pszPath);
  std::wstring::operator=(pszPath, v13);
  v14 = Utility::TrimTrailingBackSlashFromPath(v71, pszPath);
  std::wstring::operator=(pszPath, v14);
  std::wstring::_Tidy_deallocate(v71);
  v15 = Utility::ToLower(v71, pszPath);
  std::wstring::operator=(pszPath, v15);
  std::wstring::_Tidy_deallocate(v71);
  if ( v64 >= 0x104 )
  {
    if ( std::wstring::find(pszPath, &Utility::PathPrefixLongPath) )
    {
      v17 = std::operator+<unsigned short>(v71, v16, pszPath);
      std::wstring::operator=(pszPath, v17);
      v18 = (unsigned __int16 **)v71;
LABEL_78:
      std::wstring::_Tidy_deallocate(v18);
      goto LABEL_79;
    }
    goto LABEL_79;
  }
  if ( !std::wstring::find(pszPath, Utility::PathPrefixDeviceDrivePath) && v64 < 0x104 )
  {
    *(_OWORD *)v68 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v68[0]) = 0;
    std::wstring::resize(v68, 260);
    v19 = (unsigned __int16 *)v68;
    if ( si128.m128i_i64[1] > 7uLL )
      v19 = v68[0];
    v20 = (wchar_t *)pszPath;
    if ( v65 > 7 )
      v20 = (wchar_t *)pszPath[0];
    if ( (int)ConvertDevicePathToDrivePath(v20, v19) >= 0 )
    {
      v21 = v68;
      if ( si128.m128i_i64[1] > 7uLL )
        v21 = (unsigned __int16 **)v68[0];
      v22 = -1;
      do
        ++v22;
      while ( *((_WORD *)v21 + v22) );
      std::wstring::resize(v68, v22);
      if ( si128.m128i_i64[0] >= 3uLL )
      {
        v23 = v68;
        if ( si128.m128i_i64[1] > 7uLL )
          v23 = (unsigned __int16 **)v68[0];
        if ( (unsigned int)_o_iswalpha(*(unsigned __int16 *)v23) )
        {
          v24 = v68;
          if ( si128.m128i_i64[1] > 7uLL )
            v24 = (unsigned __int16 **)v68[0];
          if ( *((_WORD *)v24 + 1) == 58 )
          {
            v25 = v68;
            if ( si128.m128i_i64[1] > 7uLL )
              v25 = (unsigned __int16 **)v68[0];
            if ( *((_WORD *)v25 + 2) == 92 )
              std::wstring::operator=(pszPath, v68);
          }
        }
      }
    }
    v18 = v68;
    goto LABEL_78;
  }
  if ( !v64 )
  {
LABEL_79:
    v27 = pszPath[0];
    goto LABEL_80;
  }
  v26 = pszPath;
  v27 = pszPath[0];
  if ( v65 > 7 )
    v26 = (LPCWSTR *)pszPath[0];
  if ( *(_WORD *)v26 == 92 )
  {
    *(_OWORD *)v66 = 0;
    v67 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v66[0]) = 0;
    if ( !std::wstring::find(pszPath, Utility::PathPrefixGlobal) )
    {
      std::wstring::wstring(v70, pszPath, qword_180121B00, v64);
      std::wstring::operator=(pszPath, v70);
      std::wstring::_Tidy_deallocate(v70);
      if ( v64 < 0x104 )
      {
        std::wstring::resize(v66, 260);
        v28 = (unsigned __int16 *)v66;
        if ( v67.m128i_i64[1] > 7uLL )
          v28 = v66[0];
        v29 = (wchar_t *)pszPath;
        if ( v65 > 7 )
          v29 = (wchar_t *)pszPath[0];
        if ( (int)ConvertDevicePathToDrivePath(v29, v28) >= 0 )
        {
          v30 = v66;
          if ( v67.m128i_i64[1] > 7uLL )
            v30 = (unsigned __int16 **)v66[0];
          v31 = -1;
          do
            ++v31;
          while ( *((_WORD *)v30 + v31) );
          std::wstring::resize(v66, v31);
        }
      }
      goto LABEL_66;
    }
    if ( std::wstring::find(pszPath, &Utility::PathPrefixLongPath) )
    {
      if ( std::wstring::find(pszPath, Utility::PathPrefixDrivePath) )
      {
LABEL_66:
        if ( v67.m128i_i64[0] >= 3uLL )
        {
          v32 = v66;
          if ( v67.m128i_i64[1] > 7uLL )
            v32 = (unsigned __int16 **)v66[0];
          if ( (unsigned int)_o_iswalpha(*(unsigned __int16 *)v32) )
          {
            v33 = v66;
            if ( v67.m128i_i64[1] > 7uLL )
              v33 = (unsigned __int16 **)v66[0];
            if ( *((_WORD *)v33 + 1) == 58 )
            {
              v34 = v66;
              if ( v67.m128i_i64[1] > 7uLL )
                v34 = (unsigned __int16 **)v66[0];
              if ( *((_WORD *)v34 + 2) == 92 )
                std::wstring::operator=(pszPath, v66);
            }
          }
        }
        v18 = v66;
        goto LABEL_78;
      }
      std::wstring::wstring(v70, pszPath, qword_180121B40, v64);
    }
    else
    {
      std::wstring::wstring(v70, pszPath, qword_180121B20, v64);
    }
    std::wstring::operator=(v66, v70);
    std::wstring::_Tidy_deallocate(v70);
    goto LABEL_66;
  }
LABEL_80:
  if ( v64 >= 2 )
  {
    v35 = pszPath;
    if ( v65 > 7 )
      v35 = (LPCWSTR *)v27;
    if ( *(_WORD *)v35 == 92 )
    {
      v36 = pszPath;
      if ( v65 > 7 )
        v36 = (LPCWSTR *)v27;
      if ( *((_WORD *)v36 + 1) != 92 )
      {
        GetCurrentDirectoryW(0x104u, Buffer);
        std::wstring::wstring(v71, Buffer);
        std::wstring::wstring(v70, v71, 0, 2);
        v37 = std::operator+<unsigned short>(v74, v70, pszPath);
        std::wstring::operator=(pszPath, v37);
        std::wstring::_Tidy_deallocate(v74);
        std::wstring::_Tidy_deallocate(v70);
        v38 = (const WCHAR *)pszPath;
        if ( v65 > 7 )
          v38 = pszPath[0];
        if ( !PathFileExistsW(v38) )
        {
          std::wstring::_Assign<unsigned short>(pszPath, &pszFormat, 0);
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          *a3 = LastError;
        }
        std::wstring::_Tidy_deallocate(v71);
        v27 = pszPath[0];
      }
    }
    if ( v64 >= 2 )
    {
      v40 = pszPath;
      if ( v65 > 7 )
        v40 = (LPCWSTR *)v27;
      v41 = _o_iswalpha(*(unsigned __int16 *)v40);
      v27 = pszPath[0];
      if ( v41 )
      {
        v42 = pszPath;
        if ( v65 > 7 )
          v42 = (LPCWSTR *)pszPath[0];
        if ( *((_WORD *)v42 + 1) == 58 )
          goto LABEL_120;
      }
    }
  }
  if ( v64 <= 0x104 )
    goto LABEL_147;
  v43 = pszPath;
  if ( v65 > 7 )
    v43 = (LPCWSTR *)v27;
  if ( *(_WORD *)v43 != 92 )
    goto LABEL_147;
  v44 = pszPath;
  if ( v65 > 7 )
    v44 = (LPCWSTR *)v27;
  if ( *((_WORD *)v44 + 1) != 92 )
    goto LABEL_147;
  v45 = pszPath;
  if ( v65 > 7 )
    v45 = (LPCWSTR *)v27;
  if ( *((_WORD *)v45 + 2) != 63 )
    goto LABEL_147;
  v46 = pszPath;
  if ( v65 > 7 )
    v46 = (LPCWSTR *)v27;
  if ( *((_WORD *)v46 + 3) != 92 )
    goto LABEL_147;
  v47 = pszPath;
  if ( v65 > 7 )
    v47 = (LPCWSTR *)v27;
  if ( !(unsigned int)_o_iswalpha(*((unsigned __int16 *)v47 + 4)) )
    goto LABEL_147;
  v48 = pszPath;
  v27 = pszPath[0];
  if ( v65 > 7 )
    v48 = (LPCWSTR *)pszPath[0];
  if ( *((_WORD *)v48 + 5) == 58 )
  {
LABEL_120:
    v49 = pszPath;
    if ( v65 > 7 )
      v49 = (LPCWSTR *)v27;
    if ( PathIsNetworkPathW((LPCWSTR)v49) )
    {
      v50 = pszPath;
      if ( v65 > 7 )
        v50 = (LPCWSTR *)pszPath[0];
      AslLogCallPrintf(3, "Utility::VerifyAndNormalizeFilePath", 1833, "Unsupported network path: %ws", v50);
      std::wstring::_Assign<unsigned short>(pszPath, &pszFormat, 0);
      *a3 = -2147467259;
    }
    else
    {
      v51 = (const WCHAR *)pszPath;
      if ( v65 > 7 )
        v51 = pszPath[0];
      FileAttributesW = GetFileAttributesW(v51);
      v53 = (const WCHAR *)pszPath;
      if ( FileAttributesW == -1 )
      {
        pNumArgs = 0;
        if ( v65 > 7 )
          v53 = pszPath[0];
        v54 = CommandLineToArgvW(v53, &pNumArgs);
        v62 = v54;
        v55 = *v54;
        do
          ++v11;
        while ( v55[v11] );
        std::wstring::_Assign<unsigned short>(pszPath, v55, v11);
        v56 = (const WCHAR *)pszPath;
        if ( v65 > 7 )
          v56 = pszPath[0];
        if ( GetFileAttributesW(v56) == -1 )
        {
          std::wstring::_Assign<unsigned short>(pszPath, &pszFormat, 0);
          v57 = GetLastError();
          if ( v57 > 0 )
            v57 = (unsigned __int16)v57 | 0x80070000;
          *a3 = v57;
        }
        if ( v54 )
          LocalFree(v54);
      }
      else if ( (FileAttributesW & 0x11440) != 0 )
      {
        std::wstring::_Assign<unsigned short>(pszPath, &pszFormat, 0);
        *a3 = -2147024864;
      }
      else if ( (FileAttributesW & 0x10) != 0 )
      {
        std::wstring::_Assign<unsigned short>(pszPath, &pszFormat, 0);
        *a3 = -2147024894;
      }
      else if ( std::wstring::find(pszPath, L"~") != -1 )
      {
        LongPath = Utility::GetLongPath(v74, pszPath);
        std::wstring::operator=(pszPath, LongPath);
        std::wstring::_Tidy_deallocate(v74);
        *a3 = 0;
      }
    }
  }
  else
  {
LABEL_147:
    std::wstring::_Assign<unsigned short>(pszPath, &pszFormat, 0);
    *a3 = -2147024893;
  }
  Utility::ToLower(a1, pszPath);
  std::wstring::_Tidy_deallocate(pszPathOut);
  std::wstring::_Tidy_deallocate(pszPath);
  return a1;
}

```

## disassembly

```asm
0x1800ceeb4  push    rbx
0x1800ceeb6  push    rsi
0x1800ceeb7  push    rdi
0x1800ceeb8  push    r12
0x1800ceeba  push    r13
0x1800ceebc  push    r14
0x1800ceebe  push    r15
0x1800ceec0  mov     eax, 1430h
0x1800ceec5  call    _alloca_probe
0x1800ceeca  sub     rsp, rax
0x1800ceecd  mov     rax, cs:__security_cookie
0x1800ceed4  xor     rax, rsp
0x1800ceed7  mov     [rsp+1468h+var_48], rax
0x1800ceedf  mov     r15, r8
0x1800ceee2  mov     rbx, rdx
0x1800ceee5  mov     r12, rcx
0x1800ceee8  mov     [rsp+1468h+var_1430], rcx
0x1800ceeed  xor     esi, esi
0x1800ceeef  xor     edx, edx
0x1800ceef1  lea     rcx, [rsp+1468h+pszPath]
0x1800ceef9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x1800ceefe  nop
0x1800ceeff  mov     edx, 105h
0x1800cef04  lea     rcx, [rsp+1468h+pszPathOut]
0x1800cef0c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x1800cef11  nop
0x1800cef12  lea     edi, [rsi+7]
0x1800cef15  mov     r13d, 8000h
0x1800cef1b  cmp     [rbx+18h], rdi
0x1800cef1f  jbe     short loc_1800CEF26
0x1800cef21  mov     r8, [rbx]
0x1800cef24  jmp     short loc_1800CEF29
0x1800cef26  mov     r8, rbx; pszPathIn
0x1800cef29  mov     rdx, [rsp+1468h+cchPathOut]; cchPathOut
0x1800cef31  lea     rcx, [rsp+1468h+pszPathOut]
0x1800cef39  cmp     rdx, rdi
0x1800cef3c  cmova   rcx, [rsp+1468h+pszPathOut]; pszPathOut
0x1800cef45  mov     r9d, 1; dwFlags
0x1800cef4b  call    cs:__imp_PathCchCanonicalizeEx
0x1800cef51  mov     r14d, eax
0x1800cef54  cmp     ax, 7Ah ; 'z'
0x1800cef58  jnz     short loc_1800CEF80
0x1800cef5a  mov     rdx, [rsp+1468h+cchPathOut]
0x1800cef62  cmp     rdx, r13
0x1800cef65  jnb     short loc_1800CEF80
0x1800cef67  add     rdx, rdx
0x1800cef6a  cmp     rdx, r13
0x1800cef6d  cmova   rdx, r13
0x1800cef71  lea     rcx, [rsp+1468h+pszPathOut]
0x1800cef79  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800cef7e  jmp     short loc_1800CEF1B
0x1800cef80  lea     rdx, [rsp+1468h+pszPathOut]
0x1800cef88  lea     rcx, [rsp+1468h+pszPath]
0x1800cef90  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800cef95  test    r14d, r14d
0x1800cef98  js      short loc_1800CEFD5
0x1800cef9a  lea     rax, [rsp+1468h+pszPath]
0x1800cefa2  cmp     [rsp+1468h+var_1320], rdi
0x1800cefaa  cmova   rax, [rsp+1468h+pszPath]
0x1800cefb3  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800cefb7  mov     rdx, r14
0x1800cefba  inc     rdx
0x1800cefbd  cmp     [rax+rdx*2], si
0x1800cefc1  jnz     short loc_1800CEFBA
0x1800cefc3  inc     rdx
0x1800cefc6  lea     rcx, [rsp+1468h+pszPath]
0x1800cefce  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800cefd3  jmp     short loc_1800CF00C
0x1800cefd5  mov     rdx, rbx
0x1800cefd8  lea     rcx, [rsp+1468h+pszPath]
0x1800cefe0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800cefe5  mov     dword ptr [rsp+1468h+var_1448], r14d
0x1800cefea  lea     r9, aPathcchcanonic; "PathCchCanonicalizeEx failed: [0x%08x]"
0x1800ceff1  mov     r8d, 6A7h
0x1800ceff7  lea     rdx, aUtilityVerifya; "Utility::VerifyAndNormalizeFilePath"
0x1800ceffe  mov     ecx, 1
0x1800cf003  call    AslLogCallPrintf
0x1800cf008  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800cf00c  lea     rcx, [rsp+1468h+pszPath]
0x1800cf014  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x1800cf019  mov     rdx, rax
0x1800cf01c  lea     rcx, [rsp+1468h+pszPath]
0x1800cf024  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800cf029  lea     rdx, [rsp+1468h+pszPath]
0x1800cf031  lea     rcx, [rsp+1468h+var_12B8]
0x1800cf039  call    ?TrimTrailingBackSlashFromPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::TrimTrailingBackSlashFromPath(std::wstring const &)
0x1800cf03e  mov     rdx, rax
0x1800cf041  lea     rcx, [rsp+1468h+pszPath]
0x1800cf049  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800cf04e  lea     rcx, [rsp+1468h+var_12B8]
0x1800cf056  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cf05b  lea     rdx, [rsp+1468h+pszPath]
0x1800cf063  lea     rcx, [rsp+1468h+var_12B8]
0x1800cf06b  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800cf070  mov     rdx, rax
0x1800cf073  lea     rcx, [rsp+1468h+pszPath]
0x1800cf07b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800cf080  lea     rcx, [rsp+1468h+var_12B8]
0x1800cf088  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cf08d  mov     ebx, 104h
0x1800cf092  lea     rcx, [rsp+1468h+pszPath]
0x1800cf09a  cmp     [rsp+1468h+var_1328], rbx
0x1800cf0a2  jb      short loc_1800CF0EB
0x1800cf0a4  lea     rdx, ?PathPrefixLongPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixLongPath
0x1800cf0ab  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x1800cf0b0  test    rax, rax
0x1800cf0b3  jz      loc_1800CF4C9
0x1800cf0b9  lea     r8, [rsp+1468h+pszPath]
0x1800cf0c1  lea     rcx, [rsp+1468h+var_12B8]
0x1800cf0c9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@0@Z; std::operator+<ushort>(std::wstring const &,std::wstring const &)
0x1800cf0ce  mov     rdx, rax
0x1800cf0d1  lea     rcx, [rsp+1468h+pszPath]
0x1800cf0d9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800cf0de  lea     rcx, [rsp+1468h+var_12B8]
0x1800cf0e6  jmp     loc_1800CF4C4
0x1800cf0eb  lea     rdx, ?PathPrefixDeviceDrivePath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixDeviceDrivePath
0x1800cf0f2  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x1800cf0f7  test    rax, rax
0x1800cf0fa  jnz     loc_1800CF247
0x1800cf100  cmp     [rsp+1468h+var_1328], rbx
0x1800cf108  jnb     loc_1800CF247
0x1800cf10e  xorps   xmm0, xmm0
0x1800cf111  movups  xmmword ptr [rsp+1468h+var_12F8], xmm0
0x1800cf119  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800cf121  movdqu  [rsp+1468h+var_12E8], xmm1
0x1800cf12a  mov     word ptr [rsp+1468h+var_12F8], si
0x1800cf132  mov     rdx, rbx
0x1800cf135  lea     rcx, [rsp+1468h+var_12F8]
0x1800cf13d  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800cf142  lea     rdx, [rsp+1468h+var_12F8]
0x1800cf14a  cmp     qword ptr [rsp+1468h+var_12E8+8], rdi
0x1800cf152  cmova   rdx, [rsp+1468h+var_12F8]; unsigned __int16 *
0x1800cf15b  lea     rcx, [rsp+1468h+pszPath]
0x1800cf163  cmp     [rsp+1468h+var_1320], rdi
0x1800cf16b  cmova   rcx, [rsp+1468h+pszPath]; String1
0x1800cf174  call    ?ConvertDevicePathToDrivePath@@YAJPEBGPEAG@Z; ConvertDevicePathToDrivePath(ushort const *,ushort *)
0x1800cf179  test    eax, eax
0x1800cf17b  js      loc_1800CF23A
0x1800cf181  lea     rax, [rsp+1468h+var_12F8]
0x1800cf189  cmp     qword ptr [rsp+1468h+var_12E8+8], rdi
0x1800cf191  cmova   rax, [rsp+1468h+var_12F8]
0x1800cf19a  mov     rdx, r14
0x1800cf19d  inc     rdx
0x1800cf1a0  cmp     [rax+rdx*2], si
0x1800cf1a4  jnz     short loc_1800CF19D
0x1800cf1a6  lea     rcx, [rsp+1468h+var_12F8]
0x1800cf1ae  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800cf1b3  cmp     qword ptr [rsp+1468h+var_12E8], 3
0x1800cf1bc  jb      short loc_1800CF23A
0x1800cf1be  lea     rcx, [rsp+1468h+var_12F8]
0x1800cf1c6  cmp     qword ptr [rsp+1468h+var_12E8+8], rdi
0x1800cf1ce  cmova   rcx, [rsp+1468h+var_12F8]
0x1800cf1d7  movzx   ecx, word ptr [rcx]
0x1800cf1da  call    cs:__imp__o_iswalpha
0x1800cf1e0  test    eax, eax
0x1800cf1e2  jz      short loc_1800CF23A
0x1800cf1e4  lea     rax, [rsp+1468h+var_12F8]
0x1800cf1ec  cmp     qword ptr [rsp+1468h+var_12E8+8], rdi
0x1800cf1f4  cmova   rax, [rsp+1468h+var_12F8]
0x1800cf1fd  cmp     word ptr [rax+2], 3Ah ; ':'
0x1800cf202  jnz     short loc_1800CF23A
0x1800cf204  lea     rax, [rsp+1468h+var_12F8]
0x1800cf20c  cmp     qword ptr [rsp+1468h+var_12E8+8], rdi
0x1800cf214  cmova   rax, [rsp+1468h+var_12F8]
0x1800cf21d  cmp     word ptr [rax+4], 5Ch ; '\'
0x1800cf222  jnz     short loc_1800CF23A
0x1800cf224  lea     rdx, [rsp+1468h+var_12F8]
0x1800cf22c  lea     rcx, [rsp+1468h+pszPath]
0x1800cf234  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800cf239  nop
0x1800cf23a  lea     rcx, [rsp+1468h+var_12F8]
0x1800cf242  jmp     loc_1800CF4C4
0x1800cf247  cmp     [rsp+1468h+var_1328], 1
0x1800cf250  jb      loc_1800CF4C9
0x1800cf256  lea     rax, [rsp+1468h+pszPath]
0x1800cf25e  mov     rdx, [rsp+1468h+pszPath]
0x1800cf266  cmp     [rsp+1468h+var_1320], rdi
0x1800cf26e  cmova   rax, rdx
0x1800cf272  cmp     word ptr [rax], 5Ch ; '\'
0x1800cf276  jnz     loc_1800CF4D1
0x1800cf27c  xorps   xmm0, xmm0
0x1800cf27f  movups  xmmword ptr [rsp+1468h+var_1318], xmm0
0x1800cf287  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800cf28f  movdqu  [rsp+1468h+var_1308], xmm1
0x1800cf298  mov     word ptr [rsp+1468h+var_1318], si
0x1800cf2a0  lea     rdx, ?PathPrefixGlobal@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixGlobal
0x1800cf2a7  lea     rcx, [rsp+1468h+pszPath]
0x1800cf2af  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x1800cf2b4  test    rax, rax
0x1800cf2b7  jnz     loc_1800CF397
0x1800cf2bd  mov     r9, [rsp+1468h+var_1328]
0x1800cf2c5  mov     r8, cs:qword_180121B00
0x1800cf2cc  lea     rdx, [rsp+1468h+pszPath]
0x1800cf2d4  lea     rcx, [rsp+1468h+var_12D8]
0x1800cf2dc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x1800cf2e1  lea     rdx, [rsp+1468h+var_12D8]
0x1800cf2e9  lea     rcx, [rsp+1468h+pszPath]
0x1800cf2f1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800cf2f6  lea     rcx, [rsp+1468h+var_12D8]
0x1800cf2fe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cf303  cmp     [rsp+1468h+var_1328], rbx
0x1800cf30b  jnb     loc_1800CF435
0x1800cf311  mov     rdx, rbx
0x1800cf314  lea     rcx, [rsp+1468h+var_1318]
0x1800cf31c  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800cf321  lea     rdx, [rsp+1468h+var_1318]
0x1800cf329  cmp     qword ptr [rsp+1468h+var_1308+8], rdi
0x1800cf331  cmova   rdx, [rsp+1468h+var_1318]; unsigned __int16 *
0x1800cf33a  lea     rcx, [rsp+1468h+pszPath]
0x1800cf342  cmp     [rsp+1468h+var_1320], rdi
0x1800cf34a  cmova   rcx, [rsp+1468h+pszPath]; String1
0x1800cf353  call    ?ConvertDevicePathToDrivePath@@YAJPEBGPEAG@Z; ConvertDevicePathToDrivePath(ushort const *,ushort *)
0x1800cf358  test    eax, eax
0x1800cf35a  js      loc_1800CF435
0x1800cf360  lea     rax, [rsp+1468h+var_1318]
0x1800cf368  cmp     qword ptr [rsp+1468h+var_1308+8], rdi
0x1800cf370  cmova   rax, [rsp+1468h+var_1318]
0x1800cf379  mov     rdx, r14
0x1800cf37c  inc     rdx
0x1800cf37f  cmp     [rax+rdx*2], si
0x1800cf383  jnz     short loc_1800CF37C
0x1800cf385  lea     rcx, [rsp+1468h+var_1318]
0x1800cf38d  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800cf392  jmp     loc_1800CF435
0x1800cf397  lea     rdx, ?PathPrefixLongPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixLongPath
0x1800cf39e  lea     rcx, [rsp+1468h+pszPath]
0x1800cf3a6  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x1800cf3ab  test    rax, rax
0x1800cf3ae  jnz     short loc_1800CF3D6
0x1800cf3b0  mov     r9, [rsp+1468h+var_1328]
0x1800cf3b8  mov     r8, cs:qword_180121B20
0x1800cf3bf  lea     rdx, [rsp+1468h+pszPath]
0x1800cf3c7  lea     rcx, [rsp+1468h+var_12D8]
0x1800cf3cf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x1800cf3d4  jmp     short loc_1800CF413
0x1800cf3d6  lea     rdx, ?PathPrefixDrivePath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixDrivePath
0x1800cf3dd  lea     rcx, [rsp+1468h+pszPath]
0x1800cf3e5  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x1800cf3ea  test    rax, rax
0x1800cf3ed  jnz     short loc_1800CF435
0x1800cf3ef  mov     r9, [rsp+1468h+var_1328]
0x1800cf3f7  mov     r8, cs:qword_180121B40
0x1800cf3fe  lea     rdx, [rsp+1468h+pszPath]
0x1800cf406  lea     rcx, [rsp+1468h+var_12D8]
0x1800cf40e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x1800cf413  lea     rdx, [rsp+1468h+var_12D8]
0x1800cf41b  lea     rcx, [rsp+1468h+var_1318]
0x1800cf423  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800cf428  lea     rcx, [rsp+1468h+var_12D8]
0x1800cf430  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cf435  cmp     qword ptr [rsp+1468h+var_1308], 3
0x1800cf43e  jb      short loc_1800CF4BC
0x1800cf440  lea     rcx, [rsp+1468h+var_1318]
0x1800cf448  cmp     qword ptr [rsp+1468h+var_1308+8], rdi
0x1800cf450  cmova   rcx, [rsp+1468h+var_1318]
0x1800cf459  movzx   ecx, word ptr [rcx]
0x1800cf45c  call    cs:__imp__o_iswalpha
0x1800cf462  test    eax, eax
0x1800cf464  jz      short loc_1800CF4BC
0x1800cf466  lea     rax, [rsp+1468h+var_1318]
0x1800cf46e  cmp     qword ptr [rsp+1468h+var_1308+8], rdi
0x1800cf476  cmova   rax, [rsp+1468h+var_1318]
0x1800cf47f  cmp     word ptr [rax+2], 3Ah ; ':'
0x1800cf484  jnz     short loc_1800CF4BC
0x1800cf486  lea     rax, [rsp+1468h+var_1318]
0x1800cf48e  cmp     qword ptr [rsp+1468h+var_1308+8], rdi
0x1800cf496  cmova   rax, [rsp+1468h+var_1318]
0x1800cf49f  cmp     word ptr [rax+4], 5Ch ; '\'
0x1800cf4a4  jnz     short loc_1800CF4BC
0x1800cf4a6  lea     rdx, [rsp+1468h+var_1318]
0x1800cf4ae  lea     rcx, [rsp+1468h+pszPath]
0x1800cf4b6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800cf4bb  nop
0x1800cf4bc  lea     rcx, [rsp+1468h+var_1318]
0x1800cf4c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cf4c9  mov     rdx, [rsp+1468h+pszPath]
0x1800cf4d1  cmp     [rsp+1468h+var_1328], 2
0x1800cf4da  jb      loc_1800CF661
0x1800cf4e0  lea     rax, [rsp+1468h+pszPath]
0x1800cf4e8  cmp     [rsp+1468h+var_1320], rdi
0x1800cf4f0  cmova   rax, rdx
0x1800cf4f4  cmp     word ptr [rax], 5Ch ; '\'
0x1800cf4f8  jnz     loc_1800CF60E
0x1800cf4fe  lea     rax, [rsp+1468h+pszPath]
0x1800cf506  cmp     [rsp+1468h+var_1320], rdi
0x1800cf50e  cmova   rax, rdx
0x1800cf512  cmp     word ptr [rax+2], 5Ch ; '\'
0x1800cf517  jz      loc_1800CF60E
0x1800cf51d  lea     rdx, [rsp+1468h+Buffer]; lpBuffer
0x1800cf525  mov     ecx, ebx; nBufferLength
0x1800cf527  call    cs:__imp_GetCurrentDirectoryW
0x1800cf52d  lea     rdx, [rsp+1468h+Buffer]
0x1800cf535  lea     rcx, [rsp+1468h+var_12B8]
0x1800cf53d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cf542  nop
0x1800cf543  mov     r9d, 2
0x1800cf549  xor     r8d, r8d
0x1800cf54c  lea     rdx, [rsp+1468h+var_12B8]
0x1800cf554  lea     rcx, [rsp+1468h+var_12D8]
0x1800cf55c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@_K1AEBV?$allocator@G@1@@Z; std::wstring::wstring(std::wstring const &,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
  ... truncated ...
```
