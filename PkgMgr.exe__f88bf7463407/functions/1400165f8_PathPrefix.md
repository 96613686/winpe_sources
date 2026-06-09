# PathPrefix

- ea: `0x1400165f8`
- end: `0x14001685a`
- name: `PathPrefix`
- size: `610`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140015a08`
- `0x140017568`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x140011a4c`
- `0x140011e8c`
- `0x1400165f8`
- `0x140029c00`

## string_xrefs

- `0x14001663e`: `No full path result specified`
- `0x140016783`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140016830`: `onecore\base\cbs\util\cbspath.cpp`
- `0x14001669c`: `Invalid full path specified`
- `0x1400167ef`: `Invalid path provided to prefix.`

## pseudocode

```c
__int64 __fastcall PathPrefix(_WORD **a1)
{
  int v2; // ebx
  int v3; // edx
  __int64 v4; // rdx
  _WORD *v5; // rbx
  int v6; // edx
  unsigned __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // esi
  int v11; // edx
  int v12; // [rsp+20h] [rbp-38h]
  int v13[2]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v14; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]

  if ( !a1 )
  {
    v2 = -2147467261;
    LODWORD(v14) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No full path result specified");
      *(_QWORD *)v13 = &v14;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v3,
        3,
        (unsigned int)": {}",
        (__int64)v13);
    }
    v4 = 143;
    goto LABEL_30;
  }
  v5 = *a1;
  if ( !*a1 )
  {
    v2 = -2147024809;
    LODWORD(v14) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid full path specified");
      *(_QWORD *)v13 = &v14;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v6,
        3,
        (unsigned int)": {}",
        (__int64)v13);
    }
    v4 = 144;
    goto LABEL_30;
  }
  if ( (unsigned __int16)(*v5 - 97) > 0x19u && (unsigned __int16)(*v5 - 65) > 0x19u || v5[1] != 58 || v5[2] != 92 )
  {
    v7 = -1;
    do
      ++v7;
    while ( v5[v7] );
    if ( v7 < 4 || *v5 != 92 || v5[1] != 92 )
    {
      v2 = -2147024809;
      LODWORD(v14) = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid path provided to prefix.");
        *(_QWORD *)v13 = &v14;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v11,
          3,
          (unsigned int)": {}",
          (__int64)v13);
      }
      v4 = 171;
      goto LABEL_30;
    }
    if ( v5[2] != 63 && v5[3] != 92 )
    {
      v14 = 0;
      v8 = SczSize(v5, &v14);
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA2,
          (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
          (const char *)(unsigned int)v8,
          v12);
        return v9;
      }
      memmove_0(v5, v5 + 1, 2 * v14 - 2);
      v2 = SczAllocPrefixSz(a1, L"\\\\?\\UNC");
      if ( v2 < 0 )
      {
        v4 = 166;
        goto LABEL_30;
      }
    }
    return 0;
  }
  v2 = SczAllocPrefixSz(a1, L"\\\\?\\");
  if ( v2 >= 0 )
    return 0;
  v4 = 153;
LABEL_30:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\base\\cbs\\util\\cbspath.cpp",
    (const char *)(unsigned int)v2,
    v12);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400165f8  push    rbp
