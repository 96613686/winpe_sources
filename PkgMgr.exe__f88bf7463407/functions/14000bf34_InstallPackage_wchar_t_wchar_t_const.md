# InstallPackage(wchar_t * *,wchar_t const *)

- ea: `0x14000bf34`
- end: `0x14000c077`
- name: `?InstallPackage@@YAJPEAPEA_WPEB_W@Z`
- size: `323`
- prototype: `__int64 __fastcall(wchar_t **, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000aca8`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x14000726c`
- `0x14000bf34`
- `0x140011100`
- `0x1400113d4`

## string_xrefs

- `0x14000bf6b`: ` /add-package /packagepath:"%s" /ignorecheck`
- `0x14000bf90`: `Failed to allocate memory for command line.`
- `0x14000bff5`: `Failed to allocate memory for command line.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall InstallPackage(wchar_t **a1, const wchar_t *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v5; // edx
  __int64 v6; // rdx
  int v7; // eax
  int v8; // edx
  int v10; // [rsp+20h] [rbp-40h]
  __int64 v11; // [rsp+30h] [rbp-30h] BYREF
  int v12[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v13; // [rsp+40h] [rbp-20h]
  int v14; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  v13 = -2;
  v11 = 0;
  v3 = SczAllocFormatted(&v11, L" /add-package /packagepath:\"%s\" /ignorecheck", a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v7 = SczAllocConcatSz(a1, v11);
    v4 = v7;
    if ( v7 >= 0 )
    {
      v4 = 0;
      goto LABEL_11;
    }
    v14 = v7;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
      *(_QWORD *)v12 = &v14;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v8,
        3,
        (unsigned int)": {}",
        (__int64)v12);
    }
    v6 = 214;
  }
  else
  {
    v14 = v3;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate memory for command line.");
      *(_QWORD *)v12 = &v14;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v5,
        3,
        (unsigned int)": {}",
        (__int64)v12);
    }
    v6 = 212;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\main.cpp",
    (const char *)v4,
    v10);
LABEL_11:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v11);
  return v4;
}

```

## disassembly

```asm
0x14000bf34  mov     rax, rsp
0x14000bf37  push    rbp
0x14000bf38  mov     rbp, rsp
0x14000bf3b  sub     rsp, 60h
0x14000bf3f  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x14000bf47  mov     [rax+18h], rbx
0x14000bf4b  mov     [rax+20h], rdi
0x14000bf4f  mov     rax, cs:__security_cookie
0x14000bf56  xor     rax, rsp
0x14000bf59  mov     [rbp+var_10], rax
0x14000bf5d  mov     rdi, rcx
0x14000bf60  mov     [rbp+var_30], 0
0x14000bf68  mov     r8, rdx
0x14000bf6b  lea     rdx, aAddPackagePack; " /add-package /packagepath:\"%s\" /igno"...
0x14000bf72  lea     rcx, [rbp+var_30]
0x14000bf76  call    SczAllocFormatted
0x14000bf7b  mov     ebx, eax
0x14000bf7d  test    eax, eax
0x14000bf7f  jns     short loc_14000BFD4
0x14000bf81  mov     [rbp+var_18], eax
0x14000bf84  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000bf8b  test    rcx, rcx
0x14000bf8e  jz      short loc_14000BFCD
0x14000bf90  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000bf97  mov     edi, 3
0x14000bf9c  mov     r8d, edi
0x14000bf9f  xor     edx, edx
0x14000bfa1  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000bfa6  lea     rax, [rbp+var_18]
0x14000bfaa  mov     qword ptr [rbp+var_28], rax
0x14000bfae  lea     rax, [rbp+var_28]
0x14000bfb2  mov     qword ptr [rsp+60h+var_40], rax
0x14000bfb7  lea     r9, asc_14002D4FC; ": {}"
0x14000bfbe  mov     r8d, edi
0x14000bfc1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000bfc8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000bfcd  mov     edx, 0D4h
0x14000bfd2  jmp     short loc_14000C037
0x14000bfd4  mov     rdx, [rbp+var_30]
0x14000bfd8  mov     rcx, rdi
0x14000bfdb  call    SczAllocConcatSz
0x14000bfe0  mov     ebx, eax
0x14000bfe2  test    eax, eax
0x14000bfe4  jns     short loc_14000C04C
0x14000bfe6  mov     [rbp+var_18], eax
0x14000bfe9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000bff0  test    rcx, rcx
0x14000bff3  jz      short loc_14000C032
0x14000bff5  lea     r9, aFailedToAlloca_2; "Failed to allocate memory for command l"...
0x14000bffc  mov     edi, 3
0x14000c001  mov     r8d, edi
0x14000c004  xor     edx, edx
0x14000c006  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14000c00b  lea     rax, [rbp+var_18]
0x14000c00f  mov     qword ptr [rbp+var_28], rax
0x14000c013  lea     rax, [rbp+var_28]
0x14000c017  mov     qword ptr [rsp+60h+var_40], rax; int
0x14000c01c  lea     r9, asc_14002D4FC; ": {}"
0x14000c023  mov     r8d, edi
0x14000c026  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000c02d  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14000c032  mov     edx, 0D6h; void *
0x14000c037  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\pkgmgrshim\\main.cp"...
0x14000c03e  mov     r9d, ebx; char *
0x14000c041  mov     rcx, [rbp+8]; this
0x14000c045  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c04a  jmp     short loc_14000C04E
0x14000c04c  xor     ebx, ebx
0x14000c04e  lea     rcx, [rbp+var_30]
0x14000c052  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x14000c057  mov     eax, ebx
0x14000c059  mov     rcx, [rbp+var_10]
0x14000c05d  xor     rcx, rsp; StackCookie
0x14000c060  call    __security_check_cookie
0x14000c065  lea     r11, [rsp+60h+var_s0]
0x14000c06a  mov     rbx, [r11+20h]
0x14000c06e  mov     rdi, [r11+28h]
0x14000c072  mov     rsp, r11
0x14000c075  pop     rbp
0x14000c076  retn
```
