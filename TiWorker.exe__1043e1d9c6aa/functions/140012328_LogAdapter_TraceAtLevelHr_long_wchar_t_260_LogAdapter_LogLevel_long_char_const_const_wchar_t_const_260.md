# LogAdapter::TraceAtLevelHr<long,wchar_t [260]>(LogAdapter::LogLevel,long,char const * const,wchar_t const (&)[260])

- ea: `0x140012328`
- end: `0x14001239b`
- name: `??$TraceAtLevelHr@J$$BY0BAE@_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEAY0BAE@$$CB_W@Z`
- size: `115`
- prototype: `__int64 __fastcall(__int64, int, int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140012c58`

## callees

- `0x140002310`
- `0x140008ef4`
- `0x14001219c`
- `0x140012328`

## string_xrefs

- `0x140012350`: `Unable to remove file {}.`

## pseudocode

```c
__int64 __fastcall LogAdapter::TraceAtLevelHr<long,wchar_t [260]>(__int64 a1, int a2, int a3, __int64 a4)
{
  __int64 v4; // rdx
  __int64 result; // rax
  int *v6; // [rsp+30h] [rbp-28h] BYREF
  int v7; // [rsp+38h] [rbp-20h] BYREF

  v7 = a2;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t [260]>(
      (_DWORD)LogAdapter::g_Logger,
      a2,
      a3,
      (unsigned int)"Unable to remove file {}.",
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
0x140012328  sub     rsp, 58h
0x14001232c  mov     rax, cs:__security_cookie
0x140012333  xor     rax, rsp
0x140012336  mov     [rsp+58h+var_18], rax
0x14001233b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012342  mov     [rsp+58h+var_20], edx
0x140012346  test    rcx, rcx
0x140012349  jz      short loc_140012389
0x14001234b  mov     [rsp+58h+var_38], r9
0x140012350  lea     r9, aUnableToRemove_0; "Unable to remove file {}."
0x140012357  call    ??$LogNumObjects@$$BY0BAE@_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEAY0BAE@$$CB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t [260]>(bool,LogAdapter::LogLevel,char const * const,wchar_t const (&)[260])
0x14001235c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140012363  lea     rax, [rsp+58h+var_20]
0x140012368  mov     [rsp+58h+var_28], rax
0x14001236d  lea     r9, a0; ": {0}"
0x140012374  lea     rax, [rsp+58h+var_28]
0x140012379  mov     r8d, 1
0x14001237f  mov     [rsp+58h+var_38], rax
0x140012384  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140012389  mov     rcx, [rsp+58h+var_18]
0x14001238e  xor     rcx, rsp; StackCookie
0x140012391  call    __security_check_cookie
0x140012396  add     rsp, 58h
0x14001239a  retn
```