0x1400165fa  push    rbx
0x1400165fb  push    rsi
0x1400165fc  push    rdi
0x1400165fd  push    r14
0x1400165ff  push    r15
0x140016601  mov     rbp, rsp
0x140016604  sub     rsp, 58h
0x140016608  mov     rax, cs:__security_cookie
0x14001660f  xor     rax, rsp
0x140016612  mov     [rbp+var_18], rax
0x140016616  xor     r15d, r15d
0x140016619  mov     rdi, rcx
0x14001661c  test    rcx, rcx
0x14001661f  jnz     short loc_14001667B
0x140016621  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016628  mov     ebx, 80004003h
0x14001662d  mov     dword ptr [rbp+var_20], ebx
0x140016630  test    rcx, rcx
0x140016633  jz      short loc_140016671
0x140016635  lea     edi, [r15+3]
0x140016639  xor     edx, edx
0x14001663b  mov     r8d, edi
0x14001663e  lea     r9, aNoFullPathResu; "No full path result specified"
0x140016645  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001664a  lea     rcx, [rbp+var_28]
0x14001664e  mov     r8d, edi
0x140016651  mov     qword ptr [rsp+58h+var_38], rcx
0x140016656  lea     rax, [rbp+var_20]
0x14001665a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016661  lea     r9, asc_14002D4FC; ": {}"
0x140016668  mov     qword ptr [rbp+var_28], rax
0x14001666c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140016671  mov     edx, 8Fh
0x140016676  jmp     loc_14001682C
0x14001667b  mov     rbx, [rcx]
0x14001667e  test    rbx, rbx
0x140016681  jnz     short loc_1400166DE
0x140016683  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001668a  mov     ebx, 80070057h
0x14001668f  mov     dword ptr [rbp+var_20], ebx
0x140016692  test    rcx, rcx
0x140016695  jz      short loc_1400166D4
0x140016697  mov     edi, 3
0x14001669c  lea     r9, aInvalidFullPat; "Invalid full path specified"
0x1400166a3  mov     r8d, edi
0x1400166a6  xor     edx, edx
0x1400166a8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400166ad  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400166b4  lea     rax, [rbp+var_20]
0x1400166b8  mov     qword ptr [rbp+var_28], rax
0x1400166bc  lea     r9, asc_14002D4FC; ": {}"
0x1400166c3  lea     rax, [rbp+var_28]
0x1400166c7  mov     r8d, edi
0x1400166ca  mov     qword ptr [rsp+58h+var_38], rax
0x1400166cf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400166d4  mov     edx, 90h
0x1400166d9  jmp     loc_14001682C
0x1400166de  movzx   eax, word ptr [rbx]
0x1400166e1  mov     ecx, 5Ch ; '\'
0x1400166e6  sub     ax, 61h ; 'a'
0x1400166ea  cmp     ax, 19h
0x1400166ee  jbe     short loc_1400166FD
0x1400166f0  movzx   eax, word ptr [rbx]
0x1400166f3  sub     ax, 41h ; 'A'
0x1400166f7  cmp     ax, 19h
0x1400166fb  ja      short loc_140016731
0x1400166fd  mov     eax, 3Ah ; ':'
0x140016702  cmp     ax, [rbx+2]
0x140016706  jnz     short loc_140016731
0x140016708  cmp     cx, [rbx+4]
0x14001670c  jnz     short loc_140016731
0x14001670e  lea     rdx, asc_14002FB90; "\\\\?\\"
0x140016715  mov     rcx, rdi
0x140016718  call    SczAllocPrefixSz
0x14001671d  mov     ebx, eax
0x14001671f  test    eax, eax
0x140016721  jns     loc_1400167D2
0x140016727  mov     edx, 99h
0x14001672c  jmp     loc_14001682C
0x140016731  or      rax, 0FFFFFFFFFFFFFFFFh
0x140016735  inc     rax
0x140016738  cmp     [rbx+rax*2], r15w
0x14001673d  jnz     short loc_140016735
0x14001673f  cmp     rax, 4
0x140016743  jb      loc_1400167D6
0x140016749  cmp     cx, [rbx]
0x14001674c  jnz     loc_1400167D6
0x140016752  cmp     cx, [rbx+2]
0x140016756  jnz     short loc_1400167D6
0x140016758  mov     eax, 3Fh ; '?'
0x14001675d  cmp     ax, [rbx+4]
0x140016761  jz      short loc_1400167D2
0x140016763  cmp     cx, [rbx+6]
0x140016767  jz      short loc_1400167D2
0x140016769  lea     rdx, [rbp+var_20]
0x14001676d  mov     [rbp+var_20], r15
0x140016771  mov     rcx, rbx
0x140016774  call    SczSize
0x140016779  mov     esi, eax
0x14001677b  test    eax, eax
0x14001677d  jns     short loc_14001679E
0x14001677f  mov     rcx, [rbp+30h]; this
0x140016783  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x14001678a  mov     r9d, eax; char *
0x14001678d  mov     edx, 0A2h; void *
0x140016792  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016797  mov     eax, esi
0x140016799  jmp     loc_140016841
0x14001679e  mov     r8, [rbp+var_20]
0x1400167a2  lea     rdx, [rbx+2]; Src
0x1400167a6  mov     rcx, rbx; void *
0x1400167a9  lea     r8, ds:0FFFFFFFFFFFFFFFEh[r8*2]; Size
0x1400167b1  call    memmove_0
0x1400167b6  lea     rdx, aUnc; "\\\\?\\UNC"
0x1400167bd  mov     rcx, rdi
0x1400167c0  call    SczAllocPrefixSz
0x1400167c5  mov     ebx, eax
0x1400167c7  test    eax, eax
0x1400167c9  jns     short loc_1400167D2
0x1400167cb  mov     edx, 0A6h
0x1400167d0  jmp     short loc_14001682C
0x1400167d2  xor     eax, eax
0x1400167d4  jmp     short loc_140016841
0x1400167d6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400167dd  mov     ebx, 80070057h
0x1400167e2  mov     dword ptr [rbp+var_20], ebx
0x1400167e5  test    rcx, rcx
0x1400167e8  jz      short loc_140016827
0x1400167ea  mov     edi, 3
0x1400167ef  lea     r9, aInvalidPathPro; "Invalid path provided to prefix."
0x1400167f6  mov     r8d, edi
0x1400167f9  xor     edx, edx
0x1400167fb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140016800  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016807  lea     rax, [rbp+var_20]
0x14001680b  mov     qword ptr [rbp+var_28], rax
0x14001680f  lea     r9, asc_14002D4FC; ": {}"
0x140016816  lea     rax, [rbp+var_28]
0x14001681a  mov     r8d, edi
0x14001681d  mov     qword ptr [rsp+58h+var_38], rax; int
0x140016822  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140016827  mov     edx, 0ABh; void *
0x14001682c  mov     rcx, [rbp+30h]; this
0x140016830  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140016837  mov     r9d, ebx; char *
0x14001683a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001683f  mov     eax, ebx
0x140016841  mov     rcx, [rbp+var_18]
0x140016845  xor     rcx, rsp; StackCookie
0x140016848  call    __security_check_cookie
0x14001684d  add     rsp, 58h
0x140016851  pop     r15
0x140016853  pop     r14
0x140016855  pop     rdi
0x140016856  pop     rsi
0x140016857  pop     rbx
0x140016858  pop     rbp
0x140016859  retn
```
