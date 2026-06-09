# FileGetContent

- ea: `0x1800427f8`
- end: `0x180042d34`
- name: `FileGetContent`
- size: `1340`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18006def0`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x18000636c`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001a810`
- `0x1800296a4`
- `0x1800427f8`

## import_xrefs

- `ntdll!NtClose` at `0x180042abc`
- `ntdll!NtClose` at `0x180042bf1`
- `ntdll!NtClose` at `0x180042c0d`
- `ntdll!NtClose` at `0x180042cce`
- `ntdll!NtClose` at `0x180042cf6`
- `ntdll!NtClose` at `0x180042abc`
- `ntdll!NtClose` at `0x180042bf1`
- `ntdll!NtClose` at `0x180042c0d`
- `ntdll!NtClose` at `0x180042cce`
- `ntdll!NtClose` at `0x180042cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042b69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042c33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042a2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042b69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042c33`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180042b34`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180042b34`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180042a17`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180042a17`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800429f3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800429f3`

## string_xrefs

- `0x180042851`: `No path specified`
- `0x180042c56`: `Failed to open file: {}`
- `0x1800428c8`: `No read count result specified`
- `0x180042927`: `Read count exceeds maximum size`
- `0x180042b83`: `Failed to read from file`
- `0x180042989`: `No read result specified`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FileGetContent(const WCHAR *a1, __int64 a2, union _LARGE_INTEGER *a3, _QWORD *a4)
{
  unsigned int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  char *FileW; // rax
  char *v14; // rdi
  signed int v15; // esi
  __int64 v16; // rdx
  unsigned int v17; // eax
  unsigned int v18; // ebx
  union _LARGE_INTEGER v19; // r14
  union _LARGE_INTEGER v20; // rsi
  char *v21; // r12
  DWORD v22; // r8d
  signed int LastError; // esi
  __int64 v24; // rdx
  unsigned int v25; // eax
  signed int v26; // esi
  __int64 v27; // rdx
  unsigned int v28; // eax
  unsigned int *dwCreationDisposition; // [rsp+20h] [rbp-50h]
  unsigned int *dwCreationDispositiona; // [rsp+20h] [rbp-50h]
  unsigned int *dwCreationDispositionb; // [rsp+20h] [rbp-50h]
  unsigned int v32[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v33; // [rsp+48h] [rbp-28h]
  const WCHAR *v34; // [rsp+50h] [rbp-20h] BYREF
  int v35; // [rsp+58h] [rbp-18h] BYREF
  DWORD NumberOfBytesRead; // [rsp+5Ch] [rbp-14h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v33 = -2;
  v34 = a1;
  FileSize.QuadPart = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    v35 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No path specified");
      *(_QWORD *)v32 = &v35;
      dwCreationDisposition = v32;
      LOBYTE(v7) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v7,
        3,
        ": {}");
    }
    v8 = 1728;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v6,
      (int)dwCreationDisposition);
    return v6;
  }
  if ( !a3 )
  {
    v6 = -2147467261;
    v35 = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No read count result specified");
      *(_QWORD *)v32 = &v35;
      dwCreationDisposition = v32;
      LOBYTE(v10) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v10,
        3,
        ": {}");
    }
    v8 = 1729;
    goto LABEL_5;
  }
  if ( a3->QuadPart == -1 )
  {
    v6 = -2147024809;
    v35 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Read count exceeds maximum size");
      *(_QWORD *)v32 = &v35;
      dwCreationDisposition = v32;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v11,
        3,
        ": {}");
    }
    v8 = 1730;
    goto LABEL_5;
  }
  if ( !a4 )
  {
    v6 = -2147467261;
    v35 = -2147467261;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No read result specified");
      *(_QWORD *)v32 = &v35;
      dwCreationDisposition = v32;
      LOBYTE(v12) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v12,
        3,
        ": {}");
    }
    v8 = 1731;
    goto LABEL_5;
  }
  FileW = (char *)CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v14 = FileW;
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( GetFileSizeEx(FileW, &FileSize) )
    {
      v19.QuadPart = 0;
      v20 = FileSize;
      if ( a3->QuadPart && a3->QuadPart < (unsigned __int64)FileSize.QuadPart )
        v20 = *a3;
      v21 = (char *)operator new[](v20.QuadPart + 1);
      if ( v20.QuadPart )
      {
        while ( 1 )
        {
          v22 = v20.QuadPart - v19.QuadPart <= 0xFFFFFFFFuLL ? v20.LowPart - v19.LowPart : -1;
          NumberOfBytesRead = v22;
          if ( !ReadFile(v14, &v21[v19.QuadPart], v22, &NumberOfBytesRead, 0) )
            break;
          if ( NumberOfBytesRead )
          {
            v19.QuadPart += NumberOfBytesRead;
            if ( v19.QuadPart < (unsigned __int64)v20.QuadPart )
              continue;
          }
          goto LABEL_40;
        }
        LastError = GetLastError();
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to read from file");
          if ( LastError > 0 )
            v25 = (unsigned __int16)LastError | 0x80070000;
          else
            v25 = LastError;
          v35 = v25;
          *(_QWORD *)v32 = &v35;
          dwCreationDispositionb = v32;
          LOBYTE(v24) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v24,
            3,
            ": {0}");
        }
        if ( LastError )
        {
          v18 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x6EF,
                  (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
                  (const char *)(unsigned int)LastError,
                  (unsigned int)dwCreationDispositionb);
          if ( NtClose(v14) < 0 )
            __fastfail(7u);
        }
        else
        {
          if ( NtClose(v14) < 0 )
            __fastfail(7u);
          v18 = 0;
        }
        operator delete(v21);
        return v18;
      }
