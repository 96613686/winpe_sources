# CbsEsdLoad(void)

- ea: `0x1800ee104`
- end: `0x1800ee65c`
- name: `?CbsEsdLoad@@YAJXZ`
- size: `1368`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting`

## callers

- `0x1800ee670`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x1800062b8`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x18001a810`
- `0x1800296a4`
- `0x18003cd78`
- `0x180042764`
- `0x180080418`
- `0x1800ed724`
- `0x1800ee104`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800ee241`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800ee241`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee35d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee5da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee35d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee445`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ee5da`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1800ee162`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1800ee162`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ee4db`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ee4db`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800ee341`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800ee42d`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800ee341`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800ee42d`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x1800ee21e`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x1800ee21e`

## string_xrefs

- `0x1800ee2ce`: `wimgapi.dll`
- `0x1800ee426`: `wimgapi.dll`
- `0x1800ee5f9`: `Failed to get this module's file path.`
- `0x1800ee57a`: `Failed to resolve wimgapi.dll import: {}`
- `0x1800ee464`: `Failed to load wimgapi.dll from system32.`
- `0x1800ee38e`: `Failed to load wimgapi.dll from path: {}`
- `0x1800ee272`: `Module file path is malformed.`

## pseudocode

```c
int CbsEsdLoad(void)
{
  signed int LastError; // ebx
  __int64 v1; // rdx
  unsigned int v2; // eax
  __int64 v3; // rdx
  wchar_t *v5; // rax
  int v6; // ebx
  __int64 v7; // rdx
  int v8; // eax
  const WCHAR *v9; // rbx
  HMODULE Library; // rax
  signed int v11; // esi
  __int64 v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // rdx
  int v15; // edi
  __int64 v16; // rdx
  unsigned int v17; // eax
  unsigned int v18; // esi
  char **v19; // r14
  __int64 v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // rdx
  unsigned int v23; // eax
  void *p_lpLibFileName; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpLibFileName; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v26[2]; // [rsp+38h] [rbp-C8h] BYREF
  const WCHAR *v27; // [rsp+40h] [rbp-C0h] BYREF
  HMODULE phModule; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v29[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  phModule = 0;
  memset_0(Filename, 0, 0x208u);
  lpLibFileName = 0;
  if ( !GetModuleHandleExW(6u, &word_180243A50, &phModule) )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get this module's handle.");
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      else
        v2 = LastError;
      v29[0] = v2;
      LOBYTE(v1) = 1;
      lpLibFileName = (LPCWSTR)v29;
      p_lpLibFileName = &lpLibFileName;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v1,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v3 = 129;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v3,
               (unsigned int)"onecore\\base\\cbs\\esd\\lib\\cbsesdwrapper.cpp",
               (const char *)(unsigned int)LastError,
               (unsigned int)p_lpLibFileName);
    }
    return 0;
  }
  if ( GetModuleFileNameW(phModule, Filename, 0x104u) - 1 > 0x102 )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to get this module's file path.");
      if ( LastError > 0 )
        v23 = (unsigned __int16)LastError | 0x80070000;
      else
        v23 = LastError;
      LODWORD(lpLibFileName) = v23;
      LOBYTE(v22) = 1;
      *(_QWORD *)v26 = &lpLibFileName;
      p_lpLibFileName = v26;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v22,
        3,
        ": {0}");
    }
    if ( LastError )
    {
      v3 = 133;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v3,
               (unsigned int)"onecore\\base\\cbs\\esd\\lib\\cbsesdwrapper.cpp",
               (const char *)(unsigned int)LastError,
               (unsigned int)p_lpLibFileName);
    }
    return 0;
  }
  v5 = wcsrchr(Filename, 0x5Cu);
  if ( !v5 )
  {
    v6 = -2147418113;
    v29[0] = -2147418113;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Module file path is malformed.");
      lpLibFileName = (LPCWSTR)v29;
      LOBYTE(v7) = 1;
      p_lpLibFileName = &lpLibFileName;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v7,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecore\\base\\cbs\\esd\\lib\\cbsesdwrapper.cpp",
      (const char *)0x8000FFFFLL,
      (int)p_lpLibFileName);
    return v6;
  }
  v5[1] = 0;
  v8 = SczAllocConcat2Sz(&lpLibFileName, Filename, L"wimgapi.dll");
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8F,
      (unsigned int)"onecore\\base\\cbs\\esd\\lib\\cbsesdwrapper.cpp",
      (const char *)(unsigned int)v8,
      (int)p_lpLibFileName);
    if ( lpLibFileName )
      operator delete((void *)(lpLibFileName - 4));
    return v6;
  }
  v9 = lpLibFileName;
  BYTE1(v29[0]) = 1;
  if ( !(unsigned int)DoesFileExist(lpLibFileName) )
  {
    Library = LoadLibraryExW(L"wimgapi.dll", 0, 0x800u);
    vhWimgapiDll = Library;
    if ( !Library )
    {
      v11 = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to load wimgapi.dll from system32.");
        if ( v11 > 0 )
          v17 = (unsigned __int16)v11 | 0x80070000;
        else
          v17 = v11;
        LODWORD(lpLibFileName) = v17;
        LOBYTE(v16) = 1;
        *(_QWORD *)v26 = &lpLibFileName;
        p_lpLibFileName = v26;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v16,
          3,
          ": {0}");
      }
      if ( v11 )
      {
        v14 = 155;
        goto LABEL_28;
      }
LABEL_44:
      wil::details::lambda_call__CbsEsdLoad_::_2_::_lambda_1___::_lambda_call__CbsEsdLoad_::_2_::_lambda_1___(v29);
      if ( v9 )
        operator delete((void *)(v9 - 4));
      return 0;
    }
LABEL_39:
    v18 = 0;
    while ( 1 )
    {
      v19 = &(&off_18023F570)[2 * v18];
      *(_QWORD *)v19[1] = GetProcAddress(Library, *v19);
      if ( !*(_QWORD *)v19[1] )
        break;
      if ( ++v18 >= 9 )
      {
        vbValid = 1;
        BYTE1(v29[0]) = 0;
        goto LABEL_44;
      }
      Library = vhWimgapiDll;
    }
    v11 = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<char const *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to resolve wimgapi.dll import: {}",
        v19);
      if ( v11 > 0 )
        v21 = (unsigned __int16)v11 | 0x80070000;
      else
        v21 = v11;
      LODWORD(lpLibFileName) = v21;
      LOBYTE(v20) = 1;
      *(_QWORD *)v26 = &lpLibFileName;
      p_lpLibFileName = v26;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v20,
        3,
        ": {0}");
    }
    if ( v11 )
    {
      v14 = 162;
      goto LABEL_28;
    }
    goto LABEL_44;
  }
  Library = LoadLibraryExW(v9, 0, 8u);
  vhWimgapiDll = Library;
  if ( Library )
    goto LABEL_39;
  v11 = GetLastError();
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    v27 = v9;
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      *(_QWORD *)&LogAdapter::g_Logger,
      0,
      3,
      "Failed to load wimgapi.dll from path: {}",
      &v27);
    if ( v11 > 0 )
      v13 = (unsigned __int16)v11 | 0x80070000;
    else
      v13 = v11;
    LODWORD(lpLibFileName) = v13;
    LOBYTE(v12) = 1;
    *(_QWORD *)v26 = &lpLibFileName;
    p_lpLibFileName = v26;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v12,
      3,
      ": {0}");
  }
  if ( !v11 )
    goto LABEL_44;
  v14 = 150;
LABEL_28:
  v15 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\base\\cbs\\esd\\lib\\cbsesdwrapper.cpp",
          (const char *)(unsigned int)v11,
          (unsigned int)p_lpLibFileName);
  wil::details::lambda_call__CbsEsdLoad_::_2_::_lambda_1___::_lambda_call__CbsEsdLoad_::_2_::_lambda_1___(v29);
  if ( v9 )
    operator delete((void *)(v9 - 4));
  return v15;
}

```

