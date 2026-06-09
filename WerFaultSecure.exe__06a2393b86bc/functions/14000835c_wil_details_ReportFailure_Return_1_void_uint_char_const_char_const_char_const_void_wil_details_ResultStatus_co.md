# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000835c`
- end: `0x1400085e9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140007ee8`

## callees

- `0x1400023d0`
- `0x140002fcc`
- `0x1400037e4`
- `0x140005f10`
- `0x140005f2c`
- `0x140006008`
- `0x14000835c`
- `0x1400112a0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000840a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000840a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140008588`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140008588`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400084fe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400084fe`

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
  wil::details::in1diag4 *v14; // rcx
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
    wil::details::in1diag4::_FailFastImmediate_Unexpected(v14);
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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v17, v15);
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
0x14000835c  push    rbp
0x14000835e  push    rbx
0x14000835f  push    rsi
0x140008360  push    rdi
0x140008361  push    r12
0x140008363  push    r14
0x140008365  push    r15
0x140008367  lea     rbp, [rsp-13D0h]
0x14000836f  mov     eax, 14D0h
0x140008374  call    _alloca_probe
0x140008379  sub     rsp, rax
0x14000837c  mov     rax, cs:__security_cookie
0x140008383  xor     rax, rsp
0x140008386  mov     [rbp+1400h+var_40], rax
0x14000838d  mov     r14, r8
0x140008390  mov     esi, edx
0x140008392  mov     r15, rcx
0x140008395  mov     rdi, [rbp+1400h+arg_28]
0x14000839c  xor     edx, edx; Val
0x14000839e  mov     r8d, 98h; Size
0x1400083a4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400083a9  call    memset_0
0x1400083ae  nop
0x1400083af  xor     r12d, r12d
0x1400083b2  mov     [rbp+1400h+OutputString], r12w
0x1400083ba  mov     [rbp+1400h+var_1440], r12b
0x1400083be  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1400083c5  mov     ecx, [rdx]; this
0x1400083c7  mov     [rsp+1500h+var_14D8], ecx
0x1400083cb  mov     eax, [rdx+4]
0x1400083ce  mov     [rsp+1500h+var_14D4], eax
0x1400083d2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400083d7  mov     ebx, eax
0x1400083d9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1400083e1  mov     ecx, r12d
0x1400083e4  lea     eax, [r12+8]
0x1400083e9  cmp     dword ptr [rdx+8], 1
0x1400083ed  cmovz   ecx, eax
0x1400083f0  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1400083f4  lea     ecx, [rax-7]
0x1400083f7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400083ff  inc     ecx
0x140008401  mov     [rsp+1500h+var_14D0], ecx
0x140008405  mov     [rsp+1500h+var_14C8], r12
0x14000840a  call    cs:__imp_GetCurrentThreadId
0x140008410  mov     [rsp+1500h+var_14C0], eax
0x140008414  mov     [rsp+1500h+var_14A8], r14
0x140008419  mov     [rsp+1500h+var_14A0], esi
0x14000841d  mov     [rsp+1500h+var_149C], ebx
0x140008421  mov     [rsp+1500h+var_14B8], r12
0x140008426  mov     [rsp+1500h+var_14B0], r12
0x14000842b  mov     [rbp+1400h+var_1458], rdi
0x14000842f  mov     [rbp+1400h+var_1450], r15
0x140008433  mov     [rsp+1500h+var_1498], r12
0x140008438  xorps   xmm0, xmm0
0x14000843b  xor     eax, eax
0x14000843d  movups  [rbp+1400h+var_1478], xmm0
0x140008441  mov     [rbp+1400h+var_1468], rax
0x140008445  xorps   xmm1, xmm1
0x140008448  movups  [rsp+1500h+var_1490], xmm1
0x14000844d  mov     [rbp+1400h+var_1480], rax
0x140008451  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140008458  test    rax, rax
0x14000845b  jz      short loc_140008468
0x14000845d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008462  mov     [rbp+1400h+var_1460], rax
0x140008466  jmp     short loc_14000846C
0x140008468  mov     [rbp+1400h+var_1460], r12
0x14000846c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140008473  test    rax, rax
0x140008476  jz      short loc_140008482
0x140008478  lea     rcx, [rsp+1500h+var_14E0]
0x14000847d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008482  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140008489  test    rax, rax
0x14000848c  jz      short loc_1400084A2
0x14000848e  mov     r8d, 400h
0x140008494  lea     rdx, [rbp+1400h+var_1440]
0x140008498  lea     rcx, [rsp+1500h+var_14E0]
0x14000849d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084a2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400084a9  test    rax, rax
0x1400084ac  jz      short loc_1400084B8
0x1400084ae  lea     rcx, [rsp+1500h+var_14E0]
0x1400084b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084b8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400084bf  test    rax, rax
0x1400084c2  jz      short loc_1400084D5
0x1400084c4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400084c9  jnz     short loc_1400084D5
0x1400084cb  lea     rcx, [rsp+1500h+var_14E0]
0x1400084d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084d5  cmp     [rsp+1500h+var_14D8], r12d
0x1400084da  jge     loc_1400085E3
0x1400084e0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400084e7  jnz     short loc_140008508
0x1400084e9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400084f0  test    rax, rax
0x1400084f3  jz      short loc_1400084FE
0x1400084f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084fa  test    al, al
0x1400084fc  jmp     short loc_140008506
0x1400084fe  call    cs:__imp_IsDebuggerPresent
0x140008504  test    eax, eax
0x140008506  jz      short loc_14000850F
0x140008508  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000850d  jz      short loc_140008535
0x14000850f  mov     rax, cs:g_pfnResultLoggingCallback
0x140008516  test    rax, rax
0x140008519  jz      short loc_14000858E
0x14000851b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140008522  jnz     short loc_14000858E
0x140008524  xor     r8d, r8d
0x140008527  xor     edx, edx
0x140008529  lea     rcx, [rsp+1500h+var_14E0]
0x14000852e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008533  jmp     short loc_14000858E
0x140008535  mov     ebx, 800h
0x14000853a  mov     rax, cs:g_pfnResultLoggingCallback
0x140008541  test    rax, rax
0x140008544  jz      short loc_140008563
0x140008546  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000854d  jnz     short loc_140008563
0x14000854f  mov     r8d, ebx
0x140008552  lea     rdx, [rbp+1400h+OutputString]
0x140008559  lea     rcx, [rsp+1500h+var_14E0]
0x14000855e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008563  cmp     [rbp+1400h+OutputString], r12w
0x14000856b  jnz     short loc_140008581
0x14000856d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140008572  mov     rdx, rbx; wchar_t *
0x140008575  lea     rcx, [rbp+1400h+OutputString]; this
0x14000857c  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140008581  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140008588  call    cs:__imp_OutputDebugStringW
0x14000858e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140008593  jnz     short loc_14000859E
0x140008595  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000859c  jz      short loc_1400085B0
0x14000859e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400085a5  test    rax, rax
0x1400085a8  jz      short loc_1400085B0
0x1400085aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085af  nop
0x1400085b0  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1400085b5  jnz     short loc_1400085D8
0x1400085b7  mov     rcx, [rbp+1400h+var_40]
0x1400085be  xor     rcx, rsp; StackCookie
0x1400085c1  call    __security_check_cookie
0x1400085c6  add     rsp, 14D0h
0x1400085cd  pop     r15
0x1400085cf  pop     r14
0x1400085d1  pop     r12
0x1400085d3  pop     rdi
0x1400085d4  pop     rsi
0x1400085d5  pop     rbx
0x1400085d6  pop     rbp
0x1400085d7  retn
0x1400085d8  lea     rcx, [rsp+1500h+var_14E0]; this
0x1400085dd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400085e3  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
```
