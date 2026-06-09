# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003208`
- end: `0x140003495`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002ce8`

## callees

- `0x140002120`
- `0x140002c58`
- `0x140003208`
- `0x140004374`
- `0x140005270`
- `0x1400061c0`
- `0x14000629c`
- `0x14000acc0`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400032b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400032b6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400033aa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400033aa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003434`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003434`

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
0x140003208  push    rbp
0x14000320a  push    rbx
0x14000320b  push    rsi
0x14000320c  push    rdi
0x14000320d  push    r12
0x14000320f  push    r14
0x140003211  push    r15
0x140003213  lea     rbp, [rsp-13D0h]
0x14000321b  mov     eax, 14D0h
0x140003220  call    _alloca_probe
0x140003225  sub     rsp, rax
0x140003228  mov     rax, cs:__security_cookie
0x14000322f  xor     rax, rsp
0x140003232  mov     [rbp+1400h+var_40], rax
0x140003239  mov     r14, r8
0x14000323c  mov     esi, edx
0x14000323e  mov     r15, rcx
0x140003241  mov     rdi, [rbp+1400h+arg_28]
0x140003248  xor     edx, edx; Val
0x14000324a  mov     r8d, 98h; Size
0x140003250  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140003255  call    memset_0
0x14000325a  nop
0x14000325b  xor     r12d, r12d
0x14000325e  mov     [rbp+1400h+OutputString], r12w
0x140003266  mov     [rbp+1400h+var_1440], r12b
0x14000326a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x140003271  mov     ecx, [rdx]; this
0x140003273  mov     [rsp+1500h+var_14D8], ecx
0x140003277  mov     eax, [rdx+4]
0x14000327a  mov     [rsp+1500h+var_14D4], eax
0x14000327e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003283  mov     ebx, eax
0x140003285  mov     dword ptr [rsp+1500h+var_14E0], 1
0x14000328d  mov     ecx, r12d
0x140003290  lea     eax, [r12+8]
0x140003295  cmp     dword ptr [rdx+8], 1
0x140003299  cmovz   ecx, eax
0x14000329c  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1400032a0  lea     ecx, [rax-7]
0x1400032a3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400032ab  inc     ecx
0x1400032ad  mov     [rsp+1500h+var_14D0], ecx
0x1400032b1  mov     [rsp+1500h+var_14C8], r12
0x1400032b6  call    cs:__imp_GetCurrentThreadId
0x1400032bc  mov     [rsp+1500h+var_14C0], eax
0x1400032c0  mov     [rsp+1500h+var_14A8], r14
0x1400032c5  mov     [rsp+1500h+var_14A0], esi
0x1400032c9  mov     [rsp+1500h+var_149C], ebx
0x1400032cd  mov     [rsp+1500h+var_14B8], r12
0x1400032d2  mov     [rsp+1500h+var_14B0], r12
0x1400032d7  mov     [rbp+1400h+var_1458], rdi
0x1400032db  mov     [rbp+1400h+var_1450], r15
0x1400032df  mov     [rsp+1500h+var_1498], r12
0x1400032e4  xorps   xmm0, xmm0
0x1400032e7  xor     eax, eax
0x1400032e9  movups  [rbp+1400h+var_1478], xmm0
0x1400032ed  mov     [rbp+1400h+var_1468], rax
0x1400032f1  xorps   xmm1, xmm1
0x1400032f4  movups  [rsp+1500h+var_1490], xmm1
0x1400032f9  mov     [rbp+1400h+var_1480], rax
0x1400032fd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003304  test    rax, rax
0x140003307  jz      short loc_140003314
0x140003309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000330e  mov     [rbp+1400h+var_1460], rax
0x140003312  jmp     short loc_140003318
0x140003314  mov     [rbp+1400h+var_1460], r12
0x140003318  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000331f  test    rax, rax
0x140003322  jz      short loc_14000332E
0x140003324  lea     rcx, [rsp+1500h+var_14E0]
0x140003329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000332e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003335  test    rax, rax
0x140003338  jz      short loc_14000334E
0x14000333a  mov     r8d, 400h
0x140003340  lea     rdx, [rbp+1400h+var_1440]
0x140003344  lea     rcx, [rsp+1500h+var_14E0]
0x140003349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000334e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003355  test    rax, rax
0x140003358  jz      short loc_140003364
0x14000335a  lea     rcx, [rsp+1500h+var_14E0]
0x14000335f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003364  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000336b  test    rax, rax
0x14000336e  jz      short loc_140003381
0x140003370  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003375  jnz     short loc_140003381
0x140003377  lea     rcx, [rsp+1500h+var_14E0]
0x14000337c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003381  cmp     [rsp+1500h+var_14D8], r12d
0x140003386  jge     loc_14000348F
0x14000338c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140003393  jnz     short loc_1400033B4
0x140003395  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000339c  test    rax, rax
0x14000339f  jz      short loc_1400033AA
0x1400033a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033a6  test    al, al
0x1400033a8  jmp     short loc_1400033B2
0x1400033aa  call    cs:__imp_IsDebuggerPresent
0x1400033b0  test    eax, eax
0x1400033b2  jz      short loc_1400033BB
0x1400033b4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400033b9  jz      short loc_1400033E1
0x1400033bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1400033c2  test    rax, rax
0x1400033c5  jz      short loc_14000343A
0x1400033c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400033ce  jnz     short loc_14000343A
0x1400033d0  xor     r8d, r8d
0x1400033d3  xor     edx, edx
0x1400033d5  lea     rcx, [rsp+1500h+var_14E0]
0x1400033da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033df  jmp     short loc_14000343A
0x1400033e1  mov     ebx, 800h
0x1400033e6  mov     rax, cs:g_pfnResultLoggingCallback
0x1400033ed  test    rax, rax
0x1400033f0  jz      short loc_14000340F
0x1400033f2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400033f9  jnz     short loc_14000340F
0x1400033fb  mov     r8d, ebx
0x1400033fe  lea     rdx, [rbp+1400h+OutputString]
0x140003405  lea     rcx, [rsp+1500h+var_14E0]
0x14000340a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000340f  cmp     [rbp+1400h+OutputString], r12w
0x140003417  jnz     short loc_14000342D
0x140003419  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x14000341e  mov     rdx, rbx; unsigned __int16 *
0x140003421  lea     rcx, [rbp+1400h+OutputString]; this
0x140003428  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000342d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140003434  call    cs:__imp_OutputDebugStringW
0x14000343a  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x14000343f  jnz     short loc_14000344A
0x140003441  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140003448  jz      short loc_14000345C
0x14000344a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003451  test    rax, rax
0x140003454  jz      short loc_14000345C
0x140003456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000345b  nop
0x14000345c  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140003461  jnz     short loc_140003484
0x140003463  mov     rcx, [rbp+1400h+var_40]
0x14000346a  xor     rcx, rsp; StackCookie
0x14000346d  call    __security_check_cookie
0x140003472  add     rsp, 14D0h
0x140003479  pop     r15
0x14000347b  pop     r14
0x14000347d  pop     r12
0x14000347f  pop     rdi
0x140003480  pop     rsi
0x140003481  pop     rbx
0x140003482  pop     rbp
0x140003483  retn
0x140003484  lea     rcx, [rsp+1500h+var_14E0]; this
0x140003489  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000348f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
