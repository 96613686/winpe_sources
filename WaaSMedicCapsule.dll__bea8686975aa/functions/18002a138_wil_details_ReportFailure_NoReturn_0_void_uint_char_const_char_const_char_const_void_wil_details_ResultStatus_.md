# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18002a138`
- end: `0x18002a3fd`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180029fcc`

## callees

- `0x180004708`
- `0x180008254`
- `0x180009750`
- `0x18000a65c`
- `0x18000a9b0`
- `0x18000ab38`
- `0x18002a138`
- `0x180060700`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a1f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a1f9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002a391`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002a391`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002a2f5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002a2f5`

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
0x18002a138  mov     [rsp-8+arg_18], rbx
0x18002a13d  push    rbp
0x18002a13e  push    rsi
0x18002a13f  push    rdi
0x18002a140  push    r12
0x18002a142  push    r13
0x18002a144  push    r14
0x18002a146  push    r15
0x18002a148  lea     rbp, [rsp-13C0h]
0x18002a150  mov     eax, 14C0h
0x18002a155  call    _alloca_probe
0x18002a15a  sub     rsp, rax
0x18002a15d  mov     r14, r8
0x18002a160  mov     esi, edx
0x18002a162  mov     rbx, rcx
0x18002a165  mov     r15, [rbp+13F0h+arg_28]
0x18002a16c  xor     r13d, r13d
0x18002a16f  cmp     cs:g_pfnThrowPlatformException, r13
0x18002a176  setnz   dil
0x18002a17a  xor     edx, edx; Val
0x18002a17c  mov     r8d, 98h; Size
0x18002a182  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18002a187  call    memset_0
0x18002a18c  nop
0x18002a18d  mov     [rbp+13F0h+OutputString], r13w
0x18002a195  mov     [rbp+13F0h+var_1430], r13b
0x18002a199  mov     rdx, [rbp+13F0h+arg_30]; int
0x18002a1a0  mov     ecx, [rdx]; this
0x18002a1a2  mov     [rsp+14F0h+var_14C8], ecx
0x18002a1a6  mov     eax, [rdx+4]
0x18002a1a9  mov     [rsp+14F0h+var_14C4], eax
0x18002a1ad  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002a1b2  mov     r12d, eax
0x18002a1b5  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18002a1ba  mov     ecx, r13d
0x18002a1bd  lea     eax, [r13+8]
0x18002a1c1  cmp     dword ptr [rdx+8], 1
0x18002a1c5  cmovz   ecx, eax
0x18002a1c8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18002a1cc  lea     ecx, [rax-7]
0x18002a1cf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002a1d7  inc     ecx
0x18002a1d9  mov     [rsp+14F0h+var_14C0], ecx
0x18002a1dd  mov     rcx, [rbp+13F0h+arg_38]
0x18002a1e4  test    rcx, rcx
0x18002a1e7  jz      short loc_18002A1F4
0x18002a1e9  cmp     [rcx], r13w
0x18002a1ed  mov     [rsp+14F0h+var_14B8], rcx
0x18002a1f2  jnz     short loc_18002A1F9
0x18002a1f4  mov     [rsp+14F0h+var_14B8], r13
0x18002a1f9  call    cs:__imp_GetCurrentThreadId
0x18002a1ff  mov     [rsp+14F0h+var_14B0], eax
0x18002a203  mov     [rsp+14F0h+var_1498], r14
0x18002a208  mov     [rsp+14F0h+var_1490], esi
0x18002a20c  mov     [rsp+14F0h+var_148C], r12d
0x18002a211  mov     [rsp+14F0h+var_14A8], r13
0x18002a216  mov     [rsp+14F0h+var_14A0], r13
0x18002a21b  mov     [rbp+13F0h+var_1448], r15
0x18002a21f  mov     [rbp+13F0h+var_1440], rbx
0x18002a223  mov     [rsp+14F0h+var_1488], r13
0x18002a228  xorps   xmm0, xmm0
0x18002a22b  xor     eax, eax
0x18002a22d  movups  [rbp+13F0h+var_1468], xmm0
0x18002a231  mov     [rbp+13F0h+var_1458], rax
0x18002a235  xorps   xmm1, xmm1
0x18002a238  movups  [rsp+14F0h+var_1480], xmm1
0x18002a23d  mov     [rbp+13F0h+var_1470], rax
0x18002a241  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002a248  test    rax, rax
0x18002a24b  jz      short loc_18002A258
0x18002a24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a252  mov     [rbp+13F0h+var_1450], rax
0x18002a256  jmp     short loc_18002A25C
0x18002a258  mov     [rbp+13F0h+var_1450], r13
0x18002a25c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002a263  test    rax, rax
0x18002a266  jz      short loc_18002A272
0x18002a268  lea     rcx, [rsp+14F0h+var_14D0]
0x18002a26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a272  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002a279  test    rax, rax
0x18002a27c  jz      short loc_18002A292
0x18002a27e  mov     r8d, 400h
0x18002a284  lea     rdx, [rbp+13F0h+var_1430]
0x18002a288  lea     rcx, [rsp+14F0h+var_14D0]
0x18002a28d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a292  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002a299  test    rax, rax
0x18002a29c  jz      short loc_18002A2A8
0x18002a29e  lea     rcx, [rsp+14F0h+var_14D0]
0x18002a2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2a8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002a2af  test    rax, rax
0x18002a2b2  jz      short loc_18002A2CA
0x18002a2b4  test    dil, dil
0x18002a2b7  jnz     short loc_18002A2CA
0x18002a2b9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002a2be  jnz     short loc_18002A2CA
0x18002a2c0  lea     rcx, [rsp+14F0h+var_14D0]
0x18002a2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2ca  cmp     [rsp+14F0h+var_14C8], r13d
0x18002a2cf  jl      short loc_18002A2D7
0x18002a2d1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002a2d7  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18002a2de  jnz     short loc_18002A2FF
0x18002a2e0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002a2e7  test    rax, rax
0x18002a2ea  jz      short loc_18002A2F5
0x18002a2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a2f1  test    al, al
0x18002a2f3  jmp     short loc_18002A2FD
0x18002a2f5  call    cs:__imp_IsDebuggerPresent
0x18002a2fb  test    eax, eax
0x18002a2fd  jz      short loc_18002A308
0x18002a2ff  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002a304  mov     bl, 1
0x18002a306  jz      short loc_18002A30B
0x18002a308  mov     bl, r13b
0x18002a30b  test    dil, dil
0x18002a30e  jnz     short loc_18002A33A
0x18002a310  test    bl, bl
0x18002a312  jnz     short loc_18002A33A
0x18002a314  mov     rax, cs:g_pfnResultLoggingCallback
0x18002a31b  test    rax, rax
0x18002a31e  jz      short loc_18002A397
0x18002a320  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18002a327  jnz     short loc_18002A397
0x18002a329  xor     r8d, r8d
0x18002a32c  xor     edx, edx
0x18002a32e  lea     rcx, [rsp+14F0h+var_14D0]
0x18002a333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a338  jmp     short loc_18002A397
0x18002a33a  mov     esi, 800h
0x18002a33f  mov     rax, cs:g_pfnResultLoggingCallback
0x18002a346  test    rax, rax
0x18002a349  jz      short loc_18002A368
0x18002a34b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18002a352  jnz     short loc_18002A368
0x18002a354  mov     r8d, esi
0x18002a357  lea     rdx, [rbp+13F0h+OutputString]
0x18002a35e  lea     rcx, [rsp+14F0h+var_14D0]
0x18002a363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a368  cmp     [rbp+13F0h+OutputString], r13w
0x18002a370  jnz     short loc_18002A386
0x18002a372  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18002a377  mov     rdx, rsi; unsigned __int16 *
0x18002a37a  lea     rcx, [rbp+13F0h+OutputString]; this
0x18002a381  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002a386  test    bl, bl
0x18002a388  jz      short loc_18002A397
0x18002a38a  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18002a391  call    cs:__imp_OutputDebugStringW
0x18002a397  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18002a39c  jnz     short loc_18002A3A7
0x18002a39e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18002a3a5  jz      short loc_18002A3B9
0x18002a3a7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002a3ae  test    rax, rax
0x18002a3b1  jz      short loc_18002A3B9
0x18002a3b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3b8  nop
0x18002a3b9  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18002a3be  jz      short loc_18002A3CB
0x18002a3c0  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002a3c5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18002a3cb  test    dil, dil
0x18002a3ce  jz      short loc_18002A3E8
0x18002a3d0  lea     rdx, [rbp+13F0h+OutputString]
0x18002a3d7  lea     rcx, [rsp+14F0h+var_14D0]
0x18002a3dc  mov     rax, cs:g_pfnThrowPlatformException
0x18002a3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3e8  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002a3ed  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18002a3f2  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002a3f7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
