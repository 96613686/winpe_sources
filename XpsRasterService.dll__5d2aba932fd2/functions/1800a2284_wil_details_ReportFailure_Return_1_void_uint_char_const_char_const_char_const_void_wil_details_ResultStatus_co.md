# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800a2284`
- end: `0x1800a252a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800a1ee8`

## callees

- `0x180003180`
- `0x180003cc4`
- `0x1800a0280`
- `0x1800a2284`
- `0x1800a3be4`
- `0x1800a49e0`
- `0x1800a50c8`
- `0x1800a52d0`
- `0x1800c3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a234a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a234a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a24c9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a24c9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a243f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a243f`

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
0x1800a2284  push    rbp
0x1800a2286  push    rbx
0x1800a2287  push    rsi
0x1800a2288  push    rdi
0x1800a2289  push    r12
0x1800a228b  push    r14
0x1800a228d  push    r15
0x1800a228f  lea     rbp, [rsp-13D0h]
0x1800a2297  mov     eax, 14D0h
0x1800a229c  call    _alloca_probe
0x1800a22a1  sub     rsp, rax
0x1800a22a4  mov     rax, cs:__security_cookie
0x1800a22ab  xor     rax, rsp
0x1800a22ae  mov     [rbp+1400h+var_40], rax
0x1800a22b5  mov     rsi, r8
0x1800a22b8  mov     edi, edx
0x1800a22ba  mov     rbx, rcx
0x1800a22bd  mov     r14, [rbp+1400h+arg_28]
0x1800a22c4  xor     edx, edx; Val
0x1800a22c6  mov     r8d, 98h; Size
0x1800a22cc  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800a22d1  call    memset_0
0x1800a22d6  nop
0x1800a22d7  xor     r12d, r12d
0x1800a22da  mov     [rbp+1400h+OutputString], r12w
0x1800a22e2  mov     [rbp+1400h+var_1440], r12b
0x1800a22e6  mov     rdx, [rbp+1400h+arg_30]; int
0x1800a22ed  mov     ecx, [rdx]; this
0x1800a22ef  mov     [rsp+1500h+var_14D8], ecx
0x1800a22f3  mov     eax, [rdx+4]
0x1800a22f6  mov     [rsp+1500h+var_14D4], eax
0x1800a22fa  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800a22ff  mov     r15d, eax
0x1800a2302  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800a230a  mov     ecx, r12d
0x1800a230d  lea     eax, [r12+8]
0x1800a2312  cmp     dword ptr [rdx+8], 1
0x1800a2316  cmovz   ecx, eax
0x1800a2319  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800a231d  lea     ecx, [rax-7]
0x1800a2320  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800a2328  inc     ecx
0x1800a232a  mov     [rsp+1500h+var_14D0], ecx
0x1800a232e  mov     rcx, [rbp+1400h+arg_38]
0x1800a2335  test    rcx, rcx
0x1800a2338  jz      short loc_1800A2345
0x1800a233a  cmp     [rcx], r12w
0x1800a233e  mov     [rsp+1500h+var_14C8], rcx
0x1800a2343  jnz     short loc_1800A234A
0x1800a2345  mov     [rsp+1500h+var_14C8], r12
0x1800a234a  call    cs:__imp_GetCurrentThreadId
0x1800a2350  mov     [rsp+1500h+var_14C0], eax
0x1800a2354  mov     [rsp+1500h+var_14A8], rsi
0x1800a2359  mov     [rsp+1500h+var_14A0], edi
0x1800a235d  mov     [rsp+1500h+var_149C], r15d
0x1800a2362  mov     [rsp+1500h+var_14B8], r12
0x1800a2367  mov     [rsp+1500h+var_14B0], r12
0x1800a236c  mov     [rbp+1400h+var_1458], r14
0x1800a2370  mov     [rbp+1400h+var_1450], rbx
0x1800a2374  mov     [rsp+1500h+var_1498], r12
0x1800a2379  xorps   xmm0, xmm0
0x1800a237c  xor     eax, eax
0x1800a237e  movups  [rbp+1400h+var_1478], xmm0
0x1800a2382  mov     [rbp+1400h+var_1468], rax
0x1800a2386  xorps   xmm1, xmm1
0x1800a2389  movups  [rsp+1500h+var_1490], xmm1
0x1800a238e  mov     [rbp+1400h+var_1480], rax
0x1800a2392  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800a2399  test    rax, rax
0x1800a239c  jz      short loc_1800A23A9
0x1800a239e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a23a3  mov     [rbp+1400h+var_1460], rax
0x1800a23a7  jmp     short loc_1800A23AD
0x1800a23a9  mov     [rbp+1400h+var_1460], r12
0x1800a23ad  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800a23b4  test    rax, rax
0x1800a23b7  jz      short loc_1800A23C3
0x1800a23b9  lea     rcx, [rsp+1500h+var_14E0]
0x1800a23be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a23c3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800a23ca  test    rax, rax
0x1800a23cd  jz      short loc_1800A23E3
0x1800a23cf  mov     r8d, 400h
0x1800a23d5  lea     rdx, [rbp+1400h+var_1440]
0x1800a23d9  lea     rcx, [rsp+1500h+var_14E0]
0x1800a23de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a23e3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800a23ea  test    rax, rax
0x1800a23ed  jz      short loc_1800A23F9
0x1800a23ef  lea     rcx, [rsp+1500h+var_14E0]
0x1800a23f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a23f9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800a2400  test    rax, rax
0x1800a2403  jz      short loc_1800A2416
0x1800a2405  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800a240a  jnz     short loc_1800A2416
0x1800a240c  lea     rcx, [rsp+1500h+var_14E0]
0x1800a2411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2416  cmp     [rsp+1500h+var_14D8], r12d
0x1800a241b  jge     loc_1800A2524
0x1800a2421  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800a2428  jnz     short loc_1800A2449
0x1800a242a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800a2431  test    rax, rax
0x1800a2434  jz      short loc_1800A243F
0x1800a2436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a243b  test    al, al
0x1800a243d  jmp     short loc_1800A2447
0x1800a243f  call    cs:__imp_IsDebuggerPresent
0x1800a2445  test    eax, eax
0x1800a2447  jz      short loc_1800A2450
0x1800a2449  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800a244e  jz      short loc_1800A2476
0x1800a2450  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a2457  test    rax, rax
0x1800a245a  jz      short loc_1800A24CF
0x1800a245c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800a2463  jnz     short loc_1800A24CF
0x1800a2465  xor     r8d, r8d
0x1800a2468  xor     edx, edx
0x1800a246a  lea     rcx, [rsp+1500h+var_14E0]
0x1800a246f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2474  jmp     short loc_1800A24CF
0x1800a2476  mov     ebx, 800h
0x1800a247b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a2482  test    rax, rax
0x1800a2485  jz      short loc_1800A24A4
0x1800a2487  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800a248e  jnz     short loc_1800A24A4
0x1800a2490  mov     r8d, ebx
0x1800a2493  lea     rdx, [rbp+1400h+OutputString]
0x1800a249a  lea     rcx, [rsp+1500h+var_14E0]
0x1800a249f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a24a4  cmp     [rbp+1400h+OutputString], r12w
0x1800a24ac  jnz     short loc_1800A24C2
0x1800a24ae  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800a24b3  mov     rdx, rbx; wchar_t *
0x1800a24b6  lea     rcx, [rbp+1400h+OutputString]; this
0x1800a24bd  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800a24c2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800a24c9  call    cs:__imp_OutputDebugStringW
0x1800a24cf  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800a24d4  jnz     short loc_1800A24DF
0x1800a24d6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800a24dd  jz      short loc_1800A24F1
0x1800a24df  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800a24e6  test    rax, rax
0x1800a24e9  jz      short loc_1800A24F1
0x1800a24eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a24f0  nop
0x1800a24f1  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800a24f6  jnz     short loc_1800A2519
0x1800a24f8  mov     rcx, [rbp+1400h+var_40]
0x1800a24ff  xor     rcx, rsp; StackCookie
0x1800a2502  call    __security_check_cookie
0x1800a2507  add     rsp, 14D0h
0x1800a250e  pop     r15
0x1800a2510  pop     r14
0x1800a2512  pop     r12
0x1800a2514  pop     rdi
0x1800a2515  pop     rsi
0x1800a2516  pop     rbx
0x1800a2517  pop     rbp
0x1800a2518  retn
0x1800a2519  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800a251e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800a2524  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
