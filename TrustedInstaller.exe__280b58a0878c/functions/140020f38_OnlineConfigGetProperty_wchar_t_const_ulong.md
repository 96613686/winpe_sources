# OnlineConfigGetProperty(wchar_t const *,ulong *)

- ea: `0x140020f38`
- end: `0x140020ff6`
- name: `?OnlineConfigGetProperty@@YAJPEB_WPEAK@Z`
- size: `190`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400178b8`
- `0x140018630`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x14001a16c`
- `0x140020f38`

## string_xrefs

- `0x140020fd8`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide\Configuration`

## pseudocode

```c
__int64 __fastcall OnlineConfigGetProperty(wchar_t *a1, unsigned int *a2)
{
  int v2; // edx
  int v4; // [rsp+20h] [rbp-38h]
  int v5[2]; // [rsp+30h] [rbp-28h] BYREF
  int v6; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a2 )
  {
    *a2 = 0;
    return CbsRegQueryDWORDValue(
             (HKEY)a1,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide\\Configuration",
             1,
             a1,
             a2);
  }
  else
  {
    v6 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No value result specified");
      *(_QWORD *)v5 = &v6;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v2,
        3,
        (unsigned int)": {}",
        (__int64)v5);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsmaintenanceactions.cpp",
      (const char *)0x80004003LL,
      v4);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x140020f38  sub     rsp, 58h
0x140020f3c  mov     rax, cs:__security_cookie
0x140020f43  xor     rax, rsp
0x140020f46  mov     [rsp+58h+var_18], rax
0x140020f4b  test    rdx, rdx
0x140020f4e  jnz     short loc_140020FC4
0x140020f50  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020f57  mov     [rsp+58h+var_20], 80004003h
0x140020f5f  test    rcx, rcx
0x140020f62  jz      short loc_140020FA1
0x140020f64  lea     r9, aNoValueResultS; "No value result specified"
0x140020f6b  lea     r8d, [rdx+3]
0x140020f6f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140020f74  lea     rcx, [rsp+58h+var_20]
0x140020f79  mov     r8d, 3
0x140020f7f  mov     qword ptr [rsp+58h+var_28], rcx
0x140020f84  lea     r9, asc_1400353E8; ": {}"
0x140020f8b  lea     rcx, [rsp+58h+var_28]
0x140020f90  mov     qword ptr [rsp+58h+var_38], rcx; int
0x140020f95  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140020f9c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140020fa1  mov     rcx, [rsp+58h]; this
0x140020fa6  lea     r8, aOnecoreBaseCbs_6; "onecore\\base\\cbs\\util\\cbsmaintenanc"...
0x140020fad  mov     r9d, 80004003h; char *
0x140020fb3  mov     edx, 72h ; 'r'; void *
0x140020fb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140020fbd  mov     eax, 80004003h
0x140020fc2  jmp     short loc_140020FE4
0x140020fc4  mov     dword ptr [rdx], 0
0x140020fca  mov     r9, rcx; wchar_t *
0x140020fcd  mov     qword ptr [rsp+58h+var_38], rdx; unsigned int *
0x140020fd2  mov     r8d, 1; unsigned int
0x140020fd8  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140020fdf  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x140020fe4  mov     rcx, [rsp+58h+var_18]
0x140020fe9  xor     rcx, rsp; StackCookie
0x140020fec  call    __security_check_cookie
0x140020ff1  add     rsp, 58h
0x140020ff5  retn
```
