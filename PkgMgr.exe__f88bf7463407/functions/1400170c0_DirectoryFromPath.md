# DirectoryFromPath

- ea: `0x1400170c0`
- end: `0x14001738a`
- name: `DirectoryFromPath`
- size: `714`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140013288`

## callees

- `0x140001fcc`
- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x14000726c`
- `0x140010164`
- `0x140010b3c`
- `0x1400170c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400171d5`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400171d5`

## string_xrefs

- `0x140017283`: `Failed to copy source string to destination`
- `0x140017112`: `No path specified`
- `0x140017172`: `No directory result specified`
- `0x14001730e`: `Invalid path.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DirectoryFromPath(wchar_t *a1, wchar_t **a2)
{
  unsigned int v4; // ebx
  int v5; // edx
  __int64 v6; // rdx
  int v7; // edx
  wchar_t *v8; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // r14
  int v11; // eax
  unsigned int v12; // esi
  wchar_t *v14; // rsi
  unsigned __int64 v15; // rax
  int v16; // eax
  int v17; // edx
  int v18; // edx
  int v19; // [rsp+20h] [rbp-40h]
  wchar_t *v20; // [rsp+30h] [rbp-30h] BYREF
  int v21[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v22; // [rsp+40h] [rbp-20h]
  int v23; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v22 = -2;
  if ( !a1 )
  {
    v4 = -2147024809;
    v23 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No path specified");
      v20 = (wchar_t *)&v23;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v5,
        3,
        (unsigned int)": {}",
        (__int64)&v20);
    }
    v6 = 38;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)v4,
      v19);
    return v4;
  }
  if ( !a2 )
  {
    v4 = -2147467261;
    v23 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No directory result specified");
      v20 = (wchar_t *)&v23;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v7,
        3,
        (unsigned int)": {}",
        (__int64)&v20);
    }
    v6 = 39;
    goto LABEL_27;
  }
  if ( *a2 )
  {
    operator delete(*a2 - 4);
    *a2 = 0;
  }
  v8 = wcsrchr(a1, 0x5Cu);
  if ( !v8 || v8 == a1 )
  {
    v4 = -2147024809;
    v23 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid path.");
      *(_QWORD *)v21 = &v23;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v18,
        3,
        (unsigned int)": {}",
        (__int64)v21);
    }
    v6 = 46;
    goto LABEL_27;
  }
  v9 = v8 - a1;
  v10 = v9 + 1;
  v20 = 0;
  v11 = SczAlloc(&v20, v9 + 3);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
      (const char *)(unsigned int)v11,
      v19);
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v20);
    return v12;
  }
  v14 = v20;
  if ( !v20 )
    goto LABEL_23;
  v15 = -1;
  do
    ++v15;
  while ( a1[v15] );
  if ( v10 > v15 || (v16 = StringCchCopyNW(v20, v10 + 2, a1, v10), v4 = v16, v16 >= 0) )
  {
LABEL_23:
    v20 = 0;
    *a2 = v14;
    Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v20);
    return 0;
  }
  v23 = v16;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to copy source string to destination");
    *(_QWORD *)v21 = &v23;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v17,
      3,
      (unsigned int)": {}",
      (__int64)v21);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3B,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
    (const char *)v4,
    v19);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v20);
  return v4;
}

