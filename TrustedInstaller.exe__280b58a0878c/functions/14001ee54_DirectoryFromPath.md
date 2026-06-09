# DirectoryFromPath

- ea: `0x14001ee54`
- end: `0x14001f0f3`
- name: `DirectoryFromPath`
- size: `671`
- prototype: `__int64 __fastcall(wchar_t *, wchar_t **)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140010d00`
- `0x140018630`

## callees

- `0x1400023e0`
- `0x140002674`
- `0x1400054b0`
- `0x14000ee94`
- `0x140016a40`
- `0x140016fb4`
- `0x14001c5fc`
- `0x14001c7a8`
- `0x14001ee54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14001ef5d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x14001ef5d`

## string_xrefs

- `0x14001eff3`: `Failed to copy source string to destination`
- `0x14001eea4`: `No path specified`
- `0x14001eeff`: `No directory result specified`
- `0x14001f07d`: `Invalid path.`

## pseudocode

```c
__int64 __fastcall DirectoryFromPath(wchar_t *a1, wchar_t **a2)
{
  unsigned int v4; // ebx
  int v5; // edx
  __int64 v6; // rdx
  int v7; // edx
  wchar_t *v8; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // r15
  int v11; // eax
  unsigned int v12; // esi
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  wchar_t *v15; // r14
  unsigned __int64 v16; // rax
  int v17; // eax
  int v18; // edx
  int v20; // edx
  int v21; // [rsp+20h] [rbp-30h]
  wchar_t *v22; // [rsp+30h] [rbp-20h] BYREF
  int v23[2]; // [rsp+38h] [rbp-18h] BYREF
  int v24; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  if ( a1 )
  {
    if ( a2 )
    {
      if ( *a2 )
      {
        operator delete(*a2 - 4, (unsigned __int64)a2);
        *a2 = 0;
      }
      v8 = wcsrchr(a1, 0x5Cu);
      if ( v8 && v8 != a1 )
      {
        v22 = 0;
        v9 = v8 - a1;
        v10 = v9 + 1;
        v11 = SczAlloc(&v22, v9 + 3);
        v12 = v11;
        if ( v11 >= 0 )
        {
          v15 = v22;
          if ( !v22 )
            goto LABEL_24;
          v16 = -1;
          do
            ++v16;
          while ( a1[v16] );
          if ( v10 > v16 || (v17 = StringCchCopyNW(v22, v10 + 2, a1, v10), v12 = v17, v17 >= 0) )
          {
LABEL_24:
            v22 = 0;
            *a2 = v15;
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v22);
            return 0;
          }
          v24 = v17;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              LogAdapter::g_Logger,
              0,
              3,
              "Failed to copy source string to destination");
            *(_QWORD *)v23 = &v24;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v18,
              3,
              (unsigned int)": {}",
              (__int64)v23);
          }
          v13 = v12;
          v14 = 59;
        }
        else
        {
          v13 = (unsigned int)v11;
          v14 = 52;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
          (const char *)v13,
          v21);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v22);
        return v12;
      }
      v4 = -2147024809;
      v24 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Invalid path.");
        *(_QWORD *)v23 = &v24;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v20,
          3,
          (unsigned int)": {}",
          (__int64)v23);
      }
      v6 = 46;
    }
    else
    {
      v4 = -2147467261;
      v24 = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No directory result specified");
        v22 = (wchar_t *)&v24;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v7,
          3,
          (unsigned int)": {}",
          (__int64)&v22);
      }
      v6 = 39;
    }
  }
  else
  {
    v4 = -2147024809;
    v24 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No path specified");
      v22 = (wchar_t *)&v24;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v5,
        3,
        (unsigned int)": {}",
        (__int64)&v22);
    }
    v6 = 38;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
    (const char *)v4,
    v21);
  return v4;
}

```

## disassembly

