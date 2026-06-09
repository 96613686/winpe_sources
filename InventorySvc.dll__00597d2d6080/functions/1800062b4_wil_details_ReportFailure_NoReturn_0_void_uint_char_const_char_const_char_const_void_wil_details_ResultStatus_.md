# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800062b4`
- end: `0x180006560`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005d78`

## callees

- `0x1800038b8`
- `0x1800062b4`
- `0x18000b994`
- `0x18000d9e8`
- `0x18000fbf8`
- `0x180010630`
- `0x1800108c4`
- `0x1800ce770`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000635d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000635d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006458`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006458`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800064f4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800064f4`

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
0x1800062b4  mov     [rsp-8+arg_18], rbx
0x1800062b9  push    rbp
0x1800062ba  push    rsi
0x1800062bb  push    rdi
0x1800062bc  push    r12
0x1800062be  push    r13
0x1800062c0  push    r14
0x1800062c2  push    r15
0x1800062c4  lea     rbp, [rsp-13C0h]
0x1800062cc  mov     eax, 14C0h
0x1800062d1  call    _alloca_probe
0x1800062d6  sub     rsp, rax
0x1800062d9  mov     r14, r8
0x1800062dc  mov     esi, edx
0x1800062de  mov     r15, rcx
0x1800062e1  mov     rdi, [rbp+13F0h+arg_28]
0x1800062e8  xor     r13d, r13d
0x1800062eb  cmp     cs:g_pfnThrowPlatformException, r13
0x1800062f2  setnz   r12b
0x1800062f6  xor     edx, edx; Val
0x1800062f8  mov     r8d, 98h; Size
0x1800062fe  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180006303  call    memset_0
0x180006308  nop
0x180006309  mov     [rbp+13F0h+OutputString], r13w
0x180006311  mov     [rbp+13F0h+var_1430], r13b
0x180006315  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000631c  mov     ecx, [rdx]; this
0x18000631e  mov     [rsp+14F0h+var_14C8], ecx
0x180006322  mov     eax, [rdx+4]
0x180006325  mov     [rsp+14F0h+var_14C4], eax
0x180006329  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000632e  mov     ebx, eax
0x180006330  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180006335  mov     ecx, r13d
0x180006338  lea     eax, [r13+8]
0x18000633c  cmp     dword ptr [rdx+8], 1
0x180006340  cmovz   ecx, eax
0x180006343  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180006347  lea     ecx, [rax-7]
0x18000634a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006352  inc     ecx
0x180006354  mov     [rsp+14F0h+var_14C0], ecx
0x180006358  mov     [rsp+14F0h+var_14B8], r13
0x18000635d  call    cs:__imp_GetCurrentThreadId
0x180006363  mov     [rsp+14F0h+var_14B0], eax
0x180006367  mov     [rsp+14F0h+var_1498], r14
0x18000636c  mov     [rsp+14F0h+var_1490], esi
0x180006370  mov     [rsp+14F0h+var_148C], ebx
0x180006374  mov     [rsp+14F0h+var_14A8], r13
0x180006379  mov     [rsp+14F0h+var_14A0], r13
0x18000637e  mov     [rbp+13F0h+var_1448], rdi
0x180006382  mov     [rbp+13F0h+var_1440], r15
0x180006386  mov     [rsp+14F0h+var_1488], r13
0x18000638b  xorps   xmm0, xmm0
0x18000638e  xor     eax, eax
0x180006390  movups  [rbp+13F0h+var_1468], xmm0
0x180006394  mov     [rbp+13F0h+var_1458], rax
0x180006398  xorps   xmm1, xmm1
0x18000639b  movups  [rsp+14F0h+var_1480], xmm1
0x1800063a0  mov     [rbp+13F0h+var_1470], rax
0x1800063a4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800063ab  test    rax, rax
0x1800063ae  jz      short loc_1800063BB
0x1800063b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063b5  mov     [rbp+13F0h+var_1450], rax
0x1800063b9  jmp     short loc_1800063BF
0x1800063bb  mov     [rbp+13F0h+var_1450], r13
0x1800063bf  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800063c6  test    rax, rax
0x1800063c9  jz      short loc_1800063D5
0x1800063cb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800063d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800063dc  test    rax, rax
0x1800063df  jz      short loc_1800063F5
0x1800063e1  mov     r8d, 400h
0x1800063e7  lea     rdx, [rbp+13F0h+var_1430]
0x1800063eb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800063f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063f5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800063fc  test    rax, rax
0x1800063ff  jz      short loc_18000640B
0x180006401  lea     rcx, [rsp+14F0h+var_14D0]
0x180006406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000640b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006412  test    rax, rax
0x180006415  jz      short loc_18000642D
0x180006417  test    r12b, r12b
0x18000641a  jnz     short loc_18000642D
0x18000641c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006421  jnz     short loc_18000642D
0x180006423  lea     rcx, [rsp+14F0h+var_14D0]
0x180006428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000642d  cmp     [rsp+14F0h+var_14C8], r13d
0x180006432  jl      short loc_18000643A
0x180006434  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000643a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180006441  jnz     short loc_180006462
0x180006443  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000644a  test    rax, rax
0x18000644d  jz      short loc_180006458
0x18000644f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006454  test    al, al
0x180006456  jmp     short loc_180006460
0x180006458  call    cs:__imp_IsDebuggerPresent
0x18000645e  test    eax, eax
0x180006460  jz      short loc_18000646B
0x180006462  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006467  mov     bl, 1
0x180006469  jz      short loc_18000646E
0x18000646b  mov     bl, r13b
0x18000646e  test    r12b, r12b
0x180006471  jnz     short loc_18000649D
0x180006473  test    bl, bl
0x180006475  jnz     short loc_18000649D
0x180006477  mov     rax, cs:g_pfnResultLoggingCallback
0x18000647e  test    rax, rax
0x180006481  jz      short loc_1800064FA
0x180006483  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000648a  jnz     short loc_1800064FA
0x18000648c  xor     r8d, r8d
0x18000648f  xor     edx, edx
0x180006491  lea     rcx, [rsp+14F0h+var_14D0]
0x180006496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000649b  jmp     short loc_1800064FA
0x18000649d  mov     edi, 800h
0x1800064a2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800064a9  test    rax, rax
0x1800064ac  jz      short loc_1800064CB
0x1800064ae  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800064b5  jnz     short loc_1800064CB
0x1800064b7  mov     r8d, edi
0x1800064ba  lea     rdx, [rbp+13F0h+OutputString]
0x1800064c1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800064c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064cb  cmp     [rbp+13F0h+OutputString], r13w
0x1800064d3  jnz     short loc_1800064E9
0x1800064d5  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800064da  mov     rdx, rdi; unsigned __int16 *
0x1800064dd  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800064e4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800064e9  test    bl, bl
0x1800064eb  jz      short loc_1800064FA
0x1800064ed  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800064f4  call    cs:__imp_OutputDebugStringW
0x1800064fa  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800064ff  jnz     short loc_18000650A
0x180006501  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180006508  jz      short loc_18000651C
0x18000650a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006511  test    rax, rax
0x180006514  jz      short loc_18000651C
0x180006516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000651b  nop
0x18000651c  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180006521  jz      short loc_18000652E
0x180006523  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006528  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000652e  test    r12b, r12b
0x180006531  jz      short loc_18000654B
0x180006533  lea     rdx, [rbp+13F0h+OutputString]
0x18000653a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000653f  mov     rax, cs:g_pfnThrowPlatformException
0x180006546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000654b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006550  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180006555  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000655a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
