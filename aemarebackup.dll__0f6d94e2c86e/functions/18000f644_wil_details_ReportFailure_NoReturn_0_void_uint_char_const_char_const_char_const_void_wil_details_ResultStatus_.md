# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000f644`
- end: `0x18000f909`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000f524`

## callees

- `0x180005914`
- `0x180009f84`
- `0x18000ba60`
- `0x18000da68`
- `0x18000e370`
- `0x18000e53c`
- `0x18000f644`
- `0x1800e67d0`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f705`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f705`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f801`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f801`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f89d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f89d`

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
0x18000f644  mov     [rsp-8+arg_18], rbx
0x18000f649  push    rbp
0x18000f64a  push    rsi
0x18000f64b  push    rdi
0x18000f64c  push    r12
0x18000f64e  push    r13
0x18000f650  push    r14
0x18000f652  push    r15
0x18000f654  lea     rbp, [rsp-13C0h]
0x18000f65c  mov     eax, 14C0h
0x18000f661  call    _alloca_probe
0x18000f666  sub     rsp, rax
0x18000f669  mov     r14, r8
0x18000f66c  mov     esi, edx
0x18000f66e  mov     rbx, rcx
0x18000f671  mov     r15, [rbp+13F0h+arg_28]
0x18000f678  xor     r13d, r13d
0x18000f67b  cmp     cs:g_pfnThrowPlatformException, r13
0x18000f682  setnz   dil
0x18000f686  xor     edx, edx; Val
0x18000f688  mov     r8d, 98h; Size
0x18000f68e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000f693  call    memset_0
0x18000f698  nop
0x18000f699  mov     [rbp+13F0h+OutputString], r13w
0x18000f6a1  mov     [rbp+13F0h+var_1430], r13b
0x18000f6a5  mov     rdx, [rbp+13F0h+arg_30]; int
0x18000f6ac  mov     ecx, [rdx]; this
0x18000f6ae  mov     [rsp+14F0h+var_14C8], ecx
0x18000f6b2  mov     eax, [rdx+4]
0x18000f6b5  mov     [rsp+14F0h+var_14C4], eax
0x18000f6b9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000f6be  mov     r12d, eax
0x18000f6c1  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000f6c6  mov     ecx, r13d
0x18000f6c9  lea     eax, [r13+8]
0x18000f6cd  cmp     dword ptr [rdx+8], 1
0x18000f6d1  cmovz   ecx, eax
0x18000f6d4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000f6d8  lea     ecx, [rax-7]
0x18000f6db  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000f6e3  inc     ecx
0x18000f6e5  mov     [rsp+14F0h+var_14C0], ecx
0x18000f6e9  mov     rcx, [rbp+13F0h+arg_38]
0x18000f6f0  test    rcx, rcx
0x18000f6f3  jz      short loc_18000F700
0x18000f6f5  cmp     [rcx], r13w
0x18000f6f9  mov     [rsp+14F0h+var_14B8], rcx
0x18000f6fe  jnz     short loc_18000F705
0x18000f700  mov     [rsp+14F0h+var_14B8], r13
0x18000f705  call    cs:__imp_GetCurrentThreadId
0x18000f70b  mov     [rsp+14F0h+var_14B0], eax
0x18000f70f  mov     [rsp+14F0h+var_1498], r14
0x18000f714  mov     [rsp+14F0h+var_1490], esi
0x18000f718  mov     [rsp+14F0h+var_148C], r12d
0x18000f71d  mov     [rsp+14F0h+var_14A8], r13
0x18000f722  mov     [rsp+14F0h+var_14A0], r13
0x18000f727  mov     [rbp+13F0h+var_1448], r15
0x18000f72b  mov     [rbp+13F0h+var_1440], rbx
0x18000f72f  mov     [rsp+14F0h+var_1488], r13
0x18000f734  xorps   xmm0, xmm0
0x18000f737  xor     eax, eax
0x18000f739  movups  [rbp+13F0h+var_1468], xmm0
0x18000f73d  mov     [rbp+13F0h+var_1458], rax
0x18000f741  xorps   xmm1, xmm1
0x18000f744  movups  [rsp+14F0h+var_1480], xmm1
0x18000f749  mov     [rbp+13F0h+var_1470], rax
0x18000f74d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000f754  test    rax, rax
0x18000f757  jz      short loc_18000F764
0x18000f759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f75e  mov     [rbp+13F0h+var_1450], rax
0x18000f762  jmp     short loc_18000F768
0x18000f764  mov     [rbp+13F0h+var_1450], r13
0x18000f768  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000f76f  test    rax, rax
0x18000f772  jz      short loc_18000F77E
0x18000f774  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f77e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000f785  test    rax, rax
0x18000f788  jz      short loc_18000F79E
0x18000f78a  mov     r8d, 400h
0x18000f790  lea     rdx, [rbp+13F0h+var_1430]
0x18000f794  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f79e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f7a5  test    rax, rax
0x18000f7a8  jz      short loc_18000F7B4
0x18000f7aa  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f7af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7b4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f7bb  test    rax, rax
0x18000f7be  jz      short loc_18000F7D6
0x18000f7c0  test    dil, dil
0x18000f7c3  jnz     short loc_18000F7D6
0x18000f7c5  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000f7ca  jnz     short loc_18000F7D6
0x18000f7cc  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7d6  cmp     [rsp+14F0h+var_14C8], r13d
0x18000f7db  jl      short loc_18000F7E3
0x18000f7dd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000f7e3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000f7ea  jnz     short loc_18000F80B
0x18000f7ec  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000f7f3  test    rax, rax
0x18000f7f6  jz      short loc_18000F801
0x18000f7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7fd  test    al, al
0x18000f7ff  jmp     short loc_18000F809
0x18000f801  call    cs:__imp_IsDebuggerPresent
0x18000f807  test    eax, eax
0x18000f809  jz      short loc_18000F814
0x18000f80b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000f810  mov     bl, 1
0x18000f812  jz      short loc_18000F817
0x18000f814  mov     bl, r13b
0x18000f817  test    dil, dil
0x18000f81a  jnz     short loc_18000F846
0x18000f81c  test    bl, bl
0x18000f81e  jnz     short loc_18000F846
0x18000f820  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f827  test    rax, rax
0x18000f82a  jz      short loc_18000F8A3
0x18000f82c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000f833  jnz     short loc_18000F8A3
0x18000f835  xor     r8d, r8d
0x18000f838  xor     edx, edx
0x18000f83a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f844  jmp     short loc_18000F8A3
0x18000f846  mov     esi, 800h
0x18000f84b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f852  test    rax, rax
0x18000f855  jz      short loc_18000F874
0x18000f857  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000f85e  jnz     short loc_18000F874
0x18000f860  mov     r8d, esi
0x18000f863  lea     rdx, [rbp+13F0h+OutputString]
0x18000f86a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f86f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f874  cmp     [rbp+13F0h+OutputString], r13w
0x18000f87c  jnz     short loc_18000F892
0x18000f87e  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000f883  mov     rdx, rsi; unsigned __int16 *
0x18000f886  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000f88d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000f892  test    bl, bl
0x18000f894  jz      short loc_18000F8A3
0x18000f896  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000f89d  call    cs:__imp_OutputDebugStringW
0x18000f8a3  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000f8a8  jnz     short loc_18000F8B3
0x18000f8aa  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000f8b1  jz      short loc_18000F8C5
0x18000f8b3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000f8ba  test    rax, rax
0x18000f8bd  jz      short loc_18000F8C5
0x18000f8bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8c4  nop
0x18000f8c5  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000f8ca  jz      short loc_18000F8D7
0x18000f8cc  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000f8d1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000f8d7  test    dil, dil
0x18000f8da  jz      short loc_18000F8F4
0x18000f8dc  lea     rdx, [rbp+13F0h+OutputString]
0x18000f8e3  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f8e8  mov     rax, cs:g_pfnThrowPlatformException
0x18000f8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8f4  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000f8f9  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000f8fe  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000f903  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
