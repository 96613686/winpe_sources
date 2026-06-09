# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800031f8`
- end: `0x18000348e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002ec0`

## callees

- `0x1800031f8`
- `0x180004174`
- `0x180008b30`
- `0x180009788`
- `0x1800099e0`
- `0x18024d12e`
- `0x18024d160`
- `0x18024d1f0`
- `0x18024f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800032a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800032a3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003428`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003428`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000339e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000339e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x1800031f8  mov     [rsp-8+arg_10], rbx
0x1800031fd  push    rbp
0x1800031fe  push    rsi
0x1800031ff  push    rdi
0x180003200  push    r14
0x180003202  push    r15
0x180003204  lea     rbp, [rsp-13D0h]
0x18000320c  mov     eax, 14D0h
0x180003211  call    _alloca_probe
0x180003216  sub     rsp, rax
0x180003219  mov     rax, cs:__security_cookie
0x180003220  xor     rax, rsp
0x180003223  mov     [rbp+13F0h+var_30], rax
0x18000322a  mov     esi, edx
0x18000322c  mov     r14, rcx
0x18000322f  mov     rdi, [rbp+13F0h+arg_28]
0x180003236  xor     edx, edx; Val
0x180003238  mov     r8d, 98h; Size
0x18000323e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003243  call    memset_0
0x180003248  nop
0x180003249  xor     r15d, r15d
0x18000324c  mov     [rbp+13F0h+OutputString], r15w
0x180003254  mov     [rbp+13F0h+var_1430], r15b
0x180003258  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000325f  mov     ecx, [rdx]; this
0x180003261  mov     [rsp+14F0h+var_14C8], ecx
0x180003265  mov     eax, [rdx+4]
0x180003268  mov     [rsp+14F0h+var_14C4], eax
0x18000326c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003271  mov     ebx, eax
0x180003273  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000327b  mov     ecx, r15d
0x18000327e  lea     eax, [r15+8]
0x180003282  cmp     dword ptr [rdx+8], 1
0x180003286  cmovz   ecx, eax
0x180003289  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000328d  lea     ecx, [rax-7]
0x180003290  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003298  inc     ecx
0x18000329a  mov     [rsp+14F0h+var_14C0], ecx
0x18000329e  mov     [rsp+14F0h+var_14B8], r15
0x1800032a3  call    cs:__imp_GetCurrentThreadId
0x1800032a9  mov     [rsp+14F0h+var_14B0], eax
0x1800032ad  lea     rax, aWil; "wil"
0x1800032b4  mov     [rsp+14F0h+var_1498], rax
0x1800032b9  mov     [rsp+14F0h+var_1490], esi
0x1800032bd  mov     [rsp+14F0h+var_148C], ebx
0x1800032c1  mov     [rsp+14F0h+var_14A8], r15
0x1800032c6  mov     [rsp+14F0h+var_14A0], r15
0x1800032cb  mov     [rbp+13F0h+var_1448], rdi
0x1800032cf  mov     [rbp+13F0h+var_1440], r14
0x1800032d3  mov     [rsp+14F0h+var_1488], r15
0x1800032d8  xorps   xmm0, xmm0
0x1800032db  xor     eax, eax
0x1800032dd  movups  [rbp+13F0h+var_1468], xmm0
0x1800032e1  mov     [rbp+13F0h+var_1458], rax
0x1800032e5  xorps   xmm1, xmm1
0x1800032e8  movups  [rsp+14F0h+var_1480], xmm1
0x1800032ed  mov     [rbp+13F0h+var_1470], rax
0x1800032f1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800032f8  test    rax, rax
0x1800032fb  jz      short loc_180003308
0x1800032fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003302  mov     [rbp+13F0h+var_1450], rax
0x180003306  jmp     short loc_18000330C
0x180003308  mov     [rbp+13F0h+var_1450], r15
0x18000330c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003313  test    rax, rax
0x180003316  jz      short loc_180003322
0x180003318  lea     rcx, [rsp+14F0h+var_14D0]
0x18000331d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003322  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003329  test    rax, rax
0x18000332c  jz      short loc_180003342
0x18000332e  mov     r8d, 400h
0x180003334  lea     rdx, [rbp+13F0h+var_1430]
0x180003338  lea     rcx, [rsp+14F0h+var_14D0]
0x18000333d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003342  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003349  test    rax, rax
0x18000334c  jz      short loc_180003358
0x18000334e  lea     rcx, [rsp+14F0h+var_14D0]
0x180003353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003358  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000335f  test    rax, rax
0x180003362  jz      short loc_180003375
0x180003364  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003369  jnz     short loc_180003375
0x18000336b  lea     rcx, [rsp+14F0h+var_14D0]
0x180003370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003375  cmp     [rsp+14F0h+var_14C8], r15d
0x18000337a  jge     loc_180003488
0x180003380  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180003387  jnz     short loc_1800033A8
0x180003389  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003390  test    rax, rax
0x180003393  jz      short loc_18000339E
0x180003395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000339a  test    al, al
0x18000339c  jmp     short loc_1800033A6
0x18000339e  call    cs:__imp_IsDebuggerPresent
0x1800033a4  test    eax, eax
0x1800033a6  jz      short loc_1800033AF
0x1800033a8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800033ad  jz      short loc_1800033D5
0x1800033af  mov     rax, cs:g_pfnResultLoggingCallback
0x1800033b6  test    rax, rax
0x1800033b9  jz      short loc_18000342E
0x1800033bb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800033c2  jnz     short loc_18000342E
0x1800033c4  xor     r8d, r8d
0x1800033c7  xor     edx, edx
0x1800033c9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033d3  jmp     short loc_18000342E
0x1800033d5  mov     ebx, 800h
0x1800033da  mov     rax, cs:g_pfnResultLoggingCallback
0x1800033e1  test    rax, rax
0x1800033e4  jz      short loc_180003403
0x1800033e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800033ed  jnz     short loc_180003403
0x1800033ef  mov     r8d, ebx
0x1800033f2  lea     rdx, [rbp+13F0h+OutputString]
0x1800033f9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003403  cmp     [rbp+13F0h+OutputString], r15w
0x18000340b  jnz     short loc_180003421
0x18000340d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003412  mov     rdx, rbx; unsigned __int16 *
0x180003415  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000341c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003421  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003428  call    cs:__imp_OutputDebugStringW
0x18000342e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003433  jnz     short loc_18000343E
0x180003435  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000343c  jz      short loc_180003450
0x18000343e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003445  test    rax, rax
0x180003448  jz      short loc_180003450
0x18000344a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000344f  nop
0x180003450  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003455  jnz     short loc_18000347D
0x180003457  mov     rcx, [rbp+13F0h+var_30]
0x18000345e  xor     rcx, rsp; StackCookie
0x180003461  call    __security_check_cookie
0x180003466  mov     rbx, [rsp+14F0h+arg_10]
0x18000346e  add     rsp, 14D0h
0x180003475  pop     r15
0x180003477  pop     r14
0x180003479  pop     rdi
0x18000347a  pop     rsi
0x18000347b  pop     rbp
0x18000347c  retn
0x18000347d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003482  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003488  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
