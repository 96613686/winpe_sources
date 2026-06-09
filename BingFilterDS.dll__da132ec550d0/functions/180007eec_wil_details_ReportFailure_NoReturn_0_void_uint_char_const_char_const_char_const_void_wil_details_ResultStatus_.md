# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180007eec`
- end: `0x180008198`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180007b3c`

## callees

- `0x180004994`
- `0x180005b40`
- `0x180006bd4`
- `0x180006f10`
- `0x1800070e4`
- `0x180007eec`
- `0x18000c4f2`
- `0x18000c5f0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f95`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008090`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008090`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000812c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000812c`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x180007eec  mov     [rsp-8+arg_18], rbx
0x180007ef1  push    rbp
0x180007ef2  push    rsi
0x180007ef3  push    rdi
0x180007ef4  push    r12
0x180007ef6  push    r13
0x180007ef8  push    r14
0x180007efa  push    r15
0x180007efc  lea     rbp, [rsp-13C0h]
0x180007f04  mov     eax, 14C0h
0x180007f09  call    _alloca_probe
0x180007f0e  sub     rsp, rax
0x180007f11  mov     r14, r8
0x180007f14  mov     esi, edx
0x180007f16  mov     r15, rcx
0x180007f19  mov     rdi, [rbp+13F0h+arg_28]
0x180007f20  xor     r13d, r13d
0x180007f23  cmp     cs:g_pfnThrowPlatformException, r13
0x180007f2a  setnz   r12b
0x180007f2e  xor     edx, edx; Val
0x180007f30  mov     r8d, 98h; Size
0x180007f36  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180007f3b  call    memset_0
0x180007f40  nop
0x180007f41  mov     [rbp+13F0h+OutputString], r13w
0x180007f49  mov     [rbp+13F0h+var_1430], r13b
0x180007f4d  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180007f54  mov     ecx, [rdx]; this
0x180007f56  mov     [rsp+14F0h+var_14C8], ecx
0x180007f5a  mov     eax, [rdx+4]
0x180007f5d  mov     [rsp+14F0h+var_14C4], eax
0x180007f61  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007f66  mov     ebx, eax
0x180007f68  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180007f6d  mov     ecx, r13d
0x180007f70  lea     eax, [r13+8]
0x180007f74  cmp     dword ptr [rdx+8], 1
0x180007f78  cmovz   ecx, eax
0x180007f7b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007f7f  lea     ecx, [rax-7]
0x180007f82  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007f8a  inc     ecx
0x180007f8c  mov     [rsp+14F0h+var_14C0], ecx
0x180007f90  mov     [rsp+14F0h+var_14B8], r13
0x180007f95  call    cs:__imp_GetCurrentThreadId
0x180007f9b  mov     [rsp+14F0h+var_14B0], eax
0x180007f9f  mov     [rsp+14F0h+var_1498], r14
0x180007fa4  mov     [rsp+14F0h+var_1490], esi
0x180007fa8  mov     [rsp+14F0h+var_148C], ebx
0x180007fac  mov     [rsp+14F0h+var_14A8], r13
0x180007fb1  mov     [rsp+14F0h+var_14A0], r13
0x180007fb6  mov     [rbp+13F0h+var_1448], rdi
0x180007fba  mov     [rbp+13F0h+var_1440], r15
0x180007fbe  mov     [rsp+14F0h+var_1488], r13
0x180007fc3  xorps   xmm0, xmm0
0x180007fc6  xor     eax, eax
0x180007fc8  movups  [rbp+13F0h+var_1468], xmm0
0x180007fcc  mov     [rbp+13F0h+var_1458], rax
0x180007fd0  xorps   xmm1, xmm1
0x180007fd3  movups  [rsp+14F0h+var_1480], xmm1
0x180007fd8  mov     [rbp+13F0h+var_1470], rax
0x180007fdc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007fe3  test    rax, rax
0x180007fe6  jz      short loc_180007FF3
0x180007fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fed  mov     [rbp+13F0h+var_1450], rax
0x180007ff1  jmp     short loc_180007FF7
0x180007ff3  mov     [rbp+13F0h+var_1450], r13
0x180007ff7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007ffe  test    rax, rax
0x180008001  jz      short loc_18000800D
0x180008003  lea     rcx, [rsp+14F0h+var_14D0]
0x180008008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000800d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008014  test    rax, rax
0x180008017  jz      short loc_18000802D
0x180008019  mov     r8d, 400h
0x18000801f  lea     rdx, [rbp+13F0h+var_1430]
0x180008023  lea     rcx, [rsp+14F0h+var_14D0]
0x180008028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000802d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008034  test    rax, rax
0x180008037  jz      short loc_180008043
0x180008039  lea     rcx, [rsp+14F0h+var_14D0]
0x18000803e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008043  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000804a  test    rax, rax
0x18000804d  jz      short loc_180008065
0x18000804f  test    r12b, r12b
0x180008052  jnz     short loc_180008065
0x180008054  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180008059  jnz     short loc_180008065
0x18000805b  lea     rcx, [rsp+14F0h+var_14D0]
0x180008060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008065  cmp     [rsp+14F0h+var_14C8], r13d
0x18000806a  jl      short loc_180008072
0x18000806c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180008072  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180008079  jnz     short loc_18000809A
0x18000807b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008082  test    rax, rax
0x180008085  jz      short loc_180008090
0x180008087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000808c  test    al, al
0x18000808e  jmp     short loc_180008098
0x180008090  call    cs:__imp_IsDebuggerPresent
0x180008096  test    eax, eax
0x180008098  jz      short loc_1800080A3
0x18000809a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000809f  mov     bl, 1
0x1800080a1  jz      short loc_1800080A6
0x1800080a3  mov     bl, r13b
0x1800080a6  test    r12b, r12b
0x1800080a9  jnz     short loc_1800080D5
0x1800080ab  test    bl, bl
0x1800080ad  jnz     short loc_1800080D5
0x1800080af  mov     rax, cs:g_pfnResultLoggingCallback
0x1800080b6  test    rax, rax
0x1800080b9  jz      short loc_180008132
0x1800080bb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800080c2  jnz     short loc_180008132
0x1800080c4  xor     r8d, r8d
0x1800080c7  xor     edx, edx
0x1800080c9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800080ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080d3  jmp     short loc_180008132
0x1800080d5  mov     edi, 800h
0x1800080da  mov     rax, cs:g_pfnResultLoggingCallback
0x1800080e1  test    rax, rax
0x1800080e4  jz      short loc_180008103
0x1800080e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800080ed  jnz     short loc_180008103
0x1800080ef  mov     r8d, edi
0x1800080f2  lea     rdx, [rbp+13F0h+OutputString]
0x1800080f9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800080fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008103  cmp     [rbp+13F0h+OutputString], r13w
0x18000810b  jnz     short loc_180008121
0x18000810d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180008112  mov     rdx, rdi; unsigned __int16 *
0x180008115  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000811c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008121  test    bl, bl
0x180008123  jz      short loc_180008132
0x180008125  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000812c  call    cs:__imp_OutputDebugStringW
0x180008132  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180008137  jnz     short loc_180008142
0x180008139  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180008140  jz      short loc_180008154
0x180008142  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008149  test    rax, rax
0x18000814c  jz      short loc_180008154
0x18000814e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008153  nop
0x180008154  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180008159  jz      short loc_180008166
0x18000815b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008160  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180008166  test    r12b, r12b
0x180008169  jz      short loc_180008183
0x18000816b  lea     rdx, [rbp+13F0h+OutputString]
0x180008172  lea     rcx, [rsp+14F0h+var_14D0]
0x180008177  mov     rax, cs:g_pfnThrowPlatformException
0x18000817e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008183  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008188  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000818d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180008192  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
