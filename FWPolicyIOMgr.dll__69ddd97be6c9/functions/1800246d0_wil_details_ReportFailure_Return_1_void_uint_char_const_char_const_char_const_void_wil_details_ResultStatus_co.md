# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800246d0`
- end: `0x180024987`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `695`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001f020`

## callees

- `0x18001f650`
- `0x1800246d0`
- `0x180027604`
- `0x1800289b0`
- `0x1800298f8`
- `0x180029b2c`
- `0x180039b40`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002479c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002479c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180024921`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180024921`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180024897`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180024897`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned __int64 *a7)
{
  unsigned int v9; // ebx
  int v10; // ecx
  __int64 v11; // r8
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  unsigned __int64 v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v17; // [rsp+30h] [rbp-D0h]
  __int128 v18; // [rsp+40h] [rbp-C0h]
  __int128 v19; // [rsp+50h] [rbp-B0h]
  __int128 v20; // [rsp+60h] [rbp-A0h]
  __int128 v21; // [rsp+70h] [rbp-90h]
  _OWORD v22[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v23; // [rsp+A0h] [rbp-60h]
  __int64 v24; // [rsp+B0h] [rbp-50h]
  _BYTE v25[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  *(_OWORD *)v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  memset(v22, 0, sizeof(v22));
  v23 = 0;
  v24 = 0;
  OutputString[0] = 0;
  v25[0] = 0;
  v16[1] = *a7;
  v9 = wil::details::RecordReturn((wil::details *)LODWORD(v16[1]), a2);
  LODWORD(v16[0]) = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  HIDWORD(v16[0]) = v10;
  LODWORD(v17) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  *((_QWORD *)&v17 + 1) = 0;
  LODWORD(v18) = GetCurrentThreadId();
  *((_QWORD *)&v19 + 1) = "wil";
  v20 = __PAIR64__(v9, a2);
  *((_QWORD *)&v18 + 1) = 0;
  *(_QWORD *)&v19 = 0;
  *((_QWORD *)&v23 + 1) = a6;
  v24 = a1;
  v21 = 0;
  memset(v22, 0, sizeof(v22));
  if ( wil::details::g_pfnGetModuleName )
    *(_QWORD *)&v23 = wil::details::g_pfnGetModuleName(v13);
  else
    *(_QWORD *)&v23 = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v16, v25, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v16);
  if ( wil::details::g_pfnOriginateCallback && (v16[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v16);
  if ( SLODWORD(v16[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v16[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (unsigned __int16 *)0x800, (unsigned __int64)v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v16[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v16[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v16, v12);
}

```

## disassembly

