# SczAllocGuid

- ea: `0x140018298`
- end: `0x140018461`
- name: `SczAllocGuid`
- size: `457`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000e1f0`
- `0x140013d48`

## callees

- `0x140002310`
- `0x140002cf8`
- `0x1400053c0`
- `0x140008d38`
- `0x140008ef4`
- `0x140017ec8`
- `0x140018298`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14001834f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x14001834f`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400183bf`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400183bf`

## string_xrefs

- `0x1400182de`: `No path specified`

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
  int v9[2]; // [rsp+30h] [rbp-29h] BYREF
  int v10; // [rsp+38h] [rbp-21h] BYREF
  GUID pguid; // [rsp+40h] [rbp-19h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( !a1 )
  {
    v2 = -2147024809;
    v10 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No path specified");
      *(_QWORD *)v9 = &v10;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v3,
        3,
        (__int64)": {}",
        (__int64)v9);
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
    v10 = v6;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Error getting GUID");
      *(_QWORD *)v9 = &v10;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v7,
        3,
        (__int64)": {}",
        (__int64)v9);
    }
    v4 = 822;
    goto LABEL_5;
  }
  if ( !StringFromGUID2(&pguid, sz, 39) )
  {
    v2 = -2147418113;
    v10 = -2147418113;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Error forming string from GUID");
      *(_QWORD *)v9 = &v10;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v8,
        3,
        (__int64)": {}",
        (__int64)v9);
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
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)(unsigned int)v2);
    return (unsigned int)v2;
  }
  return 0;
}

```

## disassembly

```asm
0x140018298  mov     [rsp-8+arg_8], rbx
0x14001829d  mov     [rsp-8+arg_10], rdi
0x1400182a2  push    rbp
0x1400182a3  lea     rbp, [rsp-57h]
0x1400182a8  sub     rsp, 0B0h
0x1400182af  mov     rax, cs:__security_cookie
0x1400182b6  xor     rax, rsp
0x1400182b9  mov     [rbp+57h+var_10], rax
0x1400182bd  mov     rdi, rcx
0x1400182c0  test    rcx, rcx
0x1400182c3  jnz     short loc_140018335
0x1400182c5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400182cc  mov     ebx, 80070057h
0x1400182d1  mov     [rbp+57h+var_78], ebx
0x1400182d4  test    rcx, rcx
0x1400182d7  jz      short loc_140018316
0x1400182d9  mov     edi, 3
0x1400182de  lea     r9, aNoPathSpecifie; "No path specified"
0x1400182e5  mov     r8d, edi
0x1400182e8  xor     edx, edx
0x1400182ea  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400182ef  lea     rcx, [rbp+57h+var_80]
0x1400182f3  mov     r8d, edi
0x1400182f6  mov     qword ptr [rsp+0B0h+var_90], rcx; int
0x1400182fb  lea     rax, [rbp+57h+var_78]
0x1400182ff  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018306  lea     r9, asc_140030534; ": {}"
0x14001830d  mov     qword ptr [rbp+57h+var_80], rax
0x140018311  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140018316  mov     edx, 331h; void *
0x14001831b  mov     rcx, [rbp+5Fh]; this
0x14001831f  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x140018326  mov     r9d, ebx; char *
0x140018329  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001832e  mov     eax, ebx
0x140018330  jmp     loc_140018440
0x140018335  xor     edx, edx; Val
0x140018337  lea     rcx, [rbp+57h+sz]; void *
0x14001833b  xorps   xmm0, xmm0
0x14001833e  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x140018342  lea     r8d, [rdx+4Eh]; Size
0x140018346  call    memset_0
0x14001834b  lea     rcx, [rbp+57h+pguid]; pguid
0x14001834f  call    cs:__imp_CoCreateGuid
0x140018355  mov     ebx, eax
0x140018357  test    eax, eax
0x140018359  jns     short loc_1400183B1
0x14001835b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018362  mov     [rbp+57h+var_78], eax
0x140018365  test    rcx, rcx
0x140018368  jz      short loc_1400183A7
0x14001836a  mov     edi, 3
0x14001836f  lea     r9, aErrorGettingGu; "Error getting GUID"
0x140018376  mov     r8d, edi
0x140018379  xor     edx, edx
0x14001837b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140018380  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018387  lea     rax, [rbp+57h+var_78]
0x14001838b  mov     qword ptr [rbp+57h+var_80], rax
0x14001838f  lea     r9, asc_140030534; ": {}"
0x140018396  lea     rax, [rbp+57h+var_80]
0x14001839a  mov     r8d, edi
0x14001839d  mov     qword ptr [rsp+0B0h+var_90], rax
0x1400183a2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400183a7  mov     edx, 336h
0x1400183ac  jmp     loc_14001831B
0x1400183b1  mov     r8d, 27h ; '''; cchMax
0x1400183b7  lea     rdx, [rbp+57h+sz]; lpsz
0x1400183bb  lea     rcx, [rbp+57h+pguid]; rguid
0x1400183bf  call    cs:__imp_StringFromGUID2
0x1400183c5  test    eax, eax
0x1400183c7  jnz     short loc_140018422
0x1400183c9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400183d0  mov     ebx, 8000FFFFh
0x1400183d5  mov     [rbp+57h+var_78], ebx
0x1400183d8  test    rcx, rcx
0x1400183db  jz      short loc_140018418
0x1400183dd  lea     edi, [rax+3]
0x1400183e0  xor     edx, edx
0x1400183e2  mov     r8d, edi
0x1400183e5  lea     r9, aErrorFormingSt; "Error forming string from GUID"
0x1400183ec  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400183f1  lea     rcx, [rbp+57h+var_80]
0x1400183f5  mov     r8d, edi
0x1400183f8  mov     qword ptr [rsp+0B0h+var_90], rcx
0x1400183fd  lea     rax, [rbp+57h+var_78]
0x140018401  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018408  lea     r9, asc_140030534; ": {}"
0x14001840f  mov     qword ptr [rbp+57h+var_80], rax
0x140018413  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140018418  mov     edx, 337h
0x14001841d  jmp     loc_14001831B
0x140018422  lea     rdx, [rbp+57h+sz]
0x140018426  mov     rcx, rdi
0x140018429  call    SczAllocFromSz
0x14001842e  mov     ebx, eax
0x140018430  test    eax, eax
0x140018432  jns     short loc_14001843E
0x140018434  mov     edx, 339h
0x140018439  jmp     loc_14001831B
0x14001843e  xor     eax, eax
0x140018440  mov     rcx, [rbp+57h+var_10]
0x140018444  xor     rcx, rsp; StackCookie
0x140018447  call    __security_check_cookie
0x14001844c  lea     r11, [rsp+0B0h+var_s0]
0x140018454  mov     rbx, [r11+18h]
0x140018458  mov     rdi, [r11+20h]
0x14001845c  mov     rsp, r11
0x14001845f  pop     rbp
0x140018460  retn
```
