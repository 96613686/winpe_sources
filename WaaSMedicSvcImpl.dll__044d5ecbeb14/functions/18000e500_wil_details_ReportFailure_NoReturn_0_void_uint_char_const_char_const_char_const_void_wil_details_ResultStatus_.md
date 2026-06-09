# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000e500`
- end: `0x18000e7c5`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000e2e0`

## callees

- `0x180005bbc`
- `0x18000a944`
- `0x18000b8d4`
- `0x18000c6c4`
- `0x18000ca20`
- `0x18000cba8`
- `0x18000e500`
- `0x18006b240`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e5c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e5c1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e759`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e759`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e6bd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e6bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  bool v11; // di
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v23 = *a7;
  v24 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v23, (int)a7);
  v21 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v22 = v13;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v26 = a8, v18) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v31 = a2;
  v32 = v12;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v19 = 1, (v22 & 2) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0, v17);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v15);
  if ( v11 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v21, OutputString);
  wil::ThrowResultException((wil *)&v21, v15);
  wil::details::WilFailFast((wil::details *)&v21, v20);
}

```

## disassembly

```asm
0x18000e500  mov     [rsp-8+arg_18], rbx
0x18000e505  push    rbp
0x18000e506  push    rsi
0x18000e507  push    rdi
0x18000e508  push    r12
0x18000e50a  push    r13
0x18000e50c  push    r14
0x18000e50e  push    r15
0x18000e510  lea     rbp, [rsp-13C0h]
0x18000e518  mov     eax, 14C0h
0x18000e51d  call    _alloca_probe
0x18000e522  sub     rsp, rax
0x18000e525  mov     r14, r8
0x18000e528  mov     esi, edx
0x18000e52a  mov     rbx, rcx
0x18000e52d  mov     r15, [rbp+13F0h+arg_28]
0x18000e534  xor     r13d, r13d
0x18000e537  cmp     cs:g_pfnThrowPlatformException, r13
0x18000e53e  setnz   dil
0x18000e542  xor     edx, edx; Val
0x18000e544  mov     r8d, 98h; Size
0x18000e54a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000e54f  call    memset_0
0x18000e554  nop
0x18000e555  mov     [rbp+13F0h+OutputString], r13w
0x18000e55d  mov     [rbp+13F0h+var_1430], r13b
0x18000e561  mov     rdx, [rbp+13F0h+arg_30]; int
0x18000e568  mov     ecx, [rdx]; this
0x18000e56a  mov     [rsp+14F0h+var_14C8], ecx
0x18000e56e  mov     eax, [rdx+4]
0x18000e571  mov     [rsp+14F0h+var_14C4], eax
0x18000e575  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000e57a  mov     r12d, eax
0x18000e57d  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000e582  mov     ecx, r13d
0x18000e585  lea     eax, [r13+8]
0x18000e589  cmp     dword ptr [rdx+8], 1
0x18000e58d  cmovz   ecx, eax
0x18000e590  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000e594  lea     ecx, [rax-7]
0x18000e597  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000e59f  inc     ecx
0x18000e5a1  mov     [rsp+14F0h+var_14C0], ecx
0x18000e5a5  mov     rcx, [rbp+13F0h+arg_38]
0x18000e5ac  test    rcx, rcx
0x18000e5af  jz      short loc_18000E5BC
0x18000e5b1  cmp     [rcx], r13w
0x18000e5b5  mov     [rsp+14F0h+var_14B8], rcx
0x18000e5ba  jnz     short loc_18000E5C1
0x18000e5bc  mov     [rsp+14F0h+var_14B8], r13
0x18000e5c1  call    cs:__imp_GetCurrentThreadId
0x18000e5c7  mov     [rsp+14F0h+var_14B0], eax
0x18000e5cb  mov     [rsp+14F0h+var_1498], r14
0x18000e5d0  mov     [rsp+14F0h+var_1490], esi
0x18000e5d4  mov     [rsp+14F0h+var_148C], r12d
0x18000e5d9  mov     [rsp+14F0h+var_14A8], r13
0x18000e5de  mov     [rsp+14F0h+var_14A0], r13
0x18000e5e3  mov     [rbp+13F0h+var_1448], r15
0x18000e5e7  mov     [rbp+13F0h+var_1440], rbx
0x18000e5eb  mov     [rsp+14F0h+var_1488], r13
0x18000e5f0  xorps   xmm0, xmm0
0x18000e5f3  xor     eax, eax
0x18000e5f5  movups  [rbp+13F0h+var_1468], xmm0
0x18000e5f9  mov     [rbp+13F0h+var_1458], rax
0x18000e5fd  xorps   xmm1, xmm1
0x18000e600  movups  [rsp+14F0h+var_1480], xmm1
0x18000e605  mov     [rbp+13F0h+var_1470], rax
0x18000e609  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000e610  test    rax, rax
0x18000e613  jz      short loc_18000E620
0x18000e615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e61a  mov     [rbp+13F0h+var_1450], rax
0x18000e61e  jmp     short loc_18000E624
0x18000e620  mov     [rbp+13F0h+var_1450], r13
0x18000e624  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e62b  test    rax, rax
0x18000e62e  jz      short loc_18000E63A
0x18000e630  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e63a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e641  test    rax, rax
0x18000e644  jz      short loc_18000E65A
0x18000e646  mov     r8d, 400h
0x18000e64c  lea     rdx, [rbp+13F0h+var_1430]
0x18000e650  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e65a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e661  test    rax, rax
0x18000e664  jz      short loc_18000E670
0x18000e666  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e670  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e677  test    rax, rax
0x18000e67a  jz      short loc_18000E692
0x18000e67c  test    dil, dil
0x18000e67f  jnz     short loc_18000E692
0x18000e681  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000e686  jnz     short loc_18000E692
0x18000e688  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e692  cmp     [rsp+14F0h+var_14C8], r13d
0x18000e697  jl      short loc_18000E69F
0x18000e699  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000e69f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000e6a6  jnz     short loc_18000E6C7
0x18000e6a8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e6af  test    rax, rax
0x18000e6b2  jz      short loc_18000E6BD
0x18000e6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6b9  test    al, al
0x18000e6bb  jmp     short loc_18000E6C5
0x18000e6bd  call    cs:__imp_IsDebuggerPresent
0x18000e6c3  test    eax, eax
0x18000e6c5  jz      short loc_18000E6D0
0x18000e6c7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000e6cc  mov     bl, 1
0x18000e6ce  jz      short loc_18000E6D3
0x18000e6d0  mov     bl, r13b
0x18000e6d3  test    dil, dil
0x18000e6d6  jnz     short loc_18000E702
0x18000e6d8  test    bl, bl
0x18000e6da  jnz     short loc_18000E702
0x18000e6dc  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e6e3  test    rax, rax
0x18000e6e6  jz      short loc_18000E75F
0x18000e6e8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000e6ef  jnz     short loc_18000E75F
0x18000e6f1  xor     r8d, r8d
0x18000e6f4  xor     edx, edx
0x18000e6f6  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e6fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e700  jmp     short loc_18000E75F
0x18000e702  mov     esi, 800h
0x18000e707  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e70e  test    rax, rax
0x18000e711  jz      short loc_18000E730
0x18000e713  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000e71a  jnz     short loc_18000E730
0x18000e71c  mov     r8d, esi
0x18000e71f  lea     rdx, [rbp+13F0h+OutputString]
0x18000e726  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e72b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e730  cmp     [rbp+13F0h+OutputString], r13w
0x18000e738  jnz     short loc_18000E74E
0x18000e73a  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000e73f  mov     rdx, rsi; unsigned __int16 *
0x18000e742  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000e749  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000e74e  test    bl, bl
0x18000e750  jz      short loc_18000E75F
0x18000e752  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000e759  call    cs:__imp_OutputDebugStringW
0x18000e75f  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000e764  jnz     short loc_18000E76F
0x18000e766  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000e76d  jz      short loc_18000E781
0x18000e76f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e776  test    rax, rax
0x18000e779  jz      short loc_18000E781
0x18000e77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e780  nop
0x18000e781  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000e786  jz      short loc_18000E793
0x18000e788  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000e78d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000e793  test    dil, dil
0x18000e796  jz      short loc_18000E7B0
0x18000e798  lea     rdx, [rbp+13F0h+OutputString]
0x18000e79f  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e7a4  mov     rax, cs:g_pfnThrowPlatformException
0x18000e7ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7b0  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000e7b5  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000e7ba  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000e7bf  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
