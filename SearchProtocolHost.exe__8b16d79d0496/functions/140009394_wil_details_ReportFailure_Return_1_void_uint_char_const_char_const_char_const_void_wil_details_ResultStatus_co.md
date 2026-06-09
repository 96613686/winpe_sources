# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140009394`
- end: `0x140009642`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400088a0`

## callees

- `0x140005240`
- `0x140006210`
- `0x140009394`
- `0x14001c80c`
- `0x140023f8c`
- `0x1400328a8`
- `0x140032fa0`
- `0x140069b10`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009462`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009462`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400095e1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400095e1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140009557`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140009557`

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
  __int64 v38; // [rsp+C0h] [rbp-40h]
  char v39[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v38 = -2;
  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
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
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v39, 1024);
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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
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
0x140009394  push    rbp
0x140009396  push    rbx
0x140009397  push    rsi
0x140009398  push    rdi
0x140009399  push    r12
0x14000939b  push    r14
0x14000939d  push    r15
0x14000939f  lea     rbp, [rsp-13E0h]
0x1400093a7  mov     eax, 14E0h
0x1400093ac  call    _alloca_probe
0x1400093b1  sub     rsp, rax
0x1400093b4  mov     [rbp+1410h+var_1450], 0FFFFFFFFFFFFFFFEh
0x1400093bc  mov     rax, cs:__security_cookie
0x1400093c3  xor     rax, rsp
0x1400093c6  mov     [rbp+1410h+var_40], rax
0x1400093cd  mov     rsi, r8
0x1400093d0  mov     edi, edx
0x1400093d2  mov     rbx, rcx
0x1400093d5  mov     r14, [rbp+1410h+arg_28]
0x1400093dc  xor     edx, edx; Val
0x1400093de  mov     r8d, 98h; Size
0x1400093e4  lea     rcx, [rsp+1510h+var_14F0]; void *
0x1400093e9  call    memset_0
0x1400093ee  nop
0x1400093ef  xor     r12d, r12d
0x1400093f2  mov     [rbp+1410h+OutputString], r12w
0x1400093fa  mov     [rbp+1410h+var_1440], r12b
0x1400093fe  mov     rdx, [rbp+1410h+arg_30]; int
0x140009405  mov     ecx, [rdx]; this
0x140009407  mov     [rsp+1510h+var_14E8], ecx
0x14000940b  mov     eax, [rdx+4]
0x14000940e  mov     [rsp+1510h+var_14E4], eax
0x140009412  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140009417  mov     r15d, eax
0x14000941a  mov     dword ptr [rsp+1510h+var_14F0], 1
0x140009422  mov     ecx, r12d
0x140009425  lea     eax, [r12+8]
0x14000942a  cmp     dword ptr [rdx+8], 1
0x14000942e  cmovz   ecx, eax
0x140009431  mov     dword ptr [rsp+1510h+var_14F0+4], ecx
0x140009435  lea     ecx, [rax-7]
0x140009438  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140009440  inc     ecx
0x140009442  mov     [rsp+1510h+var_14E0], ecx
0x140009446  mov     rcx, [rbp+1410h+arg_38]
0x14000944d  test    rcx, rcx
0x140009450  jz      short loc_14000945D
0x140009452  cmp     [rcx], r12w
0x140009456  mov     [rsp+1510h+var_14D8], rcx
0x14000945b  jnz     short loc_140009462
0x14000945d  mov     [rsp+1510h+var_14D8], r12
0x140009462  call    cs:__imp_GetCurrentThreadId
0x140009468  mov     [rsp+1510h+var_14D0], eax
0x14000946c  mov     [rsp+1510h+var_14B8], rsi
0x140009471  mov     [rsp+1510h+var_14B0], edi
0x140009475  mov     [rsp+1510h+var_14AC], r15d
0x14000947a  mov     [rsp+1510h+var_14C8], r12
0x14000947f  mov     [rsp+1510h+var_14C0], r12
0x140009484  mov     [rbp+1410h+var_1468], r14
0x140009488  mov     [rbp+1410h+var_1460], rbx
0x14000948c  mov     [rsp+1510h+var_14A8], r12
0x140009491  xorps   xmm0, xmm0
0x140009494  xor     eax, eax
0x140009496  movups  [rbp+1410h+var_1488], xmm0
0x14000949a  mov     [rbp+1410h+var_1478], rax
0x14000949e  xorps   xmm1, xmm1
0x1400094a1  movups  [rsp+1510h+var_14A0], xmm1
0x1400094a6  mov     [rbp+1410h+var_1490], rax
0x1400094aa  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400094b1  test    rax, rax
0x1400094b4  jz      short loc_1400094C1
0x1400094b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400094bb  mov     [rbp+1410h+var_1470], rax
0x1400094bf  jmp     short loc_1400094C5
0x1400094c1  mov     [rbp+1410h+var_1470], r12
0x1400094c5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400094cc  test    rax, rax
0x1400094cf  jz      short loc_1400094DB
0x1400094d1  lea     rcx, [rsp+1510h+var_14F0]
0x1400094d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400094db  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400094e2  test    rax, rax
0x1400094e5  jz      short loc_1400094FB
0x1400094e7  mov     r8d, 400h
0x1400094ed  lea     rdx, [rbp+1410h+var_1440]
0x1400094f1  lea     rcx, [rsp+1510h+var_14F0]
0x1400094f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400094fb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140009502  test    rax, rax
0x140009505  jz      short loc_140009511
0x140009507  lea     rcx, [rsp+1510h+var_14F0]
0x14000950c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009511  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140009518  test    rax, rax
0x14000951b  jz      short loc_14000952E
0x14000951d  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x140009522  jnz     short loc_14000952E
0x140009524  lea     rcx, [rsp+1510h+var_14F0]
0x140009529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000952e  cmp     [rsp+1510h+var_14E8], r12d
0x140009533  jge     loc_14000963C
0x140009539  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140009540  jnz     short loc_140009561
0x140009542  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140009549  test    rax, rax
0x14000954c  jz      short loc_140009557
0x14000954e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009553  test    al, al
0x140009555  jmp     short loc_14000955F
0x140009557  call    cs:__imp_IsDebuggerPresent
0x14000955d  test    eax, eax
0x14000955f  jz      short loc_140009568
0x140009561  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x140009566  jz      short loc_14000958E
0x140009568  mov     rax, cs:g_pfnResultLoggingCallback
0x14000956f  test    rax, rax
0x140009572  jz      short loc_1400095E7
0x140009574  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000957b  jnz     short loc_1400095E7
0x14000957d  xor     r8d, r8d
0x140009580  xor     edx, edx
0x140009582  lea     rcx, [rsp+1510h+var_14F0]
0x140009587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000958c  jmp     short loc_1400095E7
0x14000958e  mov     ebx, 800h
0x140009593  mov     rax, cs:g_pfnResultLoggingCallback
0x14000959a  test    rax, rax
0x14000959d  jz      short loc_1400095BC
0x14000959f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400095a6  jnz     short loc_1400095BC
0x1400095a8  mov     r8d, ebx
0x1400095ab  lea     rdx, [rbp+1410h+OutputString]
0x1400095b2  lea     rcx, [rsp+1510h+var_14F0]
0x1400095b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095bc  cmp     [rbp+1410h+OutputString], r12w
0x1400095c4  jnz     short loc_1400095DA
0x1400095c6  lea     r8, [rsp+1510h+var_14F0]; unsigned __int64
0x1400095cb  mov     rdx, rbx; wchar_t *
0x1400095ce  lea     rcx, [rbp+1410h+OutputString]; this
0x1400095d5  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1400095da  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x1400095e1  call    cs:__imp_OutputDebugStringW
0x1400095e7  test    byte ptr [rsp+1510h+var_14F0+4], 4
0x1400095ec  jnz     short loc_1400095F7
0x1400095ee  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400095f5  jz      short loc_140009609
0x1400095f7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400095fe  test    rax, rax
0x140009601  jz      short loc_140009609
0x140009603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009608  nop
0x140009609  test    byte ptr [rsp+1510h+var_14F0+4], 1
0x14000960e  jnz     short loc_140009631
0x140009610  mov     rcx, [rbp+1410h+var_40]
0x140009617  xor     rcx, rsp; StackCookie
0x14000961a  call    __security_check_cookie
0x14000961f  add     rsp, 14E0h
0x140009626  pop     r15
0x140009628  pop     r14
0x14000962a  pop     r12
0x14000962c  pop     rdi
0x14000962d  pop     rsi
0x14000962e  pop     rbx
0x14000962f  pop     rbp
0x140009630  retn
0x140009631  lea     rcx, [rsp+1510h+var_14F0]; this
0x140009636  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000963c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
