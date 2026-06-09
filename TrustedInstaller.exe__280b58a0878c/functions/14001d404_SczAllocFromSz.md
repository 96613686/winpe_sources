# SczAllocFromSz

- ea: `0x14001d404`
- end: `0x14001d5c6`
- name: `SczAllocFromSz`
- size: `450`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14000c6e4`
- `0x14000ec74`
- `0x140010334`
- `0x1400139cc`
- `0x1400178b8`
- `0x140018180`
- `0x140018630`
- `0x14001d7d4`
- `0x14001fc6c`
- `0x140024980`
- `0x1400259e0`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x14000580c`
- `0x140016a40`
- `0x140016fb4`
- `0x14001c7a8`
- `0x14001d404`

## string_xrefs

- `0x14001d562`: `Failed to copy source string to destination`

## pseudocode

```c
__int64 __fastcall SczAllocFromSz(wchar_t **a1, const wchar_t *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v8; // rdx
  __int64 v9; // rax
  unsigned __int64 v10; // r14
  int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  __int64 v14; // rdx
  int v15; // [rsp+20h] [rbp-30h]
  int v16[2]; // [rsp+30h] [rbp-20h] BYREF
  int v17; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  if ( !a1 )
  {
    v4 = -2147467261;
    v17 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string result specified");
      *(_QWORD *)v16 = &v17;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v16);
    }
    v6 = 399;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)v4,
      v15);
    return v4;
  }
  if ( !a2 )
  {
    v4 = -2147024809;
    v17 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string specified");
      *(_QWORD *)v16 = &v17;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v8,
        3,
        (__int64)": {}",
        (__int64)v16);
    }
    v6 = 400;
    goto LABEL_5;
  }
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  v10 = v9 + 1;
  v11 = SczAlloc(a1, v9 + 1);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v13 = StringCchCopyW(*a1, v10, a2);
    v4 = v13;
    if ( v13 < 0 )
    {
      v17 = v13;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy source string to destination");
        *(_QWORD *)v16 = &v17;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v14,
          3,
          (__int64)": {}",
          (__int64)v16);
      }
      v6 = 404;
      goto LABEL_5;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)(unsigned int)v11,
      v15);
    return v12;
  }
}

```

## disassembly

