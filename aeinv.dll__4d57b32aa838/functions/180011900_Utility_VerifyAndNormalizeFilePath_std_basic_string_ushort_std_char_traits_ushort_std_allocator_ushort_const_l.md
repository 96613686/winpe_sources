# Utility::VerifyAndNormalizeFilePath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,long &)

- ea: `0x180011900`
- end: `0x180012392`
- name: `?VerifyAndNormalizeFilePath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@AEAJ@Z`
- size: `2706`
- prototype: `__int64 __fastcall(__int64, __int64, signed int *)`
- caller_count: `4`
- callee_count: `23`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18001118c`
- `0x1800114a4`
- `0x1800114d4`
- `0x180055dcc`

## callees

- `0x180005ed0`
- `0x1800118d0`
- `0x180011900`
- `0x1800150ac`
- `0x1800175b0`
- `0x1800176e0`
- `0x180018300`
- `0x180018450`
- `0x180018a60`
- `0x1800197d4`
- `0x18001bd90`
- `0x18001becc`
- `0x18001ccfc`
- `0x18001ea80`
- `0x180022500`
- `0x1800404c4`
- `0x180041ef8`
- `0x180045480`
- `0x180046c3c`
- `0x180052bfc`
- `0x180059920`
- `0x180116360`
- `0x180125400`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180011c21`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180011e74`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180012042`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180012103`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180011c21`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180011e74`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180012042`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180012103`
- `KERNEL32!GetCurrentDirectoryW` at `0x180011f3f`
- `KERNEL32!GetCurrentDirectoryW` at `0x180011f3f`
- `KERNEL32!GetFileAttributesW` at `0x1800121cd`
- `KERNEL32!GetFileAttributesW` at `0x180012247`
- `KERNEL32!GetFileAttributesW` at `0x1800121cd`
- `KERNEL32!GetFileAttributesW` at `0x180012247`
- `KERNEL32!LocalFree` at `0x180012289`
- `KERNEL32!LocalFree` at `0x180012289`
- `KERNEL32!GetLastError` at `0x180011ff7`
- `KERNEL32!GetLastError` at `0x180012269`
- `KERNEL32!GetLastError` at `0x180011ff7`
- `KERNEL32!GetLastError` at `0x180012269`
- `SHLWAPI!PathFileExistsW` at `0x180011fd6`
- `SHLWAPI!PathFileExistsW` at `0x180011fd6`
- `SHLWAPI!PathIsNetworkPathW` at `0x18001214c`
- `SHLWAPI!PathIsNetworkPathW` at `0x18001214c`
- `SHELL32!CommandLineToArgvW` at `0x180012203`
- `SHELL32!CommandLineToArgvW` at `0x180012203`

## string_xrefs

- `0x180011a3f`: `PathCchCanonicalizeEx failed: [0x%08x]`
- `0x180012174`: `Unsupported network path: %ws`
- `0x180011a4c`: `Utility::VerifyAndNormalizeFilePath`
- `0x180012181`: `Utility::VerifyAndNormalizeFilePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Utility::VerifyAndNormalizeFilePath(__int64 a1, __int64 a2, signed int *a3)
{
  const unsigned __int16 *v6; // r8
  unsigned __int16 *v7; // rcx
  int v8; // edi
  unsigned __int64 v9; // rdx
  LPCWSTR *v10; // rax
  __int64 v11; // rdi
  __int64 v12; // rdx
  unsigned __int16 *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned __int16 **v17; // rcx
  unsigned __int16 *v18; // rdx
  wchar_t *v19; // rcx
  unsigned __int16 **v20; // rax
  __int64 v21; // rdx
  unsigned __int16 **v22; // rcx
  unsigned __int16 **v23; // rax
  unsigned __int16 **v24; // rax
  LPCWSTR *v25; // rax
  LPCWSTR v26; // rdx
  __int64 v27; // rax
  unsigned __int16 *v28; // rdx
  wchar_t *v29; // rcx
  unsigned __int16 **v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rax
  unsigned __int16 **v33; // rcx
  unsigned __int16 **v34; // rax
  unsigned __int16 **v35; // rax
  LPCWSTR *v36; // rax
  LPCWSTR *v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  const WCHAR *v40; // rcx
  signed int LastError; // eax
  LPCWSTR *v42; // rcx
  int v43; // eax
  LPCWSTR *v44; // rax
  LPCWSTR *v45; // rax
  LPCWSTR *v46; // rax
  LPCWSTR *v47; // rax
  LPCWSTR *v48; // rax
  LPCWSTR *v49; // rcx
  LPCWSTR *v50; // rax
  LPCWSTR *v51; // rcx
  const WCHAR *v52; // rcx
  DWORD FileAttributesW; // eax
  const WCHAR *v54; // rcx
  LPWSTR *v55; // rbx
  LPWSTR v56; // rdx
  const WCHAR *v57; // rcx
  signed int v58; // eax
  __int64 LongPath; // rax
  __int64 result; // rax
  __int64 v61; // rcx
  const struct wil::FailureInfo *v62; // r9
  int pNumArgs; // [rsp+30h] [rbp-1448h] BYREF
  __int64 v64; // [rsp+38h] [rbp-1440h]
  __int64 v65; // [rsp+40h] [rbp-1438h]
  LPWSTR *v66; // [rsp+48h] [rbp-1430h]
  void **v67; // [rsp+50h] [rbp-1428h] BYREF
  __int64 v68; // [rsp+58h] [rbp-1420h] BYREF
  _BYTE v69[40]; // [rsp+70h] [rbp-1408h] BYREF
  __int128 v70; // [rsp+98h] [rbp-13E0h]
  __int128 v71; // [rsp+A8h] [rbp-13D0h]
  __int128 v72; // [rsp+B8h] [rbp-13C0h]
  __int128 v73; // [rsp+C8h] [rbp-13B0h]
  __int128 v74; // [rsp+D8h] [rbp-13A0h]
  __int128 v75; // [rsp+E8h] [rbp-1390h]
  __int128 v76; // [rsp+F8h] [rbp-1380h]
  __int128 v77; // [rsp+108h] [rbp-1370h]
  __int64 v78; // [rsp+118h] [rbp-1360h]
  LPCWSTR pszPath[2]; // [rsp+140h] [rbp-1338h] BYREF
  unsigned __int64 v80; // [rsp+150h] [rbp-1328h]
  unsigned __int64 v81; // [rsp+158h] [rbp-1320h]
  unsigned __int16 *v82[3]; // [rsp+160h] [rbp-1318h] BYREF
  unsigned __int64 v83; // [rsp+178h] [rbp-1300h]
  unsigned __int16 *v84[3]; // [rsp+180h] [rbp-12F8h] BYREF
  unsigned __int64 v85; // [rsp+198h] [rbp-12E0h]
  _BYTE v86[32]; // [rsp+1A0h] [rbp-12D8h] BYREF
  unsigned __int16 *v87[3]; // [rsp+1C0h] [rbp-12B8h] BYREF
  unsigned __int64 v88; // [rsp+1D8h] [rbp-12A0h]
  _BYTE v89[32]; // [rsp+1E0h] [rbp-1298h] BYREF
  _BYTE v90[32]; // [rsp+200h] [rbp-1278h] BYREF
  _OWORD Buffer[9]; // [rsp+220h] [rbp-1258h] BYREF
  __int64 v92; // [rsp+2B0h] [rbp-11C8h]
  _BYTE v93[4096]; // [rsp+430h] [rbp-1048h] BYREF

  v65 = -2;
  try
  {
    v64 = a1;
    std::wstring::wstring(pszPath, 0);
    std::wstring::wstring(v87, 261);
    while ( 1 )
    {
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v6 = (const unsigned __int16 *)a2;
      else
        v6 = *(const unsigned __int16 **)a2;
      v7 = (unsigned __int16 *)v87;
      if ( v88 > 7 )
        v7 = v87[0];
      v8 = PathCchCanonicalizeEx(v7, v88, v6, PATHCCH_ALLOW_LONG_PATHS);
      if ( (_WORD)v8 != 122 || v88 >= 0x8000 )
        break;
      v9 = 2 * v88;
      if ( 2 * v88 > 0x8000 )
        v9 = 0x8000;
      std::wstring::resize(v87, v9);
    }
    std::wstring::operator=(pszPath, v87);
    if ( v8 < 0 )
    {
      std::wstring::operator=(pszPath, a2);
      AslLogCallPrintf(
        1,
        (unsigned int)"Utility::VerifyAndNormalizeFilePath",
        1703,
        (unsigned int)"PathCchCanonicalizeEx failed: [0x%08x]");
      v11 = -1;
    }
    else
    {
      v10 = pszPath;
      if ( v81 > 7 )
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
    v14 = Utility::TrimTrailingBackSlashFromPath(v86, pszPath);
    std::wstring::operator=(pszPath, v14);
    std::wstring::~wstring(v86);
    v15 = Utility::ToLower((__int64)v86, (__int64 *)pszPath);
    std::wstring::operator=(pszPath, v15);
    std::wstring::~wstring(v86);
    if ( v80 >= 0x104 )
    {
      if ( std::wstring::find(pszPath, Utility::PathPrefixLongPath) )
      {
        v16 = std::operator+<unsigned short>(v86, Utility::PathPrefixLongPath, pszPath);
        std::wstring::operator=(pszPath, v16);
        v17 = (unsigned __int16 **)v86;
LABEL_78:
        std::wstring::~wstring(v17);
        goto LABEL_79;
      }
      goto LABEL_79;
    }
    if ( !std::wstring::find(pszPath, Utility::PathPrefixDeviceDrivePath) && v80 < 0x104 )
    {
      std::wstring::wstring(v84);
      std::wstring::resize(v84, 260);
      v18 = (unsigned __int16 *)v84;
      if ( v85 > 7 )
        v18 = v84[0];
      v19 = (wchar_t *)pszPath;
      if ( v81 > 7 )
        v19 = (wchar_t *)pszPath[0];
      if ( (int)ConvertDevicePathToDrivePath(v19, v18) >= 0 )
      {
        v20 = v84;
        if ( v85 > 7 )
          v20 = (unsigned __int16 **)v84[0];
        v21 = -1;
        do
          ++v21;
        while ( *((_WORD *)v20 + v21) );
        std::wstring::resize(v84, v21);
        if ( v84[2] >= (unsigned __int16 *)3 )
        {
          v22 = v84;
          if ( v85 > 7 )
            v22 = (unsigned __int16 **)v84[0];
          if ( (unsigned int)_o_iswalpha(*(unsigned __int16 *)v22) )
          {
            v23 = v84;
            if ( v85 > 7 )
              v23 = (unsigned __int16 **)v84[0];
            if ( *((_WORD *)v23 + 1) == 58 )
            {
              v24 = v84;
              if ( v85 > 7 )
                v24 = (unsigned __int16 **)v84[0];
              if ( *((_WORD *)v24 + 2) == 92 )
                std::wstring::operator=(pszPath, v84);
            }
          }
        }
      }
      v17 = v84;
      goto LABEL_78;
    }
    if ( !v80 )
    {
LABEL_79:
      v26 = pszPath[0];
LABEL_80:
      if ( v80 >= 2 )
      {
        v36 = pszPath;
        if ( v81 > 7 )
          v36 = (LPCWSTR *)v26;
        if ( *(_WORD *)v36 == 92 )
        {
          v37 = pszPath;
          if ( v81 > 7 )
            v37 = (LPCWSTR *)v26;
          if ( *((_WORD *)v37 + 1) != 92 )
          {
            GetCurrentDirectoryW(0x104u, (LPWSTR)Buffer);
            std::wstring::wstring(v86, Buffer);
            v38 = std::wstring::substr(v86, v89, 0, 2);
            v39 = std::operator+<unsigned short>(v90, v38, pszPath);
            std::wstring::operator=(pszPath, v39);
            std::wstring::~wstring(v90);
            std::wstring::~wstring(v89);
            v40 = (const WCHAR *)pszPath;
            if ( v81 > 7 )
              v40 = pszPath[0];
            if ( !PathFileExistsW(v40) )
            {
              std::wstring::_Assign<unsigned short>(pszPath, &byte_1801389F0);
              LastError = GetLastError();
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
              *a3 = LastError;
            }
            std::wstring::~wstring(v86);
            v26 = pszPath[0];
          }
        }
        if ( v80 >= 2 )
        {
          v42 = pszPath;
          if ( v81 > 7 )
            v42 = (LPCWSTR *)v26;
          v43 = _o_iswalpha(*(unsigned __int16 *)v42);
          v26 = pszPath[0];
          if ( v43 )
          {
            v44 = pszPath;
            if ( v81 > 7 )
              v44 = (LPCWSTR *)pszPath[0];
            if ( *((_WORD *)v44 + 1) == 58 )
              goto LABEL_120;
          }
        }
      }
      if ( v80 <= 0x104 )
        goto LABEL_145;
      v45 = pszPath;
      if ( v81 > 7 )
        v45 = (LPCWSTR *)v26;
      if ( *(_WORD *)v45 != 92 )
        goto LABEL_145;
      v46 = pszPath;
      if ( v81 > 7 )
        v46 = (LPCWSTR *)v26;
      if ( *((_WORD *)v46 + 1) != 92 )
        goto LABEL_145;
      v47 = pszPath;
      if ( v81 > 7 )
        v47 = (LPCWSTR *)v26;
      if ( *((_WORD *)v47 + 2) != 63 )
        goto LABEL_145;
      v48 = pszPath;
      if ( v81 > 7 )
        v48 = (LPCWSTR *)v26;
      if ( *((_WORD *)v48 + 3) != 92 )
        goto LABEL_145;
      v49 = pszPath;
      if ( v81 > 7 )
        v49 = (LPCWSTR *)v26;
      if ( !(unsigned int)_o_iswalpha(*((unsigned __int16 *)v49 + 4)) )
        goto LABEL_145;
      v50 = pszPath;
      v26 = pszPath[0];
      if ( v81 > 7 )
        v50 = (LPCWSTR *)pszPath[0];
      if ( *((_WORD *)v50 + 5) == 58 )
      {
LABEL_120:
        v51 = pszPath;
        if ( v81 > 7 )
          v51 = (LPCWSTR *)v26;
        if ( PathIsNetworkPathW((LPCWSTR)v51) )
        {
          AslLogCallPrintf(
            3,
            (unsigned int)"Utility::VerifyAndNormalizeFilePath",
            1833,
            (unsigned int)"Unsupported network path: %ws");
          std::wstring::_Assign<unsigned short>(pszPath, &byte_1801389F0);
          *a3 = -2147467259;
        }
        else
        {
          v52 = (const WCHAR *)pszPath;
          if ( v81 > 7 )
            v52 = pszPath[0];
          FileAttributesW = GetFileAttributesW(v52);
          v54 = (const WCHAR *)pszPath;
          if ( FileAttributesW == -1 )
          {
            pNumArgs = 0;
            if ( v81 > 7 )
              v54 = pszPath[0];
            v55 = CommandLineToArgvW(v54, &pNumArgs);
            v66 = v55;
            v56 = *v55;
            do
              ++v11;
            while ( v56[v11] );
            std::wstring::_Assign<unsigned short>(pszPath, v56);
            v57 = (const WCHAR *)pszPath;
            if ( v81 > 7 )
              v57 = pszPath[0];
            if ( GetFileAttributesW(v57) == -1 )
            {
              std::wstring::_Assign<unsigned short>(pszPath, &byte_1801389F0);
              v58 = GetLastError();
              if ( v58 > 0 )
                v58 = (unsigned __int16)v58 | 0x80070000;
              *a3 = v58;
            }
            if ( v55 )
              LocalFree(v55);
          }
          else if ( (FileAttributesW & 0x11440) != 0 )
          {
            std::wstring::_Assign<unsigned short>(pszPath, &byte_1801389F0);
            *a3 = -2147024864;
          }
          else if ( (FileAttributesW & 0x10) != 0 )
          {
            std::wstring::_Assign<unsigned short>(pszPath, &byte_1801389F0);
            *a3 = -2147024894;
          }
          else if ( std::wstring::find(pszPath, L"~", 0) != -1 )
          {
            LongPath = Utility::GetLongPath((__int64)v89, (const WCHAR *)pszPath);
            std::wstring::operator=(pszPath, LongPath);
            std::wstring::~wstring(v89);
            *a3 = 0;
          }
        }
      }
      else
      {
LABEL_145:
        std::wstring::_Assign<unsigned short>(pszPath, &byte_1801389F0);
        *a3 = -2147024893;
      }
      Utility::ToLower(a1, (__int64 *)pszPath);
      std::wstring::~wstring(v87);
      std::wstring::~wstring(pszPath);
      return a1;
    }
    v25 = pszPath;
    v26 = pszPath[0];
    if ( v81 > 7 )
      v25 = (LPCWSTR *)pszPath[0];
    if ( *(_WORD *)v25 != 92 )
      goto LABEL_80;
    std::wstring::wstring(v82);
    if ( !std::wstring::find(pszPath, Utility::PathPrefixGlobal) )
    {
      v27 = std::wstring::substr(pszPath, v86, qword_180183090, v80);
      std::wstring::operator=(pszPath, v27);
      std::wstring::~wstring(v86);
      if ( v80 < 0x104 )
      {
        std::wstring::resize(v82, 260);
        v28 = (unsigned __int16 *)v82;
        if ( v83 > 7 )
          v28 = v82[0];
        v29 = (wchar_t *)pszPath;
        if ( v81 > 7 )
          v29 = (wchar_t *)pszPath[0];
        if ( (int)ConvertDevicePathToDrivePath(v29, v28) >= 0 )
        {
          v30 = v82;
          if ( v83 > 7 )
            v30 = (unsigned __int16 **)v82[0];
          v31 = -1;
          do
            ++v31;
          while ( *((_WORD *)v30 + v31) );
          std::wstring::resize(v82, v31);
        }
      }
      goto LABEL_66;
    }
    if ( std::wstring::find(pszPath, Utility::PathPrefixLongPath) )
    {
      if ( std::wstring::find(pszPath, Utility::PathPrefixDrivePath) )
      {
LABEL_66:
        if ( v82[2] >= (unsigned __int16 *)3 )
        {
          v33 = v82;
          if ( v83 > 7 )
            v33 = (unsigned __int16 **)v82[0];
          if ( (unsigned int)_o_iswalpha(*(unsigned __int16 *)v33) )
          {
            v34 = v82;
            if ( v83 > 7 )
              v34 = (unsigned __int16 **)v82[0];
            if ( *((_WORD *)v34 + 1) == 58 )
            {
              v35 = v82;
              if ( v83 > 7 )
                v35 = (unsigned __int16 **)v82[0];
              if ( *((_WORD *)v35 + 2) == 92 )
                std::wstring::operator=(pszPath, v82);
            }
          }
        }
        v17 = v82;
        goto LABEL_78;
      }
      v32 = std::wstring::substr(pszPath, v86, qword_1801830D0, v80);
    }
    else
    {
      v32 = std::wstring::substr(pszPath, v86, qword_1801830B0, v80);
    }
    std::wstring::operator=(v82, v32);
    std::wstring::~wstring(v86);
    goto LABEL_66;
  }
  catch ( wil::ResultException v69 )
  {
    memset_0(v93, 0, sizeof(v93));
    Buffer[0] = *(_OWORD *)&v69[24];
    Buffer[1] = v70;
    Buffer[2] = v71;
    Buffer[3] = v72;
    Buffer[4] = v73;
    Buffer[5] = v74;
    Buffer[6] = v75;
    Buffer[7] = v76;
    Buffer[8] = v77;
    v92 = v78;
    wil::GetFailureLogString((wil *)v93, (unsigned __int16 *)0x800, (unsigned __int64)Buffer, v62);
    AslLogCallPrintf(1, (unsigned int)"Utility::VerifyAndNormalizeFilePath", 1890, (unsigned int)"%ws");
    wil::ResultException::~ResultException((wil::ResultException *)v69);
    goto LABEL_147;
  }
  catch ( std::exception v67 )
  {
    GetLastError();
    AslLogCallPrintf(1, (unsigned int)"Utility::VerifyAndNormalizeFilePath", 1895, (unsigned int)"Exception: 0x%08x %s");
    v67 = &std::exception::`vftable';
    o___std_exception_destroy_0(&v68);
    goto LABEL_147;
  }
  catch ( ... )
  {
    AslLogCallPrintf(1, (unsigned int)"Utility::VerifyAndNormalizeFilePath", 1900, (unsigned int)"Exception: [0x%08x]");
LABEL_147:
    std::wstring::wstring(v64);
    return v61;
  }
  return result;
}

```

## disassembly

```asm
0x180011900  push    rbx
0x180011902  push    rsi
0x180011903  push    rdi
0x180011904  push    r12
0x180011906  push    r13
0x180011908  push    r14
0x18001190a  push    r15
0x18001190c  mov     eax, 1440h
0x180011911  call    _alloca_probe
0x180011916  sub     rsp, rax
0x180011919  mov     [rsp+1478h+var_1438], 0FFFFFFFFFFFFFFFEh
0x180011922  mov     rax, cs:__security_cookie
0x180011929  xor     rax, rsp
0x18001192c  mov     [rsp+1478h+var_48], rax
0x180011934  mov     rsi, r8
0x180011937  mov     rbx, rdx
0x18001193a  mov     r14, rcx
0x18001193d  mov     [rsp+1478h+var_1440], rcx
0x180011942  xor     r12d, r12d
0x180011945  xor     edx, edx
0x180011947  lea     rcx, [rsp+1478h+pszPath]
0x18001194f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x180011954  nop
0x180011955  mov     edx, 105h
0x18001195a  lea     rcx, [rsp+1478h+var_12B8]
0x180011962  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x180011967  nop
0x180011968  lea     r15d, [r12+7]
0x18001196d  mov     r13d, 8000h
0x180011973  cmp     [rbx+18h], r15
0x180011977  jbe     short loc_18001197E
0x180011979  mov     r8, [rbx]
0x18001197c  jmp     short loc_180011981
0x18001197e  mov     r8, rbx; unsigned __int16 *
0x180011981  mov     rdx, [rsp+1478h+var_12A0]; unsigned __int64
0x180011989  lea     rcx, [rsp+1478h+var_12B8]
0x180011991  cmp     rdx, r15
0x180011994  cmova   rcx, [rsp+1478h+var_12B8]; unsigned __int16 *
0x18001199d  mov     r9d, 1; enum PATHCCH_OPTIONS
0x1800119a3  call    ?PathCchCanonicalizeEx@@YAJPEAG_KPEBGW4PATHCCH_OPTIONS@@@Z; PathCchCanonicalizeEx(ushort *,unsigned __int64,ushort const *,PATHCCH_OPTIONS)
0x1800119a8  mov     edi, eax
0x1800119aa  cmp     di, 7Ah ; 'z'
0x1800119ae  jnz     short loc_1800119D6
0x1800119b0  mov     rdx, [rsp+1478h+var_12A0]
0x1800119b8  cmp     rdx, r13
0x1800119bb  jnb     short loc_1800119D6
0x1800119bd  add     rdx, rdx
0x1800119c0  cmp     rdx, r13
0x1800119c3  cmova   rdx, r13
0x1800119c7  lea     rcx, [rsp+1478h+var_12B8]
0x1800119cf  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800119d4  jmp     short loc_180011973
0x1800119d6  lea     rdx, [rsp+1478h+var_12B8]
0x1800119de  lea     rcx, [rsp+1478h+pszPath]
0x1800119e6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800119eb  test    edi, edi
0x1800119ed  js      short loc_180011A2B
0x1800119ef  lea     rax, [rsp+1478h+pszPath]
0x1800119f7  cmp     [rsp+1478h+var_1320], r15
0x1800119ff  cmova   rax, [rsp+1478h+pszPath]
0x180011a08  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011a0c  mov     rdx, rdi
0x180011a0f  inc     rdx
0x180011a12  cmp     [rax+rdx*2], r12w
0x180011a17  jnz     short loc_180011A0F
0x180011a19  inc     rdx
0x180011a1c  lea     rcx, [rsp+1478h+pszPath]
0x180011a24  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180011a29  jmp     short loc_180011A61
0x180011a2b  mov     rdx, rbx
0x180011a2e  lea     rcx, [rsp+1478h+pszPath]
0x180011a36  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180011a3b  mov     dword ptr [rsp+1478h+var_1458], edi
0x180011a3f  lea     r9, aPathcchcanonic; "PathCchCanonicalizeEx failed: [0x%08x]"
0x180011a46  mov     r8d, 6A7h
0x180011a4c  lea     rdx, aUtilityVerifya; "Utility::VerifyAndNormalizeFilePath"
0x180011a53  mov     ecx, 1
0x180011a58  call    AslLogCallPrintf
0x180011a5d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011a61  lea     rcx, [rsp+1478h+pszPath]
0x180011a69  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x180011a6e  mov     rdx, rax
0x180011a71  lea     rcx, [rsp+1478h+pszPath]
0x180011a79  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180011a7e  lea     rdx, [rsp+1478h+pszPath]
0x180011a86  lea     rcx, [rsp+1478h+var_12D8]
0x180011a8e  call    ?TrimTrailingBackSlashFromPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::TrimTrailingBackSlashFromPath(std::wstring const &)
0x180011a93  mov     rdx, rax
0x180011a96  lea     rcx, [rsp+1478h+pszPath]
0x180011a9e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180011aa3  lea     rcx, [rsp+1478h+var_12D8]
0x180011aab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011ab0  lea     rdx, [rsp+1478h+pszPath]
0x180011ab8  lea     rcx, [rsp+1478h+var_12D8]
0x180011ac0  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x180011ac5  mov     rdx, rax
0x180011ac8  lea     rcx, [rsp+1478h+pszPath]
0x180011ad0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180011ad5  lea     rcx, [rsp+1478h+var_12D8]
0x180011add  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011ae2  mov     ebx, 104h
0x180011ae7  lea     rcx, [rsp+1478h+pszPath]
0x180011aef  cmp     [rsp+1478h+var_1328], rbx
0x180011af7  jb      short loc_180011B47
0x180011af9  lea     rdx, ?PathPrefixLongPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixLongPath
0x180011b00  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x180011b05  test    rax, rax
0x180011b08  jz      loc_180011EE1
0x180011b0e  lea     r8, [rsp+1478h+pszPath]
0x180011b16  lea     rdx, ?PathPrefixLongPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixLongPath
0x180011b1d  lea     rcx, [rsp+1478h+var_12D8]
0x180011b25  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@0@Z; std::operator+<ushort>(std::wstring const &,std::wstring const &)
0x180011b2a  mov     rdx, rax
0x180011b2d  lea     rcx, [rsp+1478h+pszPath]
0x180011b35  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180011b3a  lea     rcx, [rsp+1478h+var_12D8]
0x180011b42  jmp     loc_180011EDC
0x180011b47  lea     rdx, ?PathPrefixDeviceDrivePath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixDeviceDrivePath
0x180011b4e  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x180011b53  test    rax, rax
0x180011b56  jnz     loc_180011C8E
0x180011b5c  cmp     [rsp+1478h+var_1328], rbx
0x180011b64  jnb     loc_180011C8E
0x180011b6a  lea     rcx, [rsp+1478h+var_12F8]
0x180011b72  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180011b77  nop
0x180011b78  mov     rdx, rbx
0x180011b7b  lea     rcx, [rsp+1478h+var_12F8]
0x180011b83  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180011b88  lea     rdx, [rsp+1478h+var_12F8]
0x180011b90  cmp     [rsp+1478h+var_12E0], r15
0x180011b98  cmova   rdx, [rsp+1478h+var_12F8]; unsigned __int16 *
0x180011ba1  lea     rcx, [rsp+1478h+pszPath]
0x180011ba9  cmp     [rsp+1478h+var_1320], r15
0x180011bb1  cmova   rcx, [rsp+1478h+pszPath]; String1
0x180011bba  call    ?ConvertDevicePathToDrivePath@@YAJPEBGPEAG@Z; ConvertDevicePathToDrivePath(ushort const *,ushort *)
0x180011bbf  test    eax, eax
0x180011bc1  js      loc_180011C81
0x180011bc7  lea     rax, [rsp+1478h+var_12F8]
0x180011bcf  cmp     [rsp+1478h+var_12E0], r15
0x180011bd7  cmova   rax, [rsp+1478h+var_12F8]
0x180011be0  mov     rdx, rdi
0x180011be3  inc     rdx
0x180011be6  cmp     [rax+rdx*2], r12w
0x180011beb  jnz     short loc_180011BE3
0x180011bed  lea     rcx, [rsp+1478h+var_12F8]
0x180011bf5  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180011bfa  cmp     [rsp+1478h+var_12E8], 3
0x180011c03  jb      short loc_180011C81
0x180011c05  lea     rcx, [rsp+1478h+var_12F8]
0x180011c0d  cmp     [rsp+1478h+var_12E0], r15
0x180011c15  cmova   rcx, [rsp+1478h+var_12F8]
0x180011c1e  movzx   ecx, word ptr [rcx]
0x180011c21  call    cs:__imp__o_iswalpha
0x180011c27  test    eax, eax
0x180011c29  jz      short loc_180011C81
0x180011c2b  lea     rax, [rsp+1478h+var_12F8]
0x180011c33  cmp     [rsp+1478h+var_12E0], r15
0x180011c3b  cmova   rax, [rsp+1478h+var_12F8]
0x180011c44  cmp     word ptr [rax+2], 3Ah ; ':'
0x180011c49  jnz     short loc_180011C81
0x180011c4b  lea     rax, [rsp+1478h+var_12F8]
0x180011c53  cmp     [rsp+1478h+var_12E0], r15
0x180011c5b  cmova   rax, [rsp+1478h+var_12F8]
0x180011c64  cmp     word ptr [rax+4], 5Ch ; '\'
0x180011c69  jnz     short loc_180011C81
0x180011c6b  lea     rdx, [rsp+1478h+var_12F8]
0x180011c73  lea     rcx, [rsp+1478h+pszPath]
0x180011c7b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180011c80  nop
0x180011c81  lea     rcx, [rsp+1478h+var_12F8]
0x180011c89  jmp     loc_180011EDC
0x180011c8e  cmp     [rsp+1478h+var_1328], 1
0x180011c97  jb      loc_180011EE1
0x180011c9d  lea     rax, [rsp+1478h+pszPath]
0x180011ca5  mov     rdx, [rsp+1478h+pszPath]
0x180011cad  cmp     [rsp+1478h+var_1320], r15
0x180011cb5  cmova   rax, rdx
0x180011cb9  cmp     word ptr [rax], 5Ch ; '\'
0x180011cbd  jnz     loc_180011EE9
0x180011cc3  lea     rcx, [rsp+1478h+var_1318]
0x180011ccb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180011cd0  nop
0x180011cd1  lea     rdx, ?PathPrefixGlobal@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixGlobal
0x180011cd8  lea     rcx, [rsp+1478h+pszPath]
0x180011ce0  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x180011ce5  lea     rcx, [rsp+1478h+pszPath]
0x180011ced  test    rax, rax
0x180011cf0  jnz     loc_180011DC4
0x180011cf6  mov     r9, [rsp+1478h+var_1328]
0x180011cfe  mov     r8, cs:qword_180183090
0x180011d05  lea     rdx, [rsp+1478h+var_12D8]
0x180011d0d  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180011d12  mov     rdx, rax
0x180011d15  lea     rcx, [rsp+1478h+pszPath]
0x180011d1d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180011d22  lea     rcx, [rsp+1478h+var_12D8]
0x180011d2a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011d2f  cmp     [rsp+1478h+var_1328], rbx
0x180011d37  jnb     loc_180011E4D
0x180011d3d  mov     rdx, rbx
0x180011d40  lea     rcx, [rsp+1478h+var_1318]
0x180011d48  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180011d4d  lea     rdx, [rsp+1478h+var_1318]
0x180011d55  cmp     [rsp+1478h+var_1300], r15
0x180011d5d  cmova   rdx, [rsp+1478h+var_1318]; unsigned __int16 *
0x180011d66  lea     rcx, [rsp+1478h+pszPath]
0x180011d6e  cmp     [rsp+1478h+var_1320], r15
0x180011d76  cmova   rcx, [rsp+1478h+pszPath]; String1
0x180011d7f  call    ?ConvertDevicePathToDrivePath@@YAJPEBGPEAG@Z; ConvertDevicePathToDrivePath(ushort const *,ushort *)
0x180011d84  test    eax, eax
0x180011d86  js      loc_180011E4D
0x180011d8c  lea     rax, [rsp+1478h+var_1318]
0x180011d94  cmp     [rsp+1478h+var_1300], r15
0x180011d9c  cmova   rax, [rsp+1478h+var_1318]
0x180011da5  mov     rdx, rdi
0x180011da8  inc     rdx
0x180011dab  cmp     [rax+rdx*2], r12w
0x180011db0  jnz     short loc_180011DA8
0x180011db2  lea     rcx, [rsp+1478h+var_1318]
0x180011dba  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180011dbf  jmp     loc_180011E4D
0x180011dc4  lea     rdx, ?PathPrefixLongPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixLongPath
0x180011dcb  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x180011dd0  lea     rcx, [rsp+1478h+pszPath]
0x180011dd8  test    rax, rax
0x180011ddb  jnz     short loc_180011DFB
0x180011ddd  mov     r9, [rsp+1478h+var_1328]
0x180011de5  mov     r8, cs:qword_1801830B0
0x180011dec  lea     rdx, [rsp+1478h+var_12D8]
0x180011df4  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180011df9  jmp     short loc_180011E30
0x180011dfb  lea     rdx, ?PathPrefixDrivePath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::PathPrefixDrivePath
0x180011e02  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x180011e07  test    rax, rax
0x180011e0a  jnz     short loc_180011E4D
0x180011e0c  mov     r9, [rsp+1478h+var_1328]
0x180011e14  mov     r8, cs:qword_1801830D0
0x180011e1b  lea     rdx, [rsp+1478h+var_12D8]
0x180011e23  lea     rcx, [rsp+1478h+pszPath]
0x180011e2b  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180011e30  mov     rdx, rax
0x180011e33  lea     rcx, [rsp+1478h+var_1318]
0x180011e3b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180011e40  lea     rcx, [rsp+1478h+var_12D8]
0x180011e48  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011e4d  cmp     [rsp+1478h+var_1308], 3
0x180011e56  jb      short loc_180011ED4
0x180011e58  lea     rcx, [rsp+1478h+var_1318]
0x180011e60  cmp     [rsp+1478h+var_1300], r15
0x180011e68  cmova   rcx, [rsp+1478h+var_1318]
0x180011e71  movzx   ecx, word ptr [rcx]
0x180011e74  call    cs:__imp__o_iswalpha
0x180011e7a  test    eax, eax
0x180011e7c  jz      short loc_180011ED4
0x180011e7e  lea     rax, [rsp+1478h+var_1318]
0x180011e86  cmp     [rsp+1478h+var_1300], r15
0x180011e8e  cmova   rax, [rsp+1478h+var_1318]
0x180011e97  cmp     word ptr [rax+2], 3Ah ; ':'
0x180011e9c  jnz     short loc_180011ED4
0x180011e9e  lea     rax, [rsp+1478h+var_1318]
0x180011ea6  cmp     [rsp+1478h+var_1300], r15
0x180011eae  cmova   rax, [rsp+1478h+var_1318]
0x180011eb7  cmp     word ptr [rax+4], 5Ch ; '\'
0x180011ebc  jnz     short loc_180011ED4
0x180011ebe  lea     rdx, [rsp+1478h+var_1318]
0x180011ec6  lea     rcx, [rsp+1478h+pszPath]
0x180011ece  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180011ed3  nop
0x180011ed4  lea     rcx, [rsp+1478h+var_1318]
0x180011edc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180011ee1  mov     rdx, [rsp+1478h+pszPath]
0x180011ee9  cmp     [rsp+1478h+var_1328], 2
0x180011ef2  jb      loc_180012073
0x180011ef8  lea     rax, [rsp+1478h+pszPath]
0x180011f00  cmp     [rsp+1478h+var_1320], r15
0x180011f08  cmova   rax, rdx
0x180011f0c  cmp     word ptr [rax], 5Ch ; '\'
0x180011f10  jnz     loc_180012020
0x180011f16  lea     rax, [rsp+1478h+pszPath]
0x180011f1e  cmp     [rsp+1478h+var_1320], r15
0x180011f26  cmova   rax, rdx
0x180011f2a  cmp     word ptr [rax+2], 5Ch ; '\'
0x180011f2f  jz      loc_180012020
0x180011f35  lea     rdx, [rsp+1478h+Buffer]; lpBuffer
0x180011f3d  mov     ecx, ebx; nBufferLength
0x180011f3f  call    cs:__imp_GetCurrentDirectoryW
0x180011f45  lea     rdx, [rsp+1478h+Buffer]
0x180011f4d  lea     rcx, [rsp+1478h+var_12D8]
0x180011f55  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011f5a  nop
0x180011f5b  mov     r9d, 2
0x180011f61  xor     r8d, r8d
0x180011f64  lea     rdx, [rsp+1478h+var_1298]
0x180011f6c  lea     rcx, [rsp+1478h+var_12D8]
0x180011f74  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180011f79  nop
0x180011f7a  lea     r8, [rsp+1478h+pszPath]
0x180011f82  mov     rdx, rax
0x180011f85  lea     rcx, [rsp+1478h+var_1278]
  ... truncated ...
```
