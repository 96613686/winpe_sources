# MoveToCbsTemp

- ea: `0x18003f8a4`
- end: `0x18003fc0e`
- name: `MoveToCbsTemp`
- size: `874`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180040bb4`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x1800062b8`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x1800296a4`
- `0x180036824`
- `0x18003d278`
- `0x18003ddc8`
- `0x18003e9cc`
- `0x18003f8a4`
- `0x180046050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fb3d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003fa35`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003fa35`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003fa5f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003fa5f`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003fb29`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18003fb29`

## string_xrefs

- `0x18003f9c7`: `CbsTemp`
- `0x18003f9ed`: `Failed to get CbsTemp dir`
- `0x18003f90f`: `No directory specified`
- `0x18003fb5c`: `Failed to move to CbsTemp`
- `0x18003fb10`: `Moving directory from {} to {}`

## pseudocode

```c
__int64 __fastcall MoveToCbsTemp(const WCHAR *a1, __int64 a2, const WCHAR **a3)
{
  HRESULT v6; // ebx
  __int64 v7; // rdx
  __int64 v9; // rdx
  int WindowsDirectory; // eax
  __int64 v11; // rdx
  __int64 v12; // rdx
  const WCHAR *v13; // rbx
  signed int LastError; // edi
  __int64 v15; // rdx
  unsigned int v16; // eax
  unsigned int v17; // edi
  void *p_lpNewFileName; // [rsp+20h] [rbp-59h]
  LPCWSTR lpNewFileName; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v20[2]; // [rsp+38h] [rbp-41h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+40h] [rbp-39h] BYREF
  int v22; // [rsp+48h] [rbp-31h] BYREF
  GUID pguid; // [rsp+50h] [rbp-29h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  lpExistingFileName = a1;
  lpNewFileName = 0;
  pguid = 0;
  memset_0(sz, 0, 0x4Eu);
  if ( !a1 )
  {
    v6 = -2147024809;
    v22 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No directory specified");
      lpNewFileName = (LPCWSTR)&v22;
      LOBYTE(v7) = 1;
      p_lpNewFileName = &lpNewFileName;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v7,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A4,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)0x80070057LL,
      (int)p_lpNewFileName);
    return (unsigned int)v6;
  }
  if ( *a3 )
  {
    operator delete((void *)(*a3 - 4));
    *a3 = 0;
  }
  if ( a2 )
  {
    v6 = SczAllocFromSz(&lpNewFileName);
    if ( v6 < 0 )
    {
      v9 = 681;
      goto LABEL_11;
    }
  }
  else
  {
    WindowsDirectory = PathGetWindowsDirectory((LPWSTR *)&lpNewFileName, (__int64)L"CbsTemp");
    v6 = WindowsDirectory;
    if ( WindowsDirectory < 0 )
    {
      v22 = WindowsDirectory;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get CbsTemp dir");
        *(_QWORD *)v20 = &v22;
        LOBYTE(v11) = 1;
        p_lpNewFileName = v20;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v11,
          3,
          ": {}");
      }
      v9 = 687;
      goto LABEL_11;
    }
  }
  v6 = CoCreateGuid(&pguid);
  if ( v6 < 0 )
  {
    v9 = 690;
    goto LABEL_11;
  }
  if ( !StringFromGUID2(&pguid, sz, 39) )
  {
    v6 = -2147418113;
    v22 = -2147418113;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to convert guid to string");
      *(_QWORD *)v20 = &v22;
      LOBYTE(v12) = 1;
      p_lpNewFileName = v20;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v12,
        3,
        ": {}");
    }
    v9 = 692;
    goto LABEL_11;
  }
  v6 = SczEnsureBackslashTerminated(&lpNewFileName);
  if ( v6 < 0 )
  {
    v9 = 694;
    goto LABEL_11;
  }
  v6 = SczAllocConcatSz(&lpNewFileName, sz);
  if ( v6 < 0 )
  {
    v9 = 695;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)(unsigned int)v6,
      (int)p_lpNewFileName);
    if ( lpNewFileName )
      operator delete((void *)(lpNewFileName - 4));
    return (unsigned int)v6;
  }
  v13 = lpNewFileName;
  *(_QWORD *)v20 = lpNewFileName;
  LogAdapter::TraceInfo<wchar_t const *,wchar_t *>("Moving directory from {} to {}", &lpExistingFileName, v20);
  if ( MoveFileExW(lpExistingFileName, v13, 1u) )
  {
    *a3 = v13;
    return 0;
  }
  LastError = GetLastError();
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to move to CbsTemp");
    if ( LastError > 0 )
      v16 = (unsigned __int16)LastError | 0x80070000;
    else
      v16 = LastError;
    v22 = v16;
    LOBYTE(v15) = 1;
    *(_QWORD *)v20 = &v22;
    p_lpNewFileName = v20;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v15,
      3,
      ": {0}");
  }
  if ( !LastError )
  {
    if ( v13 )
      operator delete((void *)(v13 - 4));
    return 0;
  }
  v17 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x2BB,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
          (const char *)(unsigned int)LastError,
          (unsigned int)p_lpNewFileName);
  if ( v13 )
    operator delete((void *)(v13 - 4));
  return v17;
}

