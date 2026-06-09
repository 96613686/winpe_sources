# FileGetContent

- ea: `0x180148984`
- end: `0x180148f40`
- name: `FileGetContent`
- size: `1468`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x1800c52f8`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x1800061e0`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x18008b38c`
- `0x18008b3ec`
- `0x180148984`

## import_xrefs

- `ntdll!NtClose` at `0x180148c85`
- `ntdll!NtClose` at `0x180148ca4`
- `ntdll!NtClose` at `0x180148d4e`
- `ntdll!NtClose` at `0x180148df2`
- `ntdll!NtClose` at `0x180148e1a`
- `ntdll!NtClose` at `0x180148eda`
- `ntdll!NtClose` at `0x180148f02`
- `ntdll!NtClose` at `0x180148c85`
- `ntdll!NtClose` at `0x180148ca4`
- `ntdll!NtClose` at `0x180148d4e`
- `ntdll!NtClose` at `0x180148df2`
- `ntdll!NtClose` at `0x180148e1a`
- `ntdll!NtClose` at `0x180148eda`
- `ntdll!NtClose` at `0x180148f02`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180148d1a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180148d1a`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180148be0`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180148be0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180148bbc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180148bbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148e3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180148e3f`

## string_xrefs

- `0x1801489dd`: `No path specified`
- `0x180148e62`: `Failed to open file: {}`
- `0x180148ac8`: `Read count exceeds maximum size`
- `0x180148b3e`: `No read result specified`
- `0x180148a54`: `No read count result specified`
- `0x180148d84`: `Failed to read from file`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall FileGetContent(const WCHAR *a1, __int64 a2, union _LARGE_INTEGER *a3, _QWORD *a4)
{
  unsigned int v6; // edi
  char *FileW; // rax
  char *v9; // rdi
  signed int v10; // esi
  unsigned int v11; // eax
  unsigned int v12; // ebx
  union _LARGE_INTEGER v13; // r14
  union _LARGE_INTEGER v14; // rsi
  char *v15; // r15
  DWORD v16; // r8d
  signed int v17; // esi
  unsigned int v18; // eax
  const struct std::nothrow_t *v19; // rdx
  const struct std::nothrow_t *v20; // rdx
  signed int LastError; // esi
  unsigned int v22; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-50h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-50h]
  unsigned int dwCreationDispositionb; // [rsp+20h] [rbp-50h]
  unsigned int v26[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v27; // [rsp+48h] [rbp-28h]
  const WCHAR *v28; // [rsp+50h] [rbp-20h] BYREF
  int v29; // [rsp+58h] [rbp-18h] BYREF
  DWORD NumberOfBytesRead; // [rsp+5Ch] [rbp-14h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v27 = -2;
  v28 = a1;
  FileSize.QuadPart = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    v29 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No path specified");
      *(_QWORD *)v26 = &v29;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v26);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C0,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    return v6;
  }
  if ( !a3 )
  {
    v6 = -2147467261;
    v29 = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No read count result specified");
      *(_QWORD *)v26 = &v29;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v26);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C1,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)0x80004003LL,
      dwCreationDisposition);
    return v6;
  }
  if ( a3->QuadPart == -1 )
  {
    v6 = -2147024809;
    v29 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Read count exceeds maximum size");
      *(_QWORD *)v26 = &v29;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v26);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C2,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    return v6;
  }
  if ( !a4 )
  {
    v6 = -2147467261;
    v29 = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No read result specified");
      *(_QWORD *)v26 = &v29;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
        (__int64)v26);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C3,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)0x80004003LL,
      dwCreationDisposition);
    return v6;
  }
  FileW = (char *)CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v9 = FileW;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to open file: {}",
        (__int64)&v28);
      if ( LastError > 0 )
        v22 = (unsigned __int16)LastError | 0x80070000;
      else
        v22 = LastError;
      v29 = v22;
      *(_QWORD *)v26 = &v29;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)v26);
    }
    if ( LastError )
    {
      v12 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x6C9,
              (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
              (const char *)(unsigned int)LastError,
              dwCreationDispositiona);
      if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v9) < 0 )
        __fastfail(7u);
      return v12;
    }
    if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v9) < 0 )
      __fastfail(7u);
  }
  else if ( GetFileSizeEx(FileW, &FileSize) )
  {
    v13.QuadPart = 0;
    v14 = FileSize;
    if ( a3->QuadPart && a3->QuadPart < (unsigned __int64)FileSize.QuadPart )
      v14 = *a3;
    v15 = (char *)operator new[](v14.QuadPart + 1);
    if ( v14.QuadPart )
    {
      while ( 1 )
      {
        v16 = v14.QuadPart - v13.QuadPart <= 0xFFFFFFFFuLL ? v14.LowPart - v13.LowPart : -1;
        NumberOfBytesRead = v16;
        if ( !ReadFile(v9, &v15[v13.QuadPart], v16, &NumberOfBytesRead, 0) )
          break;
        if ( NumberOfBytesRead )
        {
          v13.QuadPart += NumberOfBytesRead;
          if ( v13.QuadPart < (unsigned __int64)v14.QuadPart )
            continue;
        }
        goto LABEL_42;
      }
      v17 = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to read from file");
        if ( v17 > 0 )
          v18 = (unsigned __int16)v17 | 0x80070000;
        else
          v18 = v17;
        v29 = v18;
        *(_QWORD *)v26 = &v29;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
          (__int64)v26);
      }
      if ( v17 )
      {
        v12 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x6EF,
                (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
                (const char *)(unsigned int)v17,
                dwCreationDispositionb);
        if ( NtClose(v9) < 0 )
          __fastfail(7u);
        operator delete(v15, v19);
        return v12;
      }
      if ( NtClose(v9) < 0 )
        __fastfail(7u);
      operator delete(v15, v20);
    }
    else
    {
LABEL_42:
      v15[v14.QuadPart] = 0;
      *a4 = v15;
      *a3 = v13;
      if ( NtClose(v9) < 0 )
        __fastfail(7u);
    }
  }
  else
  {
    v10 = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get size of the file: {}",
        (__int64)&v28);
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      else
        v11 = v10;
      v29 = v11;
      *(_QWORD *)v26 = &v29;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)v26);
    }
    if ( v10 )
    {
      v12 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x6CC,
              (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
              (const char *)(unsigned int)v10,
              dwCreationDispositiona);
      if ( NtClose(v9) < 0 )
        __fastfail(7u);
      return v12;
    }
    if ( NtClose(v9) < 0 )
      __fastfail(7u);
  }
  return 0;
}

