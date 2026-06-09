# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003214`
- end: `0x1800034a1`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002ed8`

## callees

- `0x180001ed0`
- `0x180002878`
- `0x180003214`
- `0x1800064b4`
- `0x180008228`
- `0x18000a678`
- `0x18000a884`
- `0x180010010`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800032c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800032c2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003440`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003440`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800033b6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800033b6`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180003214  push    rbp
0x180003216  push    rbx
0x180003217  push    rsi
0x180003218  push    rdi
0x180003219  push    r12
0x18000321b  push    r14
0x18000321d  push    r15
0x18000321f  lea     rbp, [rsp-13D0h]
0x180003227  mov     eax, 14D0h
0x18000322c  call    _alloca_probe
0x180003231  sub     rsp, rax
0x180003234  mov     rax, cs:__security_cookie
0x18000323b  xor     rax, rsp
0x18000323e  mov     [rbp+1400h+var_40], rax
0x180003245  mov     r14, r8
0x180003248  mov     esi, edx
0x18000324a  mov     r15, rcx
0x18000324d  mov     rdi, [rbp+1400h+arg_28]
0x180003254  xor     edx, edx; Val
0x180003256  mov     r8d, 98h; Size
0x18000325c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003261  call    memset_0
0x180003266  nop
0x180003267  xor     r12d, r12d
0x18000326a  mov     [rbp+1400h+OutputString], r12w
0x180003272  mov     [rbp+1400h+var_1440], r12b
0x180003276  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000327d  mov     ecx, [rdx]; this
0x18000327f  mov     [rsp+1500h+var_14D8], ecx
0x180003283  mov     eax, [rdx+4]
0x180003286  mov     [rsp+1500h+var_14D4], eax
0x18000328a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000328f  mov     ebx, eax
0x180003291  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003299  mov     ecx, r12d
0x18000329c  lea     eax, [r12+8]
0x1800032a1  cmp     dword ptr [rdx+8], 1
0x1800032a5  cmovz   ecx, eax
0x1800032a8  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800032ac  lea     ecx, [rax-7]
0x1800032af  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800032b7  inc     ecx
0x1800032b9  mov     [rsp+1500h+var_14D0], ecx
0x1800032bd  mov     [rsp+1500h+var_14C8], r12
0x1800032c2  call    cs:__imp_GetCurrentThreadId
0x1800032c8  mov     [rsp+1500h+var_14C0], eax
0x1800032cc  mov     [rsp+1500h+var_14A8], r14
0x1800032d1  mov     [rsp+1500h+var_14A0], esi
0x1800032d5  mov     [rsp+1500h+var_149C], ebx
0x1800032d9  mov     [rsp+1500h+var_14B8], r12
0x1800032de  mov     [rsp+1500h+var_14B0], r12
0x1800032e3  mov     [rbp+1400h+var_1458], rdi
0x1800032e7  mov     [rbp+1400h+var_1450], r15
0x1800032eb  mov     [rsp+1500h+var_1498], r12
0x1800032f0  xorps   xmm0, xmm0
0x1800032f3  xor     eax, eax
0x1800032f5  movups  [rbp+1400h+var_1478], xmm0
0x1800032f9  mov     [rbp+1400h+var_1468], rax
0x1800032fd  xorps   xmm1, xmm1
0x180003300  movups  [rsp+1500h+var_1490], xmm1
0x180003305  mov     [rbp+1400h+var_1480], rax
0x180003309  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003310  test    rax, rax
0x180003313  jz      short loc_180003320
0x180003315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000331a  mov     [rbp+1400h+var_1460], rax
0x18000331e  jmp     short loc_180003324
0x180003320  mov     [rbp+1400h+var_1460], r12
0x180003324  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000332b  test    rax, rax
0x18000332e  jz      short loc_18000333A
0x180003330  lea     rcx, [rsp+1500h+var_14E0]
0x180003335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000333a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003341  test    rax, rax
0x180003344  jz      short loc_18000335A
0x180003346  mov     r8d, 400h
0x18000334c  lea     rdx, [rbp+1400h+var_1440]
0x180003350  lea     rcx, [rsp+1500h+var_14E0]
0x180003355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000335a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003361  test    rax, rax
0x180003364  jz      short loc_180003370
0x180003366  lea     rcx, [rsp+1500h+var_14E0]
0x18000336b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003370  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003377  test    rax, rax
0x18000337a  jz      short loc_18000338D
0x18000337c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003381  jnz     short loc_18000338D
0x180003383  lea     rcx, [rsp+1500h+var_14E0]
0x180003388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000338d  cmp     [rsp+1500h+var_14D8], r12d
0x180003392  jge     loc_18000349B
0x180003398  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000339f  jnz     short loc_1800033C0
0x1800033a1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800033a8  test    rax, rax
0x1800033ab  jz      short loc_1800033B6
0x1800033ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033b2  test    al, al
0x1800033b4  jmp     short loc_1800033BE
0x1800033b6  call    cs:__imp_IsDebuggerPresent
0x1800033bc  test    eax, eax
0x1800033be  jz      short loc_1800033C7
0x1800033c0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800033c5  jz      short loc_1800033ED
0x1800033c7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800033ce  test    rax, rax
0x1800033d1  jz      short loc_180003446
0x1800033d3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800033da  jnz     short loc_180003446
0x1800033dc  xor     r8d, r8d
0x1800033df  xor     edx, edx
0x1800033e1  lea     rcx, [rsp+1500h+var_14E0]
0x1800033e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033eb  jmp     short loc_180003446
0x1800033ed  mov     ebx, 800h
0x1800033f2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800033f9  test    rax, rax
0x1800033fc  jz      short loc_18000341B
0x1800033fe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003405  jnz     short loc_18000341B
0x180003407  mov     r8d, ebx
0x18000340a  lea     rdx, [rbp+1400h+OutputString]
0x180003411  lea     rcx, [rsp+1500h+var_14E0]
0x180003416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000341b  cmp     [rbp+1400h+OutputString], r12w
0x180003423  jnz     short loc_180003439
0x180003425  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000342a  mov     rdx, rbx; unsigned __int16 *
0x18000342d  lea     rcx, [rbp+1400h+OutputString]; this
0x180003434  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003439  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003440  call    cs:__imp_OutputDebugStringW
0x180003446  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000344b  jnz     short loc_180003456
0x18000344d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003454  jz      short loc_180003468
0x180003456  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000345d  test    rax, rax
0x180003460  jz      short loc_180003468
0x180003462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003467  nop
0x180003468  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000346d  jnz     short loc_180003490
0x18000346f  mov     rcx, [rbp+1400h+var_40]
0x180003476  xor     rcx, rsp; StackCookie
0x180003479  call    __security_check_cookie
0x18000347e  add     rsp, 14D0h
0x180003485  pop     r15
0x180003487  pop     r14
0x180003489  pop     r12
0x18000348b  pop     rdi
0x18000348c  pop     rsi
0x18000348d  pop     rbx
0x18000348e  pop     rbp
0x18000348f  retn
0x180003490  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003495  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000349b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