```

## disassembly

```asm
0x18003f8a4  mov     [rsp-8+arg_18], rbx
0x18003f8a9  push    rbp
0x18003f8aa  push    rsi
0x18003f8ab  push    rdi
0x18003f8ac  lea     rbp, [rsp-47h]
0x18003f8b1  sub     rsp, 0C0h
0x18003f8b8  mov     rax, cs:__security_cookie
0x18003f8bf  xor     rax, rsp
0x18003f8c2  mov     [rbp+57h+var_20], rax
0x18003f8c6  mov     rsi, rdx
0x18003f8c9  mov     [rbp+57h+lpExistingFileName], rcx
0x18003f8cd  xor     edx, edx; Val
0x18003f8cf  mov     [rbp+57h+lpNewFileName], 0
0x18003f8d7  mov     rdi, r8
0x18003f8da  mov     rbx, rcx
0x18003f8dd  xorps   xmm0, xmm0
0x18003f8e0  lea     rcx, [rbp+57h+sz]; void *
0x18003f8e4  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x18003f8e8  lea     r8d, [rdx+4Eh]; Size
0x18003f8ec  call    memset_0
0x18003f8f1  test    rbx, rbx
0x18003f8f4  jnz     short loc_18003F968
0x18003f8f6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18003f8fd  mov     ebx, 80070057h
0x18003f902  mov     [rbp+57h+var_88], ebx
0x18003f905  test    rcx, rcx
0x18003f908  jz      short loc_18003F949
0x18003f90a  mov     esi, 3
0x18003f90f  lea     r9, aNoDirectorySpe; "No directory specified"
0x18003f916  mov     r8d, esi
0x18003f919  xor     edx, edx
0x18003f91b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18003f920  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18003f927  lea     rax, [rbp+57h+var_88]
0x18003f92b  mov     [rbp+57h+lpNewFileName], rax
0x18003f92f  lea     r9, asc_1801CAFB4; ": {}"
0x18003f936  lea     rax, [rbp+57h+lpNewFileName]
0x18003f93a  mov     r8d, esi
0x18003f93d  mov     dl, 1
0x18003f93f  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18003f944  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18003f949  mov     rcx, [rbp+5Fh]; this
0x18003f94d  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18003f954  mov     r9d, ebx; char *
0x18003f957  mov     edx, 2A4h; void *
0x18003f95c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f961  mov     eax, ebx
0x18003f963  jmp     loc_18003FBEE
0x18003f968  mov     rcx, [rdi]
0x18003f96b  test    rcx, rcx
0x18003f96e  jz      short loc_18003F980
0x18003f970  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18003f974  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003f979  mov     qword ptr [rdi], 0
0x18003f980  lea     rcx, [rbp+57h+lpNewFileName]
0x18003f984  test    rsi, rsi
0x18003f987  jz      short loc_18003F9C7
0x18003f989  mov     rdx, rsi
0x18003f98c  call    SczAllocFromSz
0x18003f991  mov     ebx, eax
0x18003f993  test    eax, eax
0x18003f995  jns     loc_18003FA31
0x18003f99b  mov     edx, 2A9h; void *
0x18003f9a0  mov     rcx, [rbp+5Fh]; this
0x18003f9a4  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18003f9ab  mov     r9d, ebx; char *
0x18003f9ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f9b3  mov     rcx, [rbp+57h+lpNewFileName]
0x18003f9b7  test    rcx, rcx
0x18003f9ba  jz      short loc_18003F961
0x18003f9bc  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18003f9c0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003f9c5  jmp     short loc_18003F961
0x18003f9c7  lea     rdx, aCbstemp; "CbsTemp"
0x18003f9ce  call    PathGetWindowsDirectory
0x18003f9d3  mov     ebx, eax
0x18003f9d5  test    eax, eax
0x18003f9d7  jns     short loc_18003FA31
0x18003f9d9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18003f9e0  mov     [rbp+57h+var_88], eax
0x18003f9e3  test    rcx, rcx
0x18003f9e6  jz      short loc_18003FA27
0x18003f9e8  mov     esi, 3
0x18003f9ed  lea     r9, aFailedToGetCbs_1; "Failed to get CbsTemp dir"
0x18003f9f4  mov     r8d, esi
0x18003f9f7  xor     edx, edx
0x18003f9f9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18003f9fe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18003fa05  lea     rax, [rbp+57h+var_88]
0x18003fa09  mov     qword ptr [rbp+57h+var_98], rax
0x18003fa0d  lea     r9, asc_1801CAFB4; ": {}"
0x18003fa14  lea     rax, [rbp+57h+var_98]
0x18003fa18  mov     r8d, esi
0x18003fa1b  mov     dl, 1
0x18003fa1d  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18003fa22  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18003fa27  mov     edx, 2AFh
0x18003fa2c  jmp     loc_18003F9A0
0x18003fa31  lea     rcx, [rbp+57h+pguid]; pguid
0x18003fa35  call    cs:__imp_CoCreateGuid
0x18003fa3c  nop     dword ptr [rax+rax+00h]
0x18003fa41  mov     ebx, eax
0x18003fa43  test    eax, eax
0x18003fa45  jns     short loc_18003FA51
0x18003fa47  mov     edx, 2B2h
0x18003fa4c  jmp     loc_18003F9A0
0x18003fa51  mov     r8d, 27h ; '''; cchMax
0x18003fa57  lea     rdx, [rbp+57h+sz]; lpsz
0x18003fa5b  lea     rcx, [rbp+57h+pguid]; rguid
0x18003fa5f  call    cs:__imp_StringFromGUID2
0x18003fa66  nop     dword ptr [rax+rax+00h]
0x18003fa6b  test    eax, eax
0x18003fa6d  jnz     short loc_18003FACA
0x18003fa6f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18003fa76  mov     ebx, 8000FFFFh
0x18003fa7b  mov     [rbp+57h+var_88], ebx
0x18003fa7e  test    rcx, rcx
0x18003fa81  jz      short loc_18003FAC0
0x18003fa83  lea     esi, [rax+3]
0x18003fa86  xor     edx, edx
0x18003fa88  mov     r8d, esi
0x18003fa8b  lea     r9, aFailedToConver_1; "Failed to convert guid to string"
0x18003fa92  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18003fa97  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18003fa9e  lea     rax, [rbp+57h+var_88]
0x18003faa2  mov     qword ptr [rbp+57h+var_98], rax
0x18003faa6  lea     r9, asc_1801CAFB4; ": {}"
0x18003faad  lea     rax, [rbp+57h+var_98]
0x18003fab1  mov     r8d, esi
0x18003fab4  mov     dl, 1
0x18003fab6  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18003fabb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18003fac0  mov     edx, 2B4h
0x18003fac5  jmp     loc_18003F9A0
0x18003faca  lea     rcx, [rbp+57h+lpNewFileName]
0x18003face  call    SczEnsureBackslashTerminated
0x18003fad3  mov     ebx, eax
0x18003fad5  test    eax, eax
0x18003fad7  jns     short loc_18003FAE3
0x18003fad9  mov     edx, 2B6h
0x18003fade  jmp     loc_18003F9A0
0x18003fae3  lea     rdx, [rbp+57h+sz]
0x18003fae7  lea     rcx, [rbp+57h+lpNewFileName]
0x18003faeb  call    SczAllocConcatSz
0x18003faf0  mov     ebx, eax
0x18003faf2  test    eax, eax
0x18003faf4  jns     short loc_18003FB00
0x18003faf6  mov     edx, 2B7h
0x18003fafb  jmp     loc_18003F9A0
0x18003fb00  mov     rbx, [rbp+57h+lpNewFileName]
0x18003fb04  lea     r8, [rbp+57h+var_98]
0x18003fb08  lea     rdx, [rbp+57h+lpExistingFileName]
0x18003fb0c  mov     qword ptr [rbp+57h+var_98], rbx
0x18003fb10  lea     rcx, aMovingDirector; "Moving directory from {} to {}"
0x18003fb17  call    ??$TraceInfo@PEB_WPEA_W@LogAdapter@@YAXQEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::TraceInfo<wchar_t const *,wchar_t *>(char const * const,wchar_t const * const &,wchar_t * const &)
0x18003fb1c  mov     rcx, [rbp+57h+lpExistingFileName]; lpExistingFileName
0x18003fb20  mov     r8d, 1; dwFlags
0x18003fb26  mov     rdx, rbx; lpNewFileName
0x18003fb29  call    cs:__imp_MoveFileExW
0x18003fb30  nop     dword ptr [rax+rax+00h]
0x18003fb35  test    eax, eax
0x18003fb37  jnz     loc_18003FBE9
0x18003fb3d  call    cs:__imp_GetLastError
0x18003fb44  nop     dword ptr [rax+rax+00h]
0x18003fb49  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18003fb50  mov     edi, eax
0x18003fb52  test    rcx, rcx
0x18003fb55  jz      short loc_18003FBA9
0x18003fb57  mov     esi, 3
0x18003fb5c  lea     r9, aFailedToMoveTo_1; "Failed to move to CbsTemp"
0x18003fb63  mov     r8d, esi
0x18003fb66  xor     edx, edx
0x18003fb68  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18003fb6d  test    edi, edi
0x18003fb6f  jg      short loc_18003FB75
0x18003fb71  mov     eax, edi
0x18003fb73  jmp     short loc_18003FB7D
0x18003fb75  movzx   eax, di
0x18003fb78  or      eax, 80070000h
0x18003fb7d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18003fb84  lea     r9, a0; ": {0}"
0x18003fb8b  mov     [rbp+57h+var_88], eax
0x18003fb8e  mov     r8d, esi
0x18003fb91  lea     rax, [rbp+57h+var_88]
0x18003fb95  mov     dl, 1
0x18003fb97  mov     qword ptr [rbp+57h+var_98], rax
0x18003fb9b  lea     rax, [rbp+57h+var_98]
0x18003fb9f  mov     qword ptr [rsp+0D0h+var_B0], rax; unsigned int
0x18003fba4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18003fba9  test    edi, edi
0x18003fbab  jz      short loc_18003FBD9
0x18003fbad  mov     rcx, [rbp+5Fh]; this
0x18003fbb1  lea     r8, aOnecoreBaseCbs_13; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x18003fbb8  mov     r9d, edi; char *
0x18003fbbb  mov     edx, 2BBh; void *
0x18003fbc0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003fbc5  mov     edi, eax
0x18003fbc7  test    rbx, rbx
0x18003fbca  jz      short loc_18003FBD5
0x18003fbcc  lea     rcx, [rbx-8]; Block
0x18003fbd0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003fbd5  mov     eax, edi
0x18003fbd7  jmp     short loc_18003FBEE
0x18003fbd9  test    rbx, rbx
0x18003fbdc  jz      short loc_18003FBEC
0x18003fbde  lea     rcx, [rbx-8]; Block
0x18003fbe2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003fbe7  jmp     short loc_18003FBEC
0x18003fbe9  mov     [rdi], rbx
0x18003fbec  xor     eax, eax
0x18003fbee  mov     rcx, [rbp+57h+var_20]
0x18003fbf2  xor     rcx, rsp; StackCookie
0x18003fbf5  call    __security_check_cookie
0x18003fbfa  mov     rbx, [rsp+0D0h+arg_18]
0x18003fc02  add     rsp, 0C0h
0x18003fc09  pop     rdi
0x18003fc0a  pop     rsi
0x18003fc0b  pop     rbp
0x18003fc0c  retn
```
