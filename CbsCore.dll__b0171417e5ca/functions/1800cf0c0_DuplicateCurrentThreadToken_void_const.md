# DuplicateCurrentThreadToken(void * * const)

- ea: `0x1800cf0c0`
- end: `0x1800cf2e8`
- name: `?DuplicateCurrentThreadToken@@YAJQEAPEAX@Z`
- size: `552`
- prototype: `__int64 __fastcall(PHANDLE Thread)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1800cc408`

## callees

- `0x18002e280`
- `0x18002ec34`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800cf0c0`
- `0x1800eb920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf232`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cf232`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cf189`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cf189`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cf16c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800cf16c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cf21e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800cf21e`

## string_xrefs

- `0x1800cf251`: `Failed to set thread token to current thread token`
- `0x1800cf1b8`: `Failed to open current thread token`
- `0x1800cf101`: `No thread handle specified`

## pseudocode

```c
__int64 __fastcall DuplicateCurrentThreadToken(PHANDLE Thread)
{
  unsigned int v2; // ebx
  void **InitPointer; // rbx
  HANDLE CurrentThread; // rax
  signed int LastError; // ebx
  unsigned int v6; // eax
  __int64 v7; // rdx
  unsigned int v8; // eax
  unsigned int v10; // [rsp+20h] [rbp-30h]
  unsigned int v11[2]; // [rsp+30h] [rbp-20h] BYREF
  int v12; // [rsp+38h] [rbp-18h] BYREF
  HANDLE Token; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  if ( Thread )
  {
    Token = 0;
    InitPointer = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(&Token);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0x2000Eu, 1, InitPointer) )
    {
      if ( !SetThreadToken(Thread, Token) )
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to set thread token to current thread token");
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          else
            v8 = LastError;
          v12 = v8;
          *(_QWORD *)v11 = &v12;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v11);
        }
        if ( LastError )
        {
          v7 = 310;
          goto LABEL_21;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to open current thread token");
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        else
          v6 = LastError;
        v12 = v6;
        *(_QWORD *)v11 = &v12;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v11);
      }
      if ( LastError )
      {
        v7 = 308;
LABEL_21:
        v2 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v7,
               (unsigned int)"onecore\\base\\cbs\\core\\cbsdpxwrapper.cpp",
               (const char *)(unsigned int)LastError,
               v10);
LABEL_23:
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&Token);
        return v2;
      }
    }
    v2 = 0;
    goto LABEL_23;
  }
  v2 = -2147024809;
  v12 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No thread handle specified");
    *(_QWORD *)v11 = &v12;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)v11);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x12F,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsdpxwrapper.cpp",
    (const char *)0x80070057LL,
    v10);
  return v2;
}

