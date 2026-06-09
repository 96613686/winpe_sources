# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005508`
- end: `0x1800057ae`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004934`

## callees

- `0x180003520`
- `0x180004118`
- `0x180005508`
- `0x180007d64`
- `0x180008f50`
- `0x18000a0b0`
- `0x18000a364`
- `0x180027cb0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055ce`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800056c3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800056c3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000574d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000574d`

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
0x180005508  push    rbp
0x18000550a  push    rbx
0x18000550b  push    rsi
0x18000550c  push    rdi
0x18000550d  push    r12
0x18000550f  push    r14
0x180005511  push    r15
0x180005513  lea     rbp, [rsp-13D0h]
0x18000551b  mov     eax, 14D0h
0x180005520  call    _alloca_probe
0x180005525  sub     rsp, rax
0x180005528  mov     rax, cs:__security_cookie
0x18000552f  xor     rax, rsp
0x180005532  mov     [rbp+1400h+var_40], rax
0x180005539  mov     rsi, r8
0x18000553c  mov     edi, edx
0x18000553e  mov     rbx, rcx
0x180005541  mov     r14, [rbp+1400h+arg_28]
0x180005548  xor     edx, edx; Val
0x18000554a  mov     r8d, 98h; Size
0x180005550  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180005555  call    memset_0
0x18000555a  nop
0x18000555b  xor     r12d, r12d
0x18000555e  mov     [rbp+1400h+OutputString], r12w
0x180005566  mov     [rbp+1400h+var_1440], r12b
0x18000556a  mov     rdx, [rbp+1400h+arg_30]; int
0x180005571  mov     ecx, [rdx]; this
0x180005573  mov     [rsp+1500h+var_14D8], ecx
0x180005577  mov     eax, [rdx+4]
0x18000557a  mov     [rsp+1500h+var_14D4], eax
0x18000557e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005583  mov     r15d, eax
0x180005586  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000558e  mov     ecx, r12d
0x180005591  lea     eax, [r12+8]
0x180005596  cmp     dword ptr [rdx+8], 1
0x18000559a  cmovz   ecx, eax
0x18000559d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800055a1  lea     ecx, [rax-7]
0x1800055a4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800055ac  inc     ecx
0x1800055ae  mov     [rsp+1500h+var_14D0], ecx
0x1800055b2  mov     rcx, [rbp+1400h+arg_38]
0x1800055b9  test    rcx, rcx
0x1800055bc  jz      short loc_1800055C9
0x1800055be  cmp     [rcx], r12w
0x1800055c2  mov     [rsp+1500h+var_14C8], rcx
0x1800055c7  jnz     short loc_1800055CE
0x1800055c9  mov     [rsp+1500h+var_14C8], r12
0x1800055ce  call    cs:__imp_GetCurrentThreadId
0x1800055d4  mov     [rsp+1500h+var_14C0], eax
0x1800055d8  mov     [rsp+1500h+var_14A8], rsi
0x1800055dd  mov     [rsp+1500h+var_14A0], edi
0x1800055e1  mov     [rsp+1500h+var_149C], r15d
0x1800055e6  mov     [rsp+1500h+var_14B8], r12
0x1800055eb  mov     [rsp+1500h+var_14B0], r12
0x1800055f0  mov     [rbp+1400h+var_1458], r14
0x1800055f4  mov     [rbp+1400h+var_1450], rbx
0x1800055f8  mov     [rsp+1500h+var_1498], r12
0x1800055fd  xorps   xmm0, xmm0
0x180005600  xor     eax, eax
0x180005602  movups  [rbp+1400h+var_1478], xmm0
0x180005606  mov     [rbp+1400h+var_1468], rax
0x18000560a  xorps   xmm1, xmm1
0x18000560d  movups  [rsp+1500h+var_1490], xmm1
0x180005612  mov     [rbp+1400h+var_1480], rax
0x180005616  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000561d  test    rax, rax
0x180005620  jz      short loc_18000562D
0x180005622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005627  mov     [rbp+1400h+var_1460], rax
0x18000562b  jmp     short loc_180005631
0x18000562d  mov     [rbp+1400h+var_1460], r12
0x180005631  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005638  test    rax, rax
0x18000563b  jz      short loc_180005647
0x18000563d  lea     rcx, [rsp+1500h+var_14E0]
0x180005642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005647  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000564e  test    rax, rax
0x180005651  jz      short loc_180005667
0x180005653  mov     r8d, 400h
0x180005659  lea     rdx, [rbp+1400h+var_1440]
0x18000565d  lea     rcx, [rsp+1500h+var_14E0]
0x180005662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005667  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000566e  test    rax, rax
0x180005671  jz      short loc_18000567D
0x180005673  lea     rcx, [rsp+1500h+var_14E0]
0x180005678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000567d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005684  test    rax, rax
0x180005687  jz      short loc_18000569A
0x180005689  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000568e  jnz     short loc_18000569A
0x180005690  lea     rcx, [rsp+1500h+var_14E0]
0x180005695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000569a  cmp     [rsp+1500h+var_14D8], r12d
0x18000569f  jge     loc_1800057A8
0x1800056a5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800056ac  jnz     short loc_1800056CD
0x1800056ae  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800056b5  test    rax, rax
0x1800056b8  jz      short loc_1800056C3
0x1800056ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056bf  test    al, al
0x1800056c1  jmp     short loc_1800056CB
0x1800056c3  call    cs:__imp_IsDebuggerPresent
0x1800056c9  test    eax, eax
0x1800056cb  jz      short loc_1800056D4
0x1800056cd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800056d2  jz      short loc_1800056FA
0x1800056d4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800056db  test    rax, rax
0x1800056de  jz      short loc_180005753
0x1800056e0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800056e7  jnz     short loc_180005753
0x1800056e9  xor     r8d, r8d
0x1800056ec  xor     edx, edx
0x1800056ee  lea     rcx, [rsp+1500h+var_14E0]
0x1800056f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056f8  jmp     short loc_180005753
0x1800056fa  mov     ebx, 800h
0x1800056ff  mov     rax, cs:g_pfnResultLoggingCallback
0x180005706  test    rax, rax
0x180005709  jz      short loc_180005728
0x18000570b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005712  jnz     short loc_180005728
0x180005714  mov     r8d, ebx
0x180005717  lea     rdx, [rbp+1400h+OutputString]
0x18000571e  lea     rcx, [rsp+1500h+var_14E0]
0x180005723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005728  cmp     [rbp+1400h+OutputString], r12w
0x180005730  jnz     short loc_180005746
0x180005732  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180005737  mov     rdx, rbx; unsigned __int16 *
0x18000573a  lea     rcx, [rbp+1400h+OutputString]; this
0x180005741  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005746  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000574d  call    cs:__imp_OutputDebugStringW
0x180005753  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180005758  jnz     short loc_180005763
0x18000575a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180005761  jz      short loc_180005775
0x180005763  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000576a  test    rax, rax
0x18000576d  jz      short loc_180005775
0x18000576f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005774  nop
0x180005775  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000577a  jnz     short loc_18000579D
0x18000577c  mov     rcx, [rbp+1400h+var_40]
0x180005783  xor     rcx, rsp; StackCookie
0x180005786  call    __security_check_cookie
0x18000578b  add     rsp, 14D0h
0x180005792  pop     r15
0x180005794  pop     r14
0x180005796  pop     r12
0x180005798  pop     rdi
0x180005799  pop     rsi
0x18000579a  pop     rbx
0x18000579b  pop     rbp
0x18000579c  retn
0x18000579d  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800057a2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800057a8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
