# SczAllocGuid

- ea: `0x14001d7d4`
- end: `0x14001d99d`
- name: `SczAllocGuid`
- size: `457`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400175cc`

## callees

- `0x1400023e0`
- `0x140002de4`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x14001d404`
- `0x14001d7d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14001d8fb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14001d8fb`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14001d88b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14001d88b`

## string_xrefs

- `0x14001d81a`: `No path specified`

## pseudocode

```c
__int64 __fastcall SczAllocGuid(__int64 a1)
{
  int v2; // ebx
  __int64 v3; // rdx
  __int64 v4; // rdx
  HRESULT v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rdx
  int v9; // [rsp+20h] [rbp-39h]
  int v10[2]; // [rsp+30h] [rbp-29h] BYREF
  int v11; // [rsp+38h] [rbp-21h] BYREF
  GUID pguid; // [rsp+40h] [rbp-19h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( !a1 )
  {
    v2 = -2147024809;
    v11 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No path specified");
      *(_QWORD *)v10 = &v11;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v3,
        3,
        (__int64)": {}",
        (__int64)v10);
    }
    v4 = 817;
    goto LABEL_5;
  }
  pguid = 0;
  memset_0(sz, 0, 0x4Eu);
  v6 = CoCreateGuid(&pguid);
  v2 = v6;
  if ( v6 < 0 )
  {
    v11 = v6;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Error getting GUID");
      *(_QWORD *)v10 = &v11;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v7,
        3,
        (__int64)": {}",
        (__int64)v10);
    }
    v4 = 822;
    goto LABEL_5;
  }
  if ( !StringFromGUID2(&pguid, sz, 39) )
  {
    v2 = -2147418113;
    v11 = -2147418113;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Error forming string from GUID");
      *(_QWORD *)v10 = &v11;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v8,
        3,
        (__int64)": {}",
        (__int64)v10);
    }
    v4 = 823;
    goto LABEL_5;
  }
  v2 = SczAllocFromSz(a1, sz);
  if ( v2 < 0 )
  {
    v4 = 825;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)(unsigned int)v2,
      v9);
    return (unsigned int)v2;
  }
  return 0;
}

