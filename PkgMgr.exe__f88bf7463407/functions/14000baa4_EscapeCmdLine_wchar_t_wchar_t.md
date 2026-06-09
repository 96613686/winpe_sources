# EscapeCmdLine(wchar_t *,wchar_t * *)

- ea: `0x14000baa4`
- end: `0x14000bbdb`
- name: `?EscapeCmdLine@@YAJPEA_WPEAPEA_W@Z`
- size: `311`
- prototype: `__int64 __fastcall(wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000ccac`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x14000ab70`
- `0x14000baa4`
- `0x14000c800`
- `0x14000c830`
- `0x14000cbd0`
- `0x140011884`

## string_xrefs

- `0x14000bb36`: `Failed to allocate memory for command line.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EscapeCmdLine(wchar_t *a1, wchar_t **a2)
{
  __int64 v4; // r8
  const wchar_t *v5; // rbx
  int v6; // eax
  unsigned int v7; // edi
  int v8; // edx
  int v10; // [rsp+20h] [rbp-48h]
  const wchar_t *v11; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v12; // [rsp+38h] [rbp-30h] BYREF
  int v13[2]; // [rsp+40h] [rbp-28h] BYREF
  __int64 v14; // [rsp+48h] [rbp-20h]
  int v15; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v14 = -2;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v11);
  *a2 = 0;
  if ( a1 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a1[v4] );
  }
  try
  {
    ATL::CSimpleStringT<wchar_t,0>::SetString();
    ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Replace(&v11);
  }
  catch ( ATL::CAtlException v12 )
  {
    ATL::CStringData::Release((ATL::CStringData *)(v11 - 12));
    return v12;
  }
  v5 = v11;
  v6 = SczAllocFromSz(a2, v11);
  v7 = v6;
  if ( v6 >= 0 )
  {
    ATL::CStringData::Release((ATL::CStringData *)(v5 - 12));
    return 0;
  }
  else
  {
    v15 = v6;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
      *(_QWORD *)v13 = &v15;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v8,
        3,
        (unsigned int)": {}",
        (__int64)v13);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\main.cpp",
      (const char *)v7,
      v10);
    ATL::CStringData::Release((ATL::CStringData *)(v5 - 12));
    return v7;
  }
}

```

## disassembly

```asm
0x14000baa4  mov     r11, rsp
0x14000baa7  push    rdi
0x14000baa8  sub     rsp, 60h
0x14000baac  mov     qword ptr [r11-20h], 0FFFFFFFFFFFFFFFEh
0x14000bab4  mov     [r11+18h], rbx
0x14000bab8  mov     [r11+20h], rsi
0x14000babc  mov     rax, cs:__security_cookie
0x14000bac3  xor     rax, rsp
0x14000bac6  mov     [rsp+68h+var_10], rax
0x14000bacb  mov     rdi, rdx
0x14000bace  mov     rbx, rcx
0x14000bad1  lea     rcx, [r11-38h]
0x14000bad5  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x14000bada  nop
0x14000badb  xor     esi, esi
0x14000badd  mov     [rdi], rsi
0x14000bae0  test    rbx, rbx
0x14000bae3  jnz     short loc_14000BAEA
0x14000bae5  mov     r8d, esi
0x14000bae8  jmp     short loc_14000BAF8
0x14000baea  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000baee  inc     r8
0x14000baf1  cmp     [rbx+r8*2], si
0x14000baf6  jnz     short loc_14000BAEE
0x14000baf8  mov     rdx, rbx
0x14000bafb  lea     rcx, [rsp+68h+var_38]
0x14000bb00  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x14000bb05  lea     rcx, [rsp+68h+var_38]
0x14000bb0a  call    ?Replace@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAHPEB_W0@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::Replace(wchar_t const *,wchar_t const *)
0x14000bb0f  nop
0x14000bb10  mov     rbx, [rsp+68h+var_38]
0x14000bb15  mov     rdx, rbx
0x14000bb18  mov     rcx, rdi
0x14000bb1b  call    SczAllocFromSz
0x14000bb20  mov     edi, eax
0x14000bb22  test    eax, eax
0x14000bb24  jns     short loc_14000BB9D
0x14000bb26  mov     [rsp+68h+var_18], eax
0x14000bb2a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000bb31  test    rcx, rcx
0x14000bb34  jz      short loc_14000BB76
0x14000bb36  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000bb3d  mov     esi, 3
0x14000bb42  mov     r8d, esi
0x14000bb45  xor     edx, edx
0x14000bb47  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000bb4c  lea     rax, [rsp+68h+var_18]
0x14000bb51  mov     qword ptr [rsp+68h+var_28], rax
0x14000bb56  lea     rax, [rsp+68h+var_28]
0x14000bb5b  mov     qword ptr [rsp+68h+var_48], rax; int
0x14000bb60  lea     r9, asc_14002D4FC; ": {}"
0x14000bb67  mov     r8d, esi
0x14000bb6a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000bb71  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000bb76  mov     rcx, [rsp+68h]; this
0x14000bb7b  mov     r9d, edi; char *
0x14000bb7e  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\pkgmgrshim\\main.cp"...
0x14000bb85  mov     edx, 249h; void *
0x14000bb8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000bb8f  nop
0x14000bb90  lea     rcx, [rbx-18h]; this
0x14000bb94  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14000bb99  mov     eax, edi
0x14000bb9b  jmp     short loc_14000BBBC
0x14000bb9d  lea     rcx, [rbx-18h]; this
0x14000bba1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14000bba6  xor     eax, eax
0x14000bba8  jmp     short loc_14000BBBC
0x14000bbaa  mov     rcx, [rsp+68h+var_38]
0x14000bbaf  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x14000bbb3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x14000bbb8  mov     eax, [rsp+68h+var_30]
0x14000bbbc  mov     rcx, [rsp+68h+var_10]
0x14000bbc1  xor     rcx, rsp; StackCookie
0x14000bbc4  call    __security_check_cookie
0x14000bbc9  lea     r11, [rsp+68h+var_8]
0x14000bbce  mov     rbx, [r11+20h]
0x14000bbd2  mov     rsi, [r11+28h]
0x14000bbd6  mov     rsp, r11
0x14000bbd9  pop     rdi
0x14000bbda  retn
```