## disassembly

```asm
0x1800ee104  push    rbp
0x1800ee106  push    rbx
0x1800ee107  push    rsi
0x1800ee108  push    rdi
0x1800ee109  push    r12
0x1800ee10b  push    r14
0x1800ee10d  lea     rbp, [rsp-188h]
0x1800ee115  sub     rsp, 288h
0x1800ee11c  mov     rax, cs:__security_cookie
0x1800ee123  xor     rax, rsp
0x1800ee126  mov     [rbp+1B0h+var_40], rax
0x1800ee12d  xor     edx, edx; Val
0x1800ee12f  mov     [rsp+2B0h+phModule], 0
0x1800ee138  mov     r8d, 208h; Size
0x1800ee13e  lea     rcx, [rsp+2B0h+Filename]; void *
0x1800ee143  call    memset_0
0x1800ee148  lea     r8, [rsp+2B0h+phModule]; phModule
0x1800ee14d  mov     [rsp+2B0h+lpLibFileName], 0
0x1800ee156  lea     rdx, word_180243A50; lpModuleName
0x1800ee15d  mov     ecx, 6; dwFlags
0x1800ee162  call    cs:__imp_GetModuleHandleExW
0x1800ee169  nop     dword ptr [rax+rax+00h]
0x1800ee16e  test    eax, eax
0x1800ee170  jnz     loc_1800EE20E
0x1800ee176  call    cs:__imp_GetLastError
0x1800ee17d  nop     dword ptr [rax+rax+00h]
0x1800ee182  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ee189  mov     ebx, eax
0x1800ee18b  test    rcx, rcx
0x1800ee18e  jz      short loc_1800EE1E6
0x1800ee190  mov     edi, 3
0x1800ee195  lea     r9, aFailedToGetThi; "Failed to get this module's handle."
0x1800ee19c  mov     r8d, edi
0x1800ee19f  xor     edx, edx
0x1800ee1a1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800ee1a6  test    ebx, ebx
0x1800ee1a8  jg      short loc_1800EE1AE
0x1800ee1aa  mov     eax, ebx
0x1800ee1ac  jmp     short loc_1800EE1B6
0x1800ee1ae  movzx   eax, bx
0x1800ee1b1  or      eax, 80070000h
0x1800ee1b6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ee1bd  lea     r9, a0; ": {0}"
0x1800ee1c4  mov     [rsp+2B0h+var_260], eax
0x1800ee1c8  mov     r8d, edi
0x1800ee1cb  lea     rax, [rsp+2B0h+var_260]
0x1800ee1d0  mov     dl, 1
0x1800ee1d2  mov     [rsp+2B0h+lpLibFileName], rax
0x1800ee1d7  lea     rax, [rsp+2B0h+lpLibFileName]
0x1800ee1dc  mov     qword ptr [rsp+2B0h+var_290], rax; unsigned int
0x1800ee1e1  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ee1e6  test    ebx, ebx
0x1800ee1e8  jz      loc_1800EE531
0x1800ee1ee  mov     edx, 81h; void *
0x1800ee1f3  mov     rcx, [rbp+1B8h]; this
0x1800ee1fa  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\esd\\lib\\cbsesdwra"...
0x1800ee201  mov     r9d, ebx; char *
0x1800ee204  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ee209  jmp     loc_1800EE533
0x1800ee20e  mov     rcx, [rsp+2B0h+phModule]; hModule
0x1800ee213  lea     rdx, [rsp+2B0h+Filename]; lpFilename
0x1800ee218  mov     r8d, 104h; nSize
0x1800ee21e  call    cs:__imp_GetModuleFileNameW
0x1800ee225  nop     dword ptr [rax+rax+00h]
0x1800ee22a  dec     eax
0x1800ee22c  cmp     eax, 102h
0x1800ee231  ja      loc_1800EE5DA
0x1800ee237  mov     edx, 5Ch ; '\'; Ch
0x1800ee23c  lea     rcx, [rsp+2B0h+Filename]; Str
0x1800ee241  call    cs:__imp_wcsrchr
0x1800ee248  nop     dword ptr [rax+rax+00h]
0x1800ee24d  mov     rcx, rax
0x1800ee250  test    rax, rax
0x1800ee253  jnz     short loc_1800EE2CC
0x1800ee255  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ee25c  mov     ebx, 8000FFFFh
0x1800ee261  mov     [rsp+2B0h+var_260], ebx
0x1800ee265  test    rcx, rcx
0x1800ee268  jz      short loc_1800EE2AA
0x1800ee26a  lea     edi, [rax+3]
0x1800ee26d  xor     edx, edx
0x1800ee26f  mov     r8d, edi
0x1800ee272  lea     r9, aModuleFilePath; "Module file path is malformed."
0x1800ee279  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800ee27e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ee285  lea     rax, [rsp+2B0h+var_260]
0x1800ee28a  mov     [rsp+2B0h+lpLibFileName], rax
0x1800ee28f  lea     r9, asc_1801CAFB4; ": {}"
0x1800ee296  lea     rax, [rsp+2B0h+lpLibFileName]
0x1800ee29b  mov     r8d, edi
0x1800ee29e  mov     dl, 1
0x1800ee2a0  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x1800ee2a5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ee2aa  mov     rcx, [rbp+1B8h]; this
0x1800ee2b1  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\esd\\lib\\cbsesdwra"...
0x1800ee2b8  mov     r9d, ebx; char *
0x1800ee2bb  mov     edx, 88h; void *
0x1800ee2c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ee2c5  mov     eax, ebx
0x1800ee2c7  jmp     loc_1800EE533
0x1800ee2cc  xor     eax, eax
0x1800ee2ce  lea     r8, aWimgapiDll; "wimgapi.dll"
0x1800ee2d5  mov     [rcx+2], ax
0x1800ee2d9  lea     rdx, [rsp+2B0h+Filename]
0x1800ee2de  lea     rcx, [rsp+2B0h+lpLibFileName]
0x1800ee2e3  call    SczAllocConcat2Sz
0x1800ee2e8  mov     ebx, eax
0x1800ee2ea  test    eax, eax
0x1800ee2ec  jns     short loc_1800EE31E
0x1800ee2ee  mov     rcx, [rbp+1B8h]; this
0x1800ee2f5  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\esd\\lib\\cbsesdwra"...
0x1800ee2fc  mov     r9d, eax; char *
0x1800ee2ff  mov     edx, 8Fh; void *
0x1800ee304  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ee309  mov     rcx, [rsp+2B0h+lpLibFileName]
0x1800ee30e  test    rcx, rcx
0x1800ee311  jz      short loc_1800EE2C5
0x1800ee313  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800ee317  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ee31c  jmp     short loc_1800EE2C5
0x1800ee31e  mov     rbx, [rsp+2B0h+lpLibFileName]
0x1800ee323  mov     rcx, rbx
0x1800ee326  mov     byte ptr [rsp+2B0h+var_260+1], 1
0x1800ee32b  call    DoesFileExist
0x1800ee330  xor     edx, edx; hFile
0x1800ee332  test    eax, eax
0x1800ee334  jz      loc_1800EE420
0x1800ee33a  lea     r8d, [rdx+8]; dwFlags
0x1800ee33e  mov     rcx, rbx; lpLibFileName
0x1800ee341  call    cs:__imp_LoadLibraryExW
0x1800ee348  nop     dword ptr [rax+rax+00h]
0x1800ee34d  mov     cs:?vhWimgapiDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * vhWimgapiDll
0x1800ee354  test    rax, rax
0x1800ee357  jnz     loc_1800EE4C3
0x1800ee35d  call    cs:__imp_GetLastError
0x1800ee364  nop     dword ptr [rax+rax+00h]
0x1800ee369  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ee370  mov     esi, eax
0x1800ee372  test    rcx, rcx
0x1800ee375  jz      short loc_1800EE3DC
0x1800ee377  lea     rax, [rsp+2B0h+var_270]
0x1800ee37c  mov     [rsp+2B0h+var_270], rbx
0x1800ee381  mov     edi, 3
0x1800ee386  mov     qword ptr [rsp+2B0h+var_290], rax
0x1800ee38b  mov     r8d, edi
0x1800ee38e  lea     r9, aFailedToLoadWi_0; "Failed to load wimgapi.dll from path: {"...
0x1800ee395  xor     edx, edx
0x1800ee397  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800ee39c  test    esi, esi
0x1800ee39e  jg      short loc_1800EE3A4
0x1800ee3a0  mov     eax, esi
0x1800ee3a2  jmp     short loc_1800EE3AC
0x1800ee3a4  movzx   eax, si
0x1800ee3a7  or      eax, 80070000h
0x1800ee3ac  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ee3b3  lea     r9, a0; ": {0}"
0x1800ee3ba  mov     dword ptr [rsp+2B0h+lpLibFileName], eax
0x1800ee3be  mov     r8d, edi
0x1800ee3c1  lea     rax, [rsp+2B0h+lpLibFileName]
0x1800ee3c6  mov     dl, 1
0x1800ee3c8  mov     qword ptr [rsp+2B0h+var_278], rax
0x1800ee3cd  lea     rax, [rsp+2B0h+var_278]
0x1800ee3d2  mov     qword ptr [rsp+2B0h+var_290], rax; unsigned int
0x1800ee3d7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ee3dc  test    esi, esi
0x1800ee3de  jz      loc_1800EE519
0x1800ee3e4  mov     edx, 96h; void *
0x1800ee3e9  mov     rcx, [rbp+1B8h]; this
0x1800ee3f0  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\esd\\lib\\cbsesdwra"...
0x1800ee3f7  mov     r9d, esi; char *
0x1800ee3fa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ee3ff  lea     rcx, [rsp+2B0h+var_260]
0x1800ee404  mov     edi, eax
0x1800ee406  call    wil__details__lambda_call__CbsEsdLoad____2____lambda_1______lambda_call__CbsEsdLoad____2____lambda_1___
0x1800ee40b  test    rbx, rbx
0x1800ee40e  jz      short loc_1800EE419
0x1800ee410  lea     rcx, [rbx-8]; Block
0x1800ee414  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ee419  mov     eax, edi
0x1800ee41b  jmp     loc_1800EE533
0x1800ee420  mov     r8d, 800h; dwFlags
0x1800ee426  lea     rcx, aWimgapiDll; "wimgapi.dll"
0x1800ee42d  call    cs:__imp_LoadLibraryExW
0x1800ee434  nop     dword ptr [rax+rax+00h]
0x1800ee439  mov     cs:?vhWimgapiDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * vhWimgapiDll
0x1800ee440  test    rax, rax
0x1800ee443  jnz     short loc_1800EE4C3
0x1800ee445  call    cs:__imp_GetLastError
0x1800ee44c  nop     dword ptr [rax+rax+00h]
0x1800ee451  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ee458  mov     esi, eax
0x1800ee45a  test    rcx, rcx
0x1800ee45d  jz      short loc_1800EE4B5
0x1800ee45f  mov     edi, 3
0x1800ee464  lea     r9, aFailedToLoadWi; "Failed to load wimgapi.dll from system3"...
0x1800ee46b  mov     r8d, edi
0x1800ee46e  xor     edx, edx
0x1800ee470  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800ee475  test    esi, esi
0x1800ee477  jg      short loc_1800EE47D
0x1800ee479  mov     eax, esi
0x1800ee47b  jmp     short loc_1800EE485
0x1800ee47d  movzx   eax, si
0x1800ee480  or      eax, 80070000h
0x1800ee485  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ee48c  lea     r9, a0; ": {0}"
0x1800ee493  mov     dword ptr [rsp+2B0h+lpLibFileName], eax
0x1800ee497  mov     r8d, edi
0x1800ee49a  lea     rax, [rsp+2B0h+lpLibFileName]
0x1800ee49f  mov     dl, 1
0x1800ee4a1  mov     qword ptr [rsp+2B0h+var_278], rax
0x1800ee4a6  lea     rax, [rsp+2B0h+var_278]
0x1800ee4ab  mov     qword ptr [rsp+2B0h+var_290], rax
0x1800ee4b0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ee4b5  test    esi, esi
0x1800ee4b7  jz      short loc_1800EE519
0x1800ee4b9  mov     edx, 9Bh
0x1800ee4be  jmp     loc_1800EE3E9
0x1800ee4c3  xor     esi, esi
0x1800ee4c5  lea     r12, off_18023F570; "WIMCreateFile"
0x1800ee4cc  mov     edi, esi
0x1800ee4ce  mov     rcx, rax; hModule
0x1800ee4d1  add     rdi, rdi
0x1800ee4d4  lea     r14, [r12+rdi*8]
0x1800ee4d8  mov     rdx, [r14]; lpProcName
0x1800ee4db  call    cs:__imp_GetProcAddress
0x1800ee4e2  nop     dword ptr [rax+rax+00h]
0x1800ee4e7  mov     rcx, [r12+rdi*8+8]
0x1800ee4ec  mov     [rcx], rax
0x1800ee4ef  mov     rax, [r12+rdi*8+8]
0x1800ee4f4  cmp     qword ptr [rax], 0
0x1800ee4f8  jz      short loc_1800EE553
0x1800ee4fa  inc     esi
0x1800ee4fc  cmp     esi, 9
0x1800ee4ff  jnb     short loc_1800EE50A
0x1800ee501  mov     rax, cs:?vhWimgapiDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * vhWimgapiDll
0x1800ee508  jmp     short loc_1800EE4CC
0x1800ee50a  mov     cs:?vbValid@@3HA, 1; int vbValid
0x1800ee514  mov     byte ptr [rsp+2B0h+var_260+1], 0
0x1800ee519  lea     rcx, [rsp+2B0h+var_260]
0x1800ee51e  call    wil__details__lambda_call__CbsEsdLoad____2____lambda_1______lambda_call__CbsEsdLoad____2____lambda_1___
0x1800ee523  test    rbx, rbx
0x1800ee526  jz      short loc_1800EE531
0x1800ee528  lea     rcx, [rbx-8]; Block
0x1800ee52c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ee531  xor     eax, eax
0x1800ee533  mov     rcx, [rbp+1B0h+var_40]
0x1800ee53a  xor     rcx, rsp; StackCookie
0x1800ee53d  call    __security_check_cookie
0x1800ee542  add     rsp, 288h
0x1800ee549  pop     r14
0x1800ee54b  pop     r12
0x1800ee54d  pop     rdi
0x1800ee54e  pop     rsi
0x1800ee54f  pop     rbx
0x1800ee550  pop     rbp
0x1800ee551  retn
0x1800ee553  call    cs:__imp_GetLastError
0x1800ee55a  nop     dword ptr [rax+rax+00h]
0x1800ee55f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ee566  mov     esi, eax
0x1800ee568  test    rcx, rcx
0x1800ee56b  jz      short loc_1800EE5C8
0x1800ee56d  mov     edi, 3
0x1800ee572  mov     qword ptr [rsp+2B0h+var_290], r14
0x1800ee577  mov     r8d, edi
0x1800ee57a  lea     r9, aFailedToResolv; "Failed to resolve wimgapi.dll import: {"...
0x1800ee581  xor     edx, edx
0x1800ee583  call    ??$LogNumObjects@PEBD@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEBD@Z; LogAdapter::Logger::LogNumObjects<char const *>(bool,LogAdapter::LogLevel,char const * const,char const * const &)
0x1800ee588  test    esi, esi
0x1800ee58a  jg      short loc_1800EE590
0x1800ee58c  mov     eax, esi
0x1800ee58e  jmp     short loc_1800EE598
0x1800ee590  movzx   eax, si
0x1800ee593  or      eax, 80070000h
0x1800ee598  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ee59f  lea     r9, a0; ": {0}"
0x1800ee5a6  mov     dword ptr [rsp+2B0h+lpLibFileName], eax
0x1800ee5aa  mov     r8d, edi
0x1800ee5ad  lea     rax, [rsp+2B0h+lpLibFileName]
0x1800ee5b2  mov     dl, 1
0x1800ee5b4  mov     qword ptr [rsp+2B0h+var_278], rax
0x1800ee5b9  lea     rax, [rsp+2B0h+var_278]
0x1800ee5be  mov     qword ptr [rsp+2B0h+var_290], rax
0x1800ee5c3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800ee5c8  test    esi, esi
0x1800ee5ca  jz      loc_1800EE519
0x1800ee5d0  mov     edx, 0A2h
0x1800ee5d5  jmp     loc_1800EE3E9
0x1800ee5da  call    cs:__imp_GetLastError
0x1800ee5e1  nop     dword ptr [rax+rax+00h]
0x1800ee5e6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800ee5ed  mov     ebx, eax
0x1800ee5ef  test    rcx, rcx
0x1800ee5f2  jz      short loc_1800EE64A
0x1800ee5f4  mov     edi, 3
0x1800ee5f9  lea     r9, aFailedToGetThi_0; "Failed to get this module's file path."
0x1800ee600  mov     r8d, edi
0x1800ee603  xor     edx, edx
0x1800ee605  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
  ... truncated ...
```
