# LoadWinREAgent(wchar_t const * const,IArbiterDiagnostics *,HINSTANCE__ * *)

- ea: `0x18006f3b0`
- end: `0x18006faaa`
- name: `?LoadWinREAgent@@YAJQEB_WPEAVIArbiterDiagnostics@@PEAPEAUHINSTANCE__@@@Z`
- size: `1786`
- prototype: `__int64 __fastcall(const wchar_t *const, struct IArbiterDiagnostics *, HINSTANCE *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180093714`

## callees

- `0x1800031d0`
- `0x180003c64`
- `0x1800062b8`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x1800296a4`
- `0x180037310`
- `0x18003d278`
- `0x18003ddc8`
- `0x18003e9cc`
- `0x180042764`
- `0x18004d970`
- `0x180050fd0`
- `0x180051984`
- `0x180065828`
- `0x180066cd4`
- `0x18006f3b0`
- `0x180071994`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006f680`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006f680`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f9e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f9e9`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18006f9cf`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18006f9cf`

## string_xrefs

- `0x18006f6b3`: `Failed to get system path`
- `0x18006f51f`: `WinREAgent.dll`
- `0x18006f558`: `WinREAgent.dll`
- `0x18006f7d2`: `WinREAgent.dll`
- `0x18006f585`: `Failed to get the path of the current process`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LoadWinREAgent(const wchar_t *const a1, struct IArbiterDiagnostics *a2, HINSTANCE *a3)
{
  void ***v5; // rcx
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdx
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  int Win32PathOfSiblingFile; // eax
  __int64 v14; // rdx
  __int64 v15; // rbx
  int v16; // eax
  unsigned int v17; // edi
  signed int v18; // esi
  __int64 v19; // rdx
  unsigned int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdx
  int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  HMODULE Library; // rax
  signed int LastError; // ebx
  __int64 v31; // rdx
  unsigned int v32; // eax
  unsigned int *v33; // [rsp+28h] [rbp-E0h]
  unsigned int v34[2]; // [rsp+38h] [rbp-D0h] BYREF
  HMODULE v35; // [rsp+40h] [rbp-C8h]
  __int128 v36; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-B0h]
  __int64 v38; // [rsp+60h] [rbp-A8h]
  LPCWSTR lpLibFileName; // [rsp+68h] [rbp-A0h] BYREF
  int v40[2]; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v41[4]; // [rsp+78h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+88h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C0h] [rbp+1B8h]

  v38 = -2;
  if ( a3 )
    *a3 = 0;
  v40[0] = 0;
  lpLibFileName = 0;
  v35 = 0;
  if ( a2 )
  {
    if ( !byte_18023E4D8 )
      qword_18023E4D0 = (__int64)a2;
    v5 = &g_ArbiterLogger;
    goto LABEL_7;
  }
  if ( IsWdsLoggerSetup(0) )
  {
    v5 = &g_WdsLogger;
LABEL_7:
    *(_QWORD *)&LogAdapter::g_Logger = v5;
    vpfnCustomLogging = (void (*)(unsigned int, const char *))CbsCustomLogging;
    goto LABEL_11;
  }
  v5 = *(void ****)&LogAdapter::g_Logger;
