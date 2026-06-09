# LogAdapter::TraceAtLevelWin32<ulong,wchar_t *,wchar_t *>(LogAdapter::LogLevel,ulong,char const * const,wchar_t * const &,wchar_t * const &)

- ea: `0x140017550`
- end: `0x1400175b4`
- name: `??$TraceAtLevelWin32@KPEA_WPEA_W@LogAdapter@@YAXW4LogLevel@0@KQEBDAEBQEA_W2@Z`
- size: `100`
- prototype: `__int64 __fastcall(int, int, int *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140018630`

## callees

- `0x140016ce8`
- `0x140017144`
- `0x140017550`

## string_xrefs

- `0x14001757b`: `Unable to move log: {} to backup log: {}, continuing anyway.`

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
0x140017550  mov     [rsp+arg_10], r8
0x140017555  mov     [rsp+arg_0], ecx
0x140017559  push    rbx
0x14001755a  sub     rsp, 30h
0x14001755e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140017565  mov     ebx, edx
0x140017567  test    rcx, rcx
0x14001756a  jz      short loc_1400175AE
0x14001756c  mov     rax, [rsp+38h+arg_20]
0x140017571  mov     [rsp+38h+var_10], rax
0x140017576  mov     [rsp+38h+var_18], r9
0x14001757b  lea     r9, aUnableToMoveLo; "Unable to move log: {} to backup log: {"...
0x140017582  call    ??$LogNumObjects@PEA_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEA_W3@Z; LogAdapter::Logger::LogNumObjects<wchar_t *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t * const &,wchar_t * const &)
0x140017587  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001758e  lea     rax, [rsp+38h+arg_0]
0x140017593  mov     [rsp+38h+arg_10], rax
0x140017598  xor     r8d, r8d
0x14001759b  lea     rax, [rsp+38h+arg_10]
0x1400175a0  mov     [rsp+38h+arg_0], ebx
0x1400175a4  mov     [rsp+38h+var_18], rax
0x1400175a9  call    ??$LogNumObjects@U?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatWin32ErrorWrapper@K@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatWin32ErrorWrapper<ulong> const &)
0x1400175ae  add     rsp, 30h
0x1400175b2  pop     rbx
0x1400175b3  retn
```
