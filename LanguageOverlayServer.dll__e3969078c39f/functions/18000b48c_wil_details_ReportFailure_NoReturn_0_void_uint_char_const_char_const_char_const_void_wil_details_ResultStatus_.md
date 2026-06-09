# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000b48c`
- end: `0x18000b772`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `742`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *, char)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000ae88`

## callees

- `0x1800044b8`
- `0x180007bb4`
- `0x1800089a8`
- `0x180009044`
- `0x180009b00`
- `0x180009e70`
- `0x180009ff8`
- `0x18000b48c`
- `0x1800633f0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b560`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b560`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b660`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b660`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b6fd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b6fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        char a9)
{
  bool v12; // di
  _WORD *v13; // r8
  int v14; // r13d
  int v15; // ecx
  __int64 v16; // rdx
  const struct wil::FailureInfo *v17; // rdx
  wil::details::in1diag3 *v18; // rcx
  const struct wil::FailureInfo *v19; // r9
  bool v20; // zf
  char v21; // bl
  const struct wil::FailureInfo *v22; // rdx
  int v23; // [rsp+20h] [rbp-E0h] BYREF
  int v24; // [rsp+24h] [rbp-DCh]
  int v25; // [rsp+28h] [rbp-D8h]
  int v26; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v27; // [rsp+30h] [rbp-D0h]
  _WORD *v28; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v30; // [rsp+48h] [rbp-B8h]
  __int64 v31; // [rsp+50h] [rbp-B0h]
  __int64 v32; // [rsp+58h] [rbp-A8h]
  int v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+64h] [rbp-9Ch]
  __int64 v35; // [rsp+68h] [rbp-98h]
  __int128 v36; // [rsp+70h] [rbp-90h]
  __int64 v37; // [rsp+80h] [rbp-80h]
  __int128 v38; // [rsp+88h] [rbp-78h]
  __int64 v39; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v41; // [rsp+A8h] [rbp-58h]
  __int64 v42; // [rsp+B0h] [rbp-50h]
  char v43[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v12 = (a9 & 2) == 0 && g_pfnThrowPlatformException;
  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v25 = *a7;
  v26 = a7[1];
  v14 = wil::details::RecordException((wil::details *)(unsigned int)v25, (int)a7);
  v23 = (int)v13;
  v15 = (int)v13;
  if ( *(_DWORD *)(v16 + 8) == 1 )
    v15 = (_DWORD)v13 + 8;
  v24 = v15;
  v27 = _InterlockedExchangeAdd(&`wil::details::LogFailure'::`2'::s_failureId, (_DWORD)v13 + 1) + 1;
  if ( !a8 || (v20 = *a8 == (unsigned __int16)v13, v28 = a8, v20) )
    v28 = v13;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v14;
  v30 = 0;
  v31 = 0;
  v41 = a6;
  v42 = a1;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v18);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v23, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v23);
  if ( wil::details::g_pfnOriginateCallback && !v12 && (v24 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v23);
  if ( v25 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v18);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v20 = !IsDebuggerPresent())
      : (v20 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v18) == 0),
        v20)
    || (v21 = 1, (v24 & 2) != 0) )
  {
    v21 = 0;
  }
  if ( v12 || v21 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v23, v19);
    if ( v21 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v23, 0, 0);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v18);
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v17);
  if ( v12 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v23, OutputString);
  if ( (a9 & 2) != 0 )
    wil::RethrowCaughtException(v18);
  wil::ThrowResultException((wil *)&v23, v17);
  wil::details::WilFailFast((wil::details *)&v23, v22);
}

