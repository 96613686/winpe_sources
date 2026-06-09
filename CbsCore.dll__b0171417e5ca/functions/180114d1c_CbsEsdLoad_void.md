# CbsEsdLoad(void)

- ea: `0x180114d1c`
- end: `0x180115253`
- name: `?CbsEsdLoad@@YAJXZ`
- size: `1335`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x180115260`

## callees

- `0x180013250`
- `0x180016d40`
- `0x180042448`
- `0x1800526d4`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x1800ec920`
- `0x1800f648c`
- `0x180114d1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180114e41`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180114e41`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180114d78`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x180114d78`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801150bb`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801150bb`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x180114e1e`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x180114e1e`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180114f2e`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180115005`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180114f2e`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180115005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114f4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011511e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801151ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114f4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115021`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011511e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801151ad`

## string_xrefs

- `0x180114e72`: `Module file path is malformed.`
- `0x1801151cc`: `Failed to get this module's file path.`
- `0x180115145`: `Failed to resolve wimgapi.dll import: {}`
- `0x180115040`: `Failed to load wimgapi.dll from system32.`
- `0x180114f7b`: `Failed to load wimgapi.dll from path: {}`
- `0x180114ece`: `wimgapi.dll`
- `0x180114ffe`: `wimgapi.dll`

## pseudocode

```c
__int64 CbsEsdLoad(void)
{
  signed int LastError; // edi
  unsigned int v1; // eax
  __int64 v2; // rdx
  wchar_t *v3; // rax
  unsigned int v4; // ebx
  int v5; // eax
  const WCHAR *v6; // rbx
  HMODULE Library; // rax
  signed int v8; // edi
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // eax
  unsigned int v12; // edi
  char **v13; // rsi
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // [rsp+20h] [rbp-E0h]
  unsigned int v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpLibFileName; // [rsp+38h] [rbp-C8h] BYREF
  int v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  HMODULE phModule; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v22[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  phModule = 0;
  memset_0(Filename, 0, 0x208u);
  lpLibFileName = 0;
  if ( !GetModuleHandleExW(6u, &word_1803B3DE8, &phModule) )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get this module's handle.");
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      else
        v1 = LastError;
      v22[0] = v1;
      *(_QWORD *)v20 = v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v20);
    }
    if ( LastError )
    {
      v2 = 129;
LABEL_55:
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v2,
             (unsigned int)"onecore\\base\\cbs\\esd\\lib\\cbsesdwrapper.cpp",
             (const char *)(unsigned int)LastError,
             v17);
      goto LABEL_56;
    }
    goto LABEL_39;
  }
  if ( GetModuleFileNameW(phModule, Filename, 0x104u) - 1 > 0x102 )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get this module's file path.");
      if ( LastError > 0 )
        v16 = (unsigned __int16)LastError | 0x80070000;
      else
        v16 = LastError;
      v22[0] = v16;
      *(_QWORD *)v18 = v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v18);
    }
    if ( LastError )
    {
      v2 = 133;
      goto LABEL_55;
    }
LABEL_39:
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
    return 0;
  }
  v3 = wcsrchr(Filename, 0x5Cu);
  if ( !v3 )
  {
    v22[0] = -2147418113;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Module file path is malformed.");
      *(_QWORD *)v20 = v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v20);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecore\\base\\cbs\\esd\\lib\\cbsesdwrapper.cpp",
      (const char *)0x8000FFFFLL,
      v17);
    v4 = -2147418113;
    goto LABEL_56;
  }
  v3[1] = 0;
  v5 = SczAllocConcat2Sz(&lpLibFileName, Filename, L"wimgapi.dll");
  v4 = v5;
  if ( v5 >= 0 )
  {
    v6 = lpLibFileName;
    if ( (unsigned int)DoesFileExist(lpLibFileName, 0) )
    {
      Library = LoadLibraryExW(v6, 0, 8u);
      vhWimgapiDll = Library;
      if ( !Library )
      {
        v8 = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v20 = v6;
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to load wimgapi.dll from path: {}",
            (__int64)v20);
          if ( v8 > 0 )
            v9 = (unsigned __int16)v8 | 0x80070000;
          else
            v9 = v8;
          v22[0] = v9;
          *(_QWORD *)v18 = v22;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v18);
        }
        if ( v8 )
        {
          v10 = 150;
LABEL_25:
          v4 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)v10,
                 (unsigned int)"onecore\\base\\cbs\\esd\\lib\\cbsesdwrapper.cpp",
                 (const char *)(unsigned int)v8,
                 v17);
          CbsEsdUnload();
          goto LABEL_56;
        }
        goto LABEL_47;
      }
    }
    else
    {
      Library = LoadLibraryExW(L"wimgapi.dll", 0, 0x800u);
      vhWimgapiDll = Library;
      if ( !Library )
      {
        v8 = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load wimgapi.dll from system32.");
          if ( v8 > 0 )
            v11 = (unsigned __int16)v8 | 0x80070000;
          else
            v11 = v8;
          v22[0] = v11;
          *(_QWORD *)v18 = v22;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v18);
        }
        if ( v8 )
        {
          v10 = 155;
          goto LABEL_25;
        }
LABEL_47:
        CbsEsdUnload();
        v4 = 0;
        goto LABEL_56;
      }
    }
    v12 = 0;
    while ( 1 )
    {
      v13 = &(&off_1803AF160)[2 * v12];
      *(_QWORD *)v13[1] = GetProcAddress(Library, *v13);
      if ( !*(_QWORD *)v13[1] )
        break;
      if ( ++v12 >= 9 )
      {
        vbValid = 1;
        goto LABEL_39;
      }
      Library = vhWimgapiDll;
    }
    v8 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<char const *>(
        (_DWORD)LogAdapter::g_Logger,
        0,
        3,
        (unsigned int)"Failed to resolve wimgapi.dll import: {}",
        (__int64)v13);
      if ( v8 > 0 )
        v15 = (unsigned __int16)v8 | 0x80070000;
      else
        v15 = v8;
      v22[0] = v15;
      *(_QWORD *)v18 = v22;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v18);
    }
    if ( v8 )
    {
      v10 = 162;
      goto LABEL_25;
    }
    goto LABEL_47;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8F,
    (unsigned int)"onecore\\base\\cbs\\esd\\lib\\cbsesdwrapper.cpp",
    (const char *)(unsigned int)v5,
    v17);
LABEL_56:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
  return v4;
}

```

