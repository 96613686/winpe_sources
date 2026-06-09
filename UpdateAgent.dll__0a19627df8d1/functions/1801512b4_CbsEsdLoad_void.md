# CbsEsdLoad(void)

- ea: `0x1801512b4`
- end: `0x1801518c3`
- name: `?CbsEsdLoad@@YAJXZ`
- size: `1551`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x1801518d0`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x180006a18`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000bd00`
- `0x18000c4c4`
- `0x18008b38c`
- `0x18008b3ec`
- `0x1801488f0`
- `0x18014a060`
- `0x180150760`
- `0x1801512b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801513fc`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801513fc`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801516ed`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1801516ed`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x1801513d9`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x1801513d9`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801514ff`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801515f9`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801514ff`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1801515f9`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18015131b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x18015131b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015132f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015151b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180151615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015173b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015180f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015132f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015151b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180151615`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015173b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015180f`

## string_xrefs

- `0x18015148e`: `wimgapi.dll`
- `0x1801515f2`: `wimgapi.dll`
- `0x180151544`: `Failed to load wimgapi.dll from path: {}`
- `0x180151829`: `Failed to get this module's file path.`
- `0x180151425`: `Module file path is malformed.`
- `0x18015162f`: `Failed to load wimgapi.dll from system32.`
- `0x18015175a`: `Failed to resolve wimgapi.dll import: {}`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int CbsEsdLoad(void)
{
  signed int LastError; // ebx
  unsigned int v1; // eax
  wchar_t *v3; // rax
  int v4; // ebx
  int v5; // eax
  __int64 v6; // rdx
  const struct std::nothrow_t *v7; // rdx
  const WCHAR *v8; // rbx
  HMODULE Library; // rax
  signed int v10; // esi
  unsigned int v11; // eax
  int v12; // edi
  const struct std::nothrow_t *v13; // rdx
  signed int v14; // esi
  unsigned int v15; // eax
  const struct std::nothrow_t *v16; // rdx
  unsigned int v17; // esi
  char **v18; // r14
  const struct std::nothrow_t *v19; // rdx
  signed int v20; // esi
  unsigned int v21; // eax
  const struct std::nothrow_t *v22; // rdx
  signed int v23; // ebx
  unsigned int v24; // eax
  unsigned int v25; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpLibFileName; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v27[2]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v28[2]; // [rsp+40h] [rbp-C0h] BYREF
  HMODULE phModule; // [rsp+50h] [rbp-B0h] BYREF
  int v30; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v28[1] = -2;
  phModule = 0;
  memset_0(Filename, 0, 0x208u);
  lpLibFileName = 0;
  if ( !GetModuleHandleExW(6u, &word_1803AC978, &phModule) )
  {
    LastError = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(__int64 *)&LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get this module's handle.");
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      else
        v1 = LastError;
      v30 = v1;
      lpLibFileName = (LPCWSTR)&v30;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)&lpLibFileName);
    }
    if ( LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x81,
               (unsigned int)"onecore\\base\\cbs\\esd\\lib\\cbsesdwrapper.cpp",
               (const char *)(unsigned int)LastError,
               v25);
    return 0;
  }
  if ( GetModuleFileNameW(phModule, Filename, 0x104u) - 1 <= 0x102 )
  {
    v3 = wcsrchr(Filename, 0x5Cu);
    if ( !v3 )
    {
      v4 = -2147418113;
      v30 = -2147418113;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(__int64 *)&LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Module file path is malformed.");
        lpLibFileName = (LPCWSTR)&v30;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(__int64 *)&LogAdapter::g_Logger,
          1,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)": {}",
          (__int64)&lpLibFileName);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"onecore\\base\\cbs\\esd\\lib\\cbsesdwrapper.cpp",
        (const char *)0x8000FFFFLL,
        v25);
      return v4;
    }
    v3[1] = 0;
    v5 = SczAllocConcat2Sz(&lpLibFileName, Filename, L"wimgapi.dll");
    v4 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecore\\base\\cbs\\esd\\lib\\cbsesdwrapper.cpp",
        (const char *)(unsigned int)v5,
        v25);
      if ( lpLibFileName )
        operator delete((void *)(lpLibFileName - 4), v7);
      return v4;
    }
    BYTE1(v30) = 1;
    v8 = lpLibFileName;
    if ( (unsigned int)DoesFileExist(lpLibFileName, v6) )
    {
      Library = LoadLibraryExW(v8, 0, 8u);
      vhWimgapiDll = Library;
      if ( !Library )
      {
        v10 = GetLastError();
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          v28[0] = v8;
          LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load wimgapi.dll from path: {}",
            (__int64)v28);
          if ( v10 > 0 )
            v11 = (unsigned __int16)v10 | 0x80070000;
          else
            v11 = v10;
          LODWORD(lpLibFileName) = v11;
          *(_QWORD *)v27 = &lpLibFileName;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
            (__int64)v27);
        }
        if ( v10 )
        {
          v12 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x96,
                  (unsigned int)"onecore\\base\\cbs\\esd\\lib\\cbsesdwrapper.cpp",
                  (const char *)(unsigned int)v10,
                  v25);
          wil::details::lambda_call__CbsEsdLoad_::_2_::_lambda_1___::_lambda_call__CbsEsdLoad_::_2_::_lambda_1___(&v30);
          if ( v8 )
            operator delete((void *)(v8 - 4), v13);
          return v12;
        }
        goto LABEL_57;
      }
    }
    else
    {
      Library = LoadLibraryExW(L"wimgapi.dll", 0, 0x800u);
      vhWimgapiDll = Library;
      if ( !Library )
      {
        v14 = GetLastError();
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(__int64 *)&LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to load wimgapi.dll from system32.");
          if ( v14 > 0 )
            v15 = (unsigned __int16)v14 | 0x80070000;
          else
            v15 = v14;
          LODWORD(lpLibFileName) = v15;
          *(_QWORD *)v27 = &lpLibFileName;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(__int64 *)&LogAdapter::g_Logger,
            1,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
            (__int64)v27);
        }
        if ( v14 )
        {
          v12 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x9B,
                  (unsigned int)"onecore\\base\\cbs\\esd\\lib\\cbsesdwrapper.cpp",
                  (const char *)(unsigned int)v14,
                  v25);
          wil::details::lambda_call__CbsEsdLoad_::_2_::_lambda_1___::_lambda_call__CbsEsdLoad_::_2_::_lambda_1___(&v30);
          if ( v8 )
            operator delete((void *)(v8 - 4), v16);
          return v12;
        }