```

## disassembly

```asm
0x1800cf0c0  mov     [rsp-8+arg_8], rbx
0x1800cf0c5  mov     [rsp-8+arg_10], rdi
0x1800cf0ca  push    rbp
0x1800cf0cb  mov     rbp, rsp
0x1800cf0ce  sub     rsp, 50h
0x1800cf0d2  mov     rax, cs:__security_cookie
0x1800cf0d9  xor     rax, rsp
0x1800cf0dc  mov     [rbp+var_8], rax
0x1800cf0e0  mov     rdi, rcx
0x1800cf0e3  test    rcx, rcx
0x1800cf0e6  jnz     short loc_1800CF158
0x1800cf0e8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cf0ef  mov     ebx, 80070057h
0x1800cf0f4  mov     [rbp+var_18], ebx
0x1800cf0f7  test    rcx, rcx
0x1800cf0fa  jz      short loc_1800CF13B
0x1800cf0fc  mov     edi, 3
0x1800cf101  lea     r9, aNoThreadHandle; "No thread handle specified"
0x1800cf108  mov     r8d, edi
0x1800cf10b  xor     edx, edx
0x1800cf10d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cf112  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cf119  lea     rax, [rbp+var_18]
0x1800cf11d  mov     qword ptr [rbp+var_20], rax
0x1800cf121  lea     r9, asc_1802EE7AC; ": {}"
0x1800cf128  lea     rax, [rbp+var_20]
0x1800cf12c  mov     r8d, edi
0x1800cf12f  mov     dl, 1
0x1800cf131  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800cf136  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cf13b  mov     rcx, [rbp+8]; this
0x1800cf13f  lea     r8, aOnecoreBaseCbs_82; "onecore\\base\\cbs\\core\\cbsdpxwrapper"...
0x1800cf146  mov     r9d, ebx; char *
0x1800cf149  mov     edx, 12Fh; void *
0x1800cf14e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cf153  jmp     loc_1800CF2C9
0x1800cf158  lea     rcx, [rbp+Token]
0x1800cf15c  mov     [rbp+Token], 0
0x1800cf164  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x1800cf169  mov     rbx, rax
0x1800cf16c  call    cs:__imp_GetCurrentThread
0x1800cf173  nop     dword ptr [rax+rax+00h]
0x1800cf178  mov     r9, rbx; TokenHandle
0x1800cf17b  mov     edx, 2000Eh; DesiredAccess
0x1800cf180  mov     rcx, rax; ThreadHandle
0x1800cf183  mov     r8d, 1; OpenAsSelf
0x1800cf189  call    cs:__imp_OpenThreadToken
0x1800cf190  nop     dword ptr [rax+rax+00h]
0x1800cf195  test    eax, eax
0x1800cf197  jnz     short loc_1800CF217
0x1800cf199  call    cs:__imp_GetLastError
0x1800cf1a0  nop     dword ptr [rax+rax+00h]
0x1800cf1a5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cf1ac  mov     ebx, eax
0x1800cf1ae  test    rcx, rcx
0x1800cf1b1  jz      short loc_1800CF205
0x1800cf1b3  mov     edi, 3
0x1800cf1b8  lea     r9, aFailedToOpenCu_0; "Failed to open current thread token"
0x1800cf1bf  mov     r8d, edi
0x1800cf1c2  xor     edx, edx
0x1800cf1c4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cf1c9  test    ebx, ebx
0x1800cf1cb  jg      short loc_1800CF1D1
0x1800cf1cd  mov     eax, ebx
0x1800cf1cf  jmp     short loc_1800CF1D9
0x1800cf1d1  movzx   eax, bx
0x1800cf1d4  or      eax, 80070000h
0x1800cf1d9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cf1e0  lea     r9, a0; ": {0}"
0x1800cf1e7  mov     [rbp+var_18], eax
0x1800cf1ea  mov     r8d, edi
0x1800cf1ed  lea     rax, [rbp+var_18]
0x1800cf1f1  mov     dl, 1
0x1800cf1f3  mov     qword ptr [rbp+var_20], rax
0x1800cf1f7  lea     rax, [rbp+var_20]
0x1800cf1fb  mov     qword ptr [rsp+50h+var_30], rax
0x1800cf200  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cf205  test    ebx, ebx
0x1800cf207  jz      loc_1800CF2BE
0x1800cf20d  mov     edx, 134h
0x1800cf212  jmp     loc_1800CF2A7
0x1800cf217  mov     rdx, [rbp+Token]; Token
0x1800cf21b  mov     rcx, rdi; Thread
0x1800cf21e  call    cs:__imp_SetThreadToken
0x1800cf225  nop     dword ptr [rax+rax+00h]
0x1800cf22a  test    eax, eax
0x1800cf22c  jnz     loc_1800CF2BE
0x1800cf232  call    cs:__imp_GetLastError
0x1800cf239  nop     dword ptr [rax+rax+00h]
0x1800cf23e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cf245  mov     ebx, eax
0x1800cf247  test    rcx, rcx
0x1800cf24a  jz      short loc_1800CF29E
0x1800cf24c  mov     edi, 3
0x1800cf251  lea     r9, aFailedToSetThr; "Failed to set thread token to current t"...
0x1800cf258  mov     r8d, edi
0x1800cf25b  xor     edx, edx
0x1800cf25d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800cf262  test    ebx, ebx
0x1800cf264  jg      short loc_1800CF26A
0x1800cf266  mov     eax, ebx
0x1800cf268  jmp     short loc_1800CF272
0x1800cf26a  movzx   eax, bx
0x1800cf26d  or      eax, 80070000h
0x1800cf272  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800cf279  lea     r9, a0; ": {0}"
0x1800cf280  mov     [rbp+var_18], eax
0x1800cf283  mov     r8d, edi
0x1800cf286  lea     rax, [rbp+var_18]
0x1800cf28a  mov     dl, 1
0x1800cf28c  mov     qword ptr [rbp+var_20], rax
0x1800cf290  lea     rax, [rbp+var_20]
0x1800cf294  mov     qword ptr [rsp+50h+var_30], rax; unsigned int
0x1800cf299  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800cf29e  test    ebx, ebx
0x1800cf2a0  jz      short loc_1800CF2BE
0x1800cf2a2  mov     edx, 136h; void *
0x1800cf2a7  mov     rcx, [rbp+8]; this
0x1800cf2ab  lea     r8, aOnecoreBaseCbs_82; "onecore\\base\\cbs\\core\\cbsdpxwrapper"...
0x1800cf2b2  mov     r9d, ebx; char *
0x1800cf2b5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cf2ba  mov     ebx, eax
0x1800cf2bc  jmp     short loc_1800CF2C0
0x1800cf2be  xor     ebx, ebx
0x1800cf2c0  lea     rcx, [rbp+Token]
0x1800cf2c4  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1800cf2c9  mov     eax, ebx
0x1800cf2cb  mov     rcx, [rbp+var_8]
0x1800cf2cf  xor     rcx, rsp; StackCookie
0x1800cf2d2  call    __security_check_cookie
0x1800cf2d7  mov     rbx, [rsp+50h+arg_8]
0x1800cf2dc  mov     rdi, [rsp+50h+arg_10]
0x1800cf2e1  add     rsp, 50h
0x1800cf2e5  pop     rbp
0x1800cf2e6  retn
```