```asm
0x1800246d0  mov     [rsp-8+arg_10], rbx
0x1800246d5  push    rbp
0x1800246d6  push    rsi
0x1800246d7  push    rdi
0x1800246d8  push    r14
0x1800246da  push    r15
0x1800246dc  lea     rbp, [rsp-13D0h]
0x1800246e4  mov     eax, 14D0h
0x1800246e9  call    _alloca_probe
0x1800246ee  sub     rsp, rax
0x1800246f1  mov     rax, cs:__security_cookie
0x1800246f8  xor     rax, rsp
0x1800246fb  mov     [rbp+13F0h+var_30], rax
0x180024702  mov     esi, edx
0x180024704  mov     r14, rcx
0x180024707  mov     rdi, [rbp+13F0h+arg_28]
0x18002470e  xorps   xmm0, xmm0
0x180024711  xor     eax, eax
0x180024713  movups  xmmword ptr [rsp+14F0h+var_14D0], xmm0
0x180024718  movups  [rsp+14F0h+var_14C0], xmm0
0x18002471d  movups  [rsp+14F0h+var_14B0], xmm0
0x180024722  movups  [rsp+14F0h+var_14A0], xmm0
0x180024727  movups  [rsp+14F0h+var_1490], xmm0
0x18002472c  movups  [rsp+14F0h+var_1480], xmm0
0x180024731  movups  [rbp+13F0h+var_1470], xmm0
0x180024735  movups  [rbp+13F0h+var_1460], xmm0
0x180024739  movups  [rbp+13F0h+var_1450], xmm0
0x18002473d  mov     [rbp+13F0h+var_1440], rax
0x180024741  xor     r15d, r15d
0x180024744  mov     [rbp+13F0h+OutputString], r15w
0x18002474c  mov     [rbp+13F0h+var_1430], r15b
0x180024750  mov     r8, [rbp+13F0h+arg_30]
0x180024757  mov     ecx, [r8]; this
0x18002475a  mov     dword ptr [rsp+14F0h+var_14D0+8], ecx
0x18002475e  mov     eax, [r8+4]
0x180024762  mov     dword ptr [rsp+14F0h+var_14D0+0Ch], eax
0x180024766  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002476b  mov     ebx, eax
0x18002476d  mov     edx, 1
0x180024772  mov     dword ptr [rsp+14F0h+var_14D0], edx
0x180024776  mov     ecx, r15d
0x180024779  mov     eax, 8
0x18002477e  cmp     [r8+8], edx
0x180024782  cmovz   ecx, eax
0x180024785  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180024789  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, edx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180024791  inc     edx
0x180024793  mov     dword ptr [rsp+14F0h+var_14C0], edx
0x180024797  mov     qword ptr [rsp+14F0h+var_14C0+8], r15
0x18002479c  call    cs:__imp_GetCurrentThreadId
0x1800247a2  mov     dword ptr [rsp+14F0h+var_14B0], eax
0x1800247a6  lea     rax, aWil; "wil"
0x1800247ad  mov     qword ptr [rsp+14F0h+var_14A0+8], rax
0x1800247b2  mov     dword ptr [rsp+14F0h+var_1490], esi
0x1800247b6  mov     dword ptr [rsp+14F0h+var_1490+4], ebx
0x1800247ba  mov     qword ptr [rsp+14F0h+var_14B0+8], r15
0x1800247bf  mov     qword ptr [rsp+14F0h+var_14A0], r15
0x1800247c4  mov     qword ptr [rbp+13F0h+var_1450+8], rdi
0x1800247c8  mov     [rbp+13F0h+var_1440], r14
0x1800247cc  mov     qword ptr [rsp+14F0h+var_1490+8], r15
0x1800247d1  xorps   xmm0, xmm0
0x1800247d4  xor     eax, eax
0x1800247d6  movups  [rbp+13F0h+var_1470+8], xmm0
0x1800247da  mov     qword ptr [rbp+13F0h+var_1460+8], rax
0x1800247de  xorps   xmm1, xmm1
0x1800247e1  movups  [rsp+14F0h+var_1480], xmm1
0x1800247e6  mov     qword ptr [rbp+13F0h+var_1470], rax
0x1800247ea  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800247f1  test    rax, rax
0x1800247f4  jz      short loc_180024801
0x1800247f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247fb  mov     qword ptr [rbp+13F0h+var_1450], rax
0x1800247ff  jmp     short loc_180024805
0x180024801  mov     qword ptr [rbp+13F0h+var_1450], r15
0x180024805  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002480c  test    rax, rax
0x18002480f  jz      short loc_18002481B
0x180024811  lea     rcx, [rsp+14F0h+var_14D0]
0x180024816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002481b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180024822  test    rax, rax
0x180024825  jz      short loc_18002483B
0x180024827  mov     r8d, 400h
0x18002482d  lea     rdx, [rbp+13F0h+var_1430]
0x180024831  lea     rcx, [rsp+14F0h+var_14D0]
0x180024836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002483b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180024842  test    rax, rax
0x180024845  jz      short loc_180024851
0x180024847  lea     rcx, [rsp+14F0h+var_14D0]
0x18002484c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024851  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180024858  test    rax, rax
0x18002485b  jz      short loc_18002486E
0x18002485d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180024862  jnz     short loc_18002486E
0x180024864  lea     rcx, [rsp+14F0h+var_14D0]
0x180024869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002486e  cmp     dword ptr [rsp+14F0h+var_14D0+8], r15d
0x180024873  jge     loc_180024981
0x180024879  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180024880  jnz     short loc_1800248A1
0x180024882  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180024889  test    rax, rax
0x18002488c  jz      short loc_180024897
0x18002488e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024893  test    al, al
0x180024895  jmp     short loc_18002489F
0x180024897  call    cs:__imp_IsDebuggerPresent
0x18002489d  test    eax, eax
0x18002489f  jz      short loc_1800248A8
0x1800248a1  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800248a6  jz      short loc_1800248CE
0x1800248a8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800248af  test    rax, rax
0x1800248b2  jz      short loc_180024927
0x1800248b4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800248bb  jnz     short loc_180024927
0x1800248bd  xor     r8d, r8d
0x1800248c0  xor     edx, edx
0x1800248c2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800248c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248cc  jmp     short loc_180024927
0x1800248ce  mov     rax, cs:g_pfnResultLoggingCallback
0x1800248d5  test    rax, rax
0x1800248d8  jz      short loc_1800248FA
0x1800248da  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800248e1  jnz     short loc_1800248FA
0x1800248e3  mov     r8d, 800h
0x1800248e9  lea     rdx, [rbp+13F0h+OutputString]
0x1800248f0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800248f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248fa  cmp     [rbp+13F0h+OutputString], r15w
0x180024902  jnz     short loc_18002491A
0x180024904  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180024909  mov     edx, 800h; unsigned __int16 *
0x18002490e  lea     rcx, [rbp+13F0h+OutputString]; pszDest
0x180024915  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002491a  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180024921  call    cs:__imp_OutputDebugStringW
0x180024927  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18002492c  jnz     short loc_180024937
0x18002492e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180024935  jz      short loc_180024949
0x180024937  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002493e  test    rax, rax
0x180024941  jz      short loc_180024949
0x180024943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024948  nop
0x180024949  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18002494e  jnz     short loc_180024976
0x180024950  mov     rcx, [rbp+13F0h+var_30]
0x180024957  xor     rcx, rsp; StackCookie
0x18002495a  call    __security_check_cookie
0x18002495f  mov     rbx, [rsp+14F0h+arg_10]
0x180024967  add     rsp, 14D0h
0x18002496e  pop     r15
0x180024970  pop     r14
0x180024972  pop     rdi
0x180024973  pop     rsi
0x180024974  pop     rbp
0x180024975  retn
0x180024976  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18002497b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180024981  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
