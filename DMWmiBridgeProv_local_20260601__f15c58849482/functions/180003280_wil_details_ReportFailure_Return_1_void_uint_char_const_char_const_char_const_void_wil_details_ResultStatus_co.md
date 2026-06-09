# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003280`
- end: `0x180003529`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002f48`

## callees

- `0x180003280`
- `0x1800042c4`
- `0x180008f14`
- `0x180009bd0`
- `0x180009df4`
- `0x18024ccee`
- `0x18024cd20`
- `0x18024cdb0`
- `0x18024f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000332b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000332b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800034bc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800034bc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000342c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000342c`

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
0x180003280  mov     [rsp-8+arg_10], rbx
0x180003285  push    rbp
0x180003286  push    rsi
0x180003287  push    rdi
0x180003288  push    r14
0x18000328a  push    r15
0x18000328c  lea     rbp, [rsp-13D0h]
0x180003294  mov     eax, 14D0h
0x180003299  call    _alloca_probe
0x18000329e  sub     rsp, rax
0x1800032a1  mov     rax, cs:__security_cookie
0x1800032a8  xor     rax, rsp
0x1800032ab  mov     [rbp+13F0h+var_30], rax
0x1800032b2  mov     esi, edx
0x1800032b4  mov     r14, rcx
0x1800032b7  mov     rdi, [rbp+13F0h+arg_28]
0x1800032be  xor     edx, edx; Val
0x1800032c0  mov     r8d, 98h; Size
0x1800032c6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800032cb  call    memset_0
0x1800032d0  nop
0x1800032d1  xor     r15d, r15d
0x1800032d4  mov     [rbp+13F0h+OutputString], r15w
0x1800032dc  mov     [rbp+13F0h+var_1430], r15b
0x1800032e0  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800032e7  mov     ecx, [rdx]; this
0x1800032e9  mov     [rsp+14F0h+var_14C8], ecx
0x1800032ed  mov     eax, [rdx+4]
0x1800032f0  mov     [rsp+14F0h+var_14C4], eax
0x1800032f4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800032f9  mov     ebx, eax
0x1800032fb  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180003303  mov     ecx, r15d
0x180003306  lea     eax, [r15+8]
0x18000330a  cmp     dword ptr [rdx+8], 1
0x18000330e  cmovz   ecx, eax
0x180003311  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180003315  lea     ecx, [rax-7]
0x180003318  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003320  inc     ecx
0x180003322  mov     [rsp+14F0h+var_14C0], ecx
0x180003326  mov     [rsp+14F0h+var_14B8], r15
0x18000332b  call    cs:__imp_GetCurrentThreadId
0x180003332  nop     dword ptr [rax+rax+00h]
0x180003337  mov     [rsp+14F0h+var_14B0], eax
0x18000333b  lea     rax, aWil; "wil"
0x180003342  mov     [rsp+14F0h+var_1498], rax
0x180003347  mov     [rsp+14F0h+var_1490], esi
0x18000334b  mov     [rsp+14F0h+var_148C], ebx
0x18000334f  mov     [rsp+14F0h+var_14A8], r15
0x180003354  mov     [rsp+14F0h+var_14A0], r15
0x180003359  mov     [rbp+13F0h+var_1448], rdi
0x18000335d  mov     [rbp+13F0h+var_1440], r14
0x180003361  mov     [rsp+14F0h+var_1488], r15
0x180003366  xorps   xmm0, xmm0
0x180003369  xor     eax, eax
0x18000336b  movups  [rbp+13F0h+var_1468], xmm0
0x18000336f  mov     [rbp+13F0h+var_1458], rax
0x180003373  xorps   xmm1, xmm1
0x180003376  movups  [rsp+14F0h+var_1480], xmm1
0x18000337b  mov     [rbp+13F0h+var_1470], rax
0x18000337f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003386  test    rax, rax
0x180003389  jz      short loc_180003396
0x18000338b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003390  mov     [rbp+13F0h+var_1450], rax
0x180003394  jmp     short loc_18000339A
0x180003396  mov     [rbp+13F0h+var_1450], r15
0x18000339a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800033a1  test    rax, rax
0x1800033a4  jz      short loc_1800033B0
0x1800033a6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033b0  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800033b7  test    rax, rax
0x1800033ba  jz      short loc_1800033D0
0x1800033bc  mov     r8d, 400h
0x1800033c2  lea     rdx, [rbp+13F0h+var_1430]
0x1800033c6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033d0  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800033d7  test    rax, rax
0x1800033da  jz      short loc_1800033E6
0x1800033dc  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033e6  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800033ed  test    rax, rax
0x1800033f0  jz      short loc_180003403
0x1800033f2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800033f7  jnz     short loc_180003403
0x1800033f9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800033fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003403  cmp     [rsp+14F0h+var_14C8], r15d
0x180003408  jge     loc_180003523
0x18000340e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180003415  jnz     short loc_18000343C
0x180003417  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000341e  test    rax, rax
0x180003421  jz      short loc_18000342C
0x180003423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003428  test    al, al
0x18000342a  jmp     short loc_18000343A
0x18000342c  call    cs:__imp_IsDebuggerPresent
0x180003433  nop     dword ptr [rax+rax+00h]
0x180003438  test    eax, eax
0x18000343a  jz      short loc_180003443
0x18000343c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003441  jz      short loc_180003469
0x180003443  mov     rax, cs:g_pfnResultLoggingCallback
0x18000344a  test    rax, rax
0x18000344d  jz      short loc_1800034C8
0x18000344f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003456  jnz     short loc_1800034C8
0x180003458  xor     r8d, r8d
0x18000345b  xor     edx, edx
0x18000345d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003467  jmp     short loc_1800034C8
0x180003469  mov     ebx, 800h
0x18000346e  mov     rax, cs:g_pfnResultLoggingCallback
0x180003475  test    rax, rax
0x180003478  jz      short loc_180003497
0x18000347a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003481  jnz     short loc_180003497
0x180003483  mov     r8d, ebx
0x180003486  lea     rdx, [rbp+13F0h+OutputString]
0x18000348d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003497  cmp     [rbp+13F0h+OutputString], r15w
0x18000349f  jnz     short loc_1800034B5
0x1800034a1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800034a6  mov     rdx, rbx; unsigned __int16 *
0x1800034a9  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800034b0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800034b5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800034bc  call    cs:__imp_OutputDebugStringW
0x1800034c3  nop     dword ptr [rax+rax+00h]
0x1800034c8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800034cd  jnz     short loc_1800034D8
0x1800034cf  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800034d6  jz      short loc_1800034EA
0x1800034d8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800034df  test    rax, rax
0x1800034e2  jz      short loc_1800034EA
0x1800034e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034e9  nop
0x1800034ea  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800034ef  jnz     short loc_180003518
0x1800034f1  mov     rcx, [rbp+13F0h+var_30]
0x1800034f8  xor     rcx, rsp; StackCookie
0x1800034fb  call    __security_check_cookie
0x180003500  mov     rbx, [rsp+14F0h+arg_10]
0x180003508  add     rsp, 14D0h
0x18000350f  pop     r15
0x180003511  pop     r14
0x180003513  pop     rdi
0x180003514  pop     rsi
0x180003515  pop     rbp
0x180003516  retn
0x180003518  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000351d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003523  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
