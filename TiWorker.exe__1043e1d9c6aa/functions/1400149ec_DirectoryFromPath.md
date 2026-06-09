# DirectoryFromPath

- ea: `0x1400149ec`
- end: `0x140014c8b`
- name: `DirectoryFromPath`
- size: `671`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x14000f5b0`
- `0x14001344c`
- `0x140016bf8`

## callees

- `0x140002310`
- `0x1400025a4`
- `0x1400053c0`
- `0x140006514`
- `0x140008d38`
- `0x140008ef4`
- `0x140014128`
- `0x1400149ec`
- `0x14001726c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140014af5`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x140014af5`

## string_xrefs

- `0x140014a3c`: `No path specified`
- `0x140014a97`: `No directory result specified`
- `0x140014c15`: `Invalid path.`
- `0x140014b8b`: `Failed to copy source string to destination`

## pseudocode

```c
__int64 __fastcall DirectoryFromPath(wchar_t *a1, const struct std::nothrow_t *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // rdx
  wchar_t *v8; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // r15
  int v11; // eax
  const struct std::nothrow_t *v12; // rdx
  unsigned int v13; // esi
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  wchar_t *v16; // r14
  unsigned __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rdx
  const struct std::nothrow_t *v20; // rdx
  __int64 v22; // rdx
  wchar_t *v23; // [rsp+30h] [rbp-20h] BYREF
  int v24[2]; // [rsp+38h] [rbp-18h] BYREF
  int v25; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  if ( a1 )
  {
    if ( a2 )
    {
      if ( *(_QWORD *)a2 )
      {
        operator delete((void *)(*(_QWORD *)a2 - 8LL), a2);
        *(_QWORD *)a2 = 0;
      }
      v8 = wcsrchr(a1, 0x5Cu);
      if ( v8 && v8 != a1 )
      {
        v23 = 0;
        v9 = v8 - a1;
        v10 = v9 + 1;
        v11 = SczAlloc(&v23, v9 + 3);
        v13 = v11;
        if ( v11 >= 0 )
        {
          v16 = v23;
          if ( !v23 )
            goto LABEL_24;
          v17 = -1;
          do
            ++v17;
          while ( a1[v17] );
          if ( v10 > v17 || (v18 = StringCchCopyNW(v23, v10 + 2, a1, v10), v13 = v18, v18 >= 0) )
          {
LABEL_24:
            v23 = 0;
            *(_QWORD *)a2 = v16;
            Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((__int64 *)&v23, v12);
            return 0;
          }
          v25 = v18;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              (__int64)LogAdapter::g_Logger,
              0,
              3,
              (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to copy source string to destination");
            *(_QWORD *)v24 = &v25;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (__int64)LogAdapter::g_Logger,
              v19,
              3,
              (__int64)": {}",
              (__int64)v24);
          }
          v14 = v13;
          v15 = 59;
        }
        else
        {
          v14 = (unsigned int)v11;
          v15 = 52;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (int)"onecore\\base\\cbs\\util\\cbsfile.cpp",
          (const char *)v14);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close((__int64 *)&v23, v20);
        return v13;
      }
      v4 = -2147024809;
      v25 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Invalid path.");
        *(_QWORD *)v24 = &v25;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v22,
          3,
          (__int64)": {}",
          (__int64)v24);
      }
      v6 = 46;
    }
    else
    {
      v4 = -2147467261;
      v25 = -2147467261;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"No directory result specified");
        v23 = (wchar_t *)&v25;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v7,
          3,
          (__int64)": {}",
          (__int64)&v23);
      }
      v6 = 39;
    }
  }
  else
  {
    v4 = -2147024809;
    v25 = -2147024809;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No path specified");
      v23 = (wchar_t *)&v25;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)&v23);
    }
    v6 = 38;
  }
  wil::details::in1diag3::Return_Hr(retaddr, (void *)v6, (int)"onecore\\base\\cbs\\util\\cbsfile.cpp", (const char *)v4);
  return v4;
}

```

## disassembly

