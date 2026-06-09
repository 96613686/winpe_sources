# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180006568`
- end: `0x1800067f5`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005cf0`

## callees

- `0x180002bf0`
- `0x1800038b8`
- `0x180006568`
- `0x18000b994`
- `0x18000db58`
- `0x180010630`
- `0x1800108c4`
- `0x1800ce770`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006616`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006616`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000670a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000670a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006794`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006794`

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
0x180006568  push    rbp
0x18000656a  push    rbx
0x18000656b  push    rsi
0x18000656c  push    rdi
0x18000656d  push    r12
0x18000656f  push    r14
0x180006571  push    r15
0x180006573  lea     rbp, [rsp-13D0h]
0x18000657b  mov     eax, 14D0h
0x180006580  call    _alloca_probe
0x180006585  sub     rsp, rax
0x180006588  mov     rax, cs:__security_cookie
0x18000658f  xor     rax, rsp
0x180006592  mov     [rbp+1400h+var_40], rax
0x180006599  mov     r14, r8
0x18000659c  mov     esi, edx
0x18000659e  mov     r15, rcx
0x1800065a1  mov     rdi, [rbp+1400h+arg_28]
0x1800065a8  xor     edx, edx; Val
0x1800065aa  mov     r8d, 98h; Size
0x1800065b0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800065b5  call    memset_0
0x1800065ba  nop
0x1800065bb  xor     r12d, r12d
0x1800065be  mov     [rbp+1400h+OutputString], r12w
0x1800065c6  mov     [rbp+1400h+var_1440], r12b
0x1800065ca  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800065d1  mov     ecx, [rdx]; this
0x1800065d3  mov     [rsp+1500h+var_14D8], ecx
0x1800065d7  mov     eax, [rdx+4]
0x1800065da  mov     [rsp+1500h+var_14D4], eax
0x1800065de  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800065e3  mov     ebx, eax
0x1800065e5  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800065ed  mov     ecx, r12d
0x1800065f0  lea     eax, [r12+8]
0x1800065f5  cmp     dword ptr [rdx+8], 1
0x1800065f9  cmovz   ecx, eax
0x1800065fc  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180006600  lea     ecx, [rax-7]
0x180006603  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000660b  inc     ecx
0x18000660d  mov     [rsp+1500h+var_14D0], ecx
0x180006611  mov     [rsp+1500h+var_14C8], r12
0x180006616  call    cs:__imp_GetCurrentThreadId
0x18000661c  mov     [rsp+1500h+var_14C0], eax
0x180006620  mov     [rsp+1500h+var_14A8], r14
0x180006625  mov     [rsp+1500h+var_14A0], esi
0x180006629  mov     [rsp+1500h+var_149C], ebx
0x18000662d  mov     [rsp+1500h+var_14B8], r12
0x180006632  mov     [rsp+1500h+var_14B0], r12
0x180006637  mov     [rbp+1400h+var_1458], rdi
0x18000663b  mov     [rbp+1400h+var_1450], r15
0x18000663f  mov     [rsp+1500h+var_1498], r12
0x180006644  xorps   xmm0, xmm0
0x180006647  xor     eax, eax
0x180006649  movups  [rbp+1400h+var_1478], xmm0
0x18000664d  mov     [rbp+1400h+var_1468], rax
0x180006651  xorps   xmm1, xmm1
0x180006654  movups  [rsp+1500h+var_1490], xmm1
0x180006659  mov     [rbp+1400h+var_1480], rax
0x18000665d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006664  test    rax, rax
0x180006667  jz      short loc_180006674
0x180006669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000666e  mov     [rbp+1400h+var_1460], rax
0x180006672  jmp     short loc_180006678
0x180006674  mov     [rbp+1400h+var_1460], r12
0x180006678  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000667f  test    rax, rax
0x180006682  jz      short loc_18000668E
0x180006684  lea     rcx, [rsp+1500h+var_14E0]
0x180006689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000668e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006695  test    rax, rax
0x180006698  jz      short loc_1800066AE
0x18000669a  mov     r8d, 400h
0x1800066a0  lea     rdx, [rbp+1400h+var_1440]
0x1800066a4  lea     rcx, [rsp+1500h+var_14E0]
0x1800066a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066ae  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800066b5  test    rax, rax
0x1800066b8  jz      short loc_1800066C4
0x1800066ba  lea     rcx, [rsp+1500h+var_14E0]
0x1800066bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066c4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800066cb  test    rax, rax
0x1800066ce  jz      short loc_1800066E1
0x1800066d0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800066d5  jnz     short loc_1800066E1
0x1800066d7  lea     rcx, [rsp+1500h+var_14E0]
0x1800066dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066e1  cmp     [rsp+1500h+var_14D8], r12d
0x1800066e6  jge     loc_1800067EF
0x1800066ec  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800066f3  jnz     short loc_180006714
0x1800066f5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800066fc  test    rax, rax
0x1800066ff  jz      short loc_18000670A
0x180006701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006706  test    al, al
0x180006708  jmp     short loc_180006712
0x18000670a  call    cs:__imp_IsDebuggerPresent
0x180006710  test    eax, eax
0x180006712  jz      short loc_18000671B
0x180006714  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006719  jz      short loc_180006741
0x18000671b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006722  test    rax, rax
0x180006725  jz      short loc_18000679A
0x180006727  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000672e  jnz     short loc_18000679A
0x180006730  xor     r8d, r8d
0x180006733  xor     edx, edx
0x180006735  lea     rcx, [rsp+1500h+var_14E0]
0x18000673a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000673f  jmp     short loc_18000679A
0x180006741  mov     ebx, 800h
0x180006746  mov     rax, cs:g_pfnResultLoggingCallback
0x18000674d  test    rax, rax
0x180006750  jz      short loc_18000676F
0x180006752  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180006759  jnz     short loc_18000676F
0x18000675b  mov     r8d, ebx
0x18000675e  lea     rdx, [rbp+1400h+OutputString]
0x180006765  lea     rcx, [rsp+1500h+var_14E0]
0x18000676a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000676f  cmp     [rbp+1400h+OutputString], r12w
0x180006777  jnz     short loc_18000678D
0x180006779  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000677e  mov     rdx, rbx; unsigned __int16 *
0x180006781  lea     rcx, [rbp+1400h+OutputString]; this
0x180006788  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000678d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180006794  call    cs:__imp_OutputDebugStringW
0x18000679a  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000679f  jnz     short loc_1800067AA
0x1800067a1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800067a8  jz      short loc_1800067BC
0x1800067aa  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800067b1  test    rax, rax
0x1800067b4  jz      short loc_1800067BC
0x1800067b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067bb  nop
0x1800067bc  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800067c1  jnz     short loc_1800067E4
0x1800067c3  mov     rcx, [rbp+1400h+var_40]
0x1800067ca  xor     rcx, rsp; StackCookie
0x1800067cd  call    __security_check_cookie
0x1800067d2  add     rsp, 14D0h
0x1800067d9  pop     r15
0x1800067db  pop     r14
0x1800067dd  pop     r12
0x1800067df  pop     rdi
0x1800067e0  pop     rsi
0x1800067e1  pop     rbx
0x1800067e2  pop     rbp
0x1800067e3  retn
0x1800067e4  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800067e9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800067ef  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
