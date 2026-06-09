# SczAllocFromSz

- ea: `0x140017ec8`
- end: `0x14001808a`
- name: `SczAllocFromSz`
- size: `450`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x14000e824`
- `0x14000f02c`
- `0x14000f5b0`
- `0x140012678`
- `0x140012c58`
- `0x14001344c`
- `0x140013d48`
- `0x140015228`
- `0x140018298`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140005754`
- `0x140008d38`
- `0x140008ef4`
- `0x14001726c`
- `0x140017ec8`

## string_xrefs

- `0x140018026`: `Failed to copy source string to destination`

## pseudocode

```c
__int64 __fastcall SczAllocFromSz(wchar_t **a1, wchar_t *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v8; // rdx
  __int64 v9; // rax
  size_t v10; // r14
  int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  __int64 v14; // rdx
  int v15[2]; // [rsp+30h] [rbp-20h] BYREF
  int v16; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  if ( !a1 )
  {
    v4 = -2147467261;
    v16 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string result specified");
      *(_QWORD *)v15 = &v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v15);
    }
    v6 = 399;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)v4);
    return v4;
  }
  if ( !a2 )
  {
    v4 = -2147024809;
    v16 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string specified");
      *(_QWORD *)v15 = &v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v8,
        3,
        (__int64)": {}",
        (__int64)v15);
    }
    v6 = 400;
    goto LABEL_5;
  }
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  v10 = v9 + 1;
  v11 = SczAlloc(a1, v9 + 1);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v13 = StringCchCopyW(*a1, v10, a2);
    v4 = v13;
    if ( v13 < 0 )
    {
      v16 = v13;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy source string to destination");
        *(_QWORD *)v15 = &v16;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v14,
          3,
          (__int64)": {}",
          (__int64)v15);
      }
      v6 = 404;
      goto LABEL_5;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x193,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)(unsigned int)v11);
    return v12;
  }
}

```

## disassembly

```asm
0x140017ec8  mov     [rsp-28h+arg_10], rbx
0x140017ecd  push    rbp
0x140017ece  push    rsi
0x140017ecf  push    rdi
0x140017ed0  push    r14
0x140017ed2  push    r15
0x140017ed4  mov     rbp, rsp
0x140017ed7  sub     rsp, 50h
0x140017edb  mov     rax, cs:__security_cookie
0x140017ee2  xor     rax, rsp
0x140017ee5  mov     [rbp+var_10], rax
0x140017ee9  xor     r15d, r15d
0x140017eec  mov     rbx, rdx
0x140017eef  mov     rsi, rcx
0x140017ef2  test    rcx, rcx
0x140017ef5  jnz     short loc_140017F65
0x140017ef7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017efe  mov     ebx, 80004003h
0x140017f03  mov     [rbp+var_18], ebx
0x140017f06  test    rcx, rcx
0x140017f09  jz      short loc_140017F46
0x140017f0b  lea     edi, [rsi+3]
0x140017f0e  xor     edx, edx
0x140017f10  mov     r8d, edi
0x140017f13  lea     r9, aNoStringResult; "No string result specified"
0x140017f1a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140017f1f  lea     rcx, [rbp+var_20]
0x140017f23  mov     r8d, edi
0x140017f26  mov     qword ptr [rsp+50h+var_30], rcx; int
0x140017f2b  lea     rax, [rbp+var_18]
0x140017f2f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017f36  lea     r9, asc_140030534; ": {}"
0x140017f3d  mov     qword ptr [rbp+var_20], rax
0x140017f41  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140017f46  mov     edx, 18Fh; void *
0x140017f4b  mov     rcx, [rbp+28h]; this
0x140017f4f  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x140017f56  mov     r9d, ebx; char *
0x140017f59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017f5e  mov     eax, ebx
0x140017f60  jmp     loc_14001806A
0x140017f65  test    rbx, rbx
0x140017f68  jnz     short loc_140017FC2
0x140017f6a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017f71  mov     ebx, 80070057h
0x140017f76  mov     [rbp+var_18], ebx
0x140017f79  test    rcx, rcx
0x140017f7c  jz      short loc_140017FBB
0x140017f7e  mov     edi, 3
0x140017f83  lea     r9, aNoStringSpecif; "No string specified"
0x140017f8a  mov     r8d, edi
0x140017f8d  xor     edx, edx
0x140017f8f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140017f94  lea     rcx, [rbp+var_20]
0x140017f98  mov     r8d, edi
0x140017f9b  mov     qword ptr [rsp+50h+var_30], rcx
0x140017fa0  lea     rax, [rbp+var_18]
0x140017fa4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017fab  lea     r9, asc_140030534; ": {}"
0x140017fb2  mov     qword ptr [rbp+var_20], rax
0x140017fb6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140017fbb  mov     edx, 190h
0x140017fc0  jmp     short loc_140017F4B
0x140017fc2  or      rax, 0FFFFFFFFFFFFFFFFh
0x140017fc6  inc     rax
0x140017fc9  cmp     [rdx+rax*2], r15w
0x140017fce  jnz     short loc_140017FC6
0x140017fd0  lea     r14, [rax+1]
0x140017fd4  mov     rdx, r14
0x140017fd7  call    SczAlloc
0x140017fdc  mov     edi, eax
0x140017fde  test    eax, eax
0x140017fe0  jns     short loc_140017FFE
0x140017fe2  mov     rcx, [rbp+28h]; this
0x140017fe6  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x140017fed  mov     r9d, eax; char *
0x140017ff0  mov     edx, 193h; void *
0x140017ff5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017ffa  mov     eax, edi
0x140017ffc  jmp     short loc_14001806A
0x140017ffe  mov     rcx, [rsi]; wchar_t *
0x140018001  mov     r8, rbx; wchar_t *
0x140018004  mov     rdx, r14; unsigned __int64
0x140018007  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14001800c  mov     ebx, eax
0x14001800e  test    eax, eax
0x140018010  jns     short loc_140018068
0x140018012  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018019  mov     [rbp+var_18], eax
0x14001801c  test    rcx, rcx
0x14001801f  jz      short loc_14001805E
0x140018021  mov     edi, 3
0x140018026  lea     r9, aFailedToCopySo; "Failed to copy source string to destina"...
0x14001802d  mov     r8d, edi
0x140018030  xor     edx, edx
0x140018032  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140018037  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001803e  lea     rax, [rbp+var_18]
0x140018042  mov     qword ptr [rbp+var_20], rax
0x140018046  lea     r9, asc_140030534; ": {}"
0x14001804d  lea     rax, [rbp+var_20]
0x140018051  mov     r8d, edi
0x140018054  mov     qword ptr [rsp+50h+var_30], rax
0x140018059  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001805e  mov     edx, 194h
0x140018063  jmp     loc_140017F4B
0x140018068  xor     eax, eax
0x14001806a  mov     rcx, [rbp+var_10]
0x14001806e  xor     rcx, rsp; StackCookie
0x140018071  call    __security_check_cookie
0x140018076  mov     rbx, [rsp+50h+arg_10]
0x14001807e  add     rsp, 50h
0x140018082  pop     r15
0x140018084  pop     r14
0x140018086  pop     rdi
0x140018087  pop     rsi
0x140018088  pop     rbp
0x140018089  retn
```