```

## disassembly

```asm
0x1400170c0  mov     rax, rsp
0x1400170c3  push    rbp
0x1400170c4  push    rdi
0x1400170c5  push    r12
0x1400170c7  push    r14
0x1400170c9  push    r15
0x1400170cb  mov     rbp, rsp
0x1400170ce  sub     rsp, 60h
0x1400170d2  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x1400170da  mov     [rax+18h], rbx
0x1400170de  mov     [rax+20h], rsi
0x1400170e2  mov     rax, cs:__security_cookie
0x1400170e9  xor     rax, rsp
0x1400170ec  mov     [rbp+var_10], rax
0x1400170f0  mov     rdi, rdx
0x1400170f3  mov     rbx, rcx
0x1400170f6  xor     r12d, r12d
0x1400170f9  test    rcx, rcx
0x1400170fc  jnz     short loc_140017159
0x1400170fe  mov     ebx, 80070057h
0x140017103  mov     [rbp+var_18], ebx
0x140017106  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001710d  test    rcx, rcx
0x140017110  jz      short loc_14001714F
0x140017112  lea     r9, aNoPathSpecifie; "No path specified"
0x140017119  lea     edi, [r12+3]
0x14001711e  mov     r8d, edi
0x140017121  xor     edx, edx
0x140017123  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140017128  lea     rax, [rbp+var_18]
0x14001712c  mov     [rbp+var_30], rax
0x140017130  lea     rax, [rbp+var_30]
0x140017134  mov     qword ptr [rsp+60h+var_40], rax
0x140017139  lea     r9, asc_14002D4FC; ": {}"
0x140017140  mov     r8d, edi
0x140017143  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001714a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001714f  mov     edx, 26h ; '&'
0x140017154  jmp     loc_140017350
0x140017159  test    rdi, rdi
0x14001715c  jnz     short loc_1400171B9
0x14001715e  mov     ebx, 80004003h
0x140017163  mov     [rbp+var_18], ebx
0x140017166  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001716d  test    rcx, rcx
0x140017170  jz      short loc_1400171AF
0x140017172  lea     r9, aNoDirectoryRes; "No directory result specified"
0x140017179  mov     edi, 3
0x14001717e  mov     r8d, edi
0x140017181  xor     edx, edx
0x140017183  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140017188  lea     rax, [rbp+var_18]
0x14001718c  mov     [rbp+var_30], rax
0x140017190  lea     rcx, [rbp+var_30]
0x140017194  mov     qword ptr [rsp+60h+var_40], rcx
0x140017199  lea     r9, asc_14002D4FC; ": {}"
0x1400171a0  mov     r8d, edi
0x1400171a3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400171aa  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400171af  mov     edx, 27h ; '''
0x1400171b4  jmp     loc_140017350
0x1400171b9  mov     rcx, [rdx]
0x1400171bc  test    rcx, rcx
0x1400171bf  jz      short loc_1400171CD
0x1400171c1  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1400171c5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400171ca  mov     [rdi], r12
0x1400171cd  mov     edx, 5Ch ; '\'; Ch
0x1400171d2  mov     rcx, rbx; Str
0x1400171d5  call    cs:__imp_wcsrchr
0x1400171db  test    rax, rax
0x1400171de  jz      loc_1400172FA
0x1400171e4  cmp     rax, rbx
0x1400171e7  jz      loc_1400172FA
0x1400171ed  sub     rax, rbx
0x1400171f0  sar     rax, 1
0x1400171f3  lea     r14, [rax+1]
0x1400171f7  mov     [rbp+var_30], r12
0x1400171fb  lea     rdx, [r14+2]
0x1400171ff  lea     rcx, [rbp+var_30]
0x140017203  call    SczAlloc
0x140017208  mov     esi, eax
0x14001720a  test    eax, eax
0x14001720c  jns     short loc_140017238
0x14001720e  mov     rcx, [rbp+28h]; this
0x140017212  mov     r9d, eax; char *
0x140017215  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001721c  mov     edx, 34h ; '4'; void *
0x140017221  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017226  nop
0x140017227  lea     rcx, [rbp+var_30]
0x14001722b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140017230  nop
0x140017231  mov     eax, esi
0x140017233  jmp     loc_140017365
0x140017238  mov     rsi, [rbp+var_30]
0x14001723c  test    rsi, rsi
0x14001723f  jz      loc_1400172E5
0x140017245  or      rax, 0FFFFFFFFFFFFFFFFh
0x140017249  inc     rax
0x14001724c  cmp     [rbx+rax*2], r12w
0x140017251  jnz     short loc_140017249
0x140017253  cmp     r14, rax
0x140017256  ja      loc_1400172E5
0x14001725c  mov     r9, r14; unsigned __int64
0x14001725f  mov     r8, rbx; wchar_t *
0x140017262  lea     rdx, [r14+2]; unsigned __int64
0x140017266  mov     rcx, rsi; wchar_t *
0x140017269  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x14001726e  mov     ebx, eax
0x140017270  test    eax, eax
0x140017272  jns     short loc_1400172E5
0x140017274  mov     [rbp+var_18], eax
0x140017277  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001727e  test    rcx, rcx
0x140017281  jz      short loc_1400172C0
0x140017283  lea     r9, aFailedToCopySo; "Failed to copy source string to destina"...
0x14001728a  mov     edi, 3
0x14001728f  mov     r8d, edi
0x140017292  xor     edx, edx
0x140017294  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140017299  lea     rax, [rbp+var_18]
0x14001729d  mov     qword ptr [rbp+var_28], rax
0x1400172a1  lea     rax, [rbp+var_28]
0x1400172a5  mov     qword ptr [rsp+60h+var_40], rax; int
0x1400172aa  lea     r9, asc_14002D4FC; ": {}"
0x1400172b1  mov     r8d, edi
0x1400172b4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400172bb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400172c0  mov     rcx, [rbp+28h]; this
0x1400172c4  mov     r9d, ebx; char *
0x1400172c7  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x1400172ce  mov     edx, 3Bh ; ';'; void *
0x1400172d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400172d8  nop
0x1400172d9  lea     rcx, [rbp+var_30]
0x1400172dd  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400172e2  nop
0x1400172e3  jmp     short loc_140017363
0x1400172e5  mov     [rbp+var_30], r12
0x1400172e9  mov     [rdi], rsi
0x1400172ec  lea     rcx, [rbp+var_30]
0x1400172f0  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x1400172f5  nop
0x1400172f6  xor     eax, eax
0x1400172f8  jmp     short loc_140017365
0x1400172fa  mov     ebx, 80070057h
0x1400172ff  mov     [rbp+var_18], ebx
0x140017302  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017309  test    rcx, rcx
0x14001730c  jz      short loc_14001734B
0x14001730e  lea     r9, aInvalidPath; "Invalid path."
0x140017315  mov     edi, 3
0x14001731a  mov     r8d, edi
0x14001731d  xor     edx, edx
0x14001731f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140017324  lea     rax, [rbp+var_18]
0x140017328  mov     qword ptr [rbp+var_28], rax
0x14001732c  lea     rax, [rbp+var_28]
0x140017330  mov     qword ptr [rsp+60h+var_40], rax; int
0x140017335  lea     r9, asc_14002D4FC; ": {}"
0x14001733c  mov     r8d, edi
0x14001733f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017346  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001734b  mov     edx, 2Eh ; '.'; void *
0x140017350  mov     r9d, ebx; char *
0x140017353  lea     r8, aOnecoreBaseCbs_8; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001735a  mov     rcx, [rbp+28h]; this
0x14001735e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017363  mov     eax, ebx
0x140017365  mov     rcx, [rbp+var_10]
0x140017369  xor     rcx, rsp; StackCookie
0x14001736c  call    __security_check_cookie
0x140017371  lea     r11, [rsp+60h+var_s0]
0x140017376  mov     rbx, [r11+40h]
0x14001737a  mov     rsi, [r11+48h]
0x14001737e  mov     rsp, r11
0x140017381  pop     r15
0x140017383  pop     r14
0x140017385  pop     r12
0x140017387  pop     rdi
0x140017388  pop     rbp
0x140017389  retn
```
