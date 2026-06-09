# PathPrefix

- ea: `0x14002180c`
- end: `0x140021a6e`
- name: `PathPrefix`
- size: `610`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14001fc6c`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x14001d9a4`
- `0x14001e050`
- `0x14002180c`
- `0x14002a964`

## string_xrefs

- `0x140021852`: `No full path result specified`
- `0x140021997`: `onecore\base\cbs\util\cbspath.cpp`
- `0x140021a44`: `onecore\base\cbs\util\cbspath.cpp`
- `0x1400218b0`: `Invalid full path specified`
- `0x140021a03`: `Invalid path provided to prefix.`

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
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No full path result specified");
      *(_QWORD *)v13 = &v14;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v3,
        3,
        (__int64)": {}",
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
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid full path specified");
      *(_QWORD *)v13 = &v14;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v6,
        3,
        (__int64)": {}",
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
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid path provided to prefix.");
        *(_QWORD *)v13 = &v14;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v11,
          3,
          (__int64)": {}",
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
0x14002180c  push    rbp
0x14002180e  push    rbx
0x14002180f  push    rsi
0x140021810  push    rdi
0x140021811  push    r14
0x140021813  push    r15
0x140021815  mov     rbp, rsp
0x140021818  sub     rsp, 58h
0x14002181c  mov     rax, cs:__security_cookie
0x140021823  xor     rax, rsp
0x140021826  mov     [rbp+var_18], rax
0x14002182a  xor     r15d, r15d
0x14002182d  mov     rdi, rcx
0x140021830  test    rcx, rcx
0x140021833  jnz     short loc_14002188F
0x140021835  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002183c  mov     ebx, 80004003h
0x140021841  mov     dword ptr [rbp+var_20], ebx
0x140021844  test    rcx, rcx
0x140021847  jz      short loc_140021885
0x140021849  lea     edi, [r15+3]
0x14002184d  xor     edx, edx
0x14002184f  mov     r8d, edi
0x140021852  lea     r9, aNoFullPathResu; "No full path result specified"
0x140021859  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14002185e  lea     rcx, [rbp+var_28]
0x140021862  mov     r8d, edi
0x140021865  mov     qword ptr [rsp+58h+var_38], rcx
0x14002186a  lea     rax, [rbp+var_20]
0x14002186e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140021875  lea     r9, asc_1400353E8; ": {}"
0x14002187c  mov     qword ptr [rbp+var_28], rax
0x140021880  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140021885  mov     edx, 8Fh
0x14002188a  jmp     loc_140021A40
0x14002188f  mov     rbx, [rcx]
0x140021892  test    rbx, rbx
0x140021895  jnz     short loc_1400218F2
0x140021897  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14002189e  mov     ebx, 80070057h
0x1400218a3  mov     dword ptr [rbp+var_20], ebx
0x1400218a6  test    rcx, rcx
0x1400218a9  jz      short loc_1400218E8
0x1400218ab  mov     edi, 3
0x1400218b0  lea     r9, aInvalidFullPat; "Invalid full path specified"
0x1400218b7  mov     r8d, edi
0x1400218ba  xor     edx, edx
0x1400218bc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400218c1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400218c8  lea     rax, [rbp+var_20]
0x1400218cc  mov     qword ptr [rbp+var_28], rax
0x1400218d0  lea     r9, asc_1400353E8; ": {}"
0x1400218d7  lea     rax, [rbp+var_28]
0x1400218db  mov     r8d, edi
0x1400218de  mov     qword ptr [rsp+58h+var_38], rax
0x1400218e3  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400218e8  mov     edx, 90h
0x1400218ed  jmp     loc_140021A40
0x1400218f2  movzx   eax, word ptr [rbx]
0x1400218f5  mov     ecx, 5Ch ; '\'
0x1400218fa  sub     ax, 61h ; 'a'
0x1400218fe  cmp     ax, 19h
0x140021902  jbe     short loc_140021911
0x140021904  movzx   eax, word ptr [rbx]
0x140021907  sub     ax, 41h ; 'A'
0x14002190b  cmp     ax, 19h
0x14002190f  ja      short loc_140021945
0x140021911  mov     eax, 3Ah ; ':'
0x140021916  cmp     ax, [rbx+2]
0x14002191a  jnz     short loc_140021945
0x14002191c  cmp     cx, [rbx+4]
0x140021920  jnz     short loc_140021945
0x140021922  lea     rdx, asc_140037598; "\\\\?\\"
0x140021929  mov     rcx, rdi
0x14002192c  call    SczAllocPrefixSz
0x140021931  mov     ebx, eax
0x140021933  test    eax, eax
0x140021935  jns     loc_1400219E6
0x14002193b  mov     edx, 99h
0x140021940  jmp     loc_140021A40
0x140021945  or      rax, 0FFFFFFFFFFFFFFFFh
0x140021949  inc     rax
0x14002194c  cmp     [rbx+rax*2], r15w
0x140021951  jnz     short loc_140021949
0x140021953  cmp     rax, 4
0x140021957  jb      loc_1400219EA
0x14002195d  cmp     cx, [rbx]
0x140021960  jnz     loc_1400219EA
0x140021966  cmp     cx, [rbx+2]
0x14002196a  jnz     short loc_1400219EA
0x14002196c  mov     eax, 3Fh ; '?'
0x140021971  cmp     ax, [rbx+4]
0x140021975  jz      short loc_1400219E6
0x140021977  cmp     cx, [rbx+6]
0x14002197b  jz      short loc_1400219E6
0x14002197d  lea     rdx, [rbp+var_20]
0x140021981  mov     [rbp+var_20], r15
0x140021985  mov     rcx, rbx
0x140021988  call    SczSize
0x14002198d  mov     esi, eax
0x14002198f  test    eax, eax
0x140021991  jns     short loc_1400219B2
0x140021993  mov     rcx, [rbp+30h]; this
0x140021997  lea     r8, aOnecoreBaseCbs_14; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x14002199e  mov     r9d, eax; char *
0x1400219a1  mov     edx, 0A2h; void *
0x1400219a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400219ab  mov     eax, esi
0x1400219ad  jmp     loc_140021A55
0x1400219b2  mov     r8, [rbp+var_20]
0x1400219b6  lea     rdx, [rbx+2]; Src
0x1400219ba  mov     rcx, rbx; void *
0x1400219bd  lea     r8, ds:0FFFFFFFFFFFFFFFEh[r8*2]; Size
0x1400219c5  call    memmove_0
0x1400219ca  lea     rdx, aUnc; "\\\\?\\UNC"
0x1400219d1  mov     rcx, rdi
0x1400219d4  call    SczAllocPrefixSz
0x1400219d9  mov     ebx, eax
0x1400219db  test    eax, eax
0x1400219dd  jns     short loc_1400219E6
0x1400219df  mov     edx, 0A6h
0x1400219e4  jmp     short loc_140021A40
0x1400219e6  xor     eax, eax
0x1400219e8  jmp     short loc_140021A55
0x1400219ea  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400219f1  mov     ebx, 80070057h
0x1400219f6  mov     dword ptr [rbp+var_20], ebx
0x1400219f9  test    rcx, rcx
0x1400219fc  jz      short loc_140021A3B
0x1400219fe  mov     edi, 3
0x140021a03  lea     r9, aInvalidPathPro; "Invalid path provided to prefix."
0x140021a0a  mov     r8d, edi
0x140021a0d  xor     edx, edx
0x140021a0f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140021a14  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140021a1b  lea     rax, [rbp+var_20]
0x140021a1f  mov     qword ptr [rbp+var_28], rax
0x140021a23  lea     r9, asc_1400353E8; ": {}"
0x140021a2a  lea     rax, [rbp+var_28]
0x140021a2e  mov     r8d, edi
0x140021a31  mov     qword ptr [rsp+58h+var_38], rax; int
0x140021a36  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140021a3b  mov     edx, 0ABh; void *
0x140021a40  mov     rcx, [rbp+30h]; this
0x140021a44  lea     r8, aOnecoreBaseCbs_14; "onecore\\base\\cbs\\util\\cbspath.cpp"
0x140021a4b  mov     r9d, ebx; char *
0x140021a4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140021a53  mov     eax, ebx
0x140021a55  mov     rcx, [rbp+var_18]
0x140021a59  xor     rcx, rsp; StackCookie
0x140021a5c  call    __security_check_cookie
0x140021a61  add     rsp, 58h
0x140021a65  pop     r15
0x140021a67  pop     r14
0x140021a69  pop     rdi
0x140021a6a  pop     rsi
0x140021a6b  pop     rbx
0x140021a6c  pop     rbp
0x140021a6d  retn
```