```asm
0x14001ee54  mov     [rsp-38h+arg_10], rbx
0x14001ee59  push    rbp
0x14001ee5a  push    rsi
0x14001ee5b  push    rdi
0x14001ee5c  push    r12
0x14001ee5e  push    r13
0x14001ee60  push    r14
0x14001ee62  push    r15
0x14001ee64  mov     rbp, rsp
0x14001ee67  sub     rsp, 50h
0x14001ee6b  mov     rax, cs:__security_cookie
0x14001ee72  xor     rax, rsp
0x14001ee75  mov     [rbp+var_8], rax
0x14001ee79  xor     r13d, r13d
0x14001ee7c  mov     rdi, rdx
0x14001ee7f  mov     rbx, rcx
0x14001ee82  test    rcx, rcx
0x14001ee85  jnz     short loc_14001EEE1
0x14001ee87  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ee8e  mov     ebx, 80070057h
0x14001ee93  mov     [rbp+var_10], ebx
0x14001ee96  test    rcx, rcx
0x14001ee99  jz      short loc_14001EED7
0x14001ee9b  lea     edi, [r13+3]
0x14001ee9f  xor     edx, edx
0x14001eea1  mov     r8d, edi
0x14001eea4  lea     r9, aNoPathSpecifie; "No path specified"
0x14001eeab  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001eeb0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001eeb7  lea     rax, [rbp+var_10]
0x14001eebb  mov     [rbp+var_20], rax
0x14001eebf  lea     r9, asc_1400353E8; ": {}"
0x14001eec6  lea     rax, [rbp+var_20]
0x14001eeca  mov     r8d, edi
0x14001eecd  mov     qword ptr [rsp+50h+var_30], rax
0x14001eed2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001eed7  mov     edx, 26h ; '&'
0x14001eedc  jmp     loc_14001F0BA
0x14001eee1  test    rdi, rdi
0x14001eee4  jnz     short loc_14001EF41
0x14001eee6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001eeed  mov     ebx, 80004003h
0x14001eef2  mov     [rbp+var_10], ebx
0x14001eef5  test    rcx, rcx
0x14001eef8  jz      short loc_14001EF37
0x14001eefa  mov     edi, 3
0x14001eeff  lea     r9, aNoDirectoryRes; "No directory result specified"
0x14001ef06  mov     r8d, edi
0x14001ef09  xor     edx, edx
0x14001ef0b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001ef10  lea     rcx, [rbp+var_20]
0x14001ef14  mov     r8d, edi
0x14001ef17  mov     qword ptr [rsp+50h+var_30], rcx
0x14001ef1c  lea     rax, [rbp+var_10]
0x14001ef20  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001ef27  lea     r9, asc_1400353E8; ": {}"
0x14001ef2e  mov     [rbp+var_20], rax
0x14001ef32  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001ef37  mov     edx, 27h ; '''; unsigned __int64
0x14001ef3c  jmp     loc_14001F0BA
0x14001ef41  mov     rcx, [rdx]
0x14001ef44  test    rcx, rcx
0x14001ef47  jz      short loc_14001EF55
0x14001ef49  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x14001ef4d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001ef52  mov     [rdi], r13
0x14001ef55  mov     edx, 5Ch ; '\'; Ch
0x14001ef5a  mov     rcx, rbx; Str
0x14001ef5d  call    cs:__imp_wcsrchr
0x14001ef63  test    rax, rax
0x14001ef66  jz      loc_14001F064
0x14001ef6c  cmp     rax, rbx
0x14001ef6f  jz      loc_14001F064
0x14001ef75  sub     rax, rbx
0x14001ef78  mov     [rbp+var_20], r13
0x14001ef7c  sar     rax, 1
0x14001ef7f  lea     rcx, [rbp+var_20]
0x14001ef83  lea     r15, [rax+1]
0x14001ef87  lea     rdx, [r15+2]
0x14001ef8b  call    SczAlloc
0x14001ef90  mov     esi, eax
0x14001ef92  test    eax, eax
0x14001ef94  jns     short loc_14001EFA3
0x14001ef96  mov     r9d, eax
0x14001ef99  mov     edx, 34h ; '4'
0x14001ef9e  jmp     loc_14001F033
0x14001efa3  mov     r14, [rbp+var_20]
0x14001efa7  test    r14, r14
0x14001efaa  jz      loc_14001F050
0x14001efb0  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001efb4  inc     rax
0x14001efb7  cmp     [rbx+rax*2], r13w
0x14001efbc  jnz     short loc_14001EFB4
0x14001efbe  cmp     r15, rax
0x14001efc1  ja      loc_14001F050
0x14001efc7  mov     r9, r15; unsigned __int64
0x14001efca  lea     rdx, [r15+2]; unsigned __int64
0x14001efce  mov     r8, rbx; wchar_t *
0x14001efd1  mov     rcx, r14; wchar_t *
0x14001efd4  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x14001efd9  mov     esi, eax
0x14001efdb  test    eax, eax
0x14001efdd  jns     short loc_14001F050
0x14001efdf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001efe6  mov     [rbp+var_10], eax
0x14001efe9  test    rcx, rcx
0x14001efec  jz      short loc_14001F02B
0x14001efee  mov     edi, 3
0x14001eff3  lea     r9, aFailedToCopySo; "Failed to copy source string to destina"...
0x14001effa  mov     r8d, edi
0x14001effd  xor     edx, edx
0x14001efff  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001f004  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f00b  lea     rax, [rbp+var_10]
0x14001f00f  mov     qword ptr [rbp+var_18], rax
0x14001f013  lea     r9, asc_1400353E8; ": {}"
0x14001f01a  lea     rax, [rbp+var_18]
0x14001f01e  mov     r8d, edi
0x14001f021  mov     qword ptr [rsp+50h+var_30], rax; int
0x14001f026  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001f02b  mov     r9d, esi; char *
0x14001f02e  mov     edx, 3Bh ; ';'; void *
0x14001f033  mov     rcx, [rbp+38h]; this
0x14001f037  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001f03e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f043  lea     rcx, [rbp+var_20]
0x14001f047  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14001f04c  mov     eax, esi
0x14001f04e  jmp     short loc_14001F0CF
0x14001f050  lea     rcx, [rbp+var_20]
0x14001f054  mov     [rbp+var_20], r13
0x14001f058  mov     [rdi], r14
0x14001f05b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14001f060  xor     eax, eax
0x14001f062  jmp     short loc_14001F0CF
0x14001f064  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f06b  mov     ebx, 80070057h
0x14001f070  mov     [rbp+var_10], ebx
0x14001f073  test    rcx, rcx
0x14001f076  jz      short loc_14001F0B5
0x14001f078  mov     edi, 3
0x14001f07d  lea     r9, aInvalidPath; "Invalid path."
0x14001f084  mov     r8d, edi
0x14001f087  xor     edx, edx
0x14001f089  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001f08e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001f095  lea     rax, [rbp+var_10]
0x14001f099  mov     qword ptr [rbp+var_18], rax
0x14001f09d  lea     r9, asc_1400353E8; ": {}"
0x14001f0a4  lea     rax, [rbp+var_18]
0x14001f0a8  mov     r8d, edi
0x14001f0ab  mov     qword ptr [rsp+50h+var_30], rax; int
0x14001f0b0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001f0b5  mov     edx, 2Eh ; '.'; void *
0x14001f0ba  mov     rcx, [rbp+38h]; this
0x14001f0be  lea     r8, aOnecoreBaseCbs_10; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x14001f0c5  mov     r9d, ebx; char *
0x14001f0c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001f0cd  mov     eax, ebx
0x14001f0cf  mov     rcx, [rbp+var_8]
0x14001f0d3  xor     rcx, rsp; StackCookie
0x14001f0d6  call    __security_check_cookie
0x14001f0db  mov     rbx, [rsp+50h+arg_10]
0x14001f0e3  add     rsp, 50h
0x14001f0e7  pop     r15
0x14001f0e9  pop     r14
0x14001f0eb  pop     r13
0x14001f0ed  pop     r12
0x14001f0ef  pop     rdi
0x14001f0f0  pop     rsi
0x14001f0f1  pop     rbp
0x14001f0f2  retn
```
