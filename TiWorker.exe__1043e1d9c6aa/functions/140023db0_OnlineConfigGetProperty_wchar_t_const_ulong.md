# OnlineConfigGetProperty(wchar_t const *,ulong *)

- ea: `0x140023db0`
- end: `0x140023e68`
- name: `?OnlineConfigGetProperty@@YAJPEB_WPEAK@Z`
- size: `184`
- prototype: `__int64 __fastcall(wchar_t *, unsigned int *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000e824`
- `0x14000f5b0`

## callees

- `0x140002310`
- `0x1400053c0`
- `0x140008d38`
- `0x140008ef4`
- `0x14001121c`
- `0x140023db0`

## string_xrefs

- `0x140023e4a`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide\Configuration`

## pseudocode

```c
__int64 __fastcall OnlineConfigGetProperty(wchar_t *a1, unsigned int *a2, __int64 a3)
{
  __int64 v3; // rdx
  int v5; // [rsp+20h] [rbp-38h]
  int v6[2]; // [rsp+30h] [rbp-28h] BYREF
  int v7; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a2 )
  {
    *a2 = 0;
    return CbsRegQueryDWORDValue(
             (HKEY)a1,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide\\Configuration",
             a3,
             a1,
             a2);
  }
  else
  {
    v7 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No value result specified");
      *(_QWORD *)v6 = &v7;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v3,
        3,
        (__int64)": {}",
        (__int64)v6);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsmaintenanceactions.cpp",
      (const char *)0x80004003LL,
      v5);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x140023db0  sub     rsp, 58h
0x140023db4  mov     rax, cs:__security_cookie
0x140023dbb  xor     rax, rsp
0x140023dbe  mov     [rsp+58h+var_18], rax
0x140023dc3  test    rdx, rdx
0x140023dc6  jnz     short loc_140023E3C
0x140023dc8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023dcf  mov     [rsp+58h+var_20], 80004003h
0x140023dd7  test    rcx, rcx
0x140023dda  jz      short loc_140023E19
0x140023ddc  lea     r9, aNoValueResultS; "No value result specified"
0x140023de3  lea     r8d, [rdx+3]
0x140023de7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140023dec  lea     rcx, [rsp+58h+var_20]
0x140023df1  mov     r8d, 3
0x140023df7  mov     qword ptr [rsp+58h+var_28], rcx
0x140023dfc  lea     r9, asc_140030534; ": {}"
0x140023e03  lea     rcx, [rsp+58h+var_28]
0x140023e08  mov     qword ptr [rsp+58h+var_38], rcx; int
0x140023e0d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023e14  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023e19  mov     rcx, [rsp+58h]; this
0x140023e1e  lea     r8, aOnecoreBaseCbs_2; "onecore\\base\\cbs\\util\\cbsmaintenanc"...
0x140023e25  mov     r9d, 80004003h; char *
0x140023e2b  mov     edx, 72h ; 'r'; void *
0x140023e30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140023e35  mov     eax, 80004003h
0x140023e3a  jmp     short loc_140023E56
0x140023e3c  mov     dword ptr [rdx], 0
0x140023e42  mov     r9, rcx; wchar_t *
0x140023e45  mov     qword ptr [rsp+58h+var_38], rdx; unsigned int *
0x140023e4a  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140023e51  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x140023e56  mov     rcx, [rsp+58h+var_18]
0x140023e5b  xor     rcx, rsp; StackCookie
0x140023e5e  call    __security_check_cookie
0x140023e63  add     rsp, 58h
0x140023e67  retn
```
