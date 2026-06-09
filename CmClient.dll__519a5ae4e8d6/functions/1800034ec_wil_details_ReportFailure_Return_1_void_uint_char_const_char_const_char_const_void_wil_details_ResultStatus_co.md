# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800034ec`
- end: `0x180003779`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002f64`

## callees

- `0x180001550`
- `0x180002158`
- `0x1800034ec`
- `0x180004bd4`
- `0x180006380`
- `0x180006e90`
- `0x180006ffc`
- `0x18000eda0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000359a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000359a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003718`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003718`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000368e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000368e`

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
0x1800034ec  push    rbp
0x1800034ee  push    rbx
0x1800034ef  push    rsi
0x1800034f0  push    rdi
0x1800034f1  push    r12
0x1800034f3  push    r14
0x1800034f5  push    r15
0x1800034f7  lea     rbp, [rsp-13D0h]
0x1800034ff  mov     eax, 14D0h
0x180003504  call    _alloca_probe
0x180003509  sub     rsp, rax
0x18000350c  mov     rax, cs:__security_cookie
0x180003513  xor     rax, rsp
0x180003516  mov     [rbp+1400h+var_40], rax
0x18000351d  mov     r14, r8
0x180003520  mov     esi, edx
0x180003522  mov     r15, rcx
0x180003525  mov     rdi, [rbp+1400h+arg_28]
0x18000352c  xor     edx, edx; Val
0x18000352e  mov     r8d, 98h; Size
0x180003534  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003539  call    memset_0
0x18000353e  nop
0x18000353f  xor     r12d, r12d
0x180003542  mov     [rbp+1400h+OutputString], r12w
0x18000354a  mov     [rbp+1400h+var_1440], r12b
0x18000354e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180003555  mov     ecx, [rdx]; this
0x180003557  mov     [rsp+1500h+var_14D8], ecx
0x18000355b  mov     eax, [rdx+4]
0x18000355e  mov     [rsp+1500h+var_14D4], eax
0x180003562  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003567  mov     ebx, eax
0x180003569  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003571  mov     ecx, r12d
0x180003574  lea     eax, [r12+8]
0x180003579  cmp     dword ptr [rdx+8], 1
0x18000357d  cmovz   ecx, eax
0x180003580  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003584  lea     ecx, [rax-7]
0x180003587  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000358f  inc     ecx
0x180003591  mov     [rsp+1500h+var_14D0], ecx
0x180003595  mov     [rsp+1500h+var_14C8], r12
0x18000359a  call    cs:__imp_GetCurrentThreadId
0x1800035a0  mov     [rsp+1500h+var_14C0], eax
0x1800035a4  mov     [rsp+1500h+var_14A8], r14
0x1800035a9  mov     [rsp+1500h+var_14A0], esi
0x1800035ad  mov     [rsp+1500h+var_149C], ebx
0x1800035b1  mov     [rsp+1500h+var_14B8], r12
0x1800035b6  mov     [rsp+1500h+var_14B0], r12
0x1800035bb  mov     [rbp+1400h+var_1458], rdi
0x1800035bf  mov     [rbp+1400h+var_1450], r15
0x1800035c3  mov     [rsp+1500h+var_1498], r12
0x1800035c8  xorps   xmm0, xmm0
0x1800035cb  xor     eax, eax
0x1800035cd  movups  [rbp+1400h+var_1478], xmm0
0x1800035d1  mov     [rbp+1400h+var_1468], rax
0x1800035d5  xorps   xmm1, xmm1
0x1800035d8  movups  [rsp+1500h+var_1490], xmm1
0x1800035dd  mov     [rbp+1400h+var_1480], rax
0x1800035e1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800035e8  test    rax, rax
0x1800035eb  jz      short loc_1800035F8
0x1800035ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035f2  mov     [rbp+1400h+var_1460], rax
0x1800035f6  jmp     short loc_1800035FC
0x1800035f8  mov     [rbp+1400h+var_1460], r12
0x1800035fc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003603  test    rax, rax
0x180003606  jz      short loc_180003612
0x180003608  lea     rcx, [rsp+1500h+var_14E0]
0x18000360d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003612  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003619  test    rax, rax
0x18000361c  jz      short loc_180003632
0x18000361e  mov     r8d, 400h
0x180003624  lea     rdx, [rbp+1400h+var_1440]
0x180003628  lea     rcx, [rsp+1500h+var_14E0]
0x18000362d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003632  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003639  test    rax, rax
0x18000363c  jz      short loc_180003648
0x18000363e  lea     rcx, [rsp+1500h+var_14E0]
0x180003643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003648  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000364f  test    rax, rax
0x180003652  jz      short loc_180003665
0x180003654  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003659  jnz     short loc_180003665
0x18000365b  lea     rcx, [rsp+1500h+var_14E0]
0x180003660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003665  cmp     [rsp+1500h+var_14D8], r12d
0x18000366a  jge     loc_180003773
0x180003670  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003677  jnz     short loc_180003698
0x180003679  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003680  test    rax, rax
0x180003683  jz      short loc_18000368E
0x180003685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000368a  test    al, al
0x18000368c  jmp     short loc_180003696
0x18000368e  call    cs:__imp_IsDebuggerPresent
0x180003694  test    eax, eax
0x180003696  jz      short loc_18000369F
0x180003698  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000369d  jz      short loc_1800036C5
0x18000369f  mov     rax, cs:g_pfnResultLoggingCallback
0x1800036a6  test    rax, rax
0x1800036a9  jz      short loc_18000371E
0x1800036ab  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800036b2  jnz     short loc_18000371E
0x1800036b4  xor     r8d, r8d
0x1800036b7  xor     edx, edx
0x1800036b9  lea     rcx, [rsp+1500h+var_14E0]
0x1800036be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036c3  jmp     short loc_18000371E
0x1800036c5  mov     ebx, 800h
0x1800036ca  mov     rax, cs:g_pfnResultLoggingCallback
0x1800036d1  test    rax, rax
0x1800036d4  jz      short loc_1800036F3
0x1800036d6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800036dd  jnz     short loc_1800036F3
0x1800036df  mov     r8d, ebx
0x1800036e2  lea     rdx, [rbp+1400h+OutputString]
0x1800036e9  lea     rcx, [rsp+1500h+var_14E0]
0x1800036ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036f3  cmp     [rbp+1400h+OutputString], r12w
0x1800036fb  jnz     short loc_180003711
0x1800036fd  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003702  mov     rdx, rbx; unsigned __int16 *
0x180003705  lea     rcx, [rbp+1400h+OutputString]; this
0x18000370c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003711  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003718  call    cs:__imp_OutputDebugStringW
0x18000371e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003723  jnz     short loc_18000372E
0x180003725  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000372c  jz      short loc_180003740
0x18000372e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003735  test    rax, rax
0x180003738  jz      short loc_180003740
0x18000373a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000373f  nop
0x180003740  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003745  jnz     short loc_180003768
0x180003747  mov     rcx, [rbp+1400h+var_40]
0x18000374e  xor     rcx, rsp; StackCookie
0x180003751  call    __security_check_cookie
0x180003756  add     rsp, 14D0h
0x18000375d  pop     r15
0x18000375f  pop     r14
0x180003761  pop     r12
0x180003763  pop     rdi
0x180003764  pop     rsi
0x180003765  pop     rbx
0x180003766  pop     rbp
0x180003767  retn
0x180003768  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000376d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003773  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
