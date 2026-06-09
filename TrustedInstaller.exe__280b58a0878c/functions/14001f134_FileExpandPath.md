# FileExpandPath

- ea: `0x14001f134`
- end: `0x14001f65d`
- name: `FileExpandPath`
- size: `1321`
- prototype: `__int64 __fastcall(const WCHAR *, LPWSTR *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x14000c3e0`

## callees

- `0x1400023e0`
- `0x140002674`
- `0x1400054b0`
- `0x14000ee94`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x1400184fc`
- `0x14001c7a8`
- `0x14001f134`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f47a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f53c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f366`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f47a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001f53c`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14001f46d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14001f532`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14001f46d`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14001f532`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14001f288`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14001f35c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14001f288`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x14001f35c`

## string_xrefs

- `0x14001f18f`: `No relative path specified`
- `0x14001f1e9`: `No full path result specified`
- `0x14001f3f9`: `Failed to allocate buffer for expanded path.`
- `0x14001f496`: `Failed to get full path for string: {}`
- `0x14001f558`: `Failed to get full path for string: {}`
- `0x14001f5ca`: `Failed to allocate buffer for full path.`

## pseudocode

```c
__int64 __fastcall FileExpandPath(const WCHAR *a1, LPWSTR *a2)
{
  unsigned int v3; // edi
  int v4; // edx
  __int64 v5; // rdx
  int v6; // edx
  unsigned __int64 v7; // r9
  int v8; // eax
  const WCHAR *v9; // rbx
  DWORD v10; // eax
  DWORD v11; // r14d
  int v12; // edx
  signed int LastError; // ebx
  int v14; // r8d
  int v15; // edx
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  int v19; // eax
  DWORD v20; // eax
  int v21; // edx
  int v22; // r8d
  int v23; // edx
  unsigned int v24; // eax
  int v25; // edx
  int v26; // eax
  LPWSTR v27; // rdi
  DWORD FullPathNameW; // eax
  DWORD v29; // r14d
  int v30; // edx
  signed int v31; // edi
  int v32; // r8d
  int v33; // edx
  unsigned int v34; // eax
  int v35; // eax
  DWORD v36; // eax
  int v37; // edx
  signed int v38; // edi
  int v39; // r8d
  int v40; // edx
  unsigned int v41; // eax
  int v42; // edx
  unsigned int v44; // [rsp+20h] [rbp-50h]
  unsigned int v45[2]; // [rsp+30h] [rbp-40h] BYREF
  LPWSTR lpBuffer; // [rsp+38h] [rbp-38h] BYREF
  LPWSTR lpDst; // [rsp+40h] [rbp-30h] BYREF
  int *v48; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR lpSrc; // [rsp+50h] [rbp-20h] BYREF
  LPWSTR FilePart; // [rsp+58h] [rbp-18h] BYREF
  int v51; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  lpSrc = a1;
  lpDst = 0;
  lpBuffer = 0;
  FilePart = 0;
  if ( a1 )
  {
    if ( !a2 )
    {
      v3 = -2147467261;
      v51 = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No full path result specified");
        *(_QWORD *)v45 = &v51;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v6,
          3,
          (unsigned int)": {}",
          (__int64)v45);
      }
      v5 = 252;
      goto LABEL_9;
    }
    if ( *a2 )
    {
      operator delete(*a2 - 4, (unsigned __int64)a2);
      *a2 = 0;
    }
    v8 = SczAlloc(&lpDst, 260);
    v3 = v8;
    if ( v8 < 0 )
    {
      v7 = (unsigned int)v8;
      v5 = 259;
      goto LABEL_10;
    }
    v9 = lpDst;
    v10 = ExpandEnvironmentStringsW(lpSrc, lpDst, 0x104u);
    v11 = v10;
    if ( !v10 )
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          v12,
          v14,
          (unsigned int)"Failed to expand environment variables in string: {}",
          (__int64)&lpSrc);
        if ( LastError > 0 )
          v16 = (unsigned __int16)LastError | 0x80070000;
        else
          v16 = LastError;
        v51 = v16;
        *(_QWORD *)v45 = &v51;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v15,
          3,
          (unsigned int)": {0}",
          (__int64)v45);
      }
      if ( LastError )
      {
        v17 = 264;
LABEL_23:
        v18 = (unsigned int)LastError;
LABEL_24:
        v3 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v17,
               (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
               (const char *)v18,
               v44);
        goto LABEL_67;
      }
      goto LABEL_66;
    }
    if ( v10 > 0x104 )
    {
      v19 = SczAlloc(&lpDst, v10);
      v3 = v19;
      if ( v19 < 0 )
      {
        v7 = (unsigned int)v19;
        v5 = 269;
        goto LABEL_10;
      }
      v9 = lpDst;
      v20 = ExpandEnvironmentStringsW(lpSrc, lpDst, v11);
      if ( !v20 )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v21,
            v22,
            (unsigned int)"Failed to expand environment variables in string: {}",
            (__int64)&lpSrc);
          if ( LastError > 0 )
            v24 = (unsigned __int16)LastError | 0x80070000;
          else
            v24 = LastError;
          v51 = v24;
          *(_QWORD *)v45 = &v51;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v23,
            3,
            (unsigned int)": {0}",
            (__int64)v45);
        }
        if ( LastError )
        {
          v17 = 274;
          goto LABEL_23;
        }
        goto LABEL_66;
      }
      if ( v11 < v20 )
      {
        v3 = -2147024774;
        v51 = -2147024774;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to allocate buffer for expanded path.");
          *(_QWORD *)v45 = &v51;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v25,
            3,
            (unsigned int)": {}",
            (__int64)v45);
        }
        v5 = 278;
        goto LABEL_9;
      }
    }
    v26 = SczAlloc(&lpBuffer, 260);
    v3 = v26;
    if ( v26 < 0 )
    {
      v7 = (unsigned int)v26;
      v5 = 286;
      goto LABEL_10;
    }
    v27 = lpBuffer;
    FullPathNameW = GetFullPathNameW(v9, 0x104u, lpBuffer, &FilePart);
    v29 = FullPathNameW;
    if ( FullPathNameW )
    {
      if ( FullPathNameW > 0x104 )
      {
        v35 = SczAlloc(&lpBuffer, FullPathNameW);
        v3 = v35;
        if ( v35 < 0 )
        {
          v7 = (unsigned int)v35;
          v5 = 296;
          goto LABEL_10;
        }
        v27 = lpBuffer;
        v36 = GetFullPathNameW(v9, v29, lpBuffer, &FilePart);
        if ( !v36 )
        {
          v38 = GetLastError();
          if ( LogAdapter::g_Logger )
          {
            v48 = (int *)v9;
            LogAdapter::Logger::LogNumObjects<wchar_t const *>(
              (_DWORD)LogAdapter::g_Logger,
              v37,
              v39,
              (unsigned int)"Failed to get full path for string: {}",
              (__int64)&v48);
            if ( v38 > 0 )
              v41 = (unsigned __int16)v38 | 0x80070000;
            else
              v41 = v38;
            v51 = v41;
            *(_QWORD *)v45 = &v51;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v40,
              3,
              (unsigned int)": {0}",
              (__int64)v45);
          }
          if ( v38 )
          {
            v18 = (unsigned int)v38;
            v17 = 301;
            goto LABEL_24;
          }
          goto LABEL_66;
        }
        if ( v29 < v36 )
        {
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate buffer for full path.");
            v48 = &v51;
            v51 = -2147024774;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v42,
              3,
              (unsigned int)": {0}",
              (__int64)&v48);
          }
          v18 = 122;
          v17 = 305;
          goto LABEL_24;
        }
      }
      lpBuffer = 0;
      *a2 = v27;
      goto LABEL_66;
    }
    v31 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      *(_QWORD *)v45 = v9;
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (_DWORD)LogAdapter::g_Logger,
        v30,
        v32,
        (unsigned int)"Failed to get full path for string: {}",
        (__int64)v45);
      if ( v31 > 0 )
        v34 = (unsigned __int16)v31 | 0x80070000;
      else
        v34 = v31;
      v51 = v34;
      v48 = &v51;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v33,
        3,
        (unsigned int)": {0}",
        (__int64)&v48);
    }
    if ( v31 )
    {
      v18 = (unsigned int)v31;
      v17 = 291;
      goto LABEL_24;
    }
