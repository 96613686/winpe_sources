# SczAllocFormatted

- ea: `0x1400113d4`
- end: `0x140011545`
- name: `SczAllocFormatted`
- size: `369`
- prototype: `__int64(_QWORD, _QWORD, ...)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x14000aca8`
- `0x14000b454`
- `0x14000bf34`
- `0x14000c384`
- `0x14000d410`
- `0x140012b88`
- `0x140013288`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x1400113d4`
- `0x14001154c`

## pseudocode

```c
__int64 SczAllocFormatted(__int64 a1, _WORD *a2, ...)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  int v8[2]; // [rsp+30h] [rbp-28h] BYREF
  int v9; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+10h]
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a2);
  if ( !a1 )
  {
    v2 = -2147467261;
    v9 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string result specified");
      *(_QWORD *)v8 = &v9;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v3,
        3,
        (__int64)": {}",
        (__int64)v8);
    }
    v4 = 332;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)v2);
    return v2;
  }
  if ( !a2 )
  {
    v2 = -2147024809;
    v9 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No format string specified");
      *(_QWORD *)v8 = &v9;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v6,
        3,
        (__int64)": {}",
        (__int64)v8);
    }
    v4 = 333;
    goto LABEL_5;
  }
  if ( !*a2 )
  {
    v2 = -2147024809;
    v9 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Format string is empty");
      *(_QWORD *)v8 = &v9;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v7,
        3,
        (__int64)": {}",
        (__int64)v8);
    }
    v4 = 334;
    goto LABEL_5;
  }
  return SczAllocFormattedArgs(a1, a2, (__int64 *)va);
}

```

## disassembly

```asm
0x1400113d4  mov     [rsp-10h+arg_8], rdx
0x1400113d9  mov     [rsp-10h+arg_10], r8
0x1400113de  mov     [rsp-10h+arg_18], r9
0x1400113e3  push    rbp
0x1400113e4  push    rbx
0x1400113e5  mov     rbp, rsp
0x1400113e8  sub     rsp, 58h
0x1400113ec  mov     rax, cs:__security_cookie
0x1400113f3  xor     rax, rsp
0x1400113f6  mov     [rbp+var_18], rax
0x1400113fa  xor     eax, eax
0x1400113fc  test    rcx, rcx
0x1400113ff  jnz     short loc_140011470
0x140011401  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011408  mov     ebx, 80004003h
0x14001140d  mov     [rbp+var_20], ebx
0x140011410  test    rcx, rcx
0x140011413  jz      short loc_140011451
0x140011415  lea     r9, aNoStringResult; "No string result specified"
0x14001141c  xor     edx, edx
0x14001141e  lea     r8d, [rax+3]
0x140011422  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140011427  lea     rcx, [rbp+var_28]
0x14001142b  mov     r8d, 3
0x140011431  mov     qword ptr [rsp+58h+var_38], rcx; int
0x140011436  lea     rax, [rbp+var_20]
0x14001143a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011441  lea     r9, asc_14002D4FC; ": {}"
0x140011448  mov     qword ptr [rbp+var_28], rax
0x14001144c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011451  mov     edx, 14Ch; void *
0x140011456  mov     rcx, [rbp+10h]; this
0x14001145a  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x140011461  mov     r9d, ebx; char *
0x140011464  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011469  mov     eax, ebx
0x14001146b  jmp     loc_140011532
0x140011470  test    rdx, rdx
0x140011473  jnz     short loc_1400114CA
0x140011475  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001147c  mov     ebx, 80070057h
0x140011481  mov     [rbp+var_20], ebx
0x140011484  test    rcx, rcx
0x140011487  jz      short loc_1400114C3
0x140011489  lea     r9, aNoFormatString; "No format string specified"
0x140011490  lea     r8d, [rdx+3]
0x140011494  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140011499  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400114a0  lea     rax, [rbp+var_20]
0x1400114a4  mov     qword ptr [rbp+var_28], rax
0x1400114a8  lea     r9, asc_14002D4FC; ": {}"
0x1400114af  lea     rax, [rbp+var_28]
0x1400114b3  mov     r8d, 3
0x1400114b9  mov     qword ptr [rsp+58h+var_38], rax
0x1400114be  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400114c3  mov     edx, 14Dh
0x1400114c8  jmp     short loc_140011456
0x1400114ca  cmp     [rdx], ax
0x1400114cd  jnz     short loc_140011529
0x1400114cf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400114d6  mov     ebx, 80070057h
0x1400114db  mov     [rbp+var_20], ebx
0x1400114de  test    rcx, rcx
0x1400114e1  jz      short loc_14001151F
0x1400114e3  xor     edx, edx
0x1400114e5  lea     r9, aFormatStringIs; "Format string is empty"
0x1400114ec  lea     r8d, [rdx+3]
0x1400114f0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400114f5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400114fc  lea     rax, [rbp+var_20]
0x140011500  mov     qword ptr [rbp+var_28], rax
0x140011504  lea     r9, asc_14002D4FC; ": {}"
0x14001150b  lea     rax, [rbp+var_28]
0x14001150f  mov     r8d, 3
0x140011515  mov     qword ptr [rsp+58h+var_38], rax
0x14001151a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001151f  mov     edx, 14Eh
0x140011524  jmp     loc_140011456
0x140011529  lea     r8, [rbp+arg_10]
0x14001152d  call    SczAllocFormattedArgs
0x140011532  mov     rcx, [rbp+var_18]
0x140011536  xor     rcx, rsp; StackCookie
0x140011539  call    __security_check_cookie
0x14001153e  add     rsp, 58h
0x140011542  pop     rbx
0x140011543  pop     rbp
0x140011544  retn
```
