# ImpersonateToken

- ea: `0x18004797c`
- end: `0x180047d73`
- name: `ImpersonateToken`
- size: `1015`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1801b164c`

## callees

- `0x1800031d0`
- `0x180006484`
- `0x18000ba40`
- `0x18000f614`
- `0x18000f874`
- `0x1800296a4`
- `0x18004797c`

## import_xrefs

- `ntdll!NtClose` at `0x180047bfe`
- `ntdll!NtClose` at `0x180047cd8`
- `ntdll!NtClose` at `0x180047d2c`
- `ntdll!NtClose` at `0x180047bfe`
- `ntdll!NtClose` at `0x180047cd8`
- `ntdll!NtClose` at `0x180047d2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180047b2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180047b2d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180047c2c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180047c2c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180047b47`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180047b47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047b5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047c40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047b5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047c40`

## string_xrefs

- `0x1800479c8`: `No token specified`
- `0x180047a5a`: `Already impersonating`
- `0x180047adc`: `Already impersonating`
- `0x180047b80`: `Failed to impersonate token.`
- `0x180047c5a`: `Failed to impersonate token.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ImpersonateToken(HANDLE Token)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rdx
  HANDLE CurrentThread; // rax
  signed int v10; // esi
  __int64 v11; // rdx
  unsigned int v12; // eax
  signed int LastError; // ebx
  __int64 v14; // rdx
  unsigned int v15; // eax
  void *v16; // rcx
  unsigned int *v17; // [rsp+20h] [rbp-40h]
  unsigned int v18[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v19; // [rsp+38h] [rbp-28h]
  int v20; // [rsp+40h] [rbp-20h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v19 = -2;
  if ( !Token )
  {
    v2 = -2147024809;
    v20 = -2147024809;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "No token specified");
      *(_QWORD *)v18 = &v20;
      v17 = v18;
      LOBYTE(v3) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v3,
        3,
        ": {}");
    }
    v4 = 142;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
      (const char *)v2,
      (int)v17);
    return v2;
  }
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( *(_QWORD *)(v6 + 312) )
  {
    v2 = -2146498560;
    v20 = -2146498560;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Already impersonating");
      *(_QWORD *)v18 = &v20;
      v17 = v18;
      LOBYTE(v7) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v7,
        3,
        ": {}");
    }
    v4 = 143;
    goto LABEL_5;
  }
  if ( !*(_BYTE *)(v6 + 16) )
    _dyn_tls_on_demand_init();
  if ( (unsigned __int64)(*(_QWORD *)(v6 + 336) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v2 = -2146498560;
    v20 = -2146498560;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Already impersonating");
      *(_QWORD *)v18 = &v20;
      v17 = v18;
      LOBYTE(v8) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v8,
        3,
        ": {}");
    }
    v4 = 144;
    goto LABEL_5;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 0, &TokenHandle) || (v10 = GetLastError(), v10 == 1008) )
  {
    if ( SetThreadToken(0, Token) )
    {
      *(_QWORD *)(v6 + 312) = Token;
      if ( !*(_BYTE *)(v6 + 16) )
        _dyn_tls_on_demand_init();
      v16 = TokenHandle;
      TokenHandle = *(void **)(v6 + 336);
      *(_QWORD *)(v6 + 336) = v16;
    }
    else
    {
      LastError = GetLastError();
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to impersonate token.");
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
        else
          v15 = LastError;
        v20 = v15;
        *(_QWORD *)v18 = &v20;
        v17 = v18;
        LOBYTE(v14) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v14,
          3,
          ": {0}");
      }
      if ( LastError )
      {
        v2 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x9C,
               (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
               (const char *)(unsigned int)LastError,
               (unsigned int)v17);
        if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          if ( NtClose(TokenHandle) < 0 )
            __fastfail(7u);
          TokenHandle = 0;
        }
        return v2;
      }
    }
  }
  else
  {
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to impersonate token.");
      if ( v10 > 0 )
        v12 = (unsigned __int16)v10 | 0x80070000;
      else
        v12 = v10;
      v20 = v12;
      *(_QWORD *)v18 = &v20;
      v17 = v18;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v11,
        3,
        ": {0}");
    }
    if ( v10 )
    {
      v2 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x98,
             (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
             (const char *)(unsigned int)v10,
             (unsigned int)v17);
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        if ( NtClose(TokenHandle) < 0 )
          __fastfail(7u);
        TokenHandle = 0;
      }
      return v2;
    }
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    if ( NtClose(TokenHandle) < 0 )
      __fastfail(7u);
    TokenHandle = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18004797c  mov     rax, rsp
0x18004797f  push    rbp
0x180047980  push    rdi
0x180047981  push    r12
0x180047983  push    r13
0x180047985  push    r15
0x180047987  mov     rbp, rsp
0x18004798a  sub     rsp, 60h
0x18004798e  mov     [rbp+var_28], 0FFFFFFFFFFFFFFFEh
0x180047996  mov     [rax+10h], rbx
0x18004799a  mov     [rax+18h], rsi
0x18004799e  mov     rax, cs:__security_cookie
0x1800479a5  xor     rax, rsp
0x1800479a8  mov     [rbp+var_10], rax
0x1800479ac  mov     rdi, rcx
0x1800479af  test    rcx, rcx
0x1800479b2  jnz     short loc_180047A26
0x1800479b4  mov     ebx, 80070057h
0x1800479b9  mov     [rbp+var_20], ebx
0x1800479bc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800479c3  test    rcx, rcx
0x1800479c6  jz      short loc_180047A07
0x1800479c8  lea     r9, aNoTokenSpecifi; "No token specified"
0x1800479cf  mov     edi, 3
0x1800479d4  mov     r8d, edi
0x1800479d7  xor     edx, edx
0x1800479d9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800479de  lea     rax, [rbp+var_20]
0x1800479e2  mov     qword ptr [rbp+var_30], rax
0x1800479e6  lea     rax, [rbp+var_30]
0x1800479ea  mov     qword ptr [rsp+60h+var_40], rax; int
0x1800479ef  lea     r9, asc_1801CAFB4; ": {}"
0x1800479f6  mov     r8d, edi
0x1800479f9  mov     dl, 1
0x1800479fb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047a02  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180047a07  mov     edx, 8Eh; void *
0x180047a0c  mov     rcx, [rbp+28h]; this
0x180047a10  mov     r9d, ebx; char *
0x180047a13  lea     r8, aOnecoreBaseCbs_14; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x180047a1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047a1f  mov     eax, ebx
0x180047a21  jmp     loc_180047D4D
0x180047a26  mov     ecx, cs:_tls_index
0x180047a2c  mov     rax, gs:58h
0x180047a35  mov     rbx, [rax+rcx*8]
0x180047a39  mov     r13d, 138h
0x180047a3f  cmp     qword ptr [rbx+r13], 0
0x180047a44  jz      short loc_180047AA3
0x180047a46  mov     ebx, 800F0800h
0x180047a4b  mov     [rbp+var_20], ebx
0x180047a4e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047a55  test    rcx, rcx
0x180047a58  jz      short loc_180047A99
0x180047a5a  lea     r9, aAlreadyImperso; "Already impersonating"
0x180047a61  mov     edi, 3
0x180047a66  mov     r8d, edi
0x180047a69  xor     edx, edx
0x180047a6b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180047a70  lea     rax, [rbp+var_20]
0x180047a74  mov     qword ptr [rbp+var_30], rax
0x180047a78  lea     rax, [rbp+var_30]
0x180047a7c  mov     qword ptr [rsp+60h+var_40], rax
0x180047a81  lea     r9, asc_1801CAFB4; ": {}"
0x180047a88  mov     r8d, edi
0x180047a8b  mov     dl, 1
0x180047a8d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047a94  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180047a99  mov     edx, 8Fh
0x180047a9e  jmp     loc_180047A0C
0x180047aa3  mov     r12d, 10h
0x180047aa9  cmp     byte ptr [r12+rbx], 0
0x180047aae  jnz     short loc_180047AB5
0x180047ab0  call    __dyn_tls_on_demand_init
0x180047ab5  mov     r15d, 150h
0x180047abb  mov     rax, [r15+rbx]
0x180047abf  dec     rax
0x180047ac2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180047ac6  ja      short loc_180047B25
0x180047ac8  mov     ebx, 800F0800h
0x180047acd  mov     [rbp+var_20], ebx
0x180047ad0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047ad7  test    rcx, rcx
0x180047ada  jz      short loc_180047B1B
0x180047adc  lea     r9, aAlreadyImperso; "Already impersonating"
0x180047ae3  mov     edi, 3
0x180047ae8  mov     r8d, edi
0x180047aeb  xor     edx, edx
0x180047aed  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180047af2  lea     rax, [rbp+var_20]
0x180047af6  mov     qword ptr [rbp+var_30], rax
0x180047afa  lea     rax, [rbp+var_30]
0x180047afe  mov     qword ptr [rsp+60h+var_40], rax
0x180047b03  lea     r9, asc_1801CAFB4; ": {}"
0x180047b0a  mov     r8d, edi
0x180047b0d  mov     dl, 1
0x180047b0f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047b16  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180047b1b  mov     edx, 90h
0x180047b20  jmp     loc_180047A0C
0x180047b25  mov     [rbp+TokenHandle], 0
0x180047b2d  call    cs:__imp_GetCurrentThread
0x180047b34  nop     dword ptr [rax+rax+00h]
0x180047b39  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180047b3d  xor     r8d, r8d; OpenAsSelf
0x180047b40  lea     edx, [r8+0Ch]; DesiredAccess
0x180047b44  mov     rcx, rax; ThreadHandle
0x180047b47  call    cs:__imp_OpenThreadToken
0x180047b4e  nop     dword ptr [rax+rax+00h]
0x180047b53  test    eax, eax
0x180047b55  jnz     loc_180047C27
0x180047b5b  call    cs:__imp_GetLastError
0x180047b62  nop     dword ptr [rax+rax+00h]
0x180047b67  mov     esi, eax
0x180047b69  cmp     eax, 3F0h
0x180047b6e  jz      loc_180047C27
0x180047b74  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047b7b  test    rcx, rcx
0x180047b7e  jz      short loc_180047BD2
0x180047b80  lea     r9, aFailedToImpers_0; "Failed to impersonate token."
0x180047b87  mov     edi, 3
0x180047b8c  mov     r8d, edi
0x180047b8f  xor     edx, edx
0x180047b91  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180047b96  test    esi, esi
0x180047b98  jg      short loc_180047B9E
0x180047b9a  mov     eax, esi
0x180047b9c  jmp     short loc_180047BA6
0x180047b9e  movzx   eax, si
0x180047ba1  or      eax, 80070000h
0x180047ba6  mov     [rbp+var_20], eax
0x180047ba9  lea     rax, [rbp+var_20]
0x180047bad  mov     qword ptr [rbp+var_30], rax
0x180047bb1  lea     rax, [rbp+var_30]
0x180047bb5  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x180047bba  lea     r9, a0; ": {0}"
0x180047bc1  mov     r8d, edi
0x180047bc4  mov     dl, 1
0x180047bc6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047bcd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180047bd2  test    esi, esi
0x180047bd4  jz      short loc_180047C22
0x180047bd6  mov     rcx, [rbp+28h]; this
0x180047bda  mov     r9d, esi; char *
0x180047bdd  lea     r8, aOnecoreBaseCbs_14; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x180047be4  mov     edx, 98h; void *
0x180047be9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180047bee  mov     ebx, eax
0x180047bf0  mov     rcx, [rbp+TokenHandle]; Handle
0x180047bf4  lea     rdx, [rcx-1]
0x180047bf8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180047bfc  ja      short loc_180047C1D
0x180047bfe  call    cs:__imp_NtClose
0x180047c05  nop     dword ptr [rax+rax+00h]
0x180047c0a  test    eax, eax
0x180047c0c  jns     short loc_180047C15
0x180047c0e  mov     ecx, 7
0x180047c13  int     29h; Win8: RtlFailFast(ecx)
0x180047c15  mov     [rbp+TokenHandle], 0
0x180047c1d  jmp     loc_180047A1F
0x180047c22  jmp     loc_180047D1E
0x180047c27  mov     rdx, rdi; Token
0x180047c2a  xor     ecx, ecx; Thread
0x180047c2c  call    cs:__imp_SetThreadToken
0x180047c33  nop     dword ptr [rax+rax+00h]
0x180047c38  test    eax, eax
0x180047c3a  jnz     loc_180047CFE
0x180047c40  call    cs:__imp_GetLastError
0x180047c47  nop     dword ptr [rax+rax+00h]
0x180047c4c  mov     ebx, eax
0x180047c4e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047c55  test    rcx, rcx
0x180047c58  jz      short loc_180047CAC
0x180047c5a  lea     r9, aFailedToImpers_0; "Failed to impersonate token."
0x180047c61  mov     edi, 3
0x180047c66  mov     r8d, edi
0x180047c69  xor     edx, edx
0x180047c6b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180047c70  test    ebx, ebx
0x180047c72  jg      short loc_180047C78
0x180047c74  mov     eax, ebx
0x180047c76  jmp     short loc_180047C80
0x180047c78  movzx   eax, bx
0x180047c7b  or      eax, 80070000h
0x180047c80  mov     [rbp+var_20], eax
0x180047c83  lea     rax, [rbp+var_20]
0x180047c87  mov     qword ptr [rbp+var_30], rax
0x180047c8b  lea     rax, [rbp+var_30]
0x180047c8f  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x180047c94  lea     r9, a0; ": {0}"
0x180047c9b  mov     r8d, edi
0x180047c9e  mov     dl, 1
0x180047ca0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180047ca7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180047cac  test    ebx, ebx
0x180047cae  jz      short loc_180047CFC
0x180047cb0  mov     rcx, [rbp+28h]; this
0x180047cb4  mov     r9d, ebx; char *
0x180047cb7  lea     r8, aOnecoreBaseCbs_14; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x180047cbe  mov     edx, 9Ch; void *
0x180047cc3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180047cc8  mov     ebx, eax
0x180047cca  mov     rcx, [rbp+TokenHandle]; Handle
0x180047cce  lea     rdx, [rcx-1]
0x180047cd2  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180047cd6  ja      short loc_180047CF7
0x180047cd8  call    cs:__imp_NtClose
0x180047cdf  nop     dword ptr [rax+rax+00h]
0x180047ce4  test    eax, eax
0x180047ce6  jns     short loc_180047CEF
0x180047ce8  mov     ecx, 7
0x180047ced  int     29h; Win8: RtlFailFast(ecx)
0x180047cef  mov     [rbp+TokenHandle], 0
0x180047cf7  jmp     loc_180047A1F
0x180047cfc  jmp     short loc_180047D1E
0x180047cfe  mov     [rbx+r13], rdi
0x180047d02  cmp     byte ptr [r12+rbx], 0
0x180047d07  jnz     short loc_180047D0E
0x180047d09  call    __dyn_tls_on_demand_init
0x180047d0e  mov     rcx, [rbp+TokenHandle]
0x180047d12  mov     rax, [r15+rbx]
0x180047d16  mov     [rbp+TokenHandle], rax
0x180047d1a  mov     [r15+rbx], rcx
0x180047d1e  mov     rcx, [rbp+TokenHandle]; Handle
0x180047d22  lea     rax, [rcx-1]
0x180047d26  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180047d2a  ja      short loc_180047D4B
0x180047d2c  call    cs:__imp_NtClose
0x180047d33  nop     dword ptr [rax+rax+00h]
0x180047d38  test    eax, eax
0x180047d3a  jns     short loc_180047D43
0x180047d3c  mov     ecx, 7
0x180047d41  int     29h; Win8: RtlFailFast(ecx)
0x180047d43  mov     [rbp+TokenHandle], 0
0x180047d4b  xor     eax, eax
0x180047d4d  mov     rcx, [rbp+var_10]
0x180047d51  xor     rcx, rsp; StackCookie
0x180047d54  call    __security_check_cookie
0x180047d59  lea     r11, [rsp+60h+var_s0]
0x180047d5e  mov     rbx, [r11+38h]
0x180047d62  mov     rsi, [r11+40h]
0x180047d66  mov     rsp, r11
0x180047d69  pop     r15
0x180047d6b  pop     r13
0x180047d6d  pop     r12
0x180047d6f  pop     rdi
0x180047d70  pop     rbp
0x180047d71  retn
```
