# SczAllocFromSzAndEnsureBackslash

- ea: `0x140018090`
- end: `0x140018292`
- name: `SczAllocFromSzAndEnsureBackslash`
- size: `514`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140014ef0`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140005754`
- `0x140008d38`
- `0x140008ef4`
- `0x14001726c`
- `0x140018090`

## string_xrefs

- `0x14001820e`: `Failed to copy source string to destination`

## pseudocode

```c
__int64 __fastcall SczAllocFromSzAndEnsureBackslash(wchar_t **a1, wchar_t *a2)
{
  unsigned int v4; // edi
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v8; // rdx
  __int64 v9; // rax
  wchar_t v10; // r15
  __int64 v11; // r14
  int v12; // eax
  unsigned int v13; // esi
  int v14; // eax
  __int64 v15; // rdx
  int v16[2]; // [rsp+30h] [rbp-20h] BYREF
  int v17; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  if ( !a1 )
  {
    v4 = -2147467261;
    v17 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string result specified");
      *(_QWORD *)v16 = &v17;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v16);
    }
    v6 = 411;
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
    v17 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No string specified");
      *(_QWORD *)v16 = &v17;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v8,
        3,
        (__int64)": {}",
        (__int64)v16);
    }
    v6 = 412;
    goto LABEL_5;
  }
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  v10 = a2[v9 - 1];
  v11 = v9 + 1;
  if ( v10 == 92 )
    v11 = v9;
  v12 = SczAlloc(a1, v11 + 1);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v14 = StringCchCopyW(*a1, v11 + 1, a2);
    v4 = v14;
    if ( v14 < 0 )
    {
      v17 = v14;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy source string to destination");
        *(_QWORD *)v16 = &v17;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v15,
          3,
          (__int64)": {}",
          (__int64)v16);
      }
      v6 = 423;
      goto LABEL_5;
    }
    if ( v10 != 92 )
    {
      (*a1)[v11 - 1] = 92;
      (*a1)[v11] = 0;
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)(unsigned int)v12);
    return v13;
  }
}

```

## disassembly