```asm
0x1400149ec  mov     [rsp-38h+arg_10], rbx
0x1400149f1  push    rbp
0x1400149f2  push    rsi
0x1400149f3  push    rdi
0x1400149f4  push    r12
0x1400149f6  push    r13
0x1400149f8  push    r14
0x1400149fa  push    r15
0x1400149fc  mov     rbp, rsp
0x1400149ff  sub     rsp, 50h
0x140014a03  mov     rax, cs:__security_cookie
0x140014a0a  xor     rax, rsp
0x140014a0d  mov     [rbp+var_8], rax
0x140014a11  xor     r13d, r13d
0x140014a14  mov     rdi, rdx
0x140014a17  mov     rbx, rcx
0x140014a1a  test    rcx, rcx
0x140014a1d  jnz     short loc_140014A79
0x140014a1f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014a26  mov     ebx, 80070057h
0x140014a2b  mov     [rbp+var_10], ebx
0x140014a2e  test    rcx, rcx
0x140014a31  jz      short loc_140014A6F
0x140014a33  lea     edi, [r13+3]
0x140014a37  xor     edx, edx
0x140014a39  mov     r8d, edi
0x140014a3c  lea     r9, aNoPathSpecifie; "No path specified"
0x140014a43  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140014a48  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014a4f  lea     rax, [rbp+var_10]
0x140014a53  mov     [rbp+var_20], rax
0x140014a57  lea     r9, asc_140030534; ": {}"
0x140014a5e  lea     rax, [rbp+var_20]
0x140014a62  mov     r8d, edi
0x140014a65  mov     qword ptr [rsp+50h+var_30], rax
0x140014a6a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140014a6f  mov     edx, 26h ; '&'
0x140014a74  jmp     loc_140014C52
0x140014a79  test    rdi, rdi
0x140014a7c  jnz     short loc_140014AD9
0x140014a7e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014a85  mov     ebx, 80004003h
0x140014a8a  mov     [rbp+var_10], ebx
0x140014a8d  test    rcx, rcx
0x140014a90  jz      short loc_140014ACF
0x140014a92  mov     edi, 3
0x140014a97  lea     r9, aNoDirectoryRes; "No directory result specified"
0x140014a9e  mov     r8d, edi
0x140014aa1  xor     edx, edx
0x140014aa3  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140014aa8  lea     rcx, [rbp+var_20]
0x140014aac  mov     r8d, edi
0x140014aaf  mov     qword ptr [rsp+50h+var_30], rcx
0x140014ab4  lea     rax, [rbp+var_10]
0x140014ab8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014abf  lea     r9, asc_140030534; ": {}"
0x140014ac6  mov     [rbp+var_20], rax
0x140014aca  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140014acf  mov     edx, 27h ; '''; struct std::nothrow_t *
0x140014ad4  jmp     loc_140014C52
0x140014ad9  mov     rcx, [rdx]
0x140014adc  test    rcx, rcx
0x140014adf  jz      short loc_140014AED
0x140014ae1  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x140014ae5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140014aea  mov     [rdi], r13
0x140014aed  mov     edx, 5Ch ; '\'; Ch
0x140014af2  mov     rcx, rbx; Str
0x140014af5  call    cs:__imp_wcsrchr
0x140014afb  test    rax, rax
0x140014afe  jz      loc_140014BFC
0x140014b04  cmp     rax, rbx
0x140014b07  jz      loc_140014BFC
0x140014b0d  sub     rax, rbx
0x140014b10  mov     [rbp+var_20], r13
0x140014b14  sar     rax, 1
0x140014b17  lea     rcx, [rbp+var_20]
0x140014b1b  lea     r15, [rax+1]
0x140014b1f  lea     rdx, [r15+2]
0x140014b23  call    SczAlloc
0x140014b28  mov     esi, eax
0x140014b2a  test    eax, eax
0x140014b2c  jns     short loc_140014B3B
0x140014b2e  mov     r9d, eax
0x140014b31  mov     edx, 34h ; '4'
0x140014b36  jmp     loc_140014BCB
0x140014b3b  mov     r14, [rbp+var_20]
0x140014b3f  test    r14, r14
0x140014b42  jz      loc_140014BE8
0x140014b48  or      rax, 0FFFFFFFFFFFFFFFFh
0x140014b4c  inc     rax
0x140014b4f  cmp     [rbx+rax*2], r13w
0x140014b54  jnz     short loc_140014B4C
0x140014b56  cmp     r15, rax
0x140014b59  ja      loc_140014BE8
0x140014b5f  mov     r9, r15; unsigned __int64
0x140014b62  lea     rdx, [r15+2]; unsigned __int64
0x140014b66  mov     r8, rbx; wchar_t *
0x140014b69  mov     rcx, r14; wchar_t *
0x140014b6c  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x140014b71  mov     esi, eax
0x140014b73  test    eax, eax
0x140014b75  jns     short loc_140014BE8
0x140014b77  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014b7e  mov     [rbp+var_10], eax
0x140014b81  test    rcx, rcx
0x140014b84  jz      short loc_140014BC3
0x140014b86  mov     edi, 3
0x140014b8b  lea     r9, aFailedToCopySo; "Failed to copy source string to destina"...
0x140014b92  mov     r8d, edi
0x140014b95  xor     edx, edx
0x140014b97  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140014b9c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014ba3  lea     rax, [rbp+var_10]
0x140014ba7  mov     qword ptr [rbp+var_18], rax
0x140014bab  lea     r9, asc_140030534; ": {}"
0x140014bb2  lea     rax, [rbp+var_18]
0x140014bb6  mov     r8d, edi
0x140014bb9  mov     qword ptr [rsp+50h+var_30], rax; int
0x140014bbe  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140014bc3  mov     r9d, esi; char *
0x140014bc6  mov     edx, 3Bh ; ';'; void *
0x140014bcb  mov     rcx, [rbp+38h]; this
0x140014bcf  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140014bd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014bdb  lea     rcx, [rbp+var_20]
0x140014bdf  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140014be4  mov     eax, esi
0x140014be6  jmp     short loc_140014C67
0x140014be8  lea     rcx, [rbp+var_20]
0x140014bec  mov     [rbp+var_20], r13
0x140014bf0  mov     [rdi], r14
0x140014bf3  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140014bf8  xor     eax, eax
0x140014bfa  jmp     short loc_140014C67
0x140014bfc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014c03  mov     ebx, 80070057h
0x140014c08  mov     [rbp+var_10], ebx
0x140014c0b  test    rcx, rcx
0x140014c0e  jz      short loc_140014C4D
0x140014c10  mov     edi, 3
0x140014c15  lea     r9, aInvalidPath; "Invalid path."
0x140014c1c  mov     r8d, edi
0x140014c1f  xor     edx, edx
0x140014c21  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140014c26  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140014c2d  lea     rax, [rbp+var_10]
0x140014c31  mov     qword ptr [rbp+var_18], rax
0x140014c35  lea     r9, asc_140030534; ": {}"
0x140014c3c  lea     rax, [rbp+var_18]
0x140014c40  mov     r8d, edi
0x140014c43  mov     qword ptr [rsp+50h+var_30], rax; int
0x140014c48  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140014c4d  mov     edx, 2Eh ; '.'; void *
0x140014c52  mov     rcx, [rbp+38h]; this
0x140014c56  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsfile.cpp"
0x140014c5d  mov     r9d, ebx; char *
0x140014c60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140014c65  mov     eax, ebx
0x140014c67  mov     rcx, [rbp+var_8]
0x140014c6b  xor     rcx, rsp; StackCookie
0x140014c6e  call    __security_check_cookie
0x140014c73  mov     rbx, [rsp+50h+arg_10]
0x140014c7b  add     rsp, 50h
0x140014c7f  pop     r15
0x140014c81  pop     r14
0x140014c83  pop     r13
0x140014c85  pop     r12
0x140014c87  pop     rdi
0x140014c88  pop     rsi
0x140014c89  pop     rbp
0x140014c8a  retn
```
