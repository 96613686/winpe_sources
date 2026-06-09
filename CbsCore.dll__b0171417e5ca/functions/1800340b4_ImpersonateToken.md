# ImpersonateToken

- ea: `0x1800340b4`
- end: `0x18003440e`
- name: `ImpersonateToken`
- size: `858`
- prototype: `__int64 __fastcall(HANDLE Token)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18003404c`
- `0x1800ac994`

## callees

- `0x18002e280`
- `0x18002ec34`
- `0x1800340b4`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x1800ebdc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003432f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034291`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003432f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003427d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003427d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034264`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180034264`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003431b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18003431b`

## string_xrefs

- `0x1800342b7`: `Failed to impersonate token.`
- `0x18003434e`: `Failed to impersonate token.`
- `0x1800340ff`: `No token specified`
- `0x18003418a`: `Already impersonating`
- `0x18003420c`: `Already impersonating`

## pseudocode

```c
__int64 __fastcall ImpersonateToken(HANDLE Token)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rdi
  void **InitPointer; // rbx
  HANDLE CurrentThread; // rax
  signed int LastError; // ebx
  unsigned int v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // eax
  bool v11; // zf
  __int64 v12; // rcx
  unsigned int v14; // [rsp+20h] [rbp-30h]
  unsigned int v15[2]; // [rsp+30h] [rbp-20h] BYREF
  int v16; // [rsp+38h] [rbp-18h] BYREF
  __int64 v17; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  if ( Token )
  {
    v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    if ( *(_QWORD *)(v4 + 4896) )
    {
      v2 = -2146498560;
      v16 = -2146498560;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Already impersonating");
        *(_QWORD *)v15 = &v16;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v15);
      }
      v3 = 143;
      goto LABEL_5;
    }
    if ( !*(_BYTE *)(v4 + 4080) )
      _dyn_tls_on_demand_init();
    if ( (unsigned __int64)(*(_QWORD *)(v4 + 4912) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v2 = -2146498560;
      v16 = -2146498560;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Already impersonating");
        *(_QWORD *)v15 = &v16;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v15);
      }
      v3 = 144;
      goto LABEL_5;
    }
    v17 = 0;
    InitPointer = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(&v17);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xCu, 0, InitPointer) || (LastError = GetLastError(), LastError == 1008) )
    {
      if ( SetThreadToken(0, Token) )
      {
        v11 = *(_BYTE *)(v4 + 4080) == 0;
        *(_QWORD *)(v4 + 4896) = Token;
        if ( v11 )
          _dyn_tls_on_demand_init();
        v12 = v17;
        v17 = *(_QWORD *)(v4 + 4912);
        *(_QWORD *)(v4 + 4912) = v12;
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
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to impersonate token.");
          if ( LastError > 0 )
            v10 = (unsigned __int16)LastError | 0x80070000;
          else
            v10 = LastError;
          v16 = v10;
          *(_QWORD *)v15 = &v16;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v15);
        }
        if ( LastError )
        {
          v9 = 156;
          goto LABEL_33;
        }
      }
    }
    else
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to impersonate token.");
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        else
          v8 = LastError;
        v16 = v8;
        *(_QWORD *)v15 = &v16;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v15);
      }
      if ( LastError )
      {
        v9 = 152;
LABEL_33:
        v2 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v9,
               (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
               (const char *)(unsigned int)LastError,
               v14);
LABEL_38:
        Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v17);
        return v2;
      }
    }
    v2 = 0;
    goto LABEL_38;
  }
  v2 = -2147024809;
  v16 = -2147024809;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"No token specified");
    *(_QWORD *)v15 = &v16;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {}",
      (__int64)v15);
  }
  v3 = 142;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
    (const char *)v2,
    v14);
  return v2;
}

```

## disassembly

