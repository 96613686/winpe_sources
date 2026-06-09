# PathExpand

- ea: `0x18010e940`
- end: `0x18010f053`
- name: `PathExpand`
- size: `1811`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x1800d3070`
- `0x1802ae0e0`
- `0x1802ae4f0`

## callees

- `0x180013250`
- `0x180015420`
- `0x180033d50`
- `0x18004a658`
- `0x18005ad5c`
- `0x18005eef0`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb500`
- `0x1800eb920`
- `0x18010e940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010eb1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010ec2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010edf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010eecc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010eb1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010ec2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010edf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010eecc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010eb04`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010ec16`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010eb04`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010ec16`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18010eddc`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18010eeb8`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18010eddc`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18010eeb8`

## string_xrefs

- `0x18010e99e`: `No full path result specified`
- `0x18010e9f9`: `No relative path specified`
- `0x18010ef70`: `Failed to allocate buffer for full path.`
- `0x18010ecd1`: `Failed to allocate buffer for expanded path.`
- `0x18010ee1b`: `Failed to get full path for string: {}`
- `0x18010eef7`: `Failed to get full path for string: {}`
- `0x18010ea3a`: `onecore\base\cbs\util\cbspath.cpp`
- `0x18010eba0`: `onecore\base\cbs\util\cbspath.cpp`
- `0x18010ea6a`: `Invalid relative path specified`

## pseudocode

```c
__int64 __fastcall PathExpand(LPWSTR *a1, const WCHAR *a2)
{
  unsigned int v3; // edi
  __int64 v4; // rdx
  unsigned __int64 v5; // r9
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rsi
  int v8; // eax
  int v9; // eax
  LPWSTR v10; // rbx
  DWORD v11; // eax
  unsigned int v12; // ecx
  signed int LastError; // edi
  DWORD v14; // eax
  __int64 v15; // rdx
  unsigned __int64 v16; // r15
  int v17; // eax
  int v18; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  int v21; // eax
  int v22; // ecx
  int v23; // eax
  const WCHAR *v24; // rax
  int v25; // eax
  DWORD v26; // esi
  int v27; // eax
  LPWSTR v28; // rbx
  DWORD FullPathNameW; // eax
  const struct std::nothrow_t *v30; // rdx
  DWORD v31; // eax
  DWORD v32; // esi
  int v33; // eax
  DWORD v34; // eax
  int v35; // eax
  int v37; // eax
  unsigned int v38; // [rsp+20h] [rbp-50h]
  LPWSTR lpBuffer; // [rsp+30h] [rbp-40h] BYREF
  LPWSTR lpDst; // [rsp+38h] [rbp-38h] BYREF
  DWORD *p_nSize; // [rsp+40h] [rbp-30h] BYREF
  LPWSTR FilePart; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-20h] BYREF
  LPCWSTR lpSrc; // [rsp+58h] [rbp-18h] BYREF
  DWORD nSize; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  lpSrc = a2;
  lpDst = 0;
  nSize = 0;
  lpBuffer = 0;
  if ( !a1 )
  {
    v3 = -2147467261;
    nSize = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No full path result specified");
      FilePart = (LPWSTR)&nSize;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&FilePart);
    }
    v4 = 39;
    goto LABEL_9;
  }
  if ( !a2 )
  {
    v3 = -2147024809;
    nSize = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No relative path specified");
      FilePart = (LPWSTR)&nSize;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&FilePart);
    }
    v4 = 40;
    goto LABEL_9;
  }
  if ( !*a2 )
  {
    v3 = -2147024809;
    nSize = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid relative path specified");
      FilePart = (LPWSTR)&nSize;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)&FilePart);
    }
    v4 = 41;
    goto LABEL_9;
  }
  v6 = 64;
  lpFileName = (LPCWSTR)64;
  v7 = 64;
  v8 = SczAlloc(&lpDst, 64);
  v3 = v8;
  if ( v8 < 0 )
  {
    v5 = (unsigned int)v8;
    v4 = 50;
    goto LABEL_10;
  }
  v9 = ULongLongToULong(0x40u, &nSize);
  v3 = v9;
  if ( v9 < 0 )
  {
    v5 = (unsigned int)v9;
    v4 = 51;
    goto LABEL_10;
  }
  v10 = lpDst;
  v11 = ExpandEnvironmentStringsW(lpSrc, lpDst, nSize);
  v12 = v11;
  if ( !v11 )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to expand environment variables in string: {}",
        (__int64)&lpSrc);
      if ( LastError > 0 )
        v14 = (unsigned __int16)LastError | 0x80070000;
      else
        v14 = LastError;
      nSize = v14;
      FilePart = (LPWSTR)&nSize;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)&FilePart);
    }
    if ( LastError )
    {
      v15 = 54;
LABEL_27:
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v15,
             (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
             (const char *)(unsigned int)LastError,
             v38);
      goto LABEL_95;
    }
    goto LABEL_94;
  }
  v16 = v11;
  if ( v11 > 0x40uLL )
  {
    v7 = v11;
    lpFileName = (LPCWSTR)v11;
    v17 = SczAlloc(&lpDst, v11);
    v3 = v17;
    if ( v17 < 0 )
    {
      v5 = (unsigned int)v17;
      v4 = 59;
      goto LABEL_10;
    }
    v18 = ULongLongToULong(v16, &nSize);
    v3 = v18;
    if ( v18 < 0 )
    {
      v5 = (unsigned int)v18;
      v4 = 60;
      goto LABEL_10;
    }
    v10 = lpDst;
    v19 = ExpandEnvironmentStringsW(lpSrc, lpDst, nSize);
    v12 = v19;
    if ( !v19 )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to expand environment variables in string: {}",
          (__int64)&lpSrc);
        if ( LastError > 0 )
          v20 = (unsigned __int16)LastError | 0x80070000;
        else
          v20 = LastError;
        nSize = v20;
        FilePart = (LPWSTR)&nSize;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)&FilePart);
      }
      if ( LastError )
      {
        v15 = 63;
        goto LABEL_27;
      }
      goto LABEL_94;
    }
    if ( v16 < v19 )
    {
      v3 = -2147024774;
      nSize = -2147024774;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate buffer for expanded path.");
        FilePart = (LPWSTR)&nSize;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&FilePart);
      }
      v4 = 67;
      goto LABEL_9;
    }
  }
  if ( v12 <= 0x104 )
  {
LABEL_53:
    v24 = lpSrc;
    FilePart = 0;
    nSize = 0;
    if ( v10 )
      v24 = v10;
    lpFileName = v24;
    if ( v7 > 0x40 )
      v6 = v7;
    v25 = ULongLongToULong(v6, &nSize);
    v3 = v25;
    if ( v25 < 0 )
    {
      v5 = (unsigned int)v25;
      v4 = 95;
      goto LABEL_10;
    }
    v26 = nSize;
    v27 = SczAlloc(&lpBuffer, nSize);
    v3 = v27;
    if ( v27 < 0 )
    {
      v5 = (unsigned int)v27;
      v4 = 96;
      goto LABEL_10;
    }
    v28 = lpBuffer;
    FullPathNameW = GetFullPathNameW(lpFileName, v26, lpBuffer, &FilePart);
    if ( FullPathNameW )
    {
      if ( v26 < FullPathNameW )
      {
        v32 = FullPathNameW;
        if ( FullPathNameW >= 0x104 )
          v32 = FullPathNameW + 7;
        v33 = SczAlloc(&lpBuffer, v32);
        v3 = v33;
        if ( v33 < 0 )
        {
          v5 = (unsigned int)v33;
          v4 = 104;
          goto LABEL_10;
        }
        v28 = lpBuffer;
        FullPathNameW = GetFullPathNameW(lpFileName, v32, lpBuffer, &FilePart);
        if ( !FullPathNameW )
        {
          LastError = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (__int64)"Failed to get full path for string: {}",
              (__int64)&lpFileName);
            if ( LastError > 0 )
              v34 = (unsigned __int16)LastError | 0x80070000;
            else
              v34 = LastError;
            nSize = v34;
            p_nSize = &nSize;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {0}",
              (__int64)&p_nSize);
          }
          if ( LastError )
          {
            v15 = 107;
            goto LABEL_27;
          }
          goto LABEL_94;
        }
        if ( v32 < FullPathNameW )
        {
          v3 = -2147024774;
          nSize = -2147024774;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to allocate buffer for full path.");
            p_nSize = &nSize;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              1,
              3,
              (__int64)": {}",
              (__int64)&p_nSize);
          }
          v4 = 111;
          goto LABEL_9;
        }
      }
      if ( FullPathNameW > 0x104 )
      {
        v35 = PathPrefix(&lpBuffer);
        v3 = v35;
        if ( v35 < 0 )
        {
          v5 = (unsigned int)v35;
          v4 = 117;
          goto LABEL_10;
        }
        v28 = lpBuffer;
      }
      if ( v28 )
      {
        if ( *a1 )
          operator delete(*a1 - 4, v30);
        lpBuffer = 0;
        *a1 = v28;
      }
      else
      {
        v37 = SczAllocFromSz(a1, lpSrc);
        v3 = v37;
        if ( v37 < 0 )
        {
          v5 = (unsigned int)v37;
          v4 = 132;
          goto LABEL_10;
        }
      }
      goto LABEL_94;
    }
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (__int64)"Failed to get full path for string: {}",
        (__int64)&lpFileName);
      if ( LastError > 0 )
        v31 = (unsigned __int16)LastError | 0x80070000;
      else
        v31 = LastError;
      nSize = v31;
      p_nSize = &nSize;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)&p_nSize);
    }
    if ( LastError )
    {
      v15 = 99;
      goto LABEL_27;
    }