```

## disassembly

```asm
0x18000b48c  mov     [rsp-8+arg_18], rbx
0x18000b491  push    rbp
0x18000b492  push    rsi
0x18000b493  push    rdi
0x18000b494  push    r12
0x18000b496  push    r13
0x18000b498  push    r14
0x18000b49a  push    r15
0x18000b49c  lea     rbp, [rsp-13C0h]
0x18000b4a4  mov     eax, 14C0h
0x18000b4a9  call    _alloca_probe
0x18000b4ae  sub     rsp, rax
0x18000b4b1  mov     r15, r8
0x18000b4b4  mov     r14d, edx
0x18000b4b7  mov     rbx, rcx
0x18000b4ba  mov     r12, [rbp+13F0h+arg_28]
0x18000b4c1  mov     esi, [rbp+13F0h+arg_40]
0x18000b4c7  and     esi, 2
0x18000b4ca  jnz     short loc_18000B4DB
0x18000b4cc  cmp     cs:g_pfnThrowPlatformException, 0
0x18000b4d4  jz      short loc_18000B4DB
0x18000b4d6  mov     dil, 1
0x18000b4d9  jmp     short loc_18000B4DE
0x18000b4db  xor     dil, dil
0x18000b4de  xor     edx, edx; Val
0x18000b4e0  mov     r8d, 98h; Size
0x18000b4e6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000b4eb  call    memset_0
0x18000b4f0  nop
0x18000b4f1  xor     r8d, r8d
0x18000b4f4  mov     [rbp+13F0h+OutputString], r8w
0x18000b4fc  mov     [rbp+13F0h+var_1430], r8b
0x18000b500  mov     rdx, [rbp+13F0h+arg_30]; int
0x18000b507  mov     ecx, [rdx]; this
0x18000b509  mov     [rsp+14F0h+var_14C8], ecx
0x18000b50d  mov     eax, [rdx+4]
0x18000b510  mov     [rsp+14F0h+var_14C4], eax
0x18000b514  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000b519  mov     r13d, eax
0x18000b51c  mov     dword ptr [rsp+14F0h+var_14D0], r8d
0x18000b521  mov     ecx, r8d
0x18000b524  lea     eax, [r8+8]
0x18000b528  cmp     dword ptr [rdx+8], 1
0x18000b52c  cmovz   ecx, eax
0x18000b52f  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000b533  lea     ecx, [rax-7]
0x18000b536  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000b53e  inc     ecx
0x18000b540  mov     [rsp+14F0h+var_14C0], ecx
0x18000b544  mov     rcx, [rbp+13F0h+arg_38]
0x18000b54b  test    rcx, rcx
0x18000b54e  jz      short loc_18000B55B
0x18000b550  cmp     [rcx], r8w
0x18000b554  mov     [rsp+14F0h+var_14B8], rcx
0x18000b559  jnz     short loc_18000B560
0x18000b55b  mov     [rsp+14F0h+var_14B8], r8
0x18000b560  call    cs:__imp_GetCurrentThreadId
0x18000b566  mov     [rsp+14F0h+var_14B0], eax
0x18000b56a  mov     [rsp+14F0h+var_1498], r15
0x18000b56f  mov     [rsp+14F0h+var_1490], r14d
0x18000b574  mov     [rsp+14F0h+var_148C], r13d
0x18000b579  xor     r14d, r14d
0x18000b57c  mov     [rsp+14F0h+var_14A8], r14
0x18000b581  mov     [rsp+14F0h+var_14A0], r14
0x18000b586  mov     [rbp+13F0h+var_1448], r12
0x18000b58a  mov     [rbp+13F0h+var_1440], rbx
0x18000b58e  mov     [rsp+14F0h+var_1488], r14
0x18000b593  xorps   xmm0, xmm0
0x18000b596  xor     eax, eax
0x18000b598  movups  [rbp+13F0h+var_1468], xmm0
0x18000b59c  mov     [rbp+13F0h+var_1458], rax
0x18000b5a0  xorps   xmm1, xmm1
0x18000b5a3  movups  [rsp+14F0h+var_1480], xmm1
0x18000b5a8  mov     [rbp+13F0h+var_1470], rax
0x18000b5ac  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000b5b3  test    rax, rax
0x18000b5b6  jz      short loc_18000B5C3
0x18000b5b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5bd  mov     [rbp+13F0h+var_1450], rax
0x18000b5c1  jmp     short loc_18000B5C7
0x18000b5c3  mov     [rbp+13F0h+var_1450], r14
0x18000b5c7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000b5ce  test    rax, rax
0x18000b5d1  jz      short loc_18000B5DD
0x18000b5d3  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b5d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5dd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000b5e4  test    rax, rax
0x18000b5e7  jz      short loc_18000B5FD
0x18000b5e9  mov     r8d, 400h
0x18000b5ef  lea     rdx, [rbp+13F0h+var_1430]
0x18000b5f3  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5fd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b604  test    rax, rax
0x18000b607  jz      short loc_18000B613
0x18000b609  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b613  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b61a  test    rax, rax
0x18000b61d  jz      short loc_18000B635
0x18000b61f  test    dil, dil
0x18000b622  jnz     short loc_18000B635
0x18000b624  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000b629  jnz     short loc_18000B635
0x18000b62b  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b635  cmp     [rsp+14F0h+var_14C8], r14d
0x18000b63a  jl      short loc_18000B642
0x18000b63c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000b642  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r14b; bool wil::g_fIsDebuggerPresent
0x18000b649  jnz     short loc_18000B66A
0x18000b64b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000b652  test    rax, rax
0x18000b655  jz      short loc_18000B660
0x18000b657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b65c  test    al, al
0x18000b65e  jmp     short loc_18000B668
0x18000b660  call    cs:__imp_IsDebuggerPresent
0x18000b666  test    eax, eax
0x18000b668  jz      short loc_18000B673
0x18000b66a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000b66f  mov     bl, 1
0x18000b671  jz      short loc_18000B676
0x18000b673  mov     bl, r14b
0x18000b676  test    dil, dil
0x18000b679  jnz     short loc_18000B6A5
0x18000b67b  test    bl, bl
0x18000b67d  jnz     short loc_18000B6A5
0x18000b67f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b686  test    rax, rax
0x18000b689  jz      short loc_18000B703
0x18000b68b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r14b; bool wil::details::g_resultMessageCallbackSet
0x18000b692  jnz     short loc_18000B703
0x18000b694  xor     r8d, r8d
0x18000b697  xor     edx, edx
0x18000b699  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6a3  jmp     short loc_18000B703
0x18000b6a5  mov     r15d, 800h
0x18000b6ab  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b6b2  test    rax, rax
0x18000b6b5  jz      short loc_18000B6D4
0x18000b6b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r14b; bool wil::details::g_resultMessageCallbackSet
0x18000b6be  jnz     short loc_18000B6D4
0x18000b6c0  mov     r8d, r15d
0x18000b6c3  lea     rdx, [rbp+13F0h+OutputString]
0x18000b6ca  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6d4  cmp     [rbp+13F0h+OutputString], r14w
0x18000b6dc  jnz     short loc_18000B6F2
0x18000b6de  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000b6e3  mov     rdx, r15; unsigned __int16 *
0x18000b6e6  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000b6ed  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000b6f2  test    bl, bl
0x18000b6f4  jz      short loc_18000B703
0x18000b6f6  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000b6fd  call    cs:__imp_OutputDebugStringW
0x18000b703  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000b708  jnz     short loc_18000B713
0x18000b70a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r14b; bool wil::g_fBreakOnFailure
0x18000b711  jz      short loc_18000B725
0x18000b713  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000b71a  test    rax, rax
0x18000b71d  jz      short loc_18000B725
0x18000b71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b724  nop
0x18000b725  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000b72a  jz      short loc_18000B737
0x18000b72c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000b731  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000b737  test    dil, dil
0x18000b73a  jz      short loc_18000B754
0x18000b73c  lea     rdx, [rbp+13F0h+OutputString]
0x18000b743  lea     rcx, [rsp+14F0h+var_14D0]
0x18000b748  mov     rax, cs:g_pfnThrowPlatformException
0x18000b74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b754  test    esi, esi
0x18000b756  jz      short loc_18000B75D
0x18000b758  call    ?RethrowCaughtException@wil@@YAXXZ; wil::RethrowCaughtException(void)
0x18000b75d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000b762  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000b767  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000b76c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
