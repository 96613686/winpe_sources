# NormalizeProcessor(wchar_t const *,wchar_t *,ulong)

- ea: `0x1400238c8`
- end: `0x140023a42`
- name: `?NormalizeProcessor@@YAJPEB_WPEA_WK@Z`
- size: `378`
- prototype: `__int64 __fastcall(const wchar_t *, wchar_t *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation`

## callers

- `0x140022adc`
- `0x140025190`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x14000580c`
- `0x140016a40`
- `0x140016fb4`
- `0x1400238c8`

## string_xrefs

- `0x14002394b`: `onecore\base\cbs\identityutil\cbsidentityutil.cpp`
- `0x1400239a3`: `Failed to copy processor to normalized buffer.`

## pseudocode

```c
__int64 __fastcall NormalizeProcessor(const wchar_t *a1, wchar_t *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rdx
  int v6; // eax
  __int64 v7; // r11
  __int64 v8; // rdx
  unsigned __int64 v9; // rdx
  unsigned __int64 i; // rcx
  __int16 v11; // r8
  int v12; // [rsp+20h] [rbp-38h]
  int v13[2]; // [rsp+30h] [rbp-28h] BYREF
  int v14; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a2 )
  {
    v2 = -2147467261;
    v14 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No result buffer specified");
      *(_QWORD *)v13 = &v14;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v3,
        3,
        (__int64)": {}",
        (__int64)v13);
    }
    v4 = 233;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentityutil.cpp",
      (const char *)v2,
      v12);
    return v2;
  }
  if ( a1 && *a1 )
  {
    v6 = StringCchCopyW(a2, 0x20u, a1);
    v2 = v6;
    if ( v6 < 0 )
    {
      v14 = v6;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy processor to normalized buffer.");
        *(_QWORD *)v13 = &v14;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v8,
          3,
          (__int64)": {}",
          (__int64)v13);
      }
      v4 = 238;
      goto LABEL_5;
    }
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(v7 + 2 * v9) );
    for ( i = 0; i < v9; ++i )
    {
      if ( i >= 0x20 )
        break;
      v11 = *(_WORD *)(v7 + 2 * i);
      if ( (unsigned __int16)(v11 - 65) <= 0x19u )
        *(_WORD *)(v7 + 2 * i) = v11 + 32;
    }
  }
  else
  {
    *a2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1400238c8  mov     [rsp+arg_10], rbx
0x1400238cd  mov     [rsp+arg_18], rsi
0x1400238d2  push    rdi
0x1400238d3  sub     rsp, 50h
0x1400238d7  mov     rax, cs:__security_cookie
0x1400238de  xor     rax, rsp
0x1400238e1  mov     [rsp+58h+var_18], rax
0x1400238e6  xor     edi, edi
0x1400238e8  mov     r11, rdx
0x1400238eb  test    rdx, rdx
0x1400238ee  jnz     short loc_140023961
0x1400238f0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400238f7  mov     ebx, 80004003h
0x1400238fc  mov     [rsp+58h+var_20], ebx
0x140023900  test    rcx, rcx
0x140023903  jz      short loc_140023941
0x140023905  lea     edi, [rdx+3]
0x140023908  mov     r8d, edi
0x14002390b  lea     r9, aNoResultBuffer; "No result buffer specified"
0x140023912  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140023917  lea     rcx, [rsp+58h+var_28]
0x14002391c  mov     r8d, edi
0x14002391f  mov     qword ptr [rsp+58h+var_38], rcx; int
0x140023924  lea     rax, [rsp+58h+var_20]
0x140023929  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023930  lea     r9, asc_1400353E8; ": {}"
0x140023937  mov     qword ptr [rsp+58h+var_28], rax
0x14002393c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023941  mov     edx, 0E9h; void *
0x140023946  mov     rcx, [rsp+58h]; this
0x14002394b  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x140023952  mov     r9d, ebx; char *
0x140023955  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002395a  mov     eax, ebx
0x14002395c  jmp     loc_140023A25
0x140023961  test    rcx, rcx
0x140023964  jz      loc_140023A20
0x14002396a  cmp     [rcx], di
0x14002396d  jz      loc_140023A20
0x140023973  mov     r8, rcx; wchar_t *
0x140023976  mov     esi, 20h ; ' '
0x14002397b  mov     edx, esi; unsigned __int64
0x14002397d  mov     rcx, r11; wchar_t *
0x140023980  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140023985  mov     ebx, eax
0x140023987  test    eax, eax
0x140023989  jns     short loc_1400239E3
0x14002398b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023992  mov     [rsp+58h+var_20], eax
0x140023996  test    rcx, rcx
0x140023999  jz      short loc_1400239D9
0x14002399b  lea     edi, [rsi-1Dh]
0x14002399e  xor     edx, edx
0x1400239a0  mov     r8d, edi
0x1400239a3  lea     r9, aFailedToCopyPr; "Failed to copy processor to normalized "...
0x1400239aa  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400239af  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400239b6  lea     rax, [rsp+58h+var_20]
0x1400239bb  mov     qword ptr [rsp+58h+var_28], rax
0x1400239c0  lea     r9, asc_1400353E8; ": {}"
0x1400239c7  lea     rax, [rsp+58h+var_28]
0x1400239cc  mov     r8d, edi
0x1400239cf  mov     qword ptr [rsp+58h+var_38], rax
0x1400239d4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400239d9  mov     edx, 0EEh
0x1400239de  jmp     loc_140023946
0x1400239e3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400239e7  inc     rdx
0x1400239ea  cmp     [r11+rdx*2], di
0x1400239ef  jnz     short loc_1400239E7
0x1400239f1  mov     rcx, rdi
0x1400239f4  test    rdx, rdx
0x1400239f7  jz      short loc_140023A23
0x1400239f9  cmp     rcx, rsi
0x1400239fc  jnb     short loc_140023A23
0x1400239fe  movzx   r8d, word ptr [r11+rcx*2]
0x140023a03  lea     eax, [r8-41h]
0x140023a07  cmp     ax, 19h
0x140023a0b  ja      short loc_140023A16
0x140023a0d  add     r8w, si
0x140023a11  mov     [r11+rcx*2], r8w
0x140023a16  inc     rcx
0x140023a19  cmp     rcx, rdx
0x140023a1c  jb      short loc_1400239F9
0x140023a1e  jmp     short loc_140023A23
0x140023a20  mov     [rdx], di
0x140023a23  xor     eax, eax
0x140023a25  mov     rcx, [rsp+58h+var_18]
0x140023a2a  xor     rcx, rsp; StackCookie
0x140023a2d  call    __security_check_cookie
0x140023a32  mov     rbx, [rsp+58h+arg_10]
0x140023a37  mov     rsi, [rsp+58h+arg_18]
0x140023a3c  add     rsp, 50h
0x140023a40  pop     rdi
0x140023a41  retn
```