```asm
0x1800340b4  mov     [rsp-28h+arg_8], rbx
0x1800340b9  mov     [rsp-28h+arg_10], rsi
0x1800340be  push    rbp
0x1800340bf  push    rdi
0x1800340c0  push    r12
0x1800340c2  push    r13
0x1800340c4  push    r15
0x1800340c6  mov     rbp, rsp
0x1800340c9  sub     rsp, 50h
0x1800340cd  mov     rax, cs:__security_cookie
0x1800340d4  xor     rax, rsp
0x1800340d7  mov     [rbp+var_8], rax
0x1800340db  mov     rsi, rcx
0x1800340de  test    rcx, rcx
0x1800340e1  jnz     short loc_180034151
0x1800340e3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800340ea  mov     ebx, 80070057h
0x1800340ef  mov     [rbp+var_18], ebx
0x1800340f2  test    rcx, rcx
0x1800340f5  jz      short loc_180034134
0x1800340f7  lea     edi, [rsi+3]
0x1800340fa  xor     edx, edx
0x1800340fc  mov     r8d, edi
0x1800340ff  lea     r9, aNoTokenSpecifi; "No token specified"
0x180034106  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18003410b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180034112  lea     rax, [rbp+var_18]
0x180034116  mov     qword ptr [rbp+var_20], rax
0x18003411a  lea     r9, asc_1802EE7AC; ": {}"
0x180034121  lea     rax, [rbp+var_20]
0x180034125  mov     r8d, edi
0x180034128  mov     dl, 1
0x18003412a  mov     qword ptr [rsp+50h+var_30], rax; int
0x18003412f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180034134  mov     edx, 8Eh; void *
0x180034139  mov     rcx, [rbp+28h]; this
0x18003413d  lea     r8, aOnecoreBaseCbs_106; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x180034144  mov     r9d, ebx; char *
0x180034147  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003414c  jmp     loc_1800343E6
0x180034151  mov     ecx, cs:_tls_index
0x180034157  mov     rax, gs:58h
0x180034160  mov     r13d, 1320h
0x180034166  mov     rdi, [rax+rcx*8]
0x18003416a  cmp     qword ptr [rdi+r13], 0
0x18003416f  jz      short loc_1800341CE
0x180034171  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180034178  mov     ebx, 800F0800h
0x18003417d  mov     [rbp+var_18], ebx
0x180034180  test    rcx, rcx
0x180034183  jz      short loc_1800341C4
0x180034185  mov     edi, 3
0x18003418a  lea     r9, aAlreadyImperso; "Already impersonating"
0x180034191  mov     r8d, edi
0x180034194  xor     edx, edx
0x180034196  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18003419b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800341a2  lea     rax, [rbp+var_18]
0x1800341a6  mov     qword ptr [rbp+var_20], rax
0x1800341aa  lea     r9, asc_1802EE7AC; ": {}"
0x1800341b1  lea     rax, [rbp+var_20]
0x1800341b5  mov     r8d, edi
0x1800341b8  mov     dl, 1
0x1800341ba  mov     qword ptr [rsp+50h+var_30], rax
0x1800341bf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800341c4  mov     edx, 8Fh
0x1800341c9  jmp     loc_180034139
0x1800341ce  mov     r12d, 0FF0h
0x1800341d4  cmp     byte ptr [r12+rdi], 0
0x1800341d9  jnz     short loc_1800341E0
0x1800341db  call    __dyn_tls_on_demand_init
0x1800341e0  mov     r15d, 1330h
0x1800341e6  mov     rax, [r15+rdi]
0x1800341ea  dec     rax
0x1800341ed  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800341f1  ja      short loc_180034250
0x1800341f3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800341fa  mov     ebx, 800F0800h
0x1800341ff  mov     [rbp+var_18], ebx
0x180034202  test    rcx, rcx
0x180034205  jz      short loc_180034246
0x180034207  mov     edi, 3
0x18003420c  lea     r9, aAlreadyImperso; "Already impersonating"
0x180034213  mov     r8d, edi
0x180034216  xor     edx, edx
0x180034218  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18003421d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180034224  lea     rax, [rbp+var_18]
0x180034228  mov     qword ptr [rbp+var_20], rax
0x18003422c  lea     r9, asc_1802EE7AC; ": {}"
0x180034233  lea     rax, [rbp+var_20]
0x180034237  mov     r8d, edi
0x18003423a  mov     dl, 1
0x18003423c  mov     qword ptr [rsp+50h+var_30], rax
0x180034241  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180034246  mov     edx, 90h
0x18003424b  jmp     loc_180034139
0x180034250  lea     rcx, [rbp+var_10]
0x180034254  mov     [rbp+var_10], 0
0x18003425c  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x180034261  mov     rbx, rax
0x180034264  call    cs:__imp_GetCurrentThread
0x18003426b  nop     dword ptr [rax+rax+00h]
0x180034270  xor     r8d, r8d; OpenAsSelf
0x180034273  mov     r9, rbx; TokenHandle
0x180034276  mov     rcx, rax; ThreadHandle
0x180034279  lea     edx, [r8+0Ch]; DesiredAccess
0x18003427d  call    cs:__imp_OpenThreadToken
0x180034284  nop     dword ptr [rax+rax+00h]
0x180034289  test    eax, eax
0x18003428b  jnz     loc_180034316
0x180034291  call    cs:__imp_GetLastError
0x180034298  nop     dword ptr [rax+rax+00h]
0x18003429d  mov     ebx, eax
0x18003429f  cmp     eax, 3F0h
0x1800342a4  jz      short loc_180034316
0x1800342a6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800342ad  test    rcx, rcx
0x1800342b0  jz      short loc_180034304
0x1800342b2  mov     edi, 3
0x1800342b7  lea     r9, aFailedToImpers_2; "Failed to impersonate token."
0x1800342be  mov     r8d, edi
0x1800342c1  xor     edx, edx
0x1800342c3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800342c8  test    ebx, ebx
0x1800342ca  jg      short loc_1800342D0
0x1800342cc  mov     eax, ebx
0x1800342ce  jmp     short loc_1800342D8
0x1800342d0  movzx   eax, bx
0x1800342d3  or      eax, 80070000h
0x1800342d8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800342df  lea     r9, a0; ": {0}"
0x1800342e6  mov     [rbp+var_18], eax
0x1800342e9  mov     r8d, edi
0x1800342ec  lea     rax, [rbp+var_18]
0x1800342f0  mov     dl, 1
0x1800342f2  mov     qword ptr [rbp+var_20], rax
0x1800342f6  lea     rax, [rbp+var_20]
0x1800342fa  mov     qword ptr [rsp+50h+var_30], rax
0x1800342ff  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180034304  test    ebx, ebx
0x180034306  jz      loc_1800343DB
0x18003430c  mov     edx, 98h
0x180034311  jmp     loc_1800343A4
0x180034316  mov     rdx, rsi; Token
0x180034319  xor     ecx, ecx; Thread
0x18003431b  call    cs:__imp_SetThreadToken
0x180034322  nop     dword ptr [rax+rax+00h]
0x180034327  test    eax, eax
0x180034329  jnz     loc_1800343BB
0x18003432f  call    cs:__imp_GetLastError
0x180034336  nop     dword ptr [rax+rax+00h]
0x18003433b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180034342  mov     ebx, eax
0x180034344  test    rcx, rcx
0x180034347  jz      short loc_18003439B
0x180034349  mov     edi, 3
0x18003434e  lea     r9, aFailedToImpers_2; "Failed to impersonate token."
0x180034355  mov     r8d, edi
0x180034358  xor     edx, edx
0x18003435a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18003435f  test    ebx, ebx
0x180034361  jg      short loc_180034367
0x180034363  mov     eax, ebx
0x180034365  jmp     short loc_18003436F
0x180034367  movzx   eax, bx
0x18003436a  or      eax, 80070000h
0x18003436f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180034376  lea     r9, a0; ": {0}"
0x18003437d  mov     [rbp+var_18], eax
0x180034380  mov     r8d, edi
0x180034383  lea     rax, [rbp+var_18]
0x180034387  mov     dl, 1
0x180034389  mov     qword ptr [rbp+var_20], rax
0x18003438d  lea     rax, [rbp+var_20]
0x180034391  mov     qword ptr [rsp+50h+var_30], rax; unsigned int
0x180034396  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18003439b  test    ebx, ebx
0x18003439d  jz      short loc_1800343DB
0x18003439f  mov     edx, 9Ch; void *
0x1800343a4  mov     rcx, [rbp+28h]; this
0x1800343a8  lea     r8, aOnecoreBaseCbs_106; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x1800343af  mov     r9d, ebx; char *
0x1800343b2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800343b7  mov     ebx, eax
0x1800343b9  jmp     short loc_1800343DD
0x1800343bb  cmp     byte ptr [r12+rdi], 0
0x1800343c0  mov     [rdi+r13], rsi
0x1800343c4  jnz     short loc_1800343CB
0x1800343c6  call    __dyn_tls_on_demand_init
0x1800343cb  mov     rcx, [rbp+var_10]
0x1800343cf  mov     rax, [r15+rdi]
0x1800343d3  mov     [rbp+var_10], rax
0x1800343d7  mov     [r15+rdi], rcx
0x1800343db  xor     ebx, ebx
0x1800343dd  lea     rcx, [rbp+var_10]
0x1800343e1  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1800343e6  mov     eax, ebx
0x1800343e8  mov     rcx, [rbp+var_8]
0x1800343ec  xor     rcx, rsp; StackCookie
0x1800343ef  call    __security_check_cookie
0x1800343f4  lea     r11, [rsp+50h+var_s0]
0x1800343f9  mov     rbx, [r11+38h]
0x1800343fd  mov     rsi, [r11+40h]
0x180034401  mov     rsp, r11
0x180034404  pop     r15
0x180034406  pop     r13
0x180034408  pop     r12
0x18003440a  pop     rdi
0x18003440b  pop     rbp
0x18003440c  retn
```
