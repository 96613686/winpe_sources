# ComGetImpersonationToken

- ea: `0x140020c84`
- end: `0x140020f32`
- name: `ComGetImpersonationToken`
- size: `686`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001503c`
- `0x1400200b8`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x1400184fc`
- `0x1400208c0`
- `0x140020c84`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020d6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140020e12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140020def`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140020def`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140020e04`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140020e04`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x140020d29`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x140020d29`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140020d85`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140020d85`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x140020d64`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x140020d64`

## string_xrefs

- `0x140020cd4`: `No token handle result specified`
- `0x140020e7e`: `onecore\base\cbs\util\cbscom.cpp`
- `0x140020f03`: `onecore\base\cbs\util\cbscom.cpp`
- `0x140020da5`: `Failed to impersonate client.`
- `0x140020e2b`: `Failed to get user security token`

## pseudocode

```c
__int64 __fastcall ComGetImpersonationToken(void **a1)
{
  int v2; // ebx
  int v3; // edx
  __int64 v4; // rdx
  signed int LastError; // eax
  int v6; // edx
  HANDLE CurrentThread; // rax
  signed int v8; // ebx
  int v9; // edx
  unsigned int v10; // eax
  int v11; // edx
  unsigned int v13; // [rsp+20h] [rbp-40h]
  int v14[2]; // [rsp+30h] [rbp-30h] BYREF
  char v15; // [rsp+38h] [rbp-28h]
  void *ppInterface; // [rsp+40h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-18h] BYREF
  int v18; // [rsp+50h] [rbp-10h] BYREF
  int v19; // [rsp+54h] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  TokenHandle = 0;
  v19 = 0;
  if ( !a1 )
  {
    v2 = -2147467261;
    v18 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No token handle result specified");
      ppInterface = &v18;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v3,
        3,
        (unsigned int)": {}",
        (__int64)&ppInterface);
    }
    v4 = 9;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\cbs\\util\\cbscom.cpp",
      (const char *)(unsigned int)v2,
      v13);
    return (unsigned int)v2;
  }
  ppInterface = 0;
  v2 = CoGetCallContext(&GUID_0000013e_0000_0000_c000_000000000046, &ppInterface);
  if ( v2 == -2147417833 )
  {
    v19 = 1;
  }
  else
  {
    if ( v2 < 0 )
    {
      v18 = v2;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to check RPC context.");
        *(_QWORD *)v14 = &v18;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v11,
          3,
          (unsigned int)": {}",
          (__int64)v14);
      }
      v4 = 29;
      goto LABEL_31;
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppInterface + 16LL))(ppInterface);
    if ( !v19 )
    {
      v2 = CoImpersonateClient();
      goto LABEL_13;
    }
  }
  if ( ImpersonateSelf(SecurityImpersonation) )
    goto LABEL_17;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
LABEL_13:
  if ( v2 < 0 )
  {
    v18 = v2;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to impersonate client.");
      ppInterface = &v18;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v6,
        3,
        (unsigned int)": {}",
        (__int64)&ppInterface);
    }
    v4 = 42;
    goto LABEL_31;
  }
LABEL_17:
  *(_QWORD *)v14 = &v19;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 0, &TokenHandle) )
  {
    *a1 = TokenHandle;
LABEL_26:
    v2 = 0;
    goto LABEL_27;
  }
  v8 = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get user security token");
    if ( v8 > 0 )
      v10 = (unsigned __int16)v8 | 0x80070000;
    else
      v10 = v8;
    v18 = v10;
    ppInterface = &v18;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v9,
      3,
      (unsigned int)": {0}",
      (__int64)&ppInterface);
  }
  if ( !v8 )
    goto LABEL_26;
  v2 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x40,
         (unsigned int)"onecore\\base\\cbs\\util\\cbscom.cpp",
         (const char *)(unsigned int)v8,
         v13);
LABEL_27:
  v15 = 0;
  ComGetImpersonationToken_::_2_::_lambda_1_::operator()(v14);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140020c84  mov     [rsp-8+arg_8], rbx
0x140020c89  mov     [rsp-8+arg_10], rdi
0x140020c8e  push    rbp
0x140020c8f  mov     rbp, rsp
0x140020c92  sub     rsp, 60h
0x140020c96  mov     rax, cs:__security_cookie
0x140020c9d  xor     rax, rsp
0x140020ca0  mov     [rbp+var_8], rax
0x140020ca4  mov     [rbp+TokenHandle], 0
0x140020cac  mov     rdi, rcx
0x140020caf  mov     [rbp+var_C], 0
0x140020cb6  test    rcx, rcx
0x140020cb9  jnz     short loc_140020D16
0x140020cbb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020cc2  mov     ebx, 80004003h
0x140020cc7  mov     [rbp+var_10], ebx
0x140020cca  test    rcx, rcx
0x140020ccd  jz      short loc_140020D0C
0x140020ccf  mov     edi, 3
0x140020cd4  lea     r9, aNoTokenHandleR; "No token handle result specified"
0x140020cdb  mov     r8d, edi
0x140020cde  xor     edx, edx
0x140020ce0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140020ce5  lea     rcx, [rbp+ppInterface]
0x140020ce9  mov     r8d, edi
0x140020cec  mov     qword ptr [rsp+60h+var_40], rcx
0x140020cf1  lea     rax, [rbp+var_10]
0x140020cf5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020cfc  lea     r9, asc_1400353E8; ": {}"
0x140020d03  mov     [rbp+ppInterface], rax
0x140020d07  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140020d0c  mov     edx, 9
0x140020d11  jmp     loc_140020EFF
0x140020d16  lea     rdx, [rbp+ppInterface]; ppInterface
0x140020d1a  mov     [rbp+ppInterface], 0
0x140020d22  lea     rcx, _GUID_0000013e_0000_0000_c000_000000000046; riid
0x140020d29  call    cs:__imp_CoGetCallContext
0x140020d2f  mov     ebx, eax
0x140020d31  cmp     eax, 80010117h
0x140020d36  jnz     short loc_140020D41
0x140020d38  mov     [rbp+var_C], 1
0x140020d3f  jmp     short loc_140020D5F
0x140020d41  test    ebx, ebx
0x140020d43  js      loc_140020EAE
0x140020d49  mov     rcx, [rbp+ppInterface]
0x140020d4d  mov     rax, [rcx]
0x140020d50  mov     rax, [rax+10h]
0x140020d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140020d59  cmp     [rbp+var_C], 0
0x140020d5d  jz      short loc_140020D85
0x140020d5f  mov     ecx, 2; ImpersonationLevel
0x140020d64  call    cs:__imp_ImpersonateSelf
0x140020d6a  test    eax, eax
0x140020d6c  jnz     short loc_140020DE7
0x140020d6e  call    cs:__imp_GetLastError
0x140020d74  mov     ebx, eax
0x140020d76  test    eax, eax
0x140020d78  jle     short loc_140020D8D
0x140020d7a  movzx   ebx, ax
0x140020d7d  or      ebx, 80070000h
0x140020d83  jmp     short loc_140020D8D
0x140020d85  call    cs:__imp_CoImpersonateClient
0x140020d8b  mov     ebx, eax
0x140020d8d  test    ebx, ebx
0x140020d8f  jns     short loc_140020DE7
0x140020d91  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020d98  mov     [rbp+var_10], ebx
0x140020d9b  test    rcx, rcx
0x140020d9e  jz      short loc_140020DDD
0x140020da0  mov     edi, 3
0x140020da5  lea     r9, aFailedToImpers; "Failed to impersonate client."
0x140020dac  mov     r8d, edi
0x140020daf  xor     edx, edx
0x140020db1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140020db6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020dbd  lea     rax, [rbp+var_10]
0x140020dc1  mov     [rbp+ppInterface], rax
0x140020dc5  lea     r9, asc_1400353E8; ": {}"
0x140020dcc  lea     rax, [rbp+ppInterface]
0x140020dd0  mov     r8d, edi
0x140020dd3  mov     qword ptr [rsp+60h+var_40], rax
0x140020dd8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140020ddd  mov     edx, 2Ah ; '*'
0x140020de2  jmp     loc_140020EFF
0x140020de7  lea     rax, [rbp+var_C]
0x140020deb  mov     qword ptr [rbp+var_30], rax
0x140020def  call    cs:__imp_GetCurrentThread
0x140020df5  lea     r9, [rbp+TokenHandle]; TokenHandle
0x140020df9  xor     r8d, r8d; OpenAsSelf
0x140020dfc  mov     rcx, rax; ThreadHandle
0x140020dff  mov     edx, 0F01FFh; DesiredAccess
0x140020e04  call    cs:__imp_OpenThreadToken
0x140020e0a  test    eax, eax
0x140020e0c  jnz     loc_140020E96
0x140020e12  call    cs:__imp_GetLastError
0x140020e18  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020e1f  mov     ebx, eax
0x140020e21  test    rcx, rcx
0x140020e24  jz      short loc_140020E76
0x140020e26  mov     edi, 3
0x140020e2b  lea     r9, aFailedToGetUse_0; "Failed to get user security token"
0x140020e32  mov     r8d, edi
0x140020e35  xor     edx, edx
0x140020e37  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140020e3c  test    ebx, ebx
0x140020e3e  jg      short loc_140020E44
0x140020e40  mov     eax, ebx
0x140020e42  jmp     short loc_140020E4C
0x140020e44  movzx   eax, bx
0x140020e47  or      eax, 80070000h
0x140020e4c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020e53  lea     r9, a0; ": {0}"
0x140020e5a  mov     [rbp+var_10], eax
0x140020e5d  mov     r8d, edi
0x140020e60  lea     rax, [rbp+var_10]
0x140020e64  mov     [rbp+ppInterface], rax
0x140020e68  lea     rax, [rbp+ppInterface]
0x140020e6c  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x140020e71  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140020e76  test    ebx, ebx
0x140020e78  jz      short loc_140020E9D
0x140020e7a  mov     rcx, [rbp+8]; this
0x140020e7e  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\util\\cbscom.cpp"
0x140020e85  mov     r9d, ebx; char *
0x140020e88  mov     edx, 40h ; '@'; void *
0x140020e8d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140020e92  mov     ebx, eax
0x140020e94  jmp     short loc_140020E9F
0x140020e96  mov     rax, [rbp+TokenHandle]
0x140020e9a  mov     [rdi], rax
0x140020e9d  xor     ebx, ebx
0x140020e9f  lea     rcx, [rbp+var_30]
0x140020ea3  mov     [rbp+var_28], 0
0x140020ea7  call    _ComGetImpersonationToken____2____lambda_1___operator__
0x140020eac  jmp     short loc_140020F12
0x140020eae  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020eb5  mov     [rbp+var_10], ebx
0x140020eb8  test    rcx, rcx
0x140020ebb  jz      short loc_140020EFA
0x140020ebd  mov     edi, 3
0x140020ec2  lea     r9, aFailedToCheckR; "Failed to check RPC context."
0x140020ec9  mov     r8d, edi
0x140020ecc  xor     edx, edx
0x140020ece  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140020ed3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020eda  lea     rax, [rbp+var_10]
0x140020ede  mov     qword ptr [rbp+var_30], rax
0x140020ee2  lea     r9, asc_1400353E8; ": {}"
0x140020ee9  lea     rax, [rbp+var_30]
0x140020eed  mov     r8d, edi
0x140020ef0  mov     qword ptr [rsp+60h+var_40], rax; int
0x140020ef5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140020efa  mov     edx, 1Dh; void *
0x140020eff  mov     rcx, [rbp+8]; this
0x140020f03  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\util\\cbscom.cpp"
0x140020f0a  mov     r9d, ebx; char *
0x140020f0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140020f12  mov     eax, ebx
0x140020f14  mov     rcx, [rbp+var_8]
0x140020f18  xor     rcx, rsp; StackCookie
0x140020f1b  call    __security_check_cookie
0x140020f20  lea     r11, [rsp+60h+var_s0]
0x140020f25  mov     rbx, [r11+18h]
0x140020f29  mov     rdi, [r11+20h]
0x140020f2d  mov     rsp, r11
0x140020f30  pop     rbp
0x140020f31  retn
```
