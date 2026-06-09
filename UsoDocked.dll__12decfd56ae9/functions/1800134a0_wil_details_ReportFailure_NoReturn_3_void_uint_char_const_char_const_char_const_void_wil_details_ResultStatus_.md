# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800134a0`
- end: `0x180013719`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001320c`

## callees

- `0x18000856c`
- `0x1800134a0`
- `0x180015e04`
- `0x180016650`
- `0x180017360`
- `0x180019bc0`
- `0x180068320`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013559`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013559`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001365c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001365c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800136e6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800136e6`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
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
0x1800134a0  mov     [rsp-8+arg_18], rbx
0x1800134a5  push    rbp
0x1800134a6  push    rsi
0x1800134a7  push    rdi
0x1800134a8  push    r12
0x1800134aa  push    r13
0x1800134ac  push    r14
0x1800134ae  push    r15
0x1800134b0  lea     rbp, [rsp-13C0h]
0x1800134b8  mov     eax, 14C0h
0x1800134bd  call    _alloca_probe
0x1800134c2  sub     rsp, rax
0x1800134c5  mov     r14, r8
0x1800134c8  mov     esi, edx
0x1800134ca  mov     rdi, rcx
0x1800134cd  mov     r15, [rbp+13F0h+arg_28]
0x1800134d4  xor     edx, edx; Val
0x1800134d6  mov     r8d, 98h; Size
0x1800134dc  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800134e1  call    memset_0
0x1800134e6  nop
0x1800134e7  xor     r13d, r13d
0x1800134ea  mov     [rbp+13F0h+OutputString], r13w
0x1800134f2  mov     [rbp+13F0h+var_1430], r13b
0x1800134f6  mov     rbx, [rbp+13F0h+arg_30]
0x1800134fd  mov     ecx, [rbx]; this
0x1800134ff  mov     [rsp+14F0h+var_14C8], ecx
0x180013503  mov     eax, [rbx+4]
0x180013506  mov     [rsp+14F0h+var_14C4], eax
0x18001350a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001350f  mov     r12d, eax
0x180013512  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18001351a  mov     ecx, r13d
0x18001351d  lea     eax, [r13+8]
0x180013521  cmp     dword ptr [rbx+8], 1
0x180013525  cmovz   ecx, eax
0x180013528  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001352c  lea     ecx, [rax-7]
0x18001352f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180013537  inc     ecx
0x180013539  mov     [rsp+14F0h+var_14C0], ecx
0x18001353d  mov     rcx, [rbp+13F0h+arg_38]
0x180013544  test    rcx, rcx
0x180013547  jz      short loc_180013554
0x180013549  cmp     [rcx], r13w
0x18001354d  mov     [rsp+14F0h+var_14B8], rcx
0x180013552  jnz     short loc_180013559
0x180013554  mov     [rsp+14F0h+var_14B8], r13
0x180013559  call    cs:__imp_GetCurrentThreadId
0x18001355f  mov     [rsp+14F0h+var_14B0], eax
0x180013563  mov     [rsp+14F0h+var_1498], r14
0x180013568  mov     [rsp+14F0h+var_1490], esi
0x18001356c  mov     [rsp+14F0h+var_148C], r12d
0x180013571  mov     [rsp+14F0h+var_14A8], r13
0x180013576  mov     [rsp+14F0h+var_14A0], r13
0x18001357b  mov     [rbp+13F0h+var_1448], r15
0x18001357f  mov     [rbp+13F0h+var_1440], rdi
0x180013583  mov     [rsp+14F0h+var_1488], r13
0x180013588  xorps   xmm0, xmm0
0x18001358b  xor     eax, eax
0x18001358d  movups  [rbp+13F0h+var_1468], xmm0
0x180013591  mov     [rbp+13F0h+var_1458], rax
0x180013595  xorps   xmm1, xmm1
0x180013598  movups  [rsp+14F0h+var_1480], xmm1
0x18001359d  mov     [rbp+13F0h+var_1470], rax
0x1800135a1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800135a8  test    rax, rax
0x1800135ab  jz      short loc_1800135B8
0x1800135ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135b2  mov     [rbp+13F0h+var_1450], rax
0x1800135b6  jmp     short loc_1800135BC
0x1800135b8  mov     [rbp+13F0h+var_1450], r13
0x1800135bc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800135c3  test    rax, rax
0x1800135c6  jz      short loc_1800135D2
0x1800135c8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800135cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135d2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800135d9  test    rax, rax
0x1800135dc  jz      short loc_1800135F2
0x1800135de  mov     r8d, 400h
0x1800135e4  lea     rdx, [rbp+13F0h+var_1430]
0x1800135e8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800135ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135f2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800135f9  test    rax, rax
0x1800135fc  jz      short loc_180013608
0x1800135fe  lea     rcx, [rsp+14F0h+var_14D0]
0x180013603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013608  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001360f  test    rax, rax
0x180013612  jz      short loc_180013625
0x180013614  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180013619  jnz     short loc_180013625
0x18001361b  lea     rcx, [rsp+14F0h+var_14D0]
0x180013620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013625  cmp     [rsp+14F0h+var_14C8], r13d
0x18001362a  jl      short loc_18001363E
0x18001362c  mov     ecx, 8000FFFFh; this
0x180013631  mov     [rsp+14F0h+var_14C8], ecx
0x180013635  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001363a  mov     [rsp+14F0h+var_14C4], eax
0x18001363e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180013645  jnz     short loc_180013666
0x180013647  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001364e  test    rax, rax
0x180013651  jz      short loc_18001365C
0x180013653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013658  test    al, al
0x18001365a  jmp     short loc_180013664
0x18001365c  call    cs:__imp_IsDebuggerPresent
0x180013662  test    eax, eax
0x180013664  jz      short loc_18001366D
0x180013666  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001366b  jz      short loc_180013693
0x18001366d  mov     rax, cs:g_pfnResultLoggingCallback
0x180013674  test    rax, rax
0x180013677  jz      short loc_1800136EC
0x180013679  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180013680  jnz     short loc_1800136EC
0x180013682  xor     r8d, r8d
0x180013685  xor     edx, edx
0x180013687  lea     rcx, [rsp+14F0h+var_14D0]
0x18001368c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013691  jmp     short loc_1800136EC
0x180013693  mov     ebx, 800h
0x180013698  mov     rax, cs:g_pfnResultLoggingCallback
0x18001369f  test    rax, rax
0x1800136a2  jz      short loc_1800136C1
0x1800136a4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800136ab  jnz     short loc_1800136C1
0x1800136ad  mov     r8d, ebx
0x1800136b0  lea     rdx, [rbp+13F0h+OutputString]
0x1800136b7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800136bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136c1  cmp     [rbp+13F0h+OutputString], r13w
0x1800136c9  jnz     short loc_1800136DF
0x1800136cb  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800136d0  mov     rdx, rbx; unsigned __int16 *
0x1800136d3  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800136da  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800136df  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800136e6  call    cs:__imp_OutputDebugStringW
0x1800136ec  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800136f1  jnz     short loc_1800136FC
0x1800136f3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800136fa  jz      short loc_18001370E
0x1800136fc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180013703  test    rax, rax
0x180013706  jz      short loc_18001370E
0x180013708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001370d  nop
0x18001370e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180013713  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
