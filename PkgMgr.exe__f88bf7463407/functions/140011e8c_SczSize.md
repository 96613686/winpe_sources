# SczSize

- ea: `0x140011e8c`
- end: `0x140011fb1`
- name: `SczSize`
- size: `293`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x140010b3c`
- `0x140010d34`
- `0x140011100`
- `0x14001154c`
- `0x140011a4c`
- `0x140015a08`
- `0x1400165f8`
- `0x140017eb4`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x140011e8c`

## pseudocode

```c
__int64 __fastcall SczSize(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rdx
  __int64 v4; // rdx
  int v5[2]; // [rsp+30h] [rbp-28h] BYREF
  int v6; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a1 )
  {
    if ( a2 )
    {
      *a2 = *(_QWORD *)(a1 - 8);
      return 0;
    }
    else
    {
      v6 = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"No count result specified");
        *(_QWORD *)v5 = &v6;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v4,
          3,
          (__int64)": {}",
          (__int64)v5);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x248,
        (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
        (const char *)0x80004003LL);
      return 2147500035LL;
    }
  }
  else
  {
    v6 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string specified");
      *(_QWORD *)v5 = &v6;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v2,
        3,
        (__int64)": {}",
        (__int64)v5);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x247,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)0x80070057LL);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140011e8c  sub     rsp, 58h
0x140011e90  mov     rax, cs:__security_cookie
0x140011e97  xor     rax, rsp
0x140011e9a  mov     [rsp+58h+var_18], rax
0x140011e9f  test    rcx, rcx
0x140011ea2  jnz     short loc_140011F1D
0x140011ea4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011eab  mov     [rsp+58h+var_20], 80070057h
0x140011eb3  test    rcx, rcx
0x140011eb6  jz      short loc_140011EF7
0x140011eb8  xor     edx, edx
0x140011eba  lea     r9, aNoStringSpecif; "No string specified"
0x140011ec1  lea     r8d, [rdx+3]
0x140011ec5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140011eca  lea     rcx, [rsp+58h+var_28]
0x140011ecf  mov     r8d, 3
0x140011ed5  mov     qword ptr [rsp+58h+var_38], rcx; int
0x140011eda  lea     rax, [rsp+58h+var_20]
0x140011edf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011ee6  lea     r9, asc_14002D4FC; ": {}"
0x140011eed  mov     qword ptr [rsp+58h+var_28], rax
0x140011ef2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011ef7  mov     rcx, [rsp+58h]; this
0x140011efc  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x140011f03  mov     r9d, 80070057h; char *
0x140011f09  mov     edx, 247h; void *
0x140011f0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011f13  mov     eax, 80070057h
0x140011f18  jmp     loc_140011F9F
0x140011f1d  test    rdx, rdx
0x140011f20  jnz     short loc_140011F96
0x140011f22  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011f29  mov     [rsp+58h+var_20], 80004003h
0x140011f31  test    rcx, rcx
0x140011f34  jz      short loc_140011F73
0x140011f36  lea     r9, aNoCountResultS; "No count result specified"
0x140011f3d  lea     r8d, [rdx+3]
0x140011f41  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140011f46  lea     rcx, [rsp+58h+var_28]
0x140011f4b  mov     r8d, 3
0x140011f51  mov     qword ptr [rsp+58h+var_38], rcx; int
0x140011f56  lea     rax, [rsp+58h+var_20]
0x140011f5b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011f62  lea     r9, asc_14002D4FC; ": {}"
0x140011f69  mov     qword ptr [rsp+58h+var_28], rax
0x140011f6e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011f73  mov     rcx, [rsp+58h]; this
0x140011f78  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x140011f7f  mov     r9d, 80004003h; char *
0x140011f85  mov     edx, 248h; void *
0x140011f8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011f8f  mov     eax, 80004003h
0x140011f94  jmp     short loc_140011F9F
0x140011f96  mov     rax, [rcx-8]
0x140011f9a  mov     [rdx], rax
0x140011f9d  xor     eax, eax
0x140011f9f  mov     rcx, [rsp+58h+var_18]
0x140011fa4  xor     rcx, rsp; StackCookie
0x140011fa7  call    __security_check_cookie
0x140011fac  add     rsp, 58h
0x140011fb0  retn
```
