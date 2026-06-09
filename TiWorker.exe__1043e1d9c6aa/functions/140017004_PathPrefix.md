# PathPrefix

- ea: `0x140017004`
- end: `0x140017266`
- name: `PathPrefix`
- size: `610`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14001344c`
- `0x140015228`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140008d38`
- `0x140008ef4`
- `0x140017004`
- `0x140018468`
- `0x14001887c`
- `0x14002ad04`

## string_xrefs

- `0x14001704a`: `No full path result specified`
- `0x14001718f`: `onecore\base\cbs\util\cbspath.cpp`
- `0x14001723c`: `onecore\base\cbs\util\cbspath.cpp`
- `0x1400170a8`: `Invalid full path specified`
- `0x1400171fb`: `Invalid path provided to prefix.`

## pseudocode

```c
__int64 __fastcall PathPrefix(_WORD **a1)
{
  int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rdx
  _WORD *v5; // rbx
  __int64 v6; // rdx
  unsigned __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // esi
  __int64 v11; // rdx
  int v12[2]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v13; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]

  if ( !a1 )
  {
    v2 = -2147467261;
    LODWORD(v13) = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No full path result specified");
      *(_QWORD *)v12 = &v13;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v3,
        3,
        (__int64)": {}",
        (__int64)v12);
    }
    v4 = 143;
    goto LABEL_30;
  }
  v5 = *a1;
  if ( !*a1 )
  {
    v2 = -2147024809;
    LODWORD(v13) = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid full path specified");
      *(_QWORD *)v12 = &v13;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v6,
        3,
        (__int64)": {}",
        (__int64)v12);
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
      LODWORD(v13) = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid path provided to prefix.");
        *(_QWORD *)v12 = &v13;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v11,
          3,
          (__int64)": {}",
          (__int64)v12);
      }
      v4 = 171;
      goto LABEL_30;
    }
    if ( v5[2] != 63 && v5[3] != 92 )
    {
      v13 = 0;
      v8 = SczSize(v5, &v13);
      v9 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA2,
          (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
          (const char *)(unsigned int)v8);
        return v9;
      }
      memmove_0(v5, v5 + 1, 2 * v13 - 2);
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
    (int)"onecore\\base\\cbs\\util\\cbspath.cpp",
    (const char *)(unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140017004  push    rbp
0x140017006  push    rbx
0x140017007  push    rsi
0x140017008  push    rdi
0x140017009  push    r14
0x14001700b  push    r15
0x14001700d  mov     rbp, rsp
0x140017010  sub     rsp, 58h
0x140017014  mov     rax, cs:__security_cookie
0x14001701b  xor     rax, rsp
0x14001701e  mov     [rbp+var_18], rax
0x140017022  xor     r15d, r15d
0x140017025  mov     rdi, rcx
0x140017028  test    rcx, rcx
0x14001702b  jnz     short loc_140017087
0x14001702d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017034  mov     ebx, 80004003h
0x140017039  mov     dword ptr [rbp+var_20], ebx
0x14001703c  test    rcx, rcx
0x14001703f  jz      short loc_14001707D
0x140017041  lea     edi, [r15+3]
0x140017045  xor     edx, edx
0x140017047  mov     r8d, edi
0x14001704a  lea     r9, aNoFullPathResu; "No full path result specified"
0x140017051  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140017056  lea     rcx, [rbp+var_28]
0x14001705a  mov     r8d, edi
0x14001705d  mov     qword ptr [rsp+58h+var_38], rcx
0x140017062  lea     rax, [rbp+var_20]
0x140017066  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001706d  lea     r9, asc_140030534; ": {}"
0x140017074  mov     qword ptr [rbp+var_28], rax
0x140017078  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001707d  mov     edx, 8Fh
0x140017082  jmp     loc_140017238
0x140017087  mov     rbx, [rcx]
0x14001708a  test    rbx, rbx
0x14001708d  jnz     short loc_1400170EA
0x14001708f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017096  mov     ebx, 80070057h
0x14001709b  mov     dword ptr [rbp+var_20], ebx
0x14001709e  test    rcx, rcx
0x1400170a1  jz      short loc_1400170E0
0x1400170a3  mov     edi, 3
0x1400170a8  lea     r9, aInvalidFullPat; "Invalid full path specified"
0x1400170af  mov     r8d, edi
0x1400170b2  xor     edx, edx
0x1400170b4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400170b9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400170c0  lea     rax, [rbp+var_20]
0x1400170c4  mov     qword ptr [rbp+var_28], rax
0x1400170c8  lea     r9, asc_140030534; ": {}"
0x1400170cf  lea     rax, [rbp+var_28]
0x1400170d3  mov     r8d, edi
0x1400170d6  mov     qword ptr [rsp+58h+var_38], rax
0x1400170db  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400170e0  mov     edx, 90h
0x1400170e5  jmp     loc_140017238
0x1400170ea  movzx   eax, word ptr [rbx]
0x1400170ed  mov     ecx, 5Ch ; '\'
0x1400170f2  sub     ax, 61h ; 'a'
0x1400170f6  cmp     ax, 19h
0x1400170fa  jbe     short loc_140017109
0x1400170fc  movzx   eax, word ptr [rbx]
0x1400170ff  sub     ax, 41h ; 'A'
0x140017103  cmp     ax, 19h
0x140017107  ja      short loc_14001713D
0x140017109  mov     eax, 3Ah ; ':'
0x14001710e  cmp     ax, [rbx+2]
0x140017112  jnz     short loc_14001713D
0x140017114  cmp     cx, [rbx+4]
0x140017118  jnz     short loc_14001713D
0x14001711a  lea     rdx, asc_140033040; "\\\\?\\"
0x140017121  mov     rcx, rdi
0x140017124  call    SczAllocPrefixSz
0x140017129  mov     ebx, eax
0x14001712b  test    eax, eax
0x14001712d  jns     loc_1400171DE
0x140017133  mov     edx, 99h
0x140017138  jmp     loc_140017238
0x14001713d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140017141  inc     rax
0x140017144  cmp     [rbx+rax*2], r15w
0x140017149  jnz     short loc_140017141
0x14001714b  cmp     rax, 4
0x14001714f  jb      loc_1400171E2
0x140017155  cmp     cx, [rbx]
0x140017158  jnz     loc_1400171E2
0x14001715e  cmp     cx, [rbx+2]
0x140017162  jnz     short loc_1400171E2
0x140017164  mov     eax, 3Fh ; '?'
0x140017169  cmp     ax, [rbx+4]
0x14001716d  jz      short loc_1400171DE
0x14001716f  cmp     cx, [rbx+6]
0x140017173  jz      short loc_1400171DE
0x140017175  lea     rdx, [rbp+var_20]
0x140017179  mov     [rbp+var_20], r15
0x14001717d  mov     rcx, rbx
0x140017180  call    SczSize
0x140017185  mov     esi, eax
0x140017187  test    eax, eax
0x140017189  jns     short loc_1400171AA
0x14001718b  mov     rcx, [rbp+30h]; this
0x14001718f  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140017196  mov     r9d, eax; char *
0x140017199  mov     edx, 0A2h; void *
0x14001719e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400171a3  mov     eax, esi
0x1400171a5  jmp     loc_14001724D
0x1400171aa  mov     r8, [rbp+var_20]
0x1400171ae  lea     rdx, [rbx+2]; Src
0x1400171b2  mov     rcx, rbx; void *
0x1400171b5  lea     r8, ds:0FFFFFFFFFFFFFFFEh[r8*2]; Size
0x1400171bd  call    memmove_0
0x1400171c2  lea     rdx, aUnc; "\\\\?\\UNC"
0x1400171c9  mov     rcx, rdi
0x1400171cc  call    SczAllocPrefixSz
0x1400171d1  mov     ebx, eax
0x1400171d3  test    eax, eax
0x1400171d5  jns     short loc_1400171DE
0x1400171d7  mov     edx, 0A6h
0x1400171dc  jmp     short loc_140017238
0x1400171de  xor     eax, eax
0x1400171e0  jmp     short loc_14001724D
0x1400171e2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400171e9  mov     ebx, 80070057h
0x1400171ee  mov     dword ptr [rbp+var_20], ebx
0x1400171f1  test    rcx, rcx
0x1400171f4  jz      short loc_140017233
0x1400171f6  mov     edi, 3
0x1400171fb  lea     r9, aInvalidPathPro; "Invalid path provided to prefix."
0x140017202  mov     r8d, edi
0x140017205  xor     edx, edx
0x140017207  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001720c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017213  lea     rax, [rbp+var_20]
0x140017217  mov     qword ptr [rbp+var_28], rax
0x14001721b  lea     r9, asc_140030534; ": {}"
0x140017222  lea     rax, [rbp+var_28]
0x140017226  mov     r8d, edi
0x140017229  mov     qword ptr [rsp+58h+var_38], rax; int
0x14001722e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140017233  mov     edx, 0ABh; void *
0x140017238  mov     rcx, [rbp+30h]; this
0x14001723c  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140017243  mov     r9d, ebx; char *
0x140017246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001724b  mov     eax, ebx
0x14001724d  mov     rcx, [rbp+var_18]
0x140017251  xor     rcx, rsp; StackCookie
0x140017254  call    __security_check_cookie
0x140017259  add     rsp, 58h
0x14001725d  pop     r15
0x14001725f  pop     r14
0x140017261  pop     rdi
0x140017262  pop     rsi
0x140017263  pop     rbx
0x140017264  pop     rbp
0x140017265  retn
```
