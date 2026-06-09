# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800032e0`
- end: `0x180003542`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003084`

## callees

- `0x1800032e0`
- `0x180004874`
- `0x180005010`
- `0x180005740`
- `0x180006490`
- `0x18000b612`
- `0x18000b700`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003382`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003382`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003485`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003485`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000350f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000350f`

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
0x1800032e0  mov     [rsp-8+arg_18], rbx
0x1800032e5  push    rbp
0x1800032e6  push    rsi
0x1800032e7  push    rdi
0x1800032e8  push    r12
0x1800032ea  push    r13
0x1800032ec  push    r14
0x1800032ee  push    r15
0x1800032f0  lea     rbp, [rsp-13C0h]
0x1800032f8  mov     eax, 14C0h
0x1800032fd  call    _alloca_probe
0x180003302  sub     rsp, rax
0x180003305  mov     r15, r8
0x180003308  mov     r14d, edx
0x18000330b  mov     r12, rcx
0x18000330e  mov     rsi, [rbp+13F0h+arg_28]
0x180003315  xor     edx, edx; Val
0x180003317  mov     r8d, 98h; Size
0x18000331d  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003322  call    memset_0
0x180003327  nop
0x180003328  xor     r13d, r13d
0x18000332b  mov     [rbp+13F0h+OutputString], r13w
0x180003333  mov     [rbp+13F0h+var_1430], r13b
0x180003337  mov     rbx, [rbp+13F0h+arg_30]
0x18000333e  mov     ecx, [rbx]; this
0x180003340  mov     [rsp+14F0h+var_14C8], ecx
0x180003344  mov     eax, [rbx+4]
0x180003347  mov     [rsp+14F0h+var_14C4], eax
0x18000334b  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003350  mov     edi, eax
0x180003352  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000335a  mov     ecx, r13d
0x18000335d  lea     eax, [r13+8]
0x180003361  cmp     dword ptr [rbx+8], 1
0x180003365  cmovz   ecx, eax
0x180003368  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000336c  lea     ecx, [rax-7]
0x18000336f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003377  inc     ecx
0x180003379  mov     [rsp+14F0h+var_14C0], ecx
0x18000337d  mov     [rsp+14F0h+var_14B8], r13
0x180003382  call    cs:__imp_GetCurrentThreadId
0x180003388  mov     [rsp+14F0h+var_14B0], eax
0x18000338c  mov     [rsp+14F0h+var_1498], r15
0x180003391  mov     [rsp+14F0h+var_1490], r14d
0x180003396  mov     [rsp+14F0h+var_148C], edi
0x18000339a  mov     [rsp+14F0h+var_14A8], r13
0x18000339f  mov     [rsp+14F0h+var_14A0], r13
0x1800033a4  mov     [rbp+13F0h+var_1448], rsi
0x1800033a8  mov     [rbp+13F0h+var_1440], r12
0x1800033ac  mov     [rsp+14F0h+var_1488], r13
0x1800033b1  xorps   xmm0, xmm0
0x1800033b4  xor     eax, eax
0x1800033b6  movups  [rbp+13F0h+var_1468], xmm0
0x1800033ba  mov     [rbp+13F0h+var_1458], rax
0x1800033be  xorps   xmm1, xmm1
0x1800033c1  movups  [rsp+14F0h+var_1480], xmm1
0x1800033c6  mov     [rbp+13F0h+var_1470], rax
0x1800033ca  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800033d1  test    rax, rax
0x1800033d4  jz      short loc_1800033E1
0x1800033d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033db  mov     [rbp+13F0h+var_1450], rax
0x1800033df  jmp     short loc_1800033E5
0x1800033e1  mov     [rbp+13F0h+var_1450], r13
0x1800033e5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800033ec  test    rax, rax
0x1800033ef  jz      short loc_1800033FB
0x1800033f1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033fb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003402  test    rax, rax
0x180003405  jz      short loc_18000341B
0x180003407  mov     r8d, 400h
0x18000340d  lea     rdx, [rbp+13F0h+var_1430]
0x180003411  lea     rcx, [rsp+14F0h+var_14D0]
0x180003416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000341b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003422  test    rax, rax
0x180003425  jz      short loc_180003431
0x180003427  lea     rcx, [rsp+14F0h+var_14D0]
0x18000342c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003431  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003438  test    rax, rax
0x18000343b  jz      short loc_18000344E
0x18000343d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003442  jnz     short loc_18000344E
0x180003444  lea     rcx, [rsp+14F0h+var_14D0]
0x180003449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000344e  cmp     [rsp+14F0h+var_14C8], r13d
0x180003453  jl      short loc_180003467
0x180003455  mov     ecx, 8000FFFFh; this
0x18000345a  mov     [rsp+14F0h+var_14C8], ecx
0x18000345e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003463  mov     [rsp+14F0h+var_14C4], eax
0x180003467  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000346e  jnz     short loc_18000348F
0x180003470  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003477  test    rax, rax
0x18000347a  jz      short loc_180003485
0x18000347c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003481  test    al, al
0x180003483  jmp     short loc_18000348D
0x180003485  call    cs:__imp_IsDebuggerPresent
0x18000348b  test    eax, eax
0x18000348d  jz      short loc_180003496
0x18000348f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003494  jz      short loc_1800034BC
0x180003496  mov     rax, cs:g_pfnResultLoggingCallback
0x18000349d  test    rax, rax
0x1800034a0  jz      short loc_180003515
0x1800034a2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800034a9  jnz     short loc_180003515
0x1800034ab  xor     r8d, r8d
0x1800034ae  xor     edx, edx
0x1800034b0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800034b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ba  jmp     short loc_180003515
0x1800034bc  mov     ebx, 800h
0x1800034c1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800034c8  test    rax, rax
0x1800034cb  jz      short loc_1800034EA
0x1800034cd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800034d4  jnz     short loc_1800034EA
0x1800034d6  mov     r8d, ebx
0x1800034d9  lea     rdx, [rbp+13F0h+OutputString]
0x1800034e0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800034e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ea  cmp     [rbp+13F0h+OutputString], r13w
0x1800034f2  jnz     short loc_180003508
0x1800034f4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800034f9  mov     rdx, rbx; unsigned __int16 *
0x1800034fc  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003503  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003508  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000350f  call    cs:__imp_OutputDebugStringW
0x180003515  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000351a  jnz     short loc_180003525
0x18000351c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180003523  jz      short loc_180003537
0x180003525  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000352c  test    rax, rax
0x18000352f  jz      short loc_180003537
0x180003531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003536  nop
0x180003537  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000353c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
