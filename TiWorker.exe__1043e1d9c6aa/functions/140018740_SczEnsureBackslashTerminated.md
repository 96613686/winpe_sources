# SczEnsureBackslashTerminated

- ea: `0x140018740`
- end: `0x140018873`
- name: `SczEnsureBackslashTerminated`
- size: `307`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x1400079e8`
- `0x14000af9c`
- `0x14000e1f0`
- `0x14000f5b0`
- `0x140012678`
- `0x140012c58`
- `0x140016d8c`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140008d38`
- `0x140008ef4`
- `0x1400177d8`
- `0x140018740`

## string_xrefs

- `0x14001877a`: `No path result specified`

## pseudocode

```c
__int64 __fastcall SczEnsureBackslashTerminated(__int64 *a1)
{
  unsigned int v1; // ebx
  __int64 v2; // rdx
  __int64 v3; // rdx
  __int64 v5; // rdx
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rdx
  int v9[2]; // [rsp+30h] [rbp-28h] BYREF
  int v10; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a1 )
  {
    v1 = -2147467261;
    v10 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No path result specified");
      *(_QWORD *)v9 = &v10;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v2,
        3,
        (__int64)": {}",
        (__int64)v9);
    }
    v3 = 604;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)v1);
    return v1;
  }
  v5 = *a1;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(v5 + 2 * v6) );
  if ( *(_WORD *)(v5 + 2 * v6 - 2) != 92 )
  {
    v7 = SczAllocConcatSz(a1, L"\\");
    v1 = v7;
    if ( v7 < 0 )
    {
      v10 = v7;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to concat backslash onto string.");
        *(_QWORD *)v9 = &v10;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v8,
          3,
          (__int64)": {}",
          (__int64)v9);
      }
      v3 = 610;
      goto LABEL_5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140018740  mov     [rsp+arg_8], rbx
0x140018745  push    rdi
0x140018746  sub     rsp, 50h
0x14001874a  mov     rax, cs:__security_cookie
0x140018751  xor     rax, rsp
0x140018754  mov     [rsp+58h+var_18], rax
0x140018759  xor     edi, edi
0x14001875b  test    rcx, rcx
0x14001875e  jnz     short loc_1400187D5
0x140018760  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018767  mov     ebx, 80004003h
0x14001876c  mov     [rsp+58h+var_20], ebx
0x140018770  test    rcx, rcx
0x140018773  jz      short loc_1400187B5
0x140018775  mov     edi, 3
0x14001877a  lea     r9, aNoPathResultSp; "No path result specified"
0x140018781  mov     r8d, edi
0x140018784  xor     edx, edx
0x140018786  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001878b  lea     rcx, [rsp+58h+var_28]
0x140018790  mov     r8d, edi
0x140018793  mov     qword ptr [rsp+58h+var_38], rcx; int
0x140018798  lea     rax, [rsp+58h+var_20]
0x14001879d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400187a4  lea     r9, asc_140030534; ": {}"
0x1400187ab  mov     qword ptr [rsp+58h+var_28], rax
0x1400187b0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400187b5  mov     edx, 25Ch; void *
0x1400187ba  mov     rcx, [rsp+58h]; this
0x1400187bf  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x1400187c6  mov     r9d, ebx; char *
0x1400187c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400187ce  mov     eax, ebx
0x1400187d0  jmp     loc_14001885B
0x1400187d5  mov     rdx, [rcx]
0x1400187d8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400187dc  inc     rax
0x1400187df  cmp     [rdx+rax*2], di
0x1400187e3  jnz     short loc_1400187DC
0x1400187e5  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x1400187eb  jz      short loc_140018859
0x1400187ed  lea     rdx, asc_14002E964; "\\"
0x1400187f4  call    SczAllocConcatSz
0x1400187f9  mov     ebx, eax
0x1400187fb  test    eax, eax
0x1400187fd  jns     short loc_140018859
0x1400187ff  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018806  mov     [rsp+58h+var_20], eax
0x14001880a  test    rcx, rcx
0x14001880d  jz      short loc_14001884F
0x14001880f  mov     edi, 3
0x140018814  lea     r9, aFailedToConcat_2; "Failed to concat backslash onto string."
0x14001881b  mov     r8d, edi
0x14001881e  xor     edx, edx
0x140018820  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140018825  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001882c  lea     rax, [rsp+58h+var_20]
0x140018831  mov     qword ptr [rsp+58h+var_28], rax
0x140018836  lea     r9, asc_140030534; ": {}"
0x14001883d  lea     rax, [rsp+58h+var_28]
0x140018842  mov     r8d, edi
0x140018845  mov     qword ptr [rsp+58h+var_38], rax
0x14001884a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001884f  mov     edx, 262h
0x140018854  jmp     loc_1400187BA
0x140018859  xor     eax, eax
0x14001885b  mov     rcx, [rsp+58h+var_18]
0x140018860  xor     rcx, rsp; StackCookie
0x140018863  call    __security_check_cookie
0x140018868  mov     rbx, [rsp+58h+arg_8]
0x14001886d  add     rsp, 50h
0x140018871  pop     rdi
0x140018872  retn
```