LABEL_94:
    v3 = 0;
    goto LABEL_95;
  }
  v21 = PathPrefix(&lpDst);
  v22 = 0;
  if ( v21 != -2147024809 )
    v22 = v21;
  v3 = v22;
  if ( v22 >= 0 )
  {
    v10 = lpDst;
    v23 = SczSize(lpDst, &lpFileName);
    v3 = v23;
    if ( v23 < 0 )
    {
      v5 = (unsigned int)v23;
      v4 = 81;
      goto LABEL_10;
    }
    v7 = (unsigned __int64)lpFileName;
    goto LABEL_53;
  }
  v4 = 79;
LABEL_9:
  v5 = v3;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
    (const char *)v5,
    v38);
LABEL_95:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
  return v3;
}

```

## disassembly

```asm
0x18010e940  mov     [rsp-38h+arg_10], rbx
0x18010e945  push    rbp
0x18010e946  push    rsi
0x18010e947  push    rdi
0x18010e948  push    r12
0x18010e94a  push    r13
0x18010e94c  push    r14
0x18010e94e  push    r15
0x18010e950  mov     rbp, rsp
0x18010e953  sub     rsp, 70h
0x18010e957  mov     rax, cs:__security_cookie
0x18010e95e  xor     rax, rsp
0x18010e961  mov     [rbp+var_8], rax
0x18010e965  xor     r13d, r13d
0x18010e968  mov     [rbp+lpSrc], rdx
0x18010e96c  mov     [rbp+lpDst], r13
0x18010e970  mov     r12, rcx
0x18010e973  mov     [rbp+nSize], r13d
0x18010e977  mov     [rbp+lpBuffer], r13
0x18010e97b  test    rcx, rcx
0x18010e97e  jnz     short loc_18010E9DA
0x18010e980  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010e987  mov     edi, 80004003h
0x18010e98c  mov     [rbp+nSize], edi
0x18010e98f  test    rcx, rcx
0x18010e992  jz      short loc_18010E9D3
0x18010e994  lea     ebx, [r12+3]
0x18010e999  xor     edx, edx
0x18010e99b  mov     r8d, ebx
0x18010e99e  lea     r9, aNoFullPathResu; "No full path result specified"
0x18010e9a5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18010e9aa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010e9b1  lea     rax, [rbp+nSize]
0x18010e9b5  mov     [rbp+FilePart], rax
0x18010e9b9  lea     r9, asc_1802EE7AC; ": {}"
0x18010e9c0  lea     rax, [rbp+FilePart]
0x18010e9c4  mov     r8d, ebx
0x18010e9c7  mov     dl, 1
0x18010e9c9  mov     qword ptr [rsp+70h+var_50], rax
0x18010e9ce  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010e9d3  mov     edx, 27h ; '''
0x18010e9d8  jmp     short loc_18010EA33
0x18010e9da  test    rdx, rdx
0x18010e9dd  jnz     short loc_18010EA4B
0x18010e9df  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010e9e6  mov     edi, 80070057h
0x18010e9eb  mov     [rbp+nSize], edi
0x18010e9ee  test    rcx, rcx
0x18010e9f1  jz      short loc_18010EA2E
0x18010e9f3  lea     ebx, [rdx+3]
0x18010e9f6  mov     r8d, ebx
0x18010e9f9  lea     r9, aNoRelativePath; "No relative path specified"
0x18010ea00  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18010ea05  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ea0c  lea     rax, [rbp+nSize]
0x18010ea10  mov     [rbp+FilePart], rax
0x18010ea14  lea     r9, asc_1802EE7AC; ": {}"
0x18010ea1b  lea     rax, [rbp+FilePart]
0x18010ea1f  mov     r8d, ebx
0x18010ea22  mov     dl, 1
0x18010ea24  mov     qword ptr [rsp+70h+var_50], rax; int
0x18010ea29  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010ea2e  mov     edx, 28h ; '('; void *
0x18010ea33  mov     r9d, edi; char *
0x18010ea36  mov     rcx, [rbp+38h]; this
0x18010ea3a  lea     r8, aOnecoreBaseCbs_120; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x18010ea41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ea46  jmp     loc_18010EFFB
0x18010ea4b  cmp     [rdx], r13w
0x18010ea4f  jnz     short loc_18010EAAB
0x18010ea51  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ea58  mov     edi, 80070057h
0x18010ea5d  mov     [rbp+nSize], edi
0x18010ea60  test    rcx, rcx
0x18010ea63  jz      short loc_18010EAA4
0x18010ea65  mov     ebx, 3
0x18010ea6a  lea     r9, aInvalidRelativ; "Invalid relative path specified"
0x18010ea71  mov     r8d, ebx
0x18010ea74  xor     edx, edx
0x18010ea76  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18010ea7b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ea82  lea     rax, [rbp+nSize]
0x18010ea86  mov     [rbp+FilePart], rax
0x18010ea8a  lea     r9, asc_1802EE7AC; ": {}"
0x18010ea91  lea     rax, [rbp+FilePart]
0x18010ea95  mov     r8d, ebx
0x18010ea98  mov     dl, 1
0x18010ea9a  mov     qword ptr [rsp+70h+var_50], rax
0x18010ea9f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010eaa4  mov     edx, 29h ; ')'
0x18010eaa9  jmp     short loc_18010EA33
0x18010eaab  mov     r14d, 40h ; '@'
0x18010eab1  lea     rcx, [rbp+lpDst]
0x18010eab5  mov     edx, r14d
0x18010eab8  mov     [rbp+lpFileName], r14
0x18010eabc  mov     esi, r14d
0x18010eabf  call    SczAlloc
0x18010eac4  mov     edi, eax
0x18010eac6  test    eax, eax
0x18010eac8  jns     short loc_18010EAD6
0x18010eaca  mov     r9d, eax
0x18010eacd  lea     edx, [r14-0Eh]
0x18010ead1  jmp     loc_18010EA36
0x18010ead6  lea     rdx, [rbp+nSize]; unsigned int *
0x18010eada  mov     rcx, r14; unsigned __int64
0x18010eadd  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18010eae2  mov     edi, eax
0x18010eae4  test    eax, eax
0x18010eae6  jns     short loc_18010EAF5
0x18010eae8  mov     r9d, eax
0x18010eaeb  mov     edx, 33h ; '3'
0x18010eaf0  jmp     loc_18010EA36
0x18010eaf5  mov     rbx, [rbp+lpDst]
0x18010eaf9  mov     r8d, [rbp+nSize]; nSize
0x18010eafd  mov     rdx, rbx; lpDst
0x18010eb00  mov     rcx, [rbp+lpSrc]; lpSrc
0x18010eb04  call    cs:__imp_ExpandEnvironmentStringsW
0x18010eb0b  nop     dword ptr [rax+rax+00h]
0x18010eb10  mov     ecx, eax
0x18010eb12  test    eax, eax
0x18010eb14  jnz     loc_18010EBB6
0x18010eb1a  call    cs:__imp_GetLastError
0x18010eb21  nop     dword ptr [rax+rax+00h]
0x18010eb26  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010eb2d  mov     edi, eax
0x18010eb2f  test    rcx, rcx
0x18010eb32  jz      short loc_18010EB8F
0x18010eb34  lea     rax, [rbp+lpSrc]
0x18010eb38  mov     ebx, 3
0x18010eb3d  mov     r8d, ebx
0x18010eb40  mov     qword ptr [rsp+70h+var_50], rax
0x18010eb45  lea     r9, aFailedToExpand_0; "Failed to expand environment variables "...
0x18010eb4c  xor     edx, edx
0x18010eb4e  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18010eb53  test    edi, edi
0x18010eb55  jg      short loc_18010EB5B
0x18010eb57  mov     eax, edi
0x18010eb59  jmp     short loc_18010EB63
0x18010eb5b  movzx   eax, di
0x18010eb5e  or      eax, 80070000h
0x18010eb63  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010eb6a  lea     r9, a0; ": {0}"
0x18010eb71  mov     [rbp+nSize], eax
0x18010eb74  mov     r8d, ebx
0x18010eb77  lea     rax, [rbp+nSize]
0x18010eb7b  mov     dl, 1
0x18010eb7d  mov     [rbp+FilePart], rax
0x18010eb81  lea     rax, [rbp+FilePart]
0x18010eb85  mov     qword ptr [rsp+70h+var_50], rax; unsigned int
0x18010eb8a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010eb8f  test    edi, edi
0x18010eb91  jz      loc_18010EFF8
0x18010eb97  mov     edx, 36h ; '6'; void *
0x18010eb9c  mov     rcx, [rbp+38h]; this
0x18010eba0  lea     r8, aOnecoreBaseCbs_120; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x18010eba7  mov     r9d, edi; char *
0x18010ebaa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010ebaf  mov     edi, eax
0x18010ebb1  jmp     loc_18010EFFB
0x18010ebb6  mov     r15, rcx
0x18010ebb9  cmp     rcx, r14
0x18010ebbc  jbe     loc_18010ED15
0x18010ebc2  mov     rsi, rcx
0x18010ebc5  mov     [rbp+lpFileName], rcx
0x18010ebc9  mov     rdx, rcx
0x18010ebcc  lea     rcx, [rbp+lpDst]
0x18010ebd0  call    SczAlloc
0x18010ebd5  mov     edi, eax
0x18010ebd7  test    eax, eax
0x18010ebd9  jns     short loc_18010EBE8
0x18010ebdb  mov     r9d, eax
0x18010ebde  mov     edx, 3Bh ; ';'
0x18010ebe3  jmp     loc_18010EA36
0x18010ebe8  lea     rdx, [rbp+nSize]; unsigned int *
0x18010ebec  mov     rcx, r15; unsigned __int64
0x18010ebef  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18010ebf4  mov     edi, eax
0x18010ebf6  test    eax, eax
0x18010ebf8  jns     short loc_18010EC07
0x18010ebfa  mov     r9d, eax
0x18010ebfd  mov     edx, 3Ch ; '<'
0x18010ec02  jmp     loc_18010EA36
0x18010ec07  mov     rbx, [rbp+lpDst]
0x18010ec0b  mov     r8d, [rbp+nSize]; nSize
0x18010ec0f  mov     rdx, rbx; lpDst
0x18010ec12  mov     rcx, [rbp+lpSrc]; lpSrc
0x18010ec16  call    cs:__imp_ExpandEnvironmentStringsW
0x18010ec1d  nop     dword ptr [rax+rax+00h]
0x18010ec22  mov     ecx, eax
0x18010ec24  test    eax, eax
0x18010ec26  jnz     loc_18010ECB3
0x18010ec2c  call    cs:__imp_GetLastError
0x18010ec33  nop     dword ptr [rax+rax+00h]
0x18010ec38  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ec3f  mov     edi, eax
0x18010ec41  test    rcx, rcx
0x18010ec44  jz      short loc_18010ECA1
0x18010ec46  lea     rax, [rbp+lpSrc]
0x18010ec4a  mov     ebx, 3
0x18010ec4f  mov     r8d, ebx
0x18010ec52  mov     qword ptr [rsp+70h+var_50], rax
0x18010ec57  lea     r9, aFailedToExpand_0; "Failed to expand environment variables "...
0x18010ec5e  xor     edx, edx
0x18010ec60  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18010ec65  test    edi, edi
0x18010ec67  jg      short loc_18010EC6D
0x18010ec69  mov     eax, edi
0x18010ec6b  jmp     short loc_18010EC75
0x18010ec6d  movzx   eax, di
0x18010ec70  or      eax, 80070000h
0x18010ec75  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ec7c  lea     r9, a0; ": {0}"
0x18010ec83  mov     [rbp+nSize], eax
0x18010ec86  mov     r8d, ebx
0x18010ec89  lea     rax, [rbp+nSize]
0x18010ec8d  mov     dl, 1
0x18010ec8f  mov     [rbp+FilePart], rax
0x18010ec93  lea     rax, [rbp+FilePart]
0x18010ec97  mov     qword ptr [rsp+70h+var_50], rax
0x18010ec9c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010eca1  test    edi, edi
0x18010eca3  jz      loc_18010EFF8
0x18010eca9  mov     edx, 3Fh ; '?'
0x18010ecae  jmp     loc_18010EB9C
0x18010ecb3  cmp     r15, rcx
0x18010ecb6  jnb     short loc_18010ED15
0x18010ecb8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ecbf  mov     edi, 8007007Ah
0x18010ecc4  mov     [rbp+nSize], edi
0x18010ecc7  test    rcx, rcx
0x18010ecca  jz      short loc_18010ED0B
0x18010eccc  mov     ebx, 3
0x18010ecd1  lea     r9, aFailedToAlloca_50; "Failed to allocate buffer for expanded "...
0x18010ecd8  mov     r8d, ebx
0x18010ecdb  xor     edx, edx
0x18010ecdd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18010ece2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18010ece9  lea     rax, [rbp+nSize]
0x18010eced  mov     [rbp+FilePart], rax
0x18010ecf1  lea     r9, asc_1802EE7AC; ": {}"
0x18010ecf8  lea     rax, [rbp+FilePart]
0x18010ecfc  mov     r8d, ebx
0x18010ecff  mov     dl, 1
0x18010ed01  mov     qword ptr [rsp+70h+var_50], rax
0x18010ed06  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18010ed0b  mov     edx, 43h ; 'C'
0x18010ed10  jmp     loc_18010EA33
0x18010ed15  mov     r15d, 104h
0x18010ed1b  cmp     ecx, r15d
0x18010ed1e  jbe     short loc_18010ED6D
0x18010ed20  lea     rcx, [rbp+lpDst]
0x18010ed24  call    PathPrefix
0x18010ed29  mov     edi, 80070057h
0x18010ed2e  mov     ecx, r13d
0x18010ed31  cmp     eax, edi
0x18010ed33  cmovnz  ecx, eax
0x18010ed36  mov     edi, ecx
0x18010ed38  test    ecx, ecx
0x18010ed3a  jns     short loc_18010ED46
0x18010ed3c  mov     edx, 4Fh ; 'O'
0x18010ed41  jmp     loc_18010EA33
0x18010ed46  mov     rbx, [rbp+lpDst]
0x18010ed4a  lea     rdx, [rbp+lpFileName]
0x18010ed4e  mov     rcx, rbx
0x18010ed51  call    SczSize
0x18010ed56  mov     edi, eax
0x18010ed58  test    eax, eax
0x18010ed5a  jns     short loc_18010ED69
0x18010ed5c  mov     r9d, eax
0x18010ed5f  mov     edx, 51h ; 'Q'
0x18010ed64  jmp     loc_18010EA36
0x18010ed69  mov     rsi, [rbp+lpFileName]
0x18010ed6d  mov     rax, [rbp+lpSrc]
0x18010ed71  lea     rdx, [rbp+nSize]; unsigned int *
0x18010ed75  test    rbx, rbx
0x18010ed78  mov     [rbp+FilePart], r13
0x18010ed7c  mov     [rbp+nSize], r13d
0x18010ed80  cmovnz  rax, rbx
0x18010ed84  cmp     rsi, r14
0x18010ed87  mov     [rbp+lpFileName], rax
0x18010ed8b  cmova   r14, rsi
0x18010ed8f  mov     rcx, r14; unsigned __int64
0x18010ed92  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18010ed97  mov     edi, eax
0x18010ed99  test    eax, eax
0x18010ed9b  jns     short loc_18010EDAA
0x18010ed9d  mov     r9d, eax
0x18010eda0  mov     edx, 5Fh ; '_'
0x18010eda5  jmp     loc_18010EA36
0x18010edaa  mov     esi, [rbp+nSize]
0x18010edad  lea     rcx, [rbp+lpBuffer]
0x18010edb1  mov     edx, esi
0x18010edb3  call    SczAlloc
0x18010edb8  mov     edi, eax
0x18010edba  test    eax, eax
0x18010edbc  jns     short loc_18010EDCB
0x18010edbe  mov     r9d, eax
0x18010edc1  mov     edx, 60h ; '`'
0x18010edc6  jmp     loc_18010EA36
0x18010edcb  mov     rbx, [rbp+lpBuffer]
  ... truncated ...
```