LABEL_57:
        wil::details::lambda_call__CbsEsdLoad_::_2_::_lambda_1___::_lambda_call__CbsEsdLoad_::_2_::_lambda_1___(&v30);
LABEL_58:
        if ( v8 )
          operator delete((void *)(v8 - 4), v19);
        return 0;
      }
    }
    v17 = 0;
    while ( 1 )
    {
      v18 = &(&off_1803A97F0)[2 * v17];
      *(_QWORD *)v18[1] = GetProcAddress(Library, *v18);
      if ( !*(_QWORD *)v18[1] )
        break;
      if ( ++v17 >= 9 )
      {
        vbValid = 1;
        BYTE1(v30) = 0;
        wil::details::lambda_call__CbsEsdLoad_::_2_::_lambda_1___::_lambda_call__CbsEsdLoad_::_2_::_lambda_1___(&v30);
        goto LABEL_58;
      }
      Library = vhWimgapiDll;
    }
    v20 = GetLastError();
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<char const *>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to resolve wimgapi.dll import: {}",
        v18);
      if ( v20 > 0 )
        v21 = (unsigned __int16)v20 | 0x80070000;
      else
        v21 = v20;
      LODWORD(lpLibFileName) = v21;
      *(_QWORD *)v27 = &lpLibFileName;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(__int64 *)&LogAdapter::g_Logger,
        1,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
        (__int64)v27);
    }
    if ( v20 )
    {
      v12 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xA2,
              (unsigned int)"onecore\\base\\cbs\\esd\\lib\\cbsesdwrapper.cpp",
              (const char *)(unsigned int)v20,
              v25);
      wil::details::lambda_call__CbsEsdLoad_::_2_::_lambda_1___::_lambda_call__CbsEsdLoad_::_2_::_lambda_1___(&v30);
      if ( v8 )
        operator delete((void *)(v8 - 4), v22);
      return v12;
    }
    goto LABEL_57;
  }
  v23 = GetLastError();
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      *(__int64 *)&LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get this module's file path.");
    if ( v23 > 0 )
      v24 = (unsigned __int16)v23 | 0x80070000;
    else
      v24 = v23;
    LODWORD(lpLibFileName) = v24;
    *(_QWORD *)v27 = &lpLibFileName;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(__int64 *)&LogAdapter::g_Logger,
      1,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)": {0}",
      (__int64)v27);
  }
  if ( v23 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x85,
             (unsigned int)"onecore\\base\\cbs\\esd\\lib\\cbsesdwrapper.cpp",
             (const char *)(unsigned int)v23,
             v25);
  return 0;
}