```

## disassembly

```asm
0x180148984  mov     rax, rsp
0x180148987  push    rbp
0x180148988  push    rsi
0x180148989  push    rdi
0x18014898a  push    r12
0x18014898c  push    r13
0x18014898e  push    r14
0x180148990  push    r15
0x180148992  mov     rbp, rsp
0x180148995  sub     rsp, 70h
0x180148999  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x1801489a1  mov     [rax+10h], rbx
0x1801489a5  mov     rax, cs:__security_cookie
0x1801489ac  xor     rax, rsp
0x1801489af  mov     [rbp+var_8], rax
0x1801489b3  mov     r13, r9
0x1801489b6  mov     r12, r8
0x1801489b9  mov     [rbp+var_20], rcx
0x1801489bd  xor     r15d, r15d
0x1801489c0  mov     qword ptr [rbp+FileSize], r15
0x1801489c4  test    rcx, rcx
0x1801489c7  jnz     short loc_180148A3B
0x1801489c9  mov     edi, 80070057h
0x1801489ce  mov     [rbp+var_18], edi
0x1801489d1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801489d8  test    rcx, rcx
0x1801489db  jz      short loc_180148A1B
0x1801489dd  lea     r9, aNoPathSpecifie; "No path specified"
0x1801489e4  lea     ebx, [r15+3]
0x1801489e8  mov     r8d, ebx
0x1801489eb  xor     edx, edx
0x1801489ed  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801489f2  lea     rax, [rbp+var_18]
0x1801489f6  mov     qword ptr [rbp+var_30], rax
0x1801489fa  lea     rax, [rbp+var_30]
0x1801489fe  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; int
0x180148a03  lea     r9, asc_1802C6678; ": {}"
0x180148a0a  mov     r8d, ebx
0x180148a0d  mov     dl, 1
0x180148a0f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180148a16  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180148a1b  mov     rcx, [rbp+38h]; this
0x180148a1f  mov     r9d, edi; char *
0x180148a22  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180148a29  mov     edx, 6C0h; void *
0x180148a2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180148a33  nop
0x180148a34  mov     eax, edi
0x180148a36  jmp     loc_180148F1B
0x180148a3b  test    r12, r12
0x180148a3e  jnz     short loc_180148AAE
0x180148a40  mov     edi, 80004003h
0x180148a45  mov     [rbp+var_18], edi
0x180148a48  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180148a4f  test    rcx, rcx
0x180148a52  jz      short loc_180148A93
0x180148a54  lea     r9, aNoReadCountRes; "No read count result specified"
0x180148a5b  lea     ebx, [r12+3]
0x180148a60  mov     r8d, ebx
0x180148a63  xor     edx, edx
0x180148a65  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180148a6a  lea     rax, [rbp+var_18]
0x180148a6e  mov     qword ptr [rbp+var_30], rax
0x180148a72  lea     rax, [rbp+var_30]
0x180148a76  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; int
0x180148a7b  lea     r9, asc_1802C6678; ": {}"
0x180148a82  mov     r8d, ebx
0x180148a85  mov     dl, 1
0x180148a87  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180148a8e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180148a93  mov     rcx, [rbp+38h]; this
0x180148a97  mov     r9d, edi; char *
0x180148a9a  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180148aa1  mov     edx, 6C1h; void *
0x180148aa6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180148aab  nop
0x180148aac  jmp     short loc_180148A34
0x180148aae  cmp     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x180148ab2  jb      short loc_180148B25
0x180148ab4  mov     edi, 80070057h
0x180148ab9  mov     [rbp+var_18], edi
0x180148abc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180148ac3  test    rcx, rcx
0x180148ac6  jz      short loc_180148B07
0x180148ac8  lea     r9, aReadCountExcee; "Read count exceeds maximum size"
0x180148acf  mov     ebx, 3
0x180148ad4  mov     r8d, ebx
0x180148ad7  xor     edx, edx
0x180148ad9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180148ade  lea     rax, [rbp+var_18]
0x180148ae2  mov     qword ptr [rbp+var_30], rax
0x180148ae6  lea     rax, [rbp+var_30]
0x180148aea  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; int
0x180148aef  lea     r9, asc_1802C6678; ": {}"
0x180148af6  mov     r8d, ebx
0x180148af9  mov     dl, 1
0x180148afb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180148b02  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180148b07  mov     rcx, [rbp+38h]; this
0x180148b0b  mov     r9d, edi; char *
0x180148b0e  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180148b15  mov     edx, 6C2h; void *
0x180148b1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180148b1f  nop
0x180148b20  jmp     loc_180148A34
0x180148b25  test    r13, r13
0x180148b28  jnz     short loc_180148B9A
0x180148b2a  mov     edi, 80004003h
0x180148b2f  mov     [rbp+var_18], edi
0x180148b32  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180148b39  test    rcx, rcx
0x180148b3c  jz      short loc_180148B7C
0x180148b3e  lea     r9, aNoReadResultSp; "No read result specified"
0x180148b45  lea     ebx, [r13+3]
0x180148b49  mov     r8d, ebx
0x180148b4c  xor     edx, edx
0x180148b4e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180148b53  lea     rax, [rbp+var_18]
0x180148b57  mov     qword ptr [rbp+var_30], rax
0x180148b5b  lea     rax, [rbp+var_30]
0x180148b5f  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; int
0x180148b64  lea     r9, asc_1802C6678; ": {}"
0x180148b6b  mov     r8d, ebx
0x180148b6e  mov     dl, 1
0x180148b70  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180148b77  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180148b7c  mov     rcx, [rbp+38h]; this
0x180148b80  mov     r9d, edi; char *
0x180148b83  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180148b8a  mov     edx, 6C3h; void *
0x180148b8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180148b94  nop
0x180148b95  jmp     loc_180148A34
0x180148b9a  mov     [rsp+70h+hTemplateFile], r15; hTemplateFile
0x180148b9f  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180148ba7  mov     ebx, 3
0x180148bac  mov     [rsp+70h+dwCreationDisposition], ebx; dwCreationDisposition
0x180148bb0  xor     r9d, r9d; lpSecurityAttributes
0x180148bb3  mov     edx, 80000000h; dwDesiredAccess
0x180148bb8  lea     r8d, [rbx-2]; dwShareMode
0x180148bbc  call    cs:__imp_CreateFileW
0x180148bc3  nop     dword ptr [rax+rax+00h]
0x180148bc8  mov     rdi, rax
0x180148bcb  lea     rcx, [rax-1]
0x180148bcf  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180148bd3  ja      loc_180148E3F
0x180148bd9  lea     rdx, [rbp+FileSize]; lpFileSize
0x180148bdd  mov     rcx, rax; hFile
0x180148be0  call    cs:__imp_GetFileSizeEx
0x180148be7  nop     dword ptr [rax+rax+00h]
0x180148bec  test    eax, eax
0x180148bee  jnz     loc_180148CC0
0x180148bf4  call    cs:__imp_GetLastError
0x180148bfb  nop     dword ptr [rax+rax+00h]
0x180148c00  mov     esi, eax
0x180148c02  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180148c09  test    rcx, rcx
0x180148c0c  jz      short loc_180148C64
0x180148c0e  lea     rax, [rbp+var_20]
0x180148c12  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x180148c17  lea     r9, aFailedToGetSiz; "Failed to get size of the file: {}"
0x180148c1e  mov     r8d, ebx
0x180148c21  xor     edx, edx
0x180148c23  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x180148c28  test    esi, esi
0x180148c2a  jg      short loc_180148C30
0x180148c2c  mov     eax, esi
0x180148c2e  jmp     short loc_180148C38
0x180148c30  movzx   eax, si
0x180148c33  or      eax, 80070000h
0x180148c38  mov     [rbp+var_18], eax
0x180148c3b  lea     rax, [rbp+var_18]
0x180148c3f  mov     qword ptr [rbp+var_30], rax
0x180148c43  lea     rax, [rbp+var_30]
0x180148c47  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; unsigned int
0x180148c4c  lea     r9, a0; ": {0}"
0x180148c53  mov     r8d, ebx
0x180148c56  mov     dl, 1
0x180148c58  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180148c5f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180148c64  test    esi, esi
0x180148c66  jz      short loc_180148CA1
0x180148c68  mov     rcx, [rbp+38h]; this
0x180148c6c  mov     r9d, esi; char *
0x180148c6f  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180148c76  mov     edx, 6CCh; void *
0x180148c7b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180148c80  mov     ebx, eax
0x180148c82  mov     rcx, rdi; Handle
0x180148c85  call    cs:__imp_NtClose
0x180148c8c  nop     dword ptr [rax+rax+00h]
0x180148c91  test    eax, eax
0x180148c93  jns     short loc_180148C9C
0x180148c95  mov     ecx, 7
0x180148c9a  int     29h; Win8: RtlFailFast(ecx)
0x180148c9c  jmp     loc_180148EF1
0x180148ca1  mov     rcx, rdi; Handle
0x180148ca4  call    cs:__imp_NtClose
0x180148cab  nop     dword ptr [rax+rax+00h]
0x180148cb0  test    eax, eax
0x180148cb2  jns     short loc_180148CBB
0x180148cb4  mov     ecx, 7
0x180148cb9  int     29h; Win8: RtlFailFast(ecx)
0x180148cbb  jmp     loc_180148F19
0x180148cc0  mov     r14, r15
0x180148cc3  mov     rsi, qword ptr [rbp+FileSize]
0x180148cc7  cmp     [r12], r15
0x180148ccb  jz      short loc_180148CD6
0x180148ccd  cmp     [r12], rsi
0x180148cd1  cmovb   rsi, [r12]
0x180148cd6  lea     rcx, [rsi+1]; unsigned __int64
0x180148cda  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180148cdf  mov     r15, rax
0x180148ce2  test    rsi, rsi
0x180148ce5  jz      short loc_180148D3E
0x180148ce7  mov     eax, 0FFFFFFFFh
0x180148cec  mov     rcx, rsi
0x180148cef  sub     rcx, r14
0x180148cf2  cmp     rcx, rax
0x180148cf5  jbe     short loc_180148CFC
0x180148cf7  mov     r8d, eax
0x180148cfa  jmp     short loc_180148D02
0x180148cfc  mov     r8d, esi
0x180148cff  sub     r8d, r14d; nNumberOfBytesToRead
0x180148d02  mov     [rbp+NumberOfBytesRead], r8d
0x180148d06  lea     rdx, [r15+r14]; lpBuffer
0x180148d0a  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x180148d13  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180148d17  mov     rcx, rdi; hFile
0x180148d1a  call    cs:__imp_ReadFile
0x180148d21  nop     dword ptr [rax+rax+00h]
0x180148d26  test    eax, eax
0x180148d28  jz      short loc_180148D6A
0x180148d2a  mov     eax, [rbp+NumberOfBytesRead]
0x180148d2d  test    eax, eax
0x180148d2f  jz      short loc_180148D3E
0x180148d31  add     r14, rax
0x180148d34  cmp     r14, rsi
0x180148d37  mov     eax, 0FFFFFFFFh
0x180148d3c  jb      short loc_180148CEC
0x180148d3e  mov     byte ptr [r15+rsi], 0
0x180148d43  mov     [r13+0], r15
0x180148d47  mov     [r12], r14
0x180148d4b  mov     rcx, rdi; Handle
0x180148d4e  call    cs:__imp_NtClose
0x180148d55  nop     dword ptr [rax+rax+00h]
0x180148d5a  test    eax, eax
0x180148d5c  jns     short loc_180148D65
0x180148d5e  mov     ecx, 7
0x180148d63  int     29h; Win8: RtlFailFast(ecx)
0x180148d65  jmp     loc_180148F19
0x180148d6a  call    cs:__imp_GetLastError
0x180148d71  nop     dword ptr [rax+rax+00h]
0x180148d76  mov     esi, eax
0x180148d78  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180148d7f  test    rcx, rcx
0x180148d82  jz      short loc_180148DD1
0x180148d84  lea     r9, aFailedToReadFr; "Failed to read from file"
0x180148d8b  mov     r8d, ebx
0x180148d8e  xor     edx, edx
0x180148d90  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180148d95  test    esi, esi
0x180148d97  jg      short loc_180148D9D
0x180148d99  mov     eax, esi
0x180148d9b  jmp     short loc_180148DA5
0x180148d9d  movzx   eax, si
0x180148da0  or      eax, 80070000h
0x180148da5  mov     [rbp+var_18], eax
0x180148da8  lea     rax, [rbp+var_18]
0x180148dac  mov     qword ptr [rbp+var_30], rax
0x180148db0  lea     rax, [rbp+var_30]
0x180148db4  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; unsigned int
0x180148db9  lea     r9, a0; ": {0}"
0x180148dc0  mov     r8d, ebx
0x180148dc3  mov     dl, 1
0x180148dc5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180148dcc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180148dd1  test    esi, esi
0x180148dd3  jz      short loc_180148E17
0x180148dd5  mov     rcx, [rbp+38h]; this
0x180148dd9  mov     r9d, esi; char *
0x180148ddc  lea     r8, aOnecoreBaseCbs_15; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180148de3  mov     edx, 6EFh; void *
0x180148de8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180148ded  mov     ebx, eax
0x180148def  mov     rcx, rdi; Handle
0x180148df2  call    cs:__imp_NtClose
0x180148df9  nop     dword ptr [rax+rax+00h]
0x180148dfe  test    eax, eax
0x180148e00  jns     short loc_180148E09
0x180148e02  mov     ecx, 7
0x180148e07  int     29h; Win8: RtlFailFast(ecx)
0x180148e09  mov     rcx, r15; void *
0x180148e0c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180148e11  nop
0x180148e12  jmp     loc_180148EF1
0x180148e17  mov     rcx, rdi; Handle
0x180148e1a  call    cs:__imp_NtClose
0x180148e21  nop     dword ptr [rax+rax+00h]
0x180148e26  test    eax, eax
  ... truncated ...
```
