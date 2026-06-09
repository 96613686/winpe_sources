# SczPublicAllocFromSz

- ea: `0x14001ddb8`
- end: `0x14001e047`
- name: `SczPublicAllocFromSz`
- size: `655`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14000fe34`
- `0x14000ffb4`
- `0x1400259e0`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x14000580c`
- `0x140016a40`
- `0x140016fb4`
- `0x14001c760`
- `0x14001ddb8`
- `0x14002b010`

## string_xrefs

- `0x14001dfe9`: `Failed to copy new string.`

## pseudocode

```c
__int64 __fastcall SczPublicAllocFromSz(_QWORD *a1, size_t a2, const wchar_t *a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  HRESULT v12; // eax
  __int64 v13; // rdx
  size_t v14; // rbx
  wchar_t *v15; // rax
  __int64 v16; // r11
  __int64 v17; // rdx
  int v18; // [rsp+20h] [rbp-30h]
  int v19[2]; // [rsp+30h] [rbp-20h] BYREF
  size_t pcchLength; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  if ( !a1 )
  {
    v6 = -2147467261;
    LODWORD(pcchLength) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string result specified");
      *(_QWORD *)v19 = &pcchLength;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v7,
        3,
        (__int64)": {}",
        (__int64)v19);
    }
    v8 = 521;
    goto LABEL_5;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    LODWORD(pcchLength) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No malloc specified");
      *(_QWORD *)v19 = &pcchLength;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v10,
        3,
        (__int64)": {}",
        (__int64)v19);
    }
    v8 = 522;
    goto LABEL_5;
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    LODWORD(pcchLength) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string specified");
      *(_QWORD *)v19 = &pcchLength;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v11,
        3,
        (__int64)": {}",
        (__int64)v19);
    }
    v8 = 523;
    goto LABEL_5;
  }
  pcchLength = 0;
  v12 = StringLengthWorkerW(a3, a2, &pcchLength);
  v6 = v12;
  if ( v12 < 0 )
  {
    LODWORD(pcchLength) = v12;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get length of passed in string");
      *(_QWORD *)v19 = &pcchLength;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v13,
        3,
        (__int64)": {}",
        (__int64)v19);
    }
    v8 = 526;
    goto LABEL_5;
  }
  v14 = pcchLength;
  v15 = (wchar_t *)(*(__int64 (__fastcall **)(size_t, size_t))(*(_QWORD *)a2 + 24LL))(a2, 2 * pcchLength + 2);
  if ( !v15 )
  {
    v6 = -2147024882;
    v8 = 529;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)(unsigned int)v6,
      v18);
    return (unsigned int)v6;
  }
  v6 = StringCchCopyW(v15, v14 + 1, a3);
  if ( v6 < 0 )
  {
    (*(void (__fastcall **)(size_t, __int64))(*(_QWORD *)a2 + 40LL))(a2, v16);
    LODWORD(pcchLength) = v6;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy new string.");
      *(_QWORD *)v19 = &pcchLength;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v17,
        3,
        (__int64)": {}",
        (__int64)v19);
    }
    v8 = 535;
    goto LABEL_5;
  }
  *a1 = v16;
  return 0;
}

```

## disassembly

