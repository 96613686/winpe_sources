# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800ed14c`
- end: `0x1800ed411`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800ecf60`

## callees

- `0x180003a40`
- `0x1800e4d20`
- `0x1800e7f74`
- `0x1800e97a8`
- `0x1800ebc40`
- `0x1800ec390`
- `0x1800ec608`
- `0x1800ed14c`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ed20d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ed20d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ed3a5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ed3a5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ed309`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ed309`

## pseudocode

```c
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
      g_pfnResultLoggingCallback(&v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0);
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
0x1800ed14c  mov     [rsp-8+arg_18], rbx
0x1800ed151  push    rbp
0x1800ed152  push    rsi
0x1800ed153  push    rdi
0x1800ed154  push    r12
0x1800ed156  push    r13
0x1800ed158  push    r14
0x1800ed15a  push    r15
0x1800ed15c  lea     rbp, [rsp-13C0h]
0x1800ed164  mov     eax, 14C0h
0x1800ed169  call    _alloca_probe
0x1800ed16e  sub     rsp, rax
0x1800ed171  mov     r14, r8
0x1800ed174  mov     esi, edx
0x1800ed176  mov     rbx, rcx
0x1800ed179  mov     r15, [rbp+13F0h+arg_28]
0x1800ed180  xor     r13d, r13d
0x1800ed183  cmp     cs:g_pfnThrowPlatformException, r13
0x1800ed18a  setnz   dil
0x1800ed18e  xor     edx, edx; Val
0x1800ed190  mov     r8d, 98h; Size
0x1800ed196  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800ed19b  call    memset_0
0x1800ed1a0  nop
0x1800ed1a1  mov     [rbp+13F0h+OutputString], r13w
0x1800ed1a9  mov     [rbp+13F0h+var_1430], r13b
0x1800ed1ad  mov     rdx, [rbp+13F0h+arg_30]; int
0x1800ed1b4  mov     ecx, [rdx]; this
0x1800ed1b6  mov     [rsp+14F0h+var_14C8], ecx
0x1800ed1ba  mov     eax, [rdx+4]
0x1800ed1bd  mov     [rsp+14F0h+var_14C4], eax
0x1800ed1c1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800ed1c6  mov     r12d, eax
0x1800ed1c9  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x1800ed1ce  mov     ecx, r13d
0x1800ed1d1  lea     eax, [r13+8]
0x1800ed1d5  cmp     dword ptr [rdx+8], 1
0x1800ed1d9  cmovz   ecx, eax
0x1800ed1dc  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800ed1e0  lea     ecx, [rax-7]
0x1800ed1e3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800ed1eb  inc     ecx
0x1800ed1ed  mov     [rsp+14F0h+var_14C0], ecx
0x1800ed1f1  mov     rcx, [rbp+13F0h+arg_38]
0x1800ed1f8  test    rcx, rcx
0x1800ed1fb  jz      short loc_1800ED208
0x1800ed1fd  cmp     [rcx], r13w
0x1800ed201  mov     [rsp+14F0h+var_14B8], rcx
0x1800ed206  jnz     short loc_1800ED20D
0x1800ed208  mov     [rsp+14F0h+var_14B8], r13
0x1800ed20d  call    cs:__imp_GetCurrentThreadId
0x1800ed213  mov     [rsp+14F0h+var_14B0], eax
0x1800ed217  mov     [rsp+14F0h+var_1498], r14
0x1800ed21c  mov     [rsp+14F0h+var_1490], esi
0x1800ed220  mov     [rsp+14F0h+var_148C], r12d
0x1800ed225  mov     [rsp+14F0h+var_14A8], r13
0x1800ed22a  mov     [rsp+14F0h+var_14A0], r13
0x1800ed22f  mov     [rbp+13F0h+var_1448], r15
0x1800ed233  mov     [rbp+13F0h+var_1440], rbx
0x1800ed237  mov     [rsp+14F0h+var_1488], r13
0x1800ed23c  xorps   xmm0, xmm0
0x1800ed23f  xor     eax, eax
0x1800ed241  movups  [rbp+13F0h+var_1468], xmm0
0x1800ed245  mov     [rbp+13F0h+var_1458], rax
0x1800ed249  xorps   xmm1, xmm1
0x1800ed24c  movups  [rsp+14F0h+var_1480], xmm1
0x1800ed251  mov     [rbp+13F0h+var_1470], rax
0x1800ed255  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800ed25c  test    rax, rax
0x1800ed25f  jz      short loc_1800ED26C
0x1800ed261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed266  mov     [rbp+13F0h+var_1450], rax
0x1800ed26a  jmp     short loc_1800ED270
0x1800ed26c  mov     [rbp+13F0h+var_1450], r13
0x1800ed270  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800ed277  test    rax, rax
0x1800ed27a  jz      short loc_1800ED286
0x1800ed27c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800ed281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed286  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800ed28d  test    rax, rax
0x1800ed290  jz      short loc_1800ED2A6
0x1800ed292  mov     r8d, 400h
0x1800ed298  lea     rdx, [rbp+13F0h+var_1430]
0x1800ed29c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800ed2a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed2a6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800ed2ad  test    rax, rax
0x1800ed2b0  jz      short loc_1800ED2BC
0x1800ed2b2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800ed2b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed2bc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800ed2c3  test    rax, rax
0x1800ed2c6  jz      short loc_1800ED2DE
0x1800ed2c8  test    dil, dil
0x1800ed2cb  jnz     short loc_1800ED2DE
0x1800ed2cd  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800ed2d2  jnz     short loc_1800ED2DE
0x1800ed2d4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800ed2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed2de  cmp     [rsp+14F0h+var_14C8], r13d
0x1800ed2e3  jl      short loc_1800ED2EB
0x1800ed2e5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800ed2eb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800ed2f2  jnz     short loc_1800ED313
0x1800ed2f4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800ed2fb  test    rax, rax
0x1800ed2fe  jz      short loc_1800ED309
0x1800ed300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed305  test    al, al
0x1800ed307  jmp     short loc_1800ED311
0x1800ed309  call    cs:__imp_IsDebuggerPresent
0x1800ed30f  test    eax, eax
0x1800ed311  jz      short loc_1800ED31C
0x1800ed313  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800ed318  mov     bl, 1
0x1800ed31a  jz      short loc_1800ED31F
0x1800ed31c  mov     bl, r13b
0x1800ed31f  test    dil, dil
0x1800ed322  jnz     short loc_1800ED34E
0x1800ed324  test    bl, bl
0x1800ed326  jnz     short loc_1800ED34E
0x1800ed328  mov     rax, cs:g_pfnResultLoggingCallback
0x1800ed32f  test    rax, rax
0x1800ed332  jz      short loc_1800ED3AB
0x1800ed334  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800ed33b  jnz     short loc_1800ED3AB
0x1800ed33d  xor     r8d, r8d
0x1800ed340  xor     edx, edx
0x1800ed342  lea     rcx, [rsp+14F0h+var_14D0]
0x1800ed347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed34c  jmp     short loc_1800ED3AB
0x1800ed34e  mov     esi, 800h
0x1800ed353  mov     rax, cs:g_pfnResultLoggingCallback
0x1800ed35a  test    rax, rax
0x1800ed35d  jz      short loc_1800ED37C
0x1800ed35f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800ed366  jnz     short loc_1800ED37C
0x1800ed368  mov     r8d, esi
0x1800ed36b  lea     rdx, [rbp+13F0h+OutputString]
0x1800ed372  lea     rcx, [rsp+14F0h+var_14D0]
0x1800ed377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed37c  cmp     [rbp+13F0h+OutputString], r13w
0x1800ed384  jnz     short loc_1800ED39A
0x1800ed386  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800ed38b  mov     rdx, rsi; unsigned __int16 *
0x1800ed38e  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800ed395  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800ed39a  test    bl, bl
0x1800ed39c  jz      short loc_1800ED3AB
0x1800ed39e  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800ed3a5  call    cs:__imp_OutputDebugStringW
0x1800ed3ab  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800ed3b0  jnz     short loc_1800ED3BB
0x1800ed3b2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800ed3b9  jz      short loc_1800ED3CD
0x1800ed3bb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800ed3c2  test    rax, rax
0x1800ed3c5  jz      short loc_1800ED3CD
0x1800ed3c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed3cc  nop
0x1800ed3cd  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800ed3d2  jz      short loc_1800ED3DF
0x1800ed3d4  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800ed3d9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800ed3df  test    dil, dil
0x1800ed3e2  jz      short loc_1800ED3FC
0x1800ed3e4  lea     rdx, [rbp+13F0h+OutputString]
0x1800ed3eb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800ed3f0  mov     rax, cs:g_pfnThrowPlatformException
0x1800ed3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed3fc  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800ed401  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1800ed406  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800ed40b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
