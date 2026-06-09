# LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)

- ea: `0x14001e898`
- end: `0x14001e90b`
- name: `??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z`
- size: `115`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001e980`

## callees

- `0x1400023e0`
- `0x140016bfc`
- `0x140016fb4`
- `0x14001e898`

## string_xrefs

- `0x14001e8c0`: `Failed NTFS compressing file {}`

## pseudocode

```c
__int64 __fastcall LogAdapter::TraceAtLevelHr<long,wchar_t const *>(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdx
  __int64 result; // rax
  int *v6; // [rsp+30h] [rbp-28h] BYREF
  int v7; // [rsp+38h] [rbp-20h] BYREF

  v7 = a2;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (__int64)LogAdapter::g_Logger,
      a2,
      a3,
      (__int64)"Failed NTFS compressing file {}",
      a4);
    v6 = &v7;
    return LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
             (__int64)LogAdapter::g_Logger,
             v4,
             1,
             (__int64)": {0}",
             (__int64)&v6);
  }
  return result;
}

```

## disassembly

```asm
0x14001e898  sub     rsp, 58h
0x14001e89c  mov     rax, cs:__security_cookie
0x14001e8a3  xor     rax, rsp
0x14001e8a6  mov     [rsp+58h+var_18], rax
0x14001e8ab  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e8b2  mov     [rsp+58h+var_20], edx
0x14001e8b6  test    rcx, rcx
0x14001e8b9  jz      short loc_14001E8F9
0x14001e8bb  mov     [rsp+58h+var_38], r9
0x14001e8c0  lea     r9, aFailedNtfsComp; "Failed NTFS compressing file {}"
0x14001e8c7  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001e8cc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001e8d3  lea     rax, [rsp+58h+var_20]
0x14001e8d8  mov     [rsp+58h+var_28], rax
0x14001e8dd  lea     r9, a0; ": {0}"
0x14001e8e4  lea     rax, [rsp+58h+var_28]
0x14001e8e9  mov     r8d, 1
0x14001e8ef  mov     [rsp+58h+var_38], rax
0x14001e8f4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001e8f9  mov     rcx, [rsp+58h+var_18]
0x14001e8fe  xor     rcx, rsp; StackCookie
0x14001e901  call    __security_check_cookie
0x14001e906  add     rsp, 58h
0x14001e90a  retn
```
