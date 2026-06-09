# LogAdapter::TraceAtLevelWin32<ulong,>(LogAdapter::LogLevel,ulong,char const * const)

- ea: `0x14001c6e8`
- end: `0x14001c746`
- name: `??$TraceAtLevelWin32@K$$V@LogAdapter@@YAXW4LogLevel@0@KQEBD@Z`
- size: `94`
- prototype: `__int64 __fastcall(int, int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14002027c`

## callees

- `0x140016a40`
- `0x140017144`
- `0x14001c6e8`

## string_xrefs

- `0x14001c706`: `Failed restart attempt.`

## pseudocode

```c
__int64 __fastcall LogAdapter::TraceAtLevelWin32<unsigned long,>(int a1, int a2, int *a3)
{
  int v4; // edx
  int v5; // r9d
  __int64 result; // rax
  int v7; // [rsp+40h] [rbp+8h] BYREF
  int *v8; // [rsp+50h] [rbp+18h] BYREF

  v8 = a3;
  v7 = a1;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed restart attempt.");
    v8 = &v7;
    v7 = a2;
    return LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatWin32ErrorWrapper<unsigned long>>(
             (_DWORD)LogAdapter::g_Logger,
             v4,
             3,
             v5,
             (__int64)&v8);
  }
  return result;
}

```

## disassembly

```asm
0x14001c6e8  mov     [rsp+arg_10], r8
0x14001c6ed  mov     [rsp+arg_0], ecx
0x14001c6f1  push    rbx
0x14001c6f2  sub     rsp, 30h
0x14001c6f6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001c6fd  mov     ebx, edx
0x14001c6ff  test    rcx, rcx
0x14001c702  jz      short loc_14001C740
0x14001c704  xor     edx, edx
0x14001c706  lea     r9, aFailedRestartA; "Failed restart attempt."
0x14001c70d  lea     r8d, [rdx+3]
0x14001c711  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x14001c716  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001c71d  lea     rax, [rsp+38h+arg_0]
0x14001c722  mov     [rsp+38h+arg_10], rax
0x14001c727  mov     r8d, 3
0x14001c72d  lea     rax, [rsp+38h+arg_10]
0x14001c732  mov     [rsp+38h+arg_0], ebx
0x14001c736  mov     [rsp+38h+var_18], rax
0x14001c73b  call    ??$LogNumObjects@U?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong> const &)
0x14001c740  add     rsp, 30h
0x14001c744  pop     rbx
0x14001c745  retn
```
