# LogAdapter::TraceAtLevelWin32<ulong,wchar_t *,wchar_t *>(LogAdapter::LogLevel,ulong,char const * const,wchar_t * const &,wchar_t * const &)

- ea: `0x14000e170`
- end: `0x14000e1d4`
- name: `??$TraceAtLevelWin32@KPEA_WPEA_W@LogAdapter@@YAXW4LogLevel@0@KQEBDAEBQEA_W2@Z`
- size: `100`
- prototype: `__int64 __fastcall(int, int, int *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f5b0`

## callees

- `0x14000dac8`
- `0x14000dd94`
- `0x14000e170`

## string_xrefs

- `0x14000e19b`: `Unable to move log: {} to backup log: {}, continuing anyway.`

## pseudocode

```c
__int64 __fastcall LogAdapter::TraceAtLevelWin32<unsigned long,wchar_t *,wchar_t *>(
        int a1,
        int a2,
        int *a3,
        __int64 a4,
        __int64 a5)
{
  int v6; // edx
  int v7; // r9d
  __int64 result; // rax
  int v9; // [rsp+40h] [rbp+8h] BYREF
  int *v10; // [rsp+50h] [rbp+18h] BYREF

  v10 = a3;
  v9 = a1;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      a2,
      (_DWORD)a3,
      (unsigned int)"Unable to move log: {} to backup log: {}, continuing anyway.",
      a4,
      a5);
    v10 = &v9;
    v9 = a2;
    return LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatWin32ErrorWrapper<unsigned long>>(
             (_DWORD)LogAdapter::g_Logger,
             v6,
             0,
             v7,
             (__int64)&v10);
  }
  return result;
}

```

## disassembly

```asm
0x14000e170  mov     [rsp+arg_10], r8
0x14000e175  mov     [rsp+arg_0], ecx
0x14000e179  push    rbx
0x14000e17a  sub     rsp, 30h
0x14000e17e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000e185  mov     ebx, edx
0x14000e187  test    rcx, rcx
0x14000e18a  jz      short loc_14000E1CE
0x14000e18c  mov     rax, [rsp+38h+arg_20]
0x14000e191  mov     [rsp+38h+var_10], rax
0x14000e196  mov     [rsp+38h+var_18], r9
0x14000e19b  lea     r9, aUnableToMoveLo; "Unable to move log: {} to backup log: {"...
0x14000e1a2  call    ??$LogNumObjects@PEA_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEA_W3@Z; LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t * const &,wchar_t * const &)
0x14000e1a7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14000e1ae  lea     rax, [rsp+38h+arg_0]
0x14000e1b3  mov     [rsp+38h+arg_10], rax
0x14000e1b8  xor     r8d, r8d
0x14000e1bb  lea     rax, [rsp+38h+arg_10]
0x14000e1c0  mov     [rsp+38h+arg_0], ebx
0x14000e1c4  mov     [rsp+38h+var_18], rax
0x14000e1c9  call    ??$LogNumObjects@U?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong> const &)
0x14000e1ce  add     rsp, 30h
0x14000e1d2  pop     rbx
0x14000e1d3  retn
```
