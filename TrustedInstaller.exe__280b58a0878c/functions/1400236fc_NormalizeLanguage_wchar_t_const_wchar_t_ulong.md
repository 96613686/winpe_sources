# NormalizeLanguage(wchar_t const *,wchar_t *,ulong)

- ea: `0x1400236fc`
- end: `0x1400238c1`
- name: `?NormalizeLanguage@@YAJPEB_WPEA_WK@Z`
- size: `453`
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
- `0x1400236fc`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x140023881`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x140023895`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x140023881`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x140023895`

## string_xrefs

- `0x14002377f`: `onecore\base\cbs\identityutil\cbsidentityutil.cpp`
- `0x1400237da`: `Failed to copy language string to normalized string.`

## pseudocode

```c
__int64 __fastcall NormalizeLanguage(const wchar_t *a1, wchar_t *a2)
{
  unsigned int v3; // edi
  __int64 v4; // rdx
  __int64 v5; // rdx
  int v7; // eax
  unsigned __int64 v8; // r11
  int v9; // ebx
  __int64 v10; // rdx
  int v11; // r9d
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // rdx
  wchar_t v14; // cx
  wchar_t v15; // cx
  int v16; // [rsp+20h] [rbp-38h]
  int v17[2]; // [rsp+30h] [rbp-28h] BYREF
  int v18; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a2 )
  {
    v3 = -2147467261;
    v18 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No result buffer specified");
      *(_QWORD *)v17 = &v18;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v4,
        3,
        (__int64)": {}",
        (__int64)v17);
    }
    v5 = 147;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\cbs\\identityutil\\cbsidentityutil.cpp",
      (const char *)v3,
      v16);
    return v3;
  }
  if ( !a1 || !*a1 )
    goto LABEL_27;
  v7 = StringCchCopyW(a2, 0x20u, a1);
  v3 = v7;
  if ( v7 < 0 )
  {
    v18 = v7;
    if ( LogAdapter::g_Logger )
    {
      v9 = v8 - 29;
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        v8 - 29,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy language string to normalized string.");
      *(_QWORD *)v17 = &v18;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v10,
        v9,
        (__int64)": {}",
        (__int64)v17);
    }
    v5 = 153;
    goto LABEL_5;
  }
  v11 = 1;
  v12 = -1;
  do
    ++v12;
  while ( a2[v12] );
  v13 = 0;
  if ( v12 )
  {
    do
    {
      if ( v13 >= v8 )
        break;
      v14 = a2[v13];
      if ( v14 == 45 )
      {
        v11 = 0;
      }
      else if ( v11 )
      {
        if ( (unsigned __int16)(v14 - 65) <= 0x19u )
        {
          v15 = v8 + v14;
LABEL_23:
          a2[v13] = v15;
        }
      }
      else if ( (unsigned __int16)(v14 - 97) <= 0x19u )
      {
        v15 = v14 - v8;
        goto LABEL_23;
      }
    }
    while ( ++v13 < v12 );
  }
  if ( !lstrcmpW(a2, L"neutral") || !lstrcmpW(a2, L"none") )
LABEL_27:
    *a2 = 0;
  return 0;
}

```

## disassembly