```asm
0x14001d404  mov     [rsp-28h+arg_10], rbx
0x14001d409  push    rbp
0x14001d40a  push    rsi
0x14001d40b  push    rdi
0x14001d40c  push    r14
0x14001d40e  push    r15
0x14001d410  mov     rbp, rsp
0x14001d413  sub     rsp, 50h
0x14001d417  mov     rax, cs:__security_cookie
0x14001d41e  xor     rax, rsp
0x14001d421  mov     [rbp+var_10], rax
0x14001d425  xor     r15d, r15d
0x14001d428  mov     rbx, rdx
0x14001d42b  mov     rsi, rcx
0x14001d42e  test    rcx, rcx
0x14001d431  jnz     short loc_14001D4A1
0x14001d433  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d43a  mov     ebx, 80004003h
0x14001d43f  mov     [rbp+var_18], ebx
0x14001d442  test    rcx, rcx
0x14001d445  jz      short loc_14001D482
0x14001d447  lea     edi, [rsi+3]
0x14001d44a  xor     edx, edx
0x14001d44c  mov     r8d, edi
0x14001d44f  lea     r9, aNoStringResult; "No string result specified"
0x14001d456  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001d45b  lea     rcx, [rbp+var_20]
0x14001d45f  mov     r8d, edi
0x14001d462  mov     qword ptr [rsp+50h+var_30], rcx; int
0x14001d467  lea     rax, [rbp+var_18]
0x14001d46b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d472  lea     r9, asc_1400353E8; ": {}"
0x14001d479  mov     qword ptr [rbp+var_20], rax
0x14001d47d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001d482  mov     edx, 18Fh; void *
0x14001d487  mov     rcx, [rbp+28h]; this
0x14001d48b  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x14001d492  mov     r9d, ebx; char *
0x14001d495  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d49a  mov     eax, ebx
0x14001d49c  jmp     loc_14001D5A6
0x14001d4a1  test    rbx, rbx
0x14001d4a4  jnz     short loc_14001D4FE
0x14001d4a6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d4ad  mov     ebx, 80070057h
0x14001d4b2  mov     [rbp+var_18], ebx
0x14001d4b5  test    rcx, rcx
0x14001d4b8  jz      short loc_14001D4F7
0x14001d4ba  mov     edi, 3
0x14001d4bf  lea     r9, aNoStringSpecif; "No string specified"
0x14001d4c6  mov     r8d, edi
0x14001d4c9  xor     edx, edx
0x14001d4cb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001d4d0  lea     rcx, [rbp+var_20]
0x14001d4d4  mov     r8d, edi
0x14001d4d7  mov     qword ptr [rsp+50h+var_30], rcx
0x14001d4dc  lea     rax, [rbp+var_18]
0x14001d4e0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d4e7  lea     r9, asc_1400353E8; ": {}"
0x14001d4ee  mov     qword ptr [rbp+var_20], rax
0x14001d4f2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001d4f7  mov     edx, 190h
0x14001d4fc  jmp     short loc_14001D487
0x14001d4fe  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001d502  inc     rax
0x14001d505  cmp     [rdx+rax*2], r15w
0x14001d50a  jnz     short loc_14001D502
0x14001d50c  lea     r14, [rax+1]
0x14001d510  mov     rdx, r14
0x14001d513  call    SczAlloc
0x14001d518  mov     edi, eax
0x14001d51a  test    eax, eax
0x14001d51c  jns     short loc_14001D53A
0x14001d51e  mov     rcx, [rbp+28h]; this
0x14001d522  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x14001d529  mov     r9d, eax; char *
0x14001d52c  mov     edx, 193h; void *
0x14001d531  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d536  mov     eax, edi
0x14001d538  jmp     short loc_14001D5A6
0x14001d53a  mov     rcx, [rsi]; wchar_t *
0x14001d53d  mov     r8, rbx; wchar_t *
0x14001d540  mov     rdx, r14; unsigned __int64
0x14001d543  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001d548  mov     ebx, eax
0x14001d54a  test    eax, eax
0x14001d54c  jns     short loc_14001D5A4
0x14001d54e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d555  mov     [rbp+var_18], eax
0x14001d558  test    rcx, rcx
0x14001d55b  jz      short loc_14001D59A
0x14001d55d  mov     edi, 3
0x14001d562  lea     r9, aFailedToCopySo; "Failed to copy source string to destina"...
0x14001d569  mov     r8d, edi
0x14001d56c  xor     edx, edx
0x14001d56e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001d573  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d57a  lea     rax, [rbp+var_18]
0x14001d57e  mov     qword ptr [rbp+var_20], rax
0x14001d582  lea     r9, asc_1400353E8; ": {}"
0x14001d589  lea     rax, [rbp+var_20]
0x14001d58d  mov     r8d, edi
0x14001d590  mov     qword ptr [rsp+50h+var_30], rax
0x14001d595  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001d59a  mov     edx, 194h
0x14001d59f  jmp     loc_14001D487
0x14001d5a4  xor     eax, eax
0x14001d5a6  mov     rcx, [rbp+var_10]
0x14001d5aa  xor     rcx, rsp; StackCookie
0x14001d5ad  call    __security_check_cookie
0x14001d5b2  mov     rbx, [rsp+50h+arg_10]
0x14001d5ba  add     rsp, 50h
0x14001d5be  pop     r15
0x14001d5c0  pop     r14
0x14001d5c2  pop     rdi
0x14001d5c3  pop     rsi
0x14001d5c4  pop     rbp
0x14001d5c5  retn
```