```

## disassembly

```asm
0x14001d7d4  mov     [rsp-8+arg_8], rbx
0x14001d7d9  mov     [rsp-8+arg_10], rdi
0x14001d7de  push    rbp
0x14001d7df  lea     rbp, [rsp-57h]
0x14001d7e4  sub     rsp, 0B0h
0x14001d7eb  mov     rax, cs:__security_cookie
0x14001d7f2  xor     rax, rsp
0x14001d7f5  mov     [rbp+57h+var_10], rax
0x14001d7f9  mov     rdi, rcx
0x14001d7fc  test    rcx, rcx
0x14001d7ff  jnz     short loc_14001D871
0x14001d801  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d808  mov     ebx, 80070057h
0x14001d80d  mov     [rbp+57h+var_78], ebx
0x14001d810  test    rcx, rcx
0x14001d813  jz      short loc_14001D852
0x14001d815  mov     edi, 3
0x14001d81a  lea     r9, aNoPathSpecifie; "No path specified"
0x14001d821  mov     r8d, edi
0x14001d824  xor     edx, edx
0x14001d826  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001d82b  lea     rcx, [rbp+57h+var_80]
0x14001d82f  mov     r8d, edi
0x14001d832  mov     qword ptr [rsp+0B0h+var_90], rcx; int
0x14001d837  lea     rax, [rbp+57h+var_78]
0x14001d83b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d842  lea     r9, asc_1400353E8; ": {}"
0x14001d849  mov     qword ptr [rbp+57h+var_80], rax
0x14001d84d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001d852  mov     edx, 331h; void *
0x14001d857  mov     rcx, [rbp+5Fh]; this
0x14001d85b  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x14001d862  mov     r9d, ebx; char *
0x14001d865  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d86a  mov     eax, ebx
0x14001d86c  jmp     loc_14001D97C
0x14001d871  xor     edx, edx; Val
0x14001d873  lea     rcx, [rbp+57h+sz]; void *
0x14001d877  xorps   xmm0, xmm0
0x14001d87a  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x14001d87e  lea     r8d, [rdx+4Eh]; Size
0x14001d882  call    memset_0
0x14001d887  lea     rcx, [rbp+57h+pguid]; pguid
0x14001d88b  call    cs:__imp_CoCreateGuid
0x14001d891  mov     ebx, eax
0x14001d893  test    eax, eax
0x14001d895  jns     short loc_14001D8ED
0x14001d897  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d89e  mov     [rbp+57h+var_78], eax
0x14001d8a1  test    rcx, rcx
0x14001d8a4  jz      short loc_14001D8E3
0x14001d8a6  mov     edi, 3
0x14001d8ab  lea     r9, aErrorGettingGu; "Error getting GUID"
0x14001d8b2  mov     r8d, edi
0x14001d8b5  xor     edx, edx
0x14001d8b7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001d8bc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d8c3  lea     rax, [rbp+57h+var_78]
0x14001d8c7  mov     qword ptr [rbp+57h+var_80], rax
0x14001d8cb  lea     r9, asc_1400353E8; ": {}"
0x14001d8d2  lea     rax, [rbp+57h+var_80]
0x14001d8d6  mov     r8d, edi
0x14001d8d9  mov     qword ptr [rsp+0B0h+var_90], rax
0x14001d8de  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001d8e3  mov     edx, 336h
0x14001d8e8  jmp     loc_14001D857
0x14001d8ed  mov     r8d, 27h ; '''; cchMax
0x14001d8f3  lea     rdx, [rbp+57h+sz]; lpsz
0x14001d8f7  lea     rcx, [rbp+57h+pguid]; rguid
0x14001d8fb  call    cs:__imp_StringFromGUID2
0x14001d901  test    eax, eax
0x14001d903  jnz     short loc_14001D95E
0x14001d905  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d90c  mov     ebx, 8000FFFFh
0x14001d911  mov     [rbp+57h+var_78], ebx
0x14001d914  test    rcx, rcx
0x14001d917  jz      short loc_14001D954
0x14001d919  lea     edi, [rax+3]
0x14001d91c  xor     edx, edx
0x14001d91e  mov     r8d, edi
0x14001d921  lea     r9, aErrorFormingSt; "Error forming string from GUID"
0x14001d928  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001d92d  lea     rcx, [rbp+57h+var_80]
0x14001d931  mov     r8d, edi
0x14001d934  mov     qword ptr [rsp+0B0h+var_90], rcx
0x14001d939  lea     rax, [rbp+57h+var_78]
0x14001d93d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001d944  lea     r9, asc_1400353E8; ": {}"
0x14001d94b  mov     qword ptr [rbp+57h+var_80], rax
0x14001d94f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001d954  mov     edx, 337h
0x14001d959  jmp     loc_14001D857
0x14001d95e  lea     rdx, [rbp+57h+sz]
0x14001d962  mov     rcx, rdi
0x14001d965  call    SczAllocFromSz
0x14001d96a  mov     ebx, eax
0x14001d96c  test    eax, eax
0x14001d96e  jns     short loc_14001D97A
0x14001d970  mov     edx, 339h
0x14001d975  jmp     loc_14001D857
0x14001d97a  xor     eax, eax
0x14001d97c  mov     rcx, [rbp+57h+var_10]
0x14001d980  xor     rcx, rsp; StackCookie
0x14001d983  call    __security_check_cookie
0x14001d988  lea     r11, [rsp+0B0h+var_s0]
0x14001d990  mov     rbx, [r11+18h]
0x14001d994  mov     rdi, [r11+20h]
0x14001d998  mov     rsp, r11
0x14001d99b  pop     rbp
0x14001d99c  retn
```
