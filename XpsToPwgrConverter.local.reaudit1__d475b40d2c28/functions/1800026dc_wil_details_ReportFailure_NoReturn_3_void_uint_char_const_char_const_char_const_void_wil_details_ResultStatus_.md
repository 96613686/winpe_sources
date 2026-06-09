# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800026dc`
- end: `0x180002955`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002444`

## callees

- `0x180002194`
- `0x1800026dc`
- `0x1800049e4`
- `0x180005180`
- `0x180005db0`
- `0x180008230`
- `0x18000f4f0`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002795`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002795`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002898`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002898`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002922`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002922`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x1800026dc  mov     [rsp-8+arg_18], rbx
0x1800026e1  push    rbp
0x1800026e2  push    rsi
0x1800026e3  push    rdi
0x1800026e4  push    r12
0x1800026e6  push    r13
0x1800026e8  push    r14
0x1800026ea  push    r15
0x1800026ec  lea     rbp, [rsp-13C0h]
0x1800026f4  mov     eax, 14C0h
0x1800026f9  call    _alloca_probe
0x1800026fe  sub     rsp, rax
0x180002701  mov     r14, r8
0x180002704  mov     esi, edx
0x180002706  mov     rdi, rcx
0x180002709  mov     r15, [rbp+13F0h+arg_28]
0x180002710  xor     edx, edx; Val
0x180002712  mov     r8d, 98h; Size
0x180002718  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000271d  call    memset_0
0x180002722  nop
0x180002723  xor     r13d, r13d
0x180002726  mov     [rbp+13F0h+OutputString], r13w
0x18000272e  mov     [rbp+13F0h+var_1430], r13b
0x180002732  mov     rbx, [rbp+13F0h+arg_30]
0x180002739  mov     ecx, [rbx]; this
0x18000273b  mov     [rsp+14F0h+var_14C8], ecx
0x18000273f  mov     eax, [rbx+4]
0x180002742  mov     [rsp+14F0h+var_14C4], eax
0x180002746  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000274b  mov     r12d, eax
0x18000274e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002756  mov     ecx, r13d
0x180002759  lea     eax, [r13+8]
0x18000275d  cmp     dword ptr [rbx+8], 1
0x180002761  cmovz   ecx, eax
0x180002764  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002768  lea     ecx, [rax-7]
0x18000276b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002773  inc     ecx
0x180002775  mov     [rsp+14F0h+var_14C0], ecx
0x180002779  mov     rcx, [rbp+13F0h+arg_38]
0x180002780  test    rcx, rcx
0x180002783  jz      short loc_180002790
0x180002785  cmp     [rcx], r13w
0x180002789  mov     [rsp+14F0h+var_14B8], rcx
0x18000278e  jnz     short loc_180002795
0x180002790  mov     [rsp+14F0h+var_14B8], r13
0x180002795  call    cs:__imp_GetCurrentThreadId
0x18000279b  mov     [rsp+14F0h+var_14B0], eax
0x18000279f  mov     [rsp+14F0h+var_1498], r14
0x1800027a4  mov     [rsp+14F0h+var_1490], esi
0x1800027a8  mov     [rsp+14F0h+var_148C], r12d
0x1800027ad  mov     [rsp+14F0h+var_14A8], r13
0x1800027b2  mov     [rsp+14F0h+var_14A0], r13
0x1800027b7  mov     [rbp+13F0h+var_1448], r15
0x1800027bb  mov     [rbp+13F0h+var_1440], rdi
0x1800027bf  mov     [rsp+14F0h+var_1488], r13
0x1800027c4  xorps   xmm0, xmm0
0x1800027c7  xor     eax, eax
0x1800027c9  movups  [rbp+13F0h+var_1468], xmm0
0x1800027cd  mov     [rbp+13F0h+var_1458], rax
0x1800027d1  xorps   xmm1, xmm1
0x1800027d4  movups  [rsp+14F0h+var_1480], xmm1
0x1800027d9  mov     [rbp+13F0h+var_1470], rax
0x1800027dd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800027e4  test    rax, rax
0x1800027e7  jz      short loc_1800027F4
0x1800027e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027ee  mov     [rbp+13F0h+var_1450], rax
0x1800027f2  jmp     short loc_1800027F8
0x1800027f4  mov     [rbp+13F0h+var_1450], r13
0x1800027f8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800027ff  test    rax, rax
0x180002802  jz      short loc_18000280E
0x180002804  lea     rcx, [rsp+14F0h+var_14D0]
0x180002809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000280e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002815  test    rax, rax
0x180002818  jz      short loc_18000282E
0x18000281a  mov     r8d, 400h
0x180002820  lea     rdx, [rbp+13F0h+var_1430]
0x180002824  lea     rcx, [rsp+14F0h+var_14D0]
0x180002829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000282e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002835  test    rax, rax
0x180002838  jz      short loc_180002844
0x18000283a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000283f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002844  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000284b  test    rax, rax
0x18000284e  jz      short loc_180002861
0x180002850  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002855  jnz     short loc_180002861
0x180002857  lea     rcx, [rsp+14F0h+var_14D0]
0x18000285c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002861  cmp     [rsp+14F0h+var_14C8], r13d
0x180002866  jl      short loc_18000287A
0x180002868  mov     ecx, 8000FFFFh; this
0x18000286d  mov     [rsp+14F0h+var_14C8], ecx
0x180002871  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002876  mov     [rsp+14F0h+var_14C4], eax
0x18000287a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002881  jnz     short loc_1800028A2
0x180002883  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000288a  test    rax, rax
0x18000288d  jz      short loc_180002898
0x18000288f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002894  test    al, al
0x180002896  jmp     short loc_1800028A0
0x180002898  call    cs:__imp_IsDebuggerPresent
0x18000289e  test    eax, eax
0x1800028a0  jz      short loc_1800028A9
0x1800028a2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800028a7  jz      short loc_1800028CF
0x1800028a9  mov     rax, cs:g_pfnResultLoggingCallback
0x1800028b0  test    rax, rax
0x1800028b3  jz      short loc_180002928
0x1800028b5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800028bc  jnz     short loc_180002928
0x1800028be  xor     r8d, r8d
0x1800028c1  xor     edx, edx
0x1800028c3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800028c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028cd  jmp     short loc_180002928
0x1800028cf  mov     ebx, 800h
0x1800028d4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800028db  test    rax, rax
0x1800028de  jz      short loc_1800028FD
0x1800028e0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800028e7  jnz     short loc_1800028FD
0x1800028e9  mov     r8d, ebx
0x1800028ec  lea     rdx, [rbp+13F0h+OutputString]
0x1800028f3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800028f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028fd  cmp     [rbp+13F0h+OutputString], r13w
0x180002905  jnz     short loc_18000291B
0x180002907  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000290c  mov     rdx, rbx; unsigned __int16 *
0x18000290f  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002916  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000291b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002922  call    cs:__imp_OutputDebugStringW
0x180002928  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000292d  jnz     short loc_180002938
0x18000292f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002936  jz      short loc_18000294A
0x180002938  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000293f  test    rax, rax
0x180002942  jz      short loc_18000294A
0x180002944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002949  nop
0x18000294a  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000294f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