LABEL_66:
    v3 = 0;
    goto LABEL_67;
  }
  v3 = -2147024809;
  v51 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No relative path specified");
    *(_QWORD *)v45 = &v51;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v4,
      3,
      (unsigned int)": {}",
      (__int64)v45);
  }
  v5 = 251;
LABEL_9:
  v7 = v3;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
    (const char *)v7,
    v44);
LABEL_67:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpBuffer);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpDst);
  return v3;
}

```

## disassembly

```asm
0x14001f134  mov     [rsp-28h+arg_10], rbx
0x14001f139  push    rbp
0x14001f13a  push    rsi
0x14001f13b  push    rdi
0x14001f13c  push    r12
0x14001f13e  push    r14
0x14001f140  mov     rbp, rsp
0x14001f143  sub     rsp, 70h
0x14001f147  mov     rax, cs:__security_cookie
0x14001f14e  xor     rax, rsp
0x14001f151  mov     [rbp+var_8], rax
0x14001f155  mov     [rbp+lpSrc], rcx
0x14001f159  mov     rsi, rdx
0x14001f15c  mov     [rbp+lpDst], 0
0x14001f164  mov     [rbp+lpBuffer], 0
0x14001f16c  mov     [rbp+FilePart], 0
0x14001f174  test    rcx, rcx
0x14001f177  jnz     short loc_14001F1D0
0x14001f179  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f180  mov     edi, 80070057h
0x14001f185  mov     [rbp+var_10], edi
0x14001f188  test    rcx, rcx
0x14001f18b  jz      short loc_14001F1C9
0x14001f18d  xor     edx, edx
0x14001f18f  lea     r9, aNoRelativePath; "No relative path specified"
0x14001f196  lea     r8d, [rdx+3]
0x14001f19a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001f19f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f1a6  lea     rax, [rbp+var_10]
0x14001f1aa  mov     qword ptr [rbp+var_40], rax
0x14001f1ae  lea     r9, asc_1400353E8; ": {}"
0x14001f1b5  lea     rax, [rbp+var_40]
0x14001f1b9  mov     r8d, 3
0x14001f1bf  mov     qword ptr [rsp+70h+var_50], rax
0x14001f1c4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001f1c9  mov     edx, 0FBh
0x14001f1ce  jmp     short loc_14001F228
0x14001f1d0  test    rsi, rsi
0x14001f1d3  jnz     short loc_14001F240
0x14001f1d5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f1dc  mov     edi, 80004003h
0x14001f1e1  mov     [rbp+var_10], edi
0x14001f1e4  test    rcx, rcx
0x14001f1e7  jz      short loc_14001F223
0x14001f1e9  lea     r9, aNoFullPathResu; "No full path result specified"
0x14001f1f0  xor     edx, edx
0x14001f1f2  lea     r8d, [rsi+3]
0x14001f1f6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001f1fb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f202  lea     rax, [rbp+var_10]
0x14001f206  mov     qword ptr [rbp+var_40], rax
0x14001f20a  lea     r9, asc_1400353E8; ": {}"
0x14001f211  lea     rax, [rbp+var_40]
0x14001f215  lea     r8d, [rsi+3]
0x14001f219  mov     qword ptr [rsp+70h+var_50], rax; int
0x14001f21e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001f223  mov     edx, 0FCh; void *
0x14001f228  mov     r9d, edi; char *
0x14001f22b  mov     rcx, [rbp+28h]; this
0x14001f22f  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001f236  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f23b  jmp     loc_14001F629
0x14001f240  mov     rcx, [rdx]
0x14001f243  test    rcx, rcx
0x14001f246  jz      short loc_14001F258
0x14001f248  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x14001f24c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001f251  mov     qword ptr [rsi], 0
0x14001f258  mov     r12d, 104h
0x14001f25e  lea     rcx, [rbp+lpDst]
0x14001f262  mov     edx, r12d
0x14001f265  call    SczAlloc
0x14001f26a  mov     edi, eax
0x14001f26c  test    eax, eax
0x14001f26e  jns     short loc_14001F27A
0x14001f270  mov     r9d, eax
0x14001f273  lea     edx, [r12-1]
0x14001f278  jmp     short loc_14001F22B
0x14001f27a  mov     rbx, [rbp+lpDst]
0x14001f27e  mov     r8d, r12d; nSize
0x14001f281  mov     rcx, [rbp+lpSrc]; lpSrc
0x14001f285  mov     rdx, rbx; lpDst
0x14001f288  call    cs:__imp_ExpandEnvironmentStringsW
0x14001f28e  mov     r14d, eax
0x14001f291  test    eax, eax
0x14001f293  jnz     loc_14001F326
0x14001f299  call    cs:__imp_GetLastError
0x14001f29f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f2a6  mov     ebx, eax
0x14001f2a8  test    rcx, rcx
0x14001f2ab  jz      short loc_14001F2FF
0x14001f2ad  lea     rax, [rbp+lpSrc]
0x14001f2b1  lea     r9, aFailedToExpand_0; "Failed to expand environment variables "...
0x14001f2b8  mov     qword ptr [rsp+70h+var_50], rax
0x14001f2bd  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001f2c2  test    ebx, ebx
0x14001f2c4  jg      short loc_14001F2CA
0x14001f2c6  mov     eax, ebx
0x14001f2c8  jmp     short loc_14001F2D2
0x14001f2ca  movzx   eax, bx
0x14001f2cd  or      eax, 80070000h
0x14001f2d2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f2d9  lea     r9, a0; ": {0}"
0x14001f2e0  mov     [rbp+var_10], eax
0x14001f2e3  mov     r8d, 3
0x14001f2e9  lea     rax, [rbp+var_10]
0x14001f2ed  mov     qword ptr [rbp+var_40], rax
0x14001f2f1  lea     rax, [rbp+var_40]
0x14001f2f5  mov     qword ptr [rsp+70h+var_50], rax; unsigned int
0x14001f2fa  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001f2ff  test    ebx, ebx
0x14001f301  jz      loc_14001F627
0x14001f307  mov     edx, 108h; void *
0x14001f30c  mov     r9d, ebx; char *
0x14001f30f  mov     rcx, [rbp+28h]; this
0x14001f313  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001f31a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001f31f  mov     edi, eax
0x14001f321  jmp     loc_14001F629
0x14001f326  cmp     r14d, r12d
0x14001f329  jbe     loc_14001F43D
0x14001f32f  mov     rdx, r14
0x14001f332  lea     rcx, [rbp+lpDst]
0x14001f336  call    SczAlloc
0x14001f33b  mov     edi, eax
0x14001f33d  test    eax, eax
0x14001f33f  jns     short loc_14001F34E
0x14001f341  mov     r9d, eax
0x14001f344  mov     edx, 10Dh
0x14001f349  jmp     loc_14001F22B
0x14001f34e  mov     rbx, [rbp+lpDst]
0x14001f352  mov     r8d, r14d; nSize
0x14001f355  mov     rcx, [rbp+lpSrc]; lpSrc
0x14001f359  mov     rdx, rbx; lpDst
0x14001f35c  call    cs:__imp_ExpandEnvironmentStringsW
0x14001f362  test    eax, eax
0x14001f364  jnz     short loc_14001F3DE
0x14001f366  call    cs:__imp_GetLastError
0x14001f36c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f373  mov     ebx, eax
0x14001f375  test    rcx, rcx
0x14001f378  jz      short loc_14001F3CC
0x14001f37a  lea     rax, [rbp+lpSrc]
0x14001f37e  lea     r9, aFailedToExpand_0; "Failed to expand environment variables "...
0x14001f385  mov     qword ptr [rsp+70h+var_50], rax
0x14001f38a  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001f38f  test    ebx, ebx
0x14001f391  jg      short loc_14001F397
0x14001f393  mov     eax, ebx
0x14001f395  jmp     short loc_14001F39F
0x14001f397  movzx   eax, bx
0x14001f39a  or      eax, 80070000h
0x14001f39f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f3a6  lea     r9, a0; ": {0}"
0x14001f3ad  mov     [rbp+var_10], eax
0x14001f3b0  mov     r8d, 3
0x14001f3b6  lea     rax, [rbp+var_10]
0x14001f3ba  mov     qword ptr [rbp+var_40], rax
0x14001f3be  lea     rax, [rbp+var_40]
0x14001f3c2  mov     qword ptr [rsp+70h+var_50], rax
0x14001f3c7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001f3cc  test    ebx, ebx
0x14001f3ce  jz      loc_14001F627
0x14001f3d4  mov     edx, 112h
0x14001f3d9  jmp     loc_14001F30C
0x14001f3de  cmp     r14d, eax
0x14001f3e1  jnb     short loc_14001F43D
0x14001f3e3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f3ea  mov     edi, 8007007Ah
0x14001f3ef  mov     [rbp+var_10], edi
0x14001f3f2  test    rcx, rcx
0x14001f3f5  jz      short loc_14001F433
0x14001f3f7  xor     edx, edx
0x14001f3f9  lea     r9, aFailedToAlloca_17; "Failed to allocate buffer for expanded "...
0x14001f400  lea     r8d, [rdx+3]
0x14001f404  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001f409  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f410  lea     rax, [rbp+var_10]
0x14001f414  mov     qword ptr [rbp+var_40], rax
0x14001f418  lea     r9, asc_1400353E8; ": {}"
0x14001f41f  lea     rax, [rbp+var_40]
0x14001f423  mov     r8d, 3
0x14001f429  mov     qword ptr [rsp+70h+var_50], rax
0x14001f42e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001f433  mov     edx, 116h
0x14001f438  jmp     loc_14001F228
0x14001f43d  mov     rdx, r12
0x14001f440  lea     rcx, [rbp+lpBuffer]
0x14001f444  call    SczAlloc
0x14001f449  mov     edi, eax
0x14001f44b  test    eax, eax
0x14001f44d  jns     short loc_14001F45C
0x14001f44f  mov     r9d, eax
0x14001f452  mov     edx, 11Eh
0x14001f457  jmp     loc_14001F22B
0x14001f45c  mov     rdi, [rbp+lpBuffer]
0x14001f460  lea     r9, [rbp+FilePart]; lpFilePart
0x14001f464  mov     r8, rdi; lpBuffer
0x14001f467  mov     edx, r12d; nBufferLength
0x14001f46a  mov     rcx, rbx; lpFileName
0x14001f46d  call    cs:__imp_GetFullPathNameW
0x14001f473  mov     r14d, eax
0x14001f476  test    eax, eax
0x14001f478  jnz     short loc_14001F4F9
0x14001f47a  call    cs:__imp_GetLastError
0x14001f480  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f487  mov     edi, eax
0x14001f489  test    rcx, rcx
0x14001f48c  jz      short loc_14001F4E4
0x14001f48e  lea     rax, [rbp+var_40]
0x14001f492  mov     qword ptr [rbp+var_40], rbx
0x14001f496  lea     r9, aFailedToGetFul; "Failed to get full path for string: {}"
0x14001f49d  mov     qword ptr [rsp+70h+var_50], rax
0x14001f4a2  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001f4a7  test    edi, edi
0x14001f4a9  jg      short loc_14001F4AF
0x14001f4ab  mov     eax, edi
0x14001f4ad  jmp     short loc_14001F4B7
0x14001f4af  movzx   eax, di
0x14001f4b2  or      eax, 80070000h
0x14001f4b7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f4be  lea     r9, a0; ": {0}"
0x14001f4c5  mov     [rbp+var_10], eax
0x14001f4c8  mov     r8d, 3
0x14001f4ce  lea     rax, [rbp+var_10]
0x14001f4d2  mov     [rbp+var_28], rax
0x14001f4d6  lea     rax, [rbp+var_28]
0x14001f4da  mov     qword ptr [rsp+70h+var_50], rax
0x14001f4df  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001f4e4  test    edi, edi
0x14001f4e6  jz      loc_14001F627
0x14001f4ec  mov     r9d, edi
0x14001f4ef  mov     edx, 123h
0x14001f4f4  jmp     loc_14001F30F
0x14001f4f9  cmp     r14d, r12d
0x14001f4fc  jbe     loc_14001F61C
0x14001f502  mov     rdx, r14
0x14001f505  lea     rcx, [rbp+lpBuffer]
0x14001f509  call    SczAlloc
0x14001f50e  mov     edi, eax
0x14001f510  test    eax, eax
0x14001f512  jns     short loc_14001F521
0x14001f514  mov     r9d, eax
0x14001f517  mov     edx, 128h
0x14001f51c  jmp     loc_14001F22B
0x14001f521  mov     rdi, [rbp+lpBuffer]
0x14001f525  lea     r9, [rbp+FilePart]; lpFilePart
0x14001f529  mov     r8, rdi; lpBuffer
0x14001f52c  mov     edx, r14d; nBufferLength
0x14001f52f  mov     rcx, rbx; lpFileName
0x14001f532  call    cs:__imp_GetFullPathNameW
0x14001f538  test    eax, eax
0x14001f53a  jnz     short loc_14001F5B7
0x14001f53c  call    cs:__imp_GetLastError
0x14001f542  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f549  mov     edi, eax
0x14001f54b  test    rcx, rcx
0x14001f54e  jz      short loc_14001F5A6
0x14001f550  lea     rax, [rbp+var_28]
0x14001f554  mov     [rbp+var_28], rbx
0x14001f558  lea     r9, aFailedToGetFul; "Failed to get full path for string: {}"
0x14001f55f  mov     qword ptr [rsp+70h+var_50], rax
0x14001f564  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001f569  test    edi, edi
0x14001f56b  jg      short loc_14001F571
0x14001f56d  mov     eax, edi
0x14001f56f  jmp     short loc_14001F579
0x14001f571  movzx   eax, di
0x14001f574  or      eax, 80070000h
0x14001f579  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f580  lea     r9, a0; ": {0}"
0x14001f587  mov     [rbp+var_10], eax
0x14001f58a  mov     r8d, 3
0x14001f590  lea     rax, [rbp+var_10]
0x14001f594  mov     qword ptr [rbp+var_40], rax
0x14001f598  lea     rax, [rbp+var_40]
0x14001f59c  mov     qword ptr [rsp+70h+var_50], rax
0x14001f5a1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001f5a6  test    edi, edi
0x14001f5a8  jz      short loc_14001F627
0x14001f5aa  mov     r9d, edi
0x14001f5ad  mov     edx, 12Dh
0x14001f5b2  jmp     loc_14001F30F
0x14001f5b7  cmp     r14d, eax
0x14001f5ba  jnb     short loc_14001F61C
0x14001f5bc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f5c3  test    rcx, rcx
0x14001f5c6  jz      short loc_14001F60C
0x14001f5c8  xor     edx, edx
0x14001f5ca  lea     r9, aFailedToAlloca_9; "Failed to allocate buffer for full path"...
0x14001f5d1  lea     r8d, [rdx+3]
0x14001f5d5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001f5da  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f5e1  lea     rax, [rbp+var_10]
0x14001f5e5  mov     [rbp+var_28], rax
0x14001f5e9  lea     r9, a0; ": {0}"
0x14001f5f0  lea     rax, [rbp+var_28]
0x14001f5f4  mov     edi, 8007007Ah
0x14001f5f9  mov     r8d, 3
0x14001f5ff  mov     qword ptr [rsp+70h+var_50], rax
  ... truncated ...
```
