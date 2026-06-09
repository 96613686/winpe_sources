# LogAdapter::TraceAtLevelWin32<ulong,wchar_t *,wchar_t *>(LogAdapter::LogLevel,ulong,char const * const,wchar_t * const &,wchar_t * const &)

- ea: `0x1400126b8`
- end: `0x140012723`
- name: `??$TraceAtLevelWin32@KPEA_WPEA_W@LogAdapter@@YAXW4LogLevel@0@KQEBDAEBQEA_W2@Z`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140013288`

## callees

- `0x1400122e0`
- `0x140012400`
- `0x1400126b8`

## string_xrefs

- `0x1400126e3`: `Unable to move log: {} to backup log: {}, continuing anyway.`

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
  __int64 result; // rax
  int v8; // [rsp+40h] [rbp+8h] BYREF
  int *v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = a3;
  v8 = a1;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(
      (_DWORD)LogAdapter::g_Logger,
      a2,
      (_DWORD)a3,
      (unsigned int)"Unable to move log: {} to backup log: {}, continuing anyway.",
      a4,
      a5);
    v9 = &v8;
    v8 = a2;
    return LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatWin32ErrorWrapper<unsigned long>>(
             (_DWORD)LogAdapter::g_Logger,
             v6,
             0,
             (unsigned int)": {0}",
             (__int64)&v9);
  }
  return result;
}

```

## disassembly

```asm
0x1400126b8  mov     [rsp+arg_10], r8
0x1400126bd  mov     [rsp+arg_0], ecx
0x1400126c1  push    rbx
0x1400126c2  sub     rsp, 30h
0x1400126c6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400126cd  mov     ebx, edx
0x1400126cf  test    rcx, rcx
0x1400126d2  jz      short loc_14001271D
0x1400126d4  mov     rax, [rsp+38h+arg_20]
0x1400126d9  mov     [rsp+38h+var_10], rax
0x1400126de  mov     [rsp+38h+var_18], r9
0x1400126e3  lea     r9, aUnableToMoveLo; "Unable to move log: {} to backup log: {"...
0x1400126ea  call    ??$LogNumObjects@PEA_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEA_W3@Z; LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t * const &,wchar_t * const &)
0x1400126ef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400126f6  lea     rax, [rsp+38h+arg_0]
0x1400126fb  mov     [rsp+38h+arg_10], rax
0x140012700  lea     r9, a0; ": {0}"
0x140012707  lea     rax, [rsp+38h+arg_10]
0x14001270c  mov     [rsp+38h+arg_0], ebx
0x140012710  xor     r8d, r8d
0x140012713  mov     [rsp+38h+var_18], rax
0x140012718  call    ??$LogNumObjects@U?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong> const &)
0x14001271d  add     rsp, 30h
0x140012721  pop     rbx
0x140012722  retn
```