LABEL_40:
      v21[v20.QuadPart] = 0;
      *a4 = v21;
      *a3 = v19;
    }
    else
    {
      v15 = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to get size of the file: {}",
          &v34);
        if ( v15 > 0 )
          v17 = (unsigned __int16)v15 | 0x80070000;
        else
          v17 = v15;
        v35 = v17;
        *(_QWORD *)v32 = &v35;
        dwCreationDispositiona = v32;
        LOBYTE(v16) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v16,
          3,
          ": {0}");
      }
      if ( v15 )
      {
        v18 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x6CC,
                (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
                (const char *)(unsigned int)v15,
                (unsigned int)dwCreationDispositiona);
        if ( NtClose(v14) < 0 )
          __fastfail(7u);
        return v18;
      }
    }
LABEL_65:
    if ( NtClose(v14) < 0 )
      __fastfail(7u);
    return 0;
  }
  v26 = GetLastError();
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      *(_QWORD *)&LogAdapter::g_Logger,
      0,
      3,
      "Failed to open file: {}",
      &v34);
    if ( v26 > 0 )
      v28 = (unsigned __int16)v26 | 0x80070000;
    else
      v28 = v26;
    v35 = v28;
    *(_QWORD *)v32 = &v35;
    dwCreationDispositiona = v32;
    LOBYTE(v27) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v27,
      3,
      ": {0}");
  }
  if ( v26 )
  {
    v18 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x6C9,
            (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
            (const char *)(unsigned int)v26,
            (unsigned int)dwCreationDispositiona);
    if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && NtClose(v14) < 0 )
      __fastfail(7u);
    return v18;
  }
  if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_65;
  return 0;
}

