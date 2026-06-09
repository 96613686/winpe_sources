# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800073e4`
- end: `0x180007671`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800070a8`

## callees

- `0x180003c70`
- `0x180004754`
- `0x1800073e4`
- `0x180009564`
- `0x18000a940`
- `0x18000bf18`
- `0x18000c140`
- `0x180085620`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007492`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007492`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007610`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007610`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007586`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007586`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x1800073e4  push    rbp
0x1800073e6  push    rbx
0x1800073e7  push    rsi
0x1800073e8  push    rdi
0x1800073e9  push    r12
0x1800073eb  push    r14
0x1800073ed  push    r15
0x1800073ef  lea     rbp, [rsp-13D0h]
0x1800073f7  mov     eax, 14D0h
0x1800073fc  call    _alloca_probe
0x180007401  sub     rsp, rax
0x180007404  mov     rax, cs:__security_cookie
0x18000740b  xor     rax, rsp
0x18000740e  mov     [rbp+1400h+var_40], rax
0x180007415  mov     r14, r8
0x180007418  mov     esi, edx
0x18000741a  mov     r15, rcx
0x18000741d  mov     rdi, [rbp+1400h+arg_28]
0x180007424  xor     edx, edx; Val
0x180007426  mov     r8d, 98h; Size
0x18000742c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180007431  call    memset_0
0x180007436  nop
0x180007437  xor     r12d, r12d
0x18000743a  mov     [rbp+1400h+OutputString], r12w
0x180007442  mov     [rbp+1400h+var_1440], r12b
0x180007446  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000744d  mov     ecx, [rdx]; this
0x18000744f  mov     [rsp+1500h+var_14D8], ecx
0x180007453  mov     eax, [rdx+4]
0x180007456  mov     [rsp+1500h+var_14D4], eax
0x18000745a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000745f  mov     ebx, eax
0x180007461  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180007469  mov     ecx, r12d
0x18000746c  lea     eax, [r12+8]
0x180007471  cmp     dword ptr [rdx+8], 1
0x180007475  cmovz   ecx, eax
0x180007478  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000747c  lea     ecx, [rax-7]
0x18000747f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007487  inc     ecx
0x180007489  mov     [rsp+1500h+var_14D0], ecx
0x18000748d  mov     [rsp+1500h+var_14C8], r12
0x180007492  call    cs:__imp_GetCurrentThreadId
0x180007498  mov     [rsp+1500h+var_14C0], eax
0x18000749c  mov     [rsp+1500h+var_14A8], r14
0x1800074a1  mov     [rsp+1500h+var_14A0], esi
0x1800074a5  mov     [rsp+1500h+var_149C], ebx
0x1800074a9  mov     [rsp+1500h+var_14B8], r12
0x1800074ae  mov     [rsp+1500h+var_14B0], r12
0x1800074b3  mov     [rbp+1400h+var_1458], rdi
0x1800074b7  mov     [rbp+1400h+var_1450], r15
0x1800074bb  mov     [rsp+1500h+var_1498], r12
0x1800074c0  xorps   xmm0, xmm0
0x1800074c3  xor     eax, eax
0x1800074c5  movups  [rbp+1400h+var_1478], xmm0
0x1800074c9  mov     [rbp+1400h+var_1468], rax
0x1800074cd  xorps   xmm1, xmm1
0x1800074d0  movups  [rsp+1500h+var_1490], xmm1
0x1800074d5  mov     [rbp+1400h+var_1480], rax
0x1800074d9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800074e0  test    rax, rax
0x1800074e3  jz      short loc_1800074F0
0x1800074e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074ea  mov     [rbp+1400h+var_1460], rax
0x1800074ee  jmp     short loc_1800074F4
0x1800074f0  mov     [rbp+1400h+var_1460], r12
0x1800074f4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800074fb  test    rax, rax
0x1800074fe  jz      short loc_18000750A
0x180007500  lea     rcx, [rsp+1500h+var_14E0]
0x180007505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000750a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007511  test    rax, rax
0x180007514  jz      short loc_18000752A
0x180007516  mov     r8d, 400h
0x18000751c  lea     rdx, [rbp+1400h+var_1440]
0x180007520  lea     rcx, [rsp+1500h+var_14E0]
0x180007525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000752a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007531  test    rax, rax
0x180007534  jz      short loc_180007540
0x180007536  lea     rcx, [rsp+1500h+var_14E0]
0x18000753b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007540  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007547  test    rax, rax
0x18000754a  jz      short loc_18000755D
0x18000754c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180007551  jnz     short loc_18000755D
0x180007553  lea     rcx, [rsp+1500h+var_14E0]
0x180007558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000755d  cmp     [rsp+1500h+var_14D8], r12d
0x180007562  jge     loc_18000766B
0x180007568  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000756f  jnz     short loc_180007590
0x180007571  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007578  test    rax, rax
0x18000757b  jz      short loc_180007586
0x18000757d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007582  test    al, al
0x180007584  jmp     short loc_18000758E
0x180007586  call    cs:__imp_IsDebuggerPresent
0x18000758c  test    eax, eax
0x18000758e  jz      short loc_180007597
0x180007590  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180007595  jz      short loc_1800075BD
0x180007597  mov     rax, cs:g_pfnResultLoggingCallback
0x18000759e  test    rax, rax
0x1800075a1  jz      short loc_180007616
0x1800075a3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800075aa  jnz     short loc_180007616
0x1800075ac  xor     r8d, r8d
0x1800075af  xor     edx, edx
0x1800075b1  lea     rcx, [rsp+1500h+var_14E0]
0x1800075b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075bb  jmp     short loc_180007616
0x1800075bd  mov     ebx, 800h
0x1800075c2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800075c9  test    rax, rax
0x1800075cc  jz      short loc_1800075EB
0x1800075ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800075d5  jnz     short loc_1800075EB
0x1800075d7  mov     r8d, ebx
0x1800075da  lea     rdx, [rbp+1400h+OutputString]
0x1800075e1  lea     rcx, [rsp+1500h+var_14E0]
0x1800075e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075eb  cmp     [rbp+1400h+OutputString], r12w
0x1800075f3  jnz     short loc_180007609
0x1800075f5  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800075fa  mov     rdx, rbx; unsigned __int16 *
0x1800075fd  lea     rcx, [rbp+1400h+OutputString]; this
0x180007604  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007609  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180007610  call    cs:__imp_OutputDebugStringW
0x180007616  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000761b  jnz     short loc_180007626
0x18000761d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180007624  jz      short loc_180007638
0x180007626  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000762d  test    rax, rax
0x180007630  jz      short loc_180007638
0x180007632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007637  nop
0x180007638  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000763d  jnz     short loc_180007660
0x18000763f  mov     rcx, [rbp+1400h+var_40]
0x180007646  xor     rcx, rsp; StackCookie
0x180007649  call    __security_check_cookie
0x18000764e  add     rsp, 14D0h
0x180007655  pop     r15
0x180007657  pop     r14
0x180007659  pop     r12
0x18000765b  pop     rdi
0x18000765c  pop     rsi
0x18000765d  pop     rbx
0x18000765e  pop     rbp
0x18000765f  retn
0x180007660  lea     rcx, [rsp+1500h+var_14E0]; this
0x180007665  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000766b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
