# GetModulePath(wchar_t * *)

- ea: `0x1400092fc`
- end: `0x140009525`
- name: `?GetModulePath@@YAJPEAPEA_W@Z`
- size: `553`
- prototype: `__int64 __fastcall(wchar_t **)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140007524`
- `0x14000aca8`

## callees

- `0x140002360`
- `0x140002d98`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x1400092fc`
- `0x14000952c`
- `0x140011884`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140009472`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140009472`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x14000934b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x14000934b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400093ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400093ef`

## string_xrefs

- `0x140009405`: `Failed getting module location - path too long`

## pseudocode

```c
int __fastcall GetModulePath(wchar_t **a1)
{
  DWORD ModuleFileNameW; // eax
  signed int LastError; // ebx
  int v4; // edx
  unsigned int v5; // eax
  __int64 v6; // rdx
  int v8; // edx
  unsigned int v9; // eax
  wchar_t *v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // edx
  unsigned int v14; // [rsp+20h] [rbp-E0h]
  unsigned int v15[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v16; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  memset_0(Filename, 0, 0x208u);
  *a1 = 0;
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting module location");
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      else
        v5 = LastError;
      v16 = v5;
      *(_QWORD *)v15 = &v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v4,
        3,
        (unsigned int)": {0}",
        (__int64)v15);
    }
    if ( LastError )
    {
      v6 = 165;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v6,
               (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\util.cpp",
               (const char *)(unsigned int)LastError,
               v14);
    }
    return 0;
  }
  if ( ModuleFileNameW >= 0x104 )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting module location - path too long");
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      else
        v9 = LastError;
      v16 = v9;
      *(_QWORD *)v15 = &v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v8,
        3,
        (unsigned int)": {0}",
        (__int64)v15);
    }
    if ( LastError )
    {
      v6 = 169;
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v6,
               (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\util.cpp",
               (const char *)(unsigned int)LastError,
               v14);
    }
    return 0;
  }
  v10 = wcsrchr(Filename, 0x5Cu);
  if ( v10 )
    *v10 = 0;
  v11 = SczAllocFromSz(a1, Filename);
  v12 = v11;
  if ( v11 >= 0 )
    return 0;
  v16 = v11;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed allocating memory");
    *(_QWORD *)v15 = &v16;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v13,
      3,
      (unsigned int)": {}",
      (__int64)v15);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB3,
    (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\util.cpp",
    (const char *)v12,
    v14);
  return v12;
}

```

## disassembly

