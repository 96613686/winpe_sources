# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002780`
- end: `0x1800029f9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800023a4`

## callees

- `0x1800020e4`
- `0x180002780`
- `0x180004c84`
- `0x180005420`
- `0x180006050`
- `0x180008540`
- `0x18000caf0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002839`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002839`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800029c6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800029c6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000293c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000293c`

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
0x180002780  mov     [rsp-8+arg_18], rbx
0x180002785  push    rbp
0x180002786  push    rsi
0x180002787  push    rdi
0x180002788  push    r12
0x18000278a  push    r13
0x18000278c  push    r14
0x18000278e  push    r15
0x180002790  lea     rbp, [rsp-13C0h]
0x180002798  mov     eax, 14C0h
0x18000279d  call    _alloca_probe
0x1800027a2  sub     rsp, rax
0x1800027a5  mov     r14, r8
0x1800027a8  mov     esi, edx
0x1800027aa  mov     rdi, rcx
0x1800027ad  mov     r15, [rbp+13F0h+arg_28]
0x1800027b4  xor     edx, edx; Val
0x1800027b6  mov     r8d, 98h; Size
0x1800027bc  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800027c1  call    memset_0
0x1800027c6  nop
0x1800027c7  xor     r13d, r13d
0x1800027ca  mov     [rbp+13F0h+OutputString], r13w
0x1800027d2  mov     [rbp+13F0h+var_1430], r13b
0x1800027d6  mov     rbx, [rbp+13F0h+arg_30]
0x1800027dd  mov     ecx, [rbx]; this
0x1800027df  mov     [rsp+14F0h+var_14C8], ecx
0x1800027e3  mov     eax, [rbx+4]
0x1800027e6  mov     [rsp+14F0h+var_14C4], eax
0x1800027ea  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800027ef  mov     r12d, eax
0x1800027f2  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800027fa  mov     ecx, r13d
0x1800027fd  lea     eax, [r13+8]
0x180002801  cmp     dword ptr [rbx+8], 1
0x180002805  cmovz   ecx, eax
0x180002808  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000280c  lea     ecx, [rax-7]
0x18000280f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002817  inc     ecx
0x180002819  mov     [rsp+14F0h+var_14C0], ecx
0x18000281d  mov     rcx, [rbp+13F0h+arg_38]
0x180002824  test    rcx, rcx
0x180002827  jz      short loc_180002834
0x180002829  cmp     [rcx], r13w
0x18000282d  mov     [rsp+14F0h+var_14B8], rcx
0x180002832  jnz     short loc_180002839
0x180002834  mov     [rsp+14F0h+var_14B8], r13
0x180002839  call    cs:__imp_GetCurrentThreadId
0x18000283f  mov     [rsp+14F0h+var_14B0], eax
0x180002843  mov     [rsp+14F0h+var_1498], r14
0x180002848  mov     [rsp+14F0h+var_1490], esi
0x18000284c  mov     [rsp+14F0h+var_148C], r12d
0x180002851  mov     [rsp+14F0h+var_14A8], r13
0x180002856  mov     [rsp+14F0h+var_14A0], r13
0x18000285b  mov     [rbp+13F0h+var_1448], r15
0x18000285f  mov     [rbp+13F0h+var_1440], rdi
0x180002863  mov     [rsp+14F0h+var_1488], r13
0x180002868  xorps   xmm0, xmm0
0x18000286b  xor     eax, eax
0x18000286d  movups  [rbp+13F0h+var_1468], xmm0
0x180002871  mov     [rbp+13F0h+var_1458], rax
0x180002875  xorps   xmm1, xmm1
0x180002878  movups  [rsp+14F0h+var_1480], xmm1
0x18000287d  mov     [rbp+13F0h+var_1470], rax
0x180002881  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002888  test    rax, rax
0x18000288b  jz      short loc_180002898
0x18000288d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002892  mov     [rbp+13F0h+var_1450], rax
0x180002896  jmp     short loc_18000289C
0x180002898  mov     [rbp+13F0h+var_1450], r13
0x18000289c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800028a3  test    rax, rax
0x1800028a6  jz      short loc_1800028B2
0x1800028a8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800028ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028b2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800028b9  test    rax, rax
0x1800028bc  jz      short loc_1800028D2
0x1800028be  mov     r8d, 400h
0x1800028c4  lea     rdx, [rbp+13F0h+var_1430]
0x1800028c8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800028cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028d2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800028d9  test    rax, rax
0x1800028dc  jz      short loc_1800028E8
0x1800028de  lea     rcx, [rsp+14F0h+var_14D0]
0x1800028e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028e8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800028ef  test    rax, rax
0x1800028f2  jz      short loc_180002905
0x1800028f4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800028f9  jnz     short loc_180002905
0x1800028fb  lea     rcx, [rsp+14F0h+var_14D0]
0x180002900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002905  cmp     [rsp+14F0h+var_14C8], r13d
0x18000290a  jl      short loc_18000291E
0x18000290c  mov     ecx, 8000FFFFh; this
0x180002911  mov     [rsp+14F0h+var_14C8], ecx
0x180002915  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000291a  mov     [rsp+14F0h+var_14C4], eax
0x18000291e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002925  jnz     short loc_180002946
0x180002927  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000292e  test    rax, rax
0x180002931  jz      short loc_18000293C
0x180002933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002938  test    al, al
0x18000293a  jmp     short loc_180002944
0x18000293c  call    cs:__imp_IsDebuggerPresent
0x180002942  test    eax, eax
0x180002944  jz      short loc_18000294D
0x180002946  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000294b  jz      short loc_180002973
0x18000294d  mov     rax, cs:g_pfnResultLoggingCallback
0x180002954  test    rax, rax
0x180002957  jz      short loc_1800029CC
0x180002959  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002960  jnz     short loc_1800029CC
0x180002962  xor     r8d, r8d
0x180002965  xor     edx, edx
0x180002967  lea     rcx, [rsp+14F0h+var_14D0]
0x18000296c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002971  jmp     short loc_1800029CC
0x180002973  mov     ebx, 800h
0x180002978  mov     rax, cs:g_pfnResultLoggingCallback
0x18000297f  test    rax, rax
0x180002982  jz      short loc_1800029A1
0x180002984  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000298b  jnz     short loc_1800029A1
0x18000298d  mov     r8d, ebx
0x180002990  lea     rdx, [rbp+13F0h+OutputString]
0x180002997  lea     rcx, [rsp+14F0h+var_14D0]
0x18000299c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029a1  cmp     [rbp+13F0h+OutputString], r13w
0x1800029a9  jnz     short loc_1800029BF
0x1800029ab  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800029b0  mov     rdx, rbx; unsigned __int16 *
0x1800029b3  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800029ba  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800029bf  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800029c6  call    cs:__imp_OutputDebugStringW
0x1800029cc  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800029d1  jnz     short loc_1800029DC
0x1800029d3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800029da  jz      short loc_1800029EE
0x1800029dc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800029e3  test    rax, rax
0x1800029e6  jz      short loc_1800029EE
0x1800029e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ed  nop
0x1800029ee  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800029f3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
