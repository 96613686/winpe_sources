# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005580`
- end: `0x180005826`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005104`

## callees

- `0x1800028d0`
- `0x1800033a0`
- `0x180005580`
- `0x180007684`
- `0x18000959c`
- `0x18000b3f8`
- `0x18000b690`
- `0x180055ca0`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005646`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005646`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800057c5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800057c5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000573b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000573b`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180005580  push    rbp
0x180005582  push    rbx
0x180005583  push    rsi
0x180005584  push    rdi
0x180005585  push    r12
0x180005587  push    r14
0x180005589  push    r15
0x18000558b  lea     rbp, [rsp-13D0h]
0x180005593  mov     eax, 14D0h
0x180005598  call    _alloca_probe
0x18000559d  sub     rsp, rax
0x1800055a0  mov     rax, cs:__security_cookie
0x1800055a7  xor     rax, rsp
0x1800055aa  mov     [rbp+1400h+var_40], rax
0x1800055b1  mov     rsi, r8
0x1800055b4  mov     edi, edx
0x1800055b6  mov     rbx, rcx
0x1800055b9  mov     r14, [rbp+1400h+arg_28]
0x1800055c0  xor     edx, edx; Val
0x1800055c2  mov     r8d, 98h; Size
0x1800055c8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800055cd  call    memset_0
0x1800055d2  nop
0x1800055d3  xor     r12d, r12d
0x1800055d6  mov     [rbp+1400h+OutputString], r12w
0x1800055de  mov     [rbp+1400h+var_1440], r12b
0x1800055e2  mov     rdx, [rbp+1400h+arg_30]; int
0x1800055e9  mov     ecx, [rdx]; this
0x1800055eb  mov     [rsp+1500h+var_14D8], ecx
0x1800055ef  mov     eax, [rdx+4]
0x1800055f2  mov     [rsp+1500h+var_14D4], eax
0x1800055f6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800055fb  mov     r15d, eax
0x1800055fe  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005606  mov     ecx, r12d
0x180005609  lea     eax, [r12+8]
0x18000560e  cmp     dword ptr [rdx+8], 1
0x180005612  cmovz   ecx, eax
0x180005615  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005619  lea     ecx, [rax-7]
0x18000561c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005624  inc     ecx
0x180005626  mov     [rsp+1500h+var_14D0], ecx
0x18000562a  mov     rcx, [rbp+1400h+arg_38]
0x180005631  test    rcx, rcx
0x180005634  jz      short loc_180005641
0x180005636  cmp     [rcx], r12w
0x18000563a  mov     [rsp+1500h+var_14C8], rcx
0x18000563f  jnz     short loc_180005646
0x180005641  mov     [rsp+1500h+var_14C8], r12
0x180005646  call    cs:__imp_GetCurrentThreadId
0x18000564c  mov     [rsp+1500h+var_14C0], eax
0x180005650  mov     [rsp+1500h+var_14A8], rsi
0x180005655  mov     [rsp+1500h+var_14A0], edi
0x180005659  mov     [rsp+1500h+var_149C], r15d
0x18000565e  mov     [rsp+1500h+var_14B8], r12
0x180005663  mov     [rsp+1500h+var_14B0], r12
0x180005668  mov     [rbp+1400h+var_1458], r14
0x18000566c  mov     [rbp+1400h+var_1450], rbx
0x180005670  mov     [rsp+1500h+var_1498], r12
0x180005675  xorps   xmm0, xmm0
0x180005678  xor     eax, eax
0x18000567a  movups  [rbp+1400h+var_1478], xmm0
0x18000567e  mov     [rbp+1400h+var_1468], rax
0x180005682  xorps   xmm1, xmm1
0x180005685  movups  [rsp+1500h+var_1490], xmm1
0x18000568a  mov     [rbp+1400h+var_1480], rax
0x18000568e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005695  test    rax, rax
0x180005698  jz      short loc_1800056A5
0x18000569a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000569f  mov     [rbp+1400h+var_1460], rax
0x1800056a3  jmp     short loc_1800056A9
0x1800056a5  mov     [rbp+1400h+var_1460], r12
0x1800056a9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800056b0  test    rax, rax
0x1800056b3  jz      short loc_1800056BF
0x1800056b5  lea     rcx, [rsp+1500h+var_14E0]
0x1800056ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056bf  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800056c6  test    rax, rax
0x1800056c9  jz      short loc_1800056DF
0x1800056cb  mov     r8d, 400h
0x1800056d1  lea     rdx, [rbp+1400h+var_1440]
0x1800056d5  lea     rcx, [rsp+1500h+var_14E0]
0x1800056da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056df  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800056e6  test    rax, rax
0x1800056e9  jz      short loc_1800056F5
0x1800056eb  lea     rcx, [rsp+1500h+var_14E0]
0x1800056f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056f5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800056fc  test    rax, rax
0x1800056ff  jz      short loc_180005712
0x180005701  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005706  jnz     short loc_180005712
0x180005708  lea     rcx, [rsp+1500h+var_14E0]
0x18000570d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005712  cmp     [rsp+1500h+var_14D8], r12d
0x180005717  jge     loc_180005820
0x18000571d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005724  jnz     short loc_180005745
0x180005726  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000572d  test    rax, rax
0x180005730  jz      short loc_18000573B
0x180005732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005737  test    al, al
0x180005739  jmp     short loc_180005743
0x18000573b  call    cs:__imp_IsDebuggerPresent
0x180005741  test    eax, eax
0x180005743  jz      short loc_18000574C
0x180005745  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000574a  jz      short loc_180005772
0x18000574c  mov     rax, cs:g_pfnResultLoggingCallback
0x180005753  test    rax, rax
0x180005756  jz      short loc_1800057CB
0x180005758  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000575f  jnz     short loc_1800057CB
0x180005761  xor     r8d, r8d
0x180005764  xor     edx, edx
0x180005766  lea     rcx, [rsp+1500h+var_14E0]
0x18000576b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005770  jmp     short loc_1800057CB
0x180005772  mov     ebx, 800h
0x180005777  mov     rax, cs:g_pfnResultLoggingCallback
0x18000577e  test    rax, rax
0x180005781  jz      short loc_1800057A0
0x180005783  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000578a  jnz     short loc_1800057A0
0x18000578c  mov     r8d, ebx
0x18000578f  lea     rdx, [rbp+1400h+OutputString]
0x180005796  lea     rcx, [rsp+1500h+var_14E0]
0x18000579b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057a0  cmp     [rbp+1400h+OutputString], r12w
0x1800057a8  jnz     short loc_1800057BE
0x1800057aa  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800057af  mov     rdx, rbx; unsigned __int16 *
0x1800057b2  lea     rcx, [rbp+1400h+OutputString]; this
0x1800057b9  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800057be  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800057c5  call    cs:__imp_OutputDebugStringW
0x1800057cb  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800057d0  jnz     short loc_1800057DB
0x1800057d2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800057d9  jz      short loc_1800057ED
0x1800057db  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800057e2  test    rax, rax
0x1800057e5  jz      short loc_1800057ED
0x1800057e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ec  nop
0x1800057ed  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800057f2  jnz     short loc_180005815
0x1800057f4  mov     rcx, [rbp+1400h+var_40]
0x1800057fb  xor     rcx, rsp; StackCookie
0x1800057fe  call    __security_check_cookie
0x180005803  add     rsp, 14D0h
0x18000580a  pop     r15
0x18000580c  pop     r14
0x18000580e  pop     r12
0x180005810  pop     rdi
0x180005811  pop     rsi
0x180005812  pop     rbx
0x180005813  pop     rbp
0x180005814  retn
0x180005815  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000581a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005820  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
