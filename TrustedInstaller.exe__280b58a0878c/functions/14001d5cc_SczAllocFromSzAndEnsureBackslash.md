# SczAllocFromSzAndEnsureBackslash

- ea: `0x14001d5cc`
- end: `0x14001d7ce`
- name: `SczAllocFromSzAndEnsureBackslash`
- size: `514`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14001fab0`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x14000580c`
- `0x140016a40`
- `0x140016fb4`
- `0x14001c7a8`
- `0x14001d5cc`

## string_xrefs

- `0x14001d74a`: `Failed to copy source string to destination`

## pseudocode

```c
__int64 __fastcall SczAllocFromSzAndEnsureBackslash(wchar_t **a1, const wchar_t *a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v8; // rdx
  __int64 v9; // rax
  wchar_t v10; // r15
  __int64 v11; // r14
  int v12; // eax
  unsigned int v13; // esi
  int v14; // eax
  __int64 v15; // rdx
  int v16; // [rsp+20h] [rbp-30h]
  int v17[2]; // [rsp+30h] [rbp-20h] BYREF
  int v18; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  if ( !a1 )
  {
    v4 = -2147467261;
    v18 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string result specified");
      *(_QWORD *)v17 = &v18;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v17);
    }
    v6 = 411;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)v4,
      v16);
    return v4;
  }
  if ( !a2 )
  {
    v4 = -2147024809;
    v18 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string specified");
      *(_QWORD *)v17 = &v18;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v8,
        3,
        (__int64)": {}",
        (__int64)v17);
    }
    v6 = 412;
    goto LABEL_5;
  }
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  v10 = a2[v9 - 1];
  v11 = v9 + 1;
  if ( v10 == 92 )
    v11 = v9;
  v12 = SczAlloc(a1, v11 + 1);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v14 = StringCchCopyW(*a1, v11 + 1, a2);
    v4 = v14;
    if ( v14 < 0 )
    {
      v18 = v14;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy source string to destination");
        *(_QWORD *)v17 = &v18;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v15,
          3,
          (__int64)": {}",
          (__int64)v17);
      }
      v6 = 423;
      goto LABEL_5;
    }
    if ( v10 != 92 )
    {
      (*a1)[v11 - 1] = 92;
      (*a1)[v11] = 0;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)(unsigned int)v12,
      v16);
    return v13;
  }
}

```

## disassembly