LABEL_11:
  if ( !a3 )
  {
    v6 = -2147024809;
    v40[0] = -2147024809;
    if ( v5 )
    {
      LogAdapter::Logger::LogNumObjects<>(v5, 0, 3, "Invalid arg: pModuleHandle.");
      *(_QWORD *)v41 = v40;
      v33 = v41;
      LOBYTE(v7) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v7,
        3,
        ": {}");
    }
    v8 = 3024;
    goto LABEL_15;
  }
  if ( a1 )
  {
    v6 = SczAllocFromSz(&lpLibFileName);
    if ( v6 < 0 )
    {
      v8 = 3031;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
        (const char *)(unsigned int)v6,
        (int)v33);
LABEL_16:
      if ( lpLibFileName )
        operator delete((void *)(lpLibFileName - 4));
      return (unsigned int)v6;
    }
    v6 = SczEnsureBackslashTerminated(&lpLibFileName);
    if ( v6 < 0 )
    {
      v8 = 3032;
      goto LABEL_15;
    }
    v6 = SczAllocConcatSz(&lpLibFileName, L"WinREAgent.dll");
    if ( v6 < 0 )
    {
      v8 = 3033;
      goto LABEL_15;
    }
    goto LABEL_66;
  }
  v36 = 0;
  v37 = 0;
  Win32PathOfSiblingFile = Windows::COM::GetWin32PathOfSiblingFile(LoadWinREAgent, L"WinREAgent.dll", &v36);
  v6 = Win32PathOfSiblingFile;
  if ( Win32PathOfSiblingFile < 0 )
  {
    v40[0] = Win32PathOfSiblingFile;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to get the path of the current process");
      *(_QWORD *)v41 = v40;
      v33 = v41;
      LOBYTE(v14) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v14,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBE2,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
      (const char *)(unsigned int)v6,
      (int)v33);
    if ( v37 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v37);
    goto LABEL_16;
  }
  v15 = v37;
  v16 = SczAllocFromSz(&lpLibFileName);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBE4,
      (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
      (const char *)(unsigned int)v16,
      (int)v33);
    if ( v15 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v15);
    goto LABEL_35;
  }
  if ( (unsigned int)DoesFileExist(lpLibFileName) )
  {
LABEL_64:
    if ( v15 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v15);
LABEL_66:
    if ( *(_QWORD *)&LogAdapter::g_Logger )
      LogAdapter::Logger::LogNumObjects<wchar_t [15],AutoScz>(LogAdapter::g_Logger, v10, v11, v12);
    if ( !(unsigned int)DoesFileExist(lpLibFileName) )
    {
      v6 = -2147024894;
      v40[0] = -2147024894;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<AutoScz>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "File [{0}] doesn't exist",
          &lpLibFileName);
        *(_QWORD *)v41 = v40;
        v33 = v41;
        LOBYTE(v24) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v24,
          3,
          ": {}");
      }
      v8 = 3064;
      goto LABEL_15;
    }
    v25 = VerifyFileSignature(lpLibFileName, v40);
    v6 = v25;
    if ( v25 < 0 )
    {
      v40[0] = v25;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<AutoScz>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to verify the signature of {0}",
          &lpLibFileName);
        *(_QWORD *)v34 = v40;
        v33 = v34;
        LOBYTE(v27) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v27,
          3,
          ": {}");
      }
      v8 = 3069;
      goto LABEL_15;
    }
    if ( !v40[0] )
    {
      v6 = -2146869244;
      v41[0] = -2146869244;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<AutoScz>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "{0} not signed with a valid MS signature",
          &lpLibFileName);
        *(_QWORD *)v34 = v41;
        v33 = v34;
        LOBYTE(v28) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v28,
          3,
          ": {}");
      }
      v8 = 3070;
      goto LABEL_15;
    }
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LOBYTE(v26) = 1;
      LogAdapter::Logger::LogNumObjects<AutoScz>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v26,
        1,
        "Signature verified for: {0}",
        &lpLibFileName);
    }
    Library = LoadLibraryExW(lpLibFileName, 0, 8u);
    v35 = Library;
    if ( Library )
    {
      *a3 = Library;
    }
    else
    {
      LastError = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogPartial<wchar_t [15]>();
        if ( LastError > 0 )
          v32 = (unsigned __int16)LastError | 0x80070000;
        else
          v32 = LastError;
        v41[0] = v32;
        *(_QWORD *)v34 = v41;
        v33 = v34;
        LOBYTE(v31) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v31,
          3,
          ": {0}");
      }
      if ( LastError )
      {
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xC06,
               (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
               (const char *)(unsigned int)LastError,
               (unsigned int)v33);
        goto LABEL_16;
      }
    }
    goto LABEL_91;
  }
  memset_0(Buffer, 0, 0x208u);
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 <= 0x102 )
  {
    v21 = SczAllocFromSz(&lpLibFileName);
    v17 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBF0,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
        (const char *)(unsigned int)v21,
        (int)v33);
      if ( v15 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v15);
      goto LABEL_35;
    }
    v22 = SczEnsureBackslashTerminated(&lpLibFileName);
    v17 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBF1,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
        (const char *)(unsigned int)v22,
        (int)v33);
      if ( v15 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v15);
      goto LABEL_35;
    }
    v23 = SczAllocConcatSz(&lpLibFileName, L"WinREAgent.dll");
    v17 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBF2,
        (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
        (const char *)(unsigned int)v23,
        (int)v33);
      if ( v15 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v15);
      goto LABEL_35;
    }
    goto LABEL_64;
  }
  v18 = GetLastError();
  if ( *(_QWORD *)&LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get system path");
    if ( v18 > 0 )
      v20 = (unsigned __int16)v18 | 0x80070000;
    else
      v20 = v18;
    v40[0] = v20;
    *(_QWORD *)v41 = v40;
    v33 = v41;
    LOBYTE(v19) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      *(_QWORD *)&LogAdapter::g_Logger,
      v19,
      3,
      ": {0}");
  }
  if ( !v18 )
  {
    if ( v15 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v15);
LABEL_91:
    if ( lpLibFileName )
      operator delete((void *)(lpLibFileName - 4));
    return 0;
  }
  v17 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0xBEF,
          (unsigned int)"onecore\\base\\servicing\\arbiter\\arbiter.cpp",
          (const char *)(unsigned int)v18,
          (unsigned int)v33);
  if ( v15 )
    anonymous_namespace_::OurRtlFreeStringRoutine(v15);