```asm
0x14001ddb8  push    rbp
0x14001ddba  push    rbx
0x14001ddbb  push    rsi
0x14001ddbc  push    rdi
0x14001ddbd  push    r14
0x14001ddbf  mov     rbp, rsp
0x14001ddc2  sub     rsp, 50h
0x14001ddc6  mov     rax, cs:__security_cookie
0x14001ddcd  xor     rax, rsp
0x14001ddd0  mov     [rbp+var_10], rax
0x14001ddd4  mov     rsi, r8
0x14001ddd7  mov     rdi, rdx
0x14001ddda  mov     r14, rcx
0x14001dddd  test    rcx, rcx
0x14001dde0  jnz     short loc_14001DE51
0x14001dde2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001dde9  mov     ebx, 80004003h
0x14001ddee  mov     dword ptr [rbp+pcchLength], ebx
0x14001ddf1  test    rcx, rcx
0x14001ddf4  jz      short loc_14001DE32
0x14001ddf6  lea     edi, [r14+3]
0x14001ddfa  xor     edx, edx
0x14001ddfc  mov     r8d, edi
0x14001ddff  lea     r9, aNoStringResult; "No string result specified"
0x14001de06  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001de0b  lea     rcx, [rbp+var_20]
0x14001de0f  mov     r8d, edi
0x14001de12  mov     qword ptr [rsp+50h+var_30], rcx; int
0x14001de17  lea     rax, [rbp+pcchLength]
0x14001de1b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001de22  lea     r9, asc_1400353E8; ": {}"
0x14001de29  mov     qword ptr [rbp+var_20], rax
0x14001de2d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001de32  mov     edx, 209h; void *
0x14001de37  mov     rcx, [rbp+28h]; this
0x14001de3b  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x14001de42  mov     r9d, ebx; char *
0x14001de45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001de4a  mov     eax, ebx
0x14001de4c  jmp     loc_14001E030
0x14001de51  test    rdi, rdi
0x14001de54  jnz     short loc_14001DEAE
0x14001de56  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001de5d  mov     ebx, 80070057h
0x14001de62  mov     dword ptr [rbp+pcchLength], ebx
0x14001de65  test    rcx, rcx
0x14001de68  jz      short loc_14001DEA7
0x14001de6a  mov     edi, 3
0x14001de6f  lea     r9, aNoMallocSpecif; "No malloc specified"
0x14001de76  mov     r8d, edi
0x14001de79  xor     edx, edx
0x14001de7b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001de80  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001de87  lea     rax, [rbp+pcchLength]
0x14001de8b  mov     qword ptr [rbp+var_20], rax
0x14001de8f  lea     r9, asc_1400353E8; ": {}"
0x14001de96  lea     rax, [rbp+var_20]
0x14001de9a  mov     r8d, edi
0x14001de9d  mov     qword ptr [rsp+50h+var_30], rax
0x14001dea2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001dea7  mov     edx, 20Ah
0x14001deac  jmp     short loc_14001DE37
0x14001deae  test    rsi, rsi
0x14001deb1  jnz     short loc_14001DF0C
0x14001deb3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001deba  mov     ebx, 80070057h
0x14001debf  mov     dword ptr [rbp+pcchLength], ebx
0x14001dec2  test    rcx, rcx
0x14001dec5  jz      short loc_14001DF02
0x14001dec7  lea     edi, [rsi+3]
0x14001deca  xor     edx, edx
0x14001decc  mov     r8d, edi
0x14001decf  lea     r9, aNoStringSpecif; "No string specified"
0x14001ded6  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001dedb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001dee2  lea     rax, [rbp+pcchLength]
0x14001dee6  mov     qword ptr [rbp+var_20], rax
0x14001deea  lea     r9, asc_1400353E8; ": {}"
0x14001def1  lea     rax, [rbp+var_20]
0x14001def5  mov     r8d, edi
0x14001def8  mov     qword ptr [rsp+50h+var_30], rax
0x14001defd  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001df02  mov     edx, 20Bh; cchMax
0x14001df07  jmp     loc_14001DE37
0x14001df0c  lea     r8, [rbp+pcchLength]; pcchLength
0x14001df10  mov     [rbp+pcchLength], 0
0x14001df18  mov     rcx, rsi; psz
0x14001df1b  call    StringLengthWorkerW
0x14001df20  mov     ebx, eax
0x14001df22  test    eax, eax
0x14001df24  jns     short loc_14001DF7C
0x14001df26  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001df2d  mov     dword ptr [rbp+pcchLength], eax
0x14001df30  test    rcx, rcx
0x14001df33  jz      short loc_14001DF72
0x14001df35  mov     edi, 3
0x14001df3a  lea     r9, aFailedToGetLen; "Failed to get length of passed in strin"...
0x14001df41  mov     r8d, edi
0x14001df44  xor     edx, edx
0x14001df46  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001df4b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001df52  lea     rax, [rbp+pcchLength]
0x14001df56  mov     qword ptr [rbp+var_20], rax
0x14001df5a  lea     r9, asc_1400353E8; ": {}"
0x14001df61  lea     rax, [rbp+var_20]
0x14001df65  mov     r8d, edi
0x14001df68  mov     qword ptr [rsp+50h+var_30], rax
0x14001df6d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001df72  mov     edx, 20Eh
0x14001df77  jmp     loc_14001DE37
0x14001df7c  mov     rax, [rdi]
0x14001df7f  mov     rcx, rdi
0x14001df82  mov     rbx, [rbp+pcchLength]
0x14001df86  mov     rax, [rax+18h]
0x14001df8a  lea     rdx, ds:2[rbx*2]
0x14001df92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001df97  mov     r11, rax
0x14001df9a  test    rax, rax
0x14001df9d  jnz     short loc_14001DFAE
0x14001df9f  mov     ebx, 8007000Eh
0x14001dfa4  mov     edx, 211h
0x14001dfa9  jmp     loc_14001DE37
0x14001dfae  lea     rdx, [rbx+1]; unsigned __int64
0x14001dfb2  mov     r8, rsi; wchar_t *
0x14001dfb5  mov     rcx, r11; wchar_t *
0x14001dfb8  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001dfbd  mov     ebx, eax
0x14001dfbf  test    eax, eax
0x14001dfc1  jns     short loc_14001E02B
0x14001dfc3  mov     rdx, [rdi]
0x14001dfc6  mov     rcx, rdi
0x14001dfc9  mov     rax, [rdx+28h]
0x14001dfcd  mov     rdx, r11
0x14001dfd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001dfd5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001dfdc  mov     dword ptr [rbp+pcchLength], ebx
0x14001dfdf  test    rcx, rcx
0x14001dfe2  jz      short loc_14001E021
0x14001dfe4  mov     edi, 3
0x14001dfe9  lea     r9, aFailedToCopyNe; "Failed to copy new string."
0x14001dff0  mov     r8d, edi
0x14001dff3  xor     edx, edx
0x14001dff5  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001dffa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e001  lea     rax, [rbp+pcchLength]
0x14001e005  mov     qword ptr [rbp+var_20], rax
0x14001e009  lea     r9, asc_1400353E8; ": {}"
0x14001e010  lea     rax, [rbp+var_20]
0x14001e014  mov     r8d, edi
0x14001e017  mov     qword ptr [rsp+50h+var_30], rax
0x14001e01c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001e021  mov     edx, 217h
0x14001e026  jmp     loc_14001DE37
0x14001e02b  mov     [r14], r11
0x14001e02e  xor     eax, eax
0x14001e030  mov     rcx, [rbp+var_10]
0x14001e034  xor     rcx, rsp; StackCookie
0x14001e037  call    __security_check_cookie
0x14001e03c  add     rsp, 50h
0x14001e040  pop     r14
0x14001e042  pop     rdi
0x14001e043  pop     rsi
0x14001e044  pop     rbx
0x14001e045  pop     rbp
0x14001e046  retn
```
