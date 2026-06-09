# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000a0b8`
- end: `0x18000a37d`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180009dd0`

## callees

- `0x1800024ac`
- `0x180005464`
- `0x180006b70`
- `0x180008b18`
- `0x180009270`
- `0x18000943c`
- `0x18000a0b8`
- `0x180032bf0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a179`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a179`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a311`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a311`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a275`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a275`

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
0x18000a0b8  mov     [rsp-8+arg_18], rbx
0x18000a0bd  push    rbp
0x18000a0be  push    rsi
0x18000a0bf  push    rdi
0x18000a0c0  push    r12
0x18000a0c2  push    r13
0x18000a0c4  push    r14
0x18000a0c6  push    r15
0x18000a0c8  lea     rbp, [rsp-13C0h]
0x18000a0d0  mov     eax, 14C0h
0x18000a0d5  call    _alloca_probe
0x18000a0da  sub     rsp, rax
0x18000a0dd  mov     r14, r8
0x18000a0e0  mov     esi, edx
0x18000a0e2  mov     rbx, rcx
0x18000a0e5  mov     r15, [rbp+13F0h+arg_28]
0x18000a0ec  xor     r13d, r13d
0x18000a0ef  cmp     cs:g_pfnThrowPlatformException, r13
0x18000a0f6  setnz   dil
0x18000a0fa  xor     edx, edx; Val
0x18000a0fc  mov     r8d, 98h; Size
0x18000a102  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000a107  call    memset_0
0x18000a10c  nop
0x18000a10d  mov     [rbp+13F0h+OutputString], r13w
0x18000a115  mov     [rbp+13F0h+var_1430], r13b
0x18000a119  mov     rdx, [rbp+13F0h+arg_30]; int
0x18000a120  mov     ecx, [rdx]; this
0x18000a122  mov     [rsp+14F0h+var_14C8], ecx
0x18000a126  mov     eax, [rdx+4]
0x18000a129  mov     [rsp+14F0h+var_14C4], eax
0x18000a12d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a132  mov     r12d, eax
0x18000a135  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000a13a  mov     ecx, r13d
0x18000a13d  lea     eax, [r13+8]
0x18000a141  cmp     dword ptr [rdx+8], 1
0x18000a145  cmovz   ecx, eax
0x18000a148  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000a14c  lea     ecx, [rax-7]
0x18000a14f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a157  inc     ecx
0x18000a159  mov     [rsp+14F0h+var_14C0], ecx
0x18000a15d  mov     rcx, [rbp+13F0h+arg_38]
0x18000a164  test    rcx, rcx
0x18000a167  jz      short loc_18000A174
0x18000a169  cmp     [rcx], r13w
0x18000a16d  mov     [rsp+14F0h+var_14B8], rcx
0x18000a172  jnz     short loc_18000A179
0x18000a174  mov     [rsp+14F0h+var_14B8], r13
0x18000a179  call    cs:__imp_GetCurrentThreadId
0x18000a17f  mov     [rsp+14F0h+var_14B0], eax
0x18000a183  mov     [rsp+14F0h+var_1498], r14
0x18000a188  mov     [rsp+14F0h+var_1490], esi
0x18000a18c  mov     [rsp+14F0h+var_148C], r12d
0x18000a191  mov     [rsp+14F0h+var_14A8], r13
0x18000a196  mov     [rsp+14F0h+var_14A0], r13
0x18000a19b  mov     [rbp+13F0h+var_1448], r15
0x18000a19f  mov     [rbp+13F0h+var_1440], rbx
0x18000a1a3  mov     [rsp+14F0h+var_1488], r13
0x18000a1a8  xorps   xmm0, xmm0
0x18000a1ab  xor     eax, eax
0x18000a1ad  movups  [rbp+13F0h+var_1468], xmm0
0x18000a1b1  mov     [rbp+13F0h+var_1458], rax
0x18000a1b5  xorps   xmm1, xmm1
0x18000a1b8  movups  [rsp+14F0h+var_1480], xmm1
0x18000a1bd  mov     [rbp+13F0h+var_1470], rax
0x18000a1c1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a1c8  test    rax, rax
0x18000a1cb  jz      short loc_18000A1D8
0x18000a1cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1d2  mov     [rbp+13F0h+var_1450], rax
0x18000a1d6  jmp     short loc_18000A1DC
0x18000a1d8  mov     [rbp+13F0h+var_1450], r13
0x18000a1dc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a1e3  test    rax, rax
0x18000a1e6  jz      short loc_18000A1F2
0x18000a1e8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1f2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a1f9  test    rax, rax
0x18000a1fc  jz      short loc_18000A212
0x18000a1fe  mov     r8d, 400h
0x18000a204  lea     rdx, [rbp+13F0h+var_1430]
0x18000a208  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a20d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a212  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a219  test    rax, rax
0x18000a21c  jz      short loc_18000A228
0x18000a21e  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a228  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a22f  test    rax, rax
0x18000a232  jz      short loc_18000A24A
0x18000a234  test    dil, dil
0x18000a237  jnz     short loc_18000A24A
0x18000a239  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000a23e  jnz     short loc_18000A24A
0x18000a240  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a24a  cmp     [rsp+14F0h+var_14C8], r13d
0x18000a24f  jl      short loc_18000A257
0x18000a251  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a257  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000a25e  jnz     short loc_18000A27F
0x18000a260  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a267  test    rax, rax
0x18000a26a  jz      short loc_18000A275
0x18000a26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a271  test    al, al
0x18000a273  jmp     short loc_18000A27D
0x18000a275  call    cs:__imp_IsDebuggerPresent
0x18000a27b  test    eax, eax
0x18000a27d  jz      short loc_18000A288
0x18000a27f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000a284  mov     bl, 1
0x18000a286  jz      short loc_18000A28B
0x18000a288  mov     bl, r13b
0x18000a28b  test    dil, dil
0x18000a28e  jnz     short loc_18000A2BA
0x18000a290  test    bl, bl
0x18000a292  jnz     short loc_18000A2BA
0x18000a294  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a29b  test    rax, rax
0x18000a29e  jz      short loc_18000A317
0x18000a2a0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000a2a7  jnz     short loc_18000A317
0x18000a2a9  xor     r8d, r8d
0x18000a2ac  xor     edx, edx
0x18000a2ae  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2b8  jmp     short loc_18000A317
0x18000a2ba  mov     esi, 800h
0x18000a2bf  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a2c6  test    rax, rax
0x18000a2c9  jz      short loc_18000A2E8
0x18000a2cb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000a2d2  jnz     short loc_18000A2E8
0x18000a2d4  mov     r8d, esi
0x18000a2d7  lea     rdx, [rbp+13F0h+OutputString]
0x18000a2de  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a2e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2e8  cmp     [rbp+13F0h+OutputString], r13w
0x18000a2f0  jnz     short loc_18000A306
0x18000a2f2  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000a2f7  mov     rdx, rsi; unsigned __int16 *
0x18000a2fa  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000a301  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a306  test    bl, bl
0x18000a308  jz      short loc_18000A317
0x18000a30a  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000a311  call    cs:__imp_OutputDebugStringW
0x18000a317  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000a31c  jnz     short loc_18000A327
0x18000a31e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000a325  jz      short loc_18000A339
0x18000a327  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a32e  test    rax, rax
0x18000a331  jz      short loc_18000A339
0x18000a333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a338  nop
0x18000a339  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000a33e  jz      short loc_18000A34B
0x18000a340  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000a345  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000a34b  test    dil, dil
0x18000a34e  jz      short loc_18000A368
0x18000a350  lea     rdx, [rbp+13F0h+OutputString]
0x18000a357  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a35c  mov     rax, cs:g_pfnThrowPlatformException
0x18000a363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a368  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000a36d  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000a372  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000a377  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
