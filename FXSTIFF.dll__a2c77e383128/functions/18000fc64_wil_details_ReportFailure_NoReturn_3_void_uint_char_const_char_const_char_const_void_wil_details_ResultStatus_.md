# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000fc64`
- end: `0x18000fec6`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000fa08`

## callees

- `0x18000fc64`
- `0x180012174`
- `0x180012910`
- `0x1800137f0`
- `0x1800159a0`
- `0x180017bce`
- `0x180017c90`
- `0x180019010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18000fe09`
- `KERNEL32!IsDebuggerPresent` at `0x18000fe09`
- `KERNEL32!OutputDebugStringW` at `0x18000fe93`
- `KERNEL32!OutputDebugStringW` at `0x18000fe93`
- `KERNEL32!GetCurrentThreadId` at `0x18000fd06`
- `KERNEL32!GetCurrentThreadId` at `0x18000fd06`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x18000fc64  mov     [rsp-8+arg_18], rbx
0x18000fc69  push    rbp
0x18000fc6a  push    rsi
0x18000fc6b  push    rdi
0x18000fc6c  push    r12
0x18000fc6e  push    r13
0x18000fc70  push    r14
0x18000fc72  push    r15
0x18000fc74  lea     rbp, [rsp-13C0h]
0x18000fc7c  mov     eax, 14C0h
0x18000fc81  call    _alloca_probe
0x18000fc86  sub     rsp, rax
0x18000fc89  mov     r15, r8
0x18000fc8c  mov     r14d, edx
0x18000fc8f  mov     r12, rcx
0x18000fc92  mov     rsi, [rbp+13F0h+arg_28]
0x18000fc99  xor     edx, edx; Val
0x18000fc9b  mov     r8d, 98h; Size
0x18000fca1  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000fca6  call    memset_0
0x18000fcab  nop
0x18000fcac  xor     r13d, r13d
0x18000fcaf  mov     [rbp+13F0h+OutputString], r13w
0x18000fcb7  mov     [rbp+13F0h+var_1430], r13b
0x18000fcbb  mov     rbx, [rbp+13F0h+arg_30]
0x18000fcc2  mov     ecx, [rbx]; this
0x18000fcc4  mov     [rsp+14F0h+var_14C8], ecx
0x18000fcc8  mov     eax, [rbx+4]
0x18000fccb  mov     [rsp+14F0h+var_14C4], eax
0x18000fccf  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000fcd4  mov     edi, eax
0x18000fcd6  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000fcde  mov     ecx, r13d
0x18000fce1  lea     eax, [r13+8]
0x18000fce5  cmp     dword ptr [rbx+8], 1
0x18000fce9  cmovz   ecx, eax
0x18000fcec  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000fcf0  lea     ecx, [rax-7]
0x18000fcf3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000fcfb  inc     ecx
0x18000fcfd  mov     [rsp+14F0h+var_14C0], ecx
0x18000fd01  mov     [rsp+14F0h+var_14B8], r13
0x18000fd06  call    cs:__imp_GetCurrentThreadId
0x18000fd0c  mov     [rsp+14F0h+var_14B0], eax
0x18000fd10  mov     [rsp+14F0h+var_1498], r15
0x18000fd15  mov     [rsp+14F0h+var_1490], r14d
0x18000fd1a  mov     [rsp+14F0h+var_148C], edi
0x18000fd1e  mov     [rsp+14F0h+var_14A8], r13
0x18000fd23  mov     [rsp+14F0h+var_14A0], r13
0x18000fd28  mov     [rbp+13F0h+var_1448], rsi
0x18000fd2c  mov     [rbp+13F0h+var_1440], r12
0x18000fd30  mov     [rsp+14F0h+var_1488], r13
0x18000fd35  xorps   xmm0, xmm0
0x18000fd38  xor     eax, eax
0x18000fd3a  movups  [rbp+13F0h+var_1468], xmm0
0x18000fd3e  mov     [rbp+13F0h+var_1458], rax
0x18000fd42  xorps   xmm1, xmm1
0x18000fd45  movups  [rsp+14F0h+var_1480], xmm1
0x18000fd4a  mov     [rbp+13F0h+var_1470], rax
0x18000fd4e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000fd55  test    rax, rax
0x18000fd58  jz      short loc_18000FD65
0x18000fd5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd5f  mov     [rbp+13F0h+var_1450], rax
0x18000fd63  jmp     short loc_18000FD69
0x18000fd65  mov     [rbp+13F0h+var_1450], r13
0x18000fd69  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000fd70  test    rax, rax
0x18000fd73  jz      short loc_18000FD7F
0x18000fd75  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fd7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd7f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000fd86  test    rax, rax
0x18000fd89  jz      short loc_18000FD9F
0x18000fd8b  mov     r8d, 400h
0x18000fd91  lea     rdx, [rbp+13F0h+var_1430]
0x18000fd95  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fd9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd9f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000fda6  test    rax, rax
0x18000fda9  jz      short loc_18000FDB5
0x18000fdab  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fdb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdb5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000fdbc  test    rax, rax
0x18000fdbf  jz      short loc_18000FDD2
0x18000fdc1  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000fdc6  jnz     short loc_18000FDD2
0x18000fdc8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fdcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdd2  cmp     [rsp+14F0h+var_14C8], r13d
0x18000fdd7  jl      short loc_18000FDEB
0x18000fdd9  mov     ecx, 8000FFFFh; this
0x18000fdde  mov     [rsp+14F0h+var_14C8], ecx
0x18000fde2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000fde7  mov     [rsp+14F0h+var_14C4], eax
0x18000fdeb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000fdf2  jnz     short loc_18000FE13
0x18000fdf4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000fdfb  test    rax, rax
0x18000fdfe  jz      short loc_18000FE09
0x18000fe00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe05  test    al, al
0x18000fe07  jmp     short loc_18000FE11
0x18000fe09  call    cs:__imp_IsDebuggerPresent
0x18000fe0f  test    eax, eax
0x18000fe11  jz      short loc_18000FE1A
0x18000fe13  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000fe18  jz      short loc_18000FE40
0x18000fe1a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000fe21  test    rax, rax
0x18000fe24  jz      short loc_18000FE99
0x18000fe26  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000fe2d  jnz     short loc_18000FE99
0x18000fe2f  xor     r8d, r8d
0x18000fe32  xor     edx, edx
0x18000fe34  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fe39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe3e  jmp     short loc_18000FE99
0x18000fe40  mov     ebx, 800h
0x18000fe45  mov     rax, cs:g_pfnResultLoggingCallback
0x18000fe4c  test    rax, rax
0x18000fe4f  jz      short loc_18000FE6E
0x18000fe51  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000fe58  jnz     short loc_18000FE6E
0x18000fe5a  mov     r8d, ebx
0x18000fe5d  lea     rdx, [rbp+13F0h+OutputString]
0x18000fe64  lea     rcx, [rsp+14F0h+var_14D0]
0x18000fe69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe6e  cmp     [rbp+13F0h+OutputString], r13w
0x18000fe76  jnz     short loc_18000FE8C
0x18000fe78  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000fe7d  mov     rdx, rbx; unsigned __int16 *
0x18000fe80  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000fe87  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000fe8c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000fe93  call    cs:__imp_OutputDebugStringW
0x18000fe99  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000fe9e  jnz     short loc_18000FEA9
0x18000fea0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000fea7  jz      short loc_18000FEBB
0x18000fea9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000feb0  test    rax, rax
0x18000feb3  jz      short loc_18000FEBB
0x18000feb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000feba  nop
0x18000febb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000fec0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
