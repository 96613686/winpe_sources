# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003468`
- end: `0x1800036f3`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `651`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000330c`

## callees

- `0x180002c48`
- `0x180003468`
- `0x180003df4`
- `0x1800041f8`
- `0x180004590`
- `0x18000478c`
- `0x180036130`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003521`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003521`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800036ba`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800036ba`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000362a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000362a`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180003468  mov     [rsp-8+arg_18], rbx
0x18000346d  push    rbp
0x18000346e  push    rsi
0x18000346f  push    rdi
0x180003470  push    r12
0x180003472  push    r13
0x180003474  push    r14
0x180003476  push    r15
0x180003478  lea     rbp, [rsp-13C0h]
0x180003480  mov     eax, 14C0h
0x180003485  call    _alloca_probe
0x18000348a  sub     rsp, rax
0x18000348d  mov     r14, r8
0x180003490  mov     esi, edx
0x180003492  mov     rdi, rcx
0x180003495  mov     r15, [rbp+13F0h+arg_28]
0x18000349c  xor     edx, edx; Val
0x18000349e  mov     r8d, 98h; Size
0x1800034a4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800034a9  call    memset_0
0x1800034ae  nop
0x1800034af  xor     r13d, r13d
0x1800034b2  mov     [rbp+13F0h+OutputString], r13w
0x1800034ba  mov     [rbp+13F0h+var_1430], r13b
0x1800034be  mov     rbx, [rbp+13F0h+arg_30]
0x1800034c5  mov     ecx, [rbx]; this
0x1800034c7  mov     [rsp+14F0h+var_14C8], ecx
0x1800034cb  mov     eax, [rbx+4]
0x1800034ce  mov     [rsp+14F0h+var_14C4], eax
0x1800034d2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800034d7  mov     r12d, eax
0x1800034da  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800034e2  mov     ecx, r13d
0x1800034e5  lea     eax, [r13+8]
0x1800034e9  cmp     dword ptr [rbx+8], 1
0x1800034ed  cmovz   ecx, eax
0x1800034f0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800034f4  lea     ecx, [rax-7]
0x1800034f7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800034ff  inc     ecx
0x180003501  mov     [rsp+14F0h+var_14C0], ecx
0x180003505  mov     rcx, [rbp+13F0h+arg_38]
0x18000350c  test    rcx, rcx
0x18000350f  jz      short loc_18000351C
0x180003511  cmp     [rcx], r13w
0x180003515  mov     [rsp+14F0h+var_14B8], rcx
0x18000351a  jnz     short loc_180003521
0x18000351c  mov     [rsp+14F0h+var_14B8], r13
0x180003521  call    cs:__imp_GetCurrentThreadId
0x180003528  nop     dword ptr [rax+rax+00h]
0x18000352d  mov     [rsp+14F0h+var_14B0], eax
0x180003531  mov     [rsp+14F0h+var_1498], r14
0x180003536  mov     [rsp+14F0h+var_1490], esi
0x18000353a  mov     [rsp+14F0h+var_148C], r12d
0x18000353f  mov     [rsp+14F0h+var_14A8], r13
0x180003544  mov     [rsp+14F0h+var_14A0], r13
0x180003549  mov     [rbp+13F0h+var_1448], r15
0x18000354d  mov     [rbp+13F0h+var_1440], rdi
0x180003551  mov     [rsp+14F0h+var_1488], r13
0x180003556  xorps   xmm0, xmm0
0x180003559  xor     eax, eax
0x18000355b  movups  [rbp+13F0h+var_1468], xmm0
0x18000355f  mov     [rbp+13F0h+var_1458], rax
0x180003563  xorps   xmm1, xmm1
0x180003566  movups  [rsp+14F0h+var_1480], xmm1
0x18000356b  mov     [rbp+13F0h+var_1470], rax
0x18000356f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003576  test    rax, rax
0x180003579  jz      short loc_180003586
0x18000357b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003580  mov     [rbp+13F0h+var_1450], rax
0x180003584  jmp     short loc_18000358A
0x180003586  mov     [rbp+13F0h+var_1450], r13
0x18000358a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003591  test    rax, rax
0x180003594  jz      short loc_1800035A0
0x180003596  lea     rcx, [rsp+14F0h+var_14D0]
0x18000359b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035a0  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800035a7  test    rax, rax
0x1800035aa  jz      short loc_1800035C0
0x1800035ac  mov     r8d, 400h
0x1800035b2  lea     rdx, [rbp+13F0h+var_1430]
0x1800035b6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800035bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035c0  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800035c7  test    rax, rax
0x1800035ca  jz      short loc_1800035D6
0x1800035cc  lea     rcx, [rsp+14F0h+var_14D0]
0x1800035d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035d6  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800035dd  test    rax, rax
0x1800035e0  jz      short loc_1800035F3
0x1800035e2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800035e7  jnz     short loc_1800035F3
0x1800035e9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800035ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035f3  cmp     [rsp+14F0h+var_14C8], r13d
0x1800035f8  jl      short loc_18000360C
0x1800035fa  mov     ecx, 8000FFFFh; this
0x1800035ff  mov     [rsp+14F0h+var_14C8], ecx
0x180003603  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003608  mov     [rsp+14F0h+var_14C4], eax
0x18000360c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180003613  jnz     short loc_18000363A
0x180003615  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000361c  test    rax, rax
0x18000361f  jz      short loc_18000362A
0x180003621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003626  test    al, al
0x180003628  jmp     short loc_180003638
0x18000362a  call    cs:__imp_IsDebuggerPresent
0x180003631  nop     dword ptr [rax+rax+00h]
0x180003636  test    eax, eax
0x180003638  jz      short loc_180003641
0x18000363a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000363f  jz      short loc_180003667
0x180003641  mov     rax, cs:g_pfnResultLoggingCallback
0x180003648  test    rax, rax
0x18000364b  jz      short loc_1800036C6
0x18000364d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003654  jnz     short loc_1800036C6
0x180003656  xor     r8d, r8d
0x180003659  xor     edx, edx
0x18000365b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003665  jmp     short loc_1800036C6
0x180003667  mov     ebx, 800h
0x18000366c  mov     rax, cs:g_pfnResultLoggingCallback
0x180003673  test    rax, rax
0x180003676  jz      short loc_180003695
0x180003678  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000367f  jnz     short loc_180003695
0x180003681  mov     r8d, ebx
0x180003684  lea     rdx, [rbp+13F0h+OutputString]
0x18000368b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003695  cmp     [rbp+13F0h+OutputString], r13w
0x18000369d  jnz     short loc_1800036B3
0x18000369f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800036a4  mov     rdx, rbx; unsigned __int16 *
0x1800036a7  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800036ae  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800036b3  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800036ba  call    cs:__imp_OutputDebugStringW
0x1800036c1  nop     dword ptr [rax+rax+00h]
0x1800036c6  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800036cb  jnz     short loc_1800036D6
0x1800036cd  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800036d4  jz      short loc_1800036E8
0x1800036d6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800036dd  test    rax, rax
0x1800036e0  jz      short loc_1800036E8
0x1800036e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036e7  nop
0x1800036e8  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800036ed  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
