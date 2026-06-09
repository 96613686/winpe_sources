# ValidateComponentName(wchar_t const *,wchar_t)

- ea: `0x140024568`
- end: `0x1400246ba`
- name: `?ValidateComponentName@@YAJPEB_W_W@Z`
- size: `338`
- prototype: `__int64 __fastcall(const wchar_t *, wchar_t)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140022adc`
- `0x140025190`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016bfc`
- `0x140016fb4`
- `0x140024568`

## string_xrefs

- `0x140024691`: `onecore\base\cbs\identityutil\cbsidentityutil.cpp`

## pseudocode

```c
__int64 __fastcall ValidateComponentName(const wchar_t *a1, __int16 a2)
{
  unsigned __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  int v10; // [rsp+20h] [rbp-38h]
  int v11[2]; // [rsp+30h] [rbp-28h] BYREF
  const wchar_t *v12; // [rsp+38h] [rbp-20h] BYREF
  int v13; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v12 = a1;
  if ( a1 && *a1 )
  {
    v3 = -1;
    do
      ++v3;
    while ( a1[v3] );
    v4 = 0;
    if ( !v3 )
      return 0;
    while ( 1 )
    {
      v5 = a1[v4];
      if ( (_WORD)v5 == a2 )
        break;
      LOWORD(v5) = v5 - 32;
      if ( (unsigned __int16)v5 > 0x5Fu )
        break;
      if ( ++v4 >= v3 )
        return 0;
    }
    v13 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        (__int64)LogAdapter::g_Logger,
        v4,
        v5,
        (__int64)"Invalid character in name: {}",
        (__int64)&v12);
      *(_QWORD *)v11 = &v13;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v7,
        3,
        (__int64)": {}",
        (__int64)v11);
    }
    v8 = 126;
  }
  else
  {
    v13 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Empty name is not valid.");
      *(_QWORD *)v11 = &v13;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v9,
        3,
        (__int64)": {}",
        (__int64)v11);
    }
    v8 = 132;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentityutil.cpp",
    (const char *)0x80070057LL,
    v10);
  return 2147942487LL;
}

```

## disassembly

```asm
0x140024568  sub     rsp, 58h
0x14002456c  mov     rax, cs:__security_cookie
0x140024573  xor     rax, rsp
0x140024576  mov     [rsp+58h+var_10], rax
0x14002457b  xor     r10d, r10d
0x14002457e  mov     [rsp+58h+var_20], rcx
0x140024583  movzx   r9d, dx
0x140024587  test    rcx, rcx
0x14002458a  jz      loc_140024634
0x140024590  cmp     [rcx], r10w
0x140024594  jz      loc_140024634
0x14002459a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002459e  inc     rax
0x1400245a1  cmp     [rcx+rax*2], r10w
0x1400245a6  jnz     short loc_14002459E
0x1400245a8  mov     rdx, r10
0x1400245ab  test    rax, rax
0x1400245ae  jz      short loc_1400245CF
0x1400245b0  movzx   r8d, word ptr [rcx+rdx*2]
0x1400245b5  cmp     r8w, r9w
0x1400245b9  jz      short loc_1400245D6
0x1400245bb  sub     r8w, 20h ; ' '
0x1400245c0  cmp     r8w, 5Fh ; '_'
0x1400245c5  ja      short loc_1400245D6
0x1400245c7  inc     rdx
0x1400245ca  cmp     rdx, rax
0x1400245cd  jb      short loc_1400245B0
0x1400245cf  xor     eax, eax
0x1400245d1  jmp     loc_1400246A8
0x1400245d6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400245dd  mov     [rsp+58h+var_18], 80070057h
0x1400245e5  test    rcx, rcx
0x1400245e8  jz      short loc_14002462D
0x1400245ea  lea     rax, [rsp+58h+var_20]
0x1400245ef  lea     r9, aInvalidCharact; "Invalid character in name: {}"
0x1400245f6  mov     qword ptr [rsp+58h+var_38], rax
0x1400245fb  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140024600  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024607  lea     rax, [rsp+58h+var_18]
0x14002460c  mov     qword ptr [rsp+58h+var_28], rax
0x140024611  lea     r9, asc_1400353E8; ": {}"
0x140024618  lea     rax, [rsp+58h+var_28]
0x14002461d  mov     r8d, 3
0x140024623  mov     qword ptr [rsp+58h+var_38], rax
0x140024628  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002462d  mov     edx, 7Eh ; '~'
0x140024632  jmp     short loc_14002468C
0x140024634  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002463b  mov     [rsp+58h+var_18], 80070057h
0x140024643  test    rcx, rcx
0x140024646  jz      short loc_140024687
0x140024648  xor     edx, edx
0x14002464a  lea     r9, aEmptyNameIsNot; "Empty name is not valid."
0x140024651  lea     r8d, [rdx+3]
0x140024655  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002465a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140024661  lea     rax, [rsp+58h+var_18]
0x140024666  mov     qword ptr [rsp+58h+var_28], rax
0x14002466b  lea     r9, asc_1400353E8; ": {}"
0x140024672  lea     rax, [rsp+58h+var_28]
0x140024677  mov     r8d, 3
0x14002467d  mov     qword ptr [rsp+58h+var_38], rax; int
0x140024682  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140024687  mov     edx, 84h; void *
0x14002468c  mov     rcx, [rsp+58h]; this
0x140024691  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x140024698  mov     r9d, 80070057h; char *
0x14002469e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400246a3  mov     eax, 80070057h
0x1400246a8  mov     rcx, [rsp+58h+var_10]
0x1400246ad  xor     rcx, rsp; StackCookie
0x1400246b0  call    __security_check_cookie
0x1400246b5  add     rsp, 58h
0x1400246b9  retn
```