```

## disassembly

```asm
0x1801512b4  push    rbp
0x1801512b6  push    rbx
0x1801512b7  push    rsi
0x1801512b8  push    rdi
0x1801512b9  push    r12
0x1801512bb  push    r14
0x1801512bd  lea     rbp, [rsp-188h]
0x1801512c5  sub     rsp, 288h
0x1801512cc  mov     [rsp+2B0h+var_268], 0FFFFFFFFFFFFFFFEh
0x1801512d5  mov     rax, cs:__security_cookie
0x1801512dc  xor     rax, rsp
0x1801512df  mov     [rbp+1B0h+var_40], rax
0x1801512e6  mov     [rsp+2B0h+phModule], 0
0x1801512ef  xor     edx, edx; Val
0x1801512f1  mov     r8d, 208h; Size
0x1801512f7  lea     rcx, [rsp+2B0h+Filename]; void *
0x1801512fc  call    memset_0
0x180151301  mov     [rsp+2B0h+lpLibFileName], 0
0x18015130a  lea     r8, [rsp+2B0h+phModule]; phModule
0x18015130f  lea     rdx, word_1803AC978; lpModuleName
0x180151316  mov     ecx, 6; dwFlags
0x18015131b  call    cs:__imp_GetModuleHandleExW
0x180151322  nop     dword ptr [rax+rax+00h]
0x180151327  test    eax, eax
0x180151329  jnz     loc_1801513C9
0x18015132f  call    cs:__imp_GetLastError
0x180151336  nop     dword ptr [rax+rax+00h]
0x18015133b  mov     ebx, eax
0x18015133d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180151344  test    rcx, rcx
0x180151347  jz      short loc_18015139F
0x180151349  lea     r9, aFailedToGetThi; "Failed to get this module's handle."
0x180151350  mov     edi, 3
0x180151355  mov     r8d, edi
0x180151358  xor     edx, edx
0x18015135a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18015135f  test    ebx, ebx
0x180151361  jg      short loc_180151367
0x180151363  mov     eax, ebx
0x180151365  jmp     short loc_18015136F
0x180151367  movzx   eax, bx
0x18015136a  or      eax, 80070000h
0x18015136f  mov     [rsp+2B0h+var_258], eax
0x180151373  lea     rax, [rsp+2B0h+var_258]
0x180151378  mov     [rsp+2B0h+lpLibFileName], rax
0x18015137d  lea     rax, [rsp+2B0h+lpLibFileName]
0x180151382  mov     qword ptr [rsp+2B0h+var_290], rax; unsigned int
0x180151387  lea     r9, a0; ": {0}"
0x18015138e  mov     r8d, edi
0x180151391  mov     dl, 1
0x180151393  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18015139a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18015139f  test    ebx, ebx
0x1801513a1  jz      short loc_1801513C4
0x1801513a3  mov     rcx, [rbp+1B8h]; this
0x1801513aa  mov     r9d, ebx; char *
0x1801513ad  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\esd\\lib\\cbsesdwra"...
0x1801513b4  mov     edx, 81h; void *
0x1801513b9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801513be  nop
0x1801513bf  jmp     loc_1801518A3
0x1801513c4  jmp     loc_1801518A1
0x1801513c9  mov     r8d, 104h; nSize
0x1801513cf  lea     rdx, [rsp+2B0h+Filename]; lpFilename
0x1801513d4  mov     rcx, [rsp+2B0h+phModule]; hModule
0x1801513d9  call    cs:__imp_GetModuleFileNameW
0x1801513e0  nop     dword ptr [rax+rax+00h]
0x1801513e5  dec     eax
0x1801513e7  cmp     eax, 102h
0x1801513ec  ja      loc_18015180F
0x1801513f2  mov     edx, 5Ch ; '\'; Ch
0x1801513f7  lea     rcx, [rsp+2B0h+Filename]; Str
0x1801513fc  call    cs:__imp_wcsrchr
0x180151403  nop     dword ptr [rax+rax+00h]
0x180151408  mov     rcx, rax
0x18015140b  test    rax, rax
0x18015140e  jnz     short loc_180151488
0x180151410  mov     ebx, 8000FFFFh
0x180151415  mov     [rsp+2B0h+var_258], ebx
0x180151419  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180151420  test    rcx, rcx
0x180151423  jz      short loc_180151465
0x180151425  lea     r9, aModuleFilePath; "Module file path is malformed."
0x18015142c  lea     edi, [rax+3]
0x18015142f  mov     r8d, edi
0x180151432  xor     edx, edx
0x180151434  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180151439  lea     rax, [rsp+2B0h+var_258]
0x18015143e  mov     [rsp+2B0h+lpLibFileName], rax
0x180151443  lea     rax, [rsp+2B0h+lpLibFileName]
0x180151448  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x18015144d  lea     r9, asc_1802C6678; ": {}"
0x180151454  mov     r8d, edi
0x180151457  mov     dl, 1
0x180151459  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180151460  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180151465  mov     rcx, [rbp+1B8h]; this
0x18015146c  mov     r9d, ebx; char *
0x18015146f  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\esd\\lib\\cbsesdwra"...
0x180151476  mov     edx, 88h; void *
0x18015147b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180151480  nop
0x180151481  mov     eax, ebx
0x180151483  jmp     loc_1801518A3
0x180151488  xor     eax, eax
0x18015148a  mov     [rcx+2], ax
0x18015148e  lea     r8, aWimgapiDll_0; "wimgapi.dll"
0x180151495  lea     rdx, [rsp+2B0h+Filename]
0x18015149a  lea     rcx, [rsp+2B0h+lpLibFileName]
0x18015149f  call    SczAllocConcat2Sz
0x1801514a4  mov     ebx, eax
0x1801514a6  test    eax, eax
0x1801514a8  jns     short loc_1801514DC
0x1801514aa  mov     rcx, [rbp+1B8h]; this
0x1801514b1  mov     r9d, eax; char *
0x1801514b4  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\esd\\lib\\cbsesdwra"...
0x1801514bb  mov     edx, 8Fh; void *
0x1801514c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801514c5  nop
0x1801514c6  mov     rcx, [rsp+2B0h+lpLibFileName]
0x1801514cb  test    rcx, rcx
0x1801514ce  jz      short loc_1801514DA
0x1801514d0  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x1801514d4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801514d9  nop
0x1801514da  jmp     short loc_180151481
0x1801514dc  mov     byte ptr [rsp+2B0h+var_258+1], 1
0x1801514e1  mov     rbx, [rsp+2B0h+lpLibFileName]
0x1801514e6  mov     rcx, rbx
0x1801514e9  call    DoesFileExist
0x1801514ee  xor     edx, edx; hFile
0x1801514f0  test    eax, eax
0x1801514f2  jz      loc_1801515EC
0x1801514f8  lea     r8d, [rdx+8]; dwFlags
0x1801514fc  mov     rcx, rbx; lpLibFileName
0x1801514ff  call    cs:__imp_LoadLibraryExW
0x180151506  nop     dword ptr [rax+rax+00h]
0x18015150b  mov     cs:?vhWimgapiDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * vhWimgapiDll
0x180151512  test    rax, rax
0x180151515  jnz     loc_1801516D5
0x18015151b  call    cs:__imp_GetLastError
0x180151522  nop     dword ptr [rax+rax+00h]
0x180151527  mov     esi, eax
0x180151529  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180151530  test    rcx, rcx
0x180151533  jz      short loc_18015159A
0x180151535  mov     [rsp+2B0h+var_270], rbx
0x18015153a  lea     rax, [rsp+2B0h+var_270]
0x18015153f  mov     qword ptr [rsp+2B0h+var_290], rax
0x180151544  lea     r9, aFailedToLoadWi_0; "Failed to load wimgapi.dll from path: {"...
0x18015154b  mov     edi, 3
0x180151550  mov     r8d, edi
0x180151553  xor     edx, edx
0x180151555  call    ??$LogNumObjects@V?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$AutoGenericHandle@PEA_W$0A@$1??$CloseWithCoTaskMemFree@_W@Detail@Windows@@YAXPEA_W@Z@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(bool,LogAdapter::LogLevel,char const * const,Windows::AutoGenericHandle<wchar_t *,0,&Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)> const &)
0x18015155a  test    esi, esi
0x18015155c  jg      short loc_180151562
0x18015155e  mov     eax, esi
0x180151560  jmp     short loc_18015156A
0x180151562  movzx   eax, si
0x180151565  or      eax, 80070000h
0x18015156a  mov     dword ptr [rsp+2B0h+lpLibFileName], eax
0x18015156e  lea     rax, [rsp+2B0h+lpLibFileName]
0x180151573  mov     qword ptr [rsp+2B0h+var_278], rax
0x180151578  lea     rax, [rsp+2B0h+var_278]
0x18015157d  mov     qword ptr [rsp+2B0h+var_290], rax; unsigned int
0x180151582  lea     r9, a0; ": {0}"
0x180151589  mov     r8d, edi
0x18015158c  mov     dl, 1
0x18015158e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180151595  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18015159a  test    esi, esi
0x18015159c  jz      short loc_1801515DC
0x18015159e  mov     rcx, [rbp+1B8h]; this
0x1801515a5  mov     r9d, esi; char *
0x1801515a8  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\esd\\lib\\cbsesdwra"...
0x1801515af  mov     edx, 96h; void *
0x1801515b4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801515b9  mov     edi, eax
0x1801515bb  lea     rcx, [rsp+2B0h+var_258]
0x1801515c0  call    wil__details__lambda_call__CbsEsdLoad____2____lambda_1______lambda_call__CbsEsdLoad____2____lambda_1___
0x1801515c5  nop
0x1801515c6  test    rbx, rbx
0x1801515c9  jz      short loc_1801515D5
0x1801515cb  lea     rcx, [rbx-8]; void *
0x1801515cf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801515d4  nop
0x1801515d5  mov     eax, edi
0x1801515d7  jmp     loc_1801518A3
0x1801515dc  lea     rcx, [rsp+2B0h+var_258]
0x1801515e1  call    wil__details__lambda_call__CbsEsdLoad____2____lambda_1______lambda_call__CbsEsdLoad____2____lambda_1___
0x1801515e6  nop
0x1801515e7  jmp     loc_1801517FB
0x1801515ec  mov     r8d, 800h; dwFlags
0x1801515f2  lea     rcx, aWimgapiDll_0; "wimgapi.dll"
0x1801515f9  call    cs:__imp_LoadLibraryExW
0x180151600  nop     dword ptr [rax+rax+00h]
0x180151605  mov     cs:?vhWimgapiDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * vhWimgapiDll
0x18015160c  test    rax, rax
0x18015160f  jnz     loc_1801516D5
0x180151615  call    cs:__imp_GetLastError
0x18015161c  nop     dword ptr [rax+rax+00h]
0x180151621  mov     esi, eax
0x180151623  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18015162a  test    rcx, rcx
0x18015162d  jz      short loc_180151685
0x18015162f  lea     r9, aFailedToLoadWi; "Failed to load wimgapi.dll from system3"...
0x180151636  mov     edi, 3
0x18015163b  mov     r8d, edi
0x18015163e  xor     edx, edx
0x180151640  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180151645  test    esi, esi
0x180151647  jg      short loc_18015164D
0x180151649  mov     eax, esi
0x18015164b  jmp     short loc_180151655
0x18015164d  movzx   eax, si
0x180151650  or      eax, 80070000h
0x180151655  mov     dword ptr [rsp+2B0h+lpLibFileName], eax
0x180151659  lea     rax, [rsp+2B0h+lpLibFileName]
0x18015165e  mov     qword ptr [rsp+2B0h+var_278], rax
0x180151663  lea     rax, [rsp+2B0h+var_278]
0x180151668  mov     qword ptr [rsp+2B0h+var_290], rax; unsigned int
0x18015166d  lea     r9, a0; ": {0}"
0x180151674  mov     r8d, edi
0x180151677  mov     dl, 1
0x180151679  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180151680  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180151685  test    esi, esi
0x180151687  jz      short loc_1801516C5
0x180151689  mov     rcx, [rbp+1B8h]; this
0x180151690  mov     r9d, esi; char *
0x180151693  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\esd\\lib\\cbsesdwra"...
0x18015169a  mov     edx, 9Bh; void *
0x18015169f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801516a4  mov     edi, eax
0x1801516a6  lea     rcx, [rsp+2B0h+var_258]
0x1801516ab  call    wil__details__lambda_call__CbsEsdLoad____2____lambda_1______lambda_call__CbsEsdLoad____2____lambda_1___
0x1801516b0  nop
0x1801516b1  test    rbx, rbx
0x1801516b4  jz      short loc_1801516C0
0x1801516b6  lea     rcx, [rbx-8]; void *
0x1801516ba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801516bf  nop
0x1801516c0  jmp     loc_1801515D5
0x1801516c5  lea     rcx, [rsp+2B0h+var_258]
0x1801516ca  call    wil__details__lambda_call__CbsEsdLoad____2____lambda_1______lambda_call__CbsEsdLoad____2____lambda_1___
0x1801516cf  nop
0x1801516d0  jmp     loc_1801517FB
0x1801516d5  xor     esi, esi
0x1801516d7  lea     r12, off_1803A97F0; "WIMCreateFile"
0x1801516de  mov     edi, esi
0x1801516e0  add     rdi, rdi
0x1801516e3  lea     r14, [r12+rdi*8]
0x1801516e7  mov     rdx, [r14]; lpProcName
0x1801516ea  mov     rcx, rax; hModule
0x1801516ed  call    cs:__imp_GetProcAddress
0x1801516f4  nop     dword ptr [rax+rax+00h]
0x1801516f9  mov     rcx, [r12+rdi*8+8]
0x1801516fe  mov     [rcx], rax
0x180151701  mov     rax, [r12+rdi*8+8]
0x180151706  cmp     qword ptr [rax], 0
0x18015170a  jz      short loc_18015173B
0x18015170c  inc     esi
0x18015170e  cmp     esi, 9
0x180151711  jnb     short loc_18015171C
0x180151713  mov     rax, cs:?vhWimgapiDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * vhWimgapiDll
0x18015171a  jmp     short loc_1801516DE
0x18015171c  mov     cs:?vbValid@@3HA, 1; int vbValid
0x180151726  mov     byte ptr [rsp+2B0h+var_258+1], 0
0x18015172b  lea     rcx, [rsp+2B0h+var_258]
0x180151730  call    wil__details__lambda_call__CbsEsdLoad____2____lambda_1______lambda_call__CbsEsdLoad____2____lambda_1___
0x180151735  nop
0x180151736  jmp     loc_1801517FB
0x18015173b  call    cs:__imp_GetLastError
0x180151742  nop     dword ptr [rax+rax+00h]
0x180151747  mov     esi, eax
0x180151749  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180151750  test    rcx, rcx
0x180151753  jz      short loc_1801517B0
0x180151755  mov     qword ptr [rsp+2B0h+var_290], r14
0x18015175a  lea     r9, aFailedToResolv; "Failed to resolve wimgapi.dll import: {"...
0x180151761  mov     edi, 3
0x180151766  mov     r8d, edi
0x180151769  xor     edx, edx
0x18015176b  call    ??$LogNumObjects@PEBD@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEBD@Z; LogAdapter::Logger::LogNumObjects<char const *>(bool,LogAdapter::LogLevel,char const * const,char const * const &)
0x180151770  test    esi, esi
0x180151772  jg      short loc_180151778
0x180151774  mov     eax, esi
0x180151776  jmp     short loc_180151780
0x180151778  movzx   eax, si
0x18015177b  or      eax, 80070000h
0x180151780  mov     dword ptr [rsp+2B0h+lpLibFileName], eax
0x180151784  lea     rax, [rsp+2B0h+lpLibFileName]
0x180151789  mov     qword ptr [rsp+2B0h+var_278], rax
0x18015178e  lea     rax, [rsp+2B0h+var_278]
0x180151793  mov     qword ptr [rsp+2B0h+var_290], rax; unsigned int
0x180151798  lea     r9, a0; ": {0}"
0x18015179f  mov     r8d, edi
0x1801517a2  mov     dl, 1
0x1801517a4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801517ab  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
  ... truncated ...
```