```asm
0x1400092fc  mov     [rsp-8+arg_8], rbx
0x140009301  push    rbp
0x140009302  lea     rbp, [rsp-160h]
0x14000930a  sub     rsp, 260h
0x140009311  mov     rax, cs:__security_cookie
0x140009318  xor     rax, rsp
0x14000931b  mov     [rbp+160h+var_10], rax
0x140009322  mov     rbx, rcx
0x140009325  xor     edx, edx; Val
0x140009327  lea     rcx, [rsp+260h+Filename]; void *
0x14000932c  mov     r8d, 208h; Size
0x140009332  call    memset_0
0x140009337  mov     r8d, 104h; nSize
0x14000933d  mov     qword ptr [rbx], 0
0x140009344  lea     rdx, [rsp+260h+Filename]; lpFilename
0x140009349  xor     ecx, ecx; hModule
0x14000934b  call    cs:__imp_GetModuleFileNameW
0x140009351  test    eax, eax
0x140009353  jnz     loc_1400093E8
0x140009359  call    cs:__imp_GetLastError
0x14000935f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009366  mov     ebx, eax
0x140009368  test    rcx, rcx
0x14000936b  jz      short loc_1400093C0
0x14000936d  xor     edx, edx
0x14000936f  lea     r9, aFailedGettingM_0; "Failed getting module location"
0x140009376  lea     r8d, [rdx+3]
0x14000937a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000937f  test    ebx, ebx
0x140009381  jg      short loc_140009387
0x140009383  mov     eax, ebx
0x140009385  jmp     short loc_14000938F
0x140009387  movzx   eax, bx
0x14000938a  or      eax, 80070000h
0x14000938f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140009396  lea     r9, a0; ": {0}"
0x14000939d  mov     [rsp+260h+var_228], eax
0x1400093a1  mov     r8d, 3
0x1400093a7  lea     rax, [rsp+260h+var_228]
0x1400093ac  mov     qword ptr [rsp+260h+var_230], rax
0x1400093b1  lea     rax, [rsp+260h+var_230]
0x1400093b6  mov     qword ptr [rsp+260h+var_240], rax; unsigned int
0x1400093bb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400093c0  test    ebx, ebx
0x1400093c2  jz      loc_140009503
0x1400093c8  mov     edx, 0A5h; void *
0x1400093cd  mov     rcx, [rbp+168h]; this
0x1400093d4  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\pkgmgrshim\\util.cp"...
0x1400093db  mov     r9d, ebx; char *
0x1400093de  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400093e3  jmp     loc_140009505
0x1400093e8  cmp     eax, 104h
0x1400093ed  jb      short loc_140009468
0x1400093ef  call    cs:__imp_GetLastError
0x1400093f5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400093fc  mov     ebx, eax
0x1400093fe  test    rcx, rcx
0x140009401  jz      short loc_140009456
0x140009403  xor     edx, edx
0x140009405  lea     r9, aFailedGettingM_1; "Failed getting module location - path t"...
0x14000940c  lea     r8d, [rdx+3]
0x140009410  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140009415  test    ebx, ebx
0x140009417  jg      short loc_14000941D
0x140009419  mov     eax, ebx
0x14000941b  jmp     short loc_140009425
0x14000941d  movzx   eax, bx
0x140009420  or      eax, 80070000h
0x140009425  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000942c  lea     r9, a0; ": {0}"
0x140009433  mov     [rsp+260h+var_228], eax
0x140009437  mov     r8d, 3
0x14000943d  lea     rax, [rsp+260h+var_228]
0x140009442  mov     qword ptr [rsp+260h+var_230], rax
0x140009447  lea     rax, [rsp+260h+var_230]
0x14000944c  mov     qword ptr [rsp+260h+var_240], rax
0x140009451  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140009456  test    ebx, ebx
0x140009458  jz      loc_140009503
0x14000945e  mov     edx, 0A9h
0x140009463  jmp     loc_1400093CD
0x140009468  mov     edx, 5Ch ; '\'; Ch
0x14000946d  lea     rcx, [rsp+260h+Filename]; Str
0x140009472  call    cs:__imp_wcsrchr
0x140009478  test    rax, rax
0x14000947b  jz      short loc_140009482
0x14000947d  xor     edx, edx
0x14000947f  mov     [rax], dx
0x140009482  lea     rdx, [rsp+260h+Filename]
0x140009487  mov     rcx, rbx
0x14000948a  call    SczAllocFromSz
0x14000948f  mov     ebx, eax
0x140009491  test    eax, eax
0x140009493  jns     short loc_140009503
0x140009495  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000949c  mov     [rsp+260h+var_228], eax
0x1400094a0  test    rcx, rcx
0x1400094a3  jz      short loc_1400094E4
0x1400094a5  xor     edx, edx
0x1400094a7  lea     r9, aFailedAllocati; "Failed allocating memory"
0x1400094ae  lea     r8d, [rdx+3]
0x1400094b2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400094b7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400094be  lea     rax, [rsp+260h+var_228]
0x1400094c3  mov     qword ptr [rsp+260h+var_230], rax
0x1400094c8  lea     r9, asc_14002D4FC; ": {}"
0x1400094cf  lea     rax, [rsp+260h+var_230]
0x1400094d4  mov     r8d, 3
0x1400094da  mov     qword ptr [rsp+260h+var_240], rax; int
0x1400094df  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400094e4  mov     rcx, [rbp+168h]; this
0x1400094eb  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\pkgmgrshim\\util.cp"...
0x1400094f2  mov     r9d, ebx; char *
0x1400094f5  mov     edx, 0B3h; void *
0x1400094fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400094ff  mov     eax, ebx
0x140009501  jmp     short loc_140009505
0x140009503  xor     eax, eax
0x140009505  mov     rcx, [rbp+160h+var_10]
0x14000950c  xor     rcx, rsp; StackCookie
0x14000950f  call    __security_check_cookie
0x140009514  mov     rbx, [rsp+260h+arg_8]
0x14000951c  add     rsp, 260h
0x140009523  pop     rbp
0x140009524  retn
```