```asm
0x14001d5cc  mov     [rsp-38h+arg_10], rbx
0x14001d5d1  push    rbp
0x14001d5d2  push    rsi
0x14001d5d3  push    rdi
0x14001d5d4  push    r12
0x14001d5d6  push    r13
0x14001d5d8  push    r14
0x14001d5da  push    r15
0x14001d5dc  mov     rbp, rsp
0x14001d5df  sub     rsp, 50h
0x14001d5e3  mov     rax, cs:__security_cookie
0x14001d5ea  xor     rax, rsp
0x14001d5ed  mov     [rbp+var_10], rax
0x14001d5f1  xor     r13d, r13d
0x14001d5f4  mov     rdi, rdx
0x14001d5f7  mov     rbx, rcx
0x14001d5fa  test    rcx, rcx
0x14001d5fd  jnz     short loc_14001D66E
0x14001d5ff  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d606  mov     edi, 80004003h
0x14001d60b  mov     [rbp+var_18], edi
0x14001d60e  test    rcx, rcx
0x14001d611  jz      short loc_14001D64F
0x14001d613  lea     ebx, [r13+3]
0x14001d617  xor     edx, edx
0x14001d619  mov     r8d, ebx
0x14001d61c  lea     r9, aNoStringResult; "No string result specified"
0x14001d623  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001d628  lea     rcx, [rbp+var_20]
0x14001d62c  mov     r8d, ebx
0x14001d62f  mov     qword ptr [rsp+50h+var_30], rcx; int
0x14001d634  lea     rax, [rbp+var_18]
0x14001d638  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d63f  lea     r9, asc_1400353E8; ": {}"
0x14001d646  mov     qword ptr [rbp+var_20], rax
0x14001d64a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001d64f  mov     edx, 19Bh; void *
0x14001d654  mov     rcx, [rbp+38h]; this
0x14001d658  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x14001d65f  mov     r9d, edi; char *
0x14001d662  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d667  mov     eax, edi
0x14001d669  jmp     loc_14001D7AA
0x14001d66e  test    rdi, rdi
0x14001d671  jnz     short loc_14001D6CB
0x14001d673  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d67a  mov     edi, 80070057h
0x14001d67f  mov     [rbp+var_18], edi
0x14001d682  test    rcx, rcx
0x14001d685  jz      short loc_14001D6C4
0x14001d687  mov     ebx, 3
0x14001d68c  lea     r9, aNoStringSpecif; "No string specified"
0x14001d693  mov     r8d, ebx
0x14001d696  xor     edx, edx
0x14001d698  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001d69d  lea     rcx, [rbp+var_20]
0x14001d6a1  mov     r8d, ebx
0x14001d6a4  mov     qword ptr [rsp+50h+var_30], rcx
0x14001d6a9  lea     rax, [rbp+var_18]
0x14001d6ad  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d6b4  lea     r9, asc_1400353E8; ": {}"
0x14001d6bb  mov     qword ptr [rbp+var_20], rax
0x14001d6bf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001d6c4  mov     edx, 19Ch
0x14001d6c9  jmp     short loc_14001D654
0x14001d6cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001d6cf  inc     rax
0x14001d6d2  cmp     [rdx+rax*2], r13w
0x14001d6d7  jnz     short loc_14001D6CF
0x14001d6d9  movzx   r15d, word ptr [rdx+rax*2-2]
0x14001d6df  lea     r14, [rax+1]
0x14001d6e3  mov     ecx, 5Ch ; '\'
0x14001d6e8  cmp     r15w, cx
0x14001d6ec  mov     rcx, rbx
0x14001d6ef  cmovz   r14, rax
0x14001d6f3  lea     rdx, [r14+1]
0x14001d6f7  call    SczAlloc
0x14001d6fc  mov     esi, eax
0x14001d6fe  test    eax, eax
0x14001d700  jns     short loc_14001D721
0x14001d702  mov     rcx, [rbp+38h]; this
0x14001d706  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x14001d70d  mov     r9d, eax; char *
0x14001d710  mov     edx, 1A6h; void *
0x14001d715  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d71a  mov     eax, esi
0x14001d71c  jmp     loc_14001D7AA
0x14001d721  mov     rcx, [rbx]; wchar_t *
0x14001d724  lea     rdx, [r14+1]; unsigned __int64
0x14001d728  mov     r8, rdi; wchar_t *
0x14001d72b  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001d730  mov     edi, eax
0x14001d732  test    eax, eax
0x14001d734  jns     short loc_14001D78C
0x14001d736  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d73d  mov     [rbp+var_18], eax
0x14001d740  test    rcx, rcx
0x14001d743  jz      short loc_14001D782
0x14001d745  mov     ebx, 3
0x14001d74a  lea     r9, aFailedToCopySo; "Failed to copy source string to destina"...
0x14001d751  mov     r8d, ebx
0x14001d754  xor     edx, edx
0x14001d756  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001d75b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d762  lea     rax, [rbp+var_18]
0x14001d766  mov     qword ptr [rbp+var_20], rax
0x14001d76a  lea     r9, asc_1400353E8; ": {}"
0x14001d771  lea     rax, [rbp+var_20]
0x14001d775  mov     r8d, ebx
0x14001d778  mov     qword ptr [rsp+50h+var_30], rax
0x14001d77d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001d782  mov     edx, 1A7h
0x14001d787  jmp     loc_14001D654
0x14001d78c  mov     ecx, 5Ch ; '\'
0x14001d791  cmp     r15w, cx
0x14001d795  jz      short loc_14001D7A8
0x14001d797  mov     rax, [rbx]
0x14001d79a  mov     [rax+r14*2-2], cx
0x14001d7a0  mov     rcx, [rbx]
0x14001d7a3  mov     [rcx+r14*2], r13w
0x14001d7a8  xor     eax, eax
0x14001d7aa  mov     rcx, [rbp+var_10]
0x14001d7ae  xor     rcx, rsp; StackCookie
0x14001d7b1  call    __security_check_cookie
0x14001d7b6  mov     rbx, [rsp+50h+arg_10]
0x14001d7be  add     rsp, 50h
0x14001d7c2  pop     r15
0x14001d7c4  pop     r14
0x14001d7c6  pop     r13
0x14001d7c8  pop     r12
0x14001d7ca  pop     rdi
0x14001d7cb  pop     rsi
0x14001d7cc  pop     rbp
0x14001d7cd  retn
```