```asm
0x140018090  mov     [rsp-38h+arg_10], rbx
0x140018095  push    rbp
0x140018096  push    rsi
0x140018097  push    rdi
0x140018098  push    r12
0x14001809a  push    r13
0x14001809c  push    r14
0x14001809e  push    r15
0x1400180a0  mov     rbp, rsp
0x1400180a3  sub     rsp, 50h
0x1400180a7  mov     rax, cs:__security_cookie
0x1400180ae  xor     rax, rsp
0x1400180b1  mov     [rbp+var_10], rax
0x1400180b5  xor     r13d, r13d
0x1400180b8  mov     rdi, rdx
0x1400180bb  mov     rbx, rcx
0x1400180be  test    rcx, rcx
0x1400180c1  jnz     short loc_140018132
0x1400180c3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400180ca  mov     edi, 80004003h
0x1400180cf  mov     [rbp+var_18], edi
0x1400180d2  test    rcx, rcx
0x1400180d5  jz      short loc_140018113
0x1400180d7  lea     ebx, [r13+3]
0x1400180db  xor     edx, edx
0x1400180dd  mov     r8d, ebx
0x1400180e0  lea     r9, aNoStringResult; "No string result specified"
0x1400180e7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400180ec  lea     rcx, [rbp+var_20]
0x1400180f0  mov     r8d, ebx
0x1400180f3  mov     qword ptr [rsp+50h+var_30], rcx; int
0x1400180f8  lea     rax, [rbp+var_18]
0x1400180fc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018103  lea     r9, asc_140030534; ": {}"
0x14001810a  mov     qword ptr [rbp+var_20], rax
0x14001810e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140018113  mov     edx, 19Bh; void *
0x140018118  mov     rcx, [rbp+38h]; this
0x14001811c  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x140018123  mov     r9d, edi; char *
0x140018126  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001812b  mov     eax, edi
0x14001812d  jmp     loc_14001826E
0x140018132  test    rdi, rdi
0x140018135  jnz     short loc_14001818F
0x140018137  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001813e  mov     edi, 80070057h
0x140018143  mov     [rbp+var_18], edi
0x140018146  test    rcx, rcx
0x140018149  jz      short loc_140018188
0x14001814b  mov     ebx, 3
0x140018150  lea     r9, aNoStringSpecif; "No string specified"
0x140018157  mov     r8d, ebx
0x14001815a  xor     edx, edx
0x14001815c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140018161  lea     rcx, [rbp+var_20]
0x140018165  mov     r8d, ebx
0x140018168  mov     qword ptr [rsp+50h+var_30], rcx
0x14001816d  lea     rax, [rbp+var_18]
0x140018171  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018178  lea     r9, asc_140030534; ": {}"
0x14001817f  mov     qword ptr [rbp+var_20], rax
0x140018183  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140018188  mov     edx, 19Ch
0x14001818d  jmp     short loc_140018118
0x14001818f  or      rax, 0FFFFFFFFFFFFFFFFh
0x140018193  inc     rax
0x140018196  cmp     [rdx+rax*2], r13w
0x14001819b  jnz     short loc_140018193
0x14001819d  movzx   r15d, word ptr [rdx+rax*2-2]
0x1400181a3  lea     r14, [rax+1]
0x1400181a7  mov     ecx, 5Ch ; '\'
0x1400181ac  cmp     r15w, cx
0x1400181b0  mov     rcx, rbx
0x1400181b3  cmovz   r14, rax
0x1400181b7  lea     rdx, [r14+1]
0x1400181bb  call    SczAlloc
0x1400181c0  mov     esi, eax
0x1400181c2  test    eax, eax
0x1400181c4  jns     short loc_1400181E5
0x1400181c6  mov     rcx, [rbp+38h]; this
0x1400181ca  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x1400181d1  mov     r9d, eax; char *
0x1400181d4  mov     edx, 1A6h; void *
0x1400181d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400181de  mov     eax, esi
0x1400181e0  jmp     loc_14001826E
0x1400181e5  mov     rcx, [rbx]; wchar_t *
0x1400181e8  lea     rdx, [r14+1]; unsigned __int64
0x1400181ec  mov     r8, rdi; wchar_t *
0x1400181ef  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400181f4  mov     edi, eax
0x1400181f6  test    eax, eax
0x1400181f8  jns     short loc_140018250
0x1400181fa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018201  mov     [rbp+var_18], eax
0x140018204  test    rcx, rcx
0x140018207  jz      short loc_140018246
0x140018209  mov     ebx, 3
0x14001820e  lea     r9, aFailedToCopySo; "Failed to copy source string to destina"...
0x140018215  mov     r8d, ebx
0x140018218  xor     edx, edx
0x14001821a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001821f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018226  lea     rax, [rbp+var_18]
0x14001822a  mov     qword ptr [rbp+var_20], rax
0x14001822e  lea     r9, asc_140030534; ": {}"
0x140018235  lea     rax, [rbp+var_20]
0x140018239  mov     r8d, ebx
0x14001823c  mov     qword ptr [rsp+50h+var_30], rax
0x140018241  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140018246  mov     edx, 1A7h
0x14001824b  jmp     loc_140018118
0x140018250  mov     ecx, 5Ch ; '\'
0x140018255  cmp     r15w, cx
0x140018259  jz      short loc_14001826C
0x14001825b  mov     rax, [rbx]
0x14001825e  mov     [rax+r14*2-2], cx
0x140018264  mov     rcx, [rbx]
0x140018267  mov     [rcx+r14*2], r13w
0x14001826c  xor     eax, eax
0x14001826e  mov     rcx, [rbp+var_10]
0x140018272  xor     rcx, rsp; StackCookie
0x140018275  call    __security_check_cookie
0x14001827a  mov     rbx, [rsp+50h+arg_10]
0x140018282  add     rsp, 50h
0x140018286  pop     r15
0x140018288  pop     r14
0x14001828a  pop     r13
0x14001828c  pop     r12
0x14001828e  pop     rdi
0x14001828f  pop     rsi
0x140018290  pop     rbp
0x140018291  retn
```
