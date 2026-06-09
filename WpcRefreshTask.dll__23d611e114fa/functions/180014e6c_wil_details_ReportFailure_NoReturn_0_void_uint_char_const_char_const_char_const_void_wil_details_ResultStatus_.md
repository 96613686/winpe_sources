# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180014e6c`
- end: `0x180015131`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180014c78`

## callees

- `0x180006ed4`
- `0x18000bea4`
- `0x18000cf94`
- `0x18000dd10`
- `0x18000e2f0`
- `0x18000e58c`
- `0x180014e6c`
- `0x1800a28a0`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014f2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014f2d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800150c5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800150c5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015029`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015029`

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
0x180014e6c  mov     [rsp-8+arg_18], rbx
0x180014e71  push    rbp
0x180014e72  push    rsi
0x180014e73  push    rdi
0x180014e74  push    r12
0x180014e76  push    r13
0x180014e78  push    r14
0x180014e7a  push    r15
0x180014e7c  lea     rbp, [rsp-13C0h]
0x180014e84  mov     eax, 14C0h
0x180014e89  call    _alloca_probe
0x180014e8e  sub     rsp, rax
0x180014e91  mov     r14, r8
0x180014e94  mov     esi, edx
0x180014e96  mov     rbx, rcx
0x180014e99  mov     r15, [rbp+13F0h+arg_28]
0x180014ea0  xor     r13d, r13d
0x180014ea3  cmp     cs:g_pfnThrowPlatformException, r13
0x180014eaa  setnz   dil
0x180014eae  xor     edx, edx; Val
0x180014eb0  mov     r8d, 98h; Size
0x180014eb6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180014ebb  call    memset_0
0x180014ec0  nop
0x180014ec1  mov     [rbp+13F0h+OutputString], r13w
0x180014ec9  mov     [rbp+13F0h+var_1430], r13b
0x180014ecd  mov     rdx, [rbp+13F0h+arg_30]; int
0x180014ed4  mov     ecx, [rdx]; this
0x180014ed6  mov     [rsp+14F0h+var_14C8], ecx
0x180014eda  mov     eax, [rdx+4]
0x180014edd  mov     [rsp+14F0h+var_14C4], eax
0x180014ee1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180014ee6  mov     r12d, eax
0x180014ee9  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180014eee  mov     ecx, r13d
0x180014ef1  lea     eax, [r13+8]
0x180014ef5  cmp     dword ptr [rdx+8], 1
0x180014ef9  cmovz   ecx, eax
0x180014efc  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180014f00  lea     ecx, [rax-7]
0x180014f03  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180014f0b  inc     ecx
0x180014f0d  mov     [rsp+14F0h+var_14C0], ecx
0x180014f11  mov     rcx, [rbp+13F0h+arg_38]
0x180014f18  test    rcx, rcx
0x180014f1b  jz      short loc_180014F28
0x180014f1d  cmp     [rcx], r13w
0x180014f21  mov     [rsp+14F0h+var_14B8], rcx
0x180014f26  jnz     short loc_180014F2D
0x180014f28  mov     [rsp+14F0h+var_14B8], r13
0x180014f2d  call    cs:__imp_GetCurrentThreadId
0x180014f33  mov     [rsp+14F0h+var_14B0], eax
0x180014f37  mov     [rsp+14F0h+var_1498], r14
0x180014f3c  mov     [rsp+14F0h+var_1490], esi
0x180014f40  mov     [rsp+14F0h+var_148C], r12d
0x180014f45  mov     [rsp+14F0h+var_14A8], r13
0x180014f4a  mov     [rsp+14F0h+var_14A0], r13
0x180014f4f  mov     [rbp+13F0h+var_1448], r15
0x180014f53  mov     [rbp+13F0h+var_1440], rbx
0x180014f57  mov     [rsp+14F0h+var_1488], r13
0x180014f5c  xorps   xmm0, xmm0
0x180014f5f  xor     eax, eax
0x180014f61  movups  [rbp+13F0h+var_1468], xmm0
0x180014f65  mov     [rbp+13F0h+var_1458], rax
0x180014f69  xorps   xmm1, xmm1
0x180014f6c  movups  [rsp+14F0h+var_1480], xmm1
0x180014f71  mov     [rbp+13F0h+var_1470], rax
0x180014f75  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180014f7c  test    rax, rax
0x180014f7f  jz      short loc_180014F8C
0x180014f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f86  mov     [rbp+13F0h+var_1450], rax
0x180014f8a  jmp     short loc_180014F90
0x180014f8c  mov     [rbp+13F0h+var_1450], r13
0x180014f90  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180014f97  test    rax, rax
0x180014f9a  jz      short loc_180014FA6
0x180014f9c  lea     rcx, [rsp+14F0h+var_14D0]
0x180014fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fa6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180014fad  test    rax, rax
0x180014fb0  jz      short loc_180014FC6
0x180014fb2  mov     r8d, 400h
0x180014fb8  lea     rdx, [rbp+13F0h+var_1430]
0x180014fbc  lea     rcx, [rsp+14F0h+var_14D0]
0x180014fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fc6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180014fcd  test    rax, rax
0x180014fd0  jz      short loc_180014FDC
0x180014fd2  lea     rcx, [rsp+14F0h+var_14D0]
0x180014fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fdc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180014fe3  test    rax, rax
0x180014fe6  jz      short loc_180014FFE
0x180014fe8  test    dil, dil
0x180014feb  jnz     short loc_180014FFE
0x180014fed  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180014ff2  jnz     short loc_180014FFE
0x180014ff4  lea     rcx, [rsp+14F0h+var_14D0]
0x180014ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ffe  cmp     [rsp+14F0h+var_14C8], r13d
0x180015003  jl      short loc_18001500B
0x180015005  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001500b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180015012  jnz     short loc_180015033
0x180015014  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001501b  test    rax, rax
0x18001501e  jz      short loc_180015029
0x180015020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015025  test    al, al
0x180015027  jmp     short loc_180015031
0x180015029  call    cs:__imp_IsDebuggerPresent
0x18001502f  test    eax, eax
0x180015031  jz      short loc_18001503C
0x180015033  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180015038  mov     bl, 1
0x18001503a  jz      short loc_18001503F
0x18001503c  mov     bl, r13b
0x18001503f  test    dil, dil
0x180015042  jnz     short loc_18001506E
0x180015044  test    bl, bl
0x180015046  jnz     short loc_18001506E
0x180015048  mov     rax, cs:g_pfnResultLoggingCallback
0x18001504f  test    rax, rax
0x180015052  jz      short loc_1800150CB
0x180015054  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001505b  jnz     short loc_1800150CB
0x18001505d  xor     r8d, r8d
0x180015060  xor     edx, edx
0x180015062  lea     rcx, [rsp+14F0h+var_14D0]
0x180015067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001506c  jmp     short loc_1800150CB
0x18001506e  mov     esi, 800h
0x180015073  mov     rax, cs:g_pfnResultLoggingCallback
0x18001507a  test    rax, rax
0x18001507d  jz      short loc_18001509C
0x18001507f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180015086  jnz     short loc_18001509C
0x180015088  mov     r8d, esi
0x18001508b  lea     rdx, [rbp+13F0h+OutputString]
0x180015092  lea     rcx, [rsp+14F0h+var_14D0]
0x180015097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001509c  cmp     [rbp+13F0h+OutputString], r13w
0x1800150a4  jnz     short loc_1800150BA
0x1800150a6  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800150ab  mov     rdx, rsi; unsigned __int16 *
0x1800150ae  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800150b5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800150ba  test    bl, bl
0x1800150bc  jz      short loc_1800150CB
0x1800150be  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800150c5  call    cs:__imp_OutputDebugStringW
0x1800150cb  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800150d0  jnz     short loc_1800150DB
0x1800150d2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800150d9  jz      short loc_1800150ED
0x1800150db  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800150e2  test    rax, rax
0x1800150e5  jz      short loc_1800150ED
0x1800150e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150ec  nop
0x1800150ed  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800150f2  jz      short loc_1800150FF
0x1800150f4  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800150f9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800150ff  test    dil, dil
0x180015102  jz      short loc_18001511C
0x180015104  lea     rdx, [rbp+13F0h+OutputString]
0x18001510b  lea     rcx, [rsp+14F0h+var_14D0]
0x180015110  mov     rax, cs:g_pfnThrowPlatformException
0x180015117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001511c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180015121  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180015126  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001512b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
