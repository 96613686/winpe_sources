# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180009274`
- end: `0x1800094ff`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180009084`

## callees

- `0x180001fd4`
- `0x180009274`
- `0x180009a4c`
- `0x180009fd0`
- `0x18000ac50`
- `0x18000acc4`
- `0x18001db90`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000932d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000932d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800094c6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800094c6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009436`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009436`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
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
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180009274  mov     [rsp-8+arg_18], rbx
0x180009279  push    rbp
0x18000927a  push    rsi
0x18000927b  push    rdi
0x18000927c  push    r12
0x18000927e  push    r13
0x180009280  push    r14
0x180009282  push    r15
0x180009284  lea     rbp, [rsp-13C0h]
0x18000928c  mov     eax, 14C0h
0x180009291  call    _alloca_probe
0x180009296  sub     rsp, rax
0x180009299  mov     r14, r8
0x18000929c  mov     esi, edx
0x18000929e  mov     rdi, rcx
0x1800092a1  mov     r15, [rbp+13F0h+arg_28]
0x1800092a8  xor     edx, edx; Val
0x1800092aa  mov     r8d, 98h; Size
0x1800092b0  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800092b5  call    memset_0
0x1800092ba  nop
0x1800092bb  xor     r13d, r13d
0x1800092be  mov     [rbp+13F0h+OutputString], r13w
0x1800092c6  mov     [rbp+13F0h+var_1430], r13b
0x1800092ca  mov     rbx, [rbp+13F0h+arg_30]
0x1800092d1  mov     ecx, [rbx]; this
0x1800092d3  mov     [rsp+14F0h+var_14C8], ecx
0x1800092d7  mov     eax, [rbx+4]
0x1800092da  mov     [rsp+14F0h+var_14C4], eax
0x1800092de  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800092e3  mov     r12d, eax
0x1800092e6  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800092ee  mov     ecx, r13d
0x1800092f1  lea     eax, [r13+8]
0x1800092f5  cmp     dword ptr [rbx+8], 1
0x1800092f9  cmovz   ecx, eax
0x1800092fc  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180009300  lea     ecx, [rax-7]
0x180009303  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000930b  inc     ecx
0x18000930d  mov     [rsp+14F0h+var_14C0], ecx
0x180009311  mov     rcx, [rbp+13F0h+arg_38]
0x180009318  test    rcx, rcx
0x18000931b  jz      short loc_180009328
0x18000931d  cmp     [rcx], r13w
0x180009321  mov     [rsp+14F0h+var_14B8], rcx
0x180009326  jnz     short loc_18000932D
0x180009328  mov     [rsp+14F0h+var_14B8], r13
0x18000932d  call    cs:__imp_GetCurrentThreadId
0x180009334  nop     dword ptr [rax+rax+00h]
0x180009339  mov     [rsp+14F0h+var_14B0], eax
0x18000933d  mov     [rsp+14F0h+var_1498], r14
0x180009342  mov     [rsp+14F0h+var_1490], esi
0x180009346  mov     [rsp+14F0h+var_148C], r12d
0x18000934b  mov     [rsp+14F0h+var_14A8], r13
0x180009350  mov     [rsp+14F0h+var_14A0], r13
0x180009355  mov     [rbp+13F0h+var_1448], r15
0x180009359  mov     [rbp+13F0h+var_1440], rdi
0x18000935d  mov     [rsp+14F0h+var_1488], r13
0x180009362  xorps   xmm0, xmm0
0x180009365  xor     eax, eax
0x180009367  movups  [rbp+13F0h+var_1468], xmm0
0x18000936b  mov     [rbp+13F0h+var_1458], rax
0x18000936f  xorps   xmm1, xmm1
0x180009372  movups  [rsp+14F0h+var_1480], xmm1
0x180009377  mov     [rbp+13F0h+var_1470], rax
0x18000937b  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009382  test    rax, rax
0x180009385  jz      short loc_180009392
0x180009387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000938c  mov     [rbp+13F0h+var_1450], rax
0x180009390  jmp     short loc_180009396
0x180009392  mov     [rbp+13F0h+var_1450], r13
0x180009396  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000939d  test    rax, rax
0x1800093a0  jz      short loc_1800093AC
0x1800093a2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800093a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093ac  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800093b3  test    rax, rax
0x1800093b6  jz      short loc_1800093CC
0x1800093b8  mov     r8d, 400h
0x1800093be  lea     rdx, [rbp+13F0h+var_1430]
0x1800093c2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800093c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093cc  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800093d3  test    rax, rax
0x1800093d6  jz      short loc_1800093E2
0x1800093d8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800093dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093e2  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800093e9  test    rax, rax
0x1800093ec  jz      short loc_1800093FF
0x1800093ee  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800093f3  jnz     short loc_1800093FF
0x1800093f5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800093fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093ff  cmp     [rsp+14F0h+var_14C8], r13d
0x180009404  jl      short loc_180009418
0x180009406  mov     ecx, 8000FFFFh; this
0x18000940b  mov     [rsp+14F0h+var_14C8], ecx
0x18000940f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009414  mov     [rsp+14F0h+var_14C4], eax
0x180009418  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000941f  jnz     short loc_180009446
0x180009421  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009428  test    rax, rax
0x18000942b  jz      short loc_180009436
0x18000942d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009432  test    al, al
0x180009434  jmp     short loc_180009444
0x180009436  call    cs:__imp_IsDebuggerPresent
0x18000943d  nop     dword ptr [rax+rax+00h]
0x180009442  test    eax, eax
0x180009444  jz      short loc_18000944D
0x180009446  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000944b  jz      short loc_180009473
0x18000944d  mov     rax, cs:g_pfnResultLoggingCallback
0x180009454  test    rax, rax
0x180009457  jz      short loc_1800094D2
0x180009459  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180009460  jnz     short loc_1800094D2
0x180009462  xor     r8d, r8d
0x180009465  xor     edx, edx
0x180009467  lea     rcx, [rsp+14F0h+var_14D0]
0x18000946c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009471  jmp     short loc_1800094D2
0x180009473  mov     ebx, 800h
0x180009478  mov     rax, cs:g_pfnResultLoggingCallback
0x18000947f  test    rax, rax
0x180009482  jz      short loc_1800094A1
0x180009484  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000948b  jnz     short loc_1800094A1
0x18000948d  mov     r8d, ebx
0x180009490  lea     rdx, [rbp+13F0h+OutputString]
0x180009497  lea     rcx, [rsp+14F0h+var_14D0]
0x18000949c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094a1  cmp     [rbp+13F0h+OutputString], r13w
0x1800094a9  jnz     short loc_1800094BF
0x1800094ab  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800094b0  mov     rdx, rbx; unsigned __int16 *
0x1800094b3  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800094ba  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800094bf  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800094c6  call    cs:__imp_OutputDebugStringW
0x1800094cd  nop     dword ptr [rax+rax+00h]
0x1800094d2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800094d7  jnz     short loc_1800094E2
0x1800094d9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800094e0  jz      short loc_1800094F4
0x1800094e2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800094e9  test    rax, rax
0x1800094ec  jz      short loc_1800094F4
0x1800094ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094f3  nop
0x1800094f4  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800094f9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
