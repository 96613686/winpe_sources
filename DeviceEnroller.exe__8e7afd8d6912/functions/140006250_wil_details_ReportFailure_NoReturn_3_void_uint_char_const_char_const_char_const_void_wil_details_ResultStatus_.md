# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140006250`
- end: `0x1400064c9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140005f38`

## callees

- `0x140004e28`
- `0x140006250`
- `0x140007f74`
- `0x14000887c`
- `0x1400091c0`
- `0x14000a510`
- `0x140059180`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006309`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006309`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000640c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000640c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006496`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006496`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
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
0x140006250  mov     [rsp-8+arg_18], rbx
0x140006255  push    rbp
0x140006256  push    rsi
0x140006257  push    rdi
0x140006258  push    r12
0x14000625a  push    r13
0x14000625c  push    r14
0x14000625e  push    r15
0x140006260  lea     rbp, [rsp-13C0h]
0x140006268  mov     eax, 14C0h
0x14000626d  call    _alloca_probe
0x140006272  sub     rsp, rax
0x140006275  mov     r14, r8
0x140006278  mov     esi, edx
0x14000627a  mov     rdi, rcx
0x14000627d  mov     r15, [rbp+13F0h+arg_28]
0x140006284  xor     edx, edx; Val
0x140006286  mov     r8d, 98h; Size
0x14000628c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140006291  call    memset_0
0x140006296  nop
0x140006297  xor     r13d, r13d
0x14000629a  mov     [rbp+13F0h+OutputString], r13w
0x1400062a2  mov     [rbp+13F0h+var_1430], r13b
0x1400062a6  mov     rbx, [rbp+13F0h+arg_30]
0x1400062ad  mov     ecx, [rbx]; this
0x1400062af  mov     [rsp+14F0h+var_14C8], ecx
0x1400062b3  mov     eax, [rbx+4]
0x1400062b6  mov     [rsp+14F0h+var_14C4], eax
0x1400062ba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400062bf  mov     r12d, eax
0x1400062c2  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1400062ca  mov     ecx, r13d
0x1400062cd  lea     eax, [r13+8]
0x1400062d1  cmp     dword ptr [rbx+8], 1
0x1400062d5  cmovz   ecx, eax
0x1400062d8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400062dc  lea     ecx, [rax-7]
0x1400062df  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400062e7  inc     ecx
0x1400062e9  mov     [rsp+14F0h+var_14C0], ecx
0x1400062ed  mov     rcx, [rbp+13F0h+arg_38]
0x1400062f4  test    rcx, rcx
0x1400062f7  jz      short loc_140006304
0x1400062f9  cmp     [rcx], r13w
0x1400062fd  mov     [rsp+14F0h+var_14B8], rcx
0x140006302  jnz     short loc_140006309
0x140006304  mov     [rsp+14F0h+var_14B8], r13
0x140006309  call    cs:__imp_GetCurrentThreadId
0x14000630f  mov     [rsp+14F0h+var_14B0], eax
0x140006313  mov     [rsp+14F0h+var_1498], r14
0x140006318  mov     [rsp+14F0h+var_1490], esi
0x14000631c  mov     [rsp+14F0h+var_148C], r12d
0x140006321  mov     [rsp+14F0h+var_14A8], r13
0x140006326  mov     [rsp+14F0h+var_14A0], r13
0x14000632b  mov     [rbp+13F0h+var_1448], r15
0x14000632f  mov     [rbp+13F0h+var_1440], rdi
0x140006333  mov     [rsp+14F0h+var_1488], r13
0x140006338  xorps   xmm0, xmm0
0x14000633b  xor     eax, eax
0x14000633d  movups  [rbp+13F0h+var_1468], xmm0
0x140006341  mov     [rbp+13F0h+var_1458], rax
0x140006345  xorps   xmm1, xmm1
0x140006348  movups  [rsp+14F0h+var_1480], xmm1
0x14000634d  mov     [rbp+13F0h+var_1470], rax
0x140006351  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006358  test    rax, rax
0x14000635b  jz      short loc_140006368
0x14000635d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006362  mov     [rbp+13F0h+var_1450], rax
0x140006366  jmp     short loc_14000636C
0x140006368  mov     [rbp+13F0h+var_1450], r13
0x14000636c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006373  test    rax, rax
0x140006376  jz      short loc_140006382
0x140006378  lea     rcx, [rsp+14F0h+var_14D0]
0x14000637d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006382  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140006389  test    rax, rax
0x14000638c  jz      short loc_1400063A2
0x14000638e  mov     r8d, 400h
0x140006394  lea     rdx, [rbp+13F0h+var_1430]
0x140006398  lea     rcx, [rsp+14F0h+var_14D0]
0x14000639d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400063a2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400063a9  test    rax, rax
0x1400063ac  jz      short loc_1400063B8
0x1400063ae  lea     rcx, [rsp+14F0h+var_14D0]
0x1400063b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400063b8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400063bf  test    rax, rax
0x1400063c2  jz      short loc_1400063D5
0x1400063c4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400063c9  jnz     short loc_1400063D5
0x1400063cb  lea     rcx, [rsp+14F0h+var_14D0]
0x1400063d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400063d5  cmp     [rsp+14F0h+var_14C8], r13d
0x1400063da  jl      short loc_1400063EE
0x1400063dc  mov     ecx, 8000FFFFh; this
0x1400063e1  mov     [rsp+14F0h+var_14C8], ecx
0x1400063e5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400063ea  mov     [rsp+14F0h+var_14C4], eax
0x1400063ee  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1400063f5  jnz     short loc_140006416
0x1400063f7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400063fe  test    rax, rax
0x140006401  jz      short loc_14000640C
0x140006403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006408  test    al, al
0x14000640a  jmp     short loc_140006414
0x14000640c  call    cs:__imp_IsDebuggerPresent
0x140006412  test    eax, eax
0x140006414  jz      short loc_14000641D
0x140006416  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000641b  jz      short loc_140006443
0x14000641d  mov     rax, cs:g_pfnResultLoggingCallback
0x140006424  test    rax, rax
0x140006427  jz      short loc_14000649C
0x140006429  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140006430  jnz     short loc_14000649C
0x140006432  xor     r8d, r8d
0x140006435  xor     edx, edx
0x140006437  lea     rcx, [rsp+14F0h+var_14D0]
0x14000643c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006441  jmp     short loc_14000649C
0x140006443  mov     ebx, 800h
0x140006448  mov     rax, cs:g_pfnResultLoggingCallback
0x14000644f  test    rax, rax
0x140006452  jz      short loc_140006471
0x140006454  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14000645b  jnz     short loc_140006471
0x14000645d  mov     r8d, ebx
0x140006460  lea     rdx, [rbp+13F0h+OutputString]
0x140006467  lea     rcx, [rsp+14F0h+var_14D0]
0x14000646c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006471  cmp     [rbp+13F0h+OutputString], r13w
0x140006479  jnz     short loc_14000648F
0x14000647b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140006480  mov     rdx, rbx; unsigned __int16 *
0x140006483  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000648a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000648f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140006496  call    cs:__imp_OutputDebugStringW
0x14000649c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400064a1  jnz     short loc_1400064AC
0x1400064a3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1400064aa  jz      short loc_1400064BE
0x1400064ac  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400064b3  test    rax, rax
0x1400064b6  jz      short loc_1400064BE
0x1400064b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064bd  nop
0x1400064be  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400064c3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
