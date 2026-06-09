# SczEnsureBackslashTerminated

- ea: `0x14001dc7c`
- end: `0x14001ddaf`
- name: `SczEnsureBackslashTerminated`
- size: `307`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1400148e8`
- `0x1400175cc`
- `0x140018630`
- `0x140021594`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x14001cd14`
- `0x14001dc7c`

## string_xrefs

- `0x14001dcb6`: `No path result specified`

## pseudocode

```c
__int64 __fastcall SczEnsureBackslashTerminated(__int64 *a1)
{
  unsigned int v1; // ebx
  __int64 v2; // rdx
  __int64 v3; // rdx
  __int64 v5; // rdx
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rdx
  int v9; // [rsp+20h] [rbp-38h]
  int v10[2]; // [rsp+30h] [rbp-28h] BYREF
  int v11; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a1 )
  {
    v1 = -2147467261;
    v11 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No path result specified");
      *(_QWORD *)v10 = &v11;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v2,
        3,
        (__int64)": {}",
        (__int64)v10);
    }
    v3 = 604;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)v1,
      v9);
    return v1;
  }
  v5 = *a1;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(v5 + 2 * v6) );
  if ( *(_WORD *)(v5 + 2 * v6 - 2) != 92 )
  {
    v7 = SczAllocConcatSz(a1, L"\\");
    v1 = v7;
    if ( v7 < 0 )
    {
      v11 = v7;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to concat backslash onto string.");
        *(_QWORD *)v10 = &v11;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v8,
          3,
          (__int64)": {}",
          (__int64)v10);
      }
      v3 = 610;
      goto LABEL_5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001dc7c  mov     [rsp+arg_8], rbx
0x14001dc81  push    rdi
0x14001dc82  sub     rsp, 50h
0x14001dc86  mov     rax, cs:__security_cookie
0x14001dc8d  xor     rax, rsp
0x14001dc90  mov     [rsp+58h+var_18], rax
0x14001dc95  xor     edi, edi
0x14001dc97  test    rcx, rcx
0x14001dc9a  jnz     short loc_14001DD11
0x14001dc9c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001dca3  mov     ebx, 80004003h
0x14001dca8  mov     [rsp+58h+var_20], ebx
0x14001dcac  test    rcx, rcx
0x14001dcaf  jz      short loc_14001DCF1
0x14001dcb1  mov     edi, 3
0x14001dcb6  lea     r9, aNoPathResultSp; "No path result specified"
0x14001dcbd  mov     r8d, edi
0x14001dcc0  xor     edx, edx
0x14001dcc2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001dcc7  lea     rcx, [rsp+58h+var_28]
0x14001dccc  mov     r8d, edi
0x14001dccf  mov     qword ptr [rsp+58h+var_38], rcx; int
0x14001dcd4  lea     rax, [rsp+58h+var_20]
0x14001dcd9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001dce0  lea     r9, asc_1400353E8; ": {}"
0x14001dce7  mov     qword ptr [rsp+58h+var_28], rax
0x14001dcec  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001dcf1  mov     edx, 25Ch; void *
0x14001dcf6  mov     rcx, [rsp+58h]; this
0x14001dcfb  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x14001dd02  mov     r9d, ebx; char *
0x14001dd05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001dd0a  mov     eax, ebx
0x14001dd0c  jmp     loc_14001DD97
0x14001dd11  mov     rdx, [rcx]
0x14001dd14  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001dd18  inc     rax
0x14001dd1b  cmp     [rdx+rax*2], di
0x14001dd1f  jnz     short loc_14001DD18
0x14001dd21  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x14001dd27  jz      short loc_14001DD95
0x14001dd29  lea     rdx, asc_14002F384; "\\"
0x14001dd30  call    SczAllocConcatSz
0x14001dd35  mov     ebx, eax
0x14001dd37  test    eax, eax
0x14001dd39  jns     short loc_14001DD95
0x14001dd3b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001dd42  mov     [rsp+58h+var_20], eax
0x14001dd46  test    rcx, rcx
0x14001dd49  jz      short loc_14001DD8B
0x14001dd4b  mov     edi, 3
0x14001dd50  lea     r9, aFailedToConcat_1; "Failed to concat backslash onto string."
0x14001dd57  mov     r8d, edi
0x14001dd5a  xor     edx, edx
0x14001dd5c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001dd61  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001dd68  lea     rax, [rsp+58h+var_20]
0x14001dd6d  mov     qword ptr [rsp+58h+var_28], rax
0x14001dd72  lea     r9, asc_1400353E8; ": {}"
0x14001dd79  lea     rax, [rsp+58h+var_28]
0x14001dd7e  mov     r8d, edi
0x14001dd81  mov     qword ptr [rsp+58h+var_38], rax
0x14001dd86  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001dd8b  mov     edx, 262h
0x14001dd90  jmp     loc_14001DCF6
0x14001dd95  xor     eax, eax
0x14001dd97  mov     rcx, [rsp+58h+var_18]
0x14001dd9c  xor     rcx, rsp; StackCookie
0x14001dd9f  call    __security_check_cookie
0x14001dda4  mov     rbx, [rsp+58h+arg_8]
0x14001dda9  add     rsp, 50h
0x14001ddad  pop     rdi
0x14001ddae  retn
```