LABEL_35:
  if ( lpLibFileName )
    operator delete((void *)(lpLibFileName - 4));
  return v17;
}

```

## disassembly

```asm
0x18006f3b0  mov     rax, rsp
0x18006f3b3  push    rbp
0x18006f3b4  push    rsi
0x18006f3b5  push    rdi
0x18006f3b6  lea     rbp, [rax-1B8h]
0x18006f3bd  sub     rsp, 2A0h
0x18006f3c4  mov     [rsp+2B0h+var_258], 0FFFFFFFFFFFFFFFEh
0x18006f3cd  mov     [rax+10h], rbx
0x18006f3d1  mov     rax, cs:__security_cookie
0x18006f3d8  xor     rax, rsp
0x18006f3db  mov     [rbp+1B0h+var_20], rax
0x18006f3e2  mov     rsi, r8
0x18006f3e5  mov     rbx, rcx
0x18006f3e8  test    r8, r8
0x18006f3eb  jz      short loc_18006F3F4
0x18006f3ed  mov     qword ptr [r8], 0
0x18006f3f4  mov     [rsp+2B0h+var_248], 0
0x18006f3fc  mov     [rsp+2B0h+lpLibFileName], 0
0x18006f405  mov     qword ptr [rsp+2B0h+var_278], 0
0x18006f40e  test    rdx, rdx
0x18006f411  jz      short loc_18006F441
0x18006f413  cmp     cs:byte_18023E4D8, 0
0x18006f41a  jnz     short loc_18006F423
0x18006f41c  mov     cs:qword_18023E4D0, rdx
0x18006f423  lea     rcx, ?g_ArbiterLogger@@3VArbiterLogger@LogAdapter@@A; LogAdapter::ArbiterLogger g_ArbiterLogger
0x18006f42a  mov     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, rcx; LogAdapter::Logger * LogAdapter::g_Logger
0x18006f431  lea     rax, ?CbsCustomLogging@@YAXIPEBD@Z; CbsCustomLogging(uint,char const *)
0x18006f438  mov     cs:?vpfnCustomLogging@@3P6AXIPEBD@ZEA, rax; void (*vpfnCustomLogging)(uint,char const *)
0x18006f43f  jmp     short loc_18006F45C
0x18006f441  xor     ecx, ecx; HINSTANCE *
0x18006f443  call    ?IsWdsLoggerSetup@@YA_NPEAPEAUHINSTANCE__@@@Z; IsWdsLoggerSetup(HINSTANCE__ * *)
0x18006f448  test    al, al
0x18006f44a  jz      short loc_18006F455
0x18006f44c  lea     rcx, ?g_WdsLogger@@3VWdsLogger@LogAdapter@@A; LogAdapter::WdsLogger g_WdsLogger
0x18006f453  jmp     short loc_18006F42A
0x18006f455  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006f45c  test    rsi, rsi
0x18006f45f  jnz     loc_18006F4E9
0x18006f465  mov     ebx, 80070057h
0x18006f46a  mov     [rsp+2B0h+var_248], ebx
0x18006f46e  test    rcx, rcx
0x18006f471  jz      short loc_18006F4B3
0x18006f473  lea     r9, aInvalidArgPmod; "Invalid arg: pModuleHandle."
0x18006f47a  lea     edi, [rsi+3]
0x18006f47d  mov     r8d, edi
0x18006f480  xor     edx, edx
0x18006f482  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18006f487  lea     rax, [rsp+2B0h+var_248]
0x18006f48c  mov     qword ptr [rsp+2B0h+var_240], rax
0x18006f491  lea     rax, [rsp+2B0h+var_240]
0x18006f496  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x18006f49b  lea     r9, asc_1801CAFB4; ": {}"
0x18006f4a2  mov     r8d, edi
0x18006f4a5  mov     dl, 1
0x18006f4a7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006f4ae  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18006f4b3  mov     edx, 0BD0h; void *
0x18006f4b8  mov     rcx, [rbp+1B8h]; this
0x18006f4bf  mov     r9d, ebx; char *
0x18006f4c2  lea     r8, aOnecoreBaseSer_24; "onecore\\base\\servicing\\arbiter\\arbi"...
0x18006f4c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f4ce  nop
0x18006f4cf  mov     rcx, [rsp+2B0h+lpLibFileName]
0x18006f4d4  test    rcx, rcx
0x18006f4d7  jz      short loc_18006F4E2
0x18006f4d9  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18006f4dd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006f4e2  mov     eax, ebx
0x18006f4e4  jmp     loc_18006FA87
0x18006f4e9  test    rbx, rbx
0x18006f4ec  jz      short loc_18006F544
0x18006f4ee  mov     rdx, rbx
0x18006f4f1  lea     rcx, [rsp+2B0h+lpLibFileName]
0x18006f4f6  call    SczAllocFromSz
0x18006f4fb  mov     ebx, eax
0x18006f4fd  test    eax, eax
0x18006f4ff  jns     short loc_18006F508
0x18006f501  mov     edx, 0BD7h
0x18006f506  jmp     short loc_18006F4B8
0x18006f508  lea     rcx, [rsp+2B0h+lpLibFileName]
0x18006f50d  call    SczEnsureBackslashTerminated
0x18006f512  mov     ebx, eax
0x18006f514  test    eax, eax
0x18006f516  jns     short loc_18006F51F
0x18006f518  mov     edx, 0BD8h
0x18006f51d  jmp     short loc_18006F4B8
0x18006f51f  lea     rdx, aWinreagentDll; "WinREAgent.dll"
0x18006f526  lea     rcx, [rsp+2B0h+lpLibFileName]
0x18006f52b  call    SczAllocConcatSz
0x18006f530  mov     ebx, eax
0x18006f532  test    eax, eax
0x18006f534  jns     loc_18006F826
0x18006f53a  mov     edx, 0BD9h
0x18006f53f  jmp     loc_18006F4B8
0x18006f544  xorps   xmm0, xmm0
0x18006f547  xor     eax, eax
0x18006f549  movups  [rsp+2B0h+var_278+8], xmm0
0x18006f54e  mov     [rsp+2B0h+var_260], rax
0x18006f553  lea     r8, [rsp+2B0h+var_278+8]
0x18006f558  lea     rdx, aWinreagentDll; "WinREAgent.dll"
0x18006f55f  lea     rcx, ?LoadWinREAgent@@YAJQEB_WPEAVIArbiterDiagnostics@@PEAPEAUHINSTANCE__@@@Z; LoadWinREAgent(wchar_t const * const,IArbiterDiagnostics *,HINSTANCE__ * *)
0x18006f566  call    ?GetWin32PathOfSiblingFile@COM@Windows@@YAJPEAXPEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::COM::GetWin32PathOfSiblingFile(void *,wchar_t const *,Windows::Auto<_LUNICODE_STRING> *)
0x18006f56b  mov     ebx, eax
0x18006f56d  test    eax, eax
0x18006f56f  jns     loc_18006F5F8
0x18006f575  mov     [rsp+2B0h+var_248], eax
0x18006f579  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006f580  test    rcx, rcx
0x18006f583  jz      short loc_18006F5C7
0x18006f585  lea     r9, aFailedToGetThe_1; "Failed to get the path of the current p"...
0x18006f58c  mov     edi, 3
0x18006f591  mov     r8d, edi
0x18006f594  xor     edx, edx
0x18006f596  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18006f59b  lea     rax, [rsp+2B0h+var_248]
0x18006f5a0  mov     qword ptr [rsp+2B0h+var_240], rax
0x18006f5a5  lea     rax, [rsp+2B0h+var_240]
0x18006f5aa  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x18006f5af  lea     r9, asc_1801CAFB4; ": {}"
0x18006f5b6  mov     r8d, edi
0x18006f5b9  mov     dl, 1
0x18006f5bb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006f5c2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18006f5c7  mov     rcx, [rbp+1B8h]; this
0x18006f5ce  mov     r9d, ebx; char *
0x18006f5d1  lea     r8, aOnecoreBaseSer_24; "onecore\\base\\servicing\\arbiter\\arbi"...
0x18006f5d8  mov     edx, 0BE2h; void *
0x18006f5dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f5e2  nop
0x18006f5e3  mov     rcx, [rsp+2B0h+var_260]
0x18006f5e8  test    rcx, rcx
0x18006f5eb  jz      short loc_18006F5F3
0x18006f5ed  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18006f5f2  nop
0x18006f5f3  jmp     loc_18006F4CF
0x18006f5f8  mov     rbx, [rsp+2B0h+var_260]
0x18006f5fd  mov     rdx, rbx
0x18006f600  lea     rcx, [rsp+2B0h+lpLibFileName]
0x18006f605  call    SczAllocFromSz
0x18006f60a  mov     edi, eax
0x18006f60c  test    eax, eax
0x18006f60e  jns     short loc_18006F654
0x18006f610  mov     rcx, [rbp+1B8h]; this
0x18006f617  mov     r9d, eax; char *
0x18006f61a  lea     r8, aOnecoreBaseSer_24; "onecore\\base\\servicing\\arbiter\\arbi"...
0x18006f621  mov     edx, 0BE4h; void *
0x18006f626  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f62b  nop
0x18006f62c  test    rbx, rbx
0x18006f62f  jz      short loc_18006F63A
0x18006f631  mov     rcx, rbx
0x18006f634  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18006f639  nop
0x18006f63a  mov     rcx, [rsp+2B0h+lpLibFileName]
0x18006f63f  test    rcx, rcx
0x18006f642  jz      short loc_18006F64D
0x18006f644  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18006f648  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006f64d  mov     eax, edi
0x18006f64f  jmp     loc_18006FA87
0x18006f654  mov     rcx, [rsp+2B0h+lpLibFileName]
0x18006f659  call    DoesFileExist
0x18006f65e  test    eax, eax
0x18006f660  jnz     loc_18006F818
0x18006f666  xor     edx, edx; Val
0x18006f668  mov     r8d, 208h; Size
0x18006f66e  lea     rcx, [rbp+1B0h+Buffer]; void *
0x18006f672  call    memset_0
0x18006f677  mov     edx, 104h; uSize
0x18006f67c  lea     rcx, [rbp+1B0h+Buffer]; lpBuffer
0x18006f680  call    cs:__imp_GetSystemDirectoryW
0x18006f687  nop     dword ptr [rax+rax+00h]
0x18006f68c  dec     eax
0x18006f68e  cmp     eax, 102h
0x18006f693  jbe     loc_18006F750
0x18006f699  call    cs:__imp_GetLastError
0x18006f6a0  nop     dword ptr [rax+rax+00h]
0x18006f6a5  mov     esi, eax
0x18006f6a7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006f6ae  test    rcx, rcx
0x18006f6b1  jz      short loc_18006F709
0x18006f6b3  lea     r9, aFailedToGetSys; "Failed to get system path"
0x18006f6ba  mov     edi, 3
0x18006f6bf  mov     r8d, edi
0x18006f6c2  xor     edx, edx
0x18006f6c4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18006f6c9  test    esi, esi
0x18006f6cb  jg      short loc_18006F6D1
0x18006f6cd  mov     eax, esi
0x18006f6cf  jmp     short loc_18006F6D9
0x18006f6d1  movzx   eax, si
0x18006f6d4  or      eax, 80070000h
0x18006f6d9  mov     [rsp+2B0h+var_248], eax
0x18006f6dd  lea     rax, [rsp+2B0h+var_248]
0x18006f6e2  mov     qword ptr [rsp+2B0h+var_240], rax
0x18006f6e7  lea     rax, [rsp+2B0h+var_240]
0x18006f6ec  mov     qword ptr [rsp+2B0h+var_290], rax; unsigned int
0x18006f6f1  lea     r9, a0; ": {0}"
0x18006f6f8  mov     r8d, edi
0x18006f6fb  mov     dl, 1
0x18006f6fd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006f704  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18006f709  test    esi, esi
0x18006f70b  jz      short loc_18006F73D
0x18006f70d  mov     rcx, [rbp+1B8h]; this
0x18006f714  mov     r9d, esi; char *
0x18006f717  lea     r8, aOnecoreBaseSer_24; "onecore\\base\\servicing\\arbiter\\arbi"...
0x18006f71e  mov     edx, 0BEFh; void *
0x18006f723  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006f728  mov     edi, eax
0x18006f72a  test    rbx, rbx
0x18006f72d  jz      short loc_18006F738
0x18006f72f  mov     rcx, rbx
0x18006f732  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18006f737  nop
0x18006f738  jmp     loc_18006F63A
0x18006f73d  test    rbx, rbx
0x18006f740  jz      short loc_18006F74B
0x18006f742  mov     rcx, rbx
0x18006f745  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18006f74a  nop
0x18006f74b  jmp     loc_18006FA72
0x18006f750  lea     rdx, [rbp+1B0h+Buffer]
0x18006f754  lea     rcx, [rsp+2B0h+lpLibFileName]
0x18006f759  call    SczAllocFromSz
0x18006f75e  mov     edi, eax
0x18006f760  test    eax, eax
0x18006f762  jns     short loc_18006F793
0x18006f764  mov     rcx, [rbp+1B8h]; this
0x18006f76b  mov     r9d, eax; char *
0x18006f76e  lea     r8, aOnecoreBaseSer_24; "onecore\\base\\servicing\\arbiter\\arbi"...
0x18006f775  mov     edx, 0BF0h; void *
0x18006f77a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f77f  nop
0x18006f780  test    rbx, rbx
0x18006f783  jz      short loc_18006F78E
0x18006f785  mov     rcx, rbx
0x18006f788  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18006f78d  nop
0x18006f78e  jmp     loc_18006F63A
0x18006f793  lea     rcx, [rsp+2B0h+lpLibFileName]
0x18006f798  call    SczEnsureBackslashTerminated
0x18006f79d  mov     edi, eax
0x18006f79f  test    eax, eax
0x18006f7a1  jns     short loc_18006F7D2
0x18006f7a3  mov     rcx, [rbp+1B8h]; this
0x18006f7aa  mov     r9d, eax; char *
0x18006f7ad  lea     r8, aOnecoreBaseSer_24; "onecore\\base\\servicing\\arbiter\\arbi"...
0x18006f7b4  mov     edx, 0BF1h; void *
0x18006f7b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f7be  nop
0x18006f7bf  test    rbx, rbx
0x18006f7c2  jz      short loc_18006F7CD
0x18006f7c4  mov     rcx, rbx
0x18006f7c7  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18006f7cc  nop
0x18006f7cd  jmp     loc_18006F63A
0x18006f7d2  lea     rdx, aWinreagentDll; "WinREAgent.dll"
0x18006f7d9  lea     rcx, [rsp+2B0h+lpLibFileName]
0x18006f7de  call    SczAllocConcatSz
0x18006f7e3  mov     edi, eax
0x18006f7e5  test    eax, eax
0x18006f7e7  jns     short loc_18006F818
0x18006f7e9  mov     rcx, [rbp+1B8h]; this
0x18006f7f0  mov     r9d, eax; char *
0x18006f7f3  lea     r8, aOnecoreBaseSer_24; "onecore\\base\\servicing\\arbiter\\arbi"...
0x18006f7fa  mov     edx, 0BF2h; void *
0x18006f7ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f804  nop
0x18006f805  test    rbx, rbx
0x18006f808  jz      short loc_18006F813
0x18006f80a  mov     rcx, rbx
0x18006f80d  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18006f812  nop
0x18006f813  jmp     loc_18006F63A
0x18006f818  test    rbx, rbx
0x18006f81b  jz      short loc_18006F826
0x18006f81d  mov     rcx, rbx
0x18006f820  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x18006f825  nop
0x18006f826  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006f82d  test    rcx, rcx
0x18006f830  jz      short loc_18006F841
0x18006f832  lea     rax, [rsp+2B0h+lpLibFileName]
0x18006f837  mov     [rsp+2B0h+var_288], rax
0x18006f83c  call    ??$LogNumObjects@$$BY0P@_WVAutoScz@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEAY0P@$$CB_WAEBVAutoScz@@@Z; LogAdapter::Logger::LogNumObjects<wchar_t [15],AutoScz>(bool,LogAdapter::LogLevel,char const * const,wchar_t const (&)[15],AutoScz const &)
0x18006f841  mov     rcx, [rsp+2B0h+lpLibFileName]
0x18006f846  call    DoesFileExist
0x18006f84b  test    eax, eax
0x18006f84d  jnz     short loc_18006F8BA
0x18006f84f  mov     ebx, 80070002h
0x18006f854  mov     [rsp+2B0h+var_248], ebx
0x18006f858  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18006f85f  test    rcx, rcx
0x18006f862  jz      short loc_18006F8B0
0x18006f864  lea     rax, [rsp+2B0h+lpLibFileName]
0x18006f869  mov     qword ptr [rsp+2B0h+var_290], rax
0x18006f86e  lea     r9, aFile0DoesnTExi; "File [{0}] doesn't exist"
0x18006f875  mov     edi, 3
0x18006f87a  mov     r8d, edi
  ... truncated ...
```