```

## disassembly

```asm
0x1800427f8  mov     rax, rsp
0x1800427fb  push    rbp
0x1800427fc  push    rsi
0x1800427fd  push    rdi
0x1800427fe  push    r12
0x180042800  push    r13
0x180042802  push    r14
0x180042804  push    r15
0x180042806  mov     rbp, rsp
0x180042809  sub     rsp, 70h
0x18004280d  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x180042815  mov     [rax+10h], rbx
0x180042819  mov     rax, cs:__security_cookie
0x180042820  xor     rax, rsp
0x180042823  mov     [rbp+var_8], rax
0x180042827  mov     r13, r9
0x18004282a  mov     r15, r8
0x18004282d  mov     [rbp+var_20], rcx
0x180042831  xor     r12d, r12d
0x180042834  mov     qword ptr [rbp+FileSize], r12
0x180042838  test    rcx, rcx
0x18004283b  jnz     short loc_1800428AF
0x18004283d  mov     edi, 80070057h
0x180042842  mov     [rbp+var_18], edi
0x180042845  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004284c  test    rcx, rcx
0x18004284f  jz      short loc_180042890
0x180042851  lea     r9, aNoPathSpecifie; "No path specified"
0x180042858  lea     ebx, [r12+3]
0x18004285d  mov     r8d, ebx
0x180042860  xor     edx, edx
0x180042862  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180042867  lea     rax, [rbp+var_18]
0x18004286b  mov     qword ptr [rbp+var_30], rax
0x18004286f  lea     rax, [rbp+var_30]
0x180042873  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; int
0x180042878  lea     r9, asc_1801CAFB4; ": {}"
0x18004287f  mov     r8d, ebx
0x180042882  mov     dl, 1
0x180042884  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004288b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180042890  mov     edx, 6C0h; void *
0x180042895  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18004289c  mov     r9d, edi; char *
0x18004289f  mov     rcx, [rbp+38h]; this
0x1800428a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800428a8  mov     eax, edi
0x1800428aa  jmp     loc_180042D0F
0x1800428af  test    r15, r15
0x1800428b2  jnz     short loc_18004290D
0x1800428b4  mov     edi, 80004003h
0x1800428b9  mov     [rbp+var_18], edi
0x1800428bc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800428c3  test    rcx, rcx
0x1800428c6  jz      short loc_180042906
0x1800428c8  lea     r9, aNoReadCountRes; "No read count result specified"
0x1800428cf  lea     ebx, [r15+3]
0x1800428d3  mov     r8d, ebx
0x1800428d6  xor     edx, edx
0x1800428d8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800428dd  lea     rax, [rbp+var_18]
0x1800428e1  mov     qword ptr [rbp+var_30], rax
0x1800428e5  lea     rax, [rbp+var_30]
0x1800428e9  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800428ee  lea     r9, asc_1801CAFB4; ": {}"
0x1800428f5  mov     r8d, ebx
0x1800428f8  mov     dl, 1
0x1800428fa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180042901  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180042906  mov     edx, 6C1h
0x18004290b  jmp     short loc_180042895
0x18004290d  cmp     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x180042911  jb      short loc_180042970
0x180042913  mov     edi, 80070057h
0x180042918  mov     [rbp+var_18], edi
0x18004291b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180042922  test    rcx, rcx
0x180042925  jz      short loc_180042966
0x180042927  lea     r9, aReadCountExcee; "Read count exceeds maximum size"
0x18004292e  mov     ebx, 3
0x180042933  mov     r8d, ebx
0x180042936  xor     edx, edx
0x180042938  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004293d  lea     rax, [rbp+var_18]
0x180042941  mov     qword ptr [rbp+var_30], rax
0x180042945  lea     rax, [rbp+var_30]
0x180042949  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x18004294e  lea     r9, asc_1801CAFB4; ": {}"
0x180042955  mov     r8d, ebx
0x180042958  mov     dl, 1
0x18004295a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180042961  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180042966  mov     edx, 6C2h
0x18004296b  jmp     loc_180042895
0x180042970  test    r13, r13
0x180042973  jnz     short loc_1800429D1
0x180042975  mov     edi, 80004003h
0x18004297a  mov     [rbp+var_18], edi
0x18004297d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180042984  test    rcx, rcx
0x180042987  jz      short loc_1800429C7
0x180042989  lea     r9, aNoReadResultSp; "No read result specified"
0x180042990  lea     ebx, [r13+3]
0x180042994  mov     r8d, ebx
0x180042997  xor     edx, edx
0x180042999  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18004299e  lea     rax, [rbp+var_18]
0x1800429a2  mov     qword ptr [rbp+var_30], rax
0x1800429a6  lea     rax, [rbp+var_30]
0x1800429aa  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x1800429af  lea     r9, asc_1801CAFB4; ": {}"
0x1800429b6  mov     r8d, ebx
0x1800429b9  mov     dl, 1
0x1800429bb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800429c2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800429c7  mov     edx, 6C3h
0x1800429cc  jmp     loc_180042895
0x1800429d1  mov     [rsp+70h+hTemplateFile], r12; hTemplateFile
0x1800429d6  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800429de  mov     ebx, 3
0x1800429e3  mov     [rsp+70h+dwCreationDisposition], ebx; dwCreationDisposition
0x1800429e7  xor     r9d, r9d; lpSecurityAttributes
0x1800429ea  mov     edx, 80000000h; dwDesiredAccess
0x1800429ef  lea     r8d, [rbx-2]; dwShareMode
0x1800429f3  call    cs:__imp_CreateFileW
0x1800429fa  nop     dword ptr [rax+rax+00h]
0x1800429ff  mov     rdi, rax
0x180042a02  lea     rcx, [rax-1]
0x180042a06  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180042a0a  ja      loc_180042C33
0x180042a10  lea     rdx, [rbp+FileSize]; lpFileSize
0x180042a14  mov     rcx, rax; hFile
0x180042a17  call    cs:__imp_GetFileSizeEx
0x180042a1e  nop     dword ptr [rax+rax+00h]
0x180042a23  test    eax, eax
0x180042a25  jnz     loc_180042ADD
0x180042a2b  call    cs:__imp_GetLastError
0x180042a32  nop     dword ptr [rax+rax+00h]
0x180042a37  mov     esi, eax
0x180042a39  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180042a40  test    rcx, rcx
0x180042a43  jz      short loc_180042A9B
0x180042a45  lea     rax, [rbp+var_20]
0x180042a49  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x180042a4e  lea     r9, aFailedToGetSiz; "Failed to get size of the file: {}"
0x180042a55  mov     r8d, ebx
0x180042a58  xor     edx, edx
0x180042a5a  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180042a5f  test    esi, esi
0x180042a61  jg      short loc_180042A67
0x180042a63  mov     eax, esi
0x180042a65  jmp     short loc_180042A6F
0x180042a67  movzx   eax, si
0x180042a6a  or      eax, 80070000h
0x180042a6f  mov     [rbp+var_18], eax
0x180042a72  lea     rax, [rbp+var_18]
0x180042a76  mov     qword ptr [rbp+var_30], rax
0x180042a7a  lea     rax, [rbp+var_30]
0x180042a7e  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; unsigned int
0x180042a83  lea     r9, a0; ": {0}"
0x180042a8a  mov     r8d, ebx
0x180042a8d  mov     dl, 1
0x180042a8f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180042a96  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180042a9b  test    esi, esi
0x180042a9d  jz      short loc_180042AD8
0x180042a9f  mov     rcx, [rbp+38h]; this
0x180042aa3  mov     r9d, esi; char *
0x180042aa6  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180042aad  mov     edx, 6CCh; void *
0x180042ab2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180042ab7  mov     ebx, eax
0x180042ab9  mov     rcx, rdi; Handle
0x180042abc  call    cs:__imp_NtClose
0x180042ac3  nop     dword ptr [rax+rax+00h]
0x180042ac8  test    eax, eax
0x180042aca  jns     short loc_180042AD3
0x180042acc  mov     ecx, 7
0x180042ad1  int     29h; Win8: RtlFailFast(ecx)
0x180042ad3  jmp     loc_180042CE5
0x180042ad8  jmp     loc_180042CF3
0x180042add  mov     r14, r12
0x180042ae0  mov     rsi, qword ptr [rbp+FileSize]
0x180042ae4  cmp     [r15], r12
0x180042ae7  jz      short loc_180042AF0
0x180042ae9  cmp     [r15], rsi
0x180042aec  cmovb   rsi, [r15]
0x180042af0  lea     rcx, [rsi+1]; unsigned __int64
0x180042af4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180042af9  mov     r12, rax
0x180042afc  test    rsi, rsi
0x180042aff  jz      short loc_180042B58
0x180042b01  mov     eax, 0FFFFFFFFh
0x180042b06  mov     rcx, rsi
0x180042b09  sub     rcx, r14
0x180042b0c  cmp     rcx, rax
0x180042b0f  jbe     short loc_180042B16
0x180042b11  mov     r8d, eax
0x180042b14  jmp     short loc_180042B1C
0x180042b16  mov     r8d, esi
0x180042b19  sub     r8d, r14d; nNumberOfBytesToRead
0x180042b1c  mov     [rbp+NumberOfBytesRead], r8d
0x180042b20  lea     rdx, [r12+r14]; lpBuffer
0x180042b24  mov     qword ptr [rsp+70h+dwCreationDisposition], 0; lpOverlapped
0x180042b2d  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180042b31  mov     rcx, rdi; hFile
0x180042b34  call    cs:__imp_ReadFile
0x180042b3b  nop     dword ptr [rax+rax+00h]
0x180042b40  test    eax, eax
0x180042b42  jz      short loc_180042B69
0x180042b44  mov     eax, [rbp+NumberOfBytesRead]
0x180042b47  test    eax, eax
0x180042b49  jz      short loc_180042B58
0x180042b4b  add     r14, rax
0x180042b4e  cmp     r14, rsi
0x180042b51  mov     eax, 0FFFFFFFFh
0x180042b56  jb      short loc_180042B06
0x180042b58  mov     byte ptr [r12+rsi], 0
0x180042b5d  mov     [r13+0], r12
0x180042b61  mov     [r15], r14
0x180042b64  jmp     loc_180042CF3
0x180042b69  call    cs:__imp_GetLastError
0x180042b70  nop     dword ptr [rax+rax+00h]
0x180042b75  mov     esi, eax
0x180042b77  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180042b7e  test    rcx, rcx
0x180042b81  jz      short loc_180042BD0
0x180042b83  lea     r9, aFailedToReadFr; "Failed to read from file"
0x180042b8a  mov     r8d, ebx
0x180042b8d  xor     edx, edx
0x180042b8f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180042b94  test    esi, esi
0x180042b96  jg      short loc_180042B9C
0x180042b98  mov     eax, esi
0x180042b9a  jmp     short loc_180042BA4
0x180042b9c  movzx   eax, si
0x180042b9f  or      eax, 80070000h
0x180042ba4  mov     [rbp+var_18], eax
0x180042ba7  lea     rax, [rbp+var_18]
0x180042bab  mov     qword ptr [rbp+var_30], rax
0x180042baf  lea     rax, [rbp+var_30]
0x180042bb3  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; unsigned int
0x180042bb8  lea     r9, a0; ": {0}"
0x180042bbf  mov     r8d, ebx
0x180042bc2  mov     dl, 1
0x180042bc4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180042bcb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180042bd0  test    esi, esi
0x180042bd2  jz      short loc_180042C0A
0x180042bd4  mov     rcx, [rbp+38h]; this
0x180042bd8  mov     r9d, esi; char *
0x180042bdb  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x180042be2  mov     edx, 6EFh; void *
0x180042be7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180042bec  mov     ebx, eax
0x180042bee  mov     rcx, rdi; Handle
0x180042bf1  call    cs:__imp_NtClose
0x180042bf8  nop     dword ptr [rax+rax+00h]
0x180042bfd  test    eax, eax
0x180042bff  jns     short loc_180042C08
0x180042c01  mov     ecx, 7
0x180042c06  int     29h; Win8: RtlFailFast(ecx)
0x180042c08  jmp     short loc_180042C26
0x180042c0a  mov     rcx, rdi; Handle
0x180042c0d  call    cs:__imp_NtClose
0x180042c14  nop     dword ptr [rax+rax+00h]
0x180042c19  test    eax, eax
0x180042c1b  jns     short loc_180042C24
0x180042c1d  mov     ecx, 7
0x180042c22  int     29h; Win8: RtlFailFast(ecx)
0x180042c24  xor     ebx, ebx
0x180042c26  mov     rcx, r12; Block
0x180042c29  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180042c2e  jmp     loc_180042CE5
0x180042c33  call    cs:__imp_GetLastError
0x180042c3a  nop     dword ptr [rax+rax+00h]
0x180042c3f  mov     esi, eax
0x180042c41  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180042c48  test    rcx, rcx
0x180042c4b  jz      short loc_180042CA3
0x180042c4d  lea     rax, [rbp+var_20]
0x180042c51  mov     qword ptr [rsp+70h+dwCreationDisposition], rax
0x180042c56  lea     r9, aFailedToOpenFi; "Failed to open file: {}"
0x180042c5d  mov     r8d, ebx
0x180042c60  xor     edx, edx
0x180042c62  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180042c67  test    esi, esi
0x180042c69  jg      short loc_180042C6F
0x180042c6b  mov     eax, esi
0x180042c6d  jmp     short loc_180042C77
0x180042c6f  movzx   eax, si
0x180042c72  or      eax, 80070000h
0x180042c77  mov     [rbp+var_18], eax
0x180042c7a  lea     rax, [rbp+var_18]
0x180042c7e  mov     qword ptr [rbp+var_30], rax
0x180042c82  lea     rax, [rbp+var_30]
0x180042c86  mov     qword ptr [rsp+70h+dwCreationDisposition], rax; unsigned int
0x180042c8b  lea     r9, a0; ": {0}"
0x180042c92  mov     r8d, ebx
0x180042c95  mov     dl, 1
  ... truncated ...
```