```asm
0x1400236fc  mov     [rsp+arg_10], rbx
0x140023701  mov     [rsp+arg_18], rsi
0x140023706  push    rdi
0x140023707  sub     rsp, 50h
0x14002370b  mov     rax, cs:__security_cookie
0x140023712  xor     rax, rsp
0x140023715  mov     [rsp+58h+var_18], rax
0x14002371a  xor     esi, esi
0x14002371c  mov     rbx, rdx
0x14002371f  test    rdx, rdx
0x140023722  jnz     short loc_140023795
0x140023724  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002372b  mov     edi, 80004003h
0x140023730  mov     [rsp+58h+var_20], edi
0x140023734  test    rcx, rcx
0x140023737  jz      short loc_140023775
0x140023739  lea     ebx, [rdx+3]
0x14002373c  mov     r8d, ebx
0x14002373f  lea     r9, aNoResultBuffer; "No result buffer specified"
0x140023746  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002374b  lea     rcx, [rsp+58h+var_28]
0x140023750  mov     r8d, ebx
0x140023753  mov     qword ptr [rsp+58h+var_38], rcx; int
0x140023758  lea     rax, [rsp+58h+var_20]
0x14002375d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023764  lea     r9, asc_1400353E8; ": {}"
0x14002376b  mov     qword ptr [rsp+58h+var_28], rax
0x140023770  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023775  mov     edx, 93h; void *
0x14002377a  mov     rcx, [rsp+58h]; this
0x14002377f  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\identityutil\\cbsid"...
0x140023786  mov     r9d, edi; char *
0x140023789  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002378e  mov     eax, edi
0x140023790  jmp     loc_1400238A4
0x140023795  test    rcx, rcx
0x140023798  jz      loc_14002389F
0x14002379e  cmp     [rcx], si
0x1400237a1  jz      loc_14002389F
0x1400237a7  mov     r8, rcx; wchar_t *
0x1400237aa  mov     r11d, 20h ; ' '
0x1400237b0  mov     edx, r11d; unsigned __int64
0x1400237b3  mov     rcx, rbx; wchar_t *
0x1400237b6  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400237bb  mov     edi, eax
0x1400237bd  test    eax, eax
0x1400237bf  jns     short loc_14002381A
0x1400237c1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400237c8  mov     [rsp+58h+var_20], eax
0x1400237cc  test    rcx, rcx
0x1400237cf  jz      short loc_140023810
0x1400237d1  lea     ebx, [r11-1Dh]
0x1400237d5  xor     edx, edx
0x1400237d7  mov     r8d, ebx
0x1400237da  lea     r9, aFailedToCopyLa; "Failed to copy language string to norma"...
0x1400237e1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400237e6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400237ed  lea     rax, [rsp+58h+var_20]
0x1400237f2  mov     qword ptr [rsp+58h+var_28], rax
0x1400237f7  lea     r9, asc_1400353E8; ": {}"
0x1400237fe  lea     rax, [rsp+58h+var_28]
0x140023803  mov     r8d, ebx
0x140023806  mov     qword ptr [rsp+58h+var_38], rax
0x14002380b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023810  mov     edx, 99h
0x140023815  jmp     loc_14002377A
0x14002381a  mov     r9d, 1
0x140023820  or      r8, 0FFFFFFFFFFFFFFFFh
0x140023824  inc     r8
0x140023827  cmp     [rbx+r8*2], si
0x14002382c  jnz     short loc_140023824
0x14002382e  mov     rdx, rsi
0x140023831  test    r8, r8
0x140023834  jz      short loc_140023877
0x140023836  cmp     rdx, r11
0x140023839  jnb     short loc_140023877
0x14002383b  movzx   ecx, word ptr [rbx+rdx*2]
0x14002383f  cmp     cx, 2Dh ; '-'
0x140023843  jnz     short loc_14002384A
0x140023845  mov     r9d, esi
0x140023848  jmp     short loc_14002386F
0x14002384a  test    r9d, r9d
0x14002384d  jz      short loc_14002385E
0x14002384f  lea     eax, [rcx-41h]
0x140023852  cmp     ax, 19h
0x140023856  ja      short loc_14002386F
0x140023858  add     cx, r11w
0x14002385c  jmp     short loc_14002386B
0x14002385e  lea     eax, [rcx-61h]
0x140023861  cmp     ax, 19h
0x140023865  ja      short loc_14002386F
0x140023867  sub     cx, r11w
0x14002386b  mov     [rbx+rdx*2], cx
0x14002386f  inc     rdx
0x140023872  cmp     rdx, r8
0x140023875  jb      short loc_140023836
0x140023877  lea     rdx, aNeutral; "neutral"
0x14002387e  mov     rcx, rbx; lpString1
0x140023881  call    cs:__imp_lstrcmpW
0x140023887  test    eax, eax
0x140023889  jz      short loc_14002389F
0x14002388b  lea     rdx, aNone; "none"
0x140023892  mov     rcx, rbx; lpString1
0x140023895  call    cs:__imp_lstrcmpW
0x14002389b  test    eax, eax
0x14002389d  jnz     short loc_1400238A2
0x14002389f  mov     [rbx], si
0x1400238a2  xor     eax, eax
0x1400238a4  mov     rcx, [rsp+58h+var_18]
0x1400238a9  xor     rcx, rsp; StackCookie
0x1400238ac  call    __security_check_cookie
0x1400238b1  mov     rbx, [rsp+58h+arg_10]
0x1400238b6  mov     rsi, [rsp+58h+arg_18]
0x1400238bb  add     rsp, 50h
0x1400238bf  pop     rdi
0x1400238c0  retn
```
