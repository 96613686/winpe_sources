# OnlineConfigGetProperty(wchar_t const *,ulong *)

- ea: `0x1400237c0`
- end: `0x140023878`
- name: `?OnlineConfigGetProperty@@YAJPEB_WPEAK@Z`
- size: `184`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140012b88`
- `0x140013288`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x140017b80`
- `0x1400237c0`

## string_xrefs

- `0x14002385a`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide\Configuration`

## pseudocode

```c
__int64 __fastcall OnlineConfigGetProperty(wchar_t *a1, unsigned int *a2, __int64 a3)
{
  int v3; // edx
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
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "No value result specified");
      *(_QWORD *)v6 = &v7;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v3,
        3,
        (unsigned int)": {}",
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
0x1400237c0  sub     rsp, 58h
0x1400237c4  mov     rax, cs:__security_cookie
0x1400237cb  xor     rax, rsp
0x1400237ce  mov     [rsp+58h+var_18], rax
0x1400237d3  test    rdx, rdx
0x1400237d6  jnz     short loc_14002384C
0x1400237d8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400237df  mov     [rsp+58h+var_20], 80004003h
0x1400237e7  test    rcx, rcx
0x1400237ea  jz      short loc_140023829
0x1400237ec  lea     r9, aNoValueResultS; "No value result specified"
0x1400237f3  lea     r8d, [rdx+3]
0x1400237f7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400237fc  lea     rcx, [rsp+58h+var_20]
0x140023801  mov     r8d, 3
0x140023807  mov     qword ptr [rsp+58h+var_28], rcx
0x14002380c  lea     r9, asc_14002D4FC; ": {}"
0x140023813  lea     rcx, [rsp+58h+var_28]
0x140023818  mov     qword ptr [rsp+58h+var_38], rcx; int
0x14002381d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023824  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140023829  mov     rcx, [rsp+58h]; this
0x14002382e  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsmaintenanc"...
0x140023835  mov     r9d, 80004003h; char *
0x14002383b  mov     edx, 72h ; 'r'; void *
0x140023840  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140023845  mov     eax, 80004003h
0x14002384a  jmp     short loc_140023866
0x14002384c  mov     dword ptr [rdx], 0
0x140023852  mov     r9, rcx; wchar_t *
0x140023855  mov     qword ptr [rsp+58h+var_38], rdx; unsigned int *
0x14002385a  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140023861  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x140023866  mov     rcx, [rsp+58h+var_18]
0x14002386b  xor     rcx, rsp; StackCookie
0x14002386e  call    __security_check_cookie
0x140023873  add     rsp, 58h
0x140023877  retn
```