## disassembly

```asm
0x180114d1c  push    rbp
0x180114d1e  push    rbx
0x180114d1f  push    rsi
0x180114d20  push    rdi
0x180114d21  push    r15
0x180114d23  lea     rbp, [rsp-180h]
0x180114d2b  sub     rsp, 280h
0x180114d32  mov     rax, cs:__security_cookie
0x180114d39  xor     rax, rsp
0x180114d3c  mov     [rbp+1A0h+var_30], rax
0x180114d43  xor     edx, edx; Val
0x180114d45  mov     [rsp+2A0h+phModule], 0
0x180114d4e  mov     r8d, 208h; Size
0x180114d54  lea     rcx, [rsp+2A0h+Filename]; void *
0x180114d59  call    memset_0
0x180114d5e  lea     r8, [rsp+2A0h+phModule]; phModule
0x180114d63  mov     [rsp+2A0h+lpLibFileName], 0
0x180114d6c  lea     rdx, word_1803B3DE8; lpModuleName
0x180114d73  mov     ecx, 6; dwFlags
0x180114d78  call    cs:__imp_GetModuleHandleExW
0x180114d7f  nop     dword ptr [rax+rax+00h]
0x180114d84  test    eax, eax
0x180114d86  jnz     loc_180114E0E
0x180114d8c  call    cs:__imp_GetLastError
0x180114d93  nop     dword ptr [rax+rax+00h]
0x180114d98  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180114d9f  mov     edi, eax
0x180114da1  test    rcx, rcx
0x180114da4  jz      short loc_180114DFC
0x180114da6  mov     ebx, 3
0x180114dab  lea     r9, aFailedToGetThi; "Failed to get this module's handle."
0x180114db2  mov     r8d, ebx
0x180114db5  xor     edx, edx
0x180114db7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180114dbc  test    edi, edi
0x180114dbe  jg      short loc_180114DC4
0x180114dc0  mov     eax, edi
0x180114dc2  jmp     short loc_180114DCC
0x180114dc4  movzx   eax, di
0x180114dc7  or      eax, 80070000h
0x180114dcc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180114dd3  lea     r9, a0; ": {0}"
0x180114dda  mov     [rsp+2A0h+var_250], eax
0x180114dde  mov     r8d, ebx
0x180114de1  lea     rax, [rsp+2A0h+var_250]
0x180114de6  mov     dl, 1
0x180114de8  mov     qword ptr [rsp+2A0h+var_260], rax
0x180114ded  lea     rax, [rsp+2A0h+var_260]
0x180114df2  mov     qword ptr [rsp+2A0h+var_280], rax
0x180114df7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180114dfc  test    edi, edi
0x180114dfe  jz      loc_1801150F4
0x180114e04  mov     edx, 81h
0x180114e09  jmp     loc_18011522A
0x180114e0e  mov     rcx, [rsp+2A0h+phModule]; hModule
0x180114e13  lea     rdx, [rsp+2A0h+Filename]; lpFilename
0x180114e18  mov     r8d, 104h; nSize
0x180114e1e  call    cs:__imp_GetModuleFileNameW
0x180114e25  nop     dword ptr [rax+rax+00h]
0x180114e2a  dec     eax
0x180114e2c  cmp     eax, 102h
0x180114e31  ja      loc_1801151AD
0x180114e37  mov     edx, 5Ch ; '\'; Ch
0x180114e3c  lea     rcx, [rsp+2A0h+Filename]; Str
0x180114e41  call    cs:__imp_wcsrchr
0x180114e48  nop     dword ptr [rax+rax+00h]
0x180114e4d  mov     rcx, rax
0x180114e50  test    rax, rax
0x180114e53  jnz     short loc_180114ECC
0x180114e55  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180114e5c  mov     edi, 8000FFFFh
0x180114e61  mov     [rsp+2A0h+var_250], edi
0x180114e65  test    rcx, rcx
0x180114e68  jz      short loc_180114EAA
0x180114e6a  lea     ebx, [rax+3]
0x180114e6d  xor     edx, edx
0x180114e6f  mov     r8d, ebx
0x180114e72  lea     r9, aModuleFilePath; "Module file path is malformed."
0x180114e79  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180114e7e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180114e85  lea     rax, [rsp+2A0h+var_250]
0x180114e8a  mov     qword ptr [rsp+2A0h+var_260], rax
0x180114e8f  lea     r9, asc_1802EE7AC; ": {}"
0x180114e96  lea     rax, [rsp+2A0h+var_260]
0x180114e9b  mov     r8d, ebx
0x180114e9e  mov     dl, 1
0x180114ea0  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x180114ea5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180114eaa  mov     rcx, [rbp+1A8h]; this
0x180114eb1  lea     r8, aOnecoreBaseCbs_44; "onecore\\base\\cbs\\esd\\lib\\cbsesdwra"...
0x180114eb8  mov     r9d, edi; char *
0x180114ebb  mov     edx, 88h; void *
0x180114ec0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114ec5  mov     ebx, edi
0x180114ec7  jmp     loc_180115242
0x180114ecc  xor     eax, eax
0x180114ece  lea     r8, aWimgapiDll; "wimgapi.dll"
0x180114ed5  mov     [rcx+2], ax
0x180114ed9  lea     rdx, [rsp+2A0h+Filename]
0x180114ede  lea     rcx, [rsp+2A0h+lpLibFileName]
0x180114ee3  call    SczAllocConcat2Sz
0x180114ee8  mov     ebx, eax
0x180114eea  test    eax, eax
0x180114eec  jns     short loc_180114F0E
0x180114eee  mov     rcx, [rbp+1A8h]; this
0x180114ef5  lea     r8, aOnecoreBaseCbs_44; "onecore\\base\\cbs\\esd\\lib\\cbsesdwra"...
0x180114efc  mov     r9d, eax; char *
0x180114eff  mov     edx, 8Fh; void *
0x180114f04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180114f09  jmp     loc_180115242
0x180114f0e  mov     rbx, [rsp+2A0h+lpLibFileName]
0x180114f13  xor     edx, edx
0x180114f15  mov     rcx, rbx
0x180114f18  call    DoesFileExist
0x180114f1d  xor     edx, edx; hFile
0x180114f1f  test    eax, eax
0x180114f21  jz      loc_180114FF8
0x180114f27  lea     r8d, [rdx+8]; dwFlags
0x180114f2b  mov     rcx, rbx; lpLibFileName
0x180114f2e  call    cs:__imp_LoadLibraryExW
0x180114f35  nop     dword ptr [rax+rax+00h]
0x180114f3a  mov     cs:?vhWimgapiDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * vhWimgapiDll
0x180114f41  test    rax, rax
0x180114f44  jnz     loc_1801150A3
0x180114f4a  call    cs:__imp_GetLastError
0x180114f51  nop     dword ptr [rax+rax+00h]
0x180114f56  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180114f5d  mov     edi, eax
0x180114f5f  test    rcx, rcx
0x180114f62  jz      short loc_180114FC9
0x180114f64  mov     qword ptr [rsp+2A0h+var_260], rbx
0x180114f69  lea     rax, [rsp+2A0h+var_260]
0x180114f6e  mov     ebx, 3
0x180114f73  mov     qword ptr [rsp+2A0h+var_280], rax
0x180114f78  mov     r8d, ebx
0x180114f7b  lea     r9, aFailedToLoadWi_1; "Failed to load wimgapi.dll from path: {"...
0x180114f82  xor     edx, edx
0x180114f84  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x180114f89  test    edi, edi
0x180114f8b  jg      short loc_180114F91
0x180114f8d  mov     eax, edi
0x180114f8f  jmp     short loc_180114F99
0x180114f91  movzx   eax, di
0x180114f94  or      eax, 80070000h
0x180114f99  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180114fa0  lea     r9, a0; ": {0}"
0x180114fa7  mov     [rsp+2A0h+var_250], eax
0x180114fab  mov     r8d, ebx
0x180114fae  lea     rax, [rsp+2A0h+var_250]
0x180114fb3  mov     dl, 1
0x180114fb5  mov     qword ptr [rsp+2A0h+var_270], rax
0x180114fba  lea     rax, [rsp+2A0h+var_270]
0x180114fbf  mov     qword ptr [rsp+2A0h+var_280], rax; unsigned int
0x180114fc4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180114fc9  test    edi, edi
0x180114fcb  jz      loc_1801151A1
0x180114fd1  mov     edx, 96h; void *
0x180114fd6  mov     rcx, [rbp+1A8h]; this
0x180114fdd  lea     r8, aOnecoreBaseCbs_44; "onecore\\base\\cbs\\esd\\lib\\cbsesdwra"...
0x180114fe4  mov     r9d, edi; char *
0x180114fe7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180114fec  mov     ebx, eax
0x180114fee  call    ?CbsEsdUnload@@YAXXZ; CbsEsdUnload(void)
0x180114ff3  jmp     loc_180115242
0x180114ff8  mov     r8d, 800h; dwFlags
0x180114ffe  lea     rcx, aWimgapiDll; "wimgapi.dll"
0x180115005  call    cs:__imp_LoadLibraryExW
0x18011500c  nop     dword ptr [rax+rax+00h]
0x180115011  mov     cs:?vhWimgapiDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * vhWimgapiDll
0x180115018  test    rax, rax
0x18011501b  jnz     loc_1801150A3
0x180115021  call    cs:__imp_GetLastError
0x180115028  nop     dword ptr [rax+rax+00h]
0x18011502d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180115034  mov     edi, eax
0x180115036  test    rcx, rcx
0x180115039  jz      short loc_180115091
0x18011503b  mov     ebx, 3
0x180115040  lea     r9, aFailedToLoadWi; "Failed to load wimgapi.dll from system3"...
0x180115047  mov     r8d, ebx
0x18011504a  xor     edx, edx
0x18011504c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180115051  test    edi, edi
0x180115053  jg      short loc_180115059
0x180115055  mov     eax, edi
0x180115057  jmp     short loc_180115061
0x180115059  movzx   eax, di
0x18011505c  or      eax, 80070000h
0x180115061  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180115068  lea     r9, a0; ": {0}"
0x18011506f  mov     [rsp+2A0h+var_250], eax
0x180115073  mov     r8d, ebx
0x180115076  lea     rax, [rsp+2A0h+var_250]
0x18011507b  mov     dl, 1
0x18011507d  mov     qword ptr [rsp+2A0h+var_270], rax
0x180115082  lea     rax, [rsp+2A0h+var_270]
0x180115087  mov     qword ptr [rsp+2A0h+var_280], rax
0x18011508c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180115091  test    edi, edi
0x180115093  jz      loc_1801151A1
0x180115099  mov     edx, 9Bh
0x18011509e  jmp     loc_180114FD6
0x1801150a3  xor     edi, edi
0x1801150a5  lea     r15, off_1803AF160; "WIMCreateFile"
0x1801150ac  mov     ebx, edi
0x1801150ae  mov     rcx, rax; hModule
0x1801150b1  add     rbx, rbx
0x1801150b4  lea     rsi, [r15+rbx*8]
0x1801150b8  mov     rdx, [rsi]; lpProcName
0x1801150bb  call    cs:__imp_GetProcAddress
0x1801150c2  nop     dword ptr [rax+rax+00h]
0x1801150c7  mov     rcx, [r15+rbx*8+8]
0x1801150cc  mov     [rcx], rax
0x1801150cf  mov     rax, [r15+rbx*8+8]
0x1801150d4  cmp     qword ptr [rax], 0
0x1801150d8  jz      short loc_18011511E
0x1801150da  inc     edi
0x1801150dc  cmp     edi, 9
0x1801150df  jnb     short loc_1801150EA
0x1801150e1  mov     rax, cs:?vhWimgapiDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * vhWimgapiDll
0x1801150e8  jmp     short loc_1801150AC
0x1801150ea  mov     cs:?vbValid@@3HA, 1; int vbValid
0x1801150f4  lea     rcx, [rsp+2A0h+lpLibFileName]
0x1801150f9  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1801150fe  xor     eax, eax
0x180115100  mov     rcx, [rbp+1A0h+var_30]
0x180115107  xor     rcx, rsp; StackCookie
0x18011510a  call    __security_check_cookie
0x18011510f  add     rsp, 280h
0x180115116  pop     r15
0x180115118  pop     rdi
0x180115119  pop     rsi
0x18011511a  pop     rbx
0x18011511b  pop     rbp
0x18011511c  retn
0x18011511e  call    cs:__imp_GetLastError
0x180115125  nop     dword ptr [rax+rax+00h]
0x18011512a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180115131  mov     edi, eax
0x180115133  test    rcx, rcx
0x180115136  jz      short loc_180115193
0x180115138  mov     ebx, 3
0x18011513d  mov     qword ptr [rsp+2A0h+var_280], rsi
0x180115142  mov     r8d, ebx
0x180115145  lea     r9, aFailedToResolv_27; "Failed to resolve wimgapi.dll import: {"...
0x18011514c  xor     edx, edx
0x18011514e  call    ??$LogNumObjects@PEBD@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEBD@Z; LogAdapter::Logger::LogNumObjects<char const *>(bool,LogAdapter::LogLevel,char const * const,char const * const &)
0x180115153  test    edi, edi
0x180115155  jg      short loc_18011515B
0x180115157  mov     eax, edi
0x180115159  jmp     short loc_180115163
0x18011515b  movzx   eax, di
0x18011515e  or      eax, 80070000h
0x180115163  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18011516a  lea     r9, a0; ": {0}"
0x180115171  mov     [rsp+2A0h+var_250], eax
0x180115175  mov     r8d, ebx
0x180115178  lea     rax, [rsp+2A0h+var_250]
0x18011517d  mov     dl, 1
0x18011517f  mov     qword ptr [rsp+2A0h+var_270], rax
0x180115184  lea     rax, [rsp+2A0h+var_270]
0x180115189  mov     qword ptr [rsp+2A0h+var_280], rax
0x18011518e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180115193  test    edi, edi
0x180115195  jz      short loc_1801151A1
0x180115197  mov     edx, 0A2h
0x18011519c  jmp     loc_180114FD6
0x1801151a1  call    ?CbsEsdUnload@@YAXXZ; CbsEsdUnload(void)
0x1801151a6  xor     ebx, ebx
0x1801151a8  jmp     loc_180115242
0x1801151ad  call    cs:__imp_GetLastError
0x1801151b4  nop     dword ptr [rax+rax+00h]
0x1801151b9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801151c0  mov     edi, eax
0x1801151c2  test    rcx, rcx
0x1801151c5  jz      short loc_18011521D
0x1801151c7  mov     ebx, 3
0x1801151cc  lea     r9, aFailedToGetThi_0; "Failed to get this module's file path."
0x1801151d3  mov     r8d, ebx
0x1801151d6  xor     edx, edx
0x1801151d8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801151dd  test    edi, edi
0x1801151df  jg      short loc_1801151E5
0x1801151e1  mov     eax, edi
0x1801151e3  jmp     short loc_1801151ED
0x1801151e5  movzx   eax, di
0x1801151e8  or      eax, 80070000h
0x1801151ed  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801151f4  lea     r9, a0; ": {0}"
0x1801151fb  mov     [rsp+2A0h+var_250], eax
0x1801151ff  mov     r8d, ebx
0x180115202  lea     rax, [rsp+2A0h+var_250]
0x180115207  mov     dl, 1
0x180115209  mov     qword ptr [rsp+2A0h+var_270], rax
0x18011520e  lea     rax, [rsp+2A0h+var_270]
0x180115213  mov     qword ptr [rsp+2A0h+var_280], rax; unsigned int
0x180115218  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18011521d  test    edi, edi
0x18011521f  jz      loc_1801150F4
0x180115225  mov     edx, 85h; void *
  ... truncated ...
```
